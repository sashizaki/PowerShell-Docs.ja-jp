---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 6c036c2d8f97e559d20dd3ac40133fa06f5dab08
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2018
---
# <a name="separation-of-node-and-configuration-ids"></a>ノード ID と構成 ID の分離

## <a name="overview"></a>概要

プル モードで DSC を使う場合の柔軟性を高め、簡素化するために、今回のリリースでいくつかの機能が追加されました。 これらの機能は、複数のノードに構成を容易にセットアップして展開できる柔軟性と同時に、各ノードの状態を追跡して情報を個別にレポートできる機能も実現します。
追加された機能は次のとおりです。

* コンピューターの構成を識別する構成名。 この名前は、複数のターゲット ノードで共有できます。
* 1 つのノードを一意に識別するエージェント ID
* ターゲット ノードが初めてプル サーバーに接続した時点でのみ実行される登録ステップ

**注:** これらの機能は追加されたものです。既存のプル機能や概念と置き換わるものでありません。 このリリースで出荷された新しいプル サーバーでは、これらの新機能または以前の機能を使うことができます。

詳細については、「[構成名を使用したプル クライアントのセットアップ](https://msdn.microsoft.com/powershell/dsc/pullclientconfignames)」を参照してください。
