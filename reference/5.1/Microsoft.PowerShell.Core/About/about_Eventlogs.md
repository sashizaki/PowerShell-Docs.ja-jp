---
description: Windows powershell では、windows PowerShell イベントを記録するために、"Windows PowerShell" という名前の Windows イベントログが作成されます。 このログを表示するにはイベントビューアーまたはコマンドレットなどのイベントを取得するコマンドレットを使用し `Get-EventLog` ます。 既定では、Windows PowerShell エンジンとプロバイダーのイベントはイベントログに記録されますが、イベントログのユーザー設定変数を使用してイベントログをカスタマイズできます。 たとえば、Windows PowerShell コマンドに関するイベントを追加できます。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 11/27/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_eventlogs?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Eventlogs
ms.openlocfilehash: eb92333c6a6e220e287dcbec1441d2d05aa9275b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223507"
---
# <a name="about-eventlogs"></a>Eventlogs について

## <a name="short-description"></a>簡単な説明

Windows powershell では、windows PowerShell イベントを記録するために、"Windows PowerShell" という名前の Windows イベントログが作成されます。 このログを表示するにはイベントビューアーまたはコマンドレットなどのイベントを取得するコマンドレットを使用し `Get-EventLog` ます。 既定では、Windows PowerShell エンジンとプロバイダーのイベントはイベントログに記録されますが、イベントログのユーザー設定変数を使用してイベントログをカスタマイズできます。 たとえば、Windows PowerShell コマンドに関するイベントを追加できます。

## <a name="long-description"></a>長い説明

Windows powershell イベントログには、プログラムエンジンの起動と停止、Windows PowerShell プロバイダーの起動と停止など、Windows PowerShell の操作の詳細が記録されます。 Windows PowerShell コマンドの詳細をログに記録することもできます。

Windows PowerShell イベントログは、[アプリケーションとサービスログ] グループにあります。 Windows PowerShell ログは、Windows イベントのテクノロジを使用しない従来のイベントログです。 ログを表示するには、などの従来のイベントログ用に設計されたコマンドレットを使用し `Get-EventLog` ます。

## <a name="viewing-the-windows-powershell-event-log"></a>Windows PowerShell イベントログの表示

Windows PowerShell イベントログは、イベントビューアーで、または `Get-EventLog` コマンドレットとコマンドレットを使用して表示でき `Get-WmiObject` ます。 Windows PowerShell ログの内容を表示するには、次のように入力します。

```powershell
Get-EventLog -LogName "Windows PowerShell"
```

イベントとそのプロパティを調べるには、 `Sort-Object` コマンドレット、 `Group-Object` コマンドレット、および `Format` 動詞 (コマンドレット) を含むコマンド `Format` レットを使用します。

たとえば、イベント ID でグループ化されたログ内のイベントを表示するには、次のように入力します。

```powershell
Get-EventLog "Windows PowerShell" | Format-Table -GroupBy EventID
```

または、次のように入力します。

```powershell
Get-EventLog "Windows PowerShell" |
  Sort-Object EventID |
  Group-Object EventID
```

すべてのクラシックイベントログを表示するには、次のように入力します。

```powershell
Get-EventLog -List
```

また、コマンドレットを使用して、イベント `Get-WmiObject` 関連の Windows Management Instrumentation (WMI) クラスを使用してイベントログを確認することもできます。 たとえば、イベントログファイルのすべてのプロパティを表示するには、次のように入力します。

```powershell
Get-WmiObject Win32_NTEventlogFile |
  where LogFileName -EQ "Windows PowerShell" |
  Format-List -Property *
```

Win32 イベント関連の WMI クラスを検索するには、次のように入力します。

```powershell
Get-WmiObject -List | where Name -Like "win32*event*"
```

詳細については、「Get-help Get-EventLog」と「Get-help Get-wmiobject」と入力してください。

## <a name="selecting-events-for-the-windows-powershell-event-log"></a>Windows PowerShell イベントログのイベントの選択

イベントログのユーザー設定変数を使用して、Windows PowerShell イベントログに記録されるイベントを特定できます。

イベントログのユーザー設定変数は6つあります。エンジン (Windows PowerShell プログラム)、プロバイダー、およびコマンドの3つの各ログコンポーネントに対して、2つの変数があります。 LifeCycleEvent 変数は、通常の開始イベントと停止イベントをログに記録します。 正常性変数は、エラーイベントをログに記録します。

次の表に、イベントログのユーザー設定変数を示します。

|変数                  |説明                                    |
|--------------------------|-----------------------------------------------|
|$LogEngineLifeCycleEvent  |PowerShell の開始と停止をログに記録します。          |
|$LogEngineHealthEvent     |PowerShell プログラムエラーのログを記録します                 |
|$LogProviderLifeCycleEvent|PowerShell プロバイダーの開始と停止をログに記録します。|
|$LogProviderHealthEvent   |PowerShell プロバイダーのエラーをログに記録します                |
|$LogCommandLifeCycleEvent |コマンドの開始と完了をログに記録します。   |
|$LogCommandHealthEvent    |ログコマンドエラー                            |

