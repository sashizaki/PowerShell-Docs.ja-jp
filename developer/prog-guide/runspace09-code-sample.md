---
title: RunSpace09 コード サンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 136e451f-767b-42e0-bd6f-6486693abd5e
caps.latest.revision: 6
ms.openlocfilehash: 1a21af4b48a414d9c9fee57871eacb0a39c9ab11
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67734899"
---
# <a name="runspace09-code-sample"></a>RunSpace09 コード サンプル

記載されている Runspace09 サンプルのソース コードを次に示します[作成、コンソール アプリケーションを呼び出す非同期をパイプライン](https://msdn.microsoft.com/en-us/198c1c94-2a06-457e-93ce-c0d910618e47)します。 このサンプル アプリケーションを作成しますと、実行空間が表示されます、作成、パイプラインを非同期的に起動し、スクリプトを非同期的に処理するイベントのパイプラインは。 このアプリケーションで実行されるスクリプトは、0.5 秒の間隔 (500 ミリ秒) で、1 ~ 10 の整数を作成します。

## <a name="code-sample"></a>コード サンプル

[!code-csharp[Runspace09.cs](../../powershell-sdk-samples/SDK-2.0/csharp/Runspace09/Runspace09.cs#L11-L113 "Runspace09.cs")]

## <a name="see-also"></a>関連項目

[Windows PowerShell SDK](../windows-powershell-reference.md)