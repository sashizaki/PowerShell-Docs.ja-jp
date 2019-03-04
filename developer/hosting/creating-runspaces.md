---
title: 実行空間を作成する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 17f323c3-e873-449e-8a28-477f1c6b5e12
caps.latest.revision: 6
ms.openlocfilehash: b4e61600f68521e4e7ab56ceae3349381e88a70a
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857908"
---
# <a name="creating-runspaces"></a>実行空間を作成する

実行空間は、ホスト アプリケーションによって呼び出されるコマンドの動作環境です。 この環境には、コマンドが現在存在するデータと現在適用される言語の制限が含まれています。

 ホスト アプリケーションでは、使用可能なコアのすべてのコマンドを含む、Windows PowerShell によって提供される既定の実行空間を使用したり、使用可能なコマンドのサブセットのみが含まれるカスタムの実行空間を作成することができます。 作成するカスタマイズされた実行空間を作成する、 [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)オブジェクトを実行空間に割り当てます。

## <a name="runspace-tasks"></a>タスクの実行空間

1. [InitialSessionState を作成します。](./creating-an-initialsessionstate.md)

2. [制約付き実行空間を作成します。](./creating-a-constrained-runspace.md)

3. [複数の実行空間を作成します。](./creating-multiple-runspaces.md)

## <a name="see-also"></a>参照
