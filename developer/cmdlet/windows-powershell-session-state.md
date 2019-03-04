---
title: Windows PowerShell セッションの状態 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Cmdlets [PowerShell], session state
- session state [PowerShell]
ms.assetid: 74912940-2b10-4a76-b174-6d035d71c02b
caps.latest.revision: 8
ms.openlocfilehash: 5d4effb508c9f2544832dad557671520cb0a7ac7
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862988"
---
# <a name="windows-powershell-session-state"></a>Windows PowerShell セッション状態

セッション状態は、Windows PowerShell セッションまたはモジュールの現在の構成を参照します。 Windows PowerShell セッションは、コマンド ライン ユーザーまたはプログラムによって、ホスト アプリケーションによって対話的に使用される運用環境です。 セッションのセッション状態が"グローバル セッション状態"と呼ばれます。

開発者の観点からは、Windows PowerShell セッションは、ホスト アプリケーションが Windows PowerShell 実行空間を開くと、実行空間が閉じられますまでの時間を指します。 別の方法で検索すると、セッションは、実行空間が存在する場合に呼び出される、Windows PowerShell エンジンのインスタンスの有効期間です。

## <a name="module-session-state"></a>モジュールのセッションの状態

モジュール セッション状態は、モジュール、またはその入れ子になったモジュールの 1 つは、セッションにインポートされるたびに作成されます。 モジュールをエクスポートするコマンドレット、関数、またはスクリプトなど、要素と、セッションのグローバル セッション状態にその要素への参照が追加されます。 ただし、要素が実行されるモジュールのセッション状態で実行されます。

## <a name="session-state-data"></a>セッション状態データ

セッション状態データは、パブリックまたはプライベートにできます。 パブリック データは、セッション状態の外部からの呼び出しに使用できるプライベート データはセッション状態の内部からの呼び出しでのみ使用できます。 たとえば、モジュールは、モジュールによってのみ、または内部でのみ呼び出すことができるプライベート関数があるエクスポートされたパブリック要素。 .NET Framework 型のプライベートおよびパブリック メンバーに似ています。

セッション状態データは、現在の Windows PowerShell セッションのコンテキスト内での実行エンジンの現在のインスタンスが格納されます。 セッション状態データは、次の項目で構成されます。

- パス情報

- ドライブの情報

- Windows PowerShell プロバイダーの情報

- インポートしたモジュールとモジュールによってエクスポートされるモジュール要素 (コマンドレット、関数、スクリプトなど) への参照に関する情報。 この情報は、これらの参照はグローバル セッション状態のみです。

- セッション状態変数の情報

## <a name="accessing-session-state-data-within-cmdlets"></a>コマンドレット内でセッション状態データへのアクセス

コマンドレットでは、セッション状態データをかアクセスを通じて間接的に、 [System.Management.Automation.Pscmdlet.Sessionstate*](/dotnet/api/System.Management.Automation.PSCmdlet.SessionState)または直接コマンドレット クラスのプロパティ、 [System.Management.Automation.Sessionstate](/dotnet/api/System.Management.Automation.SessionState)クラス。 [System.Management.Automation.Sessionstate](/dotnet/api/System.Management.Automation.SessionState)クラスには、さまざまな種類のセッション状態データを調査するために使用できるプロパティが用意されています。

## <a name="see-also"></a>参照

[System.Management.Automation.Pscmdlet.Sessionstate](/dotnet/api/System.Management.Automation.PSCmdlet.SessionState)

[System.Management.Automation.Sessionstate?Displayproperty=Fullname](/dotnet/api/System.Management.Automation.SessionState)

[Windows PowerShell コマンドレット](./cmdlet-overview.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)

[Windows PowerShell シェル SDK](../windows-powershell-reference.md)
