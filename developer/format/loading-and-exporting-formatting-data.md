---
title: 読み込みと書式設定データをエクスポートする |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2a48de31-7961-4b0e-b58b-93466e38370b
caps.latest.revision: 6
ms.openlocfilehash: 86a0e8b7e8967280daa57faf5c323efcd3b1368b
ms.sourcegitcommit: 5990f04b8042ef2d8e571bec6d5b051e64c9921c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2019
ms.locfileid: "57794197"
---
# <a name="loading-and-exporting-formatting-data"></a><span data-ttu-id="cf1e1-102">書式設定データを読み込んでエクスポートする</span><span class="sxs-lookup"><span data-stu-id="cf1e1-102">Loading and Exporting Formatting Data</span></span>

<span data-ttu-id="cf1e1-103">書式設定、ファイルを作成した後は、現在のセッションにファイルを読み込むことによって、セッションの形式のデータを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-103">Once you have created your formatting file, you need to update the format data of the session by loading your files into the current session.</span></span> <span data-ttu-id="cf1e1-104">(Windows PowerShell によって提供される書式設定ファイルは、現在のセッションを開いたときに登録されているスナップインによって読み込まれます)。現在のセッションの形式のデータを更新すると、Windows PowerShell は読み込まれている書式設定ファイルで定義されているビューに関連付けられた .NET オブジェクトを表示するのにデータを使用します。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-104">(The formatting files provided by Windows PowerShell are loaded by snap-ins that are registered when the current session is opened.) Once the format data of the current session is updated, Windows PowerShell uses that data to display the .NET objects associated with the views defined in the loaded formatting files.</span></span> <span data-ttu-id="cf1e1-105">現在のセッションに読み込み可能な書式設定ファイルの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-105">There is no limit to the number of formatting files that you can load into the current session.</span></span> <span data-ttu-id="cf1e1-106">書式設定データを更新するには、に加えて、書式設定ファイルには、現在のセッションで形式のデータをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-106">In addition to updating the formatting data, you can export the format data in the current session back to a formatting file.</span></span>

## <a name="loading-format-data"></a><span data-ttu-id="cf1e1-107">形式のデータの読み込み</span><span class="sxs-lookup"><span data-stu-id="cf1e1-107">Loading format data</span></span>

<span data-ttu-id="cf1e1-108">書式設定ファイルは、次のメソッドを使用して、現在のセッションに読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-108">Formatting files can be loaded into the current session using the following methods:</span></span>

- <span data-ttu-id="cf1e1-109">書式設定ファイルは、コマンドラインから現在のセッションにインポートできます。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-109">You can import the formatting file into the current session from the command line.</span></span> <span data-ttu-id="cf1e1-110">使用して、 [Update-formatdata](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData)コマンドレットの次の手順で説明します。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-110">Use the [Update-FormatData](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData) cmdlet as described in the following procedure.</span></span>

- <span data-ttu-id="cf1e1-111">書式設定、ファイルを参照するモジュール マニフェストを作成できます。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-111">You can create a module manifest that references your formatting file.</span></span> <span data-ttu-id="cf1e1-112">モジュールを使用すると、パッケージ配布用のファイルの書式設定することができます。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-112">Modules allow you to package you formatting files for distribution.</span></span> <span data-ttu-id="cf1e1-113">使用、 [New-modulemanifest](/powershell/module/Microsoft.PowerShell.Core/New-ModuleManifest) 、マニフェストを作成するコマンドレットと[Import-module](/powershell/module/Microsoft.PowerShell.Core/Import-Module)コマンドレットを現在のセッションにモジュールを読み込めません。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-113">Use the [New-ModuleManifest](/powershell/module/Microsoft.PowerShell.Core/New-ModuleManifest) cmdlet to create the manifest, and the [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet to load the module into the current session.</span></span> <span data-ttu-id="cf1e1-114">モジュールの詳細については、次を参照してください。 [Windows PowerShell モジュールの記述](../module/writing-a-windows-powershell-module.md)します。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-114">For more information about modules, see [Writing a Windows PowerShell Module](../module/writing-a-windows-powershell-module.md).</span></span>

- <span data-ttu-id="cf1e1-115">書式設定、ファイルを参照するスナップインを作成できます。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-115">You can create a snap-in that references your formatting file.</span></span> <span data-ttu-id="cf1e1-116">使用して、 [System.Management.Automation.Pssnapin.Formats](/dotnet/api/System.Management.Automation.PSSnapIn.Formats)書式設定ファイルを参照します。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-116">Use the [System.Management.Automation.Pssnapin.Formats](/dotnet/api/System.Management.Automation.PSSnapIn.Formats) to reference your formatting files.</span></span> <span data-ttu-id="cf1e1-117">配布パッケージのコマンドレット モジュールと、関連付けられている書式設定の種類のファイルを使用する推奨になります。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-117">It is strongly encouraged to use modules to package cmdlets, and any associated formatting and types files for distribution.</span></span> <span data-ttu-id="cf1e1-118">モジュールの詳細については、次を参照してください。 [Windows PowerShell モジュールの記述](../module/writing-a-windows-powershell-module.md)します。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-118">For more information about modules, see [Writing a Windows PowerShell Module](../module/writing-a-windows-powershell-module.md).</span></span>

