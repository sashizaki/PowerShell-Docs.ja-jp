---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/start-transaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Transaction
ms.openlocfilehash: 53be131f45f15e5d2053b183040dc7b3dca4a14c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214392"
---
# Start-Transaction

## 概要
トランザクションを開始します。

## SYNTAX

```
Start-Transaction [-Timeout <Int32>] [-Independent] [-RollbackPreference <RollbackSeverity>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## Description
**開始トランザクション** コマンドレットは、1つの単位として管理される一連のコマンドであるトランザクションを開始します。
トランザクションは、完了するかコミットすることができます。
または、トランザクションによって変更されたデータが元の状態に復元されるように、完全に元に戻したり、ロールバックしたりすることもできます。
1 つのトランザクション内の一連のコマンドは 1 つの単位として管理されるので、コマンドはすべてコミットされるか、すべてロールバックされるかのいずれかとなります。

既定では、トランザクション内のいずれかのコマンドがエラーを生成すると、トランザクションは自動的にロールバックされます。
*RollbackPreference* パラメーターを使用して、この動作を変更できます。

トランザクションで使用するコマンドレットは、トランザクションをサポートするように設計されている必要があります。
トランザクションをサポートするコマンドレットには、 *UseTransaction* パラメーターがあります。
1 つのプロバイダーで複数のトランザクションを実行するには、プロバイダーがトランザクションをサポートする必要があります。
Windows Vista 以降のバージョンの windows オペレーティングシステムの Windows PowerShell レジストリプロバイダーは、トランザクションをサポートしています。
また、 **TransactedString** クラスを使用して、windows PowerShell をサポートする任意のバージョンの windows システムのトランザクションに式を含めることもできます。
他の Windows PowerShell プロバイダーもトランザクションをサポートできます。

一度に複数のトランザクションを有効にすることはできません。
トランザクションの進行中に新しい独立したトランザクションを開始すると、新しいトランザクションがアクティブなトランザクションになり、元のトランザクションを変更する前に、新しいトランザクションをコミットまたはロールバックする必要があります。

**開始トランザクション** コマンドレットは、Windows PowerShell のトランザクション機能をサポートする一連のコマンドレットの1つです。
詳細については、「about_Transactions」を参照してください。

## 例

### 例 1: トランザクションを開始してロールバックする

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany" -UseTransaction
PS HKCU:\software> New-ItemProperty "ContosoCompany" -Name "MyKey" -Value 123 -UseTransaction
PS HKCU:\software> Undo-Transaction
```

これらのコマンドは、トランザクションを開始してからロールバックします。
トランザクションはロールバックされるので、レジストリは変更されません。

### 例 2: トランザクションを開始して完了する

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany" -UseTransaction
PS HKCU:\software> New-ItemProperty "ContosoCompany" -Name "MyKey" -Value 123 -UseTransaction
PS HKCU:\software> Complete-Transaction
```

これらのコマンドは、トランザクションを開始して完了します。
**Complete Transaction** コマンドが使用されるまで、レジストリは変更されません。

### 例 3: 異なるロールバック設定を使用する

```
PS C:\> cd HKCU:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item -Path "NoPath" -Name "ContosoCompany" -UseTransaction
PS HKCU:\software> New-Item -Path . -Name "ContosoCompany" -UseTransaction
PS HKCU:\software> Start-Transaction -RollbackPreference never
PS HKCU:\software> New-Item -Path "NoPath" -Name "ContosoCompany" -UseTransaction
PS HKCU:\software> New-Item -Path . -Name "ContosoCompany" -UseTransaction

# Start-Transaction (-rollbackpreference error)

PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item -Path "NoPath" -Name "ContosoCompany" -UseTransaction
New-Item : The registry key at the specified path does not exist.
At line:1 char:9
+ new-item <<<<  -Path NoPath -Name ContosoCompany -UseTransaction

PS HKCU:\software> New-Item -Path . -Name "Contoso" -UseTransaction

New-Item : Cannot use transaction. The transaction has been rolled back or has timed out.
At line:1 char:9
+ new-item <<<<  -Path . -Name ContosoCompany -UseTransaction

# Start-Transaction (-rollbackpreference never)

PS HKCU:\software> Start-Transaction -RollbackPreference never
PS HKCU:\software> New-Item -Path "NoPath" -Name "ContosoCompany" -UseTransaction

New-Item : The registry key at the specified path does not exist.
At line:1 char:9
+ new-item <<<<  -Path NoPath -Name "ContosoCompany" -UseTransaction
PS HKCU:\software> New-Item -Path . -Name "ContosoCompany" -UseTransaction

Hive: HKEY_CURRENT_USER\Software
SKC  VC Name                           Property
---  -- ----                           --------
0   0 ContosoCompany                 {}
PS HKCU:\Software> Complete-Transaction

