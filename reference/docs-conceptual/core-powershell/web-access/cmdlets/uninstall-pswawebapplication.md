---
description: 
ms.topic: article
ms.prod: powershell
keywords: "PowerShell, コマンドレット"
ms.date: 2016-12-12
title: uninstall pswawebapplication
ms.technology: powershell
ms.openlocfilehash: cc54c94426d754ff2d3bf658e3e92083f02cd6c7
ms.sourcegitcommit: a444406120e5af4e746cbbc0558fe89a7e78aef6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="uninstall-pswawebapplication"></a>Uninstall-PswaWebApplication

## <a name="synopsis"></a>概要

Windows PowerShell® Web アプリケーションをアンインストールします。

## <a name="syntax"></a>構文

### <a name="default"></a>既定
```
Uninstall-PswaWebApplication [[-WebApplicationName] <String> ] [-DeleteTestCertificate] [-WebSiteName <String> ] [-Confirm] [-WhatIf] [ <CommonParameters>]
```

## <a name="description"></a>説明

**Uninstall-PswaWebApplication** コマンドレットは、Windows PowerShell Web アプリケーションをアンインストールし、IIS から Web サイトを削除します。 このコマンドレットでは、Windows PowerShell の実行に必要なため、IIS やインストールされている他の機能はアンインストールされません。

## <a name="parameters"></a>パラメータ

### <a name="-deletetestcertificate"></a>-DeleteTestCertificate

**Install\_PswaWebApplication** コマンドレット (**UseTestCertificate** パラメーターを指定) で作成されたテスト証明書の削除を指定します。
**Install-PswaWebApplication** コマンドレットで作成されたテスト証明書と同じ名前のテスト証明書のみが削除されます。

|||  
|-|-|
| エイリアス                              | なし                                 |
| 必須?                            | false                                |
| 位置は?                            | 名前付き                                |
| 既定値                        | true                                 |
| パイプライン入力を許可する               | false                                |
| ワイルドカード文字を許可する          | false                                |

### <a name="-webapplicationname-ltstringgt"></a>-WebApplicationName &lt;String&gt;

アンインストールする Web アプリケーションの名前を指定します。

|||  
|-|-|
| エイリアス                              | なし                                 |
| 必須?                            | false                                |
| 位置は?                            | 1 で保護されたプロセスとして起動されました                                    |
| 既定値                        | pswa                                 |
| パイプライン入力を許可する               | false                                |
| ワイルドカード文字を許可する          | false                                |

### <a name="-websitename-ltstringgt"></a>-WebSiteName &lt;String&gt;

Web アプリケーションがインストールされている Web サイトの名前を指定します。

|||  
|-|-|
| エイリアス                              | なし                                 |
| 必須?                            | false                                |
| 位置は?                            | 名前付き                                |
| 既定値                        | Default Web Site                     |
| パイプライン入力を許可する               | false                                |
| ワイルドカード文字を許可する          | false                                |

### <a name="-confirm"></a>-Confirm

コマンドレットを実行する前に、ユーザーに確認を求めます。

|||  
|-|-|
| 必須?                            | false                                |
| 位置は?                            | 名前付き                                |
| 既定値                        | false                                |
| パイプライン入力を許可する               | false                                |
| ワイルドカード文字を許可する          | false                                |

### <a name="-whatif"></a>-WhatIf

コマンドレットを実行するとどのような結果になるかを表示します。
コマンドレットは実行されません。

|||  
|-|-|
| 必須?                            | false                                |
| 位置は?                            | 名前付き                                |
| 既定値                        | false                                |
| パイプライン入力を許可する               | false                                |
| ワイルドカード文字を許可する          | false                                |

### <a name="ltcommonparametersgt"></a>&lt;CommonParameters&gt;

このコマンドレットは、-Verbose、-Debug、-ErrorAction、-ErrorVariable、-OutBuffer、および -OutVariable という共通パラメーターをサポートします。
詳細については、「[about_CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216)」を参照してください。

## <a name="inputs"></a>入力

このコマンドレットは、入力を受け取りません。

## <a name="outputs"></a>出力

このコマンドレットは、出力を返しません。

## <a name="examples"></a>例

### <a name="example-1"></a>例 1

このコマンドは、Windows PowerShell Web アプリケーションをアンインストールします。
既定値を使用して Windows PowerShell Web アプリケーションをインストールした場合、そのアプリケーションをアンインストールするときにこのコマンドレットを使用できます。

```PowerShell
Uninstall-PswaWebApplication
```

### <a name="example-2"></a>例 2

このコマンドは、Windows PowerShell Web アプリケーションをアンインストールし、アプリケーションに関連付けられているテスト証明書を削除します。
既定値を使用して Windows PowerShell Web アプリケーションをインストールし、テスト証明書を作成した場合、そのアプリケーションをアンインストールするときにこのコマンドレットを使用できます。

```PowerShell
Uninstall-PswaWebApplication -DeleteTestCertificate
```

### <a name="example-3-example-3-subheading"></a>例 3 {#example-3 .subHeading}

インストール時にカスタム Web サイトおよびアプリケーションを指定した場合、このコマンドで Windows PowerShell Web アプリケーションがアンインストールされます。
このコマンドは、*MySite* という Web サイトと *TestApplication* というアプリケーションを削除し、アプリケーションに関連付けられているテスト証明書の削除も指定します。

```
Uninstall-PswaWebApplication -WebApplicationName TestApplication -WebsiteName MySite -DeleteTestCertificate
```

## <a name="related-topics"></a>関連トピック

- [Add-PswaAuthorizationRule](add-pswaauthorizationrule.md)
- [Get-PswaAuthorizationRule](get-pswaauthorizationrule.md)
- [Install-PswaWebApplication](install-pswawebapplication.md)
- [Remove-PswaAuthorizationRule](remove-pswaauthorizationrule.md)
- [Test-PswaAuthorizationRule](test-pswaauthorizationrule.md)
