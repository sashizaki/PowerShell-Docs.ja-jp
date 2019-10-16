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
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72359651"
---
# <a name="adding-windows-powershell-activities-to-the-visual-studio-toolbox"></a>Visual Studio ツールボックスに Windows PowerShell アクティビティを追加する

ワークフローデザイナーを使用して PowerShell ワークフローを作成する前に、まず Visual Studio Workflow コンソールアプリケーションプロジェクトの [ツールボックス] に PowerShell アクティビティを追加する必要があります。 次の手順は、Visual Studio のツールボックスにアクティビティを追加する方法を示しています。

### <a name="adding-windows-powershell-activities-to-the-toolbox"></a>ツールボックスへの Windows PowerShell アクティビティの追加

1. Visual Studio で新しいワークフローコンソールアプリケーションプロジェクトを作成します。

2. **[表示]** メニューの **[ツールボックス]** をクリックします。

3. ツールボックスの内部を右クリックして [**タブの追加]** をクリックし、新しいタブに「PowerShell アクティビティ」などの名前を付けて、ツールボックスに新しいタブを追加します。

   タブを追加すると、PowerShell アクティビティをツールボックスの他のツールとは別にグループ化できます。

4. 新しいツールボックス タブで、**項目の選択**... をクリックします。**ツールボックスアイテムの選択** ダイアログボックスが表示されます。

5. **[ツールボックスアイテムの選択]** ダイアログで、 **[システム]** タブをクリックします。

6. **[参照]** をクリックします。

7. %WINDIR%\Microsoft.NET\assembly\GAC_MSIL\Microsoft.PowerShell.Core.Activities\v4.0_3.0.0.0__31bf3856ad364e フォルダーに移動し、[] をダブルクリックします。

8. **[OK]** をクリックします。 これで、[ツールボックス] で使用できるようになりました。

## <a name="see-also"></a>参照

[Windows PowerShell ワークフローを記述する](./writing-a-windows-powershell-workflow.md)

[Windows PowerShell アクティビティを使用したワークフローの作成](./creating-a-workflow-with-windows-powershell-activities.md)