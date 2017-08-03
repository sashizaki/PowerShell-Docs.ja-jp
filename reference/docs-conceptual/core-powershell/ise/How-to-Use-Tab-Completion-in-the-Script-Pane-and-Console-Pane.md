---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "スクリプト ウィンドウとコンソール ウィンドウでタブ補完を使用する方法"
ms.assetid: 3b752c3c-0bd0-4eca-a2d3-2d5a37fd9d84
ms.openlocfilehash: ba8d0af7e7fc0f1df9f65116be899097b0a97a3c
ms.sourcegitcommit: 598b7835046577841aea2211d613bb8513271a8b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2017
---
# <a name="how-to-use-tab-completion-in-the-script-pane-and-console-pane"></a>スクリプト ウィンドウとコンソール ウィンドウでタブ補完を使用する方法
タブ補完は、スクリプト ウィンドウまたはコマンド ウィンドウで入力するときに、自動的に提供される支援機能です。 この機能を活用するには、次の手順を実行します。

## <a name="to-automatically-complete-a-command-entry"></a>コマンドの入力を自動的に補完するには
コマンド ウィンドウまたはスクリプト ウィンドウでは、コマンドのいくつかの文字を入力し、Tab キーを押すと、目的の補完テキストを選択できます。 最初に入力したテキストで始まる項目が複数ある場合は、目的の項目が表示されるまで Tab キーを何回か押します。 タブ補完は、コマンドレット名、パラメーター名、変数名、オブジェクトのプロパティ名、またはファイルのパスを入力する場合に役立ちます。

> [!NOTE]
> スクリプト ウィンドウでは、.ps1、.psd1、.psm1 ファイルを編集している場合にのみ、Tab キーを押したときに自動的にコマンドが補完されます。 コマンド ウィンドウに入力する場合は、常にタブ補完が機能します。

## <a name="to-automatically-complete-a-cmdlet-parameter-entry"></a>コマンドレット パラメーターの入力を自動的に補完するには
コマンド ウィンドウまたはスクリプト ウィンドウで、コマンドレット名を入力し、その後にダッシュを入力し、次に Tab キーを押します。

たとえば、「`Get-Process -`」と入力し、Tab キーを何回か押すと、コマンドレットの各パラメーターが順番に表示されます。

## <a name="see-also"></a>参照
- [Windows PowerShell ISE の使用](using-the-windows-powershell-ise.md)
- [PowerShell タブを作成する方法](How-to-Create-a-PowerShell-Tab-in-Windows-PowerShell-ISE.md)

