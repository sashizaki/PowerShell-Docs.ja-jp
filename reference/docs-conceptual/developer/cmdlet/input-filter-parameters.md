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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364391"
---
# <a name="input-filter-parameters"></a>入力フィルターのパラメーター

コマンドレットでは、コマンドレットが影響する入力オブジェクトのセットをフィルター処理する `Filter`、`Include`、および `Exclude` パラメーターを定義できます。

通常、入力オブジェクトのセットは、`InputObject`、`Path`、または `Name` パラメーターによって指定されます。 たとえば、コマンドレットには、ワイルドカード文字を使用して複数のパスを受け取る `Path` パラメーターを指定できます。また、各パスは入力オブジェクトを指します。 `Filter`、`Include`、および `Exclude` パラメーターを一緒に使用することで、コマンドレットが呼び出されるたびに実行されるパスをさらに修飾できます。

## <a name="include-and-exclude-parameters"></a>Include パラメーターと Exclude パラメーター

`Include` パラメーターと `Exclude` パラメーターは、コマンドレットに渡された入力オブジェクトのセットに含まれるオブジェクトまたは除外されるオブジェクトを識別します。 フィルターを標準のワイルドカード言語で表現できる場合は、これらのパラメーターを使用します。 (ワイルドカード文字の詳細については、「[コマンドレットパラメーターでのワイルドカードのサポート](./supporting-wildcard-characters-in-cmdlet-parameters.md)」を参照してください)。`Include` パラメーターには、包含フィルターに一致する名前を持つすべてのオブジェクトが含まれます。 `Exclude` パラメーターは、フィルターに一致する名前を持つすべてのオブジェクトを除外します。

## <a name="filter-parameter"></a>フィルターパラメーター

`Filter` パラメーターは、標準のワイルドカード言語では表されないフィルターを指定します。 たとえば、`Filter` パラメーターを使用して、Active Directory サービスインターフェイス (ADSI) または SQL フィルターをコマンドレットに渡すことができます。 Windows PowerShell によって提供されるコマンドレットでは、これらのフィルターは、コマンドレットを使用してデータストアにアクセスする Windows PowerShell プロバイダーによって指定されます。 各プロバイダーは、通常、独自のフィルターを定義します。

## <a name="filtering-if-no-set-of-input-objects-is-specified"></a>入力オブジェクトのセットが指定されていない場合のフィルター処理

入力オブジェクトのセットが指定されていない場合、これは通常、すべてのオブジェクトに対してフィルター処理を行うことを意味します。 詳細については、「[Get Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process)」を参照してください。

## <a name="see-also"></a>参照

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)