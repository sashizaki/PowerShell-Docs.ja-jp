---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: C# での DSC リソースの作成
ms.openlocfilehash: a19559c225dd91eceed397df91dd584a577cd7d4
ms.sourcegitcommit: d43f66071f1f33b350d34fa1f46f3a35910c5d24
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74417702"
---
# <a name="authoring-a-dsc-resource-in-c"></a><span data-ttu-id="6b170-103">C\# での DSC リソースの作成</span><span class="sxs-lookup"><span data-stu-id="6b170-103">Authoring a DSC resource in C\#</span></span>

> <span data-ttu-id="6b170-104">適用先:Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="6b170-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="6b170-105">通常、Windows PowerShell Desired State Configuration (DSC) カスタム リソースは、PowerShell スクリプトで実装されます。</span><span class="sxs-lookup"><span data-stu-id="6b170-105">Typically, a Windows PowerShell Desired State Configuration (DSC) custom resource is implemented in a PowerShell script.</span></span> <span data-ttu-id="6b170-106">ただし、C# でコマンドレットを記述して、DSC カスタム リソースの機能を実装することもできます。</span><span class="sxs-lookup"><span data-stu-id="6b170-106">However, you can also implement the functionality of a DSC custom resource by writing cmdlets in C#.</span></span> <span data-ttu-id="6b170-107">C# でのコマンドレットの記述の概要については、「[Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)](/powershell/scripting/developer/windows-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b170-107">For an introduction on writing cmdlets in C#, see [Writing a Windows PowerShell Cmdlet](/powershell/scripting/developer/windows-powershell).</span></span>

<span data-ttu-id="6b170-108">C# でコマンドレットとしてリソースを実装すること以外に、MOF スキーマの作成、フォルダー構造の作成、およびカスタム DSC リソースのインポートと使用のプロセスは、「[MOF を使用したカスタム DSC リソースの記述](authoringResourceMOF.md)」で説明されていることと同じです。</span><span class="sxs-lookup"><span data-stu-id="6b170-108">Aside from implementing the resource in C# as cmdlets, the process of creating the MOF schema, creating the folder structure, importing and using your custom DSC resource are the same as described in [Writing a custom DSC resource with MOF](authoringResourceMOF.md).</span></span>

## <a name="writing-a-cmdlet-based-resource"></a><span data-ttu-id="6b170-109">コマンドレットベースのリソースの記述</span><span class="sxs-lookup"><span data-stu-id="6b170-109">Writing a cmdlet-based resource</span></span>
<span data-ttu-id="6b170-110">この例では、テキスト ファイルとその内容を管理する単純なリソースを実装します。</span><span class="sxs-lookup"><span data-stu-id="6b170-110">For this example, we will implement a simple resource that manages a text file and its contents.</span></span>

### <a name="writing-the-mof-schema"></a><span data-ttu-id="6b170-111">MOF スキーマの記述</span><span class="sxs-lookup"><span data-stu-id="6b170-111">Writing the MOF schema</span></span>

<span data-ttu-id="6b170-112">MOF リソースの定義を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6b170-112">The following is the MOF resource definition.</span></span>

```
[ClassVersion("1.0.0"), FriendlyName("xDemoFile")]
class MSFT_XDemoFile : OMI_BaseResource
{
                [Key, Description("path")] String Path;
                [Write, Description("Should the file be present"), ValueMap{"Present","Absent"}, Values{"Present","Absent"}] String Ensure;
                [Write, Description("Contentof file.")] String Content;
};
```

### <a name="setting-up-the-visual-studio-project"></a><span data-ttu-id="6b170-113">Visual Studio プロジェクトの設定</span><span class="sxs-lookup"><span data-stu-id="6b170-113">Setting up the Visual Studio project</span></span>
#### <a name="setting-up-a-cmdlet-project"></a><span data-ttu-id="6b170-114">コマンドレット プロジェクトの設定</span><span class="sxs-lookup"><span data-stu-id="6b170-114">Setting up a cmdlet project</span></span>

