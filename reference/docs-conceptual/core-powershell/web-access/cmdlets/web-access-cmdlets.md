---
ms.topic: reference
keywords: PowerShell, コマンドレット
ms.date: 12/12/2016
title: PowerShell Web Access のコマンドレット
ms.openlocfilehash: 34a7a01f154b2e43416dfe8ea43d4d8e937816d9
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2018
ms.locfileid: "34188022"
---
# <a name="windows-powershell-web-access-cmdlets"></a>Windows PowerShell Web Access のコマンドレット

このリファレンスでは、Windows PowerShell® Web Access 固有のコマンドレットの説明と構文について情報を提供します。 コマンドレットの先頭の動詞に基づいて、アルファベット順に記載しています。

## <a name="add-pswaauthorizationruleadd-pswaauthorizationrulemd"></a>[Add-PswaAuthorizationRule](add-pswaauthorizationrule.md)

Windows PowerShell® Web Access 承認規則のセットに新しい承認規則を追加します。

## <a name="get-pswaauthorizationruleget-pswaauthorizationrulemd"></a>[Get-PswaAuthorizationRule](get-pswaauthorizationrule.md)

Windows PowerShell Web Access の承認規則のセットを返します。

## <a name="install-pswawebapplicationinstall-pswawebapplicationmd"></a>[Install-PswaWebApplication](install-pswawebapplication.md)

IIS で Windows PowerShell Web Access Web アプリケーションを構成します。

## <a name="remove-pswaauthorizationruleremove-pswaauthorizationrulemd"></a>[Remove-PswaAuthorizationRule](remove-pswaauthorizationrule.md)

指定された承認規則を Windows PowerShell Web Access から削除します。

## <a name="test-pswaauthorizationruletest-pswaauthorizationrulemd"></a>[Test-PswaAuthorizationRule](test-pswaauthorizationrule.md)

特定のユーザー、コンピューター、エンドポイント アクセス要求が承認されていることを確認する承認規則をテストします。

## <a name="uninstall-pswawebapplicationuninstall-pswawebapplicationmd"></a>[Uninstall-PswaWebApplication](uninstall-pswawebapplication.md)

IIS から Windows PowerShell Web アプリケーションをアンインストールします。

>**注**:
>
>利用可能なコマンドレットすべての一覧を表示するには、
>
> `Get-Command –Module PowerShellWebAccess` コマンドレットを使用します。

いずれかのコマンドレット、またはその構文の詳細について知るには、`Get-Help `*&lt;cmdlet name&gt;* コマンドレットを使用します。この *&lt;cmdlet name&gt;* には、調べたいコマンドレット名を指定します。

詳細については、次のコマンドレットを実行してください。

- `Get-Help `*&lt;コマンドレット名&gt;*` -Detailed`
- `Get-Help `*&lt;コマンドレット名&gt;*` -Examples`
- `Get-Help `*&lt;コマンドレット名&gt;*` -Full`

### <a name="more-information"></a>詳細情報

PowerShell Web Access の詳細については、以下を参照してください。

- [Windows PowerShell Web Access のインストールと使用](../install-and-use-windows-powershell-web-access.md)