---
ms.date: 10/11/2019
keywords: DSC, PowerShell, 構成, セットアップ
title: 意思決定者向け Desired State Configuration の概要
ms.openlocfilehash: bb73ee8fe636272f99989aa45712fe34fedad617
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "75870797"
---
# <a name="desired-state-configuration-overview-for-decision-makers"></a>意思決定者向け Desired State Configuration の概要

このドキュメントでは、PowerShell Desired State Configuration (DSC) を使用するビジネス上の利点について説明します。これはテクニカル ガイドではありません。

## <a name="what-is-dsc"></a>DSC とは

PowerShell DSC は、Windows に組み込まれた構成管理プラットフォームであり、オープン標準に基づいています。 DSC には、展開ライフサイクルの各ステージ (開発、テスト、実稼働前、実稼働) およびスケールアウト中に、確実かつ一貫した機能を実現するための柔軟性が備わっています。

DSC は[構成](../configurations/configurations.md)を中心としています。 構成とは、特定の特性を持つコンピューター (またはノード) で構成された環境を記述する PowerShell スクリプトです。 これらの特性は、特定の Windows 機能が有効になっていることを確認するなどの単純な場合や、SharePoint の展開のように複雑な場合があります。

DSC には、監視とレポートの機能が組み込まれています。 システムが適合しなくなった場合、DSC は警告を生成し、システムを修正するために機能することができます。

## <a name="benefits-of-using-dsc"></a>DSC を使用する利点

構成の設計によって、それらの読み取り、保存、および更新を行う方法が簡略化されます。 構成では、ターゲット デバイスの状態が宣言されます。デバイスをその状態にするための手順が記述されるわけではありません。 これらの要因によって、DSC を使用した構成の学習、導入、実装、および保守にかかるコストが削減されます。

構成を作成することは、複雑な展開手順が 1 つの場所で、**信頼できる唯一のソース**として取得されることを意味します。 構成を使うと、コンピューターの特定のセットを繰り返し展開する場合にエラーが発生する可能性が低下します。 また、展開の速度と信頼性が向上するため、複雑な展開での迅速なターンアラウンドを実現できます。

構成は、[PowerShell ギャラリー](https://powershellgallery.com)を介して共有できます。 実行する必要がある作業について、一般的なシナリオやベスト プラクティスが既に存在している可能性があります。

## <a name="dsc-and-devops"></a>DSC と DevOps

DSC は、[DevOps](/archive/blogs/ashleymcglone/devops-for-n00bs-ie-windows-people-like-me) を念頭に置いて設計されました。 迅速な展開と反復を可能にする、人、プロセス、ツールの組み合わせであり、内部か外部かに関わらずエンド ユーザーに価値を提供することに重点が置かれています。 環境を定義する単一の構成によって、開発者が各自の要件を構成にエンコードし、その構成をソース管理にチェックインできるようになります。 そして、運用チームは、エラーが発生しやすい手動プロセスを経由せずにコードを展開できるようになります。

構成は[データドリブン](../configurations/configData.md)です。 定義されたデータにより、開発者が関与することなく、運用で簡単に環境の特定と変更を行えます。

## <a name="dsc-on-premises-and-off-premises"></a>オンプレミスおよびオフプレミスの DSC

DSC では、オンプレミスとオフプレミスの展開を管理できます。 オンプレミスのソリューションの場合、DSC には、コンピューターの管理を一元化し、それらの状態をレポートするために使用される[プル サーバー](../pull-server/pullServer.md)が備わっています。 オフプレミスのクラウド ソリューションの場合、Windows を使用できる任意の場所で DSC を使用できます。
Azure には、DSC レポートを一元化する [Azure Automation](/azure/automation) など、DSC に基づく特定のサービスがあります。

## <a name="dsc-and-compatibility"></a>DSC と互換性

DSC は Windows Server 2012 R2 で導入されましたが、Windows Management Framework (WMF) 経由で下位バージョンのオペレーティング システムで使用できます。 WMF の詳細については、「[Windows Management Framework](/powershell/scripting/wmf/overview)」をご覧ください。

DSC を使用して Linux を管理できます。 詳細については、[Linux 用 DSC の概要](../getting-started/lnxGettingStarted.md)に関するページをご覧ください。
