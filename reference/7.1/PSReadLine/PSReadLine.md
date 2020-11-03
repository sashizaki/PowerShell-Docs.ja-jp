---
Download Help Link: https://aka.ms/powershell71-help
Help Version: 7.1.0.0
keywords: powershell
Locale: en-US
Module Guid: 5714753b-2afd-4492-a5fd-01d9e2cff8b5
Module Name: PSReadLine
ms.date: 02/10/2020
schema: 2.0.0
title: PSReadLine
ms.openlocfilehash: a404461e2b92f269d581b18c3ebe7643aa86c3a4
ms.sourcegitcommit: 9d95532afe81c235c8094eae28ab84b2f77f8c48
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2020
ms.locfileid: "93220392"
---
# PSReadLine モジュール

## 説明

PSReadLine モジュールには、PowerShell でコマンドライン編集環境をカスタマイズできるコマンドレットが含まれています。 これらの記事では、PSReadLine v2.0 について説明しています。 このバージョンは、PowerShell v6 と Windows 10 10 月2018更新プログラム (ビルド 1809) に付属しています。

> [!NOTE]
> PowerShell 7.0 以降では、スクリーンリーダープログラムが検出されると、PowerShell は Windows で PSReadLine の自動読み込みをスキップします。 現在、PSReadLine は、スクリーンリーダーではうまく機能しません。 Windows での PowerShell 7.0 の既定の表示と書式設定は正常に機能します。 必要に応じて、モジュールを手動で読み込むことができます。

## PSReadLine コマンドレット

### [PSConsoleHostReadLine](PSConsoleHostReadLine.md)
PSReadLine のメインエントリポイント。

### [Get-PSReadLineKeyHandler](Get-PSReadLineKeyHandler.md)
PSReadLine モジュールのバインドされたキー関数を取得します。

### [Get-PSReadLineOption](Get-PSReadLineOption.md)
構成可能なオプションの値を取得します。

### [PSConsoleHostReadLine](PSConsoleHostReadLine.md)
この関数は、PSReadLine のメインエントリポイントです。

### [-PSReadLineKeyHandler を削除します。](Remove-PSReadLineKeyHandler.md)
キーバインドを削除します。

### [設定-PSReadLineKeyHandler](Set-PSReadLineKeyHandler.md)
ユーザー定義キーまたは PSReadLine キーハンドラー関数にキーをバインドします。

### [設定-PSReadLineOption](Set-PSReadLineOption.md)
**Psreadline** でのコマンドライン編集の動作をカスタマイズします。