1. <span data-ttu-id="6b170-115">Visual Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="6b170-115">Open Visual Studio.</span></span>
1. <span data-ttu-id="6b170-116">C# プロジェクトを作成し、名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6b170-116">Create a C# project and provide the name.</span></span>
1. <span data-ttu-id="6b170-117">使用可能なプロジェクト テンプレートから **[クラス ライブラリ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6b170-117">Select **Class Library** from the available project templates.</span></span>
1. <span data-ttu-id="6b170-118">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b170-118">Click **Ok**.</span></span>
1. <span data-ttu-id="6b170-119">System.Automation.Management.dll へのアセンブリ参照をプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="6b170-119">Add an assembly reference to System.Automation.Management.dll to your project.</span></span>
1. <span data-ttu-id="6b170-120">リソース名と一致するようにアセンブリ名を変更します。</span><span class="sxs-lookup"><span data-stu-id="6b170-120">Change the assembly name to match the resource name.</span></span> <span data-ttu-id="6b170-121">この例では、アセンブリは **MSFT_XDemoFile** という名前にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b170-121">In this case, the assembly should be named **MSFT_XDemoFile**.</span></span>

### <a name="writing-the-cmdlet-code"></a><span data-ttu-id="6b170-122">コマンドレット コードの記述</span><span class="sxs-lookup"><span data-stu-id="6b170-122">Writing the cmdlet code</span></span>

<span data-ttu-id="6b170-123">次の C# コードでは、**Get-TargetResource**、**Set-TargetResource**、および **Test-TargetResource** コマンドレットを実装します。</span><span class="sxs-lookup"><span data-stu-id="6b170-123">The following C# code implements the **Get-TargetResource**, **Set-TargetResource**, and **Test-TargetResource** cmdlets.</span></span>

```C#


namespace cSharpDSCResourceExample
{
    using System;
    using System.Collections.Generic;
    using System.IO;
    using System.Management.Automation;  // Windows PowerShell assembly.

    #region Get-TargetResource

    [OutputType(typeof(System.Collections.Hashtable))]
    [Cmdlet(VerbsCommon.Get, "TargetResource")]
    public class GetTargetResource : PSCmdlet
    {
        [Parameter(Mandatory = true)]
        public string Path { get; set; }

        /// <summary>
        /// Implement the logic to return the current state of the resource as a hashtable with keys being the resource properties
        /// and the values are the corresponding current value on the machine.
        /// </summary>
        protected override void ProcessRecord()
        {
            var currentResourceState = new Dictionary<string, string>();
            if (File.Exists(Path))
            {
                currentResourceState.Add("Ensure", "Present");

                // read current content
                string CurrentContent = "";
                using (var reader = new StreamReader(Path))
                {
                    CurrentContent = reader.ReadToEnd();
                }
                currentResourceState.Add("Content", CurrentContent);
            }
            else
            {
                currentResourceState.Add("Ensure", "Absent");
                currentResourceState.Add("Content", "");
            }
            // write the hashtable in the PS console.
            WriteObject(currentResourceState);
        }
    }

    # endregion

    #region Set-TargetResource
    [OutputType(typeof(void))]
    [Cmdlet(VerbsCommon.Set, "TargetResource")]
    public class SetTargetResource : PSCmdlet
    {
        [Parameter(Mandatory = true)]
        public string Path { get; set; }

        [Parameter(Mandatory = false)]

        [ValidateSet("Present", "Absent", IgnoreCase = true)]
        public string Ensure {
            get
            {
                // set the default to present.
               return (this._ensure ?? "Present") ;
            }
            set
            {
                this._ensure = value;
            }
        }

        [Parameter(Mandatory = false)]
        public string Content {
            get { return (string.IsNullOrEmpty(this._content) ? "" : this._content); }
            set { this._content = value; }
        }

        private string _ensure;
        private string _content;

        /// <summary>
        /// Implement the logic to set the state of the machine to the desired state.
        /// </summary>
        protected override void ProcessRecord()
        {
            WriteVerbose(string.Format("Running set with parameters {0}{1}{2}", Path, Ensure, Content));
            if (File.Exists(Path))
            {
                if (Ensure.Equals("absent", StringComparison.InvariantCultureIgnoreCase))
                {
                    File.Delete(Path);
                }
                else
                {
                    // file already exist and ensure "present" is specified. start writing the content to a file
                    if (!string.IsNullOrEmpty(Content))
                    {
                        string existingContent = null;
                        using (var reader = new StreamReader(Path))
                        {
                            existingContent = reader.ReadToEnd();
                        }
                        // check if the content of the file mathes the content passed
                        if (!existingContent.Equals(Content, StringComparison.InvariantCultureIgnoreCase))
                        {
                            WriteVerbose("Existing content did not match with desired content updating the content of the file");
                            using (var writer = new StreamWriter(Path))
                            {
                                writer.Write(Content);
                                writer.Flush();
                            }
                        }
                    }
                }

            }
            else
            {
                if (Ensure.Equals("present", StringComparison.InvariantCultureIgnoreCase))
                {
                    // if nothing is passed for content just write "" otherwise write the content passed.
                    using (var writer = new StreamWriter(Path))
                    {
                        WriteVerbose(string.Format("Creating a file under path {0} with content {1}", Path, Content));
                        writer.Write(Content);
                    }
                }

            }

            /* if you need to reboot the VM. please add the following two line of code.
            PSVariable DscMachineStatus = new PSVariable("DSCMachineStatus", 1, ScopedItemOptions.AllScope);
            this.SessionState.PSVariable.Set(DscMachineStatus);
             */

        }

    }

    # endregion

    #region Test-TargetResource

    [Cmdlet("Test", "TargetResource")]
    [OutputType(typeof(Boolean))]
    public class TestTargetResource : PSCmdlet
    {
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
            get { return (string.IsNullOrEmpty(this._content) ? "" : this._content); }
            set { this._content = value; }
        }

        private string _ensure;
        private string _content;

        /// <summary>
        /// Return a boolean value which indicates wheather the current machine is in desired state or not.
        /// </summary>
        protected override void ProcessRecord()
        {
            if (File.Exists(Path))
            {
                if( Ensure.Equals("absent", StringComparison.InvariantCultureIgnoreCase))
                {
                    WriteObject(false);
                }
                else
                {
                    // check if the content matches

                    string existingContent = null;
                    using (var stream = new StreamReader(Path))
                    {
                        existingContent = stream.ReadToEnd();
                    }

                    WriteObject(Content.Equals(existingContent, StringComparison.InvariantCultureIgnoreCase));
                }
            }
            else
            {
                WriteObject(Ensure.Equals("Absent", StringComparison.InvariantCultureIgnoreCase));
            }
        }
    }

    # endregion

}
```

### <a name="deploying-the-resource"></a><span data-ttu-id="6b170-124">リソースの展開</span><span class="sxs-lookup"><span data-stu-id="6b170-124">Deploying the resource</span></span>

<span data-ttu-id="6b170-125">コンパイル済み dll ファイルは、スクリプトベースのリソースと同様のファイル構造で保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b170-125">The compiled dll file should be saved in a file structure similar to a script-based resource.</span></span> <span data-ttu-id="6b170-126">このリソースのフォルダー構造を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6b170-126">The following is the folder structure for this resource.</span></span>

```
$env: psmodulepath (folder)
    |- MyDscResources (folder)
        |- MyDscResources.psd1 (file, required)
        |- DSCResources (folder)
            |- MSFT_XDemoFile (folder)
                |- MSFT_XDemoFile.psd1 (file, optional)
                |- MSFT_XDemoFile.dll (file, required)
                |- MSFT_XDemoFile.schema.mof (file, required)
```

### <a name="see-also"></a><span data-ttu-id="6b170-127">参照</span><span class="sxs-lookup"><span data-stu-id="6b170-127">See Also</span></span>
#### <a name="concepts"></a><span data-ttu-id="6b170-128">概念</span><span class="sxs-lookup"><span data-stu-id="6b170-128">Concepts</span></span>
[<span data-ttu-id="6b170-129">MOF を使用したカスタム DSC リソースの記述</span><span class="sxs-lookup"><span data-stu-id="6b170-129">Writing a custom DSC resource with MOF</span></span>](authoringResourceMOF.md)
#### <a name="other-resources"></a><span data-ttu-id="6b170-130">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="6b170-130">Other Resources</span></span>
[<span data-ttu-id="6b170-131">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="6b170-131">Writing a Windows PowerShell Cmdlet</span></span>](/powershell/scripting/developer/windows-powershell)
