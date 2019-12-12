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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367581"
---
# <a name="creating-runspaces"></a>実行空間を作成する

実行空間は、ホストアプリケーションによって呼び出されるコマンドのオペレーティング環境です。 この環境には、現在存在しているコマンドとデータ、および現在適用されているすべての言語制限が含まれます。

 ホストアプリケーションは、使用可能なすべてのコアコマンドを含む、Windows PowerShell によって提供される既定の実行空間を使用することも、使用可能なコマンドのサブセットのみを含むカスタム実行空間を作成することもできます。 カスタマイズされた実行空間を作成するには、 [Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)オブジェクトを作成し、それを実行空間に割り当てます。

## <a name="runspace-tasks"></a>実行空間タスク

1. [InitialSessionState の作成](./creating-an-initialsessionstate.md)

2. [制約付き実行空間の作成](./creating-a-constrained-runspace.md)

3. [複数の実行空間の作成](./creating-multiple-runspaces.md)

## <a name="see-also"></a>参照
