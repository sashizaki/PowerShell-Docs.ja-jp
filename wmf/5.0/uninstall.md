---
ms.date: 06/12/2017
author: JKeithB
ms.topic: reference
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 78ae7ecd40b4d8ad0a6750f43002986483ab18a7
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="uninstallation-instructions"></a><span data-ttu-id="641c5-102">アンインストール手順</span><span class="sxs-lookup"><span data-stu-id="641c5-102">Uninstallation Instructions</span></span>

## <a name="using-command-prompt"></a><span data-ttu-id="641c5-103">コマンド プロンプトを使用</span><span class="sxs-lookup"><span data-stu-id="641c5-103">Using Command Prompt</span></span>
1.  <span data-ttu-id="641c5-104">**コマンド プロンプト**を開きます。</span><span class="sxs-lookup"><span data-stu-id="641c5-104">Open **Command Prompt.**</span></span>
2.  <span data-ttu-id="641c5-105">[Windows Update スタンドアロン ランチャー](https://support.microsoft.com/en-us/kb/934307)を次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="641c5-105">Run the [Windows Update Standalone Launcher](https://support.microsoft.com/en-us/kb/934307) as shown below:</span></span>

<span data-ttu-id="641c5-106">Windows Server 2012 R2 および Windows 8.1:</span><span class="sxs-lookup"><span data-stu-id="641c5-106">On Windows Server 2012 R2 and Windows 8.1:</span></span>
```powershell
wusa /uninstall /kb:3134758
```
<span data-ttu-id="641c5-107">Windows Server 2012:</span><span class="sxs-lookup"><span data-stu-id="641c5-107">On Windows Server 2012:</span></span>
```powershell
wusa /uninstall /kb:3134759
```
<span data-ttu-id="641c5-108">Windows Server 2008 R2 SP1 および Windows 7 SP1:</span><span class="sxs-lookup"><span data-stu-id="641c5-108">On Windows Server 2008 R2 SP1 and Windows 7 SP1:</span></span>
```powershell
wusa /uninstall /kb:3134760
```

## <a name="using-control-panel"></a><span data-ttu-id="641c5-109">コントロール パネルを使用</span><span class="sxs-lookup"><span data-stu-id="641c5-109">Using Control Panel</span></span>
1.  <span data-ttu-id="641c5-110">**[コントロール パネル]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="641c5-110">Open **Control Panel.**</span></span>
2.  <span data-ttu-id="641c5-111">**[プログラム]** を開き、**[プログラムのアンインストール]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="641c5-111">Open **Programs**, then open **Uninstall a program.**</span></span>
3.  <span data-ttu-id="641c5-112">**[インストールされた更新プログラムを表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="641c5-112">Click **View installed updates.**</span></span>
4.  <span data-ttu-id="641c5-113">インストールされた更新プログラムの一覧から **[Windows Management Framework 5.0]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="641c5-113">Select **Windows Management Framework 5.0** from the list of installed updates.</span></span> <span data-ttu-id="641c5-114">これは *KB3134758*、*KB3134759*、または *KB3134760* に対応しています。</span><span class="sxs-lookup"><span data-stu-id="641c5-114">This corresponds to *KB3134758*, *KB3134759*, or *KB3134760*.</span></span> <span data-ttu-id="641c5-115">**[アンインストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="641c5-115">Click **Uninstall.**</span></span>