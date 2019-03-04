---
title: XML のスキーマ リファレンスを書式設定 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ac6f7aaa-d0cc-4c7b-a341-85e736174579
caps.latest.revision: 21
ms.openlocfilehash: 4dfe27a5105d82fa18e35f965f92fad16d390a2a
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857788"
---
# <a name="format-schema-xml-reference"></a>書式設定スキーマ XML リファレンス

このセクションのトピックでは、書式設定ファイル (Format.ps1xml ファイル) を使用する XML 要素について説明します。 書式設定ファイルは、.NET オブジェクトの表示方法を定義します。オブジェクト自体は変わりません。

## <a name="in-this-section"></a>このセクションの内容

[TableControl (形式) の TableColumnHeader の alignment 要素](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md)列ヘッダー内のデータを表示する方法を定義します。

[TableControl (形式) の TableColumnItem の alignment 要素](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)行のデータを表示する方法を定義します。

[TableControl (形式) の AutoSize 要素](./autosize-element-for-tablecontrol-format.md)データのサイズに基づいて、列のサイズと列の数を調整するかどうかを指定します。

[WideControl (形式) の Autosize 要素](./autosize-element-for-widecontrol-format.md)データのサイズに基づいて、列のサイズと列の数を調整するかどうかを指定します。

[ColumnNumber 要素 WideControl (形式) の](./columnnumber-element-for-widecontrol-format.md)ワイド ビューに表示される列の数を指定します。

[構成要素 (形式)](./configuration-element-format.md)書式設定ファイルの最上位の要素を表します。

[構成 (形式) のコントロールの要素を制御](./control-element-for-controls-for-configuration-format.md)書式設定ファイルと、コントロールを参照するために使用される名前のすべてのビューで使用できる一般的なコントロールを定義します。

[コントロールが表示されます (形式) の要素を制御](./control-element-for-controls-for-view-format.md)ビュー、およびコントロールを参照するために使用される名前で使用できるコントロールを定義します。

[構成 (形式) の要素を制御](./controls-element-for-configuration-format.md)書式設定ファイルのすべてのビューで使用できる一般的なコントロールを定義します。

[要素が表示されます (形式) を制御](./controls-element-for-view-format.md)特定のビューで使用できるビュー コントロールを定義します。

[構成 (形式) のコントロールのカスタム コントロール要素](./customcontrol-element-for-control-for-controls-for-configuration-format.md)コントロールを定義します。 この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。

[コントロールが表示されます (形式) のコントロールのカスタム コントロール要素](./customcontrol-element-for-control-for-controls-for-view-format.md)ビューで使用されるコントロールを定義します。

[GroupBy (形式) のカスタム コントロール要素](./customcontrol-element-for-groupby-format.md)新しいグループを表示するカスタム コントロールを定義します。

[カスタム コントロール要素 (形式)](./customcontrol-element-for-groupby-format.md)ビューのカスタム コントロールの書式を定義します。

[ExpressionBinding の構成 (形式) のコントロールの要素を CustomControlName](./customcontrolname-element-for-expressionbinding-for-controls-for-configuration-format.md)コモン コントロールの名前を指定します。 この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。

[コントロールが表示されます (形式) の ExpressionBindine CustomControlName 要素](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)コモン コントロールまたはビューのコントロールの名前を指定します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

[GroupBy (形式) の要素を CustomControlName](./customcontrolname-element-for-groupby-format.md)新しいグループを表示するために使用するカスタム コントロールの名前を指定します。 この要素は、テーブル、リスト、ワイドまたはカスタム コントロールのビューを定義するときに使用されます。

[構成 (形式) のコントロールのカスタム コントロールの要素を CustomEntry](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)コモン コントロールの定義を提供します。 この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。

[コントロールが表示されます (形式) の CustomEntries CustomEntry 要素](./customentry-element-for-customentries-for-controls-for-view-format.md)コントロールの定義を提供します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

[表示 (形式) CustomEntries CustomEntry 要素](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)カスタム コントロールのビューの定義を提供します。

[GroupBy (形式) のカスタム コントロールの要素を CustomEntry](./customentry-element-for-customcontrol-for-groupby-format.md)コントロールの定義を提供します。 この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。

[構成 (形式) のカスタム コントロールの要素を CustomEntries](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)コモン コントロールの定義を提供します。 この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。

[コントロールが表示されます (形式) のカスタム コントロールの要素を CustomEntries](./customentries-element-for-customcontrol-for-controls-for-view-format.md)コントロールの定義を提供します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

[GroupBy (形式) のカスタム コントロールの要素を CustomEntries](./customentries-element-for-customcontrol-for-groupby-format.md)コントロールの定義を提供します。 この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。

[ビュー (形式) のカスタム コントロールの要素を CustomEntries](./customentries-element-for-customcontrol-for-view-format.md)カスタム コントロールのビューの定義を提供します。 カスタム コントロールのビューには、1 つまたは複数の定義を指定する必要があります。

[コントロールの構成の CustomEntry CustomItem 要素](./customitem-element-for-customentry-for-controls-for-configuration-format.md)コントロールによって表示するデータと表示方法を定義します。 この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。

