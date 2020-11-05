---
ms.date: 12/12/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: リソースをパッケージ化してプル サーバーにアップロードする
description: この記事では、プル サーバーにリソースをアップロードして、DSC によって管理されるノードの構成によってそれらをダウンロードできるようにする方法について説明します。
ms.openlocfilehash: a19d04346a0ae546cfcaf70701fde870d3839f65
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92661697"
---
# <a name="package-and-upload-resources-to-a-pull-server"></a><span data-ttu-id="ae026-104">リソースをパッケージ化してプル サーバーにアップロードする</span><span class="sxs-lookup"><span data-stu-id="ae026-104">Package and Upload Resources to a Pull Server</span></span>

<span data-ttu-id="ae026-105">以下のセクションでは、プル サーバーを既にセットアップしてあるものとします。</span><span class="sxs-lookup"><span data-stu-id="ae026-105">The sections below assume that you have already set up a Pull Server.</span></span> <span data-ttu-id="ae026-106">プル サーバーをセットアップしていない場合は、次のガイドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ae026-106">If you have not set up your Pull Server, you can use the following guides:</span></span>

- [<span data-ttu-id="ae026-107">DSC SMB プル サーバーを設定する</span><span class="sxs-lookup"><span data-stu-id="ae026-107">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="ae026-108">DSC HTTP プル サーバーを設定する</span><span class="sxs-lookup"><span data-stu-id="ae026-108">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)

<span data-ttu-id="ae026-109">各ターゲット ノードは、構成やリソースをダウンロードし、さらにその状態を報告するように構成できます。</span><span class="sxs-lookup"><span data-stu-id="ae026-109">Each target node can be configured to download configurations, resources, and even report its status.</span></span> <span data-ttu-id="ae026-110">この記事では、ダウンロードできるようにリソースをアップロードする方法、およびリソースを自動的にダウンロードするようにクライアントを構成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ae026-110">This article will show you how to upload resources so they are available to be downloaded, and configure clients to download resources automatically.</span></span> <span data-ttu-id="ae026-111">ノードは、割り当てられた構成を **プル** または **プッシュ** (v5) によって受け取ると、構成で必要なすべてのリソースを LCM で指定された場所から自動的にダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="ae026-111">When the Node's receives an assigned Configuration, through **Pull** or **Push** (v5), it automatically downloads any resources required by the Configuration from the location specified in the LCM.</span></span>

## <a name="package-resource-modules"></a><span data-ttu-id="ae026-112">リソース モジュールをパッケージ化する</span><span class="sxs-lookup"><span data-stu-id="ae026-112">Package Resource Modules</span></span>

<span data-ttu-id="ae026-113">クライアントでダウンロードできる各リソースは、`.zip` ファイルに格納する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae026-113">Each resource available for a client to download must be stored in a `.zip` file.</span></span> <span data-ttu-id="ae026-114">以下の例では、[xPSDesiredStateConfiguration](https://www.powershellgallery.com/packages/xPSDesiredStateConfiguration/8.4.0.0) リソースを使用して必要な手順を示します。</span><span class="sxs-lookup"><span data-stu-id="ae026-114">The example below will show the required steps using the [xPSDesiredStateConfiguration](https://www.powershellgallery.com/packages/xPSDesiredStateConfiguration/8.4.0.0) resource.</span></span>

