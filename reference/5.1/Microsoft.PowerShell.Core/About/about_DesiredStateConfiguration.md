---
description: PowerShell Desired State Configuration (DSC) 機能について簡単に説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_desiredstateconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_DesiredStateConfiguration
ms.openlocfilehash: 5d088934ffc953ad19be401bce72f6287f0fde07
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "94387024"
---
# <a name="about_desiredstateconfiguration"></a><span data-ttu-id="0d7d3-104">about_DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="0d7d3-104">about_DesiredStateConfiguration</span></span>

## <a name="short-description"></a><span data-ttu-id="0d7d3-105">概要</span><span class="sxs-lookup"><span data-stu-id="0d7d3-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="0d7d3-106">PowerShell Desired State Configuration (DSC) 機能について簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="0d7d3-106">Provides a brief introduction to the PowerShell Desired State Configuration (DSC) feature.</span></span>

## <a name="long-description"></a><span data-ttu-id="0d7d3-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="0d7d3-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="0d7d3-108">DSC は、ソフトウェアサービスの構成データを展開および管理し、これらのサービスが実行される環境を管理できるようにする、PowerShell の管理プラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="0d7d3-108">DSC is a management platform in PowerShell that enables deploying and managing configuration data for software services, and managing the environment in which these services run.</span></span>

<span data-ttu-id="0d7d3-109">DSC には、ソフトウェア環境の状態をどのように構成するかを宣言によって指定するために使用できる PowerShell 言語拡張機能、新しいコマンドレット、およびリソースのセットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="0d7d3-109">DSC provides a set of PowerShell language extensions, new cmdlets, and resources that you can use to declaratively specify how you want the state of your software environment to be configured.</span></span> <span data-ttu-id="0d7d3-110">また、既存の構成を保守し、管理するための手段も提供します。</span><span class="sxs-lookup"><span data-stu-id="0d7d3-110">It also provides a means to maintain and manage existing configurations.</span></span>

<span data-ttu-id="0d7d3-111">DSC は、PowerShell 4.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0d7d3-111">DSC is introduced in PowerShell 4.0.</span></span>

