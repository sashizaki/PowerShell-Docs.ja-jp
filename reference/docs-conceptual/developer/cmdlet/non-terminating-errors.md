---
title: 終了しないエラー |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 468dabd6-bfeb-448d-8e09-0996db516edd
caps.latest.revision: 8
ms.openlocfilehash: 5f804756e0e3e867832f15f50967fd6987f160a5
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369601"
---
# <a name="non-terminating-errors"></a>終了しないエラー

このトピックでは、終了しないエラーの報告に使用する方法について説明します。 また、コマンドレット内からメソッドを呼び出す方法についても説明します。

終了しないエラーが発生した場合、コマンドレットは[WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)メソッドを呼び出してこのエラーを報告する必要があります。 コマンドレットが終了しないエラーを報告した場合、コマンドレットはこの入力オブジェクトおよびさらに受信パイプラインオブジェクトに対して引き続き操作できます。 コマンドレットで[WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)メソッドを呼び出すと、コマンドレットは、終了しないエラーの原因となった状態を説明するエラーレコードを書き込むことができます。 エラーレコードの詳細については、「 [Windows PowerShell エラーレコード](./windows-powershell-error-records.md)」を参照してください。

コマンドレットは、入力処理メソッド内から必要に応じて[WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)を呼び出すことができます。 ただし、コマンドレットで[WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)を呼び出すことができるのは、 [system](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing).......................................................[コマンドレット](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)、または、または[システム](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)の入力処理メソッド。 別のスレッドから[WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)を呼び出さないでください。 代わりに、エラーをメインスレッドに送り返します。

## <a name="see-also"></a>参照

[WriteError (システム管理)](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

[システムの管理... コマンドレット](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[システムの管理....................](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[システムの管理... コマンドレット](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[Windows PowerShell エラーレコード](./windows-powershell-error-records.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
