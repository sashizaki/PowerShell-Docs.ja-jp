---
ms.date: 12/12/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: 構成 Id (v4/v5) を使用して、プル サーバーへの公開します。
ms.openlocfilehash: 0144fec43d7a8d65b79891567cc0dc3952175343
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402398"
---
# <a name="publish-to-a-pull-server-using-configuration-ids-v4v5"></a><span data-ttu-id="dee11-103">構成 Id (v4/v5) を使用して、プル サーバーへの公開します。</span><span class="sxs-lookup"><span data-stu-id="dee11-103">Publish to a Pull Server using Configuration IDs (v4/v5)</span></span>

<span data-ttu-id="dee11-104">以下のセクションでは、プル サーバーを既に設定したことを前提としています。</span><span class="sxs-lookup"><span data-stu-id="dee11-104">The sections below assume that you have already set up a Pull Server.</span></span> <span data-ttu-id="dee11-105">プル サーバーを設定していない場合は、次のガイドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="dee11-105">If you have not set up your Pull Server, you can use the following guides:</span></span>

- [<span data-ttu-id="dee11-106">DSC SMB プル サーバーを設定する</span><span class="sxs-lookup"><span data-stu-id="dee11-106">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="dee11-107">DSC HTTP プル サーバーを設定する</span><span class="sxs-lookup"><span data-stu-id="dee11-107">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)

<span data-ttu-id="dee11-108">各ターゲット ノードは、構成、リソースをダウンロードしてもその状態を報告を構成できます。</span><span class="sxs-lookup"><span data-stu-id="dee11-108">Each target node can be configured to download configurations, resources, and even report its status.</span></span> <span data-ttu-id="dee11-109">この記事では、ダウンロード、およびリソースを自動的にダウンロードするクライアントの構成に利用できるように、リソースをアップロードする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="dee11-109">This article will show you how to upload resources so they are available to be downloaded, and configure clients to download resources automatically.</span></span> <span data-ttu-id="dee11-110">ノードがを通じて割り当てられた構成を受信すると**プル**または**プッシュ**(v5) では、自動的にダウンロードし、LCM で指定された場所からの構成に必要なすべてのリソース。</span><span class="sxs-lookup"><span data-stu-id="dee11-110">When the Node's receives an assigned Configuration, through **Pull** or **Push** (v5), it automatically downloads any resources required by the Configuration from the location specified in the LCM.</span></span>

## <a name="compile-configurations"></a><span data-ttu-id="dee11-111">構成をコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="dee11-111">Compile Configurations</span></span>

<span data-ttu-id="dee11-112">格納するため、まず[構成](../configurations/configurations.md)プル サーバーでは、".mof"ファイルにコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="dee11-112">The first step to storing [Configurations](../configurations/configurations.md) on a Pull Server, is to compile them into ".mof" files.</span></span> <span data-ttu-id="dee11-113">構成を汎用、および多くのクライアントに適用するのには使用`localhost`ノード ブロックにします。</span><span class="sxs-lookup"><span data-stu-id="dee11-113">To make a configuration generic, and applicable to more clients, use `localhost` in your Node block.</span></span> <span data-ttu-id="dee11-114">次の例を使用する構成シェル`localhost`特定のクライアント名の代わりにします。</span><span class="sxs-lookup"><span data-stu-id="dee11-114">The example below shows a Configuration shell that uses `localhost` instead of a specific client name.</span></span>

```powershell
Configuration GenericConfig
{
    Node localhost
    {

    }
}
GenericConfig
```

<span data-ttu-id="dee11-115">一般的な構成をコンパイルした後、"localhost.mof"ファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="dee11-115">Once you have compiled your generic configuration, you should have a "localhost.mof" file.</span></span>

## <a name="renaming-the-mof-file"></a><span data-ttu-id="dee11-116">MOF ファイルの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="dee11-116">Renaming the MOF file</span></span>

<span data-ttu-id="dee11-117">により、プル サーバー上の構成".mof"ファイルを保存できる**ConfigurationName**または**ConfigurationID**します。</span><span class="sxs-lookup"><span data-stu-id="dee11-117">You can store Configuration ".mof" files on a Pull Server by **ConfigurationName** or **ConfigurationID**.</span></span> <span data-ttu-id="dee11-118">によって、プル クライアントをセットアップする方法、正しくコンパイル".mof"ファイルの名前を変更するのには、次のセクションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="dee11-118">Depending on how you plan to set up your pull clients, you can choose a section below to properly rename your compiled ".mof" files.</span></span>

### <a name="configuration-ids-guid"></a><span data-ttu-id="dee11-119">構成 Id (GUID)</span><span class="sxs-lookup"><span data-stu-id="dee11-119">Configuration IDs (GUID)</span></span>

<span data-ttu-id="dee11-120">"Localhost.mof"ファイルの名前を変更する必要があります"<GUID>.mof"ファイル。</span><span class="sxs-lookup"><span data-stu-id="dee11-120">You will need to rename your "localhost.mof" file to "<GUID>.mof" file.</span></span> <span data-ttu-id="dee11-121">乱数を作成することができます**Guid**またはを使用して、次の例を使用して、 [New-guid](/powershell/module/microsoft.powershell.utility/new-guid)コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="dee11-121">You can create a random **Guid** using the example below, or by using the [New-Guid](/powershell/module/microsoft.powershell.utility/new-guid) cmdlet.</span></span>

