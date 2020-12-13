---
ms.date: 09/13/2016
ms.topic: reference
title: PowerShell バイナリ モジュールを記述する方法
description: PowerShell バイナリ モジュールを記述する方法
ms.openlocfilehash: 1d5cea474ac418f78cc782360b7c23b7614d6669
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92663076"
---
# <a name="how-to-write-a-powershell-binary-module"></a><span data-ttu-id="3480f-103">PowerShell バイナリ モジュールを記述する方法</span><span class="sxs-lookup"><span data-stu-id="3480f-103">How to Write a PowerShell Binary Module</span></span>

<span data-ttu-id="3480f-104">バイナリモジュールには、コマンドレットクラスを含む任意のアセンブリ (.dll) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="3480f-104">A binary module can be any assembly (.dll) that contains cmdlet classes.</span></span> <span data-ttu-id="3480f-105">既定では、バイナリモジュールをインポートするときに、アセンブリ内のすべてのコマンドレットがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="3480f-105">By default, all the cmdlets in the assembly are imported when the binary module is imported.</span></span> <span data-ttu-id="3480f-106">ただし、ルートモジュールがアセンブリであるモジュールマニフェストを作成することによって、インポートされるコマンドレットを制限できます。</span><span class="sxs-lookup"><span data-stu-id="3480f-106">However, you can restrict the cmdlets that are imported by creating a module manifest whose root module is the assembly.</span></span> <span data-ttu-id="3480f-107">(たとえば、マニフェストのコマンドレット Stoexport キーを使用すると、必要なコマンドレットだけをエクスポートできます)。さらに、バイナリモジュールには、追加のファイル、ディレクトリ構造、および1つのコマンドレットでは使用できない有用な管理情報を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="3480f-107">(For example, the CmdletsToExport key of the manifest can be used to export only those cmdlets that are needed.) In addition, a binary module can contain additional files, a directory structure, and other pieces of useful management information that a single cmdlet cannot.</span></span>

<span data-ttu-id="3480f-108">次の手順では、PowerShell バイナリモジュールを作成してインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3480f-108">The following procedure describes how to create and install a PowerShell binary module.</span></span>

#### <a name="how-to-create-and-install-a-powershell-binary-module"></a><span data-ttu-id="3480f-109">PowerShell バイナリモジュールを作成してインストールする方法</span><span class="sxs-lookup"><span data-stu-id="3480f-109">How to create and install a PowerShell binary module</span></span>

