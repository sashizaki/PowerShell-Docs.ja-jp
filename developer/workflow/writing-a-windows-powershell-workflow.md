---
title: Windows PowerShell ワークフローの作成 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2551ceed-836f-4275-9fc0-ea68446d6a35
caps.latest.revision: 7
ms.openlocfilehash: 4f0be193fb5b5c753d040a48e5f49235ece11708
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857408"
---
# <a name="writing-a-windows-powershell-workflow"></a>Windows PowerShell ワークフローを記述する

XAML ワークフローを作成するには、Visual studio ワークフロー デザイナーに Windows PowerShell アセンブリによって公開されているアクティビティを追加します。 次の Windows PowerShell アセンブリは、ワークフローが有効なアクティビティを公開します。

> [!IMPORTANT]
> XAML ワークフローは、ワークフローのヘルプを提供する場合、モジュールとしてパッケージ化する必要があります。 モジュールについては、次を参照してください。 [Windows PowerShell モジュールの記述](../module/writing-a-windows-powershell-module.md)します。

- [Microsoft.Powershell.Activities](/dotnet/api/Microsoft.PowerShell.Activities)

- [Microsoft.Powershell.Core.Activities](/dotnet/api/Microsoft.PowerShell.Core.Activities)

- [Microsoft.Powershell.Diagnostics.Activities](/dotnet/api/Microsoft.PowerShell.Diagnostics.Activities)

- [Microsoft.Powershell.Management.Activities](/dotnet/api/Microsoft.PowerShell.Management.Activities)

- [Microsoft.Powershell.Security.Activities](/dotnet/api/Microsoft.PowerShell.Security.Activities)

- [Microsoft.Powershell.Utility.Activities](/dotnet/api/Microsoft.PowerShell.Utility.Activities)

  次のトピックでは、Windows PowerShell のアクティビティを使用して、ワークフローを作成する方法について説明します。

- [Visual Studio ツールボックスへの Windows PowerShell アクティビティの追加](./adding-windows-powershell-activities-to-the-visual-studio-toolbox.md)

- [Windows PowerShell のアクティビティとワークフローを作成します。](./creating-a-workflow-with-windows-powershell-activities.md)

- [Windows PowerShell スクリプトを使用してワークフローを作成します。](./creating-a-workflow-by-using-a-windows-powershell-script.md)

- [インポートして、Windows PowerShell ワークフローを呼び出す](./importing-and-invoking-a-windows-powershell-workflow.md)

- [Windows PowerShell コマンドレットからワークフロー アクティビティを作成します。](./creating-a-workflow-activity-from-a-windows-powershell-cmdlet.md)