---
title: 追加する方法を参照してくださいもセクション プロバイダーのヘルプ トピック |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9c754ac3-cee3-4c13-9bad-e499c8a68a09
caps.latest.revision: 4
ms.openlocfilehash: f5c48fd04c620828a6e99c5c5424d11b31fd10e5
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858348"
---
# <a name="how-to-add-a-see-also-section-to-a-provider-help-topic"></a>プロバイダーのヘルプ トピックに関連項目を追加する方法

このセクションを設定する方法を説明します、**参照**プロバイダーのヘルプ トピックの「します。

**参照**セクションでは、プロバイダーに関連するかよりよく理解し、プロバイダーを使用して、ユーザーに役立つトピックの一覧。 トピックの一覧は、コマンドレットのヘルプ、プロバイダーのヘルプを含めることができます (「about」) ヘルプのトピックでは、Windows PowerShell の概念とします。 書籍、ホワイト ペーパー、および現在のプロバイダーのヘルプ トピックのオンライン バージョンを含む、オンラインのトピックへの参照型を含めることもできます。

オンラインのトピックを参照するときに、URI またはプレーン テキストで検索用語を提供します。 `Get-Help`コマンドレットがリンクまたは一覧の各トピックのいずれかにリダイレクトしていません。 また、`Online`のパラメーター、`Get-Help`コマンドレットは、プロバイダーのヘルプでは機能しません。

「参照」セクションがから作成された、`RelatedLinks`要素とそれに含まれるタグ。 次の XML では、タグを追加する方法を示します。

### <a name="to-add-see-also-topics"></a>トピックの「参照」を追加するには

1. *AssemblyName*.dll help.xml ファイル内で、`providerHelp`要素を追加、`RelatedLinks`要素。 `RelatedLinks`要素の最後の要素があります、`providerHelp`要素。 1 つだけ`RelatedLinks`要素は各プロバイダーのヘルプ トピックでは許可します。

   たとえば、次のように入力します。

    ```xml
    <providerHelp>
        <RelatedLinks>
        </RelatedLinks>
    </providerHelp>
    ```

2. 内の各トピックの**参照**セクション内、`RelatedLinks`要素を追加、`navigationLink`要素。 その後、各`navigationLink`要素、1 つ追加`linkText`要素と 1 つ`uri`要素。 使用していない場合、`uri`要素として追加できますが、空の要素 (\<uri/>)。

   たとえば、次のように入力します。

    ```xml
    <providerHelp>
        <RelatedLinks>
            <navigationLink>
                <linkText> </linkText>
                <uri> </uri>
            </navigationLink>
        </RelatedLinks>
    </providerHelp>
    ```

3. 間トピック名を入力、`linkText`タグ。 URI を提供する場合は、入力間、`uri`タグ。 現在のプロバイダーのヘルプ トピックのオンライン バージョンを示すために、`linkText`タグ、種類"オンライン バージョン:"トピック名の代わりにします。 通常、"オンライン バージョン:"リンクは、「参照」トピックの一覧の最初のトピックです。

   次の例には、3 つの参照トピックが含まれます。 1 つ目は、現在のトピックのオンライン バージョンを参照してください。 2 つ目は、Windows PowerShell コマンドレットのヘルプ トピックを参照します。 3 つ目は、別のオンライン トピックを参照します。

    ```xml
    <providerHelp>
        <RelatedLinks>
            <navigationLink>
                <linkText> Online version: </linkText>
                <uri>http://www.fabrikam.com/help/myFunction.htm</uri>
            </navigationLink>
            <navigationLink>
                <linkText> about_functions </linkText>
                <uri/>
            </navigationLink>
            <navigationLink>
                <linkText> Windows PowerShell Getting Started Guide </linkText>
                <uri>http://go.microsoft.com/fwlink/?LinkID=89597<uri/>
            </navigationLink>
        </RelatedLinks>
    </providerHelp>
    ```