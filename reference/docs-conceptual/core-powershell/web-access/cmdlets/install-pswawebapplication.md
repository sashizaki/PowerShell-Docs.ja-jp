---
description: ''
ms.topic: article
ms.prod: powershell
keywords: PowerShell, コマンドレット
ms.date: 12/12/2016
title: install pswawebapplication
ms.technology: powershell
ms.openlocfilehash: c7f7768a41b6784d8c29afa1fccf0b855160b777
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="install-pswawebapplication"></a>Install-PswaWebApplication

## <a name="synopsis"></a>概要

IIS で Windows PowerShell® Web Access Web アプリケーションを構成します。

## <a name="syntax"></a>構文

### <a name="default"></a>既定
```
Install-PswaWebApplication [[-WebApplicationName] <String> ] [-UseTestCertificate] [-WebSiteName <String> ] [-Confirm] [-WhatIf] [ <CommonParameters>]
```

## <a name="description"></a>説明

**Install-PswaWebApplication** コマンドレットは、Windows PowerShell Web Access Web アプリケーションを構成します。 このコマンドレットは、Web アプリケーションをインストールし、そのアプリケーションを Web サイトと関連付けます。また、必要に応じて **useTestCertificate** パラメーターを使用してテスト SSL 証明書を作成することもできます。 セキュリティ上の理由から、Web 管理者は運用環境にテスト証明書を使用しないでください。

## <a name="parameters"></a>パラメータ

### <a name="-usetestcertificate"></a>-UseTestCertificate

テスト証明書が作成されることを指定します。 このパラメーターを true に設定すると、このコマンドレットはテスト証明書を作成し、HTTPS 要求にその証明書を使用するように Windows PowerShell Web Access Web アプリケーションを構成します。 このパラメーターを false に設定すると、証明書またはバインディングは作成されません。 Windows PowerShell Web Access に別の証明書を使用する場合は、この値を false に設定します。

|||
|-|-|
| エイリアス                              | なし                                 |
| 必須?                            | false                                |
| 位置は?                            | 名前付き                                |
| 既定値                        | true                                 |
| パイプライン入力を許可する               | false                                |
| ワイルドカード文字を許可する          | false                                |

### <a name="-webapplicationnameltstringgt"></a>-WebApplicationName&lt;String&gt;

Web アプリケーションの名前を指定します。 これは Windows PowerShell Web Access URL の末尾の部分に表示されます。

|||
|-|-|
| エイリアス                              | なし                                 |
| 必須?                            | false                                |
| 位置は?                            | 1 で保護されたプロセスとして起動されました                                    |
| 既定値                        | pswa                                 |
| パイプライン入力を許可する               | false                                |
| ワイルドカード文字を許可する          | false                                |

### <a name="-websitenameltstringgt"></a>-WebSiteName&lt;String&gt;

この Windows PowerShell Web Access Web アプリケーションをインストールする Web サーバー (IIS) Web サイトの名前を指定します。

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

このコマンドレットから出力は生成されません。

## <a name="examples"></a>例

### <a name="example-1"></a>例 1

この例では、**WebApplicationName** (*pswa*) パラメーターと **WebSiteName** (*Default Web Site*) パラメーターに既定値を使用して、PSWA Web アプリケーションをインストールします。

```
Install-PswaWebApplication
```

### <a name="example-2"></a>例 2

この例では、テスト証明書を使用し、**WebApplicationName** パラメーターと **WebSiteName** パラメーターに既定値を使用して、PSWA Web アプリケーションをインストールします。

```
Install-PswaWebApplication -UseTestCertificate
```

## <a name="related-topics"></a>関連トピック

- [Add-PswaAuthorizationRule](add-pswaauthorizationrule.md)
- [Get-PswaAuthorizationRule](get-pswaauthorizationrule.md)
- [Remove-PswaAuthorizationRule](remove-pswaauthorizationrule.md)
- [Test-PswaAuthorizationRule](test-pswaauthorizationrule.md)