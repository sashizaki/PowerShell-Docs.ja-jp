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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367631"
---
# <a name="creating-a-custom-user-interface"></a><span data-ttu-id="c41d4-102">カスタム ユーザー インターフェイスを作成する</span><span class="sxs-lookup"><span data-stu-id="c41d4-102">Creating a custom user interface</span></span>

<span data-ttu-id="c41d4-103">Windows PowerShell には、Windows PowerShell エンジンをホストするカスタム対話型 UI を作成できる抽象クラスとインターフェイスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="c41d4-103">Windows PowerShell provides abstract classes and interfaces that allow you to create a custom interactive UI that hosts the Windows PowerShell engine.</span></span> <span data-ttu-id="c41d4-104">カスタム UI を作成するには、 [PSHost](/dotnet/api/System.Management.Automation.Host.PSHost)クラスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c41d4-104">To create a custom UI, you must implement the [System.Management.Automation.Host.PSHost](/dotnet/api/System.Management.Automation.Host.PSHost) class.</span></span> <span data-ttu-id="c41d4-105">必要に応じて、 [Pshostrawuserinterface](/dotnet/api/System.Management.Automation.Host.PSHostRawUserInterface)クラスと [Pshostuserinterface](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface) クラス、および [Ihostsupportsinteractivesession](/dotnet/api/System.Management.Automation.Host.IHostSupportsInteractiveSession) およびインターフェイスを実装することもできます。と [Ihostuisupportsmultiplechoiceselection](/dotnet/api/System.Management.Automation.Host.IHostUISupportsMultipleChoiceSelection) の各インターフェイスを実装することもできます。とのインターフェイスも同様です。</span><span class="sxs-lookup"><span data-stu-id="c41d4-105">Optionally, you can also implement the [System.Management.Automation.Host.Pshostrawuserinterface](/dotnet/api/System.Management.Automation.Host.PSHostRawUserInterface)and [System.Management.Automation.Host.Pshostuserinterface](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface) classes, and the [System.Management.Automation.Host.Ihostsupportsinteractivesession](/dotnet/api/System.Management.Automation.Host.IHostSupportsInteractiveSession) and [System.Management.Automation.Host.Ihostuisupportsmultiplechoiceselection](/dotnet/api/System.Management.Automation.Host.IHostUISupportsMultipleChoiceSelection) interfaces.</span></span>
