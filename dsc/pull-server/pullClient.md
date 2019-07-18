---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC プル クライアントのセットアップ
ms.openlocfilehash: 54c68ac26e5388260e252ce01418170e26ddecde
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62079644"
---
# <a name="setting-up-a-dsc-pull-client"></a>DSC プル クライアントのセットアップ

> 適用先:Windows PowerShell 4.0、Windows PowerShell 5.0

> [!IMPORTANT]
> プル サーバー (Windows Feature *DSC-Service*) は、Windows Server のサポート対象のコンポーネントですが、新機能がオファーされる予定はありません。 管理対象のクライアントは、(Windows Server のプル サーバー以降の機能が含まれる) [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) または、[こちら](pullserver.md#community-solutions-for-pull-service)に列挙されているコミュニティ ソリューションのいずれかに切り替えを開始することをお勧めします。

各ターゲット ノードに対し、プル モードを使用するように指示する必要があります。また、プル サーバーに接続して構成とリソースを取得し、レポート データの送信先にするための URL またはファイルの場所を指定する必要があります。

次のトピックでは、プル クライアントをセットアップする方法について説明します。

* [構成名を使用したプル クライアントのセットアップ](pullClientConfigNames.md)
* [構成 ID を使用したプル クライアントのセットアップ](pullClientConfigID.md)

> [!NOTE]
> これらのトピックは、PowerShell 5.0 に適用されます。 PowerShell 4.0 でのプル クライアントのセットアップについては、「[PowerShell 4.0 での構成 ID を使用したプル クライアントのセットアップ](pullClientConfigID4.md)」を参照してください。