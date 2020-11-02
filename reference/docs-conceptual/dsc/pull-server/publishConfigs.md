---
ms.date: 12/12/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: 構成 ID (v4/v5) を使用してプル サーバーに発行する
description: この記事では、リソースをアップロードしてダウンロードできるようにする方法と、リソースを自動的にダウンロードするようにクライアントを構成する方法を示します。
ms.openlocfilehash: 20e12e3cac6b6e4a86563576f4a915429b18aadb
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92646835"
---
# <a name="publish-to-a-pull-server-using-configuration-ids-v4v5"></a><span data-ttu-id="cd084-104">構成 ID (v4/v5) を使用してプル サーバーに発行する</span><span class="sxs-lookup"><span data-stu-id="cd084-104">Publish to a Pull Server using Configuration IDs (v4/v5)</span></span>

<span data-ttu-id="cd084-105">以下のセクションでは、プル サーバーを既にセットアップしてあるものとします。</span><span class="sxs-lookup"><span data-stu-id="cd084-105">The sections below assume that you have already set up a Pull Server.</span></span> <span data-ttu-id="cd084-106">プル サーバーをセットアップしていない場合は、次のガイドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="cd084-106">If you haven't set up your Pull Server, you can use the following guides:</span></span>

- [<span data-ttu-id="cd084-107">DSC SMB プル サーバーを設定する</span><span class="sxs-lookup"><span data-stu-id="cd084-107">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="cd084-108">DSC HTTP プル サーバーを設定する</span><span class="sxs-lookup"><span data-stu-id="cd084-108">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)

<span data-ttu-id="cd084-109">各ターゲット ノードは、構成やリソースをダウンロードし、さらにその状態を報告するように構成できます。</span><span class="sxs-lookup"><span data-stu-id="cd084-109">Each target node can be configured to download configurations, resources, and even report its status.</span></span> <span data-ttu-id="cd084-110">この記事では、リソースをアップロードしてダウンロードできるようにする方法と、リソースを自動的にダウンロードするようにクライアントを構成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="cd084-110">This article shows you how to upload resources so they're available to be downloaded, and configure clients to automatically download resources.</span></span> <span data-ttu-id="cd084-111">ノードは、 **プル** または **プッシュ** (v5) によって割り当てられた構成を受け取ると、その構成で要求されているすべてのリソースを、ローカル構成マネージャー (LCM) で指定された場所から自動的にダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="cd084-111">When the node receives an assigned Configuration, through **Pull** or **Push** (v5), it automatically downloads any resources required by the Configuration from the location specified in the Local Configuration Manager (LCM).</span></span>

## <a name="compile-configurations"></a><span data-ttu-id="cd084-112">構成をコンパイルする</span><span class="sxs-lookup"><span data-stu-id="cd084-112">Compile configurations</span></span>

<span data-ttu-id="cd084-113">[構成](../configurations/configurations.md)をプル サーバーに格納するための最初のステップは、それらを `.mof` ファイルにコンパイルすることです。</span><span class="sxs-lookup"><span data-stu-id="cd084-113">The first step to storing [Configurations](../configurations/configurations.md) on a Pull Server, is to compile them into `.mof` files.</span></span> <span data-ttu-id="cd084-114">構成を汎用にし、より多くのクライアントに適用できるようにするため、Node ブロックでは `localhost` を使用します。</span><span class="sxs-lookup"><span data-stu-id="cd084-114">To make a configuration generic, and applicable to more clients, use `localhost` in your Node block.</span></span> <span data-ttu-id="cd084-115">次の例では、特定のクライアント名ではなく `localhost` を使用する構成シェルを示します。</span><span class="sxs-lookup"><span data-stu-id="cd084-115">The example below shows a Configuration shell that uses `localhost` instead of a specific client name.</span></span>

```powershell
Configuration GenericConfig
{
    Node localhost
    {

    }
}
GenericConfig
```

<span data-ttu-id="cd084-116">汎用の構成をコンパイルすると、`localhost.mof` ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="cd084-116">Once you've compiled your generic configuration, you should have a `localhost.mof` file.</span></span>

