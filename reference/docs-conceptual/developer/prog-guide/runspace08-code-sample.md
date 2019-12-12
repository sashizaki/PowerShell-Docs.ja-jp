---
title: RunSpace08 コードサンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0f286201-8a02-4b00-9a2c-1b833ccdbdbf
caps.latest.revision: 7
ms.openlocfilehash: 20032913969606f722f3768b0433775aeaa8c3a8
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72366481"
---
# <a name="runspace08-code-sample"></a>RunSpace08 コード サンプル

次に示すのは、[コマンドにパラメーターを追加するコンソールアプリケーションの作成](https://msdn.microsoft.com/en-us/848b2b46-60f1-4a86-b448-cfc7c0cccfba)に関するページで説明されている Runspace08 サンプルのソースコードです。 このサンプルアプリケーションでは、実行空間を作成し、パイプラインを作成して、パイプラインに2つのコマンドを追加し、2つのパラメーターを2番目のコマンドに追加してから、パイプラインを実行します。 パイプラインに追加されるコマンドは、`Get-Process` と `Sort-Object` のコマンドレットです。

## <a name="code-sample"></a>コード サンプル

[!code-csharp[Runspace08.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/Runspace08/Runspace08.cs#L11-L86 "Runspace08.cs")]

## <a name="see-also"></a>参照

[Windows PowerShell SDK](../windows-powershell-reference.md)
