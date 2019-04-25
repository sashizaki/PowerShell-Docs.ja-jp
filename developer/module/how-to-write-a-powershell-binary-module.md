---
title: PowerShell バイナリ モジュールを記述する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb4e72e6-24c4-42b6-b7b9-a62585c17f26
caps.latest.revision: 15
ms.openlocfilehash: 9ddb3bc172c66314603d2be4df5192a76c92e05d
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62082228"
---
# <a name="how-to-write-a-powershell-binary-module"></a><span data-ttu-id="41b66-102">PowerShell バイナリ モジュールを記述する方法</span><span class="sxs-lookup"><span data-stu-id="41b66-102">How to Write a PowerShell Binary Module</span></span>

<span data-ttu-id="41b66-103">バイナリ モジュールには、コマンドレット クラスを含む任意のアセンブリ (.dll) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="41b66-103">A binary module can be any assembly (.dll) that contains cmdlet classes.</span></span> <span data-ttu-id="41b66-104">既定では、アセンブリ内のすべてのコマンドレットは、バイナリ モジュールのインポート時にインポートされます。</span><span class="sxs-lookup"><span data-stu-id="41b66-104">By default, all the cmdlets in the assembly are imported when the binary module is imported.</span></span> <span data-ttu-id="41b66-105">ただし、ルート モジュールがあるアセンブリのモジュール マニフェストを作成してインポートされたコマンドレットを制限することができます。</span><span class="sxs-lookup"><span data-stu-id="41b66-105">However, you can restrict the cmdlets that are imported by creating a module manifest whose root module is the assembly.</span></span> <span data-ttu-id="41b66-106">(たとえば、マニフェストの CmdletsToExport キーできるために必要なコマンドレットのみをエクスポートする。)さらに、バイナリ モジュールでは、追加のファイル、ディレクトリ構造、および 1 つのコマンドレットができないことに有用な管理の他の情報を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="41b66-106">(For example, the CmdletsToExport key of the manifest can be used to export only those cmdlets that are needed.) In addition, a binary module can contain additional files, a directory structure, and other pieces of useful management information that a single cmdlet cannot.</span></span>

<span data-ttu-id="41b66-107">次の手順では、作成し、PowerShell バイナリ モジュールをインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="41b66-107">The following procedure describes how to create and install a PowerShell binary module.</span></span>

#### <a name="how-to-create-and-install-a-powershell-binary-module"></a><span data-ttu-id="41b66-108">作成し、PowerShell バイナリ モジュールをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="41b66-108">How to create and install a PowerShell binary module</span></span>