## <a name="renaming-the-mof-file"></a><span data-ttu-id="cd084-117">MOF ファイルの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="cd084-117">Renaming the MOF file</span></span>

<span data-ttu-id="cd084-118">構成の `.mof` ファイルは、 **ConfigurationName** または **ConfigurationID** によってプル サーバーに格納できます。</span><span class="sxs-lookup"><span data-stu-id="cd084-118">You can store Configuration `.mof` files on a Pull Server by **ConfigurationName** or **ConfigurationID** .</span></span> <span data-ttu-id="cd084-119">プル クライアントのセットアップ方法に応じて、以下のセクションを選択し、コンパイル済みの `.mof` ファイルの名前を適切に変更できます。</span><span class="sxs-lookup"><span data-stu-id="cd084-119">Depending on how you plan to set up your pull clients, you can choose a section below to properly rename your compiled `.mof` files.</span></span>

### <a name="configuration-ids-guid"></a><span data-ttu-id="cd084-120">構成 ID (GUID)</span><span class="sxs-lookup"><span data-stu-id="cd084-120">Configuration IDs (GUID)</span></span>

<span data-ttu-id="cd084-121">`localhost.mof` ファイルの名前を `<GUID>.mof` ファイルに変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd084-121">You'll need to rename your `localhost.mof` file to `<GUID>.mof` file.</span></span> <span data-ttu-id="cd084-122">以下の例を使用するか、または [New-Guid](/powershell/module/microsoft.powershell.utility/new-guid) コマンドレットを使用して、ランダムな **Guid** を作成できます。</span><span class="sxs-lookup"><span data-stu-id="cd084-122">You can create a random **Guid** using the example below, or by using the [New-Guid](/powershell/module/microsoft.powershell.utility/new-guid) cmdlet.</span></span>

```powershell
[System.Guid]::NewGuid()
```

<span data-ttu-id="cd084-123">サンプル出力</span><span class="sxs-lookup"><span data-stu-id="cd084-123">Sample Output</span></span>

```Output
Guid
----
64856475-939e-41fb-aba5-4469f4006059
```

<span data-ttu-id="cd084-124">その後、使用可能な任意の方法を使って、`.mof` ファイルの名前を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="cd084-124">You can then rename your `.mof` file using any acceptable method.</span></span> <span data-ttu-id="cd084-125">次の例では、[Rename-Item](/powershell/module/microsoft.powershell.management/rename-item) コマンドレットを使っています。</span><span class="sxs-lookup"><span data-stu-id="cd084-125">The example below, uses the [Rename-Item](/powershell/module/microsoft.powershell.management/rename-item) cmdlet.</span></span>

```powershell
Rename-Item -Path .\localhost.mof -NewName '64856475-939e-41fb-aba5-4469f4006059.mof'
```

