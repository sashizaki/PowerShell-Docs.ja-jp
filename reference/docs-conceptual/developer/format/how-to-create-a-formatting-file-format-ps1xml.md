---
title: 書式設定ファイル (types.ps1xml) を作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb568878-f63e-4561-98e2-16ee2ac7559d
caps.latest.revision: 8
ms.openlocfilehash: e97e9ddb1bf81ba66e5f3cedddd22e3a861ce228
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363621"
---
# <a name="how-to-create-a-formatting-file-formatps1xml"></a>書式設定ファイルを作成する方法 (.format.ps1xml)

このトピックでは、書式設定ファイル (types.ps1xml) を作成する方法について説明します。

> [!NOTE]
> また、Windows PowerShell によって提供されるいずれかのファイルのコピーを作成することによって、フォーマットファイルを作成することもできます。 既存のファイルのコピーを作成する場合は、既存のデジタル署名を削除し、独自の署名を新しいファイルに追加します。

### <a name="to-create-a-formatps1xml-file"></a>Types.ps1xml ファイルを作成します。

1. メモ帳などのテキストエディターを使用して、テキストファイル (.txt) を作成します。

2. 次の行を書式設定ファイルにコピーします。

   ```xml
   <?xml version="1.0" encoding="utf-8" ?>
   <Configuration>
   <ViewDefinitions>
   </ViewDefinitions>
   </Configuration>
   ```

   - \<構成 >\</構成 > タグによって、ルート `Configuration` ノードが定義されます。 その他のすべての XML タグは、このノード内で囲まれます。

   - タグ<ViewDefinitions></ViewDefinitions>によって、`ViewDefinitions` ノードが定義されます。 すべてのビューは、このノード内で定義されます。

3. Windows PowerShell のインストールフォルダー、モジュールフォルダー、またはモジュールフォルダーのサブフォルダーにファイルを保存します。 ファイルを保存するときは、次の名前形式を使用します: `MyFile.format.ps1xml`。 フォーマットファイルでは、`.format.ps1xml` 拡張子を使用する必要があります。

   これで、書式設定ファイルにビューを追加する準備ができました。 書式設定ファイルで定義できるビューの数に制限はありません。 オブジェクトごとに1つのビュー、同じオブジェクトに対して複数のビュー、または複数のオブジェクトで使用される1つのビューを追加できます。

## <a name="see-also"></a>参照

[Windows PowerShell のフォーマットファイルと型ファイルの作成](./writing-a-powershell-formatting-file.md)