# Succeeds
```

この例では、 *RollbackPreference* パラメーター値を変更した場合の影響を示します。

最初のコマンドセット **では、** *RollbackPreference* は使用されません。
その結果、既定値 (Error) が使用されます。
トランザクションコマンドでエラーが発生した場合 (指定されたパスが存在しない場合)、トランザクションは自動的にロールバックされます。

2番目のコマンドのセット **では、** *RollbackPreference* は、値が Never であることを使用します。
その結果、トランザクション コマンドでエラーが発生しても、トランザクションは有効のままであり、正常に完了できます。

ほとんどのトランザクションはエラーなしで実行する必要があるため、通常は *RollbackPreference* の既定値を使用することをお勧めします。

### 例 4: トランザクションの実行中にこのコマンドレットを使用する

```
PS C:\> cd HKCU:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany" -UseTransaction
PS HKCU:\software> Start-Transaction
PS HKCU:\software> Get-Transaction
PS HKCU:\software> New-Item "ContosoCompany2" -UseTransaction
PS HKCU:\software> Complete-Transaction
PS HKCU:\software> Complete-Transaction
PS HKCU:\Software> Get-Transaction
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                2                 Active
```

この例は、トランザクションの実行中に **開始トランザクション** を使用した場合の影響を示しています。
結果は、進行中のトランザクションを追加した場合とほぼ同じです。

これは簡略化されたコマンドですが、このシナリオは、トランザクションが完全なトランザクションを含むスクリプトを実行する場合に頻繁に発生します。

最初の **トランザクションの開始** コマンドは、トランザクションを開始します。
最初の **新しい項目** のコマンドは、トランザクションの一部です。

2番目の **トランザクションの開始** コマンドは、新しいサブスクライバーをトランザクションに追加します。
次に、 **Get transaction** コマンドで、サブスクライバー数が2のトランザクションが返されるようになりました。
2番目の **新しい項目** コマンドは、同じトランザクションの一部です。

トランザクション全体が完了するまで、レジストリは変更されません。
トランザクションを完了するには、サブスクライバーごとに1つずつ、2つの **トランザクションの完全** なコマンドを入力する必要があります。
トランザクションを任意の時点でロールバックすると、すべてのトランザクションが両方のサブスクライバーに対してロールバックされます。

### 例 5: 1 つの処理中に独立したトランザクションを開始する

```
PS C:\> cd HKCU:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany" -UseTransaction
PS HKCU:\software> Start-Transaction -Independent
PS HKCU:\software> Get-Transaction
PS HKCU:\software> Undo-Transaction
PS HKCU:\software> New-ItemProperty -Path "ContosoCompany" -Name "MyKey" -Value 123 -UseTransaction
PS HKCU:\software> Complete-Transaction
PS HKCU:\software> dir contoso*
PS HKCU:\Software> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
PS HKCU:\software> Undo-Transaction
PS HKCU:\software> New-ItemProperty -Path "ContosoCompany" -Name "MyKey" -Value 123 -UseTransaction
MyKey
-----
123
PS HKCU:\software> Complete-Transaction
PS HKCU:\software> dir contoso*
Hive: HKEY_CURRENT_USER\Software
SKC  VC Name                           Property
---  -- ----                           --------
0   1 MyCompany                      {MyKey}
```

この例では、別のトランザクションの進行中にトランザクションを開始するために、 **開始トランザクション** の *独立* パラメーターを使用した場合の効果を示します。
この場合、新しいトランザクションは、元のトランザクションに影響を及ぼすことなくロールバックされます。

これらのトランザクションは論理的に独立していますが、一度に複数のトランザクションを有効にすることはできないので、元のトランザクションに対する作業を再開するには、その前に新しいトランザクションをロールバックするかコミットする必要があります。

最初のコマンド セットを実行すると、トランザクションが開始されます。
**新しい項目** のコマンドは、最初のトランザクションの一部です。

2番目のコマンドセットでは、 **トランザクションの開始** コマンドは、 *独立* したパラメーターを使用します。
次に示す **Get transaction** コマンドは、アクティブなトランザクションのトランザクションオブジェクトを示しています。これは、最新のものです。
サブスクライバーの数は1になります。これは、トランザクションが無関係であることを示しています。

トランザクションを **元に戻す** コマンドを使用してアクティブなトランザクションがロールバックされると、元のトランザクションは再びアクティブになります。

元のトランザクションの一部である **get-itemproperty** コマンドは、エラーが発生することなく終了します。また、元のトランザクションは、 **Complete transaction** コマンドを使用して完了できます。
その結果、レジストリが変更されます。

### 例 6: トランザクションの一部ではないコマンドを実行する

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany1" -UseTransaction
PS HKCU:\software> New-Item "ContosoCompany2"
PS HKCU:\software> New-Item "ContosoCompany3" -UseTransaction
PS HKCU:\software> dir contoso*
PS HKCU:\software> Complete-Transaction
PS HKCU:\software> dir contoso*
PS HKCU:\Software> dir contoso*

Hive: HKEY_CURRENT_USER\Software
SKC  VC Name                           Property
---  -- ----                           --------
0   0 ContosoCompany2                {}

PS HKCU:\Software> Complete-Transaction
PS HKCU:\Software> dir contoso*

Hive: HKEY_CURRENT_USER\Software
SKC  VC Name                           Property
---  -- ----                           --------
0   0 ContosoCompany1                     {}
0   0 ContosoCompany2                     {}
0   0 ContosoCompany3                     {}
```

