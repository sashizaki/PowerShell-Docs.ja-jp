---
description: 
manager: carmonm
ms.topic: article
author: jpjofre
ms.prod: powershell
keywords: "PowerShell, コマンドレット"
ms.date: 2016-12-12
title: test pswaauthorizationrule
ms.technology: powershell
ms.openlocfilehash: 1b480b68c7ce2064f42281d8c5d76156a39e0222
ms.sourcegitcommit: 4102ecc35d473211f50a453f6ae3fbea31cb3428
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2017
---
#  <a name="test-pswaauthorizationrule"></a>Test-PswaAuthorizationRule

##  <a name="synopsis"></a>概要

指定されたユーザー、コンピューター、またはエンドポイントに規則が存在するかどうかを確認します。

## <a name="syntax"></a>構文

###  <a name="computername"></a>ComputerName
```
Test-PswaAuthorizationRule [-UserName] <String> [-ComputerName] <String> [[-ConfigurationName] <String> ] [-Credential <PSCredential> ] [-Rule <PswaAuthorizationRule[]> ] [ <CommonParameters>]
```

###  <a name="connectionuri"></a>ConnectionUri
```
Test-PswaAuthorizationRule [-UserName] <String> [-ConnectionUri] <Uri> [[-ConfigurationName] <String> ] [-Credential <PSCredential> ] [-Rule <PswaAuthorizationRule[]> ] [ <CommonParameters>]
```

## <a name="description"></a>説明

**Test-PswaAuthorizationRule** コマンドレットは、指定されたユーザー、コンピューター、またはエンドポイントに規則が存在するかどうかを確認します。
また、特定のユーザー、コンピューター、エンドポイント アクセス要求が承認されていることを確認する承認規則のテストにもこのコマンドレットを使用できます。
このコマンドレットは、既定で承認ファイルのすべての規則を評価します。
ただし、テスト対象として一部の規則を指定することもできます。

このコマンドレットは、認証エラーを解決するときに役立ちます。

このコマンドレットのパラメーターは、Windows PowerShell® Web Access のサインオン ページ上のフィールドに対応しています。

## <a name="parameters"></a>パラメータ

### <a name="-computername-ltstringgt"></a>-ComputerName &lt;String&gt;

テストするコンピューターの名前を指定します。

|||  
|-|-|
| エイリアス                              | なし                                 |
| 必須?                            | true                                 |
| 位置は?                            | 2                                    |
| 既定値                        | なし                                 |
| パイプライン入力を許可する               | false                                |
| ワイルドカード文字を許可する          | false                                |

### <a name="-configurationname-ltstringgt"></a>-ConfigurationName &lt;String&gt;

テストする Windows PowerShell セッション構成 (エンドポイント、実行空間とも呼ばれます) の名前を指定します。

|||  
|-|-|
| エイリアス                              | なし                                 |
| 必須?                            | false                                |
| 位置は?                            | 3                                    |
| 既定値                        | なし                                 |
| パイプライン入力を許可する               | false                                |
| ワイルドカード文字を許可する          | false                                |

### <a name="-connectionuri-lturigt"></a>-ConnectionUri &lt;Uri&gt;

テストする接続 URI を指定します。

|||  
|-|-|
| エイリアス                              | なし                                 |
| 必須?                            | true                                 |
| 位置は?                            | 2                                    |
| 既定値                        | なし                                 |
| パイプライン入力を許可する               | false                                |
| ワイルドカード文字を許可する          | false                                |

### <a name="-credential-ltpscredentialgt"></a>-Credential &lt;PSCredential&gt;

Windows PowerShell Web Access 承認規則のテストに使用するユーザー アカウントの **PSCredential** オブジェクトを指定します。 このパラメーターを追加しない場合、現在ログオンしているユーザー アカウントがコマンドレットにより使用されます。 承認規則をリモートからテストするために必要な **PSCredential** オブジェクトを取得するには、[Get-Credential](http://go.microsoft.com/fwlink/?LinkID=293936) コマンドレットを実行します。

|||  
|-|-|
| エイリアス                              | なし                                 |
| 必須?                            | false                                |
| 位置は?                            | 名前付き                                |
| 既定値                        | なし                                 |
| パイプライン入力を許可する               | false                                |
| ワイルドカード文字を許可する          | false                                |

### <a name="-rule-ltpswaauthorizationrulegt"></a>-Rule &lt;PswaAuthorizationRule\[\]&gt;

テストする規則のサブセットを指定します。 このパラメーターを指定しない場合、すべての承認規則に対してテストが実行されます。

|||  
|-|-|
| エイリアス                              | なし                                 |
| 必須?                            | false                                |
| 位置は?                            | 名前付き                                |
| 既定値                        | なし                                 |
| パイプライン入力を許可する               | True (ByValue)                       |
| ワイルドカード文字を許可する          | false                                |

### <a name="-username-ltstringgt"></a>-UserName &lt;String&gt;

テストするユーザーの名前を指定します。

|||  
|-|-|
| エイリアス                              | なし                                 |
| 必須?                            | true                                 |
| 位置は?                            | 1 で保護されたプロセスとして起動されました                                    |
| 既定値                        | なし                                 |
| パイプライン入力を許可する               | false                                |
| ワイルドカード文字を許可する          | false                                |

### <a name="ltcommonparametersgt"></a>&lt;CommonParameters&gt;

このコマンドレットは、-Verbose、-Debug、-ErrorAction、-ErrorVariable、-OutBuffer、および -OutVariable という共通パラメーターをサポートします。
詳細については、「[about_CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216)」を参照してください。

## <a name="inputs"></a>入力

###  <a name="microsoftmanagementpowershellwebaccesspswaauthorizationrule"></a>Microsoft.Management.PowerShellWebAccess.PswaAuthorizationRule\[\]

このコマンドレットは、入力として PswaAuthorizationRule オブジェクトの配列を受け入れます。

##  <a name="outputs"></a>出力

###  <a name="microsoftmanagementpowershellwebaccesspswaauthorizationrule"></a>Microsoft.Management.PowerShellWebAccess.PswaAuthorizationRule\[\]

このコマンドレットは、出力として PswaAuthorizationRule オブジェクトの配列を生成します。

## <a name="examples"></a>例

### <a name="example-1"></a>例 1

この例では、ユーザー *contoso\\mhanson* に対して、コンピューター *srv2* への接続と、*test* という Windows PowerShell セッション構成の使用を許可するために、すべての承認規則をテストします。

```
Test-PswaAuthorizationRule -ComputerName srv2.contoso.com -UserName contoso\mhanson -ConfigurationName test
```

### <a name="example-2"></a>例 2

この例では、ユーザー *contoso\\mhanson* に適用される承認規則を確認するために、すべての承認規則をテストします。

```
Test-PswaAuthorizationRule -UserName contoso\mhanson -ComputerName *
```

##  <a name="related-topics"></a>関連トピック

-  [Add-PswaAuthorizationRule](add-pswaauthorizationrule.md)
-  [Get-PswaAuthorizationRule](get-pswaauthorizationrule.md)
-  [Install-PswaWebApplication](install-pswawebapplication.md)
-  [Remove-PswaAuthorizationRule](remove-pswaauthorizationrule.md)
