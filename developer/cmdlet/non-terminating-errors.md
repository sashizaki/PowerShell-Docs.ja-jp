---
title: 未終了エラー |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 468dabd6-bfeb-448d-8e09-0996db516edd
caps.latest.revision: 8
ms.openlocfilehash: 5f804756e0e3e867832f15f50967fd6987f160a5
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58054359"
---
# <a name="non-terminating-errors"></a>終了しないエラー

このトピックでは、未終了エラーをレポートに使用する方法について説明します。 コマンドレットは、内からメソッドを呼び出す方法も説明します。

コマンドレットが呼び出すことによってこのエラーを報告する必要があります、未終了エラーが発生したときに、 [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)メソッド。 コマンドレットが、この入力オブジェクトとそれ以上の受信の動作を続行できますコマンドレットは、未終了エラーを報告、ときにオブジェクトをパイプラインします。 コマンドレットを呼び出す場合、 [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)メソッドでは、コマンドレットは、未終了エラーの原因となった状態を説明するエラー レコードを記述できます。 エラー レコードの詳細については、[Windows PowerShell のエラー レコード](./windows-powershell-error-records.md)を参照してください。

コマンドレットを呼び出すことができます[System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)処理メソッドの入力の中から必要です。 ただし、コマンドレットを呼び出すことができます[System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)を呼び出したスレッドからのみ、 [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)、または[System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)処理方法を入力します。 呼び出さない[System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)別のスレッドから。 代わりに、メイン スレッドへのエラーを通知します。

## <a name="see-also"></a>参照

[System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

[System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[Windows PowerShell のエラー レコード](./windows-powershell-error-records.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
