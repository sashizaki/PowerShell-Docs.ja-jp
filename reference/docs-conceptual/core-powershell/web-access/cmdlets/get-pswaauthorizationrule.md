---
description: 
manager: carmonm
ms.topic: article
author: jpjofre
ms.prod: powershell
keywords: "PowerShell, コマンドレット"
ms.date: 2016-12-12
title: get pswaauthorizationrule
ms.technology: powershell
ms.openlocfilehash: eb9f42ab4d9cec111e03a096b2f00740e97ee1b7
ms.sourcegitcommit: d6ab9ab5909ed59cce4ce30e29457e0e75c7ac12
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2017
---
# <a name="get-pswaauthorizationrule"></a>Get-PswaAuthorizationRule

## <a name="synopsis"></a>概要

Windows PowerShell® Web Access の承認規則のセットを返します。

## <a name="syntax"></a>構文

### <a name="id"></a>ID
```
Get-PswaAuthorizationRule [[-Id] <Int32[]> ] [ <CommonParameters>]
```

### <a name="name"></a>名前
```
Get-PswaAuthorizationRule [-RuleName] <String[]> [ <CommonParameters>]
```

## <a name="description"></a>説明

**Get-PswaAuthorizationRule** コマンドレットは、Windows PowerShell® Web Access 承認規則のセットを返します。
**Id** パラメーターも **RuleName** パラメーターも指定されていない場合、コマンドレットによりすべての規則が列挙されます。 **Id** パラメーターは、結果を絞り込むために使用できます。

## <a name="parameters"></a>パラメータ

### <a name="-idltint32gt"></a>-Id&lt;Int32\[\]&gt;

このコマンドレットで取得する規則の識別子 (ID) を指定します。 ID を指定しない場合、このコマンドレットによりすべての承認規則が返されます。

|||  
|-|-|
| エイリアス                              | なし                                 |
| 必須?                            | false                                |
| 位置は?                            | 2                                    |
| 既定値                        | なし                                 |
| パイプライン入力を許可する               | True (ByValue, ByPropertyName)       |
| ワイルドカード文字を許可する          | false                                |

### <a name="-rulenameltstringgt"></a>-RuleName&lt;String\[\]&gt;

取得する承認規則の名前を指定します。 このパラメーターを指定すると、この配列内の文字列の規則名と正確に一致する規則が返されます。

|||  
|-|-|
| エイリアス                              | なし                                 |
| 必須?                            | true                                 |
| 位置は?                            | 2                                    |
| 既定値                        | なし                                 |
| パイプライン入力を許可する               | True (ByValue, ByPropertyName)       |
| ワイルドカード文字を許可する          | false                                |

### <a name="ltcommonparametersgt"></a>&lt;CommonParameters&gt;

このコマンドレットは、-Verbose、-Debug、-ErrorAction、-ErrorVariable、-OutBuffer、および -OutVariable という共通パラメーターをサポートします。
詳細については、「[about_CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216)」を参照してください。

## <a name="inputs"></a>入力

### <a name="int"></a>int\[\]

このコマンドレットは、入力として整数の配列または文字列値の配列を受け入れます。

### <a name="string"></a>String\[\]

このコマンドレットは、入力として整数の配列または文字列値の配列を受け入れます。

## <a name="outputs"></a>出力

### <a name="microsoftmanagementpowershellwebaccesspswaauthorizationrule"></a>Microsoft.Management.PowerShellWebAccess.PswaAuthorizationRule\[\]

このコマンドレットは、出力として PswaAuthorizationRule オブジェクトを生成します。


## <a name="examples"></a>例

### <a name="example-1"></a>例 1

この例では、すべての規則を取得します。

```PowerShell
    PS C:\> Get-PswaAuthorizationRule
```

### <a name="example-2"></a>例 2

この例では、ID が *2* の規則を取得します。

```PowerShell
    PS C:\> Get-PswaAuthorizationRule –Id 2
```

### <a name="example-3-example-3-subheading"></a>例 3 {#example-3 .subHeading}

この例は、コマンドレットでパイプラインの値を受け入れる方法を示しています。
規則の ID と規則の名前がこのコマンドレットで渡されます。

```PowerShell
    PS C:\> "rule1",0 | Get-PswaAuthorizationRule
```

## <a name="related-topics"></a>関連トピック

- [Add-PswaAuthorizationRule](add-pswaauthorizationrule.md)
- [Remove-PswaAuthorizationRule](remove-pswaauthorizationrule.md)
- [Test-PswaAuthorizationRule](test-pswaauthorizationrule.md)
- [Install-PswaWebApplication](install-pswawebapplication.md)