<span data-ttu-id="0d7d3-112">DSC の詳細については、「 [PowerShell Desired State Configuration の概要](/powershell/scripting/dsc/overview/overview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d7d3-112">For detailed information about DSC, see [PowerShell Desired State Configuration Overview](/powershell/scripting/dsc/overview/overview).</span></span>

## <a name="developing-dsc-resources-with-classes"></a><span data-ttu-id="0d7d3-113">クラスを使用した DSC リソースの開発</span><span class="sxs-lookup"><span data-stu-id="0d7d3-113">DEVELOPING DSC RESOURCES WITH CLASSES</span></span>

<span data-ttu-id="0d7d3-114">PowerShell 5.0 以降では、クラスを使用して DSC リソースを開発できます。</span><span class="sxs-lookup"><span data-stu-id="0d7d3-114">Starting in PowerShell 5.0, you can develop DSC resources by using classes.</span></span>
<span data-ttu-id="0d7d3-115">詳細については、「 [about_Classes](about_Classes.md)」と「 [PowerShell クラスを使用したカスタム DSC リソースの作成](/powershell/scripting/dsc/resources/authoringresourceclass)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d7d3-115">For more information, see [about_Classes](about_Classes.md), and [Writing a custom DSC resource with PowerShell classes](/powershell/scripting/dsc/resources/authoringresourceclass).</span></span>

## <a name="using-dsc"></a><span data-ttu-id="0d7d3-116">DSC の使用</span><span class="sxs-lookup"><span data-stu-id="0d7d3-116">USING DSC</span></span>

<span data-ttu-id="0d7d3-117">DSC を使用して環境を構成するには、まず、Configuration キーワードを使用して PowerShell スクリプトブロックを定義し、次に識別子を指定します。その後に、ブロックを区切る中かっこのペアを続けます。</span><span class="sxs-lookup"><span data-stu-id="0d7d3-117">To use DSC to configure your environment, first define a PowerShell script block using the Configuration keyword, followed by an identifier, which is in turn followed by the pair of curly braces delimiting the block.</span></span> <span data-ttu-id="0d7d3-118">構成ブロック内では、環境内の各ノード (コンピューター) に必要な構成状態を指定するノードブロックを定義できます。</span><span class="sxs-lookup"><span data-stu-id="0d7d3-118">Inside the configuration block you can define node blocks that specify the desired configuration state for each node (computer) in the environment.</span></span> <span data-ttu-id="0d7d3-119">ノードブロックは、Node キーワードで始まり、その後にターゲットコンピューターの名前が続きます。これには変数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="0d7d3-119">A node block starts with the Node keyword, followed by the name of the target computer, which can be a variable.</span></span> <span data-ttu-id="0d7d3-120">コンピューター名の後に、ノードブロックを区切る中かっこを指定します。</span><span class="sxs-lookup"><span data-stu-id="0d7d3-120">After the computer name, come the curly braces that delimit the node block.</span></span> <span data-ttu-id="0d7d3-121">ノードブロック内では、リソースブロックを定義して特定のリソースを構成できます。</span><span class="sxs-lookup"><span data-stu-id="0d7d3-121">Inside the node block, you can define resource blocks to configure specific resources.</span></span> <span data-ttu-id="0d7d3-122">リソースブロックは、次の例に示すように、リソースの型名と、そのブロックに指定する識別子、ブロックを区切る中かっこを続けて開始されます。</span><span class="sxs-lookup"><span data-stu-id="0d7d3-122">A resource block starts with the type name of the resource, followed by the identifier you want to specify for that block, followed by the curly braces that delimit the block, as shown in the following example.</span></span>

```powershell
Configuration MyWebConfig {
    # Parameters are optional
    param ($MachineName, $WebsiteFilePath)
    # A Configuration block can have one or more Node blocks
    Node $MachineName
    {
        # Next, specify one or more resource blocks
        # WindowsFeature is one of the resources you can use in a Node block
        # This example ensures the Web Server (IIS) role is installed
        WindowsFeature IIS
        {
            # To ensure that the role is not installed, set Ensure to "Absent"
            Ensure = "Present"
            Name = "Web-Server" # Use the Name property from Get-WindowsFeature
        }

        # You can use the File resource to create files and folders
        # "WebDirectory" is the name you want to use to refer to this instance
        File WebDirectory
        {
            Ensure = "Present"  # You can also set Ensure to "Absent"
            Type = "Directory" # Default is "File"
            Recurse = $true
            SourcePath = $WebsiteFilePath
            DestinationPath = "C:\inetpub\wwwroot"

            # Ensure that the IIS block is successfully run first before
            # configuring this resource
            DependsOn = "[WindowsFeature]IIS"  # Use for dependencies
        }
    }
}
```

<span data-ttu-id="0d7d3-123">構成を作成するには、PowerShell 関数を呼び出すのと同じ方法で構成ブロックを呼び出し、定義した可能性のあるパラメーター (上記の例では2つ) を渡します。</span><span class="sxs-lookup"><span data-stu-id="0d7d3-123">To create a configuration, invoke the Configuration block the same way you would invoke a PowerShell function, passing in any expected parameters you may have defined (two in the example above).</span></span> <span data-ttu-id="0d7d3-124">たとえば、この場合は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="0d7d3-124">For example, in this case:</span></span>

```powershell
MyWebConfig -MachineName "TestMachine" -WebsiteFilePath `
  "\\filesrv\WebFiles" -OutputPath "C:\Windows\system32\temp"
# OutputPath is optional
```

<span data-ttu-id="0d7d3-125">これにより、指定したパスにあるノードごとに MOF ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="0d7d3-125">This generates a MOF file per node at the path you specify.</span></span> <span data-ttu-id="0d7d3-126">これらの MOF ファイルは、各ノードに必要な構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="0d7d3-126">These MOF files specify the desired configuration for each node.</span></span> <span data-ttu-id="0d7d3-127">次に、次のコマンドレットを使用して、構成 MOF ファイルを解析し、各ノードに対応する構成を送信し、これらの構成を適用します。</span><span class="sxs-lookup"><span data-stu-id="0d7d3-127">Next, use the following cmdlet to parse the configuration MOF files, send each node its corresponding configuration, and enact those configurations.</span></span> <span data-ttu-id="0d7d3-128">クラスベースの DSC リソース用に個別の MOF ファイルを作成する必要はないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0d7d3-128">Note that you do not need to create a separate MOF file for class-based DSC resources.</span></span>

```powershell
Start-DscConfiguration -Verbose -Wait -Path "C:\Windows\system32\temp"
```

## <a name="using-dsc-to-maintain-configuration-state"></a><span data-ttu-id="0d7d3-129">DSC を使用して構成の状態を維持する</span><span class="sxs-lookup"><span data-stu-id="0d7d3-129">USING DSC TO MAINTAIN CONFIGURATION STATE</span></span>

<span data-ttu-id="0d7d3-130">DSC では、構成はべき等です。</span><span class="sxs-lookup"><span data-stu-id="0d7d3-130">With DSC, configuration is idempotent.</span></span> <span data-ttu-id="0d7d3-131">これは、DSC を使用して同じ構成を複数回実行する場合、結果として得られる構成の状態は常に同じであることを意味します。</span><span class="sxs-lookup"><span data-stu-id="0d7d3-131">This means that if you use DSC to enact the same configuration more than once, the resulting configuration state will always be the same.</span></span> <span data-ttu-id="0d7d3-132">このため、環境内のいずれかのノードが望ましい状態からドリフトを持つ可能性があると思われる場合は、同じ DSC 構成を再度実行して、目的の状態に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="0d7d3-132">Because of this, if you suspect that any nodes in your environment may have drifted from the desired state of configuration, you can enact the same DSC configuration again to bring them back to the desired state.</span></span> <span data-ttu-id="0d7d3-133">状態がドリフトであるリソースだけを対象とするように構成スクリプトを変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0d7d3-133">You do not need to modify the configuration script to address only those resources whose state has drifted from the desired state.</span></span>

<span data-ttu-id="0d7d3-134">次の例では、特定のノードでの構成の実際の状態が、ノードで有効になっている最後の DSC 構成からドリフトされているかどうかを確認する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0d7d3-134">The following example shows how you can verify whether the actual state of configuration on a given node has drifted from the last DSC configuration enacted on the node.</span></span> <span data-ttu-id="0d7d3-135">この例では、ローカルコンピューターの構成を確認しています。</span><span class="sxs-lookup"><span data-stu-id="0d7d3-135">In this example we are checking the configuration of the local computer.</span></span>

```powershell
$session = New-CimSession -ComputerName "localhost"
Test-DscConfiguration -CimSession $session
```

## <a name="built-in-dsc-resources"></a><span data-ttu-id="0d7d3-136">組み込みの DSC リソース</span><span class="sxs-lookup"><span data-stu-id="0d7d3-136">BUILT-IN DSC RESOURCES</span></span>

<span data-ttu-id="0d7d3-137">構成スクリプトには、次の組み込みリソースを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0d7d3-137">You can use the following built-in resources in your configuration scripts:</span></span>

|<span data-ttu-id="0d7d3-138">名前</span><span class="sxs-lookup"><span data-stu-id="0d7d3-138">Name</span></span>                  |<span data-ttu-id="0d7d3-139">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0d7d3-139">Properties</span></span>                                         |
|----------------------|---------------------------------------------------|
|<span data-ttu-id="0d7d3-140">ファイル</span><span class="sxs-lookup"><span data-stu-id="0d7d3-140">File</span></span>                  |<span data-ttu-id="0d7d3-141">{DestinationPath, 属性, チェックサム, コンテンツ...}</span><span class="sxs-lookup"><span data-stu-id="0d7d3-141">{DestinationPath, Attributes, Checksum, Content...}</span></span>|
|<span data-ttu-id="0d7d3-142">アーカイブ</span><span class="sxs-lookup"><span data-stu-id="0d7d3-142">Archive</span></span>               |<span data-ttu-id="0d7d3-143">{Destination、Path、Checksum、Credential...}</span><span class="sxs-lookup"><span data-stu-id="0d7d3-143">{Destination, Path, Checksum, Credential...}</span></span>       |
|<span data-ttu-id="0d7d3-144">環境</span><span class="sxs-lookup"><span data-stu-id="0d7d3-144">Environment</span></span>           |<span data-ttu-id="0d7d3-145">{Name, DependsOn, Path...}</span><span class="sxs-lookup"><span data-stu-id="0d7d3-145">{Name, DependsOn, Ensure, Path...}</span></span>                 |
|<span data-ttu-id="0d7d3-146">グループ</span><span class="sxs-lookup"><span data-stu-id="0d7d3-146">Group</span></span>                 |<span data-ttu-id="0d7d3-147">{GroupName、Credential、DependsOn、Description...}</span><span class="sxs-lookup"><span data-stu-id="0d7d3-147">{GroupName, Credential, DependsOn, Description...}</span></span> |
|<span data-ttu-id="0d7d3-148">ログ</span><span class="sxs-lookup"><span data-stu-id="0d7d3-148">Log</span></span>                   |<span data-ttu-id="0d7d3-149">{Message, DependsOn, PsDscRunAsCredential}</span><span class="sxs-lookup"><span data-stu-id="0d7d3-149">{Message, DependsOn, PsDscRunAsCredential}</span></span>         |
|<span data-ttu-id="0d7d3-150">パッケージ</span><span class="sxs-lookup"><span data-stu-id="0d7d3-150">Package</span></span>               |<span data-ttu-id="0d7d3-151">{Name, Path, ProductId, Arguments...}</span><span class="sxs-lookup"><span data-stu-id="0d7d3-151">{Name, Path, ProductId, Arguments...}</span></span>              |
|<span data-ttu-id="0d7d3-152">レジストリ</span><span class="sxs-lookup"><span data-stu-id="0d7d3-152">Registry</span></span>              |<span data-ttu-id="0d7d3-153">{Key, ValueName, DependsOn, 確認...}</span><span class="sxs-lookup"><span data-stu-id="0d7d3-153">{Key, ValueName, DependsOn, Ensure...}</span></span>             |
|<span data-ttu-id="0d7d3-154">スクリプト</span><span class="sxs-lookup"><span data-stu-id="0d7d3-154">Script</span></span>                |<span data-ttu-id="0d7d3-155">{GetScript、SetScript、TestScript、Credential...}</span><span class="sxs-lookup"><span data-stu-id="0d7d3-155">{GetScript, SetScript, TestScript, Credential...}</span></span>  |
|<span data-ttu-id="0d7d3-156">サービス</span><span class="sxs-lookup"><span data-stu-id="0d7d3-156">Service</span></span>               |<span data-ttu-id="0d7d3-157">{Name, BuiltInAccount, Credential, Dependencies...}</span><span class="sxs-lookup"><span data-stu-id="0d7d3-157">{Name, BuiltInAccount, Credential, Dependencies...}</span></span>|
|<span data-ttu-id="0d7d3-158">User</span><span class="sxs-lookup"><span data-stu-id="0d7d3-158">User</span></span>                  |<span data-ttu-id="0d7d3-159">{UserName, DependsOn, Description, Disabled...}</span><span class="sxs-lookup"><span data-stu-id="0d7d3-159">{UserName, DependsOn, Description, Disabled...}</span></span>    |
|<span data-ttu-id="0d7d3-160">WaitForAll</span><span class="sxs-lookup"><span data-stu-id="0d7d3-160">WaitForAll</span></span>            |<span data-ttu-id="0d7d3-161">{NodeName, DependsOn, PsDscRunAsC...}</span><span class="sxs-lookup"><span data-stu-id="0d7d3-161">{NodeName, ResourceName, DependsOn, PsDscRunAsC...}</span></span>|
|<span data-ttu-id="0d7d3-162">WaitForAny</span><span class="sxs-lookup"><span data-stu-id="0d7d3-162">WaitForAny</span></span>            |<span data-ttu-id="0d7d3-163">{NodeName, DependsOn, PsDscRunAsC...}</span><span class="sxs-lookup"><span data-stu-id="0d7d3-163">{NodeName, ResourceName, DependsOn, PsDscRunAsC...}</span></span>|
|<span data-ttu-id="0d7d3-164">WaitForSome</span><span class="sxs-lookup"><span data-stu-id="0d7d3-164">WaitForSome</span></span>           |<span data-ttu-id="0d7d3-165">{NodeCount, NodeName,, DependsOn...}</span><span class="sxs-lookup"><span data-stu-id="0d7d3-165">{NodeCount, NodeName, ResourceName, DependsOn...}</span></span>  |
|<span data-ttu-id="0d7d3-166">WindowsFeature</span><span class="sxs-lookup"><span data-stu-id="0d7d3-166">WindowsFeature</span></span>        |<span data-ttu-id="0d7d3-167">{Name, Credential, DependsOn, 確認...}</span><span class="sxs-lookup"><span data-stu-id="0d7d3-167">{Name, Credential, DependsOn, Ensure...}</span></span>           |
|<span data-ttu-id="0d7d3-168">WindowsOptionalFeature</span><span class="sxs-lookup"><span data-stu-id="0d7d3-168">WindowsOptionalFeature</span></span>|<span data-ttu-id="0d7d3-169">{Name, DependsOn, LogLevel...}</span><span class="sxs-lookup"><span data-stu-id="0d7d3-169">{Name, DependsOn, Ensure, LogLevel...}</span></span>             |
|<span data-ttu-id="0d7d3-170">WindowsProcess</span><span class="sxs-lookup"><span data-stu-id="0d7d3-170">WindowsProcess</span></span>        |<span data-ttu-id="0d7d3-171">{Arguments, Path, Credential, DependsOn...}</span><span class="sxs-lookup"><span data-stu-id="0d7d3-171">{Arguments, Path, Credential, DependsOn...}</span></span>        |

<span data-ttu-id="0d7d3-172">システムで使用可能な DSC リソースの一覧を取得するには、コマンドレットを実行し `Get-DscResource` ます。</span><span class="sxs-lookup"><span data-stu-id="0d7d3-172">To get a list of available DSC resources on your system, run the `Get-DscResource` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="0d7d3-173">PowerShell バージョン 7.0 より前のバージョンでは、`Get-DscResource` によるクラス ベースの DSC リソースの検出は行われません。</span><span class="sxs-lookup"><span data-stu-id="0d7d3-173">In PowerShell versions below 7.0, `Get-DscResource` does not find Class based DSC resources.</span></span>

<span data-ttu-id="0d7d3-174">このトピックの例では、File リソースと Add-windowsfeature リソースの使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0d7d3-174">The example in this topic demonstrates how to use the File and WindowsFeature resources.</span></span> <span data-ttu-id="0d7d3-175">リソースで使用できるすべてのプロパティを表示するには、PowerShell ISE の構成スクリプト内のリソースキーワード (ファイルなど) にカーソルを挿入し、 <kbd>CTRL</kbd> + <kbd>space</kbd>キーを押したままにします。</span><span class="sxs-lookup"><span data-stu-id="0d7d3-175">To see all properties that you can use with a resource, insert the cursor in the resource keyword (for example, File) within your configuration script in PowerShell ISE, hold down <kbd>CTRL</kbd>+<kbd>SPACEBAR</kbd></span></span>

## <a name="find-more-resources"></a><span data-ttu-id="0d7d3-176">その他のリソースを検索する</span><span class="sxs-lookup"><span data-stu-id="0d7d3-176">FIND MORE RESOURCES</span></span>

<span data-ttu-id="0d7d3-177">PowerShell と DSC ユーザーコミュニティ、および Microsoft によって作成されたその他の利用可能な DSC リソースをダウンロードしてインストールし、学習することができます。</span><span class="sxs-lookup"><span data-stu-id="0d7d3-177">You can download, install, and learn about many other available DSC resources that have been created by the PowerShell and DSC user community, and by Microsoft.</span></span> <span data-ttu-id="0d7d3-178">[PowerShell ギャラリー](https://www.powershellgallery.com/)にアクセスして、利用可能な DSC リソースを参照し、詳細を確認してください。</span><span class="sxs-lookup"><span data-stu-id="0d7d3-178">Visit the [PowerShell Gallery](https://www.powershellgallery.com/) to browse and learn about available DSC resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="0d7d3-179">関連項目</span><span class="sxs-lookup"><span data-stu-id="0d7d3-179">SEE ALSO</span></span>

[<span data-ttu-id="0d7d3-180">PowerShell Desired State Configuration の概要</span><span class="sxs-lookup"><span data-stu-id="0d7d3-180">PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/overview)

[<span data-ttu-id="0d7d3-181">PowerShell Desired State Configuration の組み込みリソース</span><span class="sxs-lookup"><span data-stu-id="0d7d3-181">Built-In PowerShell Desired State Configuration Resources</span></span>](/powershell/scripting/dsc/resources/resources)

[<span data-ttu-id="0d7d3-182">カスタム PowerShell Desired State Configuration リソースのビルド</span><span class="sxs-lookup"><span data-stu-id="0d7d3-182">Build Custom PowerShell Desired State Configuration Resources</span></span>](/powershell/scripting/dsc/resources/authoringResource)
