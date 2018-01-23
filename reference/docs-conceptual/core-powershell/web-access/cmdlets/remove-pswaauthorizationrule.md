---
description: 
ms.topic: article
ms.prod: powershell
keywords: "PowerShell, コマンドレット"
ms.date: 2016-12-12
title: remove pswaauthorizationrule
ms.technology: powershell
ms.openlocfilehash: 4d039e7e00f87bc7aebb89217251edbbb5c3f5be
ms.sourcegitcommit: a444406120e5af4e746cbbc0558fe89a7e78aef6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="remove-pswaauthorizationrule"></a>Remove-PswaAuthorizationRule

## <a name="synopsis"></a>概要

指定された承認規則を Windows PowerShell® Web Access から削除します。

## <a name="syntax"></a>構文

### <a name="id"></a>Id
```
Remove-PswaAuthorizationRule [-Id] <Int32[]> [-Force] [-Confirm] [-WhatIf] [ <CommonParameters>]
```

### <a name="rule"></a>ルール
```
Remove-PswaAuthorizationRule [-Rule] <PswaAuthorizationRule[]> [-Force] [-Confirm] [-WhatIf] [ <CommonParameters>]
```

## <a name="description"></a>説明

指定された承認規則を Windows PowerShell Web Access から削除します。

## <a name="parameters"></a>パラメータ

### <a name="-force"></a>-Force

ユーザーの確認を求めずにコマンドレットを実行します。 既定では、コマンドレットにより続行前に確認が求められます。

|||  
|-|-|
| エイリアス                              | なし                                 |
| 必須?                            | false                                |
| 位置は?                            | 名前付き                                |
| 既定値                        | なし                                 |
| パイプライン入力を許可する               | false                                |
| ワイルドカード文字を許可する          | false                                |

### <a name="-id-ltint32gt"></a>-Id &lt;Int32\[\]&gt;

削除する 1 つまたは複数の規則の識別子 (ID) を指定します。

|||  
|-|-|
| エイリアス                              | なし                                 |
| 必須?                            | true                                 |
| 位置は?                            | 2                                    |
| 既定値                        | なし                                 |
| パイプライン入力を許可する               | True (ByValue, ByPropertyName)       |
| ワイルドカード文字を許可する          | false                                |

### <a name="-rule-ltpswaauthorizationrulegt"></a>-Rule &lt;PswaAuthorizationRule\[\]&gt;

削除する規則を指定します。

|||  
|-|-|
| エイリアス                              | なし                                 |
| 必須?                            | true                                 |
| 位置は?                            | 2                                    |
| 既定値                        | なし                                 |
| パイプライン入力を許可する               | True (ByValue)                       |
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

コマンドレットを実行するとどのような結果になるかを表示します。 コマンドレットは実行されません。

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

### <a name="int"></a>int\[\]

このコマンドレットは、整数の配列、または PswaAuthorizationRule オブジェクトの配列を受け入れます。

### <a name="pswaauthorizationrule"></a>PswaAuthorizationRule\[\]

このコマンドレットは、整数の配列、または PswaAuthorizationRule オブジェクトの配列を受け入れます。

## <a name="outputs"></a>出力

このコマンドレットから出力は生成されません。

## <a name="examples"></a>例

### <a name="example-1"></a>例 1

この例では、ID が *2* の承認規則が削除されます。

```
Remove-PswaAuthorizationRule –Id 2
```

### <a name="example-2-example-2-subheading"></a>例 2 {#example-2 .subHeading}

この例では、すべての承認規則が削除されます。また、ユーザーの確認が必要です。

```
Get-PswaAuthorizationRule | Remove-PswaAuthorizationRule -Confirm
```

## <a name="related-topics"></a>関連トピック

- [Add-PswaAuthorizationRule](add-pswaauthorizationrule.md)
- [Get-PswaAuthorizationRule](get-pswaauthorizationrule.md)
- [Install-PswaWebApplication](install-pswawebapplication.md)
- [Test-PswaAuthorizationRule](test-pswaauthorizationrule.md)
