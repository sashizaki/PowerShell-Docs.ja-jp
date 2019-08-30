---
ms.date: 12/12/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: 構成 ID (v4/v5) を使用してプル サーバーに発行する
ms.openlocfilehash: c258814f480b91eba75c7ce9abf70c558f1f469e
ms.sourcegitcommit: 5a004064f33acc0145ccd414535763e95f998c89
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2019
ms.locfileid: "69986565"
---
# <a name="publish-to-a-pull-server-using-configuration-ids-v4v5"></a><span data-ttu-id="f9cf0-103">構成 ID (v4/v5) を使用してプル サーバーに発行する</span><span class="sxs-lookup"><span data-stu-id="f9cf0-103">Publish to a Pull Server using Configuration IDs (v4/v5)</span></span>

<span data-ttu-id="f9cf0-104">以下のセクションでは、プル サーバーを既にセットアップしてあるものとします。</span><span class="sxs-lookup"><span data-stu-id="f9cf0-104">The sections below assume that you have already set up a Pull Server.</span></span> <span data-ttu-id="f9cf0-105">プル サーバーをセットアップしていない場合は、次のガイドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f9cf0-105">If you haven't set up your Pull Server, you can use the following guides:</span></span>

- [<span data-ttu-id="f9cf0-106">DSC SMB プル サーバーを設定する</span><span class="sxs-lookup"><span data-stu-id="f9cf0-106">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="f9cf0-107">DSC HTTP プル サーバーを設定する</span><span class="sxs-lookup"><span data-stu-id="f9cf0-107">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)

<span data-ttu-id="f9cf0-108">各ターゲット ノードは、構成やリソースをダウンロードし、さらにその状態を報告するように構成できます。</span><span class="sxs-lookup"><span data-stu-id="f9cf0-108">Each target node can be configured to download configurations, resources, and even report its status.</span></span> <span data-ttu-id="f9cf0-109">この記事では、リソースをアップロードしてダウンロードできるようにする方法と、リソースを自動的にダウンロードするようにクライアントを構成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f9cf0-109">This article shows you how to upload resources so they're available to be downloaded, and configure clients to automatically download resources.</span></span> <span data-ttu-id="f9cf0-110">ノードは、**プル**または**プッシュ** (v5) によって割り当てられた構成を受け取ると、その構成で要求されているすべてのリソースを、ローカル構成マネージャー (LCM) で指定された場所から自動的にダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="f9cf0-110">When the node receives an assigned Configuration, through **Pull** or **Push** (v5), it automatically downloads any resources required by the Configuration from the location specified in the Local Configuration Manager (LCM).</span></span>

## <a name="compile-configurations"></a><span data-ttu-id="f9cf0-111">構成をコンパイルする</span><span class="sxs-lookup"><span data-stu-id="f9cf0-111">Compile configurations</span></span>

<span data-ttu-id="f9cf0-112">[構成](../configurations/configurations.md)をプル サーバーに格納するための最初のステップは、それらを `.mof` ファイルにコンパイルすることです。</span><span class="sxs-lookup"><span data-stu-id="f9cf0-112">The first step to storing [Configurations](../configurations/configurations.md) on a Pull Server, is to compile them into `.mof` files.</span></span> <span data-ttu-id="f9cf0-113">構成を汎用にし、より多くのクライアントに適用できるようにするため、Node ブロックでは `localhost` を使用します。</span><span class="sxs-lookup"><span data-stu-id="f9cf0-113">To make a configuration generic, and applicable to more clients, use `localhost` in your Node block.</span></span> <span data-ttu-id="f9cf0-114">次の例では、特定のクライアント名ではなく `localhost` を使用する構成シェルを示します。</span><span class="sxs-lookup"><span data-stu-id="f9cf0-114">The example below shows a Configuration shell that uses `localhost` instead of a specific client name.</span></span>

```powershell
Configuration GenericConfig
{
    Node localhost
    {

    }
}
GenericConfig
```

<span data-ttu-id="f9cf0-115">汎用の構成をコンパイルすると、`localhost.mof` ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f9cf0-115">Once you've compiled your generic configuration, you should have a `localhost.mof` file.</span></span>

