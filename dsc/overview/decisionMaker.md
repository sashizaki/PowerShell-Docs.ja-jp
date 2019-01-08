---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: 意思決定者向け Desired State Configuration の概要
ms.openlocfilehash: ce554d4bb994d4b1816d9d9c24599e4ef0e1c593
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402446"
---
# <a name="desired-state-configuration-overview-for-decision-makers"></a>意思決定者向け Desired State Configuration の概要

このドキュメントでは、Windows PowerShell Desired State Configuration (DSC) を使用するビジネス上の利点について説明します。 テクニカル ガイドではありません。

## <a name="what-is-desired-state-configuration"></a>Desired State Configuration とは

PowerShell Desired State Configuration は、オープン スタンダードに基づく、Windows に組み込まれた構成管理プラットフォームです。 DSC は、展開ライフサイクル (開発、テスト、実稼働前、実稼働) の各段階、およびスケールアウト中に、機能の信頼性と一貫性を維持するために十分な柔軟性があります。

DSC は[構成](../configurations/configurations.md)を中心としています。
構成とは、特定の特性を持つコンピューター ("ノード") で構成される環境を説明する読みやすいドキュメントです。
これらの特性は、特定の Windows 機能が有効になっていることを確認するなどの単純な場合や、SharePoint の展開のように複雑な場合があります。

DSC には監視とレポートも組み込まれています。
システムが適合しなくなった場合、DSC は警告を生成し、システムを修正するために機能することができます。

## <a name="benefits-of-using-desired-state-configuration"></a>Desired State Configuration を使用する利点

構成は、簡単に読み取り、保存、および更新できるように設計されています。
構成では、ターゲット デバイスをあるべき状態にするための手順を記述するのではなく、ターゲット デバイスがあるべき状態を宣言します。
これにより、DSC によって構成を学習、導入、実装、および保守するコストが非常に低く抑えられます。

構成を作成することは、複雑な展開手順が "信頼できる唯一の情報源" として 1 つの場所で取得されることを意味します。
これにより、特定の一連のマシンの展開を繰り返す場合にエラーが発生する可能性が大幅に低下します。
そして、展開の速度と信頼性を高めることで、複雑な展開も迅速に実現できるようになります。

また、構成は [PowerShell ギャラリー](https://powershellgallery.com)で共有することもできるため、実行する必要のある作業に適した一般的なシナリオやベスト プラクティスが既に存在している可能性もあります。


## <a name="desired-state-configuration-and-devops"></a>Desired State Configuration と DevOps

DSC は [DevOps](http://blogs.technet.com/b/ashleymcglone/archive/2015/11/20/devops-for-n00bs-ie-windows-people.aspx) を念頭に置いて設計され、内部や外部に関わらず、エンド ユーザーに価値を提供することに重点を置いた、迅速な展開と反復を可能にする人、プロセス、そしてツールが組み合わされたものです。
単一の構成によって環境を定義することで、開発者は要件を構成にエンコードし、その構成をソース管理にチェックインでき、運用チームではエラーが発生しやすい手動プロセスを使用する必要なく、コードを簡単に展開できるようになります。

構成は[データ ドリブン](../configurations/configData.md)でもあるため、開発者が関与することなく、運用側で簡単に環境を特定および変更することができます。

## <a name="desired-state-configuration-on-premises-and-off-premises"></a>オンプレミスとオフプレミスの Desired State Configuration
DSC を使用して、オンプレミスとオフプレミスの両方の展開を管理できます。
オンプレミスのソリューションの場合、DSC では[プル サーバー](../pull-server/pullServer.md)を使用してマシンの管理を一元化し、それらの状態をレポートできます。
クラウド ソリューションの場合、DSC は Windows が使用可能なすべての場所で使用できます。
Azure では、DSC のレポート作成を一元化する [Azure Automation](https://azure.microsoft.com/en-us/documentation/services/automation/) など、Desired State Configuration に基づいて構築された特定のサービスも提供しています。

## <a name="dsc-and-compatibility"></a>DSC と互換性

DSC は Windows Server 2012 R2 で導入されましたが、Windows Management Framework (WMF) パッケージを使用してダウンレベル オペレーティング システムで使用できます。
WMF の詳細については、[PowerShell のホーム ページ](/powershell/)をご覧ください。

DSC は、Linux の管理にも使用できます。 詳細については、[Linux 用 DSC の概要](../getting-started/lnxGettingStarted.md)に関するページをご覧ください。
