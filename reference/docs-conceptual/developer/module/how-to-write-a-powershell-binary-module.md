---
title: PowerShell バイナリモジュールを記述する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb4e72e6-24c4-42b6-b7b9-a62585c17f26
caps.latest.revision: 15
ms.openlocfilehash: ed614de125f78cbcf8411cc334baf3c95933dd47
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367121"
---
# <a name="how-to-write-a-powershell-binary-module"></a><span data-ttu-id="b4118-102">PowerShell バイナリ モジュールを記述する方法</span><span class="sxs-lookup"><span data-stu-id="b4118-102">How to Write a PowerShell Binary Module</span></span>

<span data-ttu-id="b4118-103">バイナリモジュールには、コマンドレットクラスを含む任意のアセンブリ (.dll) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b4118-103">A binary module can be any assembly (.dll) that contains cmdlet classes.</span></span> <span data-ttu-id="b4118-104">既定では、バイナリモジュールをインポートするときに、アセンブリ内のすべてのコマンドレットがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="b4118-104">By default, all the cmdlets in the assembly are imported when the binary module is imported.</span></span> <span data-ttu-id="b4118-105">ただし、ルートモジュールがアセンブリであるモジュールマニフェストを作成することによって、インポートされるコマンドレットを制限できます。</span><span class="sxs-lookup"><span data-stu-id="b4118-105">However, you can restrict the cmdlets that are imported by creating a module manifest whose root module is the assembly.</span></span> <span data-ttu-id="b4118-106">(たとえば、マニフェストのコマンドレット Stoexport キーを使用すると、必要なコマンドレットだけをエクスポートできます)。さらに、バイナリモジュールには、追加のファイル、ディレクトリ構造、および1つのコマンドレットでは使用できない有用な管理情報を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="b4118-106">(For example, the CmdletsToExport key of the manifest can be used to export only those cmdlets that are needed.) In addition, a binary module can contain additional files, a directory structure, and other pieces of useful management information that a single cmdlet cannot.</span></span>

<span data-ttu-id="b4118-107">次の手順では、PowerShell バイナリモジュールを作成してインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b4118-107">The following procedure describes how to create and install a PowerShell binary module.</span></span>

#### <a name="how-to-create-and-install-a-powershell-binary-module"></a><span data-ttu-id="b4118-108">PowerShell バイナリモジュールを作成してインストールする方法</span><span class="sxs-lookup"><span data-stu-id="b4118-108">How to create and install a PowerShell binary module</span></span>