この例は、トランザクションの進行中に実行されたコマンドをトランザクションに含めることができるかどうかを示します。
トランザクションの一部として使用されるのは、 *UseTransaction* パラメーターを使用するコマンドだけです。

1番目と3番目の **新しい項目** コマンドでは、 *UseTransaction* パラメーターを使用します。
これらのコマンドはトランザクションの一部です。
**2 番目の** *UseTransaction* コマンドでは、パラメーターを使用しないので、トランザクションの一部ではありません。

最初の dir コマンドは、効果を示しています。
2番目の **新しい項目** のコマンドはすぐに完了しますが、最初と3番目の **新しい項目** のコマンドは、トランザクションがコミットされるまで有効ではありません。

**Complete transaction** コマンドは、トランザクションをコミットします。
その結果、2番目の dir コマンドは、新しい項目がすべてレジストリに追加されたことを示します。

### 例 7: 指定した時間内に終了しないトランザクションをロールバックする

```
PS C:\> Start-Transaction -Timeout 2

# Wait two minutes...

PS C:\> Get-Transaction
PS C:\> New-Item HKCU:\Software\ContosoCompany -UseTransaction
PS C:\> Start-Transaction -Timeout 2

# Wait two minutes...

PS C:\> > Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   -----------
Error                1                 RolledBack

PS C:\> New-Item HKCU:\Software\ContosoCompany -UseTransaction

New-Item : Cannot use transaction. The transaction has been rolled back or has timed out.
At line:1 char:9
+ new-item <<<<  MyCompany -UseTransaction
```

このコマンドは、 **開始トランザクション** の *Timeout* パラメーターを使用して、2分以内に完了する必要があるトランザクションを開始します。
タイムアウトが経過してもトランザクションが完了していない場合は、自動的にロールバックされます。

タイムアウトが経過すると通知されませんが、トランザクションオブジェクトの **Status** プロパティは *rolUseTransaction* に設定され、このパラメーターを使用するコマンドは失敗します。

## PARAMETERS

### -非依存
このコマンドレットが、進行中のトランザクションから独立したトランザクションを開始することを示します。
既定では、別のトランザクションの実行中に **開始トランザクション** を使用すると、進行中のトランザクションに新しいサブスクライバーが追加されます。
このパラメーターが影響を及ぼすのは、トランザクションがセッション内で既に進行中の場合のみです。

トランザクションの進行中に **開始トランザクション** を使用すると、既定では、既存のトランザクションオブジェクトが再利用され、サブスクライバー数が増加します。
結果は、元のトランザクションの追加とほぼ同じです。
Undo-Transaction コマンドを実行すると、トランザクション全体がロールバックされます。
トランザクションを完了するには、各サブスクライバーに対して Complete-Transaction コマンドを入力する必要があります。
同時に進行している大半のトランザクションは互いに関連しているので、ほとんどの場合、既定の設定で十分です。

*独立* したパラメーターを指定した場合、このコマンドレットは、元のトランザクションに影響を与えずに完了または元に戻すことができる新しいトランザクションを作成します。
ただし、一度に複数のトランザクションを有効にすることはできないので、元のトランザクションに対する作業を再開するには、その前に新しいトランザクションを完了するか、ロールバックする必要があります。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RollbackPreference
トランザクションが自動的にロールバックされる条件を指定します。
このパラメーターの有効値は、次のとおりです。

- エラー。
終了エラーまたは未終了エラーが発生すると、トランザクションが自動的にロールバックされます。
- エラーを発生しています。
終了エラーが発生すると、トランザクションが自動的にロールバックされます。
- 不可
トランザクションは自動的にロールバックされません。

既定値は Error です。

```yaml
Type: System.Management.Automation.RollbackSeverity
Parameter Sets: (All)
Aliases:
Accepted values: Error, TerminatingError, Never

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -タイムアウト
トランザクションが有効である最大時間を分単位で指定します。
タイムアウトを過ぎると、トランザクションは自動的にロールバックされます。

既定では、コマンド ラインで開始されたトランザクションにタイムアウトはありません。
トランザクションがスクリプトによって開始された場合、既定のタイムアウトは 30 分です。

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TimeoutMins

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
コマンドレットの実行前に確認を求めるメッセージが表示されます。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
コマンドレットの実行時に発生する内容を示します。
このコマンドレットは実行されません。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### 共通パラメーター
このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### なし
パイプを使用してこのコマンドレットに入力を渡すことはできません。

## 出力

### なし
このコマンドレットは出力を生成しません。

## 注

## 関連リンク

[Complete-Transaction](Complete-Transaction.md)

[Get-Transaction](Get-Transaction.md)

[Undo-Transaction](Undo-Transaction.md)

[Use-Transaction](Use-Transaction.md)
