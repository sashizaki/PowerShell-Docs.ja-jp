---
title: 書式設定ファイルを作成する方法 (. format.ps1xml) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb568878-f63e-4561-98e2-16ee2ac7559d
caps.latest.revision: 8
ms.openlocfilehash: e97e9ddb1bf81ba66e5f3cedddd22e3a861ce228
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862968"
---
# <a name="how-to-create-a-formatting-file-formatps1xml"></a>書式設定ファイルを作成する方法 (.format.ps1xml)

このトピックでは、書式設定ファイルを作成する方法を説明します (. format.ps1xml)。

> [!NOTE]
> Windows PowerShell によって提供されるファイルの 1 つのコピーを作成して、書式設定ファイルを作成することもできます。 既存のファイルのコピーを作成する場合は、既存のデジタル署名を削除し、新しいファイルに独自の署名を追加します。

### <a name="to-create-a-formatps1xml-file"></a>作成する。 format.ps1xml ファイル。

1. メモ帳などのエディター、テキストを使用して、テキスト ファイル (.txt) を作成します。

2. 書式設定ファイルには、次の行をコピーします。

   ```xml
   <?xml version="1.0" encoding="utf-8" ?>
   <Configuration>
   <ViewDefinitions>
   </ViewDefinitions>
   </Configuration>
   ```

   - \<構成 >\<設定 > タグ定義のルート`Configuration`ノード。 その他のすべての XML タグは、このノード内で囲まれます。

   - <ViewDefinitions> </ViewDefinitions>タグを定義、`ViewDefinitions`ノード。 このノード内のすべてのビューが定義されます。

3. Windows PowerShell のインストール フォルダーに、モジュールのフォルダー、またはモジュール フォルダーのサブフォルダーにファイルを保存します。 ファイルを保存するときに、次の名前形式を使用:`MyFile.format.ps1xml`します。 書式設定ファイルを使用する必要があります、`.format.ps1xml`拡張機能。

   書式設定ファイルにビューを追加する準備が整いました。 書式設定ファイルで定義できるビューの数に制限はありません。 各オブジェクト、同じオブジェクトに複数のビュー、または複数のオブジェクトによって使用される 1 つのビューの 1 つのビューを追加することができます。

## <a name="see-also"></a>参照

[Windows PowerShell の書式設定の書き込みとファイルの種類](./writing-a-powershell-formatting-file.md)