1. <span data-ttu-id="b4118-109">バイナリ PowerShell ソリューション (でC#記述されたコマンドレットなど) を作成し、必要な機能を使用して、正常に動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="b4118-109">Create a binary PowerShell solution (such as a cmdlet written in C#), with the capabilities you need, and ensure that it runs properly.</span></span>

   <span data-ttu-id="b4118-110">コードの観点から見ると、バイナリモジュールの中核となるのは、単なるコマンドレットアセンブリです。</span><span class="sxs-lookup"><span data-stu-id="b4118-110">From a code perspective, the core of a binary module is simply a cmdlet assembly.</span></span> <span data-ttu-id="b4118-111">実際、PowerShell は、1つのコマンドレットアセンブリを読み込みとアンロードという点でモジュールとして処理し、開発者の作業を追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b4118-111">In fact, PowerShell will treat a single cmdlet assembly as a module, in terms of loading and unloading, with no additional effort on the part of the developer.</span></span> <span data-ttu-id="b4118-112">コマンドレットの記述の詳細については、「 [Windows PowerShell コマンドレットの記述](../cmdlet/writing-a-windows-powershell-cmdlet.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4118-112">For more information about writing a cmdlet, see [Writing a Windows PowerShell Cmdlet](../cmdlet/writing-a-windows-powershell-cmdlet.md).</span></span>

2. <span data-ttu-id="b4118-113">必要に応じて、ソリューションの残りの部分 (追加のコマンドレット、XML ファイルなど) を作成し、モジュールマニフェストで記述します。</span><span class="sxs-lookup"><span data-stu-id="b4118-113">If necessary, create the rest of your solution: (additional cmdlets, XML files, and so on) and describe them with a module manifest.</span></span>

   <span data-ttu-id="b4118-114">モジュールマニフェストでは、ソリューション内のコマンドレットアセンブリを記述するだけでなく、モジュールをエクスポートおよびインポートする方法、どのコマンドレットを公開するか、およびモジュールに追加されるその他のファイルについても記述できます。</span><span class="sxs-lookup"><span data-stu-id="b4118-114">In addition to describing the cmdlet assemblies in your solution, a module manifest can describe how you want your module exported and imported, what cmdlets will be exposed, and what additional files will go into the module.</span></span>
   <span data-ttu-id="b4118-115">前に説明したように、PowerShell では、追加の作業を必要とせずに、モジュールと同様にバイナリコマンドレットを扱うことができます。</span><span class="sxs-lookup"><span data-stu-id="b4118-115">As stated previously however, PowerShell can treat a binary cmdlet like a module with no additional effort.</span></span>
   <span data-ttu-id="b4118-116">そのため、モジュールマニフェストは、主に、複数のファイルを1つのパッケージに結合したり、特定のアセンブリに対してパブリケーションを明示的に制御したりする場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b4118-116">As such, a module manifest is useful mainly for combining multiple files into a single package, or for explicitly controlling publication for a given assembly.</span></span>
   <span data-ttu-id="b4118-117">詳細については、「 [PowerShell モジュールマニフェストを記述する方法](how-to-write-a-powershell-module-manifest.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4118-117">For more information, see [How to Write a PowerShell Module Manifest](how-to-write-a-powershell-module-manifest.md).</span></span>

   <span data-ttu-id="b4118-118">次のコードは、モジュールとC#して使用できる同じファイル内に3つのコマンドレットを含む、非常に単純なコードブロックです。</span><span class="sxs-lookup"><span data-stu-id="b4118-118">The following code is an extremely simple C# code block that contains three cmdlets in the same file that can be used as a module.</span></span>

   ```csharp
   using System.Management.Automation;           // Windows PowerShell namespace.

   namespace ModuleCmdlets
   {
     [Cmdlet(VerbsDiagnostic.Test,"BinaryModuleCmdlet1")]
     public class TestBinaryModuleCmdlet1Command : Cmdlet
     {
       protected override void BeginProcessing()
       {
         WriteObject("BinaryModuleCmdlet1 exported by the ModuleCmdlets module.");
       }
     }

     [Cmdlet(VerbsDiagnostic.Test, "BinaryModuleCmdlet2")]
     public class TestBinaryModuleCmdlet2Command : Cmdlet
     {
         protected override void BeginProcessing()
         {
             WriteObject("BinaryModuleCmdlet2 exported by the ModuleCmdlets module.");
         }
     }

     [Cmdlet(VerbsDiagnostic.Test, "BinaryModuleCmdlet3")]
     public class TestBinaryModuleCmdlet3Command : Cmdlet
     {
         protected override void BeginProcessing()
         {
             WriteObject("BinaryModuleCmdlet3 exported by the ModuleCmdlets module.");
         }
     }

   }
   ```

3. <span data-ttu-id="b4118-119">ソリューションをパッケージ化し、PowerShell モジュールパス内の任意の場所にパッケージを保存します。</span><span class="sxs-lookup"><span data-stu-id="b4118-119">Package your solution, and save the package to somewhere in the PowerShell module path.</span></span>

   <span data-ttu-id="b4118-120">@No__t 0 のグローバル環境変数は、PowerShell がモジュールを検索するために使用する既定のパスを記述します。</span><span class="sxs-lookup"><span data-stu-id="b4118-120">The `PSModulePath` global environment variable describes the default paths that PowerShell will use to locate your module.</span></span> <span data-ttu-id="b4118-121">たとえば、システムにモジュールを保存するための一般的なパスは、0 @no__t になります。</span><span class="sxs-lookup"><span data-stu-id="b4118-121">For example, a common path to save a module on a system would be `%SystemRoot%\users\<user>\Documents\WindowsPowerShell\Modules\<moduleName>`.</span></span> <span data-ttu-id="b4118-122">既定のパスを使用しない場合は、インストール中にモジュールの場所を明示的に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4118-122">If you do not use the default paths, you will need to explicitly state the location of your module during installation.</span></span> <span data-ttu-id="b4118-123">ソリューションの複数のアセンブリとファイルを格納するフォルダーが必要になる場合があるので、モジュールを保存するためのフォルダーを必ず作成してください。</span><span class="sxs-lookup"><span data-stu-id="b4118-123">Be sure to create a folder to save your module in, as you may need the folder to store multiple assemblies and files for your solution.</span></span>

   <span data-ttu-id="b4118-124">技術的には、モジュールを @no__t 上の任意の場所にインストールする必要がないことに注意してください-0-PowerShell がモジュールを検索する既定の場所です。</span><span class="sxs-lookup"><span data-stu-id="b4118-124">Note that technically you do not need to install your module anywhere on the `PSModulePath` - those are simply the default locations that PowerShell will look for your module.</span></span> <span data-ttu-id="b4118-125">ただし、モジュールを他の場所に格納することが適切な理由がない限り、ベストプラクティスと考えてください。</span><span class="sxs-lookup"><span data-stu-id="b4118-125">However, it is considered best practice to do so, unless you have a good reason for storing your module somewhere else.</span></span> <span data-ttu-id="b4118-126">詳細については、「 [Powershell モジュールのインストール](./installing-a-powershell-module.md)」および「 [Powershell モジュールのインストールパスの変更](./modifying-the-psmodulepath-installation-path.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4118-126">For more information, see [Installing a PowerShell Module](./installing-a-powershell-module.md) and [Modifying the PowerShell Module Installation Path](./modifying-the-psmodulepath-installation-path.md).</span></span>

4. <span data-ttu-id="b4118-127">モジュールを PowerShell にインポートし[、モジュールを呼び出します。](/powershell/module/Microsoft.PowerShell.Core/Import-Module)</span><span class="sxs-lookup"><span data-stu-id="b4118-127">Import your module into PowerShell with a call to [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module).</span></span>

   <span data-ttu-id="b4118-128">モジュールを[インポート](/powershell/module/Microsoft.PowerShell.Core/Import-Module)するためにを呼び出すと、モジュールがアクティブメモリに読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="b4118-128">Calling to [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) will load your module into active memory.</span></span> <span data-ttu-id="b4118-129">PowerShell 3.0 以降を使用している場合は、コードでモジュールの名前を呼び出すだけでもインポートされます。詳細については、「 [PowerShell モジュールのインポート](./importing-a-powershell-module.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4118-129">If you are using PowerShell 3.0 and later, simply calling the name of your module in code will also import it; for more information, see [Importing a PowerShell Module](./importing-a-powershell-module.md).</span></span>

## <a name="importing-snap-in-assemblies-as-modules"></a><span data-ttu-id="b4118-130">モジュールとしてのスナップインアセンブリのインポート</span><span class="sxs-lookup"><span data-stu-id="b4118-130">Importing Snap-in Assemblies as Modules</span></span>

<span data-ttu-id="b4118-131">スナップインアセンブリに存在するコマンドレットとプロバイダーは、バイナリモジュールとして読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="b4118-131">Cmdlets and providers that exist in snap-in assemblies can be loaded as binary modules.</span></span> <span data-ttu-id="b4118-132">スナップインアセンブリがバイナリモジュールとして読み込まれると、スナップインのコマンドレットとプロバイダーはユーザーが使用できますが、アセンブリのスナップインクラスは無視され、スナップインは登録されません。</span><span class="sxs-lookup"><span data-stu-id="b4118-132">When the snap-in assemblies are loaded as binary modules, the cmdlets and providers in the snap-in are available to the user, but the snap-in class in the assembly is ignored, and the snap-in is not registered.</span></span> <span data-ttu-id="b4118-133">その結果、コマンドレットとプロバイダーをセッションで使用できる場合でも、Windows PowerShell によって提供されるスナップインコマンドレットでスナップインを検出することはできません。</span><span class="sxs-lookup"><span data-stu-id="b4118-133">As a result, the snap-in cmdlets provided by Windows PowerShell cannot detect the snap-in even though the cmdlets and providers are available to the session.</span></span>

<span data-ttu-id="b4118-134">また、スナップインによって参照されるすべての書式設定ファイルまたは型ファイルは、バイナリモジュールの一部としてインポートできません。</span><span class="sxs-lookup"><span data-stu-id="b4118-134">In addition, any formatting or types files that are referenced by the snap-in cannot be imported as part of a binary module.</span></span>
<span data-ttu-id="b4118-135">書式設定ファイルと型ファイルをインポートするには、モジュールマニフェストを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4118-135">To import the formatting and types files you must create a module manifest.</span></span>
<span data-ttu-id="b4118-136">「 [PowerShell モジュールマニフェストを記述する方法](how-to-write-a-powershell-module-manifest.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4118-136">See, [How to Write a PowerShell Module Manifest](how-to-write-a-powershell-module-manifest.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b4118-137">参照</span><span class="sxs-lookup"><span data-stu-id="b4118-137">See Also</span></span>

[<span data-ttu-id="b4118-138">Windows PowerShell モジュールの作成</span><span class="sxs-lookup"><span data-stu-id="b4118-138">Writing a Windows PowerShell Module</span></span>](./writing-a-windows-powershell-module.md)
