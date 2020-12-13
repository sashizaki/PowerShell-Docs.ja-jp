---
ms.date: 09/12/2016
ms.topic: reference
title: HelpInfo XML サンプル ファイル
description: HelpInfo XML サンプル ファイル
ms.openlocfilehash: 321793d61ab5df3cccc7c353b6c93f5a7275b533
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647760"
---
# <a name="helpinfo-xml-sample-file"></a><span data-ttu-id="e3b50-103">HelpInfo XML サンプル ファイル</span><span class="sxs-lookup"><span data-stu-id="e3b50-103">HelpInfo XML Sample File</span></span>

<span data-ttu-id="e3b50-104">このトピックでは、"HelpInfo XML file" と呼ばれる、適切な形式の更新可能なヘルプ情報ファイルのサンプルを示します。</span><span class="sxs-lookup"><span data-stu-id="e3b50-104">This topic displays a sample of a well-formed Updatable Help Information file, commonly known as "HelpInfo XML file."</span></span> <span data-ttu-id="e3b50-105">このサンプルファイルでは、ui カルチャの要素は、UI カルチャ名のアルファベット順に並べられています。</span><span class="sxs-lookup"><span data-stu-id="e3b50-105">In this sample file, the UI culture elements are arranged in alphabetical order by UI culture name.</span></span> <span data-ttu-id="e3b50-106">アルファベット順の順序がベストプラクティスですが、必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="e3b50-106">Alphabetical ordering is a best practice, but it is not required.</span></span>

## <a name="helpinfo-xml-sample-file"></a><span data-ttu-id="e3b50-107">HelpInfo XML サンプル ファイル</span><span class="sxs-lookup"><span data-stu-id="e3b50-107">HelpInfo XML Sample File</span></span>

```xml

<?xml version="1.0" encoding="utf-8"?>
<HelpInfo xmlns="http://schemas.microsoft.com/powershell/help/2010/05">
   <HelpContentURI>https://go.microsoft.com/fwlink/?LinkID=141553</HelpContentURI>
   <SupportedUICultures>
    <UICulture>
      <UICultureName>de-DE</UICultureName>
      <UICultureVersion>2.15.0.10</UICultureVersion>
    </UICulture>
    <UICulture>
      <UICultureName>en-US</UICultureName>
      <UICultureVersion>3.2.0.7</UICultureVersion>
    </UICulture>
    <UICulture>
      <UICultureName>it-IT</UICultureName>
      <UICultureVersion>1.1.0.5</UICultureVersion>
    </UICulture>
    <UICulture>
      <UICultureName>ja-JP</UICultureName>
      <UICultureVersion>3.2.0.4</UICultureVersion>
    </UICulture>
   </SupportedUICultures>
</HelpInfo>

```
