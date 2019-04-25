---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 385bb7223b19c8ace8088ba469e543721a527b99
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62057526"
---
# <a name="uninstallation-instructions"></a><span data-ttu-id="3f13d-102">アンインストール手順</span><span class="sxs-lookup"><span data-stu-id="3f13d-102">Uninstallation Instructions</span></span>

## <a name="using-command-prompt"></a><span data-ttu-id="3f13d-103">コマンド プロンプトを使用</span><span class="sxs-lookup"><span data-stu-id="3f13d-103">Using Command Prompt</span></span>
1.  <span data-ttu-id="3f13d-104">**コマンド プロンプト**を開きます。</span><span class="sxs-lookup"><span data-stu-id="3f13d-104">Open **Command Prompt.**</span></span>
2.  <span data-ttu-id="3f13d-105">[Windows Update スタンドアロン ランチャー](https://support.microsoft.com/en-us/kb/934307)を次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="3f13d-105">Run the [Windows Update Standalone Launcher](https://support.microsoft.com/en-us/kb/934307) as shown below:</span></span>

<span data-ttu-id="3f13d-106">Windows Server 2012 R2 および Windows 8.1:</span><span class="sxs-lookup"><span data-stu-id="3f13d-106">On Windows Server 2012 R2 and Windows 8.1:</span></span>
```powershell
wusa /uninstall /kb:3134758
```
<span data-ttu-id="3f13d-107">Windows Server 2012:</span><span class="sxs-lookup"><span data-stu-id="3f13d-107">On Windows Server 2012:</span></span>
```powershell
wusa /uninstall /kb:3134759
```
<span data-ttu-id="3f13d-108">Windows Server 2008 R2 SP1 および Windows 7 SP1:</span><span class="sxs-lookup"><span data-stu-id="3f13d-108">On Windows Server 2008 R2 SP1 and Windows 7 SP1:</span></span>
```powershell
wusa /uninstall /kb:3134760
```

## <a name="using-control-panel"></a><span data-ttu-id="3f13d-109">コントロール パネルを使用</span><span class="sxs-lookup"><span data-stu-id="3f13d-109">Using Control Panel</span></span>
1.  <span data-ttu-id="3f13d-110">**[コントロール パネル]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="3f13d-110">Open **Control Panel.**</span></span>
2.  <span data-ttu-id="3f13d-111">**[プログラム]** を開き、**[プログラムのアンインストール]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="3f13d-111">Open **Programs**, then open **Uninstall a program.**</span></span>
3.  <span data-ttu-id="3f13d-112">**[インストールされた更新プログラムを表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f13d-112">Click **View installed updates.**</span></span>
4.  <span data-ttu-id="3f13d-113">インストールされた更新プログラムの一覧から **[Windows Management Framework 5.0]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3f13d-113">Select **Windows Management Framework 5.0** from the list of installed updates.</span></span> <span data-ttu-id="3f13d-114">これは *KB3134758*、*KB3134759*、または *KB3134760* に対応しています。</span><span class="sxs-lookup"><span data-stu-id="3f13d-114">This corresponds to *KB3134758*, *KB3134759*, or *KB3134760*.</span></span> <span data-ttu-id="3f13d-115">**[アンインストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f13d-115">Click **Uninstall.**</span></span>
