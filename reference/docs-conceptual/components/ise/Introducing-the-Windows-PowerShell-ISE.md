---
ms.date: 08/14/2018
keywords: PowerShell, コマンドレット
title: Windows PowerShell ISE の紹介
ms.openlocfilehash: 729c8535dbcfcd2c51070b8beac5d328375f36ae
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62057425"
---
# <a name="the-windows-powershell-ise"></a><span data-ttu-id="c8327-103">Windows PowerShell ISE</span><span class="sxs-lookup"><span data-stu-id="c8327-103">The Windows PowerShell ISE</span></span>

<span data-ttu-id="c8327-104">Windows PowerShell Integrated Scripting Environment (ISE) は、Windows PowerShell のホスト アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="c8327-104">The Windows PowerShell Integrated Scripting Environment (ISE) is a host application for Windows PowerShell.</span></span> <span data-ttu-id="c8327-105">ISE では、コマンドを実行して、単一の Windows ベースのグラフィカル ユーザー インターフェイスでスクリプトの書き込み、テスト、およびデバッグを行うことが可能です。</span><span class="sxs-lookup"><span data-stu-id="c8327-105">In the ISE, you can run commands and write, test, and debug scripts in a single Windows-based graphic user interface.</span></span> <span data-ttu-id="c8327-106">ISE では、複数行の編集、タブ補完、構文の色分け、選択的な実行、状況依存のヘルプ、および右から左方向の言語のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="c8327-106">The ISE provides multiline editing, tab completion, syntax coloring, selective execution, context-sensitive help, and support for right-to-left languages.</span></span> <span data-ttu-id="c8327-107">メニュー項目とキーボード ショートカットは、Windows PowerShell コンソールで実行する多数の同じタスクにマッピングされます。</span><span class="sxs-lookup"><span data-stu-id="c8327-107">Menu items and keyboard shortcuts are mapped to many of the same tasks that you would do in the Windows PowerShell console.</span></span> <span data-ttu-id="c8327-108">たとえば、ISE でスクリプトをデバッグするとき、編集ウィンドウでコード行を右クリックするとブレークポイントを設定できます。</span><span class="sxs-lookup"><span data-stu-id="c8327-108">For example, when you debug a script in the ISE, you can right-click on a line of code in the edit pane to set a breakpoint.</span></span>

## <a name="support"></a><span data-ttu-id="c8327-109">サポート</span><span class="sxs-lookup"><span data-stu-id="c8327-109">Support</span></span>

<span data-ttu-id="c8327-110">ISE は、Windows PowerShell V2 で初めて導入され、PowerShell V3 で再設計されました。</span><span class="sxs-lookup"><span data-stu-id="c8327-110">The ISE was first introduced with Windows PowerShell V2 and was re-designed with PowerShell V3.</span></span> <span data-ttu-id="c8327-111">ISE は、Windows PowerShell V5.1 までのすべてのサポートされているバージョンの Windows PowerShell でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c8327-111">The ISE is supported in all supported versions of Windows PowerShell up to and including Windows PowerShell V5.1.</span></span> <span data-ttu-id="c8327-112">ただし、ISE はメンテナンス モードであり、新しい機能は追加されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c8327-112">The ISE, however, is in maintenance mode and no new features are likely to be added.</span></span>
<span data-ttu-id="c8327-113">また、PowerShell v6 以降では ISE はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="c8327-113">Additionally, there is no support for the ISE with PowerShell v6 and beyond.</span></span> <span data-ttu-id="c8327-114">PowerShell スクリプトなどを管理するためのグラフィカル ツールを利用するには、[Visual Studio Code](https://code.visualstudio.com/) を検討することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c8327-114">Users wanting a graphical tool with which to manage PowerShell scripts, etc, should consider [Visual Studio Code](https://code.visualstudio.com/).</span></span>

## <a name="key-features"></a><span data-ttu-id="c8327-115">主な機能</span><span class="sxs-lookup"><span data-stu-id="c8327-115">Key Features</span></span>

<span data-ttu-id="c8327-116">Windows PowerShell ISE の主な機能:</span><span class="sxs-lookup"><span data-stu-id="c8327-116">Key features in Windows PowerShell ISE include:</span></span>

- <span data-ttu-id="c8327-117">複数行の編集:[コマンド] ウィンドウで現在の行の下に空白行を挿入するには、Shift キーを押しながら Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c8327-117">Multiline editing: To insert a blank line under the current line in the Command pane, press SHIFT+ENTER.</span></span>
- <span data-ttu-id="c8327-118">選択して実行:スクリプトの一部を実行するには、実行するテキストを選択して、**[スクリプトの実行]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8327-118">Selective execution: To run part of a script, select the text you want to run, and then click the **Run Script** button.</span></span> <span data-ttu-id="c8327-119">または、F5 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c8327-119">Or, press F5.</span></span>
- <span data-ttu-id="c8327-120">状況依存ヘルプ:**Invoke-Item** と入力し、F1 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c8327-120">Context-sensitive help: Type **Invoke-Item**, and then press F1.</span></span> <span data-ttu-id="c8327-121">ヘルプ ファイルの **Invoke-Item** コマンドレットに関する記事が開きます。</span><span class="sxs-lookup"><span data-stu-id="c8327-121">The Help file opens to the article for the **Invoke-Item** cmdlet.</span></span>

<span data-ttu-id="c8327-122">Windows PowerShell ISE では、外観の一部をカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="c8327-122">The Windows PowerShell ISE lets you customize some aspects of its appearance.</span></span> <span data-ttu-id="c8327-123">また、独自の Windows PowerShell プロファイル スクリプトもあります。</span><span class="sxs-lookup"><span data-stu-id="c8327-123">It also has its own Windows PowerShell profile script.</span></span>

## <a name="to-start-the-windows-powershell-ise"></a><span data-ttu-id="c8327-124">Windows PowerShell ISE を開始するには</span><span class="sxs-lookup"><span data-stu-id="c8327-124">To start the Windows PowerShell ISE</span></span>

<span data-ttu-id="c8327-125">**[スタート]** をクリックし、**[Windows PowerShell]** を選択して、**[Windows PowerShell ISE]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8327-125">Click **Start**, select **Windows PowerShell**, and then click **Windows PowerShell ISE**.</span></span>
<span data-ttu-id="c8327-126">代わりに、任意のコマンド シェルまたは [実行] ボックスに `powershell_ise.exe` を入力することも可能です。</span><span class="sxs-lookup"><span data-stu-id="c8327-126">Alternately, you can type `powershell_ise.exe` in any command shell or in the Run box.</span></span>

## <a name="to-get-help-in-the-windows-powershell-ise"></a><span data-ttu-id="c8327-127">Windows PowerShell ISE のヘルプを利用するには</span><span class="sxs-lookup"><span data-stu-id="c8327-127">To get Help in the Windows PowerShell ISE</span></span>

<span data-ttu-id="c8327-128">**[ヘルプ]** メニューで、**[Windows PowerShell ヘルプ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8327-128">On the **Help** menu, click **Windows PowerShell Help**.</span></span> <span data-ttu-id="c8327-129">または、F1 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c8327-129">Or, press F1.</span></span> <span data-ttu-id="c8327-130">開いたファイルは、Get-Help コマンドレットから利用できるすべてのヘルプを含む、Windows PowerShell ISE と Windows PowerShell について説明しています。</span><span class="sxs-lookup"><span data-stu-id="c8327-130">The file that opens describes Windows PowerShell ISE and Windows PowerShell, including all of the help available from the Get-Help cmdlet.</span></span>
