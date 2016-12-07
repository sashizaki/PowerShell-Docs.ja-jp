---
title: "WMF 5.1 (プレビュー) の既知の問題"
ms.date: 2016-07-13
keywords: PowerShell, DSC, WMF
description: 
ms.topic: article
author: krishna
manager: dongill
ms.prod: powershell
ms.technology: WMF
ms.openlocfilehash: e2f19ed2fa2d2070860438b128513a463d95adae
ms.sourcegitcommit: c732e3ee6d2e0e9cd8c40105d6fbfd4d207b730d
translationtype: HT
---
# <a name="known-issues-in-wmf-51-preview"></a>WMF 5.1 (プレビュー) の既知の問題 #

> 注意: この情報は暫定版であり、変更することがあります。

## <a name="starting-powershell-shortcut-as-administrator"></a>PowerShell ショートカットを管理者として起動する
WMF がインストールされている場合に、管理者としてショートカットから PowerShell を起動しようとすると、"未定義のエラー" メッセージが表示されることがあります。
管理者以外でショートカットを開きなおすと、その後は管理者でも動作するようになります。

## <a name="pester"></a>Pester
このリリースでは、Nano Server で Pester を利用するとき、2 つの問題に注意する必要があります。

* Pester 自体にテストを実行すると、FULL CLR と CORE CLR の違いに起因し、エラーが発生します。 具体的には、Validate メソッドが XmlDocument 型で利用できません。 NUnit 出力ログのスキーマの検証を試行するテストが 6 つありますが、これでエラーが発生することが確認されています。 
* 現在、コード カバレッジの 1 つでエラーが発生します。*WindowsFeature* DSC リソースが Nano Server にないためです。 しかしながら、以上のエラーは一般的に無害であり、無視しても問題ありません。

## <a name="operation-validation"></a>操作検証 

* Microsoft.PowerShell.Operation.Validation モジュールの場合、ヘルプ URI が動作しないため、Update-Help は失敗します。

## <a name="dsc-after-uninstall-wmf"></a>WMF をアンインストールした後の DSC 
* WMF をアンインストールしても、構成フォルダーから DSC の MOF ドキュメントは削除されません。 MOF ドキュメントに、以前のシステムで使用できない新しいプロパティが含まれている場合、DSC は正しく機能しません。 この場合は、管理者特権の PowerShell コンソールから次のスクリプトを実行して、DSC の状態をクリーンアップします。
 ```PowerShell
    $PreviousDSCStates = @("$env:windir\system32\configuration\*.mof",
            "$env:windir\system32\configuration\*.mof.checksum",
            "$env:windir\system32\configuration\PartialConfiguration\*.mof",
            "$env:windir\system32\configuration\PartialConfiguration\*.mof.checksum"
           )

    $PreviousDSCStates | Remove-Item -ErrorAction SilentlyContinue -Verbose
 ```  