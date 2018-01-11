---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "構成データの使用"
ms.openlocfilehash: 60c6c2d5694a03275e1a08522bdcf4b1bc5bb068
ms.sourcegitcommit: 60f06a06c2fce63024f3f4cbd7657b1dfe7fcb1a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="using-configuration-data-in-dsc"></a><span data-ttu-id="ee32f-103">DSC で構成データを使用する</span><span class="sxs-lookup"><span data-stu-id="ee32f-103">Using configuration data in DSC</span></span>

><span data-ttu-id="ee32f-104">適用先: Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="ee32f-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="ee32f-105">組み込みの DSC **ConfigurationData** パラメーターを使用して、構成内で使用可能なデータを定義することができます。</span><span class="sxs-lookup"><span data-stu-id="ee32f-105">By using the built-in DSC **ConfigurationData** parameter, you can define data that can be used within a configuration.</span></span> <span data-ttu-id="ee32f-106">これにより、複数のノードや異なる環境で使用可能な 1 つの構成を作成できます。</span><span class="sxs-lookup"><span data-stu-id="ee32f-106">This allows you to create a single configuration that can be used for multiple nodes or for different environments.</span></span> <span data-ttu-id="ee32f-107">たとえば、アプリケーションを開発している場合は、開発環境と運用環境の両方に 1 つの構成を使用し、構成データを使用して各環境のデータを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="ee32f-107">For example, if you are developing an application, you can use one configuration for both development and production environments, and use configuration data to specify data for each environment.</span></span>

