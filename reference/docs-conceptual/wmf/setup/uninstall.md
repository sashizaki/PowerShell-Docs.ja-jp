---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
title: WMF 5.0 のアンインストール
ms.openlocfilehash: f562a4a4506bfdede6b23bd186b80f40cc9e45ca
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "71147862"
---
# <a name="uninstallation-instructions"></a><span data-ttu-id="44ab3-103">アンインストール手順</span><span class="sxs-lookup"><span data-stu-id="44ab3-103">Uninstallation Instructions</span></span>

## <a name="using-command-prompt"></a><span data-ttu-id="44ab3-104">コマンド プロンプトを使用</span><span class="sxs-lookup"><span data-stu-id="44ab3-104">Using Command Prompt</span></span>

1. <span data-ttu-id="44ab3-105">**コマンド プロンプト**を開きます。</span><span class="sxs-lookup"><span data-stu-id="44ab3-105">Open **Command Prompt.**</span></span>
2. <span data-ttu-id="44ab3-106">[Windows Update スタンドアロン ランチャー](https://support.microsoft.com/en-us/kb/934307)を次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="44ab3-106">Run the [Windows Update Standalone Launcher](https://support.microsoft.com/en-us/kb/934307) as shown below:</span></span>

<span data-ttu-id="44ab3-107">Windows Server 2012 R2 および Windows 8.1:</span><span class="sxs-lookup"><span data-stu-id="44ab3-107">On Windows Server 2012 R2 and Windows 8.1:</span></span>

```powershell
wusa /uninstall /kb:3134758
```

<span data-ttu-id="44ab3-108">Windows Server 2012:</span><span class="sxs-lookup"><span data-stu-id="44ab3-108">On Windows Server 2012:</span></span>

```powershell
wusa /uninstall /kb:3134759
```

<span data-ttu-id="44ab3-109">Windows Server 2008 R2 SP1 および Windows 7 SP1:</span><span class="sxs-lookup"><span data-stu-id="44ab3-109">On Windows Server 2008 R2 SP1 and Windows 7 SP1:</span></span>

```powershell
wusa /uninstall /kb:3134760
```

## <a name="using-control-panel"></a><span data-ttu-id="44ab3-110">コントロール パネルを使用</span><span class="sxs-lookup"><span data-stu-id="44ab3-110">Using Control Panel</span></span>

1. <span data-ttu-id="44ab3-111">**[コントロール パネル]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="44ab3-111">Open **Control Panel.**</span></span>
2. <span data-ttu-id="44ab3-112">**[プログラム]** を開き、 **[プログラムのアンインストール]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="44ab3-112">Open **Programs**, then open **Uninstall a program.**</span></span>
3. <span data-ttu-id="44ab3-113">**[インストールされた更新プログラムを表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="44ab3-113">Click **View installed updates.**</span></span>
4. <span data-ttu-id="44ab3-114">インストールされた更新プログラムの一覧から **[Windows Management Framework 5.0]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="44ab3-114">Select **Windows Management Framework 5.0** from the list of installed updates.</span></span> <span data-ttu-id="44ab3-115">これは *KB3134758*、*KB3134759*、または *KB3134760* に対応しています。</span><span class="sxs-lookup"><span data-stu-id="44ab3-115">This corresponds to *KB3134758*, *KB3134759*, or *KB3134760*.</span></span> <span data-ttu-id="44ab3-116">**[アンインストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="44ab3-116">Click **Uninstall.**</span></span>