<span data-ttu-id="cd084-126">環境で **Guid** を使用する詳細については、 [Guid の計画](secureServer.md#guids)に関する項を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd084-126">For more information about using **Guids** in your environment, see [Plan for Guids](secureServer.md#guids).</span></span>

### <a name="configuration-names"></a><span data-ttu-id="cd084-127">構成名</span><span class="sxs-lookup"><span data-stu-id="cd084-127">Configuration names</span></span>

<span data-ttu-id="cd084-128">`localhost.mof` ファイルの名前を `<Configuration Name>.mof` ファイルに変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd084-128">You'll need to rename your `localhost.mof` file to `<Configuration Name>.mof` file.</span></span> <span data-ttu-id="cd084-129">次の例では、前のセクションの構成名を使っています。</span><span class="sxs-lookup"><span data-stu-id="cd084-129">In the following example, the configuration name from the previous section is used.</span></span> <span data-ttu-id="cd084-130">その後、使用可能な任意の方法を使って、`.mof` ファイルの名前を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="cd084-130">You can then rename your `.mof` file using any acceptable method.</span></span> <span data-ttu-id="cd084-131">次の例では、[Rename-Item](/powershell/module/microsoft.powershell.management/rename-item) コマンドレットを使っています。</span><span class="sxs-lookup"><span data-stu-id="cd084-131">The example below, uses the [Rename-Item](/powershell/module/microsoft.powershell.management/rename-item) cmdlet.</span></span>

```powershell
Rename-Item -Path .\localhost.mof -NewName 'GenericConfig.mof'
```

## <a name="create-the-checksum"></a><span data-ttu-id="cd084-132">チェックサムを作成する</span><span class="sxs-lookup"><span data-stu-id="cd084-132">Create the checkSum</span></span>

<span data-ttu-id="cd084-133">プル サーバーまたは SMB 共有に格納される各 `.mof` ファイルには、`.checksum` ファイルを関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd084-133">Each `.mof` file stored on a Pull Server, or SMB share needs to have an associated `.checksum` file.</span></span>
<span data-ttu-id="cd084-134">このファイルにより、クライアントは、関連付けられている `.mof` ファイルが変更され、もう一度ダウンロードする必要が生じたときに把握することができます。</span><span class="sxs-lookup"><span data-stu-id="cd084-134">This file lets clients know when the associated `.mof` file has changed and should be downloaded again.</span></span>

<span data-ttu-id="cd084-135">**チェックサム** は [New-DSCCheckSum](/powershell/module/psdesiredstateconfiguration/new-dscchecksum) コマンドレットで作成できます。</span><span class="sxs-lookup"><span data-stu-id="cd084-135">You can create a **CheckSum** with the [New-DSCCheckSum](/powershell/module/psdesiredstateconfiguration/new-dscchecksum) cmdlet.</span></span> <span data-ttu-id="cd084-136">また、`-Path` パラメーターを使用すると、ファイルのディレクトリに対して `New-DSCCheckSum` を実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="cd084-136">You can also run `New-DSCCheckSum` against a directory of files using the `-Path` parameter.</span></span>
<span data-ttu-id="cd084-137">チェックサムが既に存在する場合は、`-Force` パラメーターを使用して強制的に再作成できます。</span><span class="sxs-lookup"><span data-stu-id="cd084-137">If a checksum already exists, you can force it to be re-created with the `-Force` parameter.</span></span> <span data-ttu-id="cd084-138">次の例では、前のセクションの `.mof` ファイルが含まれているディレクトリを指定し、`-Force` パラメーターを使用しています。</span><span class="sxs-lookup"><span data-stu-id="cd084-138">The following example specified a directory containing the `.mof` file from the previous section, and uses the `-Force` parameter.</span></span>

```powershell
New-DscChecksum -Path '.\' -Force
```

<span data-ttu-id="cd084-139">出力は表示されませんが、`<GUID or Configuration Name>.mof.checksum` ファイルを確認できるようになるはずです。</span><span class="sxs-lookup"><span data-stu-id="cd084-139">No output will be shown, but you should now see a `<GUID or Configuration Name>.mof.checksum` file.</span></span>

## <a name="where-to-store-mof-files-and-checksums"></a><span data-ttu-id="cd084-140">MOF ファイルとチェックサムを格納する場所</span><span class="sxs-lookup"><span data-stu-id="cd084-140">Where to store MOF files and checkSums</span></span>

### <a name="on-a-dsc-http-pull-server"></a><span data-ttu-id="cd084-141">DSC HTTP プル サーバー上</span><span class="sxs-lookup"><span data-stu-id="cd084-141">On a DSC HTTP Pull Server</span></span>

<span data-ttu-id="cd084-142">HTTP プル サーバーをセットアップするときは、「 [DSC HTTP プル サーバーを設定する](pullServer.md)」で説明されているように、 **ModulePath** キーと **ConfigurationPath** キーに対するディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="cd084-142">When you set up your HTTP Pull Server, as explained in [Set up a DSC HTTP Pull Server](pullServer.md), you specify directories for the **ModulePath** and **ConfigurationPath** keys.</span></span> <span data-ttu-id="cd084-143">**ModulePath** キーでは、モジュールのパッケージ化された `.zip` ファイルを格納する必要がある場所を示します。</span><span class="sxs-lookup"><span data-stu-id="cd084-143">The **ModulePath** key indicates where a module's packaged `.zip` files should be stored.</span></span> <span data-ttu-id="cd084-144">**ConfigurationPath** では、`.mof` ファイルと `.checksum` ファイルを格納する必要がある場所を示します。</span><span class="sxs-lookup"><span data-stu-id="cd084-144">The **ConfigurationPath** indicates where any `.mof` files and `.checksum` files should be stored.</span></span>

```powershell
    xDscWebService PSDSCPullServer
    {
    ...
        ModulePath              = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Modules"
        ConfigurationPath       = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Configuration"
    ...
    }

```

### <a name="on-an-smb-share"></a><span data-ttu-id="cd084-145">SMB 共有上</span><span class="sxs-lookup"><span data-stu-id="cd084-145">On an SMB share</span></span>

<span data-ttu-id="cd084-146">SMB 共有を使うようプル クライアントを設定するときは、 **ConfigurationRepositoryShare** を指定します。</span><span class="sxs-lookup"><span data-stu-id="cd084-146">When you set up a Pull Client to use an SMB share, you specify a **ConfigurationRepositoryShare** .</span></span>
<span data-ttu-id="cd084-147">すべての `.mof` ファイルと `.checksum` ファイルを、 **ConfigurationRepositoryShare** ブロックの **SourcePath** ディレクトリに格納する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd084-147">All `.mof` files and `.checksum` files should be stored in the **SourcePath** directory from the **ConfigurationRepositoryShare** block.</span></span>

```powershell
ConfigurationRepositoryShare SMBPullServer
{
    SourcePath = '\\SMBPullServer\Pull'
}
```

## <a name="next-steps"></a><span data-ttu-id="cd084-148">次の手順</span><span class="sxs-lookup"><span data-stu-id="cd084-148">Next steps</span></span>

<span data-ttu-id="cd084-149">次に、指定した構成をプルするようにプル クライアントを構成します。</span><span class="sxs-lookup"><span data-stu-id="cd084-149">Next, you'll want to configure Pull Clients to pull the specified configuration.</span></span> <span data-ttu-id="cd084-150">詳しくは、次のいずれかのガイドをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cd084-150">For more information, see one of the following guides:</span></span>

- [<span data-ttu-id="cd084-151">構成 ID を使用してプル クライアントを設定する (v4)</span><span class="sxs-lookup"><span data-stu-id="cd084-151">Set up a Pull Client using Configuration IDs (v4)</span></span>](pullClientConfigId4.md)
- [<span data-ttu-id="cd084-152">構成 ID を使用してプル クライアントを設定する (v5)</span><span class="sxs-lookup"><span data-stu-id="cd084-152">Set up a Pull Client using Configuration IDs (v5)</span></span>](pullClientConfigId.md)
- [<span data-ttu-id="cd084-153">構成名を使用してプル クライアントを設定する (v5)</span><span class="sxs-lookup"><span data-stu-id="cd084-153">Set up a Pull Client using Configuration Names (v5)</span></span>](pullClientConfigNames.md)

## <a name="see-also"></a><span data-ttu-id="cd084-154">参照</span><span class="sxs-lookup"><span data-stu-id="cd084-154">See also</span></span>

- [<span data-ttu-id="cd084-155">DSC SMB プル サーバーを設定する</span><span class="sxs-lookup"><span data-stu-id="cd084-155">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="cd084-156">DSC HTTP プル サーバーを設定する</span><span class="sxs-lookup"><span data-stu-id="cd084-156">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)
- [<span data-ttu-id="cd084-157">リソースをパッケージ化してプル サーバーにアップロードする</span><span class="sxs-lookup"><span data-stu-id="cd084-157">Package and Upload Resources to a Pull Server</span></span>](package-upload-resources.md)
