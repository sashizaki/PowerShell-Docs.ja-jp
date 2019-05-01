---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: '複合リソース: リソースとしての DSC 構成の使用'
ms.openlocfilehash: 2823d05e0c8feb2933ca691f9ab5149ace2f7ee3
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62076686"
---
# <a name="composite-resources-using-a-dsc-configuration-as-a-resource"></a><span data-ttu-id="0c9ab-103">複合リソース:リソースとしての DSC 構成の使用</span><span class="sxs-lookup"><span data-stu-id="0c9ab-103">Composite resources: Using a DSC configuration as a resource</span></span>

> <span data-ttu-id="0c9ab-104">適用先:Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="0c9ab-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="0c9ab-105">実際の状況では、構成は多くのさまざまなリソースを呼び出したり、膨大な数のプロパティを設定したりするため、長く複雑になることがあります。</span><span class="sxs-lookup"><span data-stu-id="0c9ab-105">In real-world situations, configurations can become long and complex, calling many different resources and setting a vast number of properties.</span></span> <span data-ttu-id="0c9ab-106">このような複雑さに対処するために、Windows PowerShell Desired State Configuration (DSC) 構成を他の構成のリソースとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="0c9ab-106">To help address this complexity, you can use a Windows PowerShell Desired State Configuration (DSC) configuration as a resource for other configurations.</span></span> <span data-ttu-id="0c9ab-107">これは、複合リソースと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="0c9ab-107">We call this a composite resource.</span></span> <span data-ttu-id="0c9ab-108">複合リソースは、パラメーターを受け取る DSC 構成です。</span><span class="sxs-lookup"><span data-stu-id="0c9ab-108">A composite resource is a DSC configuration that takes parameters.</span></span> <span data-ttu-id="0c9ab-109">構成のパラメーターは、リソースのプロパティとして機能します。</span><span class="sxs-lookup"><span data-stu-id="0c9ab-109">The parameters of the configuration act as the properties of the resource.</span></span> <span data-ttu-id="0c9ab-110">構成は **.schema.psm1** 拡張子のファイルとして保存され、一般的な DSC リソースの MOF スキーマとリソース スクリプトの両方に代わるものです。DSC リソースの詳細については、[「DSC リソース」](resources.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c9ab-110">The configuration is saved as a file with a **.schema.psm1** extension, and takes the place of both the MOF schema and the resource script in a typical DSC resource (for more information about DSC resources, see [Windows PowerShell Desired State Configuration Resources](resources.md).</span></span>

## <a name="creating-the-composite-resource"></a><span data-ttu-id="0c9ab-111">複合リソースの作成</span><span class="sxs-lookup"><span data-stu-id="0c9ab-111">Creating the composite resource</span></span>

<span data-ttu-id="0c9ab-112">この例では、仮想マシンを構成するために多くの既存のリソースを呼び出す構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="0c9ab-112">In our example, we create a configuration that invokes a number of existing resources to configure virtual machines.</span></span> <span data-ttu-id="0c9ab-113">構成ブロックで設定する値を指定する代わりに、構成では数多くのパラメーターを受け取り、後でそれが構成ブロックで使用されます。</span><span class="sxs-lookup"><span data-stu-id="0c9ab-113">Instead of specifying the values to be set in configuration blocks, the configuration takes a number of parameters that are then used in the configuration blocks.</span></span>

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

### <a name="saving-the-configuration-as-a-composite-resource"></a><span data-ttu-id="0c9ab-114">複合リソースとしての構成の保存</span><span class="sxs-lookup"><span data-stu-id="0c9ab-114">Saving the configuration as a composite resource</span></span>

<span data-ttu-id="0c9ab-115">パラメーター化された構成を DSC リソースとして使用するには、他の MOF ベースのリソースに似たディレクトリ構造で保存し、**.schema.psm1** 拡張子を持つ名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="0c9ab-115">To use the parameterized configuration as a DSC resource, save it in a directory structure like that of any other MOF-based resource, and name it with a **.schema.psm1** extension.</span></span> <span data-ttu-id="0c9ab-116">この例では、ファイルに **xVirtualMachine.schema.psm1** という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="0c9ab-116">For this example, we’ll name the file **xVirtualMachine.schema.psm1**.</span></span> <span data-ttu-id="0c9ab-117">次の行を含む **xVirtualMachine.psd1** というマニフェストも作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c9ab-117">You also need to create a manifest named **xVirtualMachine.psd1** that contains the following line.</span></span> <span data-ttu-id="0c9ab-118">これは、**MyDscResources.psd1** に加えて **MyDscResources** フォルダーの下に格納されるすべてのリソースのモジュール マニフェストです。</span><span class="sxs-lookup"><span data-stu-id="0c9ab-118">Note that this is in addition to **MyDscResources.psd1**, the module manifest for all resources under the **MyDscResources** folder.</span></span>

```powershell
RootModule = 'xVirtualMachine.schema.psm1'
```

<span data-ttu-id="0c9ab-119">完了すると、フォルダー構造は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="0c9ab-119">When you are done, the folder structure should be as follows.</span></span>

```
$env: psmodulepath
    |- MyDscResources
           MyDscResources.psd1
        |- DSCResources
            |- xVirtualMachine
                |- xVirtualMachine.psd1
                |- xVirtualMachine.schema.psm1
```

<span data-ttu-id="0c9ab-120">これで、リソースは Get-DscResource コマンドレットを使用して検出できるようになり、そのプロパティは、そのコマンドレットまたは Windows PowerShell ISE の **Ctrl + Space** キーによるオートコンプリートを使用して検出できるようになります。</span><span class="sxs-lookup"><span data-stu-id="0c9ab-120">The resource is now discoverable by using the Get-DscResource cmdlet, and its properties are discoverable by either that cmdlet or by using **Ctrl+Space** auto-complete in the Windows PowerShell ISE.</span></span>

## <a name="using-the-composite-resource"></a><span data-ttu-id="0c9ab-121">複合リソースの使用</span><span class="sxs-lookup"><span data-stu-id="0c9ab-121">Using the composite resource</span></span>

<span data-ttu-id="0c9ab-122">次に、複合リソースを呼び出す構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="0c9ab-122">Next we create a configuration that calls the composite resource.</span></span> <span data-ttu-id="0c9ab-123">この構成は、xVirtualMachine 複合リソースを呼び出して仮想マシンを作成してから、**xComputer** リソースを呼び出して名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="0c9ab-123">This configuration calls the xVirtualMachine composite resource to create a virtual machine, and then calls the **xComputer** resource to rename it.</span></span>

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

## <a name="supporting-psdscrunascredential"></a><span data-ttu-id="0c9ab-124">PsDscRunAsCredential のサポート</span><span class="sxs-lookup"><span data-stu-id="0c9ab-124">Supporting PsDscRunAsCredential</span></span>

><span data-ttu-id="0c9ab-125">**注:** **PsDscRunAsCredential** は PowerShell 5.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0c9ab-125">**Note:** **PsDscRunAsCredential** is supported in PowerShell 5.0 and later.</span></span>

<span data-ttu-id="0c9ab-126">**PsDscRunAsCredential** プロパティを [DSC 構成](../configurations/configurations.md)リソース ブロックで使用して、指定した資格情報のもとでリソースを実行する必要があることを指定できます。</span><span class="sxs-lookup"><span data-stu-id="0c9ab-126">The **PsDscRunAsCredential** property can be used in [DSC configurations](../configurations/configurations.md) resource block to specify that the resource should be run under a specified set of credentials.</span></span>
<span data-ttu-id="0c9ab-127">詳細については、「[ユーザーの資格情報を指定して DSC を実行する](../configurations/runAsUser.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c9ab-127">For more information, see [Running DSC with user credentials](../configurations/runAsUser.md).</span></span>

<span data-ttu-id="0c9ab-128">カスタム リソース内からユーザー コンテキストにアクセスするには、自動変数 `$PsDscContext` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0c9ab-128">To access the user context from within a custom resource, you can use the automatic variable `$PsDscContext`.</span></span>

<span data-ttu-id="0c9ab-129">たとえば、次のコードは、リソースが詳細出力ストリームに実行しているユーザー コンテキストを記述します。</span><span class="sxs-lookup"><span data-stu-id="0c9ab-129">For example the following code would write the user context under which the resource is running to the verbose output stream:</span></span>

```powershell
if ($PsDscContext.RunAsUser) {
    Write-Verbose "User: $PsDscContext.RunAsUser";
}
```

## <a name="see-also"></a><span data-ttu-id="0c9ab-130">参照</span><span class="sxs-lookup"><span data-stu-id="0c9ab-130">See Also</span></span>
### <a name="concepts"></a><span data-ttu-id="0c9ab-131">概念</span><span class="sxs-lookup"><span data-stu-id="0c9ab-131">Concepts</span></span>
* [<span data-ttu-id="0c9ab-132">MOF を使用したカスタム DSC リソースの記述</span><span class="sxs-lookup"><span data-stu-id="0c9ab-132">Writing a custom DSC resource with MOF</span></span>](authoringResourceMOF.md)
* [<span data-ttu-id="0c9ab-133">Windows PowerShell Desired State Configuration の概要</span><span class="sxs-lookup"><span data-stu-id="0c9ab-133">Get Started with Windows PowerShell Desired State Configuration</span></span>](../overview/overview.md)