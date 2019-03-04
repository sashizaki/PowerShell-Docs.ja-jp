---
title: HelpInfo XML スキーマ |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 74dcb396-c295-4457-b84c-4432bdaa8df3
caps.latest.revision: 7
ms.openlocfilehash: 0f965f4ee1ef92a6a538b52b4348c04366cabf66
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862318"
---
# <a name="helpinfo-xml-schema"></a>HelpInfo XML スキーマ

このトピックには、一般的「HelpInfo XML ファイル。」と呼ばれる、更新可能なヘルプ情報ファイルの XML スキーマが含まれています。

## <a name="helpinfo-xml-schema"></a>HelpInfo XML スキーマ

HelpInfo XML ファイルは、次の XML スキーマに基づいています。

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

## <a name="helpinfo-xml-elements"></a>HelpInfo XML 要素

HelpInfo XML ファイルには、次の要素が含まれています。

HelpContentURI には、ヘルプ、モジュール用の CAB ファイルの場所の URI が含まれています。 URI は、"http"または"https"で始まる必要があります。 URI は、インターネット上の場所を指定する必要がありますが、CAB ファイルの名前を含めることはできません。 **HelpContentURI**値は、同じまたは異なる、 **HelpInfoURI**値。

SupportedUICultures すべての UI カルチャでモジュールのヘルプ ファイルを表します。 含む**UICulture**要素は、指定した UI カルチャでモジュールのヘルプ ファイルのセットを表します。

UICulture は、指定した UI カルチャでモジュールのヘルプ ファイルのセットを表します。 追加、 **UICulture**ヘルプ ファイルを記述する各 UI カルチャの要素。

UICultureName にはヘルプ ファイルを記述する UI カルチャの言語コードが含まれます。

UICultureVersion には"N1 での 4 つの部分のバージョン番号が含まれています。N2 します。N3 します。N4"では、UI カルチャでヘルプ CAB ファイルのバージョンを表す形式。 新しいヘルプで指定されている UI カルチャで CAB ファイルをアップロードするたびに、このバージョン番号をインクリメント**UICultureName**します。 この値の詳細については、「バージョン クラス (システム)"MSDN を参照してください。