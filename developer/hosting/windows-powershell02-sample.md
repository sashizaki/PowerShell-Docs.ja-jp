---
title: Windows PowerShell02 サンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 92492a7e-257d-47d3-b119-89df3c5545e8
caps.latest.revision: 9
ms.openlocfilehash: 89ad17257ebac56105a93672317a149515e80d32
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861068"
---
# <a name="windows-powershell02-sample"></a>Windows PowerShell02 サンプル

このサンプルでは、実行空間プールの実行空間を使用してコマンドを非同期的に実行する方法を示します。 サンプルでは、コマンドの一覧を生成し、必要がある場合、Windows PowerShell エンジンが、プールから、実行空間を開くときにこれらのコマンドを実行します。

## <a name="requirements"></a>要件

- このサンプルでは、Windows PowerShell 2.0 が必要です。

## <a name="demonstrates"></a>使用例

このサンプルでは、次の項目を示しています。

- 実行空間を同時に開く許可の数が最小値と最大 RunspacePool オブジェクトを作成しています。

- コマンドの一覧を作成します。

- コマンドを非同期的に実行します。

- 呼び出す、 [System.Management.Automation.Runspaces.Runspacepool.Getavailablerunspaces*](/dotnet/api/System.Management.Automation.Runspaces.RunspacePool.GetAvailableRunspaces)メソッドをいくつ実行空間は無料を参照してください。

- コマンドの出力をキャプチャ、 [System.Management.Automation.Powershell.Endinvoke*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke)メソッド。

## <a name="example"></a>例

このサンプルでは、実行空間プールの実行空間を開く方法と非同期的にこれらの実行空間でのコマンドを実行する方法を示します。

[!code-csharp[PowerShell02.cs](../../powershell-sdk-samples/SDK-2.0/csharp/PowerShell02/PowerShell02.cs#L11-L96 "PowerShell02.cs")]

## <a name="see-also"></a>参照

[Windows PowerShell ホスト アプリケーションの作成](./writing-a-windows-powershell-host-application.md)