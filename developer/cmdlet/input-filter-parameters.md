---
title: 入力フィルター パラメーター |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e45929d1-bbb4-4dc6-892f-f9eacdb1c84c
caps.latest.revision: 8
ms.openlocfilehash: 553878c34e74129f9876cca25a5393cb0d53445a
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854468"
---
# <a name="input-filter-parameters"></a>入力フィルターのパラメーター

コマンドレットを定義できます`Filter`、 `Include`、および`Exclude`パラメーターをコマンドレットに影響を与える入力オブジェクトのセットをフィルター処理します。

通常、入力オブジェクトのセットがで指定された、 `InputObject`、 `Path`、または`Name`パラメーター。 たとえば、コマンドレットが持つことができます、`Path`をワイルドカード文字、および入力オブジェクトには、各パス ポイントを使用して複数のパスを受け取るパラメーター。 、一緒に使用、 `Filter`、 `Include`、および`Exclude`パラメーターをさらには、コマンドレットの動作が呼び出されるたびにパスを修飾します。

## <a name="include-and-exclude-parameters"></a>パラメーターを含めたり除外したり

`Include`と`Exclude`パラメーターが含まれるか、コマンドレットに渡された入力オブジェクトのセットから除外するオブジェクトを識別します。 フィルターは、標準のワイルドカードの言語で表現できる場合は、これらのパラメーターを使用します。 (ワイルドカード文字の詳細については、次を参照してください[コマンドレットのパラメーターにワイルドカードをサポートしている](./supporting-wildcard-characters-in-cmdlet-parameters.md)。)。`Include`パラメーターに名前を持つ包含フィルターに一致するすべてのオブジェクトが含まれています。 `Exclude`パラメーターに名前を持つフィルターに一致するすべてのオブジェクトが除外されます。

## <a name="filter-parameter"></a>パラメーターをフィルター処理します。

`Filter`パラメーターは、標準のワイルドカードの言語で表記されていないフィルターを指定します。 たとえば、Active Directory サービス インターフェイス (ADSI) または SQL のフィルターがを介してコマンドレットに渡すことができます、`Filter`パラメーター。 Windows PowerShell によって提供される、コマンドレットでは、これらのフィルターは、コマンドレットを使用してデータ ストアにアクセスする Windows PowerShell プロバイダーによって指定されます。 通常、各プロバイダーは、独自のフィルターを定義します。

## <a name="filtering-if-no-set-of-input-objects-is-specified"></a>入力オブジェクトのセットが指定されていない場合にフィルター処理

通常入力オブジェクトのセットが指定されていない場合これをすべてのオブジェクトに対してフィルター処理することを意味します。 詳細については、次を参照してください。[Get-process](/powershell/module/Microsoft.PowerShell.Management/Get-Process)します。

## <a name="see-also"></a>参照

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)