1. <span data-ttu-id="41b66-109">バイナリ PowerShell ソリューションの作成 (で記述されたコマンドレットなどC#) の機能を持つ必要があると適切に動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="41b66-109">Create a binary PowerShell solution (such as a cmdlet written in C#), with the capabilities you need, and ensure that it runs properly.</span></span>

   <span data-ttu-id="41b66-110">コードの観点からは、バイナリ モジュールの中核は、コマンドレット アセンブリだけです。</span><span class="sxs-lookup"><span data-stu-id="41b66-110">From a code perspective, the core of a binary module is simply a cmdlet assembly.</span></span> <span data-ttu-id="41b66-111">実際には、PowerShell は、1 つのコマンドレットのアセンブリを読み込みとアンロード、何も追加の作業、開発者の観点から、モジュールとして扱います。</span><span class="sxs-lookup"><span data-stu-id="41b66-111">In fact, PowerShell will treat a single cmdlet assembly as a module, in terms of loading and unloading, with no additional effort on the part of the developer.</span></span> <span data-ttu-id="41b66-112">コマンドレットの記述方法の詳細については、次を参照してください。 [Windows PowerShell コマンドレットの記述](../cmdlet/writing-a-windows-powershell-cmdlet.md)します。</span><span class="sxs-lookup"><span data-stu-id="41b66-112">For more information about writing a cmdlet, see [Writing a Windows PowerShell Cmdlet](../cmdlet/writing-a-windows-powershell-cmdlet.md).</span></span>

2. <span data-ttu-id="41b66-113">必要に応じて、ソリューションの残りの部分を作成: (その他のコマンドレットや、XML ファイル) と、モジュール マニフェストを説明します。</span><span class="sxs-lookup"><span data-stu-id="41b66-113">If necessary, create the rest of your solution: (additional cmdlets, XML files, and so on) and describe them with a module manifest.</span></span>

   <span data-ttu-id="41b66-114">ソリューション内のコマンドレットのアセンブリを記述するだけでなく、モジュール マニフェストは、モジュールをエクスポートおよびインポートする方法、どのようなコマンドレットを公開するか、および追加のファイルがモジュールに変わりますを記述できます。</span><span class="sxs-lookup"><span data-stu-id="41b66-114">In addition to describing the cmdlet assemblies in your solution, a module manifest can describe how you want your module exported and imported, what cmdlets will be exposed, and what additional files will go into the module.</span></span> <span data-ttu-id="41b66-115">前に述べたただし、PowerShell は、何も追加の作業のモジュールと同様にバイナリ コマンドレットを扱うことができます。</span><span class="sxs-lookup"><span data-stu-id="41b66-115">As stated previously however, PowerShell can treat a binary cmdlet like a module with no additional effort.</span></span> <span data-ttu-id="41b66-116">そのため、モジュール マニフェストは、主に 1 つのパッケージに複数のファイルを結合することや、特定のアセンブリのパブリケーションを明示的に制御するために便利です。</span><span class="sxs-lookup"><span data-stu-id="41b66-116">As such, a module manifest is useful mainly for combining multiple files into a single package, or for explicitly controlling publication for a given assembly.</span></span> <span data-ttu-id="41b66-117">詳細については、次を参照してください。 [PowerShell モジュール マニフェストの記述方法](http://msdn.microsoft.com/en-us/abe4c24b-e64e-4a61-81d5-18c4fceba0b6)します。</span><span class="sxs-lookup"><span data-stu-id="41b66-117">For more information, see [How to Write a PowerShell Module Manifest](http://msdn.microsoft.com/en-us/abe4c24b-e64e-4a61-81d5-18c4fceba0b6).</span></span>

   <span data-ttu-id="41b66-118">次のコードは、非常に単純C#をモジュールとして使用できるのと同じファイル内の 3 つのコマンドレットを含むコード ブロックです。</span><span class="sxs-lookup"><span data-stu-id="41b66-118">The following code is an extremely simple C# code block that contains three cmdlets in the same file that can be used as a module.</span></span>

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

3. <span data-ttu-id="41b66-119">ソリューションをパッケージ化し、別の場所にパッケージを保存で PowerShell モジュールのパス。</span><span class="sxs-lookup"><span data-stu-id="41b66-119">Package your solution, and save the package to somewhere in the PowerShell module path.</span></span>

   <span data-ttu-id="41b66-120">`PSModulePath`グローバル環境変数には、PowerShell がモジュールの検索に使用する既定のパスがについて説明します。</span><span class="sxs-lookup"><span data-stu-id="41b66-120">The `PSModulePath` global environment variable describes the default paths that PowerShell will use to locate your module.</span></span> <span data-ttu-id="41b66-121">たとえば、システム上のモジュールを保存する共通のパスになります`%SystemRoot%\users\<user>\Documents\WindowsPowerShell\Modules\<moduleName>`します。</span><span class="sxs-lookup"><span data-stu-id="41b66-121">For example, a common path to save a module on a system would be `%SystemRoot%\users\<user>\Documents\WindowsPowerShell\Modules\<moduleName>`.</span></span> <span data-ttu-id="41b66-122">既定のパスを使用しない場合は、インストール中に、モジュールの場所を明示的に記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41b66-122">If you do not use the default paths, you will need to explicitly state the location of your module during installation.</span></span> <span data-ttu-id="41b66-123">必要に応じて複数のアセンブリと、ソリューション ファイルを格納するフォルダーで、モジュールを保存するフォルダーを作成することを確認します。</span><span class="sxs-lookup"><span data-stu-id="41b66-123">Be sure to create a folder to save your module in, as you may need the folder to store multiple assemblies and files for your solution.</span></span>

   <span data-ttu-id="41b66-124">技術的には必要はありません、モジュールを任意の場所にインストールするに注意してください、 `PSModulePath` -これらは、PowerShell は、モジュールを検索する既定の場所だけです。</span><span class="sxs-lookup"><span data-stu-id="41b66-124">Note that technically you do not need to install your module anywhere on the `PSModulePath` - those are simply the default locations that PowerShell will look for your module.</span></span> <span data-ttu-id="41b66-125">ただし、別の場所にモジュールを格納するための十分な理由がない限り、そのためのベスト プラクティスと見なされます。</span><span class="sxs-lookup"><span data-stu-id="41b66-125">However, it is considered best practice to do so, unless you have a good reason for storing your module somewhere else.</span></span> <span data-ttu-id="41b66-126">詳細については、次を参照してください。 [PowerShell モジュールのインストール](./installing-a-powershell-module.md)と[PowerShell モジュールのインストール パスを変更する](./modifying-the-psmodulepath-installation-path.md)します。</span><span class="sxs-lookup"><span data-stu-id="41b66-126">For more information, see [Installing a PowerShell Module](./installing-a-powershell-module.md) and [Modifying the PowerShell Module Installation Path](./modifying-the-psmodulepath-installation-path.md).</span></span>

4. <span data-ttu-id="41b66-127">呼び出しで、モジュールを PowerShell にインポート[Import-module](/powershell/module/Microsoft.PowerShell.Core/Import-Module)します。</span><span class="sxs-lookup"><span data-stu-id="41b66-127">Import your module into PowerShell with a call to [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module).</span></span>

   <span data-ttu-id="41b66-128">呼び出す[Import-module](/powershell/module/Microsoft.PowerShell.Core/Import-Module)アクティブ メモリに、モジュールが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="41b66-128">Calling to [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) will load your module into active memory.</span></span> <span data-ttu-id="41b66-129">PowerShell 3.0 を使用してあり、後で、単に呼び出す場合はコードで、モジュールの名前もインポートされます。詳細については、次を参照してください。 [PowerShell モジュールをインポートする](./importing-a-powershell-module.md)します。</span><span class="sxs-lookup"><span data-stu-id="41b66-129">If you are using PowerShell 3.0 and later, simply calling the name of your module in code will also import it; for more information, see [Importing a PowerShell Module](./importing-a-powershell-module.md).</span></span>

## <a name="importing-snap-in-assemblies-as-modules"></a><span data-ttu-id="41b66-130">モジュールとスナップインからアセンブリをインポートします。</span><span class="sxs-lookup"><span data-stu-id="41b66-130">Importing Snap-in Assemblies as Modules</span></span>

<span data-ttu-id="41b66-131">コマンドレットとプロバイダー スナップイン アセンブリ内に存在するは、バイナリ モジュールとして読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="41b66-131">Cmdlets and providers that exist in snap-in assemblies can be loaded as binary modules.</span></span> <span data-ttu-id="41b66-132">スナップインでアセンブリがバイナリ モジュールとして読み込まれた場合は、コマンドレットとプロバイダー、スナップインでは、ユーザーが利用できるが、アセンブリ内のスナップイン クラスは無視され、スナップインが登録されていません。</span><span class="sxs-lookup"><span data-stu-id="41b66-132">When the snap-in assemblies are loaded as binary modules, the cmdlets and providers in the snap-in are available to the user, but the snap-in class in the assembly is ignored, and the snap-in is not registered.</span></span> <span data-ttu-id="41b66-133">その結果、Windows PowerShell によって提供されるスナップインでコマンドレットは、コマンドレットとプロバイダーがセッションに使用可能な場合でものスナップインで検出できません。</span><span class="sxs-lookup"><span data-stu-id="41b66-133">As a result, the snap-in cmdlets provided by Windows PowerShell cannot detect the snap-in even though the cmdlets and providers are available to the session.</span></span>

<span data-ttu-id="41b66-134">さらに、バイナリ モジュールの一部として、スナップインによって参照されている書式設定または種類のファイルをインポートできません。</span><span class="sxs-lookup"><span data-stu-id="41b66-134">In addition, any formatting or types files that are referenced by the snap-in cannot be imported as part of a binary module.</span></span> <span data-ttu-id="41b66-135">書式設定と種類のファイルをインポートするには、モジュール マニフェストを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41b66-135">To import the formatting and types files you must create a module manifest.</span></span> <span data-ttu-id="41b66-136">参照してください、 [PowerShell モジュールのマニフェストを作成する方法](http://msdn.microsoft.com/en-us/abe4c24b-e64e-4a61-81d5-18c4fceba0b6)します。</span><span class="sxs-lookup"><span data-stu-id="41b66-136">See, [How to Write a PowerShell Module Manifest](http://msdn.microsoft.com/en-us/abe4c24b-e64e-4a61-81d5-18c4fceba0b6).</span></span>

## <a name="see-also"></a><span data-ttu-id="41b66-137">参照</span><span class="sxs-lookup"><span data-stu-id="41b66-137">See Also</span></span>

[<span data-ttu-id="41b66-138">Windows PowerShell モジュールの記述</span><span class="sxs-lookup"><span data-stu-id="41b66-138">Writing a Windows PowerShell Module</span></span>](./writing-a-windows-powershell-module.md)
