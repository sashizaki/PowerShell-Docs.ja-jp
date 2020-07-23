---
title: HelpInfo XML サンプル ファイル
ms.date: 09/12/2016
ms.openlocfilehash: ec9a2a1afed4f22be00900cbc80b580ff99f8f38
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "86953269"
---
# <a name="helpinfo-xml-sample-file"></a><span data-ttu-id="62325-102">HelpInfo XML サンプル ファイル</span><span class="sxs-lookup"><span data-stu-id="62325-102">HelpInfo XML Sample File</span></span>

<span data-ttu-id="62325-103">このトピックでは、"HelpInfo XML file" と呼ばれる、適切な形式の更新可能なヘルプ情報ファイルのサンプルを示します。</span><span class="sxs-lookup"><span data-stu-id="62325-103">This topic displays a sample of a well-formed Updatable Help Information file, commonly known as "HelpInfo XML file."</span></span> <span data-ttu-id="62325-104">このサンプルファイルでは、ui カルチャの要素は、UI カルチャ名のアルファベット順に並べられています。</span><span class="sxs-lookup"><span data-stu-id="62325-104">In this sample file, the UI culture elements are arranged in alphabetical order by UI culture name.</span></span> <span data-ttu-id="62325-105">アルファベット順の順序がベストプラクティスですが、必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="62325-105">Alphabetical ordering is a best practice, but it is not required.</span></span>

## <a name="helpinfo-xml-sample-file"></a><span data-ttu-id="62325-106">HelpInfo XML サンプル ファイル</span><span class="sxs-lookup"><span data-stu-id="62325-106">HelpInfo XML Sample File</span></span>

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
