---
title: GetProc03 (VB.NET) サンプルコード |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ff94c452-d4ec-4492-ac20-61ad52f8ae8c
caps.latest.revision: 7
ms.openlocfilehash: a0a88ca517347a94fc81534caace6efa0f13fdd7
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72360311"
---
# <a name="getproc03-vbnet-sample-code"></a>GetProc03 (VB.NET) サンプル コード

次のコードは、パイプライン入力を受け入れることができる `Get-Process` コマンドレットの実装を示しています。 この実装は、パイプライン入力を受け取り、指定された名前に基づいてローカルコンピューターからプロセス情報を取得し、 [WriteObject (system.object, system.string)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_)メソッドをパイプラインにオブジェクトを送信するための出力機構として使用する、`Name` パラメーターを定義します。

## <a name="code-sample"></a>コード サンプル

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesgetproc03#getproc03vbAll](Msh_samplesgetproc03#getproc03vbAll)]  -->