[コントロールが表示されます (形式) の CustomEntry CustomItem 要素](./customitem-element-for-customentry-for-controls-for-view-format.md)コントロールによって表示するデータと表示方法を定義します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

[表示 (形式) CustomEntry CustomItem 要素](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)カスタム コントロールのビューで表示するデータと表示方法を定義します。 この要素は、カスタム コントロールのビューを定義するときに使用されます。

[GroupBy (形式) の CustomEntry CustomItem 要素](./customitem-element-for-customentry-for-groupby-format.md)カスタム コントロールのビューで表示するデータと表示方法を定義します。 この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。

[DefaultSettings 要素 (形式)](./defaultsettings-element-format.md)書式設定ファイルのすべてのビューに適用される一般的な設定を定義します。 一般的な設定に含めるコレクションを展開する方法を定義するテーブル内のテキストの折り返し、エラーを表示します。

[DisplayError 要素 (Frmat)](./displayerror-element-format.md) #ERR 文字列がデータの一部を表示するエラーが発生したときに表示されることを指定します。

[構成 (形式) のコントロールの CustomEntry EntrySelectedBy 要素](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)コモン コントロールまたは使用するには、このコントロールに必要な条件の定義を使用する .NET 型を定義します。 この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。

[コントロールが表示されます (形式) の CustomEntry EntrySelectedBy 要素](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)このコントロールの定義または条件を使用するには、この定義が存在する必要がありますを使用する .NET 型を定義します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

[表示 (形式) CustomEntry EntrySelectedBy 要素](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)このカスタム エントリまたは条件を使用するには、このエントリが存在する必要がありますを使用する .NET 型を定義します。

[EnumerableExpansion (形式) の要素を EntrySelectedBy](./entryselectedby-element-for-enumerableexpansion-format.md)この定義または条件を使用するには、この定義が存在する必要がありますを使用する .NET 型を定義します。

[GroupBy (形式) の CustomEntry EntrySelectedBy 要素](./entryselectedby-element-for-customentry-for-groupby-format.md)このコントロールの定義または条件を使用するには、この定義が存在する必要がありますを使用する .NET 型を定義します。 この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。

[ListControl (形式) の ListEntry EntrySelectedBy 要素](./entryselectedby-element-for-listentry-for-listcontrol-format.md)このリスト ビューの定義または条件を使用するには、この定義が存在する必要がありますを使用する .NET 型を定義します。 ほとんどの場合は、リスト ビューの 1 つだけ定義が必要です。 ただし、さまざまなオブジェクトのさまざまなデータを表示する同じリスト ビューを使用する場合は、リスト ビューの複数の定義を提供できます。

[TableRowEntry (形式) の要素を EntrySelectedBy](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)プロパティ値を持つ行に表示されて .NET 型を定義します。

[WideEntry (形式) の要素を EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md)この定義の表示幅が広いまたは条件を使用するには、この定義が存在する必要がありますを使用する .NET 型を定義します。

[EnumerableExpansion 要素 (形式)](./enumerableexpansion-element-format.md)ビューに表示されている場合にオブジェクトが展開された特定の .NET コレクションを定義します。

[EnumerableExpansions 要素 (形式)](./enumerableexpansions-element-format.md)ビューに表示されているときに .NET コレクション オブジェクトを展開する方法を定義します。

[ExpressionBinding の構成 (形式) のコントロールの要素を EnumerateCollection](./enumeratecollection-element-for-expressionbinding-for-controls-for-configuration-format.md)のコレクションの要素がコントロールによって表示されることを指定します。 この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。

[ExpressionBinding のビュー (形式) のコントロールの要素を EnumerateCollection](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md)のコレクションの要素が表示されることを指定します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

[式が表示されます (形式) のカスタム コントロールのバインド要素を EnumerateCollection](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)のコレクションの要素が表示されることを指定します。 この要素は、カスタム コントロールのビューを定義するときに使用されます。

[GroupBy (形式) の ExpressionBinding EnumerateCollection 要素](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)のコレクションの要素が表示されることを指定します。 この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。

[要素 (形式) を展開](./expand-element-format.md)この定義のコレクション オブジェクトを展開する方法を指定します。

[ExpressionBinding 要素の構成 (形式) のコントロールの CustomItem](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)コントロールによって表示されるデータを定義します。 この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。

[ExpressionBinding 要素のビュー (形式) のコントロールの CustomItem](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)コントロールによって表示されるデータを定義します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

[ExpressionBinding 要素のビュー (形式) のカスタム コントロールの CustomItem](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)コントロールによって表示されるデータを定義します。 この要素は、カスタム コントロールのビューを定義するときに使用されます。

[GroupBy (形式) の CustomItem ExpressionBinding 要素](./expressionbinding-element-for-customitem-for-groupby-format.md)コントロールによって表示されるデータを定義します。 この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。

[コントロールの構成 (形式) のフレームの FirstLineHanging 要素](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)データの最初の行が左にシフト文字の数を指定します。 この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。

[フレームのコントロールのビュー (形式) の要素を FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)データの最初の行が左にシフト文字の数を指定します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

