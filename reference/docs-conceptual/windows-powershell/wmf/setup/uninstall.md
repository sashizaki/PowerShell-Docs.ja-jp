---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
title: WMF 5.0 のアンインストール
ms.openlocfilehash: fa76bacb4b62025d0d2350b9a0e072068ca83ab1
ms.sourcegitcommit: c4906f4c9fa4ef1a16dcd6dd00ff960d19446d71
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2020
ms.locfileid: "89236307"
---
# <a name="uninstallation-instructions"></a><span data-ttu-id="d1ae1-103">アンインストール手順</span><span class="sxs-lookup"><span data-stu-id="d1ae1-103">Uninstallation Instructions</span></span>

## <a name="using-command-prompt"></a><span data-ttu-id="d1ae1-104">コマンド プロンプトを使用</span><span class="sxs-lookup"><span data-stu-id="d1ae1-104">Using Command Prompt</span></span>

1. <span data-ttu-id="d1ae1-105">**コマンド プロンプト**を開きます。</span><span class="sxs-lookup"><span data-stu-id="d1ae1-105">Open **Command Prompt.**</span></span>
2. <span data-ttu-id="d1ae1-106">[Windows Update スタンドアロン ランチャー](https://support.microsoft.com/kb/934307)を次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="d1ae1-106">Run the [Windows Update Standalone Launcher](https://support.microsoft.com/kb/934307) as shown below:</span></span>

<span data-ttu-id="d1ae1-107">Windows Server 2012 R2 および Windows 8.1:</span><span class="sxs-lookup"><span data-stu-id="d1ae1-107">On Windows Server 2012 R2 and Windows 8.1:</span></span>

```powershell
wusa /uninstall /kb:3134758
```

<span data-ttu-id="d1ae1-108">Windows Server 2012:</span><span class="sxs-lookup"><span data-stu-id="d1ae1-108">On Windows Server 2012:</span></span>

```powershell
wusa /uninstall /kb:3134759
```

<span data-ttu-id="d1ae1-109">Windows Server 2008 R2 SP1 および Windows 7 SP1:</span><span class="sxs-lookup"><span data-stu-id="d1ae1-109">On Windows Server 2008 R2 SP1 and Windows 7 SP1:</span></span>

```powershell
wusa /uninstall /kb:3134760
```

## <a name="using-control-panel"></a><span data-ttu-id="d1ae1-110">コントロール パネルを使用</span><span class="sxs-lookup"><span data-stu-id="d1ae1-110">Using Control Panel</span></span>

1. <span data-ttu-id="d1ae1-111">**[コントロール パネル]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="d1ae1-111">Open **Control Panel.**</span></span>
2. <span data-ttu-id="d1ae1-112">**[プログラム]** を開き、 **[プログラムのアンインストール]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="d1ae1-112">Open **Programs**, then open **Uninstall a program.**</span></span>
3. <span data-ttu-id="d1ae1-113">**[インストールされた更新プログラムを表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1ae1-113">Click **View installed updates.**</span></span>
4. <span data-ttu-id="d1ae1-114">インストールされた更新プログラムの一覧から **[Windows Management Framework 5.0]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1ae1-114">Select **Windows Management Framework 5.0** from the list of installed updates.</span></span> <span data-ttu-id="d1ae1-115">これは *KB3134758*、*KB3134759*、または *KB3134760* に対応しています。</span><span class="sxs-lookup"><span data-stu-id="d1ae1-115">This corresponds to *KB3134758*, *KB3134759*, or *KB3134760*.</span></span> <span data-ttu-id="d1ae1-116">**[アンインストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1ae1-116">Click **Uninstall.**</span></span>
