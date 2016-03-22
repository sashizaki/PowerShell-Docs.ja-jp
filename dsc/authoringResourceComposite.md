# 複合リソース: リソースとしての DSC 構成の使用

> 適用先: Windows PowerShell 4.0、Windows PowerShell 5.0

実際の状況では、構成は多くのさまざまなリソースを呼び出したり、膨大な数のプロパティを設定したりするため、長く複雑になることがあります。 このような複雑さに対処するために、Windows PowerShell Desired State Configuration (DSC) 構成を他の構成のリソースとして使用できます。 これは、複合リソースと呼ばれます。 複合リソースは、パラメーターを受け取る DSC 構成です。 構成のパラメーターは、リソースのプロパティとして機能します。 構成は **.schema.psm1** 拡張子のファイルとして保存され、一般的な DSC リソースの MOF スキーマとリソース スクリプトの両方に代わるものです。DSC リソースの詳細については、[「DSC リソース」](resources.md)を参照してください。

## 複合リソースの作成

この例では、仮想マシンを構成するために多くの既存のリソースを呼び出す構成を作成します。 構成ブロックで設定する値を指定する代わりに、構成では数多くのパラメーターを受け取り、後でそれが構成ブロックで使用されます。

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

    # Creae VM specific diff VHD
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

### 複合リソースとしての構成の保存

パラメーター化された構成を DSC リソースとして使用するには、他の MOF ベースのリソースに似たディレクトリ構造で保存し、**.schema.psm1** 拡張子を持つ名前を指定します。 この例では、ファイルに **xVirtualMachine.schema.psm1** という名前を付けます。 次の行を含む **xVirtualMachine.psd1** というマニフェストも作成する必要があります。 これは、**MyDscResources.psd1** に加えて **MyDscResources** フォルダーの下に格納されるすべてのリソースのモジュール マニフェストです。

```powershell
RootModule = 'xVirtualMachine.schema.psm1'
```

完了すると、フォルダー構造は次のようになります。

```
$env: psmodulepath
    |- MyDscResources
           MyDscResources.psd1
        |- DSC Resources
            |- xVirtualMachine
                |- xVirtualMachine.psd1
                |- xVirtualMachine.schema.psm1
```

これで、リソースは Get-DscResource コマンドレットを使用して検出できるようになり、そのプロパティは、そのコマンドレットまたは Windows PowerShell ISE の **Ctrl + Space** キーによるオートコンプリートを使用して検出できるようになります。

## 複合リソースの使用

次に、複合リソースを呼び出す構成を作成します。 この構成は、xVirtualMachine 複合リソースを呼び出して仮想マシンを作成してから、**xComputer** リソースを呼び出して名前を変更します。

```powershell

configuration RenameVM
{

    Import-DscResource -Module TestCompositeResource
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

## 参照
### 概念
* [MOF を使用したカスタム DSC リソースの記述](authoringResourceMOF.md)
* [Windows PowerShell Desired State Configuration の概要](overview.md)
<!--HONumber=Feb16_HO4-->
