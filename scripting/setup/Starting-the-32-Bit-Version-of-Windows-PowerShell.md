---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "32 ビット版の Windows PowerShell を起動する"
ms.assetid: 12b31890-2609-4a76-8c24-0ebe78084f50
ms.openlocfilehash: 927b4028fcab68cb26d92bf292df2f0270837457
ms.sourcegitcommit: 598b7835046577841aea2211d613bb8513271a8b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2017
---
# <a name="starting-the-32-bit-version-of-windows-powershell"></a><span data-ttu-id="df4fb-103">32 ビット版の Windows PowerShell を起動する</span><span class="sxs-lookup"><span data-stu-id="df4fb-103">Starting the 32-Bit Version of Windows PowerShell</span></span>
<span data-ttu-id="df4fb-104">64 ビット コンピューターに Windows PowerShell をインストールする場合、64 ビット版に加えて、**Windows PowerShell (x86)**、つまり Windows PowerShell の 32 ビット版もインストールされます。</span><span class="sxs-lookup"><span data-stu-id="df4fb-104">When you install Windows PowerShell on a 64-bit computer, **Windows PowerShell (x86)**, a 32-bit version of Windows PowerShell is installed in addition to the 64-bit version.</span></span> <span data-ttu-id="df4fb-105">Windows PowerShell を実行すると、既定では 64 ビット版が実行されます。</span><span class="sxs-lookup"><span data-stu-id="df4fb-105">When you run Windows PowerShell, the 64-bit version runs by default.</span></span>

<span data-ttu-id="df4fb-106">ただし、32 ビット版を必要とするモジュールを使用するときや、32 ビットのコンピューターにリモートで接続しているときなど、**Windows PowerShell (x86)** の実行を必要とすることもときどきあります。</span><span class="sxs-lookup"><span data-stu-id="df4fb-106">However, you might occasionally need to run **Windows PowerShell (x86)**, such as when you are using a module that requires the 32-bit version or when you are connecting remotely to a 32-bit computer.</span></span>

<span data-ttu-id="df4fb-107">Windows PowerShell の 32 ビット版を起動するには、次の手順のいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="df4fb-107">To start a 32-bit version of Windows PowerShell, use any of the following procedures.</span></span>

#### <a name="in-windows-server-2012-r2"></a><span data-ttu-id="df4fb-108">Windows Server® 2012 R2 の場合</span><span class="sxs-lookup"><span data-stu-id="df4fb-108">In Windows Server® 2012 R2</span></span>

-   <span data-ttu-id="df4fb-109">**[スタート]** 画面で、「**Windows PowerShell (x86)**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="df4fb-109">On the **Start** screen, type **Windows PowerShell (x86)**.</span></span> <span data-ttu-id="df4fb-110">**[Windows PowerShell x86]** タイルをクリックします。</span><span class="sxs-lookup"><span data-stu-id="df4fb-110">Click the **Windows PowerShell x86** tile.</span></span>

