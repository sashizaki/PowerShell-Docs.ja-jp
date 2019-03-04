---
title: コマンドレットのパラメーター |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- optional parameters [PowerShell SDK]
- aliases [PowerShell SDK]
- parameter sets [PowerShell SDK]
- parameters [PowerShell SDK]
- mandatory parameters [PowerShell SDK]
- positional parameters [PowerShell SDK]
- cmdlets [PowerShell SDK], parameters
ms.assetid: 3f1cca5f-5b95-4bce-94a6-a22db1aefd47
caps.latest.revision: 23
ms.openlocfilehash: 914a10907bcf980eed8d7e2f819c382fe6b341ad
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853848"
---
# <a name="cmdlet-parameters"></a>コマンドレットのパラメーター

コマンドレットのパラメーターは、コマンドレットの入力を受け付けることを許可するメカニズムを提供します。 パラメーターは、コマンドラインから直接、または、引数、パイプラインを介してコマンドレットに渡されたオブジェクトからの入力を受け付けることができます (とも呼ばれます*値*) これらのパラメーターをコマンドレットが受け取る入力を指定できますが、方法コマンドレットは、アクション、およびパイプラインにコマンドレットが返すデータを実行する必要があります。

## <a name="in-this-section"></a>このセクションの内容

[パラメーターとしてプロパティを宣言する](./declaring-properties-as-parameters.md)コマンドレットのパラメーターを宣言する前に理解する必要があります、基本的な情報を提供します。

[コマンドレットのパラメーターの型](./types-of-cmdlet-parameters.md)コマンドレットで宣言するパラメーターのさまざまな種類について説明します。

[コマンドレットのパラメーター名と機能のガイドライン](./standard-cmdlet-parameter-names-and-types.md)で、名前のデータ型、および標準のパラメーターの機能をお勧めします。

[パラメーター エイリアス](./parameter-aliases.md)パラメーターを定義できるエイリアスについて説明します。

[一般的なパラメーター名](./common-parameter-names.md)このトピックでは、Windows PowerShell コマンドレットを追加しますパラメーターを示しています。

[コマンドレットのパラメーター設定](./cmdlet-parameter-sets.md)パラメーター セットを使用するさまざまなシナリオのさまざまなアクションを実行できる 1 つのコマンドレットを記述する方法について説明します。

[コマンドレットの動的パラメーター](./cmdlet-dynamic-parameters.md)は特別な条件下で、ユーザーに使用できるパラメーターについて説明します。

[コマンドレットのパラメーターにワイルドカード文字をサポートしている](./supporting-wildcard-characters-in-cmdlet-parameters.md)リソースのグループに対して実行されるコマンドレットをデザインするときに、ワイルドカード文字のサポートを提供する方法について説明します。

[パラメーターの入力を検証する](./validating-parameter-input.md)Windows PowerShell コマンドレットのパラメーターに渡される引数を検証する方法について説明します。

[入力フィルター パラメーター](./input-filter-parameters.md)について説明します、 `Filter`、 `Include`、および`Exclude`パラメーターをコマンドレットに影響を与える入力オブジェクトのセットをフィルター処理します。

## <a name="related-sections"></a>関連セクション

[パラメーターの入力を検証する方法](./how-to-validate-parameter-input.md)

## <a name="see-also"></a>参照

[パラメーター属性の宣言](./parameter-attribute-declaration.md)

[Windows PowerShell コマンドレット](./cmdlet-overview.md)
