---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/30/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-webserviceproxy?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-WebServiceProxy
ms.openlocfilehash: aea656bc8ad4416673a7abb7d32a58d45dd3cc4f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214600"
---
# New-WebServiceProxy

## 概要
PowerShell で Web サービスを使用および管理できる Web サービスプロキシオブジェクトを作成します。

## SYNTAX

### NoCredentials (既定値)

```
New-WebServiceProxy [-Uri] <Uri> [[-Class] <String>] [[-Namespace] <String>] [<CommonParameters>]
```

### 資格情報

```
New-WebServiceProxy [-Uri] <Uri> [[-Class] <String>] [[-Namespace] <String>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### UseDefaultCredential

```
New-WebServiceProxy [-Uri] <Uri> [[-Class] <String>] [[-Namespace] <String>] [-UseDefaultCredential]
 [<CommonParameters>]
```

## Description

`New-WebServiceProxy`コマンドレットを使用すると、PowerShell で Web サービスを使用できます。 コマンドレットは、Web サービスに接続し、PowerShell に Web サービスプロキシオブジェクトを作成します。 プロキシ オブジェクトを使用して Web サービスを管理できます。

Web サービスは、特にインターネット経由でネットワーク経由でデータを交換する XML ベースのプログラムです。 Microsoft .NET Framework には Web サービス プロキシ オブジェクトが用意されており、Web サービスを .NET Framework オブジェクトとして表します。

## 例

### 例 1: Web サービスのプロキシを作成する

この例では、Windows PowerShell で電卓 Web サービスの .NET Framework プロキシを作成します。

```powershell
$calc = New-WebServiceProxy -Uri "http://www.dneonline.com/calculator.asmx?wsdl"
```

### 例 2: Web サービスのプロキシを作成し、名前空間とクラスを指定する

この例では、コマンドレットを使用して、 `New-WebServiceProxy` 電卓 Web サービスの .NET Framework プロキシを作成します。

```powershell
$URI = "http://www.dneonline.com/calculator.asmx?wsdl"
$calc = New-WebServiceProxy -Uri $URI -Namespace "WSProxy" -Class "Calculator"
```

このコマンドは、 **uri** パラメーターを使用して uri を指定し、 **名前空間** と **クラス** パラメーターを使用してオブジェクトの名前空間とクラスを指定します。

### 例 3: Web サービスプロキシのメソッドを表示する

```powershell
$calc | Get-Member -MemberType method
```

```Output
   TypeName: WSProxy.Calculator

