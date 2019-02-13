---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: カスタム Windows PowerShell Desired State Configuration のビルド
ms.openlocfilehash: 882b6efed4564d2354183d7472b301e1e1758335
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "55680084"
---
# <a name="build-custom-windows-powershell-desired-state-configuration-resources"></a><span data-ttu-id="adc46-103">カスタム Windows PowerShell Desired State Configuration のビルド</span><span class="sxs-lookup"><span data-stu-id="adc46-103">Build Custom Windows PowerShell Desired State Configuration Resources</span></span>

> <span data-ttu-id="adc46-104">適用先: Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="adc46-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="adc46-105">Windows PowerShell Desired State Configuration (DSC) には、環境の構成に使用できる組み込みのリソースがあります</span><span class="sxs-lookup"><span data-stu-id="adc46-105">Windows PowerShell Desired State Configuration (DSC) has built-in resources that you can use to configure your environment.</span></span> <span data-ttu-id="adc46-106">このトピックでは、開発リソースの概要および特定の情報と例を含むトピックへのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="adc46-106">This topic provides an overview of developing resources and links to topics with specific information and examples.</span></span>

## <a name="dsc-resource-components"></a><span data-ttu-id="adc46-107">DSC リソース コンポーネント</span><span class="sxs-lookup"><span data-stu-id="adc46-107">DSC resource components</span></span>

<span data-ttu-id="adc46-108">DSC リソースは、Windows PowerShell モジュールです。</span><span class="sxs-lookup"><span data-stu-id="adc46-108">A DSC resource is a Windows PowerShell module.</span></span> <span data-ttu-id="adc46-109">モジュールには、リソースのスキーマ (構成可能なプロパティの定義) と実装 (構成で指定された実際の作業を実行するコード) の両方が含まれています。</span><span class="sxs-lookup"><span data-stu-id="adc46-109">The module contains both the schema (the definition of the configurable properties) and the implementation (the code that does the actual work specified by a configuration) for the resource.</span></span> <span data-ttu-id="adc46-110">DSC リソースのスキーマは MOF ファイルで定義でき、実装はスクリプト モジュールによって実行されます。</span><span class="sxs-lookup"><span data-stu-id="adc46-110">A DSC resource schema can be defined in a MOF file, and the implementation is performed by a script module.</span></span> <span data-ttu-id="adc46-111">バージョン 5 で PowerShell クラスがサポートされるようになってから、スキーマと実装は両方ともクラスで定義できます。</span><span class="sxs-lookup"><span data-stu-id="adc46-111">Beginning with the support of PowerShell classes in version 5, the schema and implementation can both be defined in a class.</span></span> <span data-ttu-id="adc46-112">次のトピックでは、DSC リソースを作成する方法をさらに詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="adc46-112">The following topics describe in more detail how to create DSC resources.</span></span>

* [<span data-ttu-id="adc46-113">MOF を使用したカスタム DSC リソースの記述</span><span class="sxs-lookup"><span data-stu-id="adc46-113">Writing a custom DSC resource with MOF</span></span>](authoringResourceMOF.md)
* [<span data-ttu-id="adc46-114">Implementing a DSC resource in C# (C# での DSC リソースの実装)</span><span class="sxs-lookup"><span data-stu-id="adc46-114">Implementing a DSC resource in C#</span></span>](authoringResourceMofCS.md)
* [<span data-ttu-id="adc46-115">PowerShell クラスを使用したカスタム DSC リソースの記述</span><span class="sxs-lookup"><span data-stu-id="adc46-115">Writing a custom DSC resource with PowerShell classes</span></span>](authoringResourceClass.md)
* [<span data-ttu-id="adc46-116">複合リソース: リソースとしての DSC 構成の使用</span><span class="sxs-lookup"><span data-stu-id="adc46-116">Composite resources: Using a DSC configuration as a resource</span></span>](authoringResourceComposite.md)
* [<span data-ttu-id="adc46-117">リソース デザイナー ツールの使用</span><span class="sxs-lookup"><span data-stu-id="adc46-117">Using the Resource Designer tool</span></span>](../authoringResourceMofDesigner.md)
