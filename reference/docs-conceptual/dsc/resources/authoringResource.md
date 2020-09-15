---
ms.date: 07/08/2020
keywords: DSC, PowerShell, 構成, セットアップ
title: カスタム Windows PowerShell Desired State Configuration のビルド
ms.openlocfilehash: 203a2e3d0e118b86ae1fe959cc3508b6ed2733a8
ms.sourcegitcommit: d26e2237397483c6333abcf4331bd82f2e72b4e3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2020
ms.locfileid: "86217578"
---
# <a name="build-custom-windows-powershell-desired-state-configuration-resources"></a>カスタム Windows PowerShell Desired State Configuration のビルド

> 適用先: Windows PowerShell 4.0、Windows PowerShell 5.0

Windows PowerShell Desired State Configuration (DSC) には、環境の構成に使用できる組み込みのリソースがあります このトピックでは、開発リソースの概要および特定の情報と例を含むトピックへのリンクを示します。

## <a name="dsc-resource-components"></a>DSC リソース コンポーネント

DSC リソースは、Windows PowerShell モジュールです。 モジュールには、リソースのスキーマ (構成可能なプロパティの定義) と実装 (構成で指定された実際の作業を実行するコード) の両方が含まれています。 DSC リソースのスキーマは MOF ファイルで定義でき、実装はスクリプト モジュールによって実行されます。 バージョン 5 で PowerShell クラスがサポートされるようになってから、スキーマと実装は両方ともクラスで定義できます。 次のトピックでは、DSC リソースを作成する方法をさらに詳しく説明します。

- [MOF を使用したカスタム DSC リソースの記述](authoringResourceMOF.md)
- [Implementing a DSC resource in C# (C# での DSC リソースの実装)](authoringResourceMofCS.md)
- [PowerShell クラスを使用したカスタム DSC リソースの記述](authoringResourceClass.md)
- [複合リソース: リソースとしての DSC 構成の使用](authoringResourceComposite.md)
- [リソース デザイナー ツールの使用](authoringResourceMofDesigner.md)
