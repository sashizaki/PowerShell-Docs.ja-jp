---
title: 書式設定データの読み込みとエクスポート |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2a48de31-7961-4b0e-b58b-93466e38370b
caps.latest.revision: 6
ms.openlocfilehash: 5c5168ffd74c15066b914ad1b39d9ead947c5e7f
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365121"
---
# <a name="loading-and-exporting-formatting-data"></a><span data-ttu-id="43d48-102">書式設定データを読み込んでエクスポートする</span><span class="sxs-lookup"><span data-stu-id="43d48-102">Loading and Exporting Formatting Data</span></span>

<span data-ttu-id="43d48-103">フォーマットファイルを作成したら、現在のセッションにファイルを読み込んで、セッションのフォーマットデータを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="43d48-103">Once you have created your formatting file, you need to update the format data of the session by loading your files into the current session.</span></span> <span data-ttu-id="43d48-104">(Windows PowerShell によって提供される書式設定ファイルは、現在のセッションを開いたときに登録されたスナップインによって読み込まれます)。現在のセッションの形式データが更新されると、Windows PowerShell はそのデータを使用して、読み込まれた書式設定ファイルで定義されているビューに関連付けられている .NET オブジェクトを表示します。</span><span class="sxs-lookup"><span data-stu-id="43d48-104">(The formatting files provided by Windows PowerShell are loaded by snap-ins that are registered when the current session is opened.) Once the format data of the current session is updated, Windows PowerShell uses that data to display the .NET objects associated with the views defined in the loaded formatting files.</span></span> <span data-ttu-id="43d48-105">現在のセッションに読み込むことができる書式設定ファイルの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="43d48-105">There is no limit to the number of formatting files that you can load into the current session.</span></span> <span data-ttu-id="43d48-106">書式設定データを更新するだけでなく、現在のセッションの形式データを書式設定ファイルにエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="43d48-106">In addition to updating the formatting data, you can export the format data in the current session back to a formatting file.</span></span>

## <a name="loading-format-data"></a><span data-ttu-id="43d48-107">フォーマットデータを読み込んでいます</span><span class="sxs-lookup"><span data-stu-id="43d48-107">Loading format data</span></span>

<span data-ttu-id="43d48-108">書式設定ファイルは、次のメソッドを使用して現在のセッションに読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="43d48-108">Formatting files can be loaded into the current session using the following methods:</span></span>

