---
ms.date: 09/12/2016
ms.topic: reference
title: HelpInfo XML スキーマ
description: HelpInfo XML スキーマ
ms.openlocfilehash: 157fd9c0f47c57efbaa9b7888fa174a34ad9567d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92662017"
---
# <a name="helpinfo-xml-schema"></a><span data-ttu-id="b9151-103">HelpInfo XML スキーマ</span><span class="sxs-lookup"><span data-stu-id="b9151-103">HelpInfo XML Schema</span></span>

<span data-ttu-id="b9151-104">このトピックでは、"HelpInfo XML files" と呼ばれる、更新可能なヘルプ情報ファイルの XML スキーマについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b9151-104">This topic contains the XML schema for Updatable Help Information files, commonly known as "HelpInfo XML files."</span></span>

## <a name="helpinfo-xml-schema"></a><span data-ttu-id="b9151-105">HelpInfo XML スキーマ</span><span class="sxs-lookup"><span data-stu-id="b9151-105">HelpInfo XML Schema</span></span>

<span data-ttu-id="b9151-106">HelpInfo XML ファイルは、次の XML スキーマに基づいています。</span><span class="sxs-lookup"><span data-stu-id="b9151-106">HelpInfo XML files are based on the following XML schema.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<schema targetNamespace="http://schemas.microsoft.com/powershell/help/2010/05" xmlns="http://www.w3.org/2001/XMLSchema">
  <element name="HelpInfo">
    <complexType>
      <sequence>
        <element name="HelpContentURI" type="anyURI" minOccurs="1" maxOccurs="1" />
        <element name="SupportedUICultures" minOccurs="1" maxOccurs="1">
          <complexType>
            <sequence>
              <element name="UICulture" minOccurs="1" maxOccurs="unbounded">
                <complexType>
                  <sequence>
                    <element name="UICultureName" type="language" minOccurs="1" maxOccurs="1" />
                    <element name="UICultureVersion" type="string" minOccurs="1" maxOccurs="1" />
                  </sequence>
                </complexType>
              </element>
            </sequence>
          </complexType>
        </element>
      </sequence>
    </complexType>
  </element>
</schema>
```

## <a name="helpinfo-xml-elements"></a><span data-ttu-id="b9151-107">HelpInfo XML 要素</span><span class="sxs-lookup"><span data-stu-id="b9151-107">HelpInfo XML Elements</span></span>

<span data-ttu-id="b9151-108">HelpInfo XML ファイルには、次の要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b9151-108">The HelpInfo XML file includes the following elements.</span></span>

- <span data-ttu-id="b9151-109">**Helpcontenturi** -モジュールのヘルプ CAB ファイルの場所の URI が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b9151-109">**HelpContentURI** - Contains the URI of the location of the help CAB files for the module.</span></span> <span data-ttu-id="b9151-110">URI は "http" または "https" で始まる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9151-110">The URI must begin with "http" or "https".</span></span> <span data-ttu-id="b9151-111">URI にはインターネットの場所を指定する必要がありますが、CAB ファイル名を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="b9151-111">The URI should specify an internet location, but must not include the CAB filename.</span></span> <span data-ttu-id="b9151-112">**Helpcontenturi** 値は、 **Helpinfouri** 値と同じか、または異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b9151-112">The **HelpContentURI** value can be the same or different from the **HelpInfoURI** value.</span></span>

- <span data-ttu-id="b9151-113">**SupportedUICultures** -すべての UI カルチャのモジュールのヘルプファイルを表します。</span><span class="sxs-lookup"><span data-stu-id="b9151-113">**SupportedUICultures** - Represents the module help files in all UI cultures.</span></span> <span data-ttu-id="b9151-114">**UICulture** 要素が含まれます。各要素は、指定された UI カルチャのモジュールのヘルプファイルのセットを表します。</span><span class="sxs-lookup"><span data-stu-id="b9151-114">Contains **UICulture** elements, each of which represents a set of help files for the module in a specified UI culture.</span></span>

- <span data-ttu-id="b9151-115">**UICulture** -指定された UI カルチャに含まれるモジュールのヘルプファイルのセットを表します。</span><span class="sxs-lookup"><span data-stu-id="b9151-115">**UICulture** - Represents a set of help files for the module in a specified UI culture.</span></span> <span data-ttu-id="b9151-116">ヘルプファイルが記述されている各 UI カルチャの **UICulture** 要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="b9151-116">Add a **UICulture** element for each UI culture in which the help files are written.</span></span>

- <span data-ttu-id="b9151-117">**UICultureName** -ヘルプファイルが記述されている UI カルチャの言語コードを格納します。</span><span class="sxs-lookup"><span data-stu-id="b9151-117">**UICultureName** - Contains the language code for the UI culture in which the help files are written.</span></span>

- <span data-ttu-id="b9151-118">**UICultureVersion** -"N1. に4つの部分で構成されるバージョン番号が含まれています。N2.N3.N4 "UI カルチャのヘルプ CAB ファイルのバージョンを表す形式です。</span><span class="sxs-lookup"><span data-stu-id="b9151-118">**UICultureVersion** - Contains a 4-part version number in "N1.N2.N3.N4" format that represents the version of the help CAB file in the UI culture.</span></span> <span data-ttu-id="b9151-119">**UICultureName** で指定された UI カルチャで新しいヘルプ CAB ファイルをアップロードするたびに、このバージョン番号をインクリメントします。</span><span class="sxs-lookup"><span data-stu-id="b9151-119">Increment this version number whenever you upload new help CAB files in the UI culture that is specified by **UICultureName**.</span></span> <span data-ttu-id="b9151-120">この値の詳細については、「 [バージョンクラス](/dotnet/api/system.version)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b9151-120">For more information about this value, see [Version Class](/dotnet/api/system.version).</span></span>
