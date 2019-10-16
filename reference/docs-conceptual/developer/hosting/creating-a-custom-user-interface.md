---
title: カスタムユーザーインターフェイスを作成する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d7286443-eed4-43d5-b809-50cdcdcba088
caps.latest.revision: 4
ms.openlocfilehash: 23518c625fe1138e1bd2bcc895274cb21d7daf8a
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367631"
---
# <a name="creating-a-custom-user-interface"></a>カスタム ユーザー インターフェイスを作成する

Windows PowerShell には、Windows PowerShell エンジンをホストするカスタム対話型 UI を作成できる抽象クラスとインターフェイスが用意されています。 カスタム UI を作成するには、 [PSHost](/dotnet/api/System.Management.Automation.Host.PSHost)クラスを実装する必要があります。 必要に応じて、 [Pshostrawuserinterface](/dotnet/api/System.Management.Automation.Host.PSHostRawUserInterface)クラスと[Pshostuserinterface](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface)クラスを実装することもできます。この場合は、[クラスとIhostsupportsinteractivesession](/dotnet/api/System.Management.Automation.Host.IHostSupportsInteractiveSession)と[Ihostuisupportsmultiplechoiceselection](/dotnet/api/System.Management.Automation.Host.IHostUISupportsMultipleChoiceSelection)の各インターフェイスがあることをテストしています。