```powershell
[System.Guid]::NewGuid()
```

<span data-ttu-id="dee11-122">サンプル出力</span><span class="sxs-lookup"><span data-stu-id="dee11-122">Sample Output</span></span>

```output
Guid
----
64856475-939e-41fb-aba5-4469f4006059
```

<span data-ttu-id="dee11-123">許容可能な任意のメソッドを使用して、".mof"ファイルの名前を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="dee11-123">You can then rename your ".mof" file using any acceptable method.</span></span> <span data-ttu-id="dee11-124">次の例を使用して、 [Rename-item](/powershell/module/microsoft.powershell.management/rename-item)コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="dee11-124">The example below, uses the [Rename-Item](/powershell/module/microsoft.powershell.management/rename-item) cmdlet.</span></span>

```powershell
Rename-Item -Path .\localhost.mof -NewName '64856475-939e-41fb-aba5-4469f4006059.mof'
```

<span data-ttu-id="dee11-125">使用しての詳細については**Guid** 、環境内で、次を参照してください。 [Guid の計画](/powershell/dsc/secureserver#guids)します。</span><span class="sxs-lookup"><span data-stu-id="dee11-125">For more information about using **Guids** in your environment, see [Plan for Guids](/powershell/dsc/secureserver#guids).</span></span>

### <a name="configuration-names"></a><span data-ttu-id="dee11-126">構成名</span><span class="sxs-lookup"><span data-stu-id="dee11-126">Configuration Names</span></span>

<span data-ttu-id="dee11-127">"Localhost.mof"ファイルの名前を変更する必要があります"<Configuration Name>.mof"ファイル。</span><span class="sxs-lookup"><span data-stu-id="dee11-127">You will need to rename your "localhost.mof" file to "<Configuration Name>.mof" file.</span></span> <span data-ttu-id="dee11-128">次の例では、前のセクションから構成の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="dee11-128">In the following example, the configuration name from the previous section is used.</span></span> <span data-ttu-id="dee11-129">許容可能な任意のメソッドを使用して、".mof"ファイルの名前を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="dee11-129">You can then rename your ".mof" file using any acceptable method.</span></span> <span data-ttu-id="dee11-130">次の例を使用して、 [Rename-item](/powershell/module/microsoft.powershell.management/rename-item)コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="dee11-130">The example below, uses the [Rename-Item](/powershell/module/microsoft.powershell.management/rename-item) cmdlet.</span></span>

```powershell
Rename-Item -Path .\localhost.mof -NewName 'GenericConfig.mof'
```

## <a name="create-the-checksum"></a><span data-ttu-id="dee11-131">チェックサムを作成します。</span><span class="sxs-lookup"><span data-stu-id="dee11-131">Create the CheckSum</span></span>

<span data-ttu-id="dee11-132">関連付けられている".checksum"ファイルが存在する必要がある、プル サーバーの場合、または SMB 共有で".mof"の各ファイルが格納されます。</span><span class="sxs-lookup"><span data-stu-id="dee11-132">Each ".mof" file stored on a Pull Server, or SMB share needs to have an associated ".checksum" file.</span></span> <span data-ttu-id="dee11-133">このファイルには、クライアントが関連付けられている".mof"ファイルが変更され再度ダウンロードする必要がありますを知ることができます。</span><span class="sxs-lookup"><span data-stu-id="dee11-133">This file lets clients know when the associated ".mof" file has changed and should be downloaded again.</span></span>

<span data-ttu-id="dee11-134">作成することができます、**チェックサム**で、 [New-dscchecksum](/powershell/module/psdesiredstateconfiguration/new-dscchecksum)コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="dee11-134">You can create a **CheckSum** with the [New-DSCCheckSum](/powershell/module/psdesiredstateconfiguration/new-dscchecksum) cmdlet.</span></span> <span data-ttu-id="dee11-135">実行することも`New-DSCCheckSum`を使用してファイルのディレクトリに対して、`-Path`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="dee11-135">You can also run `New-DSCCheckSum` against a directory of files using the `-Path` parameter.</span></span> <span data-ttu-id="dee11-136">チェックサムが既に存在する場合に再作成することを強制できます、`-Force`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="dee11-136">If a checksum already exists, you can force it to be re-created with the `-Force` parameter.</span></span> <span data-ttu-id="dee11-137">次の例は、前のセクションから".mof"ファイルを含むディレクトリを指定しを使用して、`-Force`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="dee11-137">The following example specified a directory containing the ".mof" file from the previous section, and uses the `-Force` parameter.</span></span>

```powershell
New-DscChecksum -Path '.\' -Force
```

<span data-ttu-id="dee11-138">出力は表示されませんが、表示する必要があります、"<GUID or Configuration Name>。 mof.checksum"ファイル。</span><span class="sxs-lookup"><span data-stu-id="dee11-138">No output will be shown, but you should now see a "<GUID or Configuration Name>.mof.checksum" file.</span></span>

## <a name="where-to-store-mof-files-and-checksums"></a><span data-ttu-id="dee11-139">MOF ファイルとチェックサムを格納する場所</span><span class="sxs-lookup"><span data-stu-id="dee11-139">Where to store MOF files and CheckSums</span></span>

### <a name="on-a-dsc-http-pull-server"></a><span data-ttu-id="dee11-140">DSC の HTTP プル サーバー</span><span class="sxs-lookup"><span data-stu-id="dee11-140">On a DSC HTTP Pull Server</span></span>

<span data-ttu-id="dee11-141">設定すると、HTTP プル サーバー上で説明したよう[DSC HTTP プル サーバーを設定する](pullServer.md)、用のディレクトリを指定する、 **ModulePath**と**ConfigurationPath**キー。</span><span class="sxs-lookup"><span data-stu-id="dee11-141">When you set up your HTTP Pull Server, as explained in [Set up a DSC HTTP Pull Server](pullServer.md), you specify directories for the **ModulePath** and **ConfigurationPath** keys.</span></span> <span data-ttu-id="dee11-142">**ConfigurationPath**キーは、".mof"ファイルの格納場所を示します。</span><span class="sxs-lookup"><span data-stu-id="dee11-142">The **ConfigurationPath** key indicates where any ".mof" files should be stored.</span></span> <span data-ttu-id="dee11-143">**ConfigurationPath** ".mof"ファイルと".checksum"ファイルを格納することを示します。</span><span class="sxs-lookup"><span data-stu-id="dee11-143">The **ConfigurationPath** indicates where any ".mof" files and ".checksum" files should be stored.</span></span>

```powershell
    xDscWebService PSDSCPullServer
    {
    ...
        ModulePath              = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Modules"
        ConfigurationPath       = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Configuration"
    ...
    }

```

### <a name="on-an-smb-share"></a><span data-ttu-id="dee11-144">SMB 共有に</span><span class="sxs-lookup"><span data-stu-id="dee11-144">On an SMB Share</span></span>

<span data-ttu-id="dee11-145">指定した SMB 共有を使用するプル クライアントを設定すると、 **ConfigurationRepositoryShare**します。</span><span class="sxs-lookup"><span data-stu-id="dee11-145">When you set up a Pull Client to use an SMB share, you specify a **ConfigurationRepositoryShare**.</span></span> <span data-ttu-id="dee11-146">すべての".mof"ファイルと".checksum"ファイルを格納する必要がありますし、 **SourcePath**ディレクトリから、 **ConfigurationRepositoryShare**ブロックします。</span><span class="sxs-lookup"><span data-stu-id="dee11-146">All ".mof" files and ".checksum" files should then be stored in the **SourcePath** directory from the **ConfigurationRepositoryShare** block.</span></span>

```powershell
ConfigurationRepositoryShare SMBPullServer
{
    SourcePath = '\\SMBPullServer\Pull'
}
```

## <a name="next-steps"></a><span data-ttu-id="dee11-147">次の手順</span><span class="sxs-lookup"><span data-stu-id="dee11-147">Next Steps</span></span>

<span data-ttu-id="dee11-148">次に、指定した構成をプルするプル クライアントを構成するされます。</span><span class="sxs-lookup"><span data-stu-id="dee11-148">Next, you will want to configure Pull Clients to pull the specified configuration.</span></span> <span data-ttu-id="dee11-149">詳細については、次のガイドのいずれかを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dee11-149">For more information, see one of the following guides:</span></span>

- [<span data-ttu-id="dee11-150">構成 Id (v4) を使用して、プル クライアントの設定します。</span><span class="sxs-lookup"><span data-stu-id="dee11-150">Set up a Pull Client using Configuration IDs (v4)</span></span>](pullClientConfigId4.md)
- [<span data-ttu-id="dee11-151">構成 Id (v5) を使用して、プル クライアントの設定します。</span><span class="sxs-lookup"><span data-stu-id="dee11-151">Set up a Pull Client using Configuration IDs (v5)</span></span>](pullClientConfigId.md)
- [<span data-ttu-id="dee11-152">構成名 (v5) を使用したプル クライアントのセットアップします。</span><span class="sxs-lookup"><span data-stu-id="dee11-152">Set up a Pull Client using Configuration Names (v5)</span></span>](pullClientConfigNames.md)

## <a name="see-also"></a><span data-ttu-id="dee11-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="dee11-153">See also</span></span>

- [<span data-ttu-id="dee11-154">DSC SMB プル サーバーを設定する</span><span class="sxs-lookup"><span data-stu-id="dee11-154">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="dee11-155">DSC HTTP プル サーバーを設定する</span><span class="sxs-lookup"><span data-stu-id="dee11-155">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)
- [<span data-ttu-id="dee11-156">パッケージと、プル サーバーにアップロード リソース</span><span class="sxs-lookup"><span data-stu-id="dee11-156">Package and Upload Resources to a Pull Server</span></span>](package-upload-resources.md)
