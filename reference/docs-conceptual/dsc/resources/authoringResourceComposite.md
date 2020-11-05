---
ms.date: 07/08/2020
keywords: DSC, PowerShell, 構成, セットアップ
title: 複合リソース - リソースとしての DSC 構成の使用
description: この記事では、複合リソースを作成および使用する方法について説明します。
ms.openlocfilehash: c1f0e3b45c3a393c04700b5a4bc88be365794820
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92667302"
---
# <a name="composite-resources-using-a-dsc-configuration-as-a-resource"></a><span data-ttu-id="dbaaa-104">複合リソース: リソースとしての DSC 構成の使用</span><span class="sxs-lookup"><span data-stu-id="dbaaa-104">Composite resources: Using a DSC configuration as a resource</span></span>

> <span data-ttu-id="dbaaa-105">適用先:Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="dbaaa-105">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="dbaaa-106">実際の状況では、構成は多くのさまざまなリソースを呼び出したり、膨大な数のプロパティを設定したりするため、長く複雑になることがあります。</span><span class="sxs-lookup"><span data-stu-id="dbaaa-106">In real-world situations, configurations can become long and complex, calling many different resources and setting a vast number of properties.</span></span> <span data-ttu-id="dbaaa-107">このような複雑さに対処するために、Windows PowerShell Desired State Configuration (DSC) 構成を他の構成のリソースとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="dbaaa-107">To help address this complexity, you can use a Windows PowerShell Desired State Configuration (DSC) configuration as a resource for other configurations.</span></span> <span data-ttu-id="dbaaa-108">これは、複合リソースと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="dbaaa-108">This is called a composite resource.</span></span> <span data-ttu-id="dbaaa-109">複合リソースは、パラメーターを受け取る DSC 構成です。</span><span class="sxs-lookup"><span data-stu-id="dbaaa-109">A composite resource is a DSC configuration that takes parameters.</span></span> <span data-ttu-id="dbaaa-110">構成のパラメーターは、リソースのプロパティとして機能します。</span><span class="sxs-lookup"><span data-stu-id="dbaaa-110">The parameters of the configuration act as the properties of the resource.</span></span>
<span data-ttu-id="dbaaa-111">構成は、拡張子が `.schema.psm1` のファイルとして保存されます。</span><span class="sxs-lookup"><span data-stu-id="dbaaa-111">The configuration is saved as a file with a `.schema.psm1` extension.</span></span> <span data-ttu-id="dbaaa-112">MOF スキーマと、一般的な DSC リソースのリソース スクリプトの両方の代わりになります。</span><span class="sxs-lookup"><span data-stu-id="dbaaa-112">It takes the place of both the MOF schema, and the resource script in a typical DSC resource.</span></span> <span data-ttu-id="dbaaa-113">DSC リソースの詳細については、[Windows PowerShell Desired State Configuration](resources.md) に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbaaa-113">For more information about DSC resources, see [Windows PowerShell Desired State Configuration Resources](resources.md).</span></span>

## <a name="creating-the-composite-resource"></a><span data-ttu-id="dbaaa-114">複合リソースの作成</span><span class="sxs-lookup"><span data-stu-id="dbaaa-114">Creating the composite resource</span></span>

<span data-ttu-id="dbaaa-115">この例では、仮想マシンを構成するために多くの既存のリソースを呼び出す構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="dbaaa-115">In our example, we create a configuration that invokes a number of existing resources to configure virtual machines.</span></span> <span data-ttu-id="dbaaa-116">構成ブロックで設定する値を指定する代わりに、構成ではパラメーターが受け取られ、後でそれが構成ブロックで使用されます。</span><span class="sxs-lookup"><span data-stu-id="dbaaa-116">Instead of specifying the values to be set in configuration blocks, the configuration takes in parameters that are then used in the configuration blocks.</span></span>

