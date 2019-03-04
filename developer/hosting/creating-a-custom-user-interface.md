---
title: カスタム ユーザー インターフェイスを作成する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d7286443-eed4-43d5-b809-50cdcdcba088
caps.latest.revision: 4
ms.openlocfilehash: 23518c625fe1138e1bd2bcc895274cb21d7daf8a
ms.sourcegitcommit: c581c4c8036edf55147e7bce4b00c860da6c5a8b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/25/2019
ms.locfileid: "56863718"
---
# <a name="creating-a-custom-user-interface"></a>カスタム ユーザー インターフェイスを作成する

Windows PowerShell では、抽象クラスと、Windows PowerShell エンジンをホストするカスタムの対話型 UI を作成するためのインターフェイスを提供します。 カスタム UI を作成するには、実装する必要があります、 [System.Management.Automation.Host.PSHost](/dotnet/api/System.Management.Automation.Host.PSHost)クラス。 必要に応じて、実装することも、 [System.Management.Automation.Host.Pshostrawuserinterface](/dotnet/api/System.Management.Automation.Host.PSHostRawUserInterface)と[System.Management.Automation.Host.Pshostuserinterface](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface)クラス、および、 [System.Management.Automation.Host.Ihostsupportsinteractivesession](/dotnet/api/System.Management.Automation.Host.IHostSupportsInteractiveSession)と[System.Management.Automation.Host.Ihostuisupportsmultiplechoiceselection](/dotnet/api/System.Management.Automation.Host.IHostUISupportsMultipleChoiceSelection)インターフェイス。
