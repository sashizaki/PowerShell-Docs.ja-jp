---
title: 入力フィルターパラメーター |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e45929d1-bbb4-4dc6-892f-f9eacdb1c84c
caps.latest.revision: 8
ms.openlocfilehash: 553878c34e74129f9876cca25a5393cb0d53445a
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364391"
---
# <a name="input-filter-parameters"></a>入力フィルターのパラメーター

コマンドレットでは、コマンドレットが影響する入力オブジェクトのセットをフィルター処理する `Filter`、`Include`、`Exclude` のパラメーターを定義できます。

通常、入力オブジェクトのセットは、`InputObject`、`Path`、または `Name` パラメーターによって指定されます。 たとえば、コマンドレットには、ワイルドカード文字を使用して複数のパスを受け取る @no__t 0 パラメーターを指定できます。また、各パスは入力オブジェクトを指します。 @No__t-0、`Include`、および `Exclude` の各パラメーターは、コマンドレットが呼び出されるたびに機能するパスをさらに修飾します。

## <a name="include-and-exclude-parameters"></a>Include パラメーターと Exclude パラメーター

@No__t-0 および `Exclude` パラメーターは、コマンドレットに渡された入力オブジェクトのセットに含まれるオブジェクトまたは除外されるオブジェクトを識別します。 フィルターを標準のワイルドカード言語で表現できる場合は、これらのパラメーターを使用します。 (ワイルドカード文字の詳細については、「[コマンドレットパラメーターでのワイルドカードのサポート](./supporting-wildcard-characters-in-cmdlet-parameters.md)」を参照してください)。@No__t-1 パラメーターには、包含フィルターに一致する名前を持つすべてのオブジェクトが含まれます。 @No__t-0 パラメーターを指定すると、フィルターに一致する名前を持つすべてのオブジェクトが除外されます。

## <a name="filter-parameter"></a>フィルターパラメーター

@No__t-0 パラメーターは、標準のワイルドカード言語で表現されていないフィルターを指定します。 たとえば、Active Directory サービスインターフェイス (ADSI) または SQL フィルターは、`Filter` パラメーターを使用してコマンドレットに渡すことができます。 Windows PowerShell によって提供されるコマンドレットでは、これらのフィルターは、コマンドレットを使用してデータストアにアクセスする Windows PowerShell プロバイダーによって指定されます。 各プロバイダーは、通常、独自のフィルターを定義します。

## <a name="filtering-if-no-set-of-input-objects-is-specified"></a>入力オブジェクトのセットが指定されていない場合のフィルター処理

入力オブジェクトのセットが指定されていない場合、これは通常、すべてのオブジェクトに対してフィルター処理を行うことを意味します。 詳細については、「[Get Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process)」を参照してください。

## <a name="see-also"></a>参照

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)