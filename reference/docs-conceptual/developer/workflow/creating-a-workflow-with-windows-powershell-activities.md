---
title: Windows PowerShell アクティビティを使用したワークフローの作成 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb55971a-4ea4-4c51-aeff-4e0bb05a51b2
caps.latest.revision: 6
ms.openlocfilehash: 7d399786b9b43ee302493359d9702981045212e9
ms.sourcegitcommit: 01c60c0c97542dbad48ae34339cddbd813f1353b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2020
ms.locfileid: "78277468"
---
# <a name="creating-a-workflow-with-windows-powershell-activities"></a>Windows PowerShell アクティビティでワークフローを作成する

Windows PowerShell ワークフローを作成するには、Visual Studio のツールボックスからアクティビティを選択し、[ワークフローデザイナー] ウィンドウにドラッグします。 Visual Studio のツールボックスに Windows PowerShell アクティビティを追加する方法については、「 [Visual studio のツールボックスへの Windows Powershell アクティビティの追加](./adding-windows-powershell-activities-to-the-visual-studio-toolbox.md)」を参照してください。

次の手順では、ユーザー指定のコンピューターのグループのドメインステータスを確認し、まだ参加していない場合はドメインに参加させるワークフローを作成する方法について説明します。その後、状態をもう一度確認します。

### <a name="setting-up-the-project"></a>プロジェクトの設定

1. 「 [Visual Studio のツールボックスへの Windows PowerShell アクティビティの追加](./adding-windows-powershell-activities-to-the-visual-studio-toolbox.md)」の手順に従って、ワークフロープロジェクトを作成し、そのアクティビティ[を [ツール](/dotnet/api/Microsoft.PowerShell.Activities)ボックス] に[追加します](/dotnet/api/Microsoft.PowerShell.Management.Activities)。

2. 参照アセンブリとして、プロジェクトに対して、システムの管理、管理、および管理を行います。そのためには、「」を参照してください。

### <a name="adding-activities-to-the-workflow"></a>ワークフローへのアクティビティの追加

1. ワークフローに**Sequence**アクティビティを追加します。

2. 引数の型が `String[]`の `ComputerName` という名前の引数を作成します。 この引数は、確認して参加させるコンピューターの名前を表します。

3. 型の `DomainCred` という名前の引数を[作成します](/dotnet/api/System.Management.Automation.PSCredential)。 この引数は、ドメインにコンピューターを参加させる権限を持つドメインアカウントのドメイン資格情報を表します。

4. 型の `MachineCred` という名前の引数を[作成します](/dotnet/api/System.Management.Automation.PSCredential)。 この引数は、確認および参加するコンピューターの管理者の資格情報を表します。

5. **Sequence**アクティビティ内に**parallelforeach**アクティビティを追加します。 ループが `ComputerName` 配列の要素を反復処理するように、テキストボックスに `comp` を入力し `ComputerName` します。

6. **Parallelforeach**アクティビティの本文に**Sequence**アクティビティを追加します。 シーケンスの**DisplayName**プロパティを `JoinDomain`に設定します。

7. **GetWmiObject**アクティビティを**joindomain**シーケンスに追加します。

8. **GetWmiObject**アクティビティのプロパティを次のように編集します。

   |プロパティ|値|
   |--------------|-----------|
   |**クラス**|"Win32_ComputerSystem"|
   |**PSComputerName**|コンペティション|
   |**PSCredential**|各の Ecred|

9. **GetWmiObject**アクティビティの後に、 **Addcomputer**アクティビティを**joindomain**シーケンスに追加します。

10. 次のように、 **Addcomputer**アクティビティのプロパティを編集します。

    |プロパティ|値|
    |--------------|-----------|
    |**[ComputerName]**|コンペティション|
    |**DomainCredential**|DomainCred|

11. **Addcomputer**アクティビティの後に、 **RestartComputer**アクティビティを**joindomain**シーケンスに追加します。

12. **RestartComputer**アクティビティのプロパティを次のように編集します。

    |プロパティ|値|
    |--------------|-----------|
    |**[ComputerName]**|コンペティション|
    |**資格情報**|各の Ecred|
    |**の**|Microsoft. PowerShell. WaitForServiceTypes. PowerShell|
    |**Force**|True|
    |待機|True|
    |PSComputerName|{""}|

13. **RestartComputer**アクティビティの後に、 **GetWmiObject**アクティビティを**joindomain**シーケンスに追加します。 前の**GetWmiObject**アクティビティと同じになるように、プロパティを編集します。

    手順を完了すると、ワークフローデザインウィンドウは次のようになります。

    ワークフローデザイナーでの JoinDomain XAML の ![![ワークフローデザイナーでの Joindomain xaml](media/creating-a-workflow-with-windows-powershell-activities/joindomainworkflow.png "JoinDomainWorkflow")の](media/creating-a-workflow-with-windows-powershell-activities/joindomainworkflow.png)
    