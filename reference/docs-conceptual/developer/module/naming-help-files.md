---
title: ヘルプファイルの名前付け |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bf54eac7-88c6-4108-a5f6-2f0906d1662b
caps.latest.revision: 5
ms.openlocfilehash: f65a90023df88fceafae1d1875ddf46b9088e2b8
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367011"
---
# <a name="naming-help-files"></a>ヘルプ ファイルに名前を付ける

このトピックでは、 [get-help](/powershell/module/Microsoft.PowerShell.Core/Get-Help)コマンドレットで検索できるように、XML ベースのヘルプファイルに名前を指定する方法について説明します。 名前の要件は、コマンドの種類によって異なります。

## <a name="cmdlet-help-files"></a>コマンドレットのヘルプファイル

コマンドレットのC#ヘルプファイルには、コマンドレットが定義されているアセンブリの名前を付ける必要があります。 次のファイル名の形式を使用します。

```
<AssemblyName>.dll-help.xml
```

アセンブリが入れ子になっているモジュールの場合でも、アセンブリ名の形式が必要です。

たとえば、 [Get-WinEvent;PSITPro5_Diagnostic;](/powershell/module/Microsoft.PowerShell.Diagnostics/Get-WinEvent)コマンドレットは、Microsoft... .dll アセンブリで定義されています。 @No__t-0 コマンドレットは、モジュールディレクトリ内の dll-help ファイルでのみ `Get-WinEvent` コマンドレットのヘルプトピックを検索します。

## <a name="provider-help-files"></a>プロバイダーヘルプファイル

Windows PowerShell プロバイダーのヘルプファイルには、プロバイダーが定義されているアセンブリの名前を付ける必要があります。 次のファイル名の形式を使用します。

```
<AssemblyName>.dll-help.xml
```

アセンブリが入れ子になっているモジュールの場合でも、アセンブリ名の形式が必要です。

たとえば、証明書プロバイダーは、Microsoft の .dll アセンブリで定義されています。 @No__t-0 コマンドレットは、モジュールディレクトリ内の dll-help ファイルでのみ、証明書プロバイダーのヘルプトピックを検索します。

## <a name="function-help-files"></a>関数のヘルプファイル

関数は、[コメントベースのヘルプ](/powershell/module/microsoft.powershell.core/about/about_comment_based_help)を使用するか、XML ヘルプファイルに記載されているドキュメントに記載されています。 関数が XML ファイルに記述されている場合、関数には、XML ファイルに関数を関連付ける @no__t 0 comment キーワードが必要です。 それ以外の場合、@no__t 0 のコマンドレットはヘルプファイルを見つけることができません。

関数のヘルプファイルの名前に関する技術的な要件はありません。 ただし、関数が定義されているスクリプトモジュールのヘルプファイルには、という名前を指定することをお勧めします。 たとえば、次の関数は、hbase-runner.psm1 ファイルで定義されています。

```csharp
#.ExternalHelp MyModule.psm1-help.xml
function Test-Function { ... }
```

## <a name="cim-command-help-files"></a>CIM コマンドのヘルプファイル

Cim コマンドのヘルプファイルには、CIM コマンドが定義されている CDXML ファイルの名前を付ける必要があります。 次のファイル名の形式を使用します。

```
<FileName>.cdxml-help.xml
```

CIM コマンドは、モジュールに入れ子になったモジュールとして含めることができる、CDXML ファイルで定義されています。 CIM コマンドが関数としてセッションにインポートされると、Windows PowerShell は、関数定義に @no__t 0 comment キーワードを追加します。この関数は、CIM コマンドが定義されている CDXML ファイルの名前が付けられている XML ヘルプファイルに関数を関連付けます。

## <a name="script-workflow-help-files"></a>スクリプトワークフローのヘルプファイル

モジュールに含まれているスクリプトワークフローは、XML ベースのヘルプファイルに記載されています。 ヘルプファイルの名前に関する技術的な要件はありません。 ただし、スクリプトワークフローが定義されているスクリプトモジュールのヘルプファイルには、という名前を指定することをお勧めします。 たとえば、次のようになります。

```
<ScriptModule>.psm1-help.xml
```

スクリプト化された他のコマンドとは異なり、スクリプトワークフローには、ヘルプファイルに関連付けるための @no__t 0 コメントキーワードは必要ありません。 代わりに、Windows PowerShell は、モジュールディレクトリの UI カルチャ固有のサブディレクトリで XML ベースのヘルプファイルを検索し、すべてのファイルでスクリプトワークフローのヘルプを検索します。 `.ExternalHelp` コメントキーワードは無視されます。

@No__t-0 comment キーワードは無視されるため、`Get-Help` コマンドレットは、モジュールに含まれている場合にのみスクリプトワークフローのヘルプを見つけることができます。