- <span data-ttu-id="cf1e1-119">コマンドをプログラムで起動するが場合、は、コマンドが実行される、実行空間の最初のセッション状態を書式設定ファイルのエントリを追加できます。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-119">If you are invoking commands programmatically, you can add a formatting file entry to the initial session state of the runspace where the commands are run.</span></span> <span data-ttu-id="cf1e1-120">書式設定ファイルを追加するために使用する .NET 型の詳細については、次を参照してください。、 [System.Management.Automation.Runspaces.Sessionstateformatentry でしょうか。Displayproperty = Fullname](/dotnet/api/System.Management.Automation.Runspaces.SessionStateFormatEntry)クラス。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-120">For more information about .NET type used to add the formatting file, see the [System.Management.Automation.Runspaces.Sessionstateformatentry?Displayproperty=Fullname](/dotnet/api/System.Management.Automation.Runspaces.SessionStateFormatEntry) class.</span></span>

<span data-ttu-id="cf1e1-121">書式設定ファイルが読み込まれるときに、内部のリストに追加されます、コマンドラインでオブジェクトを表示するときに使用するビューを決定する Windows PowerShell を使用しています。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-121">When a formatting file is loaded, it is added to an internal list that Windows PowerShell uses to determine which view to use when displaying objects at the command line.</span></span> <span data-ttu-id="cf1e1-122">リストの先頭に、書式設定ファイルを先頭に追加または一覧の末尾に追加することができます。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-122">You can prepend your formatting file to the beginning of the list, or you can append it to the end of the list.</span></span> <span data-ttu-id="cf1e1-123">重要なは、Windows PowerShell コア コマンドレットによって返されるオブジェクトの方法を変更する場合など、定義されている既存のビューを持つオブジェクトのビューを定義する書式設定ファイルを読み込む場合は、書式設定ファイルをこの一覧に追加する場所を知る 表示されます。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-123">Knowing where your formatting file is added to this list is important if you are loading formatting file that defines a view for an object that has an existing view defined, such as when you want to change how an object that is returned by a Windows PowerShell core cmdlet is displayed.</span></span> <span data-ttu-id="cf1e1-124">オブジェクトの唯一のビューを定義する書式設定ファイルを読み込む場合は、前に説明した方法のいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-124">If you are loading a formatting file that defines the only view for an object, you can use any of the methods described previously.</span></span>  <span data-ttu-id="cf1e1-125">使用する必要がある、オブジェクトの別のビューを定義する書式設定ファイルを読み込む場合、 [Update-formatdata](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData)コマンドレットし、ファイル リストの先頭を先頭に追加します。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-125">If you are loading a formatting file that defines another view for an object, you must use the [Update-FormatData](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData) cmdlet and prepend your file to the beginning of the list.</span></span>

## <a name="storing-your-formatting-file"></a><span data-ttu-id="cf1e1-126">書式設定、ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-126">Storing Your Formatting File</span></span>

<span data-ttu-id="cf1e1-127">書式設定、ファイルが保存され、ディスク上の必要はありません。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-127">There is no requirement for where your formatting files are stored on disk.</span></span> <span data-ttu-id="cf1e1-128">ただし、次のフォルダーに格納することを強くお勧めします。 `user\documents\windowspowershell\`</span><span class="sxs-lookup"><span data-stu-id="cf1e1-128">However, it is strongly suggested that you store them in the following folder: `user\documents\windowspowershell\`</span></span>

#### <a name="loading-a-format-file-using-import-formatdata"></a><span data-ttu-id="cf1e1-129">インポート FormatData を使用してフォーマット ファイルの読み込み</span><span class="sxs-lookup"><span data-stu-id="cf1e1-129">Loading a format file using Import-FormatData</span></span>

1. <span data-ttu-id="cf1e1-130">ディスクに書式設定ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-130">Store your formatting file to disk.</span></span>

2. <span data-ttu-id="cf1e1-131">実行、 [Update-formatdata](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData)コマンドレットは、次のコマンドのいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-131">Run the [Update-FormatData](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData) cmdlet using one of the following commands.</span></span>

   <span data-ttu-id="cf1e1-132">一覧の前にファイルを書式を追加するには、このコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-132">To add your formatting file to the front of the list use this command.</span></span> <span data-ttu-id="cf1e1-133">オブジェクトの表示方法を変更する場合は、このコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-133">Use this command if you are changing how an object is displayed.</span></span>

   ```powershell
   Update-FormatData -PrependPath PathToFormattingFile
   ```

   <span data-ttu-id="cf1e1-134">リストの末尾にファイルを書式を追加するには、このコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-134">To add your formatting file to the end of the list use this command.</span></span>

   ```powershell
   Update-FormatData -AppendPath PathToFormattingFile
   ```

   <span data-ttu-id="cf1e1-135">使用してファイルを追加した後、 [Update-formatdata](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData)コマンドレット、ことはできませんファイルを削除する一覧から、セッションが開いているときにします。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-135">Once you have added a file using the [Update-FormatData](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData) cmdlet, you cannot remove the file from the list while the session is open.</span></span> <span data-ttu-id="cf1e1-136">書式設定ファイルを一覧から削除するセッションを閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-136">You must close the session to remove the formatting file from the list.</span></span>

## <a name="exporting-format-data"></a><span data-ttu-id="cf1e1-137">形式のデータをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-137">Exporting format data</span></span>

<span data-ttu-id="cf1e1-138">ここにセクションの本文を挿入してください。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-138">Insert section body here.</span></span>