Name                      MemberType Definition
----                      ---------- ----------
Abort                     Method     void Abort()
Add                       Method     int Add(int intA, int intB)
AddAsync                  Method     void AddAsync(int intA, int intB), void AddAsync(int intA,
BeginAdd                  Method     System.IAsyncResult BeginAdd(int intA, int intB, System.Asy
BeginDivide               Method     System.IAsyncResult BeginDivide(int intA, int intB, System.
BeginMultiply             Method     System.IAsyncResult BeginMultiply(int intA, int intB, Syste
BeginSubtract             Method     System.IAsyncResult BeginSubtract(int intA, int intB, Syste
CancelAsync               Method     void CancelAsync(System.Object userState)
CreateObjRef              Method     System.Runtime.Remoting.ObjRef CreateObjRef(type requestedT
Discover                  Method     void Discover()
Dispose                   Method     void Dispose(), void IDisposable.Dispose()
Divide                    Method     int Divide(int intA, int intB)
DivideAsync               Method     void DivideAsync(int intA, int intB), void DivideAsync(int
EndAdd                    Method     int EndAdd(System.IAsyncResult asyncResult)
EndDivide                 Method     int EndDivide(System.IAsyncResult asyncResult)
EndMultiply               Method     int EndMultiply(System.IAsyncResult asyncResult)
EndSubtract               Method     int EndSubtract(System.IAsyncResult asyncResult)
Equals                    Method     bool Equals(System.Object obj)
GetHashCode               Method     int GetHashCode()
GetLifetimeService        Method     System.Object GetLifetimeService()
GetType                   Method     type GetType()
InitializeLifetimeService Method     System.Object InitializeLifetimeService()
Multiply                  Method     int Multiply(int intA, int intB)
MultiplyAsync             Method     void MultiplyAsync(int intA, int intB), void MultiplyAsync(
Subtract                  Method     int Subtract(int intA, int intB)
SubtractAsync             Method     void SubtractAsync(int intA, int intB), void SubtractAsync(
ToString                  Method     string ToString()
```

この例では、コマンドレットを使用して、 `Get-Member` 変数内の Web サービスプロキシオブジェクトのメソッドを表示し `$calc` ます。 次の例では、これらのメソッドを使用します。

プロキシオブジェクトの **TypeName** (webserviceproxy) には、前の例で指定した名前空間とクラス名が反映されていることに注意してください。

### 例 4: Web サービスプロキシを使用する

```powershell
PS> $calc.Multiply(6,7)
42
```

この例では、変数に格納されている Web サービスプロキシを使用し `$calc` ます。 このコマンドは、プロキシの **乗算** メソッドを使用します。

## PARAMETERS

### -クラス

コマンドレットが Web サービス用に作成したプロキシ クラスの名前を指定します。 このパラメーターの値を **Namespace** パラメーターと共に使用して、クラスの完全修飾名を指定します。 既定値は、Uniform Resource Identifier (URI) から生成されます。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: FileName, FN

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

この処理を実行するアクセス許可を持つユーザー アカウントを指定します。 既定値は現在のユーザーです。 これは、 **UseDefaultCredential** パラメーターの使用に代わる方法です。

User01 や Domain01\user01」などのユーザー名を入力するか、コマンドレットによって生成されるような **PSCredential** オブジェクトを入力し `Get-Credential` ます。 ユーザー名を入力すると、このコマンドレットによってパスワードの入力が求められます。

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Credential
Aliases: Cred

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Namespace

新しいクラスの名前空間を指定します。

このパラメーターの値 **は、クラスパラメーターの** 値と共に使用して、クラスの完全修飾名を生成します。 既定値は、URI から生成された型に加えて、" **Microsoft. PowerShell. NewWebserviceProxy. autogenerated types** " になります。

名前 **空間** パラメーターの値を設定して、同じ名前を持つ複数の Web サービスにアクセスできるようにすることができます。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: NS

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Uri

Web サービスの URI を指定します。 サービスの説明が含まれているファイルの URI またはパスとファイル名を入力します。

URI は、サービスの `.asmx` 説明を返すページまたはページを返す必要があります。 ASP.NET を使用して作成された Web サービスのサービスの説明を返すには、「?」と追加します。WSDL "を Web サービスの URL (など `http://www.contoso.com/MyWebService.asmx?WSDL` ) にします。

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases: WL, WSDL, Path

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseDefaultCredential

このコマンドレットが既定の資格情報を使用することを示します。 このコマンドレットは、結果として得られるプロキシオブジェクトの **Usedefaultcredential** プロパティを True に設定します。 これは、 **Credential** パラメーターの使用に代わる方法です。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: UseDefaultCredential
Aliases: UDC

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### 共通パラメーター

このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### なし

パイプを使用してこのコマンドレットに入力を渡すことはできません。

## 出力

### Web サービスプロキシオブジェクト

このコマンドレットは、Web サービスプロキシオブジェクトを返します。 オブジェクトの名前空間とクラスは、コマンドのパラメーターによって決定されます。 既定値は入力 URI から生成されます。

## 注

`New-WebServiceProxy` は、 **システムの .net の WebClient** クラスを使用して、指定された Web サービスを読み込みます。

## 関連リンク

[New-Service](New-Service.md)
