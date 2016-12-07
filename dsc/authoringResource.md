---
title: "カスタム Windows PowerShell Desired State Configuration のビルド"
ms.date: 2016-05-16
keywords: PowerShell, DSC
description: 
ms.topic: article
author: eslesar
manager: dongill
ms.prod: powershell
ms.openlocfilehash: fe2697de322be99e9b5dfe79090fda4082a73623
ms.sourcegitcommit: c732e3ee6d2e0e9cd8c40105d6fbfd4d207b730d
translationtype: HT
---
# <a name="build-custom-windows-powershell-desired-state-configuration-resources"></a>カスタム Windows PowerShell Desired State Configuration のビルド

> 適用先: Windows PowerShell 4.0、Windows PowerShell 5.0

Windows PowerShell Desired State Configuration (DSC) には、環境の構成に使用できる組み込みのリソースがあります (詳細については、「[Windows PowerShell Desired State Configuration の組み込みリソース](builtInResource.md)」を参照してください)。このトピックでは、開発リソースの概要および特定の情報と例を含むトピックへのリンクを示します。

## <a name="dsc-resource-components"></a>DSC リソース コンポーネント

DSC リソースは、Windows PowerShell モジュールです。 モジュールには、リソースのスキーマ (構成可能なプロパティの定義) と実装 (構成で指定された実際の作業を実行するコード) の両方が含まれています。 DSC リソースのスキーマは MOF ファイルで定義でき、実装はスクリプト モジュールによって実行されます。 バージョン 5 で PowerShell クラスがサポートされるようになってから、スキーマと実装は両方ともクラスで定義できます。 次のトピックでは、DSC リソースを作成する方法をさらに詳しく説明します。

* [MOF を使用したカスタム DSC リソースの記述](authoringResourceMOF.md) 
* [Implementing a DSC resource in C# (C# での DSC リソースの実装)](authoringResourceMofCS.md) 
* [PowerShell クラスを使用したカスタム DSC リソースの記述](authoringResourceClass.md) 
* [複合リソース: リソースとしての DSC 構成の使用](authoringResourceComposite.md) 
* [リソース デザイナー ツールの使用](authoringResourceMofDesigner.md) 

