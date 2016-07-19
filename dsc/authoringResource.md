---
title: "カスタム Windows PowerShell Desired State Configuration のビルド"
ms.date: 2016-05-16
keywords: powershell,DSC
description: 
ms.topic: article
author: eslesar
manager: dongill
ms.prod: powershell
translationtype: Human Translation
ms.sourcegitcommit: 6477ae8575c83fc24150f9502515ff5b82bc8198
ms.openlocfilehash: 5b43723f7b14eb4bca06d0430b5981c3663c5801

---

# カスタム Windows PowerShell Desired State Configuration のビルド

> 適用先: Windows PowerShell 4.0、Windows PowerShell 5.0

Windows PowerShell Desired State Configuration (DSC) には、環境の構成に使用できる組み込みのリソースがあります (詳細については、「[Windows PowerShell Desired State Configuration の組み込みリソース](builtInResource.md)」を参照してください)。このトピックでは、開発リソースの概要および特定の情報と例を含むトピックへのリンクを示します。

## DSC リソース コンポーネント

DSC リソースは、Windows PowerShell モジュールです。 モジュールには、リソースのスキーマ (構成可能なプロパティの定義) と実装 (構成で指定された実際の作業を実行するコード) の両方が含まれています。 DSC リソースのスキーマは MOF ファイルで定義でき、実装はスクリプト モジュールによって実行されます。 バージョン 5 で PowerShell クラスがサポートされるようになってから、スキーマと実装は両方ともクラスで定義できます。 次のトピックでは、DSC リソースを作成する方法をさらに詳しく説明します。

* [MOF を使用したカスタム DSC リソースの記述](authoringResourceMOF.md) 
* [C での DSC リソースの実装#](authoringResourceMofCS.md) 
* [PowerShell クラスを使用したカスタム DSC リソースの記述](authoringResourceClass.md) 
* [複合リソース: リソースとしての DSC 構成の使用](authoringResourceComposite.md) 
* [リソース デザイナー ツールの使用](authoringResourceMofDesigner.md) 




<!--HONumber=Jun16_HO4-->