## <a name="renaming-the-mof-file"></a><span data-ttu-id="f9cf0-116">MOF ファイルの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="f9cf0-116">Renaming the MOF file</span></span>

<span data-ttu-id="f9cf0-117">構成の `.mof` ファイルは、**ConfigurationName** または **ConfigurationID** によってプル サーバーに格納できます。</span><span class="sxs-lookup"><span data-stu-id="f9cf0-117">You can store Configuration `.mof` files on a Pull Server by **ConfigurationName** or **ConfigurationID**.</span></span> <span data-ttu-id="f9cf0-118">プル クライアントのセットアップ方法に応じて、以下のセクションを選択し、コンパイル済みの `.mof` ファイルの名前を適切に変更できます。</span><span class="sxs-lookup"><span data-stu-id="f9cf0-118">Depending on how you plan to set up your pull clients, you can choose a section below to properly rename your compiled `.mof` files.</span></span>

### <a name="configuration-ids-guid"></a><span data-ttu-id="f9cf0-119">構成 ID (GUID)</span><span class="sxs-lookup"><span data-stu-id="f9cf0-119">Configuration IDs (GUID)</span></span>

<span data-ttu-id="f9cf0-120">`localhost.mof` ファイルの名前を `<GUID>.mof` ファイルに変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9cf0-120">You'll need to rename your `localhost.mof` file to `<GUID>.mof` file.</span></span> <span data-ttu-id="f9cf0-121">以下の例を使用するか、または [New-Guid](/powershell/module/microsoft.powershell.utility/new-guid) コマンドレットを使用して、ランダムな **Guid** を作成できます。</span><span class="sxs-lookup"><span data-stu-id="f9cf0-121">You can create a random **Guid** using the example below, or by using the [New-Guid](/powershell/module/microsoft.powershell.utility/new-guid) cmdlet.</span></span>

```powershell
[System.Guid]::NewGuid()
```

<span data-ttu-id="f9cf0-122">サンプル出力</span><span class="sxs-lookup"><span data-stu-id="f9cf0-122">Sample Output</span></span>

```Output
Guid
----
64856475-939e-41fb-aba5-4469f4006059
```

<span data-ttu-id="f9cf0-123">その後、使用可能な任意の方法を使って、`.mof` ファイルの名前を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="f9cf0-123">You can then rename your `.mof` file using any acceptable method.</span></span> <span data-ttu-id="f9cf0-124">次の例では、[Rename-Item](/powershell/module/microsoft.powershell.management/rename-item) コマンドレットを使っています。</span><span class="sxs-lookup"><span data-stu-id="f9cf0-124">The example below, uses the [Rename-Item](/powershell/module/microsoft.powershell.management/rename-item) cmdlet.</span></span>

```powershell
Rename-Item -Path .\localhost.mof -NewName '64856475-939e-41fb-aba5-4469f4006059.mof'
```

