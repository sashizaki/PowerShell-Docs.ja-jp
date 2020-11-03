---
description: Windows RT 8.1 上の Windows PowerShell 4.0 の制限事項について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_windows_rt?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Windows_RT
ms.openlocfilehash: 323f06a7a0d8253417510503c1011ac02c20179f
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222435"
---
# <a name="about-windows-rt"></a>Windows RT について

## <a name="short-description"></a>概要

Windows RT 8.1 上の Windows PowerShell 4.0 の制限事項について説明します。

## <a name="long-description"></a>詳細説明

Windows RT 8.1 オペレーティングシステムは、Advanced RISC Machine (ARM) プロセッサを使用するコンピューターとデバイス (Microsoft Surface 2 など、コンピューターに付属しているオペレーティングシステム) にインストールされます。

Windows PowerShell 4.0 は Windows RT 8.1 に含まれています。 すべてのコマンドレット、プロバイダー、およびモジュール、および Windows PowerShell 2.0 以降のリリース向けに設計されたほとんどのスクリプトは、変更せずに Windows RT 8.1 上で動作します。

Windows RT 8.1 には一部の Windows 機能が含まれていないため、windows PowerShell の一部の機能が異なる動作をしたり、Windows RT ベースのデバイスで動作しないことがあります。 次の一覧では、その違いについて説明します。

- Windows PowerShell ISE はに含まれておらず、Windows RT 8.1 で実行することはできません。
  Windows PowerShell ISE には Windows Presentation Foundation が必要ですが、Windows RT 8.1 には含まれていません。

- 既定では、Windows PowerShell リモート処理と WinRM サービスは無効になっています。
  リモート処理を有効にするには、Enable-PSRemoting コマンドレットを実行します。 また、Set-Service コマンドレットを実行して、WinRM サービスのスタートアップの種類を [自動] または [自動 (遅延開始)] に設定します。

  リモート処理が無効になっている場合は、Windows PowerShell リモート処理を使用して他のコンピューターでコマンドを実行できますが、Windows RT デバイスでコマンドを実行することはできません。 また、暗黙的なリモート処理 (つまり、コマンドレットまたはスクリプトに組み込まれていて、追加されたパラメーターで明示的に要求されていないリモート処理)
  - Windows RT 8.1 で実行されている Windows PowerShell では機能しません。

- ドメインに参加しているコンピューティングと Kerberos 認証は、Windows RT 8.1 ではサポートされていません。 Windows PowerShell を使用してこれらの機能を追加または管理することはできません。

- Windows RT 8.1 でサポートされていない Microsoft .NET Framework クラスは、windows RT 8.1 の Windows PowerShell でもサポートされていません。

- Windows RT 8.1 ではトランザクションが有効になっていません。 トランザクションのコマンドレット (UseTransaction など) が正常に動作しない場合は、トランザクションのコマンドレットを実行します。

- Windows RT 8.1 デバイス上のすべての Windows PowerShell セッションでは、ConstrainedLanguage 言語モードが使用されます。 ConstrainedLanguage 言語モードは、ユーザーモードコードの整合性 (UMCI) に関連しています。 すべての Windows コマンドレットと Windows PowerShell 言語要素が許可されますが、ユーザーが Windows PowerShell を使用して UMCI 保護を回避または違反しないように、型を制限します。

ConstrainedLanguage language モードの詳細については、「 [about_Language_Modes](about_Language_Modes.md)」を参照してください。

## <a name="see-also"></a>関連項目

[about_Language_Modes](about_Language_Modes.md)

[about_Remote](about_Remote.md)

[about_Windows_PowerShell_ISE](about_Windows_PowerShell_ISE.md)
