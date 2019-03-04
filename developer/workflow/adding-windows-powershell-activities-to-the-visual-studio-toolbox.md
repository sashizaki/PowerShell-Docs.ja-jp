---
title: Visual Studio ツールボックスへの Windows PowerShell アクティビティの追加 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9c8ef289-0659-42d1-9976-044b144201eb
caps.latest.revision: 6
ms.openlocfilehash: 2a8372d937fc3c959f7d829bb52495048423d506
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56863568"
---
# <a name="adding-windows-powershell-activities-to-the-visual-studio-toolbox"></a>Visual Studio ツールボックスに Windows PowerShell アクティビティを追加する

ワークフロー デザイナーを使用して、PowerShell ワークフローを作成する前に、Visual Studio のワークフロー コンソール アプリケーション プロジェクトのツールボックスに PowerShell アクティビティを追加する必要があります。 次の手順では、Microsoft.PowerShell.Core.Activities アセンブリから、Visual Studio のツールボックスにアクティビティを追加する方法を示します。

### <a name="adding-windows-powershell-activities-to-the-toolbox"></a>Windows PowerShell のアクティビティをツールボックスに追加します。

1. Visual Studio で新しいワークフロー コンソール アプリケーション プロジェクトを作成します。

2. **ビュー**  メニューのをクリックして**ツールボックス**します。

3. ツールボックスの内側を右クリックして、ツールボックスに新しいタブを追加**タブの追加**、新しいタブなどの「PowerShell アクティビティ」名前を付けます。

   タブを追加する PowerShell アクティビティをツールボックスには、その他のツールとは別にグループ化することができます。

4. 新しいツールボックス タブのをクリックして**アイテムの選択.**.**ツールボックス アイテムの選択**ダイアログが表示されます。

5. **ツールボックス アイテムの選択**ダイアログ ボックスで、をクリックして、 **System.Activities**タブ。

6. クリックして**参照**します。

7. %WINDIR%\Microsoft.NET\assembly\GAC_MSIL\Microsoft.PowerShell.Core.Activities\v4.0_3.0.0.0__31bf3856ad364e フォルダーに移動し、Microsoft.PowerShell.Core.Activities.dll をダブルクリックします。

8. **[OK]** をクリックします。 Microsoft.PowerShell.Core.Activities アセンブリによって定義されたアクティビティは、ツールボックスで使用できるようになりました。

## <a name="see-also"></a>参照

[Windows PowerShell ワークフローを記述する](./writing-a-windows-powershell-workflow.md)

[Windows PowerShell のアクティビティとワークフローを作成します。](./creating-a-workflow-with-windows-powershell-activities.md)