[ビュー (形式) のカスタム コントロールのフレームの FirstLineHanging 要素](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)データの最初の行が左にシフト文字の数を指定します。 この要素は、カスタム コントロールのビューを定義するときに使用されます。

[GroupBy (形式) のフレームの FirstLineHanging 要素](./firstlinehanging-element-for-frame-for-groupby-format.md)データの最初の行が左にシフト文字の数を指定します。 この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。

[コントロールの構成 (形式) のフレームの FirstLineIndent 要素](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)データの最初の行が右側にシフトした文字数を指定します。 この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。

[フレームのコントロールのビュー (形式) の要素を FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-view-format.md)データの最初の行が右側にシフトした文字数を指定します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

[FirstLineIndent 要素](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)データの最初の行が右側にシフトした文字数を指定します。 この要素は、カスタム コントロールのビューを定義するときに使用されます。

[GroupBy (形式) のフレームの FirstLineIndent 要素](./firstlineindent-element-for-frame-for-groupby-format.md)データの最初の行が右側にシフトした文字数を指定します。 この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。

[ListItem (形式) の FormatString 要素](./formatstring-element-for-listitem-for-listcontrol-format.md)プロパティまたはスクリプトの値を表示する方法を定義するフォーマット パターンを指定します。

[FormatString 要素 (形式) TableColumnItem](./formatstring-element-for-tablecolumnitem-for-tablecontrol-format.md)テーブルのプロパティまたはスクリプトの値を表示する方法を定義するフォーマット パターンを指定します。

[FormatString 要素 WideControl (形式) の WideItem](./formatstring-element-for-wideitem-for-widecontrol-format.md)ビューで、プロパティまたはスクリプトの値を表示する方法を定義するフォーマット パターンを指定します。

[構成 (形式) のコントロールの CustomItem の要素をフレーム](./frame-element-for-customitem-for-controls-for-configuration-format.md)データを左または右にシフトなど、データを表示する方法を定義します。 この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。

[コントロールが表示されます (形式) の CustomItem の要素をフレーム](./frame-element-for-customitem-for-controls-for-view-format.md)データを左または右にシフトなど、データを表示する方法を定義します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

[CustomItem のビュー (形式) のカスタム コントロールの要素をフレーム](./frame-element-for-customitem-for-customcontrol-for-view-format.md)データを左または右にシフトなど、データを表示する方法を定義します。 この要素は、カスタム コントロールのビューを定義するときに使用されます。

[CustomItem の GroupBy (形式) の要素をフレーム](./frame-element-for-customitem-for-groupby-format.md)データを左または右にシフトなど、データを表示する方法を定義します。 この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。

[ビュー (形式) の GroupBy 要素](./groupby-element-for-view-format.md)Windows PowerShell がオブジェクトの新しいグループを表示する方法を定義します。

[HideTableHeaders 要素 (形式)](./hidetableheaders-element-format.md)テーブルのヘッダーが表示されないことを指定します。

[ExpressionBinding の構成 (形式) のコントロールの要素を ItemSelectionCondition](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)このコントロールを使用するのに必要な条件を定義します。 この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。

[ExpressionBinding のビュー (形式) のコントロールの要素を ItemSelectionCondition](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)このコントロールを使用するのに必要な条件を定義します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

[式が表示されます (形式) のカスタム コントロールのバインド要素を ItemSelectionCondition](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)このコントロールを使用するのに必要な条件を定義します。 コントロールの項目の指定できる選択条件の数に制限はありません。 この要素は、カスタム コントロールのビューを定義するときに使用されます。

[GroupBy (形式) の ExpressionBinding ItemSelectionCondition 要素](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)このコントロールを使用するのに必要な条件を定義します。 コントロールの項目の指定できる選択条件の数に制限はありません。 この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。

[ListItem (形式) の要素を ItemSelectionCondition](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)使用するには、このリスト項目が存在する必要がある条件を定義します。

[ListItem の ListControl(Format) の要素にラベルを付ける](./label-element-for-listitem-for-listcontrol-format.md)行のプロパティまたはスクリプトの値のラベルを指定します。

[GroupBy (形式) の要素にラベルを付ける](./label-element-for-groupby-format.md)新しいグループが発生したときに表示されるラベルを指定します。

[TableColumnHeader (形式) の要素にラベルを付ける](./label-element-for-tablecolumnheader-for-tablecontrol-format.md)列の上部に表示されるラベルを定義します。

[コントロールの構成 (形式) のフレームの LeftIndent 要素](./leftindent-element-for-frame-for-controls-for-configuration-format.md)左余白からのデータがシフト文字の数を指定します。 この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。

[フレームのコントロールのビュー (形式) の要素を LeftIndent](./leftindent-element-for-frame-for-controls-for-view-format.md)左余白からのデータがシフト文字の数を指定します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

[ビュー (形式) のカスタム コントロールのフレームの LeftIndent 要素](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)左余白からのデータがシフト文字の数を指定します。 この要素は、カスタム コントロールのビューを定義するときに使用されます。

[GroupBy (形式) のフレームの LeftIndent 要素](./leftindent-element-for-frame-for-groupby-format.md)左余白からのデータがシフト文字の数を指定します。 この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。