> [!NOTE]
> <span data-ttu-id="ae026-115">PowerShell 4.0 を使用しているクライアントがある場合は、リソース フォルダーの構造をフラット化し、すべてのバージョン フォルダーを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae026-115">If you have any clients using PowerShell 4.0, you will need to flatten the resource folder structure and remove any version folders.</span></span> <span data-ttu-id="ae026-116">詳しくは、「[Multiple Resource Versions (複数のリソース バージョン)](../configurations/import-dscresource.md#multiple-resource-versions)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ae026-116">For more information, see [Multiple Resource Versions](../configurations/import-dscresource.md#multiple-resource-versions).</span></span>

<span data-ttu-id="ae026-117">好みのユーティリティ、スクリプト、または方法を使って、リソース ディレクトリを圧縮することができます。</span><span class="sxs-lookup"><span data-stu-id="ae026-117">You can compress the resource directory using any utility, script, or method that you prefer.</span></span> <span data-ttu-id="ae026-118">Windows の場合、`xPSDesiredStateConfiguration` ディレクトリを " _右クリック_ " して、 **[送信先]** 、 **[圧縮フォルダー]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="ae026-118">In Windows, you can _right-click_ on the `xPSDesiredStateConfiguration` directory, and select **Send To** , then **Compressed Folder**.</span></span>

![右クリック - [送信先] - [圧縮フォルダー]](media/package-upload-resources/right-click.gif)

### <a name="naming-the-resource-archive"></a><span data-ttu-id="ae026-120">リソース アーカイブの名前を指定する</span><span class="sxs-lookup"><span data-stu-id="ae026-120">Naming the Resource Archive</span></span>

<span data-ttu-id="ae026-121">リソース アーカイブには、次の形式で名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae026-121">The Resource archive needs to be named with the following format:</span></span>

```
{ModuleName}_{Version}.zip
```

<span data-ttu-id="ae026-122">上の例では、`xPSDesiredStateConfiguration.zip` の名前を `xPSDesiredStateConfiguration_8.4.4.0.zip` に変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae026-122">In the example above, `xPSDesiredStateConfiguration.zip` should be renamed `xPSDesiredStateConfiguration_8.4.4.0.zip`.</span></span>

### <a name="create-checksums"></a><span data-ttu-id="ae026-123">チェックサムを作成する</span><span class="sxs-lookup"><span data-stu-id="ae026-123">Create CheckSums</span></span>

<span data-ttu-id="ae026-124">リソース モジュールを圧縮して名前を変更した後は、 **チェックサム** を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae026-124">Once the Resource module has been compressed and renamed, you need to create a **CheckSum**.</span></span> <span data-ttu-id="ae026-125">**チェックサム** は、クライアント上の LCM によって、リソースが変更されていて、再度ダウンロードする必要があるかどうかを判断するために使われます。</span><span class="sxs-lookup"><span data-stu-id="ae026-125">The **CheckSum** is used, by the LCM on the client, to determine if the resource has been changed, and needs to be downloaded again.</span></span> <span data-ttu-id="ae026-126">次の例で示すように、 **チェックサム** は [New-DSCCheckSum](/powershell/module/PSDesiredStateConfiguration/New-DSCCheckSum) コマンドレットで作成できます。</span><span class="sxs-lookup"><span data-stu-id="ae026-126">You can create a **CheckSum** with the [New-DSCCheckSum](/powershell/module/PSDesiredStateConfiguration/New-DSCCheckSum) cmdlet, as shown in the example below.</span></span>

```powershell
New-DscChecksum -Path .\xPSDesiredStateConfiguration_8.4.4.0.zip
```

<span data-ttu-id="ae026-127">出力は示されませんが、"xPSDesiredStateConfiguration_8.4.4.0.zip.checksum" が表示されるようになるはずです。</span><span class="sxs-lookup"><span data-stu-id="ae026-127">No output will be shown, but you should now see a "xPSDesiredStateConfiguration_8.4.4.0.zip.checksum".</span></span> <span data-ttu-id="ae026-128">また、`-Path` パラメーターを使用すると、ファイルのディレクトリに対して `New-DSCCheckSum` を実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="ae026-128">You can also run `New-DSCCheckSum` against a directory of files using the `-Path` parameter.</span></span> <span data-ttu-id="ae026-129">チェックサムが既に存在する場合は、`-Force` パラメーターを使用して強制的に再作成できます。</span><span class="sxs-lookup"><span data-stu-id="ae026-129">If a checksum already exists, you can force it to be re-created with the `-Force` parameter.</span></span>

### <a name="where-to-store-resource-archives"></a><span data-ttu-id="ae026-130">リソース アーカイブを格納する場所</span><span class="sxs-lookup"><span data-stu-id="ae026-130">Where to store Resource Archives</span></span>

#### <a name="on-a-dsc-http-pull-server"></a><span data-ttu-id="ae026-131">DSC HTTP プル サーバー上</span><span class="sxs-lookup"><span data-stu-id="ae026-131">On a DSC HTTP Pull Server</span></span>

<span data-ttu-id="ae026-132">HTTP プル サーバーをセットアップするときは、「 [DSC HTTP プル サーバーを設定する](pullServer.md)」で説明されているように、 **ModulePath** キーと **ConfigurationPath** キーに対するディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="ae026-132">When you set up your HTTP Pull Server, as explained in [Set up a DSC HTTP Pull Server](pullServer.md), you specify directories for the **ModulePath** and **ConfigurationPath** keys.</span></span> <span data-ttu-id="ae026-133">**ConfigurationPath** キーは、".mof" ファイルを格納する必要がある場所を示します。</span><span class="sxs-lookup"><span data-stu-id="ae026-133">The **ConfigurationPath** key indicates where any ".mof" files should be stored.</span></span> <span data-ttu-id="ae026-134">**ModulePath** は、DSC リソース モジュールを格納する必要がある場所を示します。</span><span class="sxs-lookup"><span data-stu-id="ae026-134">The **ModulePath** indicates where any DSC Resource Modules should be stored.</span></span>

```powershell
    xDscWebService PSDSCPullServer
    {
    ...
        ModulePath              = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Modules"
        ConfigurationPath       = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Configuration"
    ...
    }

```

#### <a name="on-an-smb-share"></a><span data-ttu-id="ae026-135">SMB 共有上</span><span class="sxs-lookup"><span data-stu-id="ae026-135">On an SMB Share</span></span>

<span data-ttu-id="ae026-136">**ResourceRepositoryShare** を指定した場合は、プル クライアントをセットアップするときに、 **ResourceRepositoryShare** ブロックの **SourcePath** ディレクトリに、アーカイブとチェックサムを格納します。</span><span class="sxs-lookup"><span data-stu-id="ae026-136">If you specified a **ResourceRepositoryShare** , when setting up your Pull Client, store archives and checksums in the **SourcePath** directory from the **ResourceRepositoryShare** block.</span></span>

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

<span data-ttu-id="ae026-137">**ConfigurationRepositoryShare** だけを指定した場合は、プル クライアントをセットアップするときに、 **ConfigurationRepositoryShare** ブロックの **SourcePath** ディレクトリに、アーカイブとチェックサムを格納します。</span><span class="sxs-lookup"><span data-stu-id="ae026-137">If you specified only a **ConfigurationRepositoryShare** , when setting up your Pull Client, store archives and checksums in the **SourcePath** directory from the **ConfigurationRepositoryShare** block.</span></span>

```powershell
ConfigurationRepositoryShare SMBPullServer
{
    SourcePath = '\\SMBPullServer\Pull'
}
```

#### <a name="updating-resources"></a><span data-ttu-id="ae026-138">リソースの更新</span><span class="sxs-lookup"><span data-stu-id="ae026-138">Updating resources</span></span>

<span data-ttu-id="ae026-139">アーカイブの名前のバージョン番号を変更するか、新しいチェックサムを作成することにより、強制的にノードにリソースを更新させることができます。</span><span class="sxs-lookup"><span data-stu-id="ae026-139">You can force a Node to update its resources by changing the version number in the archive's name, or by creating a new checksum.</span></span> <span data-ttu-id="ae026-140">プル クライアントでは、LCM が更新されるときに、必要なリソースの新しいバージョンだけでなく更新されたチェックサムも確認されます。</span><span class="sxs-lookup"><span data-stu-id="ae026-140">The Pull Client will check for newer versions of required resources, as well as updated checksums, when its LCM refreshes.</span></span>

## <a name="see-also"></a><span data-ttu-id="ae026-141">参照</span><span class="sxs-lookup"><span data-stu-id="ae026-141">See also</span></span>

- [<span data-ttu-id="ae026-142">DSC SMB プル サーバーを設定する</span><span class="sxs-lookup"><span data-stu-id="ae026-142">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="ae026-143">DSC HTTP プル サーバーを設定する</span><span class="sxs-lookup"><span data-stu-id="ae026-143">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)