-   <span data-ttu-id="df4fb-111">**サーバー マネージャー**の **[ツール]** メニューから、**[Windows PowerShell (x86)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="df4fb-111">In **Server Manager**, from the **Tools** menu, select **Windows PowerShell (x86)**.</span></span>

-   <span data-ttu-id="df4fb-112">デスクトップで、右上隅にカーソルを移動し、**[検索]** をクリックする。「**PowerShell x86**」と入力し、**[Windows PowerShell (x86)]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df4fb-112">On the desktop, move the cursor to the upper right corner, click **Search**, type **PowerShell x86** and then click **Windows PowerShell (x86)**.</span></span>

-   <span data-ttu-id="df4fb-113">コマンド ラインで、次のように入力します。`%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span><span class="sxs-lookup"><span data-stu-id="df4fb-113">Via command line, enter: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span></span>

#### <a name="in-windows-server-2012"></a><span data-ttu-id="df4fb-114">Windows Server® 2012 の場合</span><span class="sxs-lookup"><span data-stu-id="df4fb-114">In Windows Server® 2012</span></span>

-   <span data-ttu-id="df4fb-115">**[スタート]** 画面で、「**PowerShell**」と入力して **[Windows PowerShell (x86)]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df4fb-115">On the **Start** screen, type **PowerShell** and then click **Windows PowerShell (x86)**.</span></span>

-   <span data-ttu-id="df4fb-116">**サーバー マネージャー**の **[ツール]** メニューから、**[Windows PowerShell (x86)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="df4fb-116">In **Server Manager**, from the **Tools** menu, select **Windows PowerShell (x86)**.</span></span>

-   <span data-ttu-id="df4fb-117">デスクトップで、右上隅にカーソルを移動し、**[検索]** をクリックする。「**PowerShell**」と入力し、**[Windows PowerShell (x86)]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df4fb-117">On the desktop, move the cursor to the upper right corner, click **Search**, type **PowerShell** and then click **Windows PowerShell (x86)**.</span></span>

-   <span data-ttu-id="df4fb-118">コマンド ラインで、次のように入力します。`%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span><span class="sxs-lookup"><span data-stu-id="df4fb-118">Via command line, enter: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span></span>

#### <a name="in-windows-81"></a><span data-ttu-id="df4fb-119">Windows® 8.1 の場合</span><span class="sxs-lookup"><span data-stu-id="df4fb-119">In Windows® 8.1</span></span>

-   <span data-ttu-id="df4fb-120">**[スタート]** 画面で、「**Windows PowerShell (x86)**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="df4fb-120">On the **Start** screen, type **Windows PowerShell (x86)**.</span></span> <span data-ttu-id="df4fb-121">**[Windows PowerShell x86]** タイルをクリックします。</span><span class="sxs-lookup"><span data-stu-id="df4fb-121">Click the **Windows PowerShell x86** tile.</span></span>

-   <span data-ttu-id="df4fb-122">Windows 8.1 の[リモート サーバー管理ツール](http://go.microsoft.com/fwlink/?LinkID=304145)を実行している場合、**[サーバー管理ツール]** メニューから [Windows PowerShell x86] を開くこともできます。</span><span class="sxs-lookup"><span data-stu-id="df4fb-122">If you are running [Remote Server Administration Tools](http://go.microsoft.com/fwlink/?LinkID=304145) for Windows 8.1, you can also open Windows PowerShell x86 from the **Server ManagerTools** menu.</span></span> <span data-ttu-id="df4fb-123">**[Windows PowerShell (x86)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="df4fb-123">Select **Windows PowerShell (x86)**.</span></span>

-   <span data-ttu-id="df4fb-124">デスクトップで、右上隅にカーソルを移動し、**[検索]** をクリックする。「**PowerShell x86**」と入力し、**[Windows PowerShell (x86)]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df4fb-124">On the desktop, move the cursor to the upper right corner, click **Search**, type **PowerShell x86** and then click **Windows PowerShell (x86)**.</span></span>
   
-   <span data-ttu-id="df4fb-125">コマンド ラインで、次のように入力します。`%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span><span class="sxs-lookup"><span data-stu-id="df4fb-125">Via command line, enter: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span></span>

#### <a name="in-windows-8"></a><span data-ttu-id="df4fb-126">In Windows® 8 の場合</span><span class="sxs-lookup"><span data-stu-id="df4fb-126">In Windows® 8</span></span>

-   <span data-ttu-id="df4fb-127">**[スタート]** 画面で、右上隅にカーソルを移動し、**[設定]** をクリックし、**[タイル]** をクリックします。そして、**[管理ツールを表示する]** スライダーを [はい] に移動させます。</span><span class="sxs-lookup"><span data-stu-id="df4fb-127">On the **Start** screen, move the cursor to the upper right corner, click **Settings**, click **Tiles**, and then move the **Show Administrative Tools** slider to Yes.</span></span> <span data-ttu-id="df4fb-128">次に「**PowerShell**」と入力し、**[Windows PowerShell(x86)]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df4fb-128">Then, type **PowerShell** and click **Windows PowerShell (x86)**.</span></span>

-   <span data-ttu-id="df4fb-129">Windows 8 の[リモート サーバー管理ツール](http://www.microsoft.com/download/details.aspx?id=28972)を実行している場合、**[サーバー管理ツール]** メニューから [Windows PowerShell x86] を開くこともできます。</span><span class="sxs-lookup"><span data-stu-id="df4fb-129">If you are running [Remote Server Administration Tools](http://www.microsoft.com/download/details.aspx?id=28972) for Windows 8, you can also open Windows PowerShell x86 from the **Server ManagerTools** menu.</span></span> <span data-ttu-id="df4fb-130">**[Windows PowerShell (x86)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="df4fb-130">Select **Windows PowerShell (x86)**.</span></span>

-   <span data-ttu-id="df4fb-131">**[スタート]** 画面またはデスクトップで、「**PowerShell (x86)**」と入力し、**[Windows PowerShell (x86)]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df4fb-131">On the **Start** screen or the desktop, type **PowerShell (x86)** and then click **Windows PowerShell (x86)**.</span></span>

-   <span data-ttu-id="df4fb-132">コマンド ラインで、次のように入力します。`%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span><span class="sxs-lookup"><span data-stu-id="df4fb-132">Via command line, enter: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span></span>