[ListControl 要素 (形式)](./listcontrol-element-format.md)ビューの一覧の形式を定義します。

[ListEntry 要素 (形式)](./listentry-element-for-listcontrol-format.md)リスト ビューの定義を提供します。

[ListEntries 要素 (形式)](./listentries-element-for-listcontrol-format.md)リスト ビューの行を表示する方法を定義します。

[ListItem 要素 (形式)](./listitem-element-for-listitems-for-listcontrol-format.md)プロパティまたはリスト ビューの行の値が表示されているスクリプトを定義します。

[リスト項目要素 (形式)](./listitems-element-for-listentry-for-listcontrol-format.md)プロパティとリスト ビューに表示されるスクリプトを定義します。

[構成 (形式) のコントロールのコントロールの要素を名前](./name-element-for-control-for-controls-for-configuration-format.md)コントロールの名前を指定します。 この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。

[SelectionSet (形式) の要素を名前](./name-element-for-selectionset-format.md)選択範囲のセットを参照するための名前を指定します。

[要素の名前を表示 (形式)](./name-element-for-view-format.md)ビューを識別するために使用される名前を指定します。

[改行要素の構成 (形式) のコントロールの CustomItem](./newline-element-for-customitem-for-controls-for-configuration-format.md)コントロールの表示に空白行を追加します。 この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。

[コントロールが表示されます (形式) の CustomItem の改行要素](./newline-element-for-customitem-for-controls-for-view-format.md)コントロールの表示に空白行を追加します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

[改行要素のビュー (形式) のカスタム コントロールの CustomItem](./newline-element-for-customitem-for-customcontrol-for-view-format.md)コントロールの表示に空白行を追加します。 この要素は、カスタム コントロールのビューを定義するときに使用されます。

[GroupBy (形式) の CustomItem に改行要素](./newline-element-for-customitem-for-groupby-format.md)コントロールの表示に空白行を追加します。 この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。

[ExpressionBinding の構成 (形式) のコントロールの PropertyName 要素](./propertyname-element-for-expressionbinding-for-controls-for-configuration-format.md)値を持つが、一般的なコントロールによって表示される、.NET プロパティを指定します。 この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。

[コントロールが表示されます (形式) の ExpressionBinding の PropertyName 要素](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md)コントロールによって表示される値を持つ .NET プロパティを指定します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

[ビュー (形式) のカスタム コントロールの ExpressionBinding の PropertyName 要素](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)コントロールによって表示される値を持つ .NET プロパティを指定します。 この要素がカスタム コントロールのビューを定義するときに使用されます。

[GroupBy (形式) の ExpressionBinding の PropertyName 要素](./propertyname-element-for-expressionbinding-for-groupby-format.md)コントロールによって表示される値を持つ .NET プロパティを指定します。 この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。

[GroupBy (形式) の PropertyName 要素](./propertyname-element-for-groupby-format.md).NET プロパティの値が変更されるたびに、新しいグループを開始するを指定します。

[PropertyName 要素の構成 (形式) のコントロールの ItemSeclectionCondition](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md) .NET プロパティ トリガーの条件を指定します。 このプロパティが存在するかを評価すると`true`条件が満たされると、およびコントロールを使用します。 この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。

[コントロールが表示されます (形式) の ItemSelectionCondition PropertyName 要素](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md).NET プロパティ トリガーの条件を指定します。 このプロパティが存在するかを評価すると`true`条件が満たされると、およびコントロールを使用します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

