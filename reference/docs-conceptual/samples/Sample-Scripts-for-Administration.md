---
ms.date: 08/27/2018
keywords: PowerShell, コマンドレット
title: システム管理のサンプル スクリプト
ms.assetid: db6334ec-ace6-436d-ab88-77aefc817511
ms.openlocfilehash: 2fd5d16759f840e6f5809ba6e65e253279176b71
ms.sourcegitcommit: 9ac95601eebf792be636ee4d85e15c7a7c35422f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2019
ms.locfileid: "64933766"
---
# <a name="sample-scripts-for-system-administration"></a>システム管理のサンプル スクリプト

PowerShell の基本的な目標は、簡単なシステム管理を、対話型またはスクリプトで提供することです。 この例のコレクションでは、PowerShell を使用してシステムを管理するシナリオについて説明します。 例は、スクリプトから使用するか、または後で関数として使用することができます。

これらの例では、コマンドレットおよび外部ツールの両方を使用しています。 外部ツールの使用は、PowerShell の長期的な設計方針の一環です。 システムが成長しても、利用可能なツールセットで必要とするすべてのことができるわけではないという状況にユーザーは絶えず遭遇します。 PowerShell ソリューションでは、コマンドレット実装のみに依存するのでなく、利用可能な外部ツールとの統合がサポートされています。