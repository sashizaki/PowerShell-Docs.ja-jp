---
ms.date: 12/19/2019
keywords: powershell,コマンドレット
title: Windows PowerShell ISE のアクセシビリティ
ms.openlocfilehash: e618daca98d76f767a8b60a3425760bfc0bd0f64
ms.sourcegitcommit: 058a6e86eac1b27ca57a11687019df98709ed709
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "75736285"
---
# <a name="accessibility-in-windows-powershell-ise"></a>Windows PowerShell ISE のアクセシビリティ

このトピックでは、Windows PowerShell Integrated Scripting Environment (ISE) の役に立つアクセシビリティ機能について説明します。

- [コンソール ウィンドウとスクリプト ウィンドウのサイズと場所を変更する方法](#how-to-change-the-size-and-location-of-the-console-and-script-panes)
- [テキストを編集するためのキーボード ショートカット](#keyboard-shortcuts-for-editing-text)
- [スクリプトを実行するためのキーボード ショートカット](#keyboard-shortcuts-for-running-scripts)
- [ビューをカスタマイズするためのキーボード ショートカット](#keyboard-shortcuts-for-customizing-the-view)
- [スクリプト デバッグ用のキーボード ショートカット](#keyboard-shortcuts-for-debugging-scripts)
- [Windows PowerShell のタブのキーボード ショートカット](#keyboard-shortcuts-for-windows-powershell-tabs)
- [開始および終了のキーボード ショートカット](#keyboard-shortcuts-for-starting-and-exiting)
- [コマンドレットを使用したブレークポイントの管理](#breakpoint-management)

Microsoft は、あらゆるユーザーの皆様に使いやすい製品とサービスをお届けできるように努めています。 以下のトピックでは、障碍のある方に Windows PowerShell ISE を快適にご利用いただくための機能、製品、およびサービスについて説明します。

Microsoft Windows のアクセシビリティ機能とユーティリティに加え、Windows PowerShell ISE には、身体に障碍のある方に役立つ次の機能が備わっています。

- キーボード ショートカット

- 構文を色分けした表や、[$psISE.Options](object-model/The-ISEOptions-Object.md) スクリプト オブジェクトを使用して他のいくつかの色の設定を変更する機能。

- テキスト サイズの変更

## <a name="how-to-change-the-size-and-location-of-the-console-and-script-panes"></a>コンソール ウィンドウとスクリプト ウィンドウのサイズと場所を変更する方法

コンソール ウィンドウとスクリプト ウィンドウのサイズと場所の変更は、次の手順で実行できます。 Windows PowerShell ISE を再び開いたときに、サイズと場所に加えた変更が保持されています。

### <a name="to-resize-the-script-pane-and-console-pane"></a>スクリプト ウィンドウとコンソール ウィンドウのサイズを変更するには

1. スクリプト ウィンドウとコンソール ウィンドウの間にある境界線の上にマウスのポインターを置いて止めます。

2. マウスのポインターが両方向矢印に変わったら、境界線をドラッグして、ウィンドウ サイズを変更します。

### <a name="to-move-the-script-pane-and-console-pane"></a>スクリプト ウィンドウとコンソール ウィンドウを移動するには

次のいずれかの操作を行います。

- スクリプト ウィンドウをコンソール ウィンドウの上に移動するには、<kbd>Ctrl</kbd> + <kbd>1</kbd> キーを押すか、ツール バーの **[スクリプト ウィンドウを上に表示]** アイコンをクリックするか、 **[表示]** メニューの **[スクリプト ウィンドウを上に表示]** をクリックします。

- スクリプト ウィンドウをコンソール ウィンドウの右側に移動するには、<kbd>Ctrl</kbd> + <kbd>2</kbd> キーを押すか、ツール バーの **[スクリプト ウィンドウを右側に表示]** アイコンをクリックするか、 **[表示]** メニューで **[スクリプト ウィンドウを右側に表示]** をクリックします。

- スクリプト ウィンドウを最大表示するには、<kbd>Ctrl</kbd> + <kbd>3</kbd> キーを押すか、ツール バーの **[スクリプト ウィンドウを最大表示]** アイコンをクリックするか、 **[表示]** メニューで **[スクリプト ウィンドウを最大表示]** をクリックします。

- コンソール ウィンドウを最大表示し、スクリプト ウィンドウを非表示にするには、タブの行の右端にある **[スクリプト ウィンドウを非表示にします]** アイコンをクリックするか、 **[表示]** メニューで **[スクリプト ウィンドウを表示]** メニュー オプションをクリックして選択解除します。

- コンソール ウィンドウを最大表示しているときに、スクリプト ウィンドウを表示するには、タブの行の右端にある **[スクリプト ウィンドウを表示]** アイコンをクリックするか、 **[表示]** メニューで **[スクリプト ウィンドウを表示]** メニュー オプションをクリックして選びます。

## <a name="keyboard-shortcuts-for-editing-text"></a>テキストを編集するためのキーボード ショートカット

テキストを編集するときに、次のキーボード ショートカットを使用できます。

|           アクション            |       キーボード ショートカット       |          使用する場所           |
| --------------------------- | ------------------------------ | ------------------------- |
| **Copy** に設定する必要があります                    | <kbd>Ctrl</kbd> + <kbd>C</kbd>   | スクリプト ウィンドウ、コンソール ウィンドウ |
| **切り取り**                     | <kbd>Ctrl</kbd> + <kbd>X</kbd>   | スクリプト ウィンドウ、コンソール ウィンドウ |
| **スクリプト内を検索**          | <kbd>Ctrl</kbd> + <kbd>F</kbd>   | スクリプト ウィンドウ               |
| **スクリプト内で次を検索**     | <kbd>F3</kbd>                  | スクリプト ウィンドウ               |
| **スクリプト内で前を検索** | <kbd>Shift</kbd> + <kbd>F3</kbd> | スクリプト ウィンドウ               |
| **[貼り付け]**                   | <kbd>Ctrl</kbd> + <kbd>V</kbd>   | スクリプト ウィンドウ、コンソール ウィンドウ |
| **やり直す**                    | <kbd>Ctrl</kbd> + <kbd>Y</kbd>   | スクリプト ウィンドウ、コンソール ウィンドウ |
| **スクリプト内で置換**       | <kbd>Ctrl</kbd> + <kbd>H</kbd>   | スクリプト ウィンドウ               |
| **および**                    | <kbd>Ctrl</kbd> + <kbd>S</kbd>   | スクリプト ウィンドウ               |
| **[すべて選択]**              | <kbd>Ctrl</kbd> + <kbd>A</kbd>   | スクリプト ウィンドウ、コンソール ウィンドウ |
| **元に戻す**                    | <kbd>Ctrl</kbd> + <kbd>Z</kbd>   | スクリプト ウィンドウ、コンソール ウィンドウ |

## <a name="keyboard-shortcuts-for-running-scripts"></a>スクリプトを実行するためのキーボード ショートカット

スクリプト ウィンドウでスクリプトを実行する場合、次のキーボード ショートカットを使用できます。

|            アクション            |                                                                                                     キーボード ショートカット                                                                                                      |
| ---------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **[新規作成]**                      | <kbd>Ctrl</kbd> + <kbd>N</kbd>                                                                                                                                                                                               |
| **[ファイル]**                     | <kbd>Ctrl</kbd> + <kbd>O</kbd>                                                                                                                                                                                               |
| **[実行]**                      | <kbd>F5</kbd>                                                                                                                                                                                                              |
| **選択範囲の実行**            | <kbd>F8</kbd>                                                                                                                                                                                                              |
| **実行を中止**           | <kbd>Ctrl</kbd> + <kbd>Break</kbd>。 コンテキストが明確な場合 (選ばれているテキストがない場合)、<kbd>Ctrl</kbd> + <kbd>C</kbd> キーを使用できます。                                                                               |
| **タブ移動** (次のスクリプトへ)     | <kbd>Ctrl</kbd> + <kbd>Tab</kbd> **注:** 次のスクリプトへのタブは、PowerShell タブを 1 つ開いている場合、または PowerShell タブを複数開いている場合にだけ機能します。ただし、フォーカスはスクリプト ウィンドウにあります。                |
| **タブ移動** (前のスクリプトへ) | <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>Tab</kbd> **注:** 前のスクリプトへのタブは、PowerShell タブを 1 つだけ開いている場合、または PowerShell タブを複数開いている場合に機能します。フォーカスはスクリプト ウィンドウにあります。 |

## <a name="keyboard-shortcuts-for-customizing-the-view"></a>ビューをカスタマイズするためのキーボード ショートカット

次のキーボード ショートカットを使用して、Windows PowerShell ISE のビューをカスタマイズできます。 アプリケーションのすべてのウィンドウから利用可能です。

|           アクション           |         キーボード ショートカット        |
| -------------------------- | -------------------------------- |
| **コンソール ウィンドウに移動**     | <kbd>Ctrl</kbd> + <kbd>D</kbd>     |
| **スクリプト ウィンドウに移動**      | <kbd>Ctrl</kbd> + <kbd>I</kbd>     |
| **スクリプト ウィンドウを表示**       | <kbd>Ctrl</kbd> + <kbd>R</kbd>     |
| **スクリプト ウィンドウを非表示にする**       | <kbd>Ctrl</kbd> + <kbd>R</kbd>     |
| **スクリプト ウィンドウを上に移動**    | <kbd>Ctrl</kbd> + <kbd>1</kbd>     |
| **スクリプト ウィンドウを右に移動** | <kbd>Ctrl</kbd> + <kbd>2</kbd>     |
| **スクリプト ウィンドウを最大表示**   | <kbd>Ctrl</kbd> + <kbd>3</kbd>     |
| **拡大**                | <kbd>Ctrl</kbd> + <kbd>プラス記号</kbd>  |
| **縮小**               | <kbd>Ctrl</kbd> + <kbd>マイナス記号</kbd> |

## <a name="keyboard-shortcuts-for-debugging-scripts"></a>スクリプト デバッグ用のキーボード ショートカット

スクリプトをデバッグするときに、次のキーボード ショートカットを使用できます。

|           アクション           |               キーボード ショートカット                |                使用する場所                |
| -------------------------- | ---------------------------------------------- | ------------------------------------ |
| **実行/続行**           | <kbd>F5</kbd>                                  | スクリプト ウィンドウ、スクリプトのデバッグ時 |
| **ステップ イン**              | <kbd>F11</kbd>                                 | スクリプト ウィンドウ、スクリプトのデバッグ時 |
| **ステップ オーバー**              | <kbd>F10</kbd>                                 | スクリプト ウィンドウ、スクリプトのデバッグ時 |
| **ステップ アウト**               | <kbd>Shift</kbd> + <kbd>F11</kbd>                | スクリプト ウィンドウ、スクリプトのデバッグ時 |
| **呼び出し履歴の表示**     | <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>D</kbd>  | スクリプト ウィンドウ、スクリプトのデバッグ時 |
| **ブレークポイントの一覧表示**       | <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>L</kbd>  | スクリプト ウィンドウ、スクリプトのデバッグ時 |
| **ブレークポイントの設定/解除**      | <kbd>F9</kbd>                                  | スクリプト ウィンドウ、スクリプトのデバッグ時 |
| **すべてのブレークポイントの削除** | <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>F9</kbd> | スクリプト ウィンドウ、スクリプトのデバッグ時 |
| **デバッガーの停止**          | <kbd>Shift</kbd> + <kbd>F5</kbd>                 | スクリプト ウィンドウ、スクリプトのデバッグ時 |

> [!NOTE]
> Windows PowerShell ISE でスクリプトをデバッグする場合は、Windows PowerShell コンソール用に設計されたキーボード ショートカットも使用できます。 それらのショートカットを使用するには、コンソール ウィンドウでショートカットを入力してから Enter キーを押します。

|                 アクション                  |      キーボード ショートカット       |                使用する場所                 |
| --------------------------------------- | ---------------------------- | ------------------------------------- |
| **続行**                            | <kbd>C</kbd>                 | コンソール ウィンドウ、スクリプトのデバッグ時 |
| **ステップ イン**                           | <kbd>S</kbd>                 | コンソール ウィンドウ、スクリプトのデバッグ時 |
| **ステップ オーバー**                           | <kbd>V</kbd>                 | コンソール ウィンドウ、スクリプトのデバッグ時 |
| **ステップ アウト**                            | <kbd>O</kbd>                 | コンソール ウィンドウ、スクリプトのデバッグ時 |
| **最後のコマンドを繰り返す** (ステップイン/オーバー) | <kbd>Enter</kbd>             | コンソール ウィンドウ、スクリプトのデバッグ時 |
| **呼び出し履歴の表示**                  | <kbd>K</kbd>                 | コンソール ウィンドウ、スクリプトのデバッグ時 |
| **デバッグの停止**                      | <kbd>Q</kbd>                 | コンソール ウィンドウ、スクリプトのデバッグ時 |
| **スクリプトの一覧表示**                     | <kbd>L</kbd>                 | コンソール ウィンドウ、スクリプトのデバッグ時 |
| **コンソールのデバッグ コマンドの表示**  | <kbd>H</kbd> または <kbd>?</kbd> | コンソール ウィンドウ、スクリプトのデバッグ時 |

## <a name="keyboard-shortcuts-for-windows-powershell-tabs"></a>Windows PowerShell のタブのキーボード ショートカット

Windows PowerShell のタブを使用するときに、次のキーボード ショートカットを使用できます。

|             アクション              |                                 キーボード ショートカット                                  |
| ------------------------------- | ---------------------------------------------------------------------------------- |
| **PowerShell タブを閉じる**        | <kbd>Ctrl</kbd> + <kbd>W</kbd>                                                       |
| **PowerShell タブの新規作成**          | <kbd>Ctrl</kbd> + <kbd>T</kbd>                                                       |
| **前の PowerShell タブ**     | <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>Tab</kbd> (任意の PowerShell タブ上で開いているファイルがない場合にのみ)                 |
| **次の Windows PowerShell タブ** | <kbd>Ctrl</kbd> + <kbd>Tab</kbd> (任意の PowerShell タブ上で開いているファイルがない場合にのみ) |

## <a name="keyboard-shortcuts-for-starting-and-exiting"></a>開始および終了のキーボード ショートカット

次のキーボード ショートカットを使用して、Windows PowerShell コンソール (**PowerShell.exe**) を起動したり、Windows PowerShell ISE を終了したりできます。

|                        アクション                         |               キーボード ショートカット               |
| ----------------------------------------------------- | --------------------------------------------- |
| **終了**                                              | <kbd>Alt</kbd> + <kbd>F4</kbd>                  |
| **PowerShell.exe を起動** (Windows PowerShell コンソール) | <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>P</kbd> |

## <a name="breakpoint-management"></a>ブレークポイントの管理

視覚に障碍のある方のために、ブレークポイントを管理するコマンドレット ([Get-PSBreakpoint](/reference/6/Microsoft.PowerShell.Utility/Get-PSBreakpoint.md)、[Set-PSBreakpoint](/reference/6/Microsoft.PowerShell.Utility/Set-PSBreakpoint.md) など) を通じて、ブレークポイント情報をご利用いただけます。
詳しくは、「[Windows PowerShell ISE でスクリプトをデバッグする方法](How-to-Debug-Scripts-in-Windows-PowerShell-ISE.md)」の「ブレークポイントを管理する方法」をご覧ください。

## <a name="see-also"></a>参照

[Windows PowerShell ISE の紹介](Introducing-the-Windows-PowerShell-ISE.md)