[ビューのカスタム コントロールの ItemSelectionCondition PropertyName 要素 (形式](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md).NET プロパティ トリガーの条件を指定します。 このプロパティが存在するかを評価すると`true`条件が満たされると、およびコントロールを使用します。 この要素は、カスタム コントロールのビューを定義するときに使用されます。

[GroupBy (形式) の ItemSelectionCondition PropertyName 要素](./propertyname-element-for-itemselectioncondition-for-groupby-format.md).NET プロパティ トリガーの条件を指定します。 このプロパティが存在するかを評価すると`true`条件が満たされると、およびコントロールを使用します。 この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。

[ListItem (形式) の ItemSelectionCondition PropertyName 要素](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md).NET プロパティ トリガーの条件を指定します。 このプロパティが存在するかを評価すると`true`条件が満たされ、ビューを使用します。 この要素は、リスト ビューを定義するときに使用されます。

[PropertyName ListControl (形式) を ListItem 要素](./propertyname-element-for-listitem-for-listcontrol-format.md).NET プロパティの値が一覧に表示を指定します。

[PropertyName 要素 EntrySelectedBy ListEntry (形式) 用の SelectionCondition](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md) .NET プロパティ トリガーの条件を指定します。 このプロパティが存在するかを評価すると`true`条件が満たされ、エントリが使用されます。 この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。

[コントロールが表示されます (形式) の SelectionCondition PropertyName 要素](./propertyname-element-for-selectioncondition-for-controls-for-view-format.md).NET プロパティ トリガーの条件を指定します。 このプロパティが存在するかを評価すると`true`条件が満たされ、エントリが使用されます。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

[PropertyName 要素のビュー (形式) のカスタム コントロールの SelectionCondition](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md) .NET プロパティ トリガーの条件を指定します。 このプロパティが存在するかを評価すると`true`条件が満たされ、定義を使用します。 この要素は、カスタム コントロールのビューを定義するときに使用されます。

[PropertyName 要素 EntrySelectedBy EnumerableExpansion (形式) 用の SelectionCondition](./propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md) .NET プロパティ トリガーの条件を指定します。 このプロパティが存在するかを評価すると`true`条件が満たされ、定義を使用します。

[GroupBy (形式) の SelectionCondition PropertyName 要素](./propertyname-element-for-selectioncondition-for-groupby-format.md).NET プロパティ トリガーの条件を指定します。 このプロパティが存在するかを評価すると`true`条件が満たされ、定義を使用します。 この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。

[PropertyName 要素 EmtrySelectedBy ListEntry (形式) 用の SelectionCondition](./propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md) .NET プロパティ トリガーの条件を指定します。 このプロパティが存在するかを評価すると`true`条件が満たされ、一覧のエントリを使用します。

[PropertyName 要素 EntrySelectedBy TableRowEntry (形式) 用の SelectionCondition](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md) .NET プロパティ トリガーの条件を指定します。 このプロパティが存在するかを評価すると`true`条件が満たされると、およびテーブル エントリが使用されます。

[PropertyName 要素 EntrySelectedBy WideEntry (形式) 用の SelectionCondition](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md) .NET プロパティ トリガーの条件を指定します。 このプロパティが存在するかを評価すると`true`条件が満たされ、定義を使用します。

[TableColumnItem (形式) の PropertyName 要素](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)行の列で値が表示されるプロパティを指定します。

[WideItem (形式) の PropertyName 要素](./propertyname-element-for-wideitem-for-widecontrol-format.md)ワイド ビューで値が表示されるオブジェクトのプロパティを指定します。

[コントロールの構成 (形式) のフレームの RightIndent 要素](./rightindent-element-for-frame-for-controls-for-configuration-format.md)右の余白からのデータがシフト文字の数を指定します。 この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。

[フレームのコントロールのビュー (形式) の要素を RightIndent](./rightindent-element-for-frame-for-controls-for-view-format.md)右の余白からのデータがシフト文字の数を指定します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

[RightIndent 要素](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)右の余白からのデータがシフト文字の数を指定します。 この要素は、カスタム コントロールのビューを定義するときに使用されます。

[GroupBy (形式) のフレームの RightIndent 要素](./rightindent-element-for-frame-for-groupby-format.md)右の余白からのデータがシフト文字の数を指定します。 この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。

[ExpressionBinding の構成 (形式) のコントロールの ScriptBlock 要素](./scriptblock-element-for-expressionbinding-for-controls-for-configuration-format.md)値を持つが、一般的なコントロールによって表示されるスクリプトを指定します。 この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。

[コントロールが表示されます (形式) の ExpressionBinding の ScriptBlock 要素](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md)値を持つが、コントロールによって表示されるスクリプトを指定します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

[ScriptBlock 要素の表示 (形式) CustomCustomControl ExpressionBinding](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)値を持つが、コントロールによって表示されるスクリプトを指定します。 この要素は、カスタム コントロールのビューを定義するときに使用されます。

[GroupBy (形式) の ExpressionBinding の ScriptBlock 要素](./scriptblock-element-for-expressionbinding-for-groupby-format.md)値を持つが、コントロールによって表示されるスクリプトを指定します。 この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。

[GroupBy (形式) の ScriptBlock 要素](./scriptblock-element-for-groupby-format.md)値が変更されるたびに、新しいグループを開始するスクリプトを指定します。

[ScriptBlock 要素の構成 (形式) のコントロールの ItemSelectionCondition](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)条件をトリガーするスクリプトを指定します。 このスクリプトを評価するときに`true`条件が満たされると、およびコントロールを使用します。 この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。

[コントロールが表示されます (形式) の ItemSelectionCondition の ScriptBlock 要素](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)条件をトリガーするスクリプトを指定します。 このスクリプトを評価するときに`true`条件が満たされると、およびコントロールを使用します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

[ビュー (形式) のカスタム コントロールの ItemSelectionCondition の ScriptBlock 要素](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)条件をトリガーするスクリプトを指定します。 このスクリプトを評価するときに`true`条件が満たされると、およびコントロールを使用します。 この要素は、カスタム コントロールのビューを定義するときに使用されます。

[GroupBy (形式) の ItemSelectionCondition の ScriptBlock 要素](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md)条件をトリガーするスクリプトを指定します。 このスクリプトを評価するときに`true`条件が満たされると、およびコントロールを使用します。 この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。

[ItemSelectionCondition ListControl (形式) 用の ScriptBlock 要素](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)条件をトリガーするスクリプトを指定します。 このスクリプトを評価するときに`true`条件が満たされ、リスト項目を使用します。 この要素は、リスト ビューを定義するときに使用されます。

[ListItem (形式) の ScriptBlock 要素](./scriptblock-element-for-listitem-for-listcontrol-format.md)値を一覧の行に表示するスクリプトを指定します。

[ScriptBlock 要素の構成 (形式) のコントロールの SelectionCondition](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)条件をトリガーするスクリプトを指定します。 このスクリプトを評価するときに`true`条件が満たされ、定義を使用します。 この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。

[コントロールが表示されます (形式) の SelectionCondition の ScriptBlock 要素](./scriptblock-element-for-selectioncondition-for-controls-for-view-format.md)条件をトリガーするスクリプトを指定します。 このスクリプトを評価するときに`true`条件が満たされ、定義を使用します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

[ビュー (形式) のカスタム コントロールの SelectionCondition の ScriptBlock 要素](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)条件をトリガーするスクリプトを指定します。 このスクリプトを評価するときに`true`条件が満たされ、定義を使用します。 この要素は、カスタム コントロールのビューを定義するときに使用されます。

[SelectionCondition EntrySelectedBy EnumerableExpansion (形式) のための ScriptBlock 要素](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)条件をトリガーするスクリプトを指定します。

[GroupBy (形式) の SelectionCondition の ScriptBlock 要素](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-groupby-format.md)条件をトリガーするスクリプトを指定します。 このスクリプトを評価するときに`true`条件が満たされ、定義を使用します。 この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。

[SelectionCondition EntrySelectedBy ListEntry (形式) のための ScriptBlock 要素](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)条件をトリガーするスクリプトを指定します。 このスクリプトを評価するときに`true`条件が満たされ、一覧のエントリを使用します。

[SelectionCondition EntrySelectedBy TableRowEntry (形式) のための ScriptBlock 要素](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)条件をトリガーするスクリプト ブロックを指定します。 このスクリプトを評価するときに`true`条件が満たされると、およびテーブル エントリが使用されます。

[SelectionCondition EntrySelectedBy WideEntry (形式) のための ScriptBlock 要素](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)条件をトリガーするスクリプトを指定します。 このスクリプトを評価するときに`true`条件が満たされると、およびワイド エントリの定義を使用します。

[TableColumnItem (形式) の ScriptBlock 要素](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)行の列で値が表示されるスクリプトを指定します。

[WideItem (形式) の ScriptBlock 要素](./scriptblock-element-for-wideitem-for-widecontrol-format.md)値をワイド ビューで表示するスクリプトを指定します。

[構成 (形式) の CustomEntry EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)使用する一般的なコントロールの定義を満たす必要がある条件を定義します。 この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。

[コントロールが表示されます (形式) の EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)コントロールの定義を使用するのに必要な条件を定義します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

[ビュー (形式) のカスタム コントロールの EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)コントロールの定義が使用するのに必要な条件を定義します。 この要素は、カスタム コントロールのビューを定義するときに使用されます。

[EnumerableExpansion (形式) の EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)この定義のコレクション オブジェクトの展開に必要な条件を定義します。

[GroupBy (形式) の EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)コントロールの定義が使用するのに必要な条件を定義します。 この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。

[ListEntry (形式) の EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)リスト ビューのこの定義を使用する必要がある条件を定義します。 リスト定義に指定できる選択条件の数に制限はありません。

[TableRowEntry (形式) の EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)テーブル ビューのこの定義に使用する必要がある条件を定義します。 テーブルの定義に指定できる選択条件の数に制限はありません。

[WideEntry (形式) の EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)この定義を使用するのに必要な条件を定義します。 ワイド エントリの定義に指定できる選択条件の数に制限はありません。

[SelectionSet 要素 (形式)](./selectionset-element-format.md)セットの名前で参照できる .NET オブジェクトのセットを定義します。

[構成 (形式) のコントロールの EntrySelectedBy SelectionSetName 要素](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)一連のコントロールのこの定義を使用する .NET 型を指定します。 この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。

[コントロールが表示されます (形式) の EntrySelectedBy SelectionSetName 要素](./selectionsetname-element-for-entryselectedby-for-controls-for-view-format.md)一連のコントロールのこの定義を使用する .NET 型を指定します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

[CustomEntry (形式) の EntrySelectedBy SelectionSetName 要素](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)リストのエントリの .NET オブジェクトのセットを指定します。 エントリに指定できる選択セットの数に制限はありません。

[EnumerableExpansion (形式) の EntrySelectedBy SelectionSetName 要素](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)この定義で展開される .NET 型のセットを指定します。

[GroupBy (形式) の EntrySelectedBy SelectionSetName 要素](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)リストのエントリの .NET オブジェクトのセットを指定します。 エントリに指定できる選択セットの数に制限はありません。 この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。

[ListEntry (形式) の EntrySelectedBy SelectionSetName 要素](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)リストのエントリの .NET オブジェクトのセットを指定します。 エントリに指定できる選択セットの数に制限はありません。

[TableRowEntry (形式) の EntrySelectedBy SelectionSetName 要素](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)一連の .NET 型、使用して、テーブル ビューのこのエントリを指定します。 エントリに指定できる選択セットの数に制限はありません。

[WideEntry (形式) の EntrySelectedBy SelectionSetName 要素](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)一連の定義については、.NET オブジェクトを指定します。 これらのオブジェクトのいずれかが表示されるたびに、定義を使用します。

[構成 (形式) のコントロールの SelectionCondition SelectionSetName 要素](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)条件をトリガーする .NET 型のセットを指定します。 このセット内の型のいずれかが存在して、条件が満たされると、このコントロールを使用して、オブジェクトが表示されます。 この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。

[コントロールが表示されます (形式) の SelectionCondition SelectionSetName 要素](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)条件をトリガーする .NET 型のセットを指定します。 このセット内の型のいずれかが存在するときに、条件が満たされ、このコントロールを使用して、オブジェクトが表示されます。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

[表示 (形式) CustomEntry EntrySelectedBy 要素](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)条件をトリガーする .NET 型のセットを指定します。 このセット内の型のいずれかが存在するときに、条件が満たされ、このコントロールを使用して、オブジェクトが表示されます。 この要素は、カスタム コントロールのビューを定義するときに使用されます。

[EntrySelectedBy EnumerableExpansion (形式) 用の SelectionCondition SelectionSetName 要素](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)条件をトリガーする .NET 型のセットを指定します。 このセット内の型のいずれかが存在するときに、条件が満たされます。

[GroupBy (形式) の SelectionCondition SelectionSetName 要素](./selectionsetname-element-for-selectioncondition-for-groupby-format.md)条件をトリガーする .NET 型のセットを指定します。 このセット内の型のいずれかが存在して、条件が満たされると、このコントロールを使用して、オブジェクトが表示されます。 この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。

[EntrySelectedBy ListEntry (形式) 用の SelectionCondition SelectionSetName 要素](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format.md)条件をトリガーする .NET 型のセットを指定します。 このセット内の型のいずれかが存在して、条件が満たされると、リスト ビューのこの定義を使用して、オブジェクトが表示されます。

[EntrySelectedBy TableRowEntry (形式) 用の SelectionCondition SelectionSetName 要素](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)条件をトリガーする .NET 型のセットを指定します。 このセット内の型のいずれかが存在して、条件が満たされると、テーブル ビューのこの定義を使用して、オブジェクトが表示されます。

[EntrySelectedBy WideEntry (形式) 用の SelectionCondition SelectionSetName 要素](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)条件をトリガーする .NET 型のセットを指定します。 このセット内の型のいずれかが存在して、条件が満たされると、表示幅が広いは、この定義を使用して、オブジェクトが表示されます。

[ViewSelectedBy (形式) の要素を SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md)ビューで表示されている .NET オブジェクトのセットを指定します。

[SelectionSets 要素 (形式)](./selectionsets-element-format.md)個々 の形式のビューで使用できる .NET オブジェクトのセットを定義します。

[ShowError 要素 (形式)](./showerror-element-format.md)のデータを表示中にエラーが発生したときに、完全なエラー レコードが表示されることを指定します。

[TableControl (形式) の TableHeaders TableColumnHeader 要素](./tablecolumnheader-element-format.md)ラベル、列の幅と、テーブルの列のラベルの配置を定義します。

[TableColumnItem 要素 (形式)](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)プロパティまたは値を持つが、行の列に表示されているスクリプトを定義します。

[TableColumnItems 要素 (形式)](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)プロパティまたは行の表示が値を持つスクリプトを定義します。

[TableControl 要素 (形式)](./tablecontrol-element-format.md)ビューのテーブル形式を定義します。

[TableHeaders 要素 (形式)](./tableheaders-element-format.md)テーブルの列のヘッダーを定義します。

[TableRowEntries 要素 (形式)](./tablerowentries-element-for-tablecontrol-format.md)テーブルの行を定義します。

[TableRowEntry 要素 (形式)](./tablerowentry-element-for-tablerowentroes-for-tablecontrol-format.md)テーブルの行に表示されるデータを定義します。

[テキスト要素の構成 (形式) のコントロールの CustomItem](./text-element-for-customitem-for-controls-for-configuration-format.md)データ、およびデータをインデントする空白文字を囲む角かっこ、ラベルなど、コントロールによって表示されるデータに追加されるテキストを指定します。 この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。

[CustomItem ビュー (形式) のコントロールのテキスト要素](./text-element-for-customitem-for-controls-for-view-format.md)データ、およびデータをインデントする空白文字を囲む角かっこ、ラベルなど、コントロールによって表示されるデータに追加されるテキストを指定します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

[CustomItem (形式) のテキスト要素](./text-element-for-customitem-for-customview-for-view-format.md)データ、およびデータをインデントする空白文字を囲む角かっこ、ラベルなど、コントロールによって表示されるデータに追加されるテキストを指定します。 この要素は、カスタム コントロールのビューを定義するときに使用されます。

[テキスト要素の GroupBy (形式) の CustomItem](./text-element-for-customitem-for-groupby-format.md)データ、およびデータをインデントする空白文字を囲む角かっこ、ラベルなど、コントロールによって表示されるデータに追加されるテキストを指定します。 この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。

[構成 (形式) のコントロールの EntrySelectedBy の TypeName 要素](./typename-element-for-entryselectedby-for-controls-for-configuration-format.md)コントロールのこの定義を使用する .NET 型を指定します。 この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。

[コントロールが表示されます (形式) の EntrySelectedBy の TypeName 要素](./typename-element-for-entryselectedby-for-controls-for-view-format.md)コントロールのこの定義を使用する .NET 型を指定します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

[TypeName 要素の表示 (形式) CustomEntry EntrySelectedBy](./typename-element-for-entryselectedby-for-customentry-for-view-format.md)このカスタム コントロールのビューの定義を使用する .NET 型を指定します。 定義に指定できる型の数に制限はありません。

[EntrySelectedBy EnumerableExpansion (形式) 用の TypeName 要素](./typename-element-for-entryselectedby-for-enumerableexpansion-format.md)この定義によって展開は、.NET 型を指定します。 この要素は、既定の設定を定義するときに使用されます。

[GroupBy (形式) の EntrySelectedBy の TypeName 要素](./typename-element-for-entryselectedby-for-groupby-format.md)この定義のカスタム コントロールを使用する .NET 型を指定します。 この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。

[EntrySelectedBy ListControl (形式) 用の TypeName 要素](./typename-element-for-entryselectedby-for-listcontrol-format.md)リスト ビューのこのエントリを使用する .NET 型を指定します。 一覧のエントリに指定できる型の数に制限はありません。

[EntrySelectedBy TableRowEntry (形式) 用の TypeName 要素](./typename-element-for-entryselectedby-for-tablecontrol-format.md)テーブル ビューのこのエントリを使用する .NET 型を指定します。 テーブルのエントリに指定できる型の数に制限はありません。

[EntrySelectedBy WideEntry (形式) 用の TypeName 要素](./typename-element-for-entryselectedby-for-wideentry-format.md)定義については、.NET 型を指定します。 このオブジェクトが表示されるたびに、定義を使用します。

[構成 (形式) のコントロールの SelectionCondition の TypeName 要素](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)条件をトリガーする .NET 型を指定します。 この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。

[コントロールが表示されます (形式) の SelectionCondition の TypeName 要素](./typename-element-for-selectioncondition-for-controls-for-view-format.md)条件をトリガーする .NET 型を指定します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

[ビュー (形式) のカスタム コントロールの SelectionCondition の TypeName 要素](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)条件をトリガーする .NET 型を指定します。 この要素は、カスタム コントロールのビューを定義するときに使用されます。

[SelectionCondition EntrySelectedBy EnumerableExpansion (形式) のための TypeName 要素](./typename-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)条件をトリガーする .NET 型を指定します。

[GroupBy (形式) の SelectionCondition の TypeName 要素](./typename-element-for-selectioncondition-for-groupby-format.md)条件をトリガーする .NET 型を指定します。 この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。

[SelectionCondition EntrySelectedBy ListControl (形式) のための TypeName 要素](./typename-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)条件をトリガーする .NET 型を指定します。 この型が存在するときに、一覧のエントリが使用されます。

[SelectionCondition EntrySelectedBy TableRowEntry (形式) のための TypeName 要素](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)条件をトリガーする .NET 型を指定します。 この型が存在して、条件が満たされると、テーブルの行を使用します。

[SelectionCondition EntrySelectedBy WideEntry (形式) のための TypeName 要素](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)条件をトリガーする .NET 型を指定します。 この型が存在する場合は、定義を使用します。

[種類 (形式) の TypeName 要素](./typename-element-for-types-format.md)選択セットに属しているオブジェクトの .NET 型を指定します。

[ViewSelectedBy (形式) の TypeName 要素](./typename-element-for-viewselectedby-format.md)ビューによって表示される .NET オブジェクトを指定します。

[型の要素 (形式)](./types-element-for-selectionset-format.md)設定で選択されている .NET オブジェクトを定義します。

[要素 (形式) を表示](./view-element-format.md)1 つまたは複数の .NET オブジェクトを表示するために使用するビューを定義します。

[ViewDefinitions 要素 (形式)](./viewdefinitions-element-format.md)オブジェクトを表示するために使用するビューを定義します。

[ViewSelectedBy 要素 (形式)](./viewselectedby-element-format.md)ビューで表示されている .NET オブジェクトを定義します。

[WideControl 要素 (形式)](./widecontrol-element-format.md)全体 (1 つの値) の一覧は、ビューの形式を定義します。 このビューには、1 つのプロパティの値または各オブジェクトのスクリプトの値が表示されます。

[WideEntries 要素 (形式)](./wideentries-element-for-widecontrol-format.md)ワイド ビューの定義を提供します。 表示幅が広いには、1 つまたは複数の定義を指定する必要があります。

[WideEntry 要素 (形式)](./wideentry-element-for-widecontrol-format.md)ワイド ビューの定義を提供します。

[WideItem 要素 (形式)](./wideitem-element-for-widecontrol-format.md)プロパティまたは値が表示されているスクリプトを定義します。

[幅要素 (形式)](./width-element-for-tablecolumnheader-for-tablecontrol-format.md) (文字) で、列の幅を定義します。

[要素 (形式) をラップ](./wrap-element-for-tablerowentry-for-tablecontrl-format.md)次の行を列の幅を超えるテキストが表示されることを指定します。

[WrapTables 要素 (形式)](./wraptables-element-format.md)データが列の幅より長い場合、次の行にテーブルのセルにデータを移動することを指定します。

## <a name="see-also"></a>参照

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
