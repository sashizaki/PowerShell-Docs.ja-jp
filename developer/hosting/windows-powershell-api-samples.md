---
title: Windows PowerShell API のサンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82df2cde-ba12-46d2-b6ec-da5455fd9b57
caps.latest.revision: 8
ms.openlocfilehash: a472f07cb24b0de8e5dcdfcaddd2802575318d7a
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860778"
---
# <a name="windows-powershell-api-samples"></a>Windows PowerShell API サンプル

このセクションには、機能が制限されている実行空間を作成する方法と、実行空間を指定する実行空間プールを使用してコマンドを非同期的に実行する方法を示すサンプル コードが含まれます。 Microsoft Visual Studio を使用して、コンソール アプリケーションを作成し、このセクションのトピックから、ホスト アプリケーションにコードをコピーすることができます。

## <a name="in-this-section"></a>このセクションの内容

[PowerShell01 サンプル](./windows-powershell01-sample.md)このサンプルは、使用する方法を示します、 [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)実行空間の機能を制限するオブジェクト。 このサンプルの出力は、実行空間、プライベートとしてコマンドレットをマークする方法、追加する方法と削除コマンドレットとプロバイダーの言語モードを制限する方法を示します、プロキシ コマンドを追加する方法。

[PowerShell02 サンプル](./windows-powershell02-sample.md)実行空間プールの実行空間を使用してコマンドを非同期的に実行する方法を示します。 サンプルでは、コマンドの一覧を生成し、必要がある場合、Windows PowerShell エンジンが、プールから、実行空間を開くときにこれらのコマンドを実行します。