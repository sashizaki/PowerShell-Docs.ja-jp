---
title: HelpInfo XML ファイルを作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3971ce1f-271c-4938-a9d3-47ff3aaf7219
caps.latest.revision: 9
ms.openlocfilehash: 7df9764fd573b75f285fec592448a550e481bea3
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367321"
---
# <a name="how-to-create-a-helpinfo-xml-file"></a>HelpInfo XML ファイルを作成する方法

このセクションのこのトピックでは、Windows PowerShell の更新可能なヘルプ機能について、"HelpInfo XML ファイル" と呼ばれるヘルプ情報ファイルを作成および設定する方法について説明します。

## <a name="helpinfo-xml-file-overview"></a>HelpInfo XML ファイルの概要

HelpInfo XML ファイルは、モジュールの更新可能なヘルプに関する主要な情報源です。 これには、モジュールのヘルプファイルの場所、サポートされている UI カルチャ、およびユーザーが最新のヘルプファイルを持っているかどうかを判断するために更新可能なヘルプが使用するバージョン番号が含まれます。

モジュールに複数の UI カルチャ用の複数のヘルプファイルが含まれている場合でも、各モジュールには HelpInfo XML ファイルが1つだけあります。 モジュールの作成者は、HelpInfo XML ファイルを作成し、モジュールマニフェストの**Helpinfouri**キーによって指定されたインターネット上の場所に配置します。 モジュールのヘルプファイルが更新されてアップロードされると、モジュールの作成者は HelpInfo XML ファイルを更新し、元の HelpInfo XML ファイルを新しいバージョンに置き換えます。

HelpInfo XML ファイルは慎重に管理することが重要です。 新しいファイルをアップロードしても、バージョン番号の増分を忘れた場合は、更新可能なヘルプによってユーザーのコンピューターに新しいファイルがダウンロードされません。 新しい UI カルチャのヘルプファイルを追加しても、HelpInfo XML ファイルを更新したり、正しい場所に配置したりしないと、更新可能なヘルプで新しいファイルがダウンロードされません。

## <a name="in-this-section"></a>このセクションの内容

このセクションには、次のトピックがあります。

- [HelpInfo XML スキーマ](./helpinfo-xml-schema.md)

- [HelpInfo XML サンプルファイル](./helpinfo-xml-sample-file.md)

- [HelpInfo XML ファイルに名前を指定する方法](./how-to-name-a-helpinfo-xml-file.md)

- [HelpInfo XML バージョン番号を設定する方法](./how-to-set-helpinfo-xml-version-numbers.md)

## <a name="see-also"></a>参照

[更新可能なヘルプのサポート](./supporting-updatable-help.md)