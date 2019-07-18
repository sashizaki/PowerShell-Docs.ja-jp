---
title: '更新可能なヘルプの作成: ステップ バイ ステップ |Microsoft Docs'
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10098160-c6b4-4339-b8ff-2c4f8cc0699b
caps.latest.revision: 13
ms.openlocfilehash: fbc77cc0fafce93d239da1c459d4b761b21ef3cb
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62082126"
---
# <a name="updatable-help-authoring-step-by-step"></a>更新可能なヘルプの作成: ステップバイステップ

このドキュメントでは、更新可能なヘルプの作成プロセスの手順が一覧表示します。

## <a name="authoring-updatable-help-step-by-step"></a>更新可能なヘルプを作成するには。ステップバイステップ

更新可能なヘルプは、エンドユーザー向けに設計されていますが、モジュールの作成者に多大なメリットを提供およびヘルプのライター、コンテンツを追加する機能も含まれますエラーを修正、複数の UI カルチャで配信後、ユーザーのコメントと、要求に応答しますモジュールが付属しています。 このトピックでは、パッケージ化する方法について説明し、アップロードのヘルプ ファイルをユーザーがダウンロードしてそれらを使用してインストールできるように、 [Update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)と[Save-help](/powershell/module/Microsoft.PowerShell.Core/Save-Help)コマンドレット。

次の手順では、更新可能なヘルプをサポートしているプロセスの概要を示します。

### <a name="step-1-find-an-internet-site-for-your-help-files"></a>手順 1:インターネット サイトのヘルプ ファイルを検索します。

更新可能なヘルプの作成の最初の手順では、モジュールのヘルプ ファイルをインターネット上の場所を検索します。 実際には、2 つの場所を使用することができます。 インターネット上の 1 つの場所とインターネット上の別の場所にあるヘルプ コンテンツ CAB ファイルには、モジュールのヘルプ情報ファイル (HelpInfo XML - 以下で説明) を保持できます。 すべてヘルプ コンテンツ用の CAB ファイルをモジュールは、同じ場所にある必要があります。 さまざまなモジュールのヘルプ コンテンツ CAB ファイルは、同じ場所に配置できます。

### <a name="step-2-add-a-helpinfouri-key-to-your-module-manifest"></a>手順 2:HelpInfoURI キー、モジュール マニフェストを追加します。

追加、 **HelpInfoURI**がモジュール マニフェスト キー。 キーの値は、モジュールの HelpInfo XML 情報ファイルの場所の統一リソース識別子 (URI) です。 セキュリティ、アドレスは、"http"または"https"で始まる必要があります。 URI は、インターネット上の場所を指定する必要がありますが、HelpInfo XML ファイルの名前を含めることはできません。

たとえば、次のように入力します。

```powershell

@{
RootModule = TestModule.psm1
ModuleVersion = '2.0'
HelpInfoURI = 'http://go.microsoft.com/fwlink/?LinkID=0123'
}
```

### <a name="step-3-create-a-helpinfo-xml-file"></a>手順 3:HelpInfo XML ファイルを作成します。

HelpInfo XML ファイルには、ヘルプ ファイルとサポートされている各 UI カルチャでモジュールの最新のヘルプ ファイルのバージョン番号のインターネット上の場所の URI が含まれています。 すべての Windows PowerShell モジュールでは、1 つの HelpInfo XML ファイルがあります。 編集または HelpInfo XML ファイルを置換するのヘルプ ファイルを更新するときにもう 1 つを入れないでください。 詳細については、次を参照してください。 [HelpInfo XML ファイルを作成する方法](./how-to-create-a-helpinfo-xml-file.md)します。

### <a name="step-4-sign-your-help-files"></a>手順 4:ヘルプ ファイルに署名します。

デジタル署名が必須ではありませんが、ファイルを共有しているときに、ベスト プラクティスの推奨事項。

### <a name="step-5-create-cab-files"></a>手順 5:CAB ファイルを作成します。

作成する、MakeCab.exe などのキャビネット (.cab) ファイルを作成するツールを使用して、します。モジュールのヘルプ ファイルを含む CAB ファイル。 サポートされている各 UI カルチャのヘルプ ファイルに個別の CAB ファイルを作成します。 詳細については、次を参照してください。[を準備する更新可能なヘルプ CAB ファイルの追加方法](./how-to-prepare-updatable-help-cab-files.md)します。

### <a name="step-6-upload-your-files"></a>手順 6:ファイルをアップロードします。

新しいまたは更新されたヘルプ ファイルを発行するで指定されたインターネット上の場所に CAB ファイルをアップロード、 **HelpContentUri** HelpInfo XML ファイル内の要素。 値で指定されたインターネット上の場所に HelpInfo XML ファイルをアップロードし、 **HelpInfoUri**モジュール マニフェストでキー。
