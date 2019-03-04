---
title: ヘルプ ファイルの名前付け |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bf54eac7-88c6-4108-a5f6-2f0906d1662b
caps.latest.revision: 5
ms.openlocfilehash: 06281a1260dbdc120867fce89e6d5c8dd0754b87
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856668"
---
# <a name="naming-help-files"></a>ヘルプ ファイルに名前を付ける

このトピックでは、XML ベースのヘルプ ファイルの名前を付ける方法をについて説明できるように、 [Get-help](/powershell/module/Microsoft.PowerShell.Core/Get-Help)コマンドレットで見つけることができます。 名の要件は、各コマンドの種類によって異なります。
このトピックでは、XML ベースのヘルプ ファイルの名前を付ける方法をについて説明できるように、 [Get-help](/powershell/module/Microsoft.PowerShell.Core/Get-Help)コマンドレットで見つけることができます。 名の要件は、各コマンドの種類によって異なります。

## <a name="cmdlet-help-files"></a>コマンドレットのヘルプ ファイル

ヘルプ ファイル、C#コマンドレットは、コマンドレットが定義されているアセンブリの名前必要があります。 次のファイル名の形式を使用します。

```
<AssemblyName>.dll-help.xml
```

アセンブリが入れ子になったモジュールの場合でも、アセンブリ名の形式が必要です。

たとえば、 [Get-winevent;PSITPro5_Diagnostic;](/powershell/module/Microsoft.PowerShell.Diagnostics/Get-WinEvent)コマンドレットが Microsoft.PowerShell.Diagnostics.dll アセンブリで定義されています。 `Get-Help`コマンドレットのヘルプ トピックを検索、`Get-WinEvent`コマンドレット モジュール ディレクトリに Microsoft.PowerShell.Diagnostics.dll help.xml ファイルにのみ存在します。
たとえば、 [Get-winevent;PSITPro5_Diagnostic;](/powershell/module/Microsoft.PowerShell.Diagnostics/Get-WinEvent)コマンドレットが Microsoft.PowerShell.Diagnostics.dll アセンブリで定義されています。 `Get-Help`コマンドレットのヘルプ トピックを検索、`Get-WinEvent`コマンドレット モジュール ディレクトリに Microsoft.PowerShell.Diagnostics.dll help.xml ファイルにのみ存在します。

## <a name="provider-help-files"></a>プロバイダーのヘルプ ファイル

Windows PowerShell プロバイダーのヘルプ ファイルは、プロバイダーが定義されているアセンブリの名前をする必要があります。 次のファイル名の形式を使用します。

```
<AssemblyName>.dll-help.xml
```

アセンブリが入れ子になったモジュールの場合でも、アセンブリ名の形式が必要です。

たとえば、証明書プロバイダーは、Microsoft.PowerShell.Security.dll アセンブリで定義されます。 `Get-Help`コマンドレットはモジュール ディレクトリに Microsoft.PowerShell.Security.dll help.xml ファイルでのみ証明書プロバイダーのヘルプ トピックを検索します。

## <a name="function-help-files"></a>関数のヘルプ ファイル

使用して関数を記述できます[コメント ベースのヘルプ](/powershell/module/microsoft.powershell.core/about/about_comment_based_help)や XML のヘルプ ファイルに記載されています。 関数が必要、関数が XML ファイルに記載されているときに、`.ExternalHelp`コメントを XML ファイルを使用して、関数を関連付けるキーワード。 それ以外の場合、`Get-Help`コマンドレットは、ヘルプ ファイルを見つけることができません。
使用して関数を記述できます[コメント ベースのヘルプ](/powershell/module/microsoft.powershell.core/about/about_comment_based_help)や XML のヘルプ ファイルに記載されています。 関数が必要、関数が XML ファイルに記載されているときに、`.ExternalHelp`コメントを XML ファイルを使用して、関数を関連付けるキーワード。 それ以外の場合、`Get-Help`コマンドレットは、ヘルプ ファイルを見つけることができません。

関数のヘルプ ファイルの名前の技術的な要件はありません。 ただし、関数が定義されている、スクリプト モジュールのヘルプ ファイルの名前をお勧めします。 たとえば、次の関数は、MyModule.psm1 ファイルで定義されます。

```csharp
#.ExternalHelp MyModule.psm1-help.xml
function Test-Function { ... }
```

## <a name="cim-command-help-files"></a>CIM コマンドのヘルプ ファイル

CIM コマンドのヘルプ ファイルは、CIM コマンドが定義されている CDXML ファイルの名前をする必要があります。 次のファイル名の形式を使用します。

```
<FileName>.cdxml-help.xml
```

CIM コマンドは、モジュールは、入れ子になったモジュールに含まれる CDXML ファイルで定義されます。 Windows PowerShell を追加、CIM コマンドを関数としてセッションにインポートするとき、`.ExternalHelp`コメント ファイルを XML ヘルプ、関数に関連付けている関数の定義のキーワードが、CIM コマンドが定義されている CDXML ファイルの名前が付け。

## <a name="script-workflow-help-files"></a>スクリプト ワークフローのヘルプ ファイル

モジュールに含まれているスクリプト ワークフローは、XML ベースのヘルプ ファイルに文書化することができます。 ヘルプ ファイルの名前の技術的な要件はありません。 ただし、スクリプト ワークフローが定義されている、スクリプト モジュールのヘルプ ファイルの名前をお勧めします。 たとえば、次のように入力します。

```
<ScriptModule>.psm1-help.xml
```

スクリプト ワークフローは必要としない、他のスクリプト化されたコマンドとは異なり、`.ExternalHelp`にヘルプ ファイルに関連付けるキーワードをコメントします。 代わりに、Windows PowerShell では、XML ベースのヘルプ ファイルをモジュール ディレクトリの UI カルチャ固有のサブディレクトリを検索し、すべてのファイル、スクリプト ワークフローのヘルプを検索します。 `.ExternalHelp` コメントのキーワードは無視されます。

`.ExternalHelp`コメント キーワードは無視されます、`Get-Help`コマンドレットは、モジュールに含まれる場合にのみに、スクリプト ワークフローのヘルプを見つけることができます。