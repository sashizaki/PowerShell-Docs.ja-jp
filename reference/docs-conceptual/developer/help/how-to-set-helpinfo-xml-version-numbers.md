---
ms.date: 09/12/2016
ms.topic: reference
title: HelpInfo XML バージョン番号を設定する方法
description: HelpInfo XML バージョン番号を設定する方法
ms.openlocfilehash: 9ef1940ca05d8aa9b04770013287490b71c8065a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92658829"
---
# <a name="how-to-set-helpinfo-xml-version-numbers"></a><span data-ttu-id="6a7fb-103">HelpInfo XML バージョン番号を設定する方法</span><span class="sxs-lookup"><span data-stu-id="6a7fb-103">How to Set HelpInfo XML Version Numbers</span></span>

<span data-ttu-id="6a7fb-104">このトピックでは、更新可能なヘルプ情報ファイル ("HelpInfo XML ファイル" と呼ばれます) でバージョン番号を設定および増やす方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6a7fb-104">This topic explains how to set and increase the version numbers in an Updatable Help Information file, commonly known as a "HelpInfo XML file."</span></span>

## <a name="how-to-set-helpinfo-xml-version-numbers"></a><span data-ttu-id="6a7fb-105">HelpInfo XML バージョン番号を設定する方法</span><span class="sxs-lookup"><span data-stu-id="6a7fb-105">How to Set HelpInfo XML Version Numbers</span></span>

<span data-ttu-id="6a7fb-106">HelpInfo XML ファイルのバージョン番号は、更新可能なヘルプの操作にとって重要です。</span><span class="sxs-lookup"><span data-stu-id="6a7fb-106">The version numbers in a HelpInfo XML file are critical to the operation of Updatable Help.</span></span> <span data-ttu-id="6a7fb-107">[Update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)および HelpInfo コマンドレットは、リモートの xml ファイル内の ui カルチャのバージョン番号が、ローカルの HelpInfo XML の ui カルチャのバージョン番号より大きい場合、またはローカルの HelpInfo xml ファイルがない場合にのみ、新しいヘルプファイルを[ダウンロードします](/powershell/module/Microsoft.PowerShell.Core/Save-Help)。</span><span class="sxs-lookup"><span data-stu-id="6a7fb-107">The [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) and [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) cmdlets download new help files only when the version number for a UI culture in the remote HelpInfo XML file is greater than the version number for that UI culture in the local HelpInfo XML, or there is no local HelpInfo XML file.</span></span>

<span data-ttu-id="6a7fb-108">HelpInfo XML ファイルは、Microsoft .NET Framework の system.xml クラスで定義されている4つの部分から構成されるバージョン番号を使用 **します。**</span><span class="sxs-lookup"><span data-stu-id="6a7fb-108">The HelpInfo XML file uses the 4-part version number that is defined in the **System.Version** class of the Microsoft .NET Framework.</span></span> <span data-ttu-id="6a7fb-109">形式は `N1.N2.N3.N4` です。</span><span class="sxs-lookup"><span data-stu-id="6a7fb-109">The format is `N1.N2.N3.N4`.</span></span> <span data-ttu-id="6a7fb-110">モジュールの作成者は、 **System. version** クラスで許可されている任意のバージョン番号付けスキームを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6a7fb-110">Module authors can use any version numbering scheme that is permitted by the **System.Version** class.</span></span> <span data-ttu-id="6a7fb-111">更新可能なヘルプでは、ui カルチャ用の CAB ファイルの新しいバージョンが、HelpInfo XML ファイルの **Helpcontenturi** 要素で指定されている場所にアップロードされたときに、ui カルチャのバージョン番号が増えるだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="6a7fb-111">Updatable Help requires only that the version number for a UI culture increase when a new version of the CAB file for that UI culture is uploaded to the location that is specified by the **HelpContentURI** element in the HelpInfo XML file.</span></span>

<span data-ttu-id="6a7fb-112">次の例は、バージョンが2.15.0.10 の場合のドイツ語 (de) UI カルチャの HelpInfo XML ファイルの要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="6a7fb-112">The following example shows the elements of the HelpInfo XML file for the German (de-DE) UI culture when the version is 2.15.0.10.</span></span>

```xml
<UICulture>
  <UICultureName>de-DE</UICultureName>
  <UICultureVersion>2.15.0.10</UICultureVersion>
</UICulture>
```

<span data-ttu-id="6a7fb-113">UI カルチャのバージョン番号は、その UI カルチャの CAB ファイルのバージョンを反映しています。</span><span class="sxs-lookup"><span data-stu-id="6a7fb-113">The version number for a UI culture reflects the version of the CAB file for that UI culture.</span></span> <span data-ttu-id="6a7fb-114">バージョン番号は CAB ファイル全体に適用されます。</span><span class="sxs-lookup"><span data-stu-id="6a7fb-114">The version number applies to the entire CAB file.</span></span> <span data-ttu-id="6a7fb-115">CAB ファイル内のファイルごとに異なるバージョン番号を設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="6a7fb-115">You cannot set different version numbers for different files in the CAB file.</span></span> <span data-ttu-id="6a7fb-116">各 UI カルチャのバージョン番号は個別に評価され、モジュールがサポートする他の UI カルチャのバージョン番号とは関係がありません。</span><span class="sxs-lookup"><span data-stu-id="6a7fb-116">The version number for each UI culture is evaluated independently and need not be related to the version numbers for other UI cultures that the module supports.</span></span>
