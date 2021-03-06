---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: CI/CD パイプラインでの DSC のロールについて
description: この記事では、CI/CD パイプラインで構成とリソースを結合するために使用できるアプローチの種類について説明します。
ms.openlocfilehash: 8d06b86724eb25e657687e6518c01bb29d984264
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92647038"
---
# <a name="understanding-dscs-role-in-a-cicd-pipeline"></a>CI/CD パイプラインでの DSC のロールについて

この記事では、構成とリソースを結合するために使用できるアプローチの種類について説明します。
各シナリオの目標は同じで、サーバーの展開の終了状態に到達するために複数の構成を選択する場合の複雑さを軽減することです。 この例には、アプリケーションの状態を維持するアプリケーション所有者や、セキュリティ ベースラインへの変更をリリースする中央の管理チームなど、サーバーの展開の結果に貢献する複数のチームが考えられます。 ここでは、各アプローチのメリットとリスクなどを含む、微妙な差異について詳しく説明します。

![CI/CD パイプラインのプロセス フロー](media/authoringAdvanced/Pipeline.jpg)

## <a name="types-of-collaborative-authoring-techniques"></a>コラボレーションの作成方法の種類

この概念を有効にするために 2 つのソリューションがローカルの Configuration Manager に組み込まれています。

|        概念         |                    詳細情報                     |
| ---------------------- | ----------------------------------------------------------- |
| 部分構成 | [ドキュメント](../pull-server/partialConfigs.md)           |
| 複合リソース    | [ドキュメント](../resources/authoringResourceComposite.md) |

## <a name="understanding-the-impact-of-each-approach"></a>各アプローチの影響を理解する

これらのいずれかのソリューションを使用して、サーバーの展開の結果を管理することができます。 ただし、各アプローチの使用による影響には、大きな違いがあります。

## <a name="partial-configurations"></a>部分構成

部分構成を使用する場合、ローカルの Configuration Manager は複数の構成を個別に管理するように構成されます。 構成は個別にコンパイルされてから、ノードに割り当てられます。 これには、各構成の名前を使用して、LCM を事前に構成する必要があります。

![部分構成の図](media/authoringAdvanced/PartialConfiguration.jpg)

部分構成では、2 つ以上のチームにサーバーの構成に対する完全な制御を提供します。多くの場合、コミュニケーションやコラボレーションの利点はありません。

これにより、リソースの競合や意図しないオーバーライドが発生したり、最終的には、資産の真の構成の制御を失う可能性があることが、お客様からのフィードバックで報告されております。

さらに、お客様からは、このモデルを使用したときに、各制御チームの構成変更がリリース パイプラインを通じて完全にテストされているとは思えず、実稼働環境で予期しない結果につながるというフィードバックもいただいております。

**サーバーにリリースされたすべての変更を 1 つのパイプラインを使用して評価することが重要です。**

次の図では、チーム B はチーム A に部分構成をリリースします。そしてチーム A は両方の構成が適用されたサーバーに対してテストを実行します。 このモデルでは、1 つの機関だけが実稼働環境で変更を行う権限を持っています。

![部分的な 1 つのパイプラインの図](media/authoringAdvanced/PartialSinglePipeline.jpg)

チーム B から変更が必要な場合は、チーム A のソース管理環境に対して Pull Request を送信する必要があります。 次に、チーム A がテスト自動化を使用して変更を確認し、その変更によってサーバーでホストされているアプリケーションやサービスでエラーが発生しないことが確認できたら、運用環境にリリースします。

## <a name="composite-resources"></a>複合リソース

複合リソースは、リソースとしてパッケージ化された単なる DSC 構成です。 複合リソースを受け入れるように LCM を構成するための特別な要件はありません。 リソースは新しい構成内で使用され、1 つのコンパイル結果が 1 つの MOF ファイルになります。

![複合リソースの図](media/authoringAdvanced/CompositeResource.jpg)

複合リソースには、2 つの一般的なシナリオがあります。 1 つ目は、複雑さを軽減し、独自の概念を抽象化することです。 2 つ目は、すべてのテストが成功した後で、アプリケーション チームがリリース パイプラインを通じて運用環境に安全に展開するために、ベースラインのパッケージ化を許可することです。

```PowerShell
Configuration Name
{
  File 1
  {
    Ensure = "Present"
    Path = "c:\inetpub\file1.zip"
    Source = "http://uri/file1.zip"
  }
  Service A
  {
    Ensure = "Present"
    Name = "ServiceA"
    Status = "Running"
  }
  SecurityBaseline Settings
  {
    Ensure = "Present"
    Datacenter = "NorthAmerica"
  }
}
```

複合リソースは、パイプラインを使用して合成とコラボレーション両方を促進させつつ、運用の成熟度を高めます。

気付かないうちに、既に複合リソースを使用している場合があります。 **ServiceSet** はその一例です。
このリソースは、複数の Windows サービスの状態を個別にリストすることなく、管理します。 Name プロパティは、各サービスの名前を指定する文字列の配列を受け入れます。 構成のコンパイル時に、MOF には ServiceSet に渡される名前ごとに一意の Service セクションが格納されます。

組織には、すべてのサーバーにインストールする必要がある "エージェント" または "ミドルウェア" がある場合があります。 このようなツールとユーティリティの依存関係、セットアップ、および構成を管理するには、複合リソースが最善の答えです。

複数のサーバーにまたがるソリューションを担当する人またはチームが、自身の要件を含む構成を作成します。 次に、複合リソースのドキュメントで説明する手順を使用して、構成を複合リソースとしてパッケージ化します。 最後に、新しい複合リソースを、ファイル共有や NuGet フィードなど、アプリケーション チームが構成で使用できる場所に発行する必要があります。

チームは、新しいバージョンをリリースするたびに、その複合リソースのモジュール マニフェストでバージョン番号をインクリメントする場合があります。 アプリケーション チームは、アプリケーションの依存関係を管理するために作成する構成に複合リソースを含めます。 運用/セキュリティ チームは、リソースの新しいバージョンをリリースするときに、アプリケーション チームに新しい変更を通知します。

アプリケーション チームは、変更がベースラインに対してのみの場合は、実稼働環境へのリリースをトリガーすることがあります。
ただし、これにより、サービス停止のリスクの前にアプリケーションへの影響を評価する機会が与えられます。

> [!NOTE]
> 複合リソースの使用についてのフィードバックには、変更するには新しい MOF をコンパイルしてリリースする必要があるというご指摘がありました。 これは仕様です。 新しい構成リリースにはそれぞれ、各リソースの特定のバージョンへの静的参照を含める必要があります。また、実稼働サーバー ノードに到達する前にテストして検証する必要があります。 ソース管理からの変更のテストとリリースのプロセスにより、小さくても頻繁なバッチで変更をリリースするための安全な環境が作成されます。

リリース パイプラインを使用して、コア インフラストラクチャを管理する方法の詳細については、ホワイト ペーパー「[The Release Pipeline Model (リリース パイプライン モデル)](../further-reading/whitepapers.md)」を参照してください。
