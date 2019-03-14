---
title: HelpInfo XML バージョン番号を設定する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93a00463-af58-41c8-b088-450909fa1d05
caps.latest.revision: 6
ms.openlocfilehash: d69e8a734aa96ff9b7911815fb43b81103548b59
ms.sourcegitcommit: 5990f04b8042ef2d8e571bec6d5b051e64c9921c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2019
ms.locfileid: "57794350"
---
# <a name="how-to-set-helpinfo-xml-version-numbers"></a>HelpInfo XML バージョン番号を設定する方法

このトピックでは、設定、および一般的「HelpInfo XML ファイル」と呼ばれる、更新可能なヘルプ情報ファイルにバージョン番号を大きく方法を説明します

## <a name="how-to-set-helpinfo-xml-version-numbers"></a>HelpInfo XML バージョン番号を設定する方法

HelpInfo XML ファイルにバージョン番号は、更新可能なヘルプの操作に重要です。 [Update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)と[Save-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)コマンドレットがリモートの HelpInfo XML ファイルでの UI カルチャのバージョン番号がの UI カルチャ、バージョン番号より大きい場合にのみ、新しいヘルプ ファイルをダウンロードしますローカルの HelpInfo XML、またはローカルの HelpInfo XML ファイルがないです。

HelpInfo XML ファイルで定義されている 4 つの部分のバージョン番号を使用して、 **System.Version** Microsoft .NET Framework のクラス。 形式は`N1.N2.N3.N4`します。 モジュールの作成者は、任意のバージョン番号付けは許可されているスキームを使用できます、 **System.Version**クラス。 更新可能なヘルプが必要ですそれだけで、バージョン番号の UI カルチャの増加がで指定された場所にその UI カルチャ用の CAB ファイルの新しいバージョンがアップロードされたときに、 **HelpContentURI** HelpInfo XML ファイル内の要素。

次の例は、ドイツ (DE-DE) UI カルチャ、バージョンが 2.15.0.10 の HelpInfo XML ファイルの要素を示しています。

```xml

<UICulture>
  <UICultureName>de-DE</UICultureName>
  <UICultureVersion>2.15.0.10</UICultureVersion>
</UICulture>
```

UI カルチャのバージョン番号は、UI カルチャ用の CAB ファイルのバージョンを反映します。 全体の CAB ファイルにバージョン番号が適用されます。 CAB ファイルに別のファイルの異なるバージョン番号を設定することはできません。 各 UI カルチャのバージョン番号は、個別が評価され、モジュールがサポートするその他の UI カルチャのバージョン番号は関係なく必要があります。