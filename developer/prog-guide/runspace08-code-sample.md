---
title: RunSpace08 コード サンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0f286201-8a02-4b00-9a2c-1b833ccdbdbf
caps.latest.revision: 7
ms.openlocfilehash: 1a09cfee3bb317de6c1ca4dde86a87d72a498e6e
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858608"
---
# <a name="runspace08-code-sample"></a>RunSpace08 コード サンプル

記載されている Runspace08 サンプルのソース コードを次に示します[、コンソール アプリケーションを追加するパラメーターを作成コマンド](http://msdn.microsoft.com/en-us/848b2b46-60f1-4a86-b448-cfc7c0cccfba)します。 このサンプル アプリケーション、実行空間を作成します、パイプラインを作成、パイプラインに 2 つのコマンドを追加します、2 番目のコマンドを 2 つのパラメーターを追加します。 およびし、パイプラインを実行します。 パイプラインに追加されるコマンドは、`Get-Process`と`Sort-Object`コマンドレット。

## <a name="code-sample"></a>コード サンプル

[!code-csharp[Runspace08.cs](../../powershell-sdk-samples/SDK-2.0/csharp/Runspace08/Runspace08.cs#L11-L86 "Runspace08.cs")]

## <a name="see-also"></a>参照

[Windows PowerShell SDK](../windows-powershell-reference.md)