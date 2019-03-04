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
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853268"
---
# <a name="how-to-create-a-helpinfo-xml-file"></a>HelpInfo XML ファイルを作成する方法

このセクションでは、このトピックでは、作成し、一般的"HelpInfo XML ファイルが、"Windows PowerShell の更新可能なヘルプ機能と呼ばれる、ヘルプ情報ファイルを設定する方法について説明します。

## <a name="helpinfo-xml-file-overview"></a>HelpInfo XML ファイルの概要

HelpInfo XML ファイルは、主要なモジュールの更新可能なヘルプについての情報源です。 これには、モジュール、サポートされている UI カルチャ、および更新可能なヘルプを使用して、ユーザーが最新のヘルプ ファイルを持つかどうかを決定するバージョン番号のヘルプ ファイルの場所が含まれます。

各モジュールは、モジュールには、複数の UI カルチャ用の複数のヘルプ ファイルが含まれています。 場合でも、1 つだけの HelpInfo XML ファイルを持っています。 モジュールの作成者が HelpInfo XML ファイルを作成しで指定されたインターネット上の場所に配置、 **HelpInfoUri**モジュール マニフェストでキー。 モジュールのヘルプ ファイルが更新され、アップロード、ときに、モジュールの作成者は HelpInfo XML ファイルを更新し、元の HelpInfo XML ファイルを新しいバージョンに置き換えます。

HelpInfo XML ファイルを慎重に維持する必要があります。 新しいファイルをアップロードする場合は、バージョン番号をインクリメントすることを忘れないで更新可能なヘルプ ユーザーのコンピューターの新しいファイルはダウンロードされません。 新しい UI カルチャのヘルプ ファイルの追加が HelpInfo XML ファイルを更新または適切な場所に配置場合、更新可能なヘルプと新しいファイルがダウンロードされません。

## <a name="in-this-section"></a>このセクションの内容

このセクションには、次のトピックがあります。

- [HelpInfo XML スキーマ](./helpinfo-xml-schema.md)

- [HelpInfo XML ファイルのサンプル](./helpinfo-xml-sample-file.md)

- [HelpInfo XML ファイル名を指定する方法](./how-to-name-a-helpinfo-xml-file.md)

- [HelpInfo XML バージョン番号を設定する方法](./how-to-set-helpinfo-xml-version-numbers.md)

## <a name="see-also"></a>参照

[更新可能なヘルプのサポート](./supporting-updatable-help.md)