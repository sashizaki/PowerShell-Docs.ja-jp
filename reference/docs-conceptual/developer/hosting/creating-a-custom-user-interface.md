---
title: カスタムユーザーインターフェイスを作成する |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: ebbaba4231b54d42cdcdef07a3ff665bd207d696
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779779"
---
# <a name="creating-a-custom-user-interface"></a>カスタム ユーザー インターフェイスを作成する

Windows PowerShell には、Windows PowerShell エンジンをホストするカスタム対話型 UI を作成できる抽象クラスとインターフェイスが用意されています。 カスタム UI を作成するには、 [PSHost](/dotnet/api/System.Management.Automation.Host.PSHost)クラスを実装する必要があります。 必要に応じて、 [Pshostrawuserinterface](/dotnet/api/System.Management.Automation.Host.PSHostRawUserInterface)クラスと Pshostuserinterface クラス、および Ihostsupportsinteractivesession および[System.Management.Automation.Host.Pshostuserinterface](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface)インターフェイスを実装することもできます。と Ihostuisupportsmultiplechoiceselection の各インターフェイスを実装することもできます。 [System.Management.Automation.Host.Ihostsupportsinteractivesession](/dotnet/api/System.Management.Automation.Host.IHostSupportsInteractiveSession)と[System.Management.Automation.Host.Ihostuisupportsmultiplechoiceselection](/dotnet/api/System.Management.Automation.Host.IHostUISupportsMultipleChoiceSelection)のインターフェイスも同様です。
