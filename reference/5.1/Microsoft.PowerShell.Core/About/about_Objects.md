---
description: Windows PowerShell のオブジェクトに関する重要な情報を提供します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 11/30/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_objects?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Objects
ms.openlocfilehash: 678eececc2625bf02a706e8ef61c83056443a12f
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223416"
---
# <a name="about-objects"></a>オブジェクトの概要

## <a name="short-description"></a>簡単な説明

Windows PowerShell のオブジェクトに関する重要な情報を提供します。

## <a name="long-description"></a>長い説明

Windows PowerShell で実行するすべての操作は、オブジェクトのコンテキスト内で行われます。 あるコマンドから次のコマンドにデータを移動すると、1つまたは複数の識別可能なオブジェクトとして移動します。 オブジェクトは、アイテムを表すデータのコレクションです。 オブジェクトは、オブジェクトの種類、メソッド、およびそのプロパティの3種類のデータで構成されます。

## <a name="types-methods-and-properties"></a>型、メソッド、およびプロパティ

オブジェクトの種類は、オブジェクトの種類を示します。 たとえば、ファイルを表すオブジェクトは、FileInfo オブジェクトです。

オブジェクトメソッドは、オブジェクトに対して実行できるアクションです。
たとえば、FileInfo オブジェクトには、ファイルのコピーに使用できる CopyTo メソッドがあります。

オブジェクトのプロパティには、オブジェクトに関する情報が格納されます。 たとえば、FileInfo オブジェクトには、ファイルが最後にアクセスされた日付と時刻を格納する LastWriteTime プロパティがあります。

オブジェクトを操作する場合は、コマンドでそのメソッドとプロパティを使用して、アクションを実行したり、データを管理したりすることができます。

## <a name="objects-in-pipelines"></a>パイプライン内のオブジェクト

パイプラインでコマンドを結合すると、それらのコマンドはオブジェクトとして相互に情報を渡します。 最初のコマンドが実行されると、パイプライン内の1つ以上のオブジェクトが2番目のコマンドに送信されます。 2番目のコマンドは、最初のコマンドからオブジェクトを受け取り、オブジェクトを処理してから、新しいオブジェクトまたは変更されたオブジェクトをパイプラインの次のコマンドに渡します。
これは、パイプライン内のすべてのコマンドが実行されるまで続行されます。

次の例は、オブジェクトが1つのコマンドから次のコマンドに渡される方法を示しています。

```powershell
Get-ChildItem C: | where { $_.PsIsContainer -eq $false } | Format-List
```

最初のコマンドは、 `Get-ChildItem C:` ファイルシステムのルートディレクトリ内の各項目について、ファイルまたはディレクトリオブジェクトを返します。 File オブジェクトと directory オブジェクトは、パイプラインから2番目のコマンドに渡されます。

2番目のコマンドは、 `where { $_.PsIsContainer -eq $false }` すべてのファイルシステムオブジェクトの PsIsContainer プロパティを使用して、PsIsContainer プロパティの値が false (false) のファイルのみを選択し \$ ます。 フォルダーはコンテナーであり、PsIsContainer プロパティに True (true) という値が設定されて \$ いますが、これは選択されていません。

2番目のコマンドは、ファイルオブジェクトのみを3番目のコマンドに渡します。このコマンドは、 `Format-List` ファイルオブジェクトを一覧に表示します。

## <a name="see-also"></a>参照

[about_Methods](about_Methods.md)

[about_Object_Creation](about_Object_Creation.md)

[about_Properties](about_Properties.md)

[about_Pipelines](about_Pipelines.md)

[Get-Member](xref:Microsoft.PowerShell.Utility.Get-Member)
