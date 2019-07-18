---
title: Windows PowerShell のアクティビティとワークフローを作成する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb55971a-4ea4-4c51-aeff-4e0bb05a51b2
caps.latest.revision: 6
ms.openlocfilehash: 98cac43698b3f537ee318cd2570b2174631665a7
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62080444"
---
# <a name="creating-a-workflow-with-windows-powershell-activities"></a>Windows PowerShell アクティビティでワークフローを作成する

Visual Studio のツールボックスからアクティビティを選択して、ワークフロー デザイナー ウィンドウにドラッグすることによって、Windows PowerShell ワークフローを作成できます。 Visual Studio ツールボックスに Windows PowerShell のアクティビティを追加する方法の詳細については、次を参照してください。[を Visual Studio ツールボックスに追加の Windows PowerShell アクティビティ](./adding-windows-powershell-activities-to-the-visual-studio-toolbox.md)します。

次の手順では、ユーザーが指定したコンピューターのグループのドメインの状態を確認、状態をもう一度確認し、既に参加していない場合に、ドメインに参加するワークフローを作成する方法について説明します。

### <a name="setting-up-the-project"></a>プロジェクトの設定

1. 」の手順に従って[を Visual Studio ツールボックスに追加の Windows PowerShell アクティビティ](./adding-windows-powershell-activities-to-the-visual-studio-toolbox.md)ワークフロー プロジェクトを作成し、アクティビティを追加する、 [Microsoft.Powershell.Activities](/dotnet/api/Microsoft.PowerShell.Activities)と[Microsoft.Powershell.Management.Activities](/dotnet/api/Microsoft.PowerShell.Management.Activities)をツールボックスにアセンブリ。

2. 参照アセンブリとプロジェクトに関する System.Management.Automation、Microsoft.PowerShell.Activities、System.Management、Microsoft.PowerShell.Management.Activities、および Microsoft.PowerShell.Commands.Management を追加します。

### <a name="adding-activities-to-the-workflow"></a>ワークフローにアクティビティを追加します。

1. 追加、**シーケンス**アクティビティをワークフロー。

2. 名前付き引数を作成する`ComputerName`の引数の型と`String[]`します。 この引数は、確認し、参加するコンピューターの名前を表します。

3. 名前付き引数`DomainCred`型の[System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential)します。 この引数は、コンピューターをドメインに参加する権限を持つドメイン アカウントのドメインの資格情報を表します。

4. 名前付き引数`MachineCred`型の[System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential)します。 この引数は、確認し、参加するには、コンピューターの管理者の資格情報を表します。

5. 追加、 **ParallelForEach**内のアクティビティ、**シーケンス**アクティビティ。 入力`comp`と`ComputerName`内の要素をループが反復処理するためのテキスト ボックス、`ComputerName`配列。

6. 追加、**シーケンス**アクティビティの本体に、 **ParallelForEach**アクティビティ。 設定、 **DisplayName**するシーケンスのプロパティ`JoinDomain`します。

7. 追加、 **GetWmiObject**アクティビティを**JoinDomain**シーケンス。

8. プロパティを編集、 **GetWmiObject**アクティビティとして次のとおりです。

   |プロパティ|値|
   |--------------|-----------|
   |**Class**|"Win32_ComputerSystem"|
   |**PSComputerName**|{comp}|
   |**PSCredential**|MachineCred|

9. 追加、 **AddComputer**アクティビティを**JoinDomain**シーケンスした後、 **GetWmiObject**アクティビティ。

10. プロパティを編集、 **AddComputer**アクティビティとして次のとおりです。

    |プロパティ|値|
    |--------------|-----------|
    |**コンピューター名**|{comp}|
    |**DomainCredential**|DomainCred|

11. 追加、 **RestartComputer**アクティビティを**JoinDomain**シーケンスした後、 **AddComputer**アクティビティ。

12. プロパティを編集、 **RestartComputer**アクティビティとして次のとおりです。

    |プロパティ|値|
    |--------------|-----------|
    |**コンピューター名**|{comp}|
    |**資格情報**|MachineCred|
    |**の**|Microsoft.PowerShell.Commands.WaitForServiceTypes.PowerShell|
    |**Force**|True|
    |Wait|True|
    |PSComputerName|{""}|

13. 追加、 **GetWmiObject**アクティビティを**JoinDomain**シーケンスした後、 **RestartComputer**アクティビティ。 前と同じにするのには、そのプロパティを編集**GetWmiObject**アクティビティ。

    手順が完了したら、ワークフローのデザイン ウィンドウは次のようになります。

    ![ワークフロー デザイナーでの JoinDomain XAML](../media/joindomainworkflow.png)
    ![ワークフロー デザイナーでの JoinDomain XAML](../media/joindomainworkflow.png "JoinDomainWorkflow")