<span data-ttu-id="f9cf0-125">環境で **Guid** を使用する詳細については、[Guid の計画](/powershell/dsc/secureserver#guids)に関する項を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9cf0-125">For more information about using **Guids** in your environment, see [Plan for Guids](/powershell/dsc/secureserver#guids).</span></span>

### <a name="configuration-names"></a><span data-ttu-id="f9cf0-126">構成名</span><span class="sxs-lookup"><span data-stu-id="f9cf0-126">Configuration names</span></span>

<span data-ttu-id="f9cf0-127">`localhost.mof` ファイルの名前を `<Configuration Name>.mof` ファイルに変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9cf0-127">You'll need to rename your `localhost.mof` file to `<Configuration Name>.mof` file.</span></span> <span data-ttu-id="f9cf0-128">次の例では、前のセクションの構成名を使っています。</span><span class="sxs-lookup"><span data-stu-id="f9cf0-128">In the following example, the configuration name from the previous section is used.</span></span> <span data-ttu-id="f9cf0-129">その後、使用可能な任意の方法を使って、`.mof` ファイルの名前を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="f9cf0-129">You can then rename your `.mof` file using any acceptable method.</span></span> <span data-ttu-id="f9cf0-130">次の例では、[Rename-Item](/powershell/module/microsoft.powershell.management/rename-item) コマンドレットを使っています。</span><span class="sxs-lookup"><span data-stu-id="f9cf0-130">The example below, uses the [Rename-Item](/powershell/module/microsoft.powershell.management/rename-item) cmdlet.</span></span>

```powershell
Rename-Item -Path .\localhost.mof -NewName 'GenericConfig.mof'
```

## <a name="create-the-checksum"></a><span data-ttu-id="f9cf0-131">チェックサムを作成する</span><span class="sxs-lookup"><span data-stu-id="f9cf0-131">Create the checkSum</span></span>

<span data-ttu-id="f9cf0-132">プル サーバーまたは SMB 共有に格納される各 `.mof` ファイルには、`.checksum` ファイルを関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9cf0-132">Each `.mof` file stored on a Pull Server, or SMB share needs to have an associated `.checksum` file.</span></span>
<span data-ttu-id="f9cf0-133">このファイルにより、クライアントは、関連付けられている `.mof` ファイルが変更され、もう一度ダウンロードする必要が生じたときに把握することができます。</span><span class="sxs-lookup"><span data-stu-id="f9cf0-133">This file lets clients know when the associated `.mof` file has changed and should be downloaded again.</span></span>

<span data-ttu-id="f9cf0-134">**チェックサム**は [New-DSCCheckSum](/powershell/module/psdesiredstateconfiguration/new-dscchecksum) コマンドレットで作成できます。</span><span class="sxs-lookup"><span data-stu-id="f9cf0-134">You can create a **CheckSum** with the [New-DSCCheckSum](/powershell/module/psdesiredstateconfiguration/new-dscchecksum) cmdlet.</span></span> <span data-ttu-id="f9cf0-135">また、`-Path` パラメーターを使用すると、ファイルのディレクトリに対して `New-DSCCheckSum` を実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="f9cf0-135">You can also run `New-DSCCheckSum` against a directory of files using the `-Path` parameter.</span></span>
<span data-ttu-id="f9cf0-136">チェックサムが既に存在する場合は、`-Force` パラメーターを使用して強制的に再作成できます。</span><span class="sxs-lookup"><span data-stu-id="f9cf0-136">If a checksum already exists, you can force it to be re-created with the `-Force` parameter.</span></span> <span data-ttu-id="f9cf0-137">次の例では、前のセクションの `.mof` ファイルが含まれているディレクトリを指定し、`-Force` パラメーターを使用しています。</span><span class="sxs-lookup"><span data-stu-id="f9cf0-137">The following example specified a directory containing the `.mof` file from the previous section, and uses the `-Force` parameter.</span></span>

```powershell
New-DscChecksum -Path '.\' -Force
```

<span data-ttu-id="f9cf0-138">出力は表示されませんが、`<GUID or Configuration Name>.mof.checksum` ファイルを確認できるようになるはずです。</span><span class="sxs-lookup"><span data-stu-id="f9cf0-138">No output will be shown, but you should now see a `<GUID or Configuration Name>.mof.checksum` file.</span></span>

## <a name="where-to-store-mof-files-and-checksums"></a><span data-ttu-id="f9cf0-139">MOF ファイルとチェックサムを格納する場所</span><span class="sxs-lookup"><span data-stu-id="f9cf0-139">Where to store MOF files and checkSums</span></span>

### <a name="on-a-dsc-http-pull-server"></a><span data-ttu-id="f9cf0-140">DSC HTTP プル サーバー上</span><span class="sxs-lookup"><span data-stu-id="f9cf0-140">On a DSC HTTP Pull Server</span></span>

<span data-ttu-id="f9cf0-141">HTTP プル サーバーをセットアップするときは、「[DSC HTTP プル サーバーを設定する](pullServer.md)」で説明されているように、**ModulePath** キーと **ConfigurationPath** キーに対するディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="f9cf0-141">When you set up your HTTP Pull Server, as explained in [Set up a DSC HTTP Pull Server](pullServer.md), you specify directories for the **ModulePath** and **ConfigurationPath** keys.</span></span> <span data-ttu-id="f9cf0-142">**ModulePath** キーでは、モジュールのパッケージ化された `.zip` ファイルを格納する必要がある場所を示します。</span><span class="sxs-lookup"><span data-stu-id="f9cf0-142">The **ModulePath** key indicates where a module's packaged `.zip` files should be stored.</span></span> <span data-ttu-id="f9cf0-143">**ConfigurationPath** では、`.mof` ファイルと `.checksum` ファイルを格納する必要がある場所を示します。</span><span class="sxs-lookup"><span data-stu-id="f9cf0-143">The **ConfigurationPath** indicates where any `.mof` files and `.checksum` files should be stored.</span></span>

```powershell
    xDscWebService PSDSCPullServer
    {
    ...
        ModulePath              = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Modules"
        ConfigurationPath       = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Configuration"
    ...
    }

```

### <a name="on-an-smb-share"></a><span data-ttu-id="f9cf0-144">SMB 共有上</span><span class="sxs-lookup"><span data-stu-id="f9cf0-144">On an SMB share</span></span>

<span data-ttu-id="f9cf0-145">SMB 共有を使うようプル クライアントを設定するときは、**ConfigurationRepositoryShare** を指定します。</span><span class="sxs-lookup"><span data-stu-id="f9cf0-145">When you set up a Pull Client to use an SMB share, you specify a **ConfigurationRepositoryShare**.</span></span>
<span data-ttu-id="f9cf0-146">すべての `.mof` ファイルと `.checksum` ファイルを、**ConfigurationRepositoryShare** ブロックの **SourcePath** ディレクトリに格納する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9cf0-146">All `.mof` files and `.checksum` files should be stored in the **SourcePath** directory from the **ConfigurationRepositoryShare** block.</span></span>

```powershell
ConfigurationRepositoryShare SMBPullServer
{
    SourcePath = '\\SMBPullServer\Pull'
}
```

## <a name="next-steps"></a><span data-ttu-id="f9cf0-147">次の手順</span><span class="sxs-lookup"><span data-stu-id="f9cf0-147">Next steps</span></span>

<span data-ttu-id="f9cf0-148">次に、指定した構成をプルするようにプル クライアントを構成します。</span><span class="sxs-lookup"><span data-stu-id="f9cf0-148">Next, you'll want to configure Pull Clients to pull the specified configuration.</span></span> <span data-ttu-id="f9cf0-149">詳しくは、次のいずれかのガイドをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f9cf0-149">For more information, see one of the following guides:</span></span>

- [<span data-ttu-id="f9cf0-150">構成 ID を使用してプル クライアントを設定する (v4)</span><span class="sxs-lookup"><span data-stu-id="f9cf0-150">Set up a Pull Client using Configuration IDs (v4)</span></span>](pullClientConfigId4.md)
- [<span data-ttu-id="f9cf0-151">構成 ID を使用してプル クライアントを設定する (v5)</span><span class="sxs-lookup"><span data-stu-id="f9cf0-151">Set up a Pull Client using Configuration IDs (v5)</span></span>](pullClientConfigId.md)
- [<span data-ttu-id="f9cf0-152">構成名を使用してプル クライアントを設定する (v5)</span><span class="sxs-lookup"><span data-stu-id="f9cf0-152">Set up a Pull Client using Configuration Names (v5)</span></span>](pullClientConfigNames.md)

## <a name="see-also"></a><span data-ttu-id="f9cf0-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="f9cf0-153">See also</span></span>

- [<span data-ttu-id="f9cf0-154">DSC SMB プル サーバーを設定する</span><span class="sxs-lookup"><span data-stu-id="f9cf0-154">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="f9cf0-155">DSC HTTP プル サーバーを設定する</span><span class="sxs-lookup"><span data-stu-id="f9cf0-155">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)
- [<span data-ttu-id="f9cf0-156">リソースをパッケージ化してプル サーバーにアップロードする</span><span class="sxs-lookup"><span data-stu-id="f9cf0-156">Package and Upload Resources to a Pull Server</span></span>](package-upload-resources.md)
