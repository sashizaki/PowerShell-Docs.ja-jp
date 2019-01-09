---
ms.date: 12/12/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: パッケージと、プル サーバーにアップロード リソース
ms.openlocfilehash: 29a62f96393a53c9e7da57a5e51732dcb0937194
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402301"
---
# <a name="package-and-upload-resources-to-a-pull-server"></a><span data-ttu-id="49cc4-103">パッケージと、プル サーバーにアップロード リソース</span><span class="sxs-lookup"><span data-stu-id="49cc4-103">Package and Upload Resources to a Pull Server</span></span>

<span data-ttu-id="49cc4-104">以下のセクションでは、プル サーバーを既に設定したことを前提としています。</span><span class="sxs-lookup"><span data-stu-id="49cc4-104">The sections below assume that you have already set up a Pull Server.</span></span> <span data-ttu-id="49cc4-105">プル サーバーを設定していない場合は、次のガイドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="49cc4-105">If you have not set up your Pull Server, you can use the following guides:</span></span>

- [<span data-ttu-id="49cc4-106">DSC SMB プル サーバーを設定する</span><span class="sxs-lookup"><span data-stu-id="49cc4-106">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="49cc4-107">DSC HTTP プル サーバーを設定する</span><span class="sxs-lookup"><span data-stu-id="49cc4-107">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)

<span data-ttu-id="49cc4-108">各ターゲット ノードは、構成、リソースをダウンロードしてもその状態を報告を構成できます。</span><span class="sxs-lookup"><span data-stu-id="49cc4-108">Each target node can be configured to download configurations, resources, and even report its status.</span></span> <span data-ttu-id="49cc4-109">この記事では、ダウンロード、およびリソースを自動的にダウンロードするクライアントの構成に利用できるように、リソースをアップロードする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="49cc4-109">This article will show you how to upload resources so they are available to be downloaded, and configure clients to download resources automatically.</span></span> <span data-ttu-id="49cc4-110">ノードがを通じて割り当てられた構成を受信すると**プル**または**プッシュ**(v5) では、自動的にダウンロードし、LCM で指定された場所からの構成に必要なすべてのリソース。</span><span class="sxs-lookup"><span data-stu-id="49cc4-110">When the Node's receives an assigned Configuration, through **Pull** or **Push** (v5), it automatically downloads any resources required by the Configuration from the location specified in the LCM.</span></span>

## <a name="package-resource-modules"></a><span data-ttu-id="49cc4-111">パッケージ リソース モジュール</span><span class="sxs-lookup"><span data-stu-id="49cc4-111">Package Resource Modules</span></span>

