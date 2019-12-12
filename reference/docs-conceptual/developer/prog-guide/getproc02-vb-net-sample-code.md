---
title: GetProc02 (VB.NET) サンプルコード |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f3497546-5b3a-4e29-84ba-cd9747be64b3
caps.latest.revision: 6
ms.openlocfilehash: 4ec63ed32bd2906f5b027523aa0f253b51a5d873
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72366771"
---
# <a name="getproc02-vbnet-sample-code"></a>GetProc02 (VB.NET) サンプル コード

次のコードは、コマンドライン入力を受け入れる `Get-Process` コマンドレットの実装を示しています。 この実装では、コマンドライン入力を許可する `Name` パラメーターを定義し、 [WriteObject (system.object, system.string)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_)メソッドを出力機構として使用して、パイプラインに出力オブジェクトを送信することに注意してください。

## <a name="code-sample"></a>コード サンプル

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesgetproc02#getproc02vball](Msh_samplesgetproc02#getproc02vball)]  -->

## <a name="see-also"></a>参照

[Windows PowerShell SDK](../windows-powershell-reference.md)