- <span data-ttu-id="43d48-109">コマンドラインから現在のセッションに書式設定ファイルをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="43d48-109">You can import the formatting file into the current session from the command line.</span></span> <span data-ttu-id="43d48-110">次の手順に従って、 [Update-FormatData](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="43d48-110">Use the [Update-FormatData](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData) cmdlet as described in the following procedure.</span></span>

- <span data-ttu-id="43d48-111">書式設定ファイルを参照するモジュールマニフェストを作成できます。</span><span class="sxs-lookup"><span data-stu-id="43d48-111">You can create a module manifest that references your formatting file.</span></span> <span data-ttu-id="43d48-112">モジュールを使用すると、配布用にフォーマットファイルをパッケージ化することができます。</span><span class="sxs-lookup"><span data-stu-id="43d48-112">Modules allow you to package you formatting files for distribution.</span></span> <span data-ttu-id="43d48-113">マニフェストを作成するには[new-modulemanifest](/powershell/module/Microsoft.PowerShell.Core/New-ModuleManifest)コマンドレットを使用し、モジュールを現在のセッションに読み込むには、モジュールの[インポート](/powershell/module/Microsoft.PowerShell.Core/Import-Module)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="43d48-113">Use the [New-ModuleManifest](/powershell/module/Microsoft.PowerShell.Core/New-ModuleManifest) cmdlet to create the manifest, and the [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet to load the module into the current session.</span></span> <span data-ttu-id="43d48-114">モジュールの詳細については、「 [Windows PowerShell モジュールの記述](../module/writing-a-windows-powershell-module.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43d48-114">For more information about modules, see [Writing a Windows PowerShell Module](../module/writing-a-windows-powershell-module.md).</span></span>

- <span data-ttu-id="43d48-115">書式設定ファイルを参照するスナップインを作成できます。</span><span class="sxs-lookup"><span data-stu-id="43d48-115">You can create a snap-in that references your formatting file.</span></span> <span data-ttu-id="43d48-116">[Add-pssnapin](/dotnet/api/System.Management.Automation.PSSnapIn.Formats)を使用して、書式設定ファイルを参照します。</span><span class="sxs-lookup"><span data-stu-id="43d48-116">Use the [System.Management.Automation.PSSnapIn.Formats](/dotnet/api/System.Management.Automation.PSSnapIn.Formats) to reference your formatting files.</span></span> <span data-ttu-id="43d48-117">モジュールをパッケージ化し、配布用に関連付けられているフォーマットファイルと型ファイルをパッケージ化することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="43d48-117">It is strongly encouraged to use modules to package cmdlets, and any associated formatting and types files for distribution.</span></span> <span data-ttu-id="43d48-118">モジュールの詳細については、「 [Windows PowerShell モジュールの記述](../module/writing-a-windows-powershell-module.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43d48-118">For more information about modules, see [Writing a Windows PowerShell Module](../module/writing-a-windows-powershell-module.md).</span></span>

- <span data-ttu-id="43d48-119">プログラムによってコマンドを呼び出す場合は、コマンドが実行される実行空間の初期セッション状態に、書式設定ファイルエントリを追加できます。</span><span class="sxs-lookup"><span data-stu-id="43d48-119">If you are invoking commands programmatically, you can add a formatting file entry to the initial session state of the runspace where the commands are run.</span></span> <span data-ttu-id="43d48-120">書式設定ファイルの追加に使用される .NET 型の詳細については、Sessionstateformatentry を参照してください。 [Displayproperty = Fullname](/dotnet/api/System.Management.Automation.Runspaces.SessionStateFormatEntry)クラス。</span><span class="sxs-lookup"><span data-stu-id="43d48-120">For more information about .NET type used to add the formatting file, see the [System.Management.Automation.Runspaces.Sessionstateformatentry?Displayproperty=Fullname](/dotnet/api/System.Management.Automation.Runspaces.SessionStateFormatEntry) class.</span></span>

<span data-ttu-id="43d48-121">フォーマットファイルが読み込まれると、コマンドラインでオブジェクトを表示するときに使用するビューを決定するために Windows PowerShell で使用される内部リストに追加されます。</span><span class="sxs-lookup"><span data-stu-id="43d48-121">When a formatting file is loaded, it is added to an internal list that Windows PowerShell uses to determine which view to use when displaying objects at the command line.</span></span> <span data-ttu-id="43d48-122">書式設定ファイルは、リストの先頭に付加することも、リストの末尾に追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="43d48-122">You can prepend your formatting file to the beginning of the list, or you can append it to the end of the list.</span></span> <span data-ttu-id="43d48-123">Windows PowerShell コアコマンドレットによって返されるオブジェクトの変更方法を変更する場合など、既存のビューが定義されているオブジェクトのビューを定義する書式設定ファイルを読み込む場合は、書式設定ファイルがこのリストに追加された場所を知っておくことが重要です。 さ.</span><span class="sxs-lookup"><span data-stu-id="43d48-123">Knowing where your formatting file is added to this list is important if you are loading formatting file that defines a view for an object that has an existing view defined, such as when you want to change how an object that is returned by a Windows PowerShell core cmdlet is displayed.</span></span> <span data-ttu-id="43d48-124">オブジェクトのビューのみを定義する書式設定ファイルを読み込む場合は、前述の方法のいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="43d48-124">If you are loading a formatting file that defines the only view for an object, you can use any of the methods described previously.</span></span>  <span data-ttu-id="43d48-125">オブジェクトの別のビューを定義する書式設定ファイルを読み込む場合は、[更新プログラムの FormatData](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData)コマンドレットを使用して、ファイルをリストの先頭に付加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="43d48-125">If you are loading a formatting file that defines another view for an object, you must use the [Update-FormatData](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData) cmdlet and prepend your file to the beginning of the list.</span></span>

## <a name="storing-your-formatting-file"></a><span data-ttu-id="43d48-126">書式設定ファイルの格納</span><span class="sxs-lookup"><span data-stu-id="43d48-126">Storing Your Formatting File</span></span>

<span data-ttu-id="43d48-127">フォーマットファイルがディスクに格納される場所に関する要件はありません。</span><span class="sxs-lookup"><span data-stu-id="43d48-127">There is no requirement for where your formatting files are stored on disk.</span></span> <span data-ttu-id="43d48-128">ただし、次のフォルダーに格納することを強くお勧めします。 `user\documents\windowspowershell\`</span><span class="sxs-lookup"><span data-stu-id="43d48-128">However, it is strongly suggested that you store them in the following folder: `user\documents\windowspowershell\`</span></span>

#### <a name="loading-a-format-file-using-import-formatdata"></a><span data-ttu-id="43d48-129">Import-FormatData を使用してフォーマットファイルを読み込む</span><span class="sxs-lookup"><span data-stu-id="43d48-129">Loading a format file using Import-FormatData</span></span>

1. <span data-ttu-id="43d48-130">フォーマットファイルをディスクに保存します。</span><span class="sxs-lookup"><span data-stu-id="43d48-130">Store your formatting file to disk.</span></span>

2. <span data-ttu-id="43d48-131">次のいずれかのコマンドを使用して、 [Update-FormatData](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData)コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="43d48-131">Run the [Update-FormatData](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData) cmdlet using one of the following commands.</span></span>

   <span data-ttu-id="43d48-132">書式設定ファイルを一覧の先頭に追加するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="43d48-132">To add your formatting file to the front of the list use this command.</span></span> <span data-ttu-id="43d48-133">オブジェクトの表示方法を変更する場合は、このコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="43d48-133">Use this command if you are changing how an object is displayed.</span></span>

   ```powershell
   Update-FormatData -PrependPath PathToFormattingFile
   ```

   <span data-ttu-id="43d48-134">書式設定ファイルを一覧の末尾に追加するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="43d48-134">To add your formatting file to the end of the list use this command.</span></span>

   ```powershell
   Update-FormatData -AppendPath PathToFormattingFile
   ```

   <span data-ttu-id="43d48-135">[更新プログラムの FormatData](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData)コマンドレットを使用してファイルを追加した後は、セッションが開いているときに一覧からファイルを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="43d48-135">Once you have added a file using the [Update-FormatData](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData) cmdlet, you cannot remove the file from the list while the session is open.</span></span> <span data-ttu-id="43d48-136">一覧から書式設定ファイルを削除するには、セッションを閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="43d48-136">You must close the session to remove the formatting file from the list.</span></span>

## <a name="exporting-format-data"></a><span data-ttu-id="43d48-137">フォーマットデータのエクスポート</span><span class="sxs-lookup"><span data-stu-id="43d48-137">Exporting format data</span></span>

<span data-ttu-id="43d48-138">ここにセクションの本文を挿入してください。</span><span class="sxs-lookup"><span data-stu-id="43d48-138">Insert section body here.</span></span>
