---
ms.date: 06/12/2017
title: WMF 5.0 のアンインストール
description: この記事では、旧バージョンの Windows から WMF をアンインストールする方法について説明します。
ms.openlocfilehash: d8078ea918db2c1cf9a7ddd6ea8d1413b593c0ff
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92660808"
---
# <a name="uninstallation-instructions"></a><span data-ttu-id="228d2-103">アンインストール手順</span><span class="sxs-lookup"><span data-stu-id="228d2-103">Uninstallation Instructions</span></span>

## <a name="using-command-prompt"></a><span data-ttu-id="228d2-104">コマンド プロンプトを使用</span><span class="sxs-lookup"><span data-stu-id="228d2-104">Using Command Prompt</span></span>

1. <span data-ttu-id="228d2-105">**コマンド プロンプト** を開きます。</span><span class="sxs-lookup"><span data-stu-id="228d2-105">Open **Command Prompt.**</span></span>
2. <span data-ttu-id="228d2-106">[Windows Update スタンドアロン ランチャー](https://support.microsoft.com/kb/934307)を次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="228d2-106">Run the [Windows Update Standalone Launcher](https://support.microsoft.com/kb/934307) as shown below:</span></span>

<span data-ttu-id="228d2-107">Windows Server 2012 R2 および Windows 8.1:</span><span class="sxs-lookup"><span data-stu-id="228d2-107">On Windows Server 2012 R2 and Windows 8.1:</span></span>

```powershell
wusa /uninstall /kb:3134758
```

<span data-ttu-id="228d2-108">Windows Server 2012:</span><span class="sxs-lookup"><span data-stu-id="228d2-108">On Windows Server 2012:</span></span>

```powershell
wusa /uninstall /kb:3134759
```

<span data-ttu-id="228d2-109">Windows Server 2008 R2 SP1 および Windows 7 SP1:</span><span class="sxs-lookup"><span data-stu-id="228d2-109">On Windows Server 2008 R2 SP1 and Windows 7 SP1:</span></span>

```powershell
wusa /uninstall /kb:3134760
```

## <a name="using-control-panel"></a><span data-ttu-id="228d2-110">コントロール パネルを使用</span><span class="sxs-lookup"><span data-stu-id="228d2-110">Using Control Panel</span></span>

1. <span data-ttu-id="228d2-111">**[コントロール パネル]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="228d2-111">Open **Control Panel.**</span></span>
2. <span data-ttu-id="228d2-112">**[プログラム]** を開き、 **[プログラムのアンインストール]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="228d2-112">Open **Programs** , then open **Uninstall a program.**</span></span>
3. <span data-ttu-id="228d2-113">**[インストールされた更新プログラムを表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="228d2-113">Click **View installed updates.**</span></span>
4. <span data-ttu-id="228d2-114">インストールされた更新プログラムの一覧から **[Windows Management Framework 5.0]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="228d2-114">Select **Windows Management Framework 5.0** from the list of installed updates.</span></span> <span data-ttu-id="228d2-115">これは *KB3134758* 、 *KB3134759* 、または *KB3134760* に対応しています。</span><span class="sxs-lookup"><span data-stu-id="228d2-115">This corresponds to *KB3134758* , *KB3134759* , or *KB3134760*.</span></span> <span data-ttu-id="228d2-116">**[アンインストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="228d2-116">Click **Uninstall.**</span></span>
