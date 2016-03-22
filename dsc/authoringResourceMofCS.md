# C`#` での DSC リソースの作成

> 適用先: Windows PowerShell 4.0、Windows PowerShell 5.0

通常、Windows PowerShell Desired State Configuration (DSC) カスタム リソースは、PowerShell スクリプトで実装されます。 ただし、C# でコマンドレットを記述して、DSC カスタム リソースの機能を実装することもできます。 C# でのコマンドレットの記述の概要については、「[Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)](https://technet.microsoft.com/en-us/library/dd878294.aspx)」を参照してください。

C# でコマンドレットとしてリソースを実装すること以外に、MOF スキーマの作成、フォルダー構造の作成、およびカスタム DSC リソースのインポートと使用のプロセスは、「[MOF を使用したカスタム DSC リソースの記述](authoringResourceMOF.md)」で説明されていることと同じです。

## コマンドレットベースのリソースの記述
この例では、テキスト ファイルとその内容を管理する単純なリソースを実装します。

### MOF スキーマの記述

MOF リソースの定義を次に示します。

```
[ClassVersion("1.0.0"), FriendlyName("xDemoFile")]
class MSFT_XDemoFile : OMI_BaseResource
{
                [Key, Description("path")] String Path;
                [Write, Description("Should the file be present"), ValueMap{"Present","Absent"}, Values{"Present","Absent"}] String Ensure;
                [Write, Description("Contentof file.")] String Content;                   
};
```

### Visual Studio プロジェクトの設定
#### コマンドレット プロジェクトの設定

1. Visual Studio を開きます。
1. C# プロジェクトを作成し、名前を指定します。
1. 使用可能なプロジェクト テンプレートから **[クラス ライブラリ]** を選択します。
1. **[OK]** をクリックします。
1. System.Automation.Management.dll へのアセンブリ参照をプロジェクトに追加します。
1. リソース名と一致するようにアセンブリ名を変更します。 この例では、アセンブリは **MSFT_XDemoFile** という名前にする必要があります。

### コマンドレット コードの記述

次の C# コードでは、**Get-TargetResource**、**Set-TargetResource**、および **Test-TargetResource** コマンドレットを実装します。

```C#
Get-TargetResource
       [OutputType(typeof(System.Collections.Hashtable))]
       [Cmdlet(VerbsCommon.Get, "TargetResource")]
       public class GetTargetResource : PSCmdlet
       {
              [Parameter(Mandatory = true)]
              public string Path { get; set; }
 
///<summary>
/// Implement the logic to write the current state of the resource as a 
/// Hash table with keys being the resource properties 
/// and the Values are the corresponding current values on the target machine.
 
///</summary>
              protected override void ProcessRecord()
              {
// Download the zip file at the end of this blog to see sample implementation.
 }
 
Set-TargetResouce
         [OutputType(typeof(void))]
    [Cmdlet(VerbsCommon.Set, "TargetResource")]
    public class SetTargetResource : PSCmdlet
    {
        privatestring _ensure;
        privatestring _content;
        
[Parameter(Mandatory = true)]
        public string Path { get; set; }
        
[Parameter(Mandatory = false)]      
       [ValidateSet("Present", "Absent", IgnoreCase = true)]
       public string Ensure {
            get
            {
                // set the default to present.
               return (this._ensure ?? "Present");
            }
            set
            {
                this._ensure = value;
            }
           } 
            public string Content {
            get { return (string.IsNullOrEmpty(this._content) ? "" : this._content); }
            set { this._content = value; }
        }
 
///<summary>
        /// Implement the logic to set the state of the machine to the desired state.
        ///</summary>
        protected override void ProcessRecord()
        {
//Implement the set method of the resource 
/* Uncomment this section if your resource needs a machine reboot.
PSVariable DscMachineStatus = new PSVariable("DSCMachineStatus", 1, ScopedItemOptions.AllScope);
                this.SessionState.PSVariable.Set(DscMachineStatus);
*/     
  }
    }
Test-TargetResource    
       [Cmdlet("Test", "TargetResource")]
    [OutputType(typeof(Boolean))]
    public class TestTargetResource : PSCmdlet
    {   
        
        private string _ensure;
        private string _content;
 
        [Parameter(Mandatory = true)]
        public string Path { get; set; }
 
        [Parameter(Mandatory = false)]
        [ValidateSet("Present", "Absent", IgnoreCase = true)]
        public string Ensure
        {
            get
            {
                // set the default to present.
                return (this._ensure ?? "Present");
            }
            set
            {
                this._ensure = value;
            }
        }
 
        [Parameter(Mandatory = false)]
        public string Content
        {
            get { return (string.IsNullOrEmpty(this._content) ? "“:this._content);}
            set { this._content = value; }
        }
 
///<summary>
/// Write a Boolean value which indicates whether the current machine is in    
/// desired state or not.
        ///</summary>
        protected override void ProcessRecord()
        {
                // Implement the test method of the resource.
        }
}
```

### リソースの展開

コンパイル済み dll ファイルは、スクリプトベースのリソースと同様のファイル構造で保存する必要があります。 このリソースのフォルダー構造を次に示します。

```
$env: psmodulepath (folder)
    |- MyDscResources (folder)
        |- DSCResources (folder)
            |- MSFT_XDemoFile (folder)
                |- MSFT_XDemoFile.psd1 (file, optional)
                |- MSFT_XDemoFile.dll (file, required)
                |- MSFT_XDemoFile.schema.mof (file, required)
```

### 参照
#### 概念
[MOF を使用したカスタム DSC リソースの記述](authoringResourceMOF.md)
#### その他のリソース
[Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)](https://msdn.microsoft.com/en-us/library/dd878294.aspx)<!--HONumber=Feb16_HO4-->