1. <span data-ttu-id="3480f-110">必要な機能を備えたバイナリ PowerShell ソリューション (C# で記述されたコマンドレットなど) を作成し、正常に動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="3480f-110">Create a binary PowerShell solution (such as a cmdlet written in C#), with the capabilities you need, and ensure that it runs properly.</span></span>

   <span data-ttu-id="3480f-111">コードの観点から見ると、バイナリモジュールの中核となるのは、単なるコマンドレットアセンブリです。</span><span class="sxs-lookup"><span data-stu-id="3480f-111">From a code perspective, the core of a binary module is simply a cmdlet assembly.</span></span> <span data-ttu-id="3480f-112">実際、PowerShell は、1つのコマンドレットアセンブリを読み込みとアンロードという点でモジュールとして処理し、開発者の作業を追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3480f-112">In fact, PowerShell will treat a single cmdlet assembly as a module, in terms of loading and unloading, with no additional effort on the part of the developer.</span></span> <span data-ttu-id="3480f-113">コマンドレットの記述の詳細については、「 [Windows PowerShell コマンドレットの記述](../cmdlet/writing-a-windows-powershell-cmdlet.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3480f-113">For more information about writing a cmdlet, see [Writing a Windows PowerShell Cmdlet](../cmdlet/writing-a-windows-powershell-cmdlet.md).</span></span>

2. <span data-ttu-id="3480f-114">必要に応じて、ソリューションの残りの部分 (追加のコマンドレット、XML ファイルなど) を作成し、モジュールマニフェストで記述します。</span><span class="sxs-lookup"><span data-stu-id="3480f-114">If necessary, create the rest of your solution: (additional cmdlets, XML files, and so on) and describe them with a module manifest.</span></span>

   <span data-ttu-id="3480f-115">モジュールマニフェストでは、ソリューション内のコマンドレットアセンブリを記述するだけでなく、モジュールをエクスポートおよびインポートする方法、どのコマンドレットを公開するか、およびモジュールに追加されるその他のファイルについても記述できます。</span><span class="sxs-lookup"><span data-stu-id="3480f-115">In addition to describing the cmdlet assemblies in your solution, a module manifest can describe how you want your module exported and imported, what cmdlets will be exposed, and what additional files will go into the module.</span></span>
   <span data-ttu-id="3480f-116">前に説明したように、PowerShell では、追加の作業を必要とせずに、モジュールと同様にバイナリコマンドレットを扱うことができます。</span><span class="sxs-lookup"><span data-stu-id="3480f-116">As stated previously however, PowerShell can treat a binary cmdlet like a module with no additional effort.</span></span>
   <span data-ttu-id="3480f-117">そのため、モジュールマニフェストは、主に、複数のファイルを1つのパッケージに結合したり、特定のアセンブリに対してパブリケーションを明示的に制御したりする場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3480f-117">As such, a module manifest is useful mainly for combining multiple files into a single package, or for explicitly controlling publication for a given assembly.</span></span>
   <span data-ttu-id="3480f-118">詳細については、「 [PowerShell モジュールマニフェストを記述する方法](how-to-write-a-powershell-module-manifest.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3480f-118">For more information, see [How to Write a PowerShell Module Manifest](how-to-write-a-powershell-module-manifest.md).</span></span>

   <span data-ttu-id="3480f-119">次のコードは、モジュールとして使用できる同じファイル内に3つのコマンドレットを含む、非常に単純な C# コードブロックです。</span><span class="sxs-lookup"><span data-stu-id="3480f-119">The following code is an extremely simple C# code block that contains three cmdlets in the same file that can be used as a module.</span></span>

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

3. <span data-ttu-id="3480f-120">ソリューションをパッケージ化し、PowerShell モジュールパス内の任意の場所にパッケージを保存します。</span><span class="sxs-lookup"><span data-stu-id="3480f-120">Package your solution, and save the package to somewhere in the PowerShell module path.</span></span>

   <span data-ttu-id="3480f-121">`PSModulePath`グローバル環境変数は、PowerShell がモジュールを検索するために使用する既定のパスを記述します。</span><span class="sxs-lookup"><span data-stu-id="3480f-121">The `PSModulePath` global environment variable describes the default paths that PowerShell will use to locate your module.</span></span> <span data-ttu-id="3480f-122">たとえば、システムにモジュールを保存するための一般的なパスは、のようになり `%SystemRoot%\users\<user>\Documents\WindowsPowerShell\Modules\<moduleName>` ます。</span><span class="sxs-lookup"><span data-stu-id="3480f-122">For example, a common path to save a module on a system would be `%SystemRoot%\users\<user>\Documents\WindowsPowerShell\Modules\<moduleName>`.</span></span> <span data-ttu-id="3480f-123">既定のパスを使用しない場合は、インストール中にモジュールの場所を明示的に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3480f-123">If you do not use the default paths, you will need to explicitly state the location of your module during installation.</span></span> <span data-ttu-id="3480f-124">ソリューションの複数のアセンブリとファイルを格納するフォルダーが必要になる場合があるので、モジュールを保存するためのフォルダーを必ず作成してください。</span><span class="sxs-lookup"><span data-stu-id="3480f-124">Be sure to create a folder to save your module in, as you may need the folder to store multiple assemblies and files for your solution.</span></span>

   <span data-ttu-id="3480f-125">技術的には、でモジュールをインストールする必要がないことに注意してください `PSModulePath` 。これらは、PowerShell がモジュールを検索する既定の場所です。</span><span class="sxs-lookup"><span data-stu-id="3480f-125">Note that technically you do not need to install your module anywhere on the `PSModulePath` - those are simply the default locations that PowerShell will look for your module.</span></span> <span data-ttu-id="3480f-126">ただし、モジュールを他の場所に格納することが適切な理由がない限り、ベストプラクティスと考えてください。</span><span class="sxs-lookup"><span data-stu-id="3480f-126">However, it is considered best practice to do so, unless you have a good reason for storing your module somewhere else.</span></span> <span data-ttu-id="3480f-127">詳細については、「 [Powershell モジュールのインストール](./installing-a-powershell-module.md) 」および「 [Powershell モジュールのインストールパスの変更](./modifying-the-psmodulepath-installation-path.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3480f-127">For more information, see [Installing a PowerShell Module](./installing-a-powershell-module.md) and [Modifying the PowerShell Module Installation Path](./modifying-the-psmodulepath-installation-path.md).</span></span>

4. <span data-ttu-id="3480f-128">モジュールを PowerShell にインポートし[、モジュールを呼び出します。](/powershell/module/Microsoft.PowerShell.Core/Import-Module)</span><span class="sxs-lookup"><span data-stu-id="3480f-128">Import your module into PowerShell with a call to [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module).</span></span>

   <span data-ttu-id="3480f-129">モジュールを [インポート](/powershell/module/Microsoft.PowerShell.Core/Import-Module) するためにを呼び出すと、モジュールがアクティブメモリに読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="3480f-129">Calling to [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) will load your module into active memory.</span></span> <span data-ttu-id="3480f-130">PowerShell 3.0 以降を使用している場合は、コードでモジュールの名前を呼び出すだけでもインポートされます。詳細については、「 [PowerShell モジュールのインポート](./importing-a-powershell-module.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3480f-130">If you are using PowerShell 3.0 and later, simply calling the name of your module in code will also import it; for more information, see [Importing a PowerShell Module](./importing-a-powershell-module.md).</span></span>

## <a name="importing-snap-in-assemblies-as-modules"></a><span data-ttu-id="3480f-131">モジュールとしてのスナップインアセンブリのインポート</span><span class="sxs-lookup"><span data-stu-id="3480f-131">Importing Snap-in Assemblies as Modules</span></span>

<span data-ttu-id="3480f-132">スナップインアセンブリに存在するコマンドレットとプロバイダーは、バイナリモジュールとして読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="3480f-132">Cmdlets and providers that exist in snap-in assemblies can be loaded as binary modules.</span></span> <span data-ttu-id="3480f-133">スナップインアセンブリがバイナリモジュールとして読み込まれると、スナップインのコマンドレットとプロバイダーはユーザーが使用できますが、アセンブリのスナップインクラスは無視され、スナップインは登録されません。</span><span class="sxs-lookup"><span data-stu-id="3480f-133">When the snap-in assemblies are loaded as binary modules, the cmdlets and providers in the snap-in are available to the user, but the snap-in class in the assembly is ignored, and the snap-in is not registered.</span></span> <span data-ttu-id="3480f-134">その結果、コマンドレットとプロバイダーをセッションで使用できる場合でも、Windows PowerShell によって提供されるスナップインコマンドレットでスナップインを検出することはできません。</span><span class="sxs-lookup"><span data-stu-id="3480f-134">As a result, the snap-in cmdlets provided by Windows PowerShell cannot detect the snap-in even though the cmdlets and providers are available to the session.</span></span>

<span data-ttu-id="3480f-135">また、スナップインによって参照されるすべての書式設定ファイルまたは型ファイルは、バイナリモジュールの一部としてインポートできません。</span><span class="sxs-lookup"><span data-stu-id="3480f-135">In addition, any formatting or types files that are referenced by the snap-in cannot be imported as part of a binary module.</span></span>
<span data-ttu-id="3480f-136">書式設定ファイルと型ファイルをインポートするには、モジュールマニフェストを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3480f-136">To import the formatting and types files you must create a module manifest.</span></span>
<span data-ttu-id="3480f-137">「 [PowerShell モジュールマニフェストを記述する方法](how-to-write-a-powershell-module-manifest.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3480f-137">See, [How to Write a PowerShell Module Manifest](how-to-write-a-powershell-module-manifest.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3480f-138">参照</span><span class="sxs-lookup"><span data-stu-id="3480f-138">See Also</span></span>

[<span data-ttu-id="3480f-139">Windows PowerShell モジュールを記述する</span><span class="sxs-lookup"><span data-stu-id="3480f-139">Writing a Windows PowerShell Module</span></span>](./writing-a-windows-powershell-module.md)