(Windows PowerShell プロバイダーの詳細については、「 [about_Providers](about_Providers.md)」を参照してください)。

既定では、次のイベントの種類のみが有効になっています。

* $LogEngineLifeCycleEvent
* $LogEngineHealthEvent
* $LogProviderLifeCycleEvent
* $LogProviderHealthEvent

イベントの種類を有効にするには、そのイベントの種類のユーザー設定変数を $true に設定します。 たとえば、コマンドのライフサイクルイベントを有効にするには、次のように入力します。

```powershell
$LogCommandLifeCycleEvent
```

または、次のように入力します。

```powershell
$LogCommandLifeCycleEvent = $true
```

イベントの種類を無効にするには、そのイベントの種類のユーザー設定変数を $false に設定します。 たとえば、コマンドのライフサイクルイベントを無効にするには、次のように入力します。

```powershell
$LogProviderLifeCycleEvent = $false
```

Windows PowerShell エンジンとコアプロバイダーが起動していることを示すイベントを除き、任意のイベントを無効にすることができます。 これらのイベントは、Windows PowerShell プロファイルが実行される前、およびホストプログラムがコマンドを受け入れる準備が整う前に生成されます。

変数の設定は、現在の Windows PowerShell セッションに対してのみ適用されます。
すべての Windows PowerShell セッションに適用するには、Windows powershell プロファイルに追加します。

## <a name="logging-module-events"></a>モジュールイベントのログ記録

Windows PowerShell 3.0 以降では、Windows PowerShell モジュールおよびスナップインのコマンドレットと関数の実行イベントを記録できます。これを行うには、モジュールとスナップインの LogPipelineExecutionDetails プロパティを TRUE に設定します。 Windows PowerShell 2.0 では、この機能はスナップインに対してのみ使用できます。

LogPipelineExecutionDetails プロパティの値が TRUE () の場合 `$true` 、Windows powershell は、セッション内のコマンドレットと関数の実行イベントをイベントビューアーの Windows powershell ログに書き込みます。 この設定は、現在のセッションでのみ有効です。

モジュール内のコマンドレットと関数の実行イベントのログ記録を有効にするには、次のコマンドシーケンスを使用します。

```powershell
Import-Module <ModuleName>
$m = Get-Module <ModuleName>
$m.LogPipelineExecutionDetails = $true
```

スナップインでコマンドレットの実行イベントのログ記録を有効にするには、次のコマンドシーケンスを使用します。

```powershell
$m = Get-PSSnapin <SnapInName> [-Registered]
$m.LogPipelineExecutionDetails = $True
```

ログ記録を無効にするには、同じコマンドシーケンスを使用して、プロパティ値を FALSE () に設定し `$false` ます。

また、[モジュールのログ記録を有効にする] グループポリシー設定を使用して、モジュールおよびスナップインのログ記録を有効または無効にすることもできます。 ポリシー値には、モジュール名とスナップイン名の一覧が含まれています。 ワイルドカードを利用できます。

モジュールに [モジュールログをオンにする] が設定されている場合、モジュールの LogPipelineExecutionDetails プロパティの値はすべてのセッションで TRUE に設定され、変更することはできません。

[モジュールログを有効にする] グループポリシー設定は、次のグループポリシーパスにあります。

```
Computer Configuration\
  Administrative Templates\
    Windows Components\
     Windows PowerShell

User Configuration\
  Administrative Templates\
    Windows Components\
      Windows PowerShell
```

ユーザー構成ポリシーは、コンピューターの構成ポリシーよりも優先されます。両方のポリシーは、モジュールとスナップインの LogPipelineExecutionDetails プロパティの値よりも優先されます。

このグループポリシー設定の詳細については、「 [about_Group_Policy_Settings](about_Group_Policy_Settings.md)」を参照してください。

## <a name="security-and-auditing"></a>セキュリティと監査

Windows PowerShell イベントログは、アクティビティを示すと共に、トラブルシューティングのための操作の詳細を提供するように設計されています。

ただし、ほとんどの Windows ベースのアプリケーションイベントログと同様に、Windows PowerShell イベントログはセキュリティで保護されていません。 セキュリティの監査や機密情報の記録には使用しないでください。

イベントログは、ユーザーが読んで理解できるように設計されています。 ユーザーは、ログの読み取りと書き込みを行うことができます。 悪意のあるユーザーが、ローカルコンピューターまたはリモートコンピューター上のイベントログを読み取り、偽のデータを記録して、それらのアクティビティのログ記録を防止する可能性があります。

## <a name="notes"></a>メモ

モジュールの作成者は、モジュールにログ機能を追加できます。 詳細については、「 [Windows PowerShell モジュールの記述](/powershell/scripting/developer/module/writing-a-windows-powershell-module)」を参照してください。

## <a name="see-also"></a>参照

[Get-EventLog](xref:Microsoft.PowerShell.Management.Get-EventLog)

[Get-WmiObject](xref:Microsoft.PowerShell.Management.Get-WmiObject)

[about_Group_Policy_Settings](about_Group_Policy_Settings.md)

[about_Preference_Variables](about_Preference_Variables.md)
