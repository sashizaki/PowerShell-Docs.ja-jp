---
title: 実行空間を作成する |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 0c27e2bf54e16a3bdc93c4b91629893bb1cc1e3e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779575"
---
# <a name="creating-runspaces"></a>実行空間を作成する

実行空間は、ホストアプリケーションによって呼び出されるコマンドのオペレーティング環境です。 この環境には、現在存在しているコマンドとデータ、および現在適用されているすべての言語制限が含まれます。

 ホストアプリケーションは、使用可能なすべてのコアコマンドを含む、Windows PowerShell によって提供される既定の実行空間を使用することも、使用可能なコマンドのサブセットのみを含むカスタム実行空間を作成することもできます。 カスタマイズされた実行空間を作成するには、 [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)オブジェクトを作成し、実行空間に割り当てます。

## <a name="runspace-tasks"></a>実行空間タスク

1. [InitialSessionState を作成する](./creating-an-initialsessionstate.md)

2. [制約付き実行空間を作成する](./creating-a-constrained-runspace.md)

3. [複数の実行空間を作成する](./creating-multiple-runspaces.md)

## <a name="see-also"></a>参照
