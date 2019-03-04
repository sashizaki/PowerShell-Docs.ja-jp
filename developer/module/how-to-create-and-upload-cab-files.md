---
title: 作成して、CAB ファイルをアップロードする方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8d35f233-5447-48a2-a961-9fbca763262b
caps.latest.revision: 7
ms.openlocfilehash: 9928a0b31a57d42eb39cea1af0509613c483caf7
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858648"
---
# <a name="how-to-create-and-upload-cab-files"></a>CAB ファイルを作成してアップロードする方法

このトピックでは、ヘルプの更新可能な CAB ファイルを作成し、更新可能なヘルプ コマンドレットが検索できる場所の場所にアップロードする方法について説明します。

## <a name="how-to-create-and-upload-updatable-help-cab-files"></a>作成して、更新可能なヘルプの CAB ファイルをアップロードする方法

更新可能なヘルプ機能を使用すると、複数の言語と文化のモジュールの新しいまたは更新されたヘルプ ファイルを配信します。 モジュールの更新可能なヘルプ パッケージを 1 つの HelpInfo XML ファイルから成ると 1 つまたは複数のキャビネット (します。CAB) ファイル。 各 CAB ファイルには、1 つの UI カルチャでモジュールのヘルプ ファイルが含まれています。 更新可能なヘルプの CAB ファイルを作成するのにには、次の手順を使用します。

1. UI カルチャでモジュールのヘルプ ファイルを整理します。 各ヘルプの更新可能な CAB ファイルには、1 つの UI カルチャの 1 つのモジュールのヘルプ ファイルが含まれています。 複数のヘルプに、モジュールごとに別の UI カルチャ用の CAB ファイルを配信できます。

2. 確認するヘルプ ファイル更新可能なヘルプで許可されているファイルの種類のみを含めるし、ヘルプ ファイルのスキーマに対して検証します。 場合、`Update-Help`コマンドレットには、正しくないか許可されている型ではないファイルが検出すると、無効なファイルはインストールされませんし、cab ファイルからファイルのインストールを停止します。 許可されているファイルの種類の一覧は、次を参照してください。[更新可能なヘルプ CAB ファイルのファイルの種類が許可される](./file-types-permitted-in-an-updatable-help-cab-file.md)します。

3. ヘルプ ファイルにデジタル署名します。 デジタル署名が必須ではありませんが、ベスト プラクティスは。

4. すべてのヘルプが新しいファイルだけでなくのカルチャまたは変更されてください、UI でモジュールのファイルが含まれます。 CAB ファイルが完全でない場合、最初にヘルプ ファイルをダウンロードまたはすべての更新をダウンロードしないユーザーはありませんすべてのモジュールのヘルプ ファイル。

5. MakeCab.exe などのキャビネット ファイルを作成するユーティリティを使用します。 Windows PowerShell では、CAB ファイルを作成するコマンドレットは含まれません。

6. CAB ファイルの名前を付けます。 詳細については、次を参照してください。[更新可能なヘルプ CAB ファイルの名前を付ける方法](./how-to-name-an-updatable-help-cab-file.md)します。

7. 指定された場所に、モジュール用の CAB ファイルをアップロード、 **HelpContentUri**モジュールの HelpInfo XML ファイル内の要素。 指定された場所に HelpInfo XML ファイルをアップロード、 **HelpInfoUri**モジュール マニフェストのキー。 **HelpContentUri**と**HelpInfoUri**同じ場所を指すことができます。

> [!CAUTION]
> 値、 **HelpInfoUri**キーと**HelpContentUri**要素は、"http"または"https"で始まる必要があります。 値は、インターネット上の場所を示す必要があり、ファイル名を含めることはできません。