```powershell
Configuration xVirtualMachine
{
    param
    (
        # Name of VMs
        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [String[]] $VMName,

        # Name of Switch to create
        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [String] $SwitchName,

        # Type of Switch to create
        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [String] $SwitchType,

        # Source Path for VHD
        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [String] $VHDParentPath,

        # Destination path for diff VHD
        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [String] $VHDPath,

        # Startup Memory for VM
        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [String] $VMStartupMemory,

        # State of the VM
        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [String] $VMState
    )

    # Import the module that defines custom resources
    Import-DscResource -Module xComputerManagement,xHyper-V

    # Install the Hyper-V role
    WindowsFeature HyperV
    {
        Ensure = "Present"
        Name = "Hyper-V"
    }

    # Create the virtual switch
    xVMSwitch $SwitchName
    {
        Ensure = "Present"
        Name = $SwitchName
        Type = $SwitchType
        DependsOn = "[WindowsFeature]HyperV"
    }

    # Check for Parent VHD file
    File ParentVHDFile
    {
        Ensure = "Present"
        DestinationPath = $VHDParentPath
        Type = "File"
        DependsOn = "[WindowsFeature]HyperV"
    }

    # Check the destination VHD folder
    File VHDFolder
    {
        Ensure = "Present"
        DestinationPath = $VHDPath
        Type = "Directory"
        DependsOn = "[File]ParentVHDFile"
    }

    # Create VM specific diff VHD
    foreach ($Name in $VMName)
    {
        xVHD "VHD$Name"
        {
            Ensure = "Present"
            Name = $Name
            Path = $VHDPath
            ParentPath = $VHDParentPath
            DependsOn = @("[WindowsFeature]HyperV",
                          "[File]VHDFolder")
        }
    }

    # Create VM using the above VHD
    foreach($Name in $VMName)
    {
        xVMHyperV "VMachine$Name"
        {
            Ensure = "Present"
            Name = $Name
            VhDPath = (Join-Path -Path $VHDPath -ChildPath $Name)
            SwitchName = $SwitchName
            StartupMemory = $VMStartupMemory
            State = $VMState
            MACAddress = $MACAddress
            WaitForIP = $true
            DependsOn = @("[WindowsFeature]HyperV",
                          "[xVHD]VHD$Name")
        }
    }
}
```

> [!NOTE]
> <span data-ttu-id="dbaaa-117">現在、DSC では、複合リソースまたは入れ子になった構成を複合リソース内に配置することはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="dbaaa-117">DSC doesn't currently support placing composite resources or nested configurations within a composite resource.</span></span>

### <a name="saving-the-configuration-as-a-composite-resource"></a><span data-ttu-id="dbaaa-118">複合リソースとしての構成の保存</span><span class="sxs-lookup"><span data-stu-id="dbaaa-118">Saving the configuration as a composite resource</span></span>

<span data-ttu-id="dbaaa-119">パラメーター化された構成を DSC リソースとして使用するには、他の MOF ベースのリソースに似たディレクトリ構造で保存し、`.schema.psm1` 拡張子を持つ名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="dbaaa-119">To use the parameterized configuration as a DSC resource, save it in a directory structure like that of any other MOF-based resource, and name it with a `.schema.psm1` extension.</span></span> <span data-ttu-id="dbaaa-120">この例では、ファイルに `xVirtualMachine.schema.psm1` という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="dbaaa-120">For this example, we'll name the file `xVirtualMachine.schema.psm1`.</span></span> <span data-ttu-id="dbaaa-121">次の行を含む `xVirtualMachine.psd1` というマニフェストも作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbaaa-121">You also need to create a manifest named `xVirtualMachine.psd1` that contains the following line.</span></span>

```powershell
RootModule = 'xVirtualMachine.schema.psm1'
```

> [!NOTE]
> <span data-ttu-id="dbaaa-122">これは、`MyDscResources` フォルダーにあるすべてのリソースのモジュール マニフェストである `MyDscResources.psd1` に追加されます。</span><span class="sxs-lookup"><span data-stu-id="dbaaa-122">This is in addition to `MyDscResources.psd1`, the module manifest for all resources under the `MyDscResources` folder.</span></span>

<span data-ttu-id="dbaaa-123">完了すると、フォルダー構造は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="dbaaa-123">When you are done, the folder structure should be as follows.</span></span>

```
$env: psmodulepath
    |- MyDscResources
        |- MyDscResources.psd1
        |- DSCResources
            |- xVirtualMachine
                |- xVirtualMachine.psd1
                |- xVirtualMachine.schema.psm1
```

<span data-ttu-id="dbaaa-124">これで、リソースは `Get-DscResource` コマンドレットを使用して検出できるようになり、そのプロパティは、そのコマンドレットまたは Windows PowerShell ISE の <kbd>Ctrl</kbd> + <kbd>Space</kbd> キーによるオートコンプリートを使用して検出できるようになります。</span><span class="sxs-lookup"><span data-stu-id="dbaaa-124">The resource is now discoverable by using the `Get-DscResource` cmdlet, and its properties are discoverable by either that cmdlet or by using <kbd>Ctrl</kbd>+<kbd>Space</kbd> autocomplete in the Windows PowerShell ISE.</span></span>

## <a name="using-the-composite-resource"></a><span data-ttu-id="dbaaa-125">複合リソースの使用</span><span class="sxs-lookup"><span data-stu-id="dbaaa-125">Using the composite resource</span></span>

