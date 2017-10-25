---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "Windows PowerShell を管理に使用する"
ms.assetid: db6334ec-ace6-436d-ab88-77aefc817511
ms.openlocfilehash: fa87745b9be04d14de37a308d870b73c5a98cf83
ms.sourcegitcommit: 74255f0b5f386a072458af058a15240140acb294
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/03/2017
---
# <a name="using-windows-powershell-for-administration"></a>Windows PowerShell を管理に使用する
Windows PowerShell の基本的目標は、より良く、より簡単なシステム管理を、対話式でもスクリプトでも提供することです。 この章では、Windows システムの管理に関する多くの問題への Windows PowerShell を使用した解決策を取り上げます。 Windows PowerShell ユーザー ガイドではスクリプトや関数について取り上げませんでしたが、後からスクリプトや関数で解決策を利用することができます。 問題の解決策の一部として、関数を含んだ例を示します。

解決策の説明全体を通し、特定のコマンドレット、一般的な Get-WmiObject コマンドレット、さらには Windows および .NET Framework インフラストラクチャの一部である外部ツールを使用した解決策の組み合わせを使用します。 外部ツールの使用は Windows PowerShell の長期的な設計意図の一部です。 システムが大きくなるにつれて、ユーザーは、使用できるツールセットでは必要なことすべてが行えない状況に絶えず直面することになります。 Windows PowerShell では、コマンドレットの実装だけに依存することを助長するのではなく、利用できるあらゆる代替シナリオの解決策を統合することをサポートしようとしています。