<span data-ttu-id="ee32f-108">このトピックでは、**ConfigurationData** ハッシュテーブルの構造について説明します。</span><span class="sxs-lookup"><span data-stu-id="ee32f-108">This topic describes the structure of the **ConfigurationData** hashtable.</span></span> <span data-ttu-id="ee32f-109">構成データの使用方法の例については、「[構成データと環境データの分離](separatingEnvData.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ee32f-109">For examples of how to use configuration data, see [Separating configuration and environment data](separatingEnvData.md).</span></span>

## <a name="the-configurationdata-common-parameter"></a><span data-ttu-id="ee32f-110">共通の ConfigurationData パラメーター</span><span class="sxs-lookup"><span data-stu-id="ee32f-110">The ConfigurationData common parameter</span></span>

<span data-ttu-id="ee32f-111">DSC 構成では、**ConfigurationData** という共通パラメーターを使用します。このパラメーターは、構成をコンパイルするときに指定します。</span><span class="sxs-lookup"><span data-stu-id="ee32f-111">A DSC configuration takes a common parameter, **ConfigurationData**, that you specify when you compile the configuration.</span></span> <span data-ttu-id="ee32f-112">構成をコンパイルする方法の詳細については、「[DSC 構成](configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee32f-112">For information about compiling configurations, see [DSC configurations](configurations.md).</span></span>

<span data-ttu-id="ee32f-113">**ConfigurationData** パラメーターはハッシュテーブルであり、**AllNodes** という名前のキーが少なくとも 1 つ必要です。</span><span class="sxs-lookup"><span data-stu-id="ee32f-113">The **ConfigurationData** parameter is a hasthtable that must have at least one key named **AllNodes**.</span></span> <span data-ttu-id="ee32f-114">その他のキーを 1 つ以上含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="ee32f-114">It can also have one or more other keys.</span></span>

><span data-ttu-id="ee32f-115">**注:**このトピックの例では、(**AllNodes** というキーではなく) `NonNodeData` という追加のキーを 1 つしか使用していませんが、追加するキーの数に制限はなく、名前も自由に付けることができます。</span><span class="sxs-lookup"><span data-stu-id="ee32f-115">**Note:** The examples in this topic use a single additional key (other than the named **AllNodes** key) named `NonNodeData`, but you can include any number of additional keys, and name them whatever you want.</span></span>

```powershell
$MyData = 
@{
    AllNodes = @()
    NonNodeData = ""   
}
```

<span data-ttu-id="ee32f-116">**AllNodes** キーの値は配列です。</span><span class="sxs-lookup"><span data-stu-id="ee32f-116">The value of the **AllNodes** key is an array.</span></span> <span data-ttu-id="ee32f-117">この配列の各要素もハッシュ テーブルであり、**NodeName** という名前のキーが少なくとも 1 つ必要です。</span><span class="sxs-lookup"><span data-stu-id="ee32f-117">Each element of this array is also a hash table that must have at least one key named **NodeName**:</span></span>

```powershell
$MyData = 
@{
    AllNodes = 
    @(
        @{
            NodeName = "VM-1"
        },

 
        @{
            NodeName = "VM-2"
        },

 
        @{
            NodeName = "VM-3"
        }
    );

    NonNodeData = ""   
}
```

<span data-ttu-id="ee32f-118">各ハッシュテーブルには他のキーを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="ee32f-118">You can add other keys to each hash table as well:</span></span>

```powershell
$MyData = 
@{
    AllNodes = 
    @(
        @{
            NodeName = "VM-1"
            Role     = "WebServer"
        },

 
        @{
            NodeName = "VM-2"
            Role     = "SQLServer"
        },

 
        @{
            NodeName = "VM-3"
            Role     = "WebServer"
        }
    );

    NonNodeData = ""   
}
```

<span data-ttu-id="ee32f-119">すべてのノードにプロパティを適用するには、**AllNodes** 配列に **NodeName** が `*` のメンバーを作成します。</span><span class="sxs-lookup"><span data-stu-id="ee32f-119">To apply a property to all nodes, you can create a member of the **AllNodes** array that has a **NodeName** of `*`.</span></span> <span data-ttu-id="ee32f-120">たとえば、すべてのノードに `LogPath` プロパティを適用するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="ee32f-120">For example, to give every node a `LogPath` property, you could do this:</span></span>

```powershell
$MyData = 
@{
    AllNodes = 
    @(
        @{
            NodeName     = "*"
            LogPath      = "C:\Logs"
        },

 
        @{
            NodeName     = "VM-1"
            Role         = "WebServer"
            SiteContents = "C:\Site1"
            SiteName     = "Website1"
        },

 
        @{
            NodeName     = "VM-2"
            Role         = "SQLServer"
        },

 
        @{
            NodeName     = "VM-3"
            Role         = "WebServer"
            SiteContents = "C:\Site2"
            SiteName     = "Website3"
        }
    );
}
```

<span data-ttu-id="ee32f-121">これは、名前が `LogPath` で `"C:\Logs"` の値を持つプロパティを、その他のブロック (`VM-1`、`VM-2`、および `VM-3`) にそれぞれ追加するのと同じことです。</span><span class="sxs-lookup"><span data-stu-id="ee32f-121">This is the equivalent of adding a property with a name of `LogPath` with a value of `"C:\Logs"` to each of the other blocks (`VM-1`, `VM-2`, and `VM-3`).</span></span>

## <a name="defining-the-configurationdata-hashtable"></a><span data-ttu-id="ee32f-122">ConfigurationData ハッシュテーブルの定義</span><span class="sxs-lookup"><span data-stu-id="ee32f-122">Defining the ConfigurationData hashtable</span></span>

<span data-ttu-id="ee32f-123">**ConfigurationData** は、(これまでの例のように) 構成として同じスクリプト ファイル内に変数として定義するか、または別個の `.psd1` ファイル内に定義することができます。</span><span class="sxs-lookup"><span data-stu-id="ee32f-123">You can define **ConfigurationData** either as a variable within the same script file as a configuration (as in our previous examples) or in a separate `.psd1` file.</span></span> <span data-ttu-id="ee32f-124">**ConfigurationData** を `.psd1` ファイル内で定義するには、構成データを表すハッシュテーブルのみが含まれるファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="ee32f-124">To define **ConfigurationData** in a `.psd1` file, create a file that contains only the hashtable that represents the configuration data.</span></span>

<span data-ttu-id="ee32f-125">たとえば、次の内容を含む `MyData.psd1` という名前のファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="ee32f-125">For example, you could create a file named `MyData.psd1` with the following contents:</span></span>

```powershell
@{
    AllNodes =
    @(
        @{
            NodeName    = 'VM-1'
            FeatureName = 'Web-Server'
        },

        @{
            NodeName    = 'VM-2'
            FeatureName = 'Hyper-V'
        }
    )
}
```

## <a name="compiling-a-configuration-with-configuration-data"></a><span data-ttu-id="ee32f-126">構成データで構成をコンパイルする</span><span class="sxs-lookup"><span data-stu-id="ee32f-126">Compiling a configuration with configuration data</span></span>

<span data-ttu-id="ee32f-127">構成データを定義した構成をコンパイルするには、**ConfigurationData** パラメーターの値として構成データを渡します。</span><span class="sxs-lookup"><span data-stu-id="ee32f-127">To compile a configuration for which you have defined configuration data, you pass the configuration data as the value of the **ConfigurationData** parameter.</span></span>

<span data-ttu-id="ee32f-128">これにより、**AllNodes** 配列の各エントリで MOF ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="ee32f-128">This will create a MOF file for each entry in the **AllNodes** array.</span></span>
<span data-ttu-id="ee32f-129">各 MOF ファイルの名前には、対応する配列エントリの `NodeName` プロパティが使用されます。</span><span class="sxs-lookup"><span data-stu-id="ee32f-129">Each MOF file will be named with the `NodeName` property of the corresponding array entry.</span></span>

<span data-ttu-id="ee32f-130">たとえば、上記 `MyData.psd1` ファイルのように構成データを定義する場合、構成をコンパイルすると `VM-1.mof` ファイルと `VM-2.mof` ファイルの両方が作成されます。</span><span class="sxs-lookup"><span data-stu-id="ee32f-130">For example, if you define configuration data as in the `MyData.psd1` file above, compiling a configuration would create both `VM-1.mof` and `VM-2.mof` files.</span></span>

### <a name="compiling-a-configuration-with-configuration-data-using-a-variable"></a><span data-ttu-id="ee32f-131">変数を用いた構成データで構成をコンパイルする</span><span class="sxs-lookup"><span data-stu-id="ee32f-131">Compiling a configuration with configuration data using a variable</span></span>

<span data-ttu-id="ee32f-132">構成として同じ `.ps1` ファイル内の変数として定義された構成データを使用するには、構成をコンパイルするときに、**ConfigurationData** パラメーターの値として変数名を渡します。</span><span class="sxs-lookup"><span data-stu-id="ee32f-132">To use configuration data that is defined as a variable in the same `.ps1` file as the configuration, you pass the variable name as the value of the **ConfigurationData** parameter when compiling the configuration:</span></span>

```powershell
MyDscConfiguration -ConfigurationData $MyData
```

### <a name="compiling-a-configuration-with-configuration-data-using-a-data-file"></a><span data-ttu-id="ee32f-133">データ ファイルを用いた構成データで構成をコンパイルする</span><span class="sxs-lookup"><span data-stu-id="ee32f-133">Compiling a configuration with configuration data using a data file</span></span>

<span data-ttu-id="ee32f-134">.psd1 ファイルに定義された構成データを使用するには、構成のコンパイル時に、そのファイルのパスと名前を **ConfigurationData** パラメーターの値として渡します。</span><span class="sxs-lookup"><span data-stu-id="ee32f-134">To use configuration data that is defined in a .psd1 file, you pass the path and name of that file as the value of the **ConfigurationData** parameter when compiling the configuration:</span></span>

```powershell
MyDscConfiguration -ConfigurationData .\MyData.psd1
```

## <a name="using-configurationdata-variables-in-a-configuration"></a><span data-ttu-id="ee32f-135">構成での ConfigurationData 変数の使用</span><span class="sxs-lookup"><span data-stu-id="ee32f-135">Using ConfigurationData variables in a configuration</span></span>

<span data-ttu-id="ee32f-136">DSC には、構成スクリプトで使用できる 3 つの特殊な変数 **$AllNodes**、**$Node**、および**$ConfigurationData** が用意されています。</span><span class="sxs-lookup"><span data-stu-id="ee32f-136">DSC provides three special variables that can be used in a configuration script: **$AllNodes**, **$Node**, and **$ConfigurationData**.</span></span>

- <span data-ttu-id="ee32f-137">**$AllNodes** は、**ConfigurationData** で定義されたノードのコレクション全体を参照します。</span><span class="sxs-lookup"><span data-stu-id="ee32f-137">**$AllNodes** refers to the entire collection of nodes defined in **ConfigurationData**.</span></span> <span data-ttu-id="ee32f-138">**.Where()** と **.ForEach()** を使用すると、**AllNodes** コレクションをフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="ee32f-138">You can filter the **AllNodes** collection by using **.Where()** and **.ForEach()**.</span></span>
- <span data-ttu-id="ee32f-139">**Node** は、**.Where()** または **.ForEach()** を使用してフィルター処理された後の **AllNodes** コレクション内にある特定のエントリを参照します。</span><span class="sxs-lookup"><span data-stu-id="ee32f-139">**Node** refers to a particular entry in the **AllNodes** collection after it is filtered by using **.Where()** or **.ForEach()**.</span></span>
- <span data-ttu-id="ee32f-140">**ConfigurationData** は、構成のコンパイル時にパラメーターとして渡されるハッシュ テーブル全体を参照します。</span><span class="sxs-lookup"><span data-stu-id="ee32f-140">**ConfigurationData** refers to the entire hash table that is passed as the parameter when compiling a configuration.</span></span>

## <a name="using-non-node-data"></a><span data-ttu-id="ee32f-141">ノード外のデータを使用する</span><span class="sxs-lookup"><span data-stu-id="ee32f-141">Using non-node data</span></span>

<span data-ttu-id="ee32f-142">上記の例でわかるように、**ConfigurationData** ハッシュテーブルには、必須の **AllNodes** キーだけでなく、複数のキーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="ee32f-142">As we've seen in previous examples, the **ConfigurationData** hashtable can have one or more keys in addition to the required **AllNodes** key.</span></span>
<span data-ttu-id="ee32f-143">このトピックの例では、追加ノードを 1 つだけ使用し、`NonNodeData` という名前を付けました。</span><span class="sxs-lookup"><span data-stu-id="ee32f-143">In the examples in this topic, we have used only a single additional node, and named it `NonNodeData`.</span></span> <span data-ttu-id="ee32f-144">実際は、定義できる追加のキーの数に制限はなく、名前も自由に設定できます。</span><span class="sxs-lookup"><span data-stu-id="ee32f-144">However, you can define any number of additional keys, and name them anything you want.</span></span>

<span data-ttu-id="ee32f-145">ノード以外のデータを使用する例は、「[構成データと環境データの分離](separatingEnvData.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ee32f-145">For an example of using non-node data, see [Separating configuration and environment data](separatingEnvData.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ee32f-146">参照</span><span class="sxs-lookup"><span data-stu-id="ee32f-146">See Also</span></span>
- [<span data-ttu-id="ee32f-147">構成データでの資格情報オプション</span><span class="sxs-lookup"><span data-stu-id="ee32f-147">Credentials Options in Configuration Data</span></span>](configDataCredentials.md)
- [<span data-ttu-id="ee32f-148">DSC 構成</span><span class="sxs-lookup"><span data-stu-id="ee32f-148">DSC Configurations</span></span>](configurations.md)

