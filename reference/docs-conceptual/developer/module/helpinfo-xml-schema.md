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
ms.openlocfilehash: 8142a620f0f71de3d2a6b33fc2e45092b5743a54
ms.sourcegitcommit: bc9a4904c2b1561386d748fc9ac242699d2f1694
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "76996002"
---
# <a name="helpinfo-xml-schema"></a>HelpInfo XML スキーマ

このトピックでは、"HelpInfo XML files" と呼ばれる、更新可能なヘルプ情報ファイルの XML スキーマについて説明します。

## <a name="helpinfo-xml-schema"></a>HelpInfo XML スキーマ

HelpInfo XML ファイルは、次の XML スキーマに基づいています。

```xml
<?xml version="1.0" encoding="utf-8"?>
<schema targetNamespace="https://schemas.microsoft.com/powershell/help/2010/05" xmlns="http://www.w3.org/2001/XMLSchema">
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

HelpContentURI には、モジュールのヘルプ CAB ファイルの場所の URI が含まれています。 URI は "http" または "https" で始まる必要があります。 URI にはインターネットの場所を指定する必要がありますが、CAB ファイル名を含めることはできません。 **Helpcontenturi**値は、 **Helpinfouri**値と同じか、または異なる場合があります。

SupportedUICultures は、すべての UI カルチャのモジュールのヘルプファイルを表します。 **UICulture**要素が含まれます。各要素は、指定された UI カルチャのモジュールのヘルプファイルのセットを表します。

UICulture は、指定された UI カルチャのモジュールのヘルプファイルのセットを表します。 ヘルプファイルが記述されている各 UI カルチャの**UICulture**要素を追加します。

UICultureName には、ヘルプファイルが記述されている UI カルチャの言語コードが含まれています。

UICultureVersion には、"N1" に4つの部分から構成されるバージョン番号が含まれています。N2.N3.N4 "UI カルチャのヘルプ CAB ファイルのバージョンを表す形式です。 **UICultureName**で指定された UI カルチャで新しいヘルプ CAB ファイルをアップロードするたびに、このバージョン番号をインクリメントします。 この値の詳細については、MSDN の「バージョンクラス (システム)」を参照してください。