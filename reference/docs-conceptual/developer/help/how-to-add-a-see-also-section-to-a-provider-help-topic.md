---
title: プロバイダーヘルプトピックの「関連項目」セクションを追加する方法Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9c754ac3-cee3-4c13-9bad-e499c8a68a09
caps.latest.revision: 4
ms.openlocfilehash: f5c48fd04c620828a6e99c5c5424d11b31fd10e5
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367841"
---
# <a name="how-to-add-a-see-also-section-to-a-provider-help-topic"></a>プロバイダーのヘルプ トピックに関連項目を追加する方法

このセクションでは、プロバイダーヘルプトピックの **「関連項目」** セクションにデータを設定する方法について説明します。

「関連項目」セクションは、プロバイダーに関連するトピックの一覧で構成され**て**います。また、ユーザーがプロバイダーをよりよく理解し、使用するために役立つ場合もあります。 トピックの一覧には、Windows PowerShell のヘルプトピック (コマンドレットのヘルプ、プロバイダーのヘルプ、および概念説明の "about") を含めることができます。 また、現在のプロバイダーのヘルプトピックのオンラインバージョンを含む、書籍、紙、およびオンラインのトピックへの参照を含めることもできます。

オンライントピックを参照するときは、プレーンテキストで URI または検索語句を指定します。 `Get-Help` コマンドレットは、一覧のどのトピックにもリンクまたはリダイレクトしません。 また、`Get-Help` コマンドレットの `Online` パラメーターは、プロバイダーのヘルプでは機能しません。

「関連項目」セクションは、`RelatedLinks` 要素とそれに含まれるタグから作成されます。 タグを追加する方法を次の XML に示します。

### <a name="to-add-see-also-topics"></a>「関連項目」を追加するには

1. Dll-help ファイル*の `providerHelp`* 要素内に、`RelatedLinks` 要素を追加します。 `RelatedLinks` 要素は、`providerHelp` 要素の最後の要素である必要があります。 各プロバイダーヘルプトピックでは、`RelatedLinks` 要素が1つだけ許可されます。

   たとえば、次のようになります。

    ```xml
    <providerHelp>
        <RelatedLinks>
        </RelatedLinks>
    </providerHelp>
    ```

2. **「関連**項目」セクションの各トピックについて、`RelatedLinks` 要素内に `navigationLink` 要素を追加します。 次に、各 `navigationLink` 要素内に、1つの `linkText` 要素と1つの `uri` 要素を追加します。 `uri` 要素を使用していない場合は、空の要素 (\<uri/>) として追加できます。

   たとえば、次のようになります。

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

3. `linkText` タグの間のトピック名を入力します。 URI を指定する場合は、`uri` タグの間に入力します。 現在のプロバイダーのヘルプトピックのオンラインバージョンを示すには、`linkText` タグの間に、トピック名の代わりに「Online version:」と入力します。 通常、"オンラインバージョン:" リンクは、「関連項目」の一覧の最初のトピックです。

   次の例には、3つのトピックも含まれています。 最初のは、現在のトピックのオンラインバージョンを参照します。 2番目のコマンドレットは、Windows PowerShell コマンドレットのヘルプトピックを参照します。 3番目のトピックでは、別のオンライントピックを参照します。

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