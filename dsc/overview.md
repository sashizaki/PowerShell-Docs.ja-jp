---
ms.date: 06/12/2017
ms.topic: conceptual
keywords: DSC, PowerShell, 構成, セットアップ
title: Windows PowerShell Desired State Configuration の概要
ms.openlocfilehash: 3f357ea11a388a05b73539a63e52e639ee906f68
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="windows-powershell-desired-state-configuration-overview"></a>Windows PowerShell Desired State Configuration の概要

> 適用先: Windows PowerShell 4.0、Windows PowerShell 5.0

DSC は PowerShell による管理プラットフォームであり、IT と開発インフラストラクチャを構成を用いてコードで管理できます。

- DSC を使用するビジネス上の利点の概要については、「[意思決定者向け Desired State Configuration の概要](decisionMaker.md)」をご覧ください。
- DSC を使用するエンジニアリングの利点の概要については、[「エンジニア向けの Desired State Configuration の概要」](DscForEngineers.md) をご覧ください。
- DSC を簡単に使用するには、[「DSC クイック スタート」](quickStart.md) をご覧ください。

## <a name="key-concepts"></a>主要概念

DSC は、システムの構成、展開、および管理に使用する宣言型プラットフォームです。 次の 3 つの主要なコンポーネントで構成されます。

- [構成](configurations.md)は、リソースのインスタンスを定義および構成する宣言型の PowerShell スクリプトです。
    構成を実行すると、DSC (および構成によって呼び出されるリソース) は、構成によってレイアウトされた状態でシステムが存在するように、単に、指定されたことを実現します。
    DSC 構成は、べき等でもあります。ローカル構成マネージャー (LCM) によって、構成によって宣言された状態でマシンが構成されることが、継続的に保証されます。
- [リソース](resources.md)は DSC の "指定されたことを実現する" 部分です。 リソースには構成のターゲットを指定された状態で保持するコードが含まれています。
    リソースは PowerShell モジュール内に存在し、ファイルまたは Windows プロセスのように汎用的なものをモデル化したり、IIS サーバーまたは Azure で実行されている VM のように具体的なものをモデル化するために作成できます。
- [ローカル構成マネージャー (LCM)](metaConfig.md) は、DSC でのリソースと構成の間の対話を容易にするエンジンです。
    LCM は、リソースによって実装される制御フローを使用してシステムを定期的にポーリングし、構成によって定義された状態が維持されるようにします。
    システムが状態外の場合、LCM はリソース内のコードに対して呼び出しを行い、構成に従って「指定されたことを実現」します。

## <a name="see-also"></a>参照

- [DSC 構成](configurations.md)
- [DSC リソース](resources.md)
- [ローカル構成マネージャーの構成](metaConfig.md)