<span data-ttu-id="dbaaa-126">次に、複合リソースを呼び出す構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="dbaaa-126">Next we create a configuration that calls the composite resource.</span></span> <span data-ttu-id="dbaaa-127">この構成は、xVirtualMachine 複合リソースを呼び出して仮想マシンを作成してから、 **xComputer** リソースを呼び出して名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="dbaaa-127">This configuration calls the xVirtualMachine composite resource to create a virtual machine, and then calls the **xComputer** resource to rename it.</span></span>

```powershell
configuration RenameVM
{
    Import-DscResource -Module xVirtualMachine
    Node localhost
    {
        xVirtualMachine VM
        {
            VMName = "Test"
            SwitchName = "Internal"
            SwitchType = "Internal"
            VhdParentPath = "C:\Demo\VHD\RTM.vhd"
            VHDPath = "C:\Demo\VHD"
            VMStartupMemory = 1024MB
            VMState = "Running"
        }
    }

    Node "192.168.10.1"
    {
        xComputer Name
        {
            Name = "SQL01"
            DomainName = "fourthcoffee.com"
        }
    }
}
```

<span data-ttu-id="dbaaa-128">このリソースを使用して複数の VM を作成することもできます。具体的には VM 名の配列を xVirtualMachine リソースに渡します。</span><span class="sxs-lookup"><span data-stu-id="dbaaa-128">You can also use this resource to create multiple VMs by passing in an array of VM names to the xVirtualMachine resource.</span></span>

```PowerShell
Configuration MultipleVms
{
    Import-DscResource -Module xVirtualMachine
    Node localhost
    {
        xVirtualMachine VMs
        {
            VMName = "IIS01", "SQL01", "SQL02"
            SwitchName = "Internal"
            SwitchType = "Internal"
            VhdParentPath = "C:\Demo\VHD\RTM.vhd"
            VHDPath = "C:\Demo\VHD"
            VMStartupMemory = 1024MB
            VMState = "Running"
        }
    }
}
```

## <a name="supporting-psdscrunascredential"></a><span data-ttu-id="dbaaa-129">PsDscRunAsCredential のサポート</span><span class="sxs-lookup"><span data-stu-id="dbaaa-129">Supporting PsDscRunAsCredential</span></span>

> [!NOTE]
> <span data-ttu-id="dbaaa-130">**PsDscRunAsCredential** は PowerShell 5.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="dbaaa-130">**PsDscRunAsCredential** is supported in PowerShell 5.0 and later.</span></span>

<span data-ttu-id="dbaaa-131">**PsDscRunAsCredential** プロパティを [DSC 構成](../configurations/configurations.md)リソース ブロックで使用して、指定した資格情報のもとでリソースを実行する必要があることを指定できます。</span><span class="sxs-lookup"><span data-stu-id="dbaaa-131">The **PsDscRunAsCredential** property can be used in [DSC configurations](../configurations/configurations.md) resource block to specify that the resource should be run under a specified set of credentials.</span></span> <span data-ttu-id="dbaaa-132">詳細については、「[ユーザーの資格情報を指定して DSC を実行する](../configurations/runAsUser.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbaaa-132">For more information, see [Running DSC with user credentials](../configurations/runAsUser.md).</span></span>

<span data-ttu-id="dbaaa-133">カスタム リソース内からユーザー コンテキストにアクセスするには、自動変数 `$PsDscContext` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="dbaaa-133">To access the user context from within a custom resource, you can use the automatic variable `$PsDscContext`.</span></span>

<span data-ttu-id="dbaaa-134">たとえば、次のコードでは、リソースが実行されているユーザー コンテキストが、詳細出力ストリームに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="dbaaa-134">For example, the following code would write the user context under which the resource is running to the verbose output stream:</span></span>

```powershell
if ($PsDscContext.RunAsUser) {
    Write-Verbose "User: $PsDscContext.RunAsUser";
}
```

## <a name="see-also"></a><span data-ttu-id="dbaaa-135">参照</span><span class="sxs-lookup"><span data-stu-id="dbaaa-135">See Also</span></span>

### <a name="concepts"></a><span data-ttu-id="dbaaa-136">概念</span><span class="sxs-lookup"><span data-stu-id="dbaaa-136">Concepts</span></span>

- [<span data-ttu-id="dbaaa-137">MOF を使用したカスタム DSC リソースの記述</span><span class="sxs-lookup"><span data-stu-id="dbaaa-137">Writing a custom DSC resource with MOF</span></span>](authoringResourceMOF.md)
- [<span data-ttu-id="dbaaa-138">Windows PowerShell Desired State Configuration の概要</span><span class="sxs-lookup"><span data-stu-id="dbaaa-138">Get Started with Windows PowerShell Desired State Configuration</span></span>](../overview/overview.md)