<span data-ttu-id="49cc4-112">クライアントをダウンロードするために使用可能な各リソースは、".zip"ファイルに格納する必要があります。</span><span class="sxs-lookup"><span data-stu-id="49cc4-112">Each resource available for a client to download must be stored in a ".zip" file.</span></span> <span data-ttu-id="49cc4-113">次の例を使用して必要な手順が表示されます、 [xPSDesiredStateConfiguration](https://www.powershellgallery.com/packages/xPSDesiredStateConfiguration/8.4.0.0)リソース。</span><span class="sxs-lookup"><span data-stu-id="49cc4-113">The example below will show the required steps using the [xPSDesiredStateConfiguration](https://www.powershellgallery.com/packages/xPSDesiredStateConfiguration/8.4.0.0) resource.</span></span>

> [!NOTE]
> <span data-ttu-id="49cc4-114">PowerShell 4.0 を使用して、クライアントがある場合に、リソースのフォルダー構造 flaten する必要があり、バージョン フォルダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="49cc4-114">If you have any clients using PowerShell 4.0, you will need to flaten the resource folder structure and remove any version folders.</span></span> <span data-ttu-id="49cc4-115">詳細については、次を参照してください。[複数のリソース バージョン](../configurations/import-dscresource.md#multiple-resource-versions)します。</span><span class="sxs-lookup"><span data-stu-id="49cc4-115">For more information, see [Multiple Resource Versions](../configurations/import-dscresource.md#multiple-resource-versions).</span></span>

<span data-ttu-id="49cc4-116">任意のユーティリティ、スクリプト、または使用するメソッドを使用して、リソース ディレクトリを圧縮することができます。</span><span class="sxs-lookup"><span data-stu-id="49cc4-116">You can compress the resource directory using any utility, script, or method that you prefer.</span></span> <span data-ttu-id="49cc4-117">、Windows で実行できます*を右クリックして*"xPSDesiredStateConfiguration"ディレクトリ、および「を送信する」、し、「圧縮フォルダー」を選択します。</span><span class="sxs-lookup"><span data-stu-id="49cc4-117">In Windows, you can *right-click* on the "xPSDesiredStateConfiguration" directory, and select "Send To", then "Compressed Folder".</span></span>

![右クリック](../media/right-click.gif)

### <a name="naming-the-resource-archive"></a><span data-ttu-id="49cc4-119">リソースのアーカイブの名前を付ける</span><span class="sxs-lookup"><span data-stu-id="49cc4-119">Naming the Resource Archive</span></span>

<span data-ttu-id="49cc4-120">リソースのアーカイブは、次の形式で名前を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="49cc4-120">The Resource archive needs to be named with the following format:</span></span>

```
{ModuleName}_{Version}.zip
```

<span data-ttu-id="49cc4-121">上記の例では、"xPSDesiredStateConfiguration.zip"によって"xPSDesiredStateConfiguration_8.4.4.0.zip"の名前を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="49cc4-121">In the example above, "xPSDesiredStateConfiguration.zip" should be renamed "xPSDesiredStateConfiguration_8.4.4.0.zip".</span></span>

### <a name="create-checksums"></a><span data-ttu-id="49cc4-122">チェックサムを作成します。</span><span class="sxs-lookup"><span data-stu-id="49cc4-122">Create CheckSums</span></span>

<span data-ttu-id="49cc4-123">リソース モジュールを圧縮され名前を変更すると、作成する必要があります、**チェックサム**します。</span><span class="sxs-lookup"><span data-stu-id="49cc4-123">Once the Resource module has been compressed and renamed, you need to create a **CheckSum**.</span></span>  <span data-ttu-id="49cc4-124">**チェックサム**使用して、クライアントでは、LCM によってリソースが変更されていると再度ダウンロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="49cc4-124">The **CheckSum** is used, by the LCM on the client, to determine if the resource has been changed, and needs to be downloaded again.</span></span> <span data-ttu-id="49cc4-125">作成することができます、**チェックサム**で、 [New-dscchecksum](/powershell/module/PSDesiredStateConfiguration/New-DSCCheckSum)コマンドレットは、次の例で示すようにします。</span><span class="sxs-lookup"><span data-stu-id="49cc4-125">You can create a **CheckSum** with the [New-DSCCheckSum](/powershell/module/PSDesiredStateConfiguration/New-DSCCheckSum) cmdlet, as shown in the example below.</span></span>

```powershell
New-DscChecksum -Path .\xPSDesiredStateConfiguration_8.4.4.0.zip
```

<span data-ttu-id="49cc4-126">出力は表示されませんが、"xPSDesiredStateConfiguration_8.4.4.0.zip.checksum"が表示されます。</span><span class="sxs-lookup"><span data-stu-id="49cc4-126">No output will be shown, but you should now see a "xPSDesiredStateConfiguration_8.4.4.0.zip.checksum".</span></span> <span data-ttu-id="49cc4-127">実行することも`New-DSCCheckSum`を使用してファイルのディレクトリに対して、`-Path`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="49cc4-127">You can also run `New-DSCCheckSum` against a directory of files using the `-Path` parameter.</span></span> <span data-ttu-id="49cc4-128">チェックサムが既に存在する場合に再作成することを強制できます、`-Force`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="49cc4-128">If a checksum already exists, you can force it to be re-created with the `-Force` parameter.</span></span>

### <a name="where-to-store-resource-archives"></a><span data-ttu-id="49cc4-129">リソースのアーカイブを格納する場所</span><span class="sxs-lookup"><span data-stu-id="49cc4-129">Where to store Resource Archives</span></span>

#### <a name="on-a-dsc-http-pull-server"></a><span data-ttu-id="49cc4-130">DSC の HTTP プル サーバー</span><span class="sxs-lookup"><span data-stu-id="49cc4-130">On a DSC HTTP Pull Server</span></span>

<span data-ttu-id="49cc4-131">設定すると、HTTP プル サーバー上で説明したよう[DSC HTTP プル サーバーを設定する](pullServer.md)、用のディレクトリを指定する、 **ModulePath**と**ConfigurationPath**キー。</span><span class="sxs-lookup"><span data-stu-id="49cc4-131">When you set up your HTTP Pull Server, as explained in [Set up a DSC HTTP Pull Server](pullServer.md), you specify directories for the **ModulePath** and **ConfigurationPath** keys.</span></span> <span data-ttu-id="49cc4-132">**ConfigurationPath**キーは、".mof"ファイルの格納場所を示します。</span><span class="sxs-lookup"><span data-stu-id="49cc4-132">The **ConfigurationPath** key indicates where any ".mof" files should be stored.</span></span> <span data-ttu-id="49cc4-133">**ModulePath** DSC リソース モジュールを格納する場所を示します。</span><span class="sxs-lookup"><span data-stu-id="49cc4-133">The **ModulePath** indicates where any DSC Resource Modules should be stored.</span></span>

```powershell
    xDscWebService PSDSCPullServer
    {
    ...
        ModulePath              = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Modules"
        ConfigurationPath       = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Configuration"
    ...
    }

```

#### <a name="on-an-smb-share"></a><span data-ttu-id="49cc4-134">SMB 共有に</span><span class="sxs-lookup"><span data-stu-id="49cc4-134">On an SMB Share</span></span>

<span data-ttu-id="49cc4-135">指定した場合、 **ResourceRepositoryShare**、プル クライアントのセットアップは、アーカイブと内のチェックサムを保存すると、 **SourcePath**ディレクトリから、 **ResourceRepositoryShare**ブロックします。</span><span class="sxs-lookup"><span data-stu-id="49cc4-135">If you specified a **ResourceRepositoryShare**, when setting up your Pull Client, store archives and checksums in the **SourcePath** directory from the **ResourceRepositoryShare** block.</span></span>

```powershell
ConfigurationRepositoryShare SMBPullServer
{
    SourcePath = '\\SMBPullServer\Configurations'
}

ResourceRepositoryShare SMBResourceServer
{
    SourcePath = '\\SMBPullServer\Resources'
}
```

<span data-ttu-id="49cc4-136">のみを指定した場合、 **ConfigurationRepositoryShare**、プル クライアントのセットアップは、アーカイブと内のチェックサムを保存すると、 **SourcePath**ディレクトリから、 **ConfigurationRepositoryShare**ブロックします。</span><span class="sxs-lookup"><span data-stu-id="49cc4-136">If you specified only a **ConfigurationRepositoryShare**, when setting up your Pull Client, store archives and checksums in the **SourcePath** directory from the **ConfigurationRepositoryShare** block.</span></span>

```powershell
ConfigurationRepositoryShare SMBPullServer
{
    SourcePath = '\\SMBPullServer\Pull'
}
```

#### <a name="updating-resources"></a><span data-ttu-id="49cc4-137">リソースの更新</span><span class="sxs-lookup"><span data-stu-id="49cc4-137">Updating resources</span></span>

<span data-ttu-id="49cc4-138">アーカイブの名、バージョン番号を変更するか、新しいチェックサムを作成して、そのリソースを更新するノードを強制することができます。</span><span class="sxs-lookup"><span data-stu-id="49cc4-138">You can force a Node to update its resources by changing the version number in the archive's name, or by creating a new checksum.</span></span> <span data-ttu-id="49cc4-139">プル クライアントは、必要なリソースの新しいバージョンの確認だけでなく、LCM が更新されると、チェックサムを更新します。</span><span class="sxs-lookup"><span data-stu-id="49cc4-139">The Pull Client will check for newer versions of required resources, as well as updated checksums, when its LCM refreshes.</span></span>

## <a name="see-also"></a><span data-ttu-id="49cc4-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="49cc4-140">See also</span></span>

- [<span data-ttu-id="49cc4-141">DSC SMB プル サーバーを設定する</span><span class="sxs-lookup"><span data-stu-id="49cc4-141">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="49cc4-142">DSC HTTP プル サーバーを設定する</span><span class="sxs-lookup"><span data-stu-id="49cc4-142">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)
