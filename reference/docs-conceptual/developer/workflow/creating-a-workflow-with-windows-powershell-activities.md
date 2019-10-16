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
ms.openlocfilehash: 98cac43698b3f537ee318cd2570b2174631665a7
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72359631"
---
# <a name="creating-a-workflow-with-windows-powershell-activities"></a>Windows PowerShell アクティビティでワークフローを作成する

Windows PowerShell ワークフローを作成するには、Visual Studio のツールボックスからアクティビティを選択し、[ワークフローデザイナー] ウィンドウにドラッグします。 Visual Studio のツールボックスに Windows PowerShell アクティビティを追加する方法については、「 [Visual studio のツールボックスへの Windows Powershell アクティビティの追加](./adding-windows-powershell-activities-to-the-visual-studio-toolbox.md)」を参照してください。

次の手順では、ユーザー指定のコンピューターのグループのドメインステータスを確認し、まだ参加していない場合はドメインに参加させるワークフローを作成する方法について説明します。その後、状態をもう一度確認します。

### <a name="setting-up-the-project"></a>プロジェクトの設定

1. 「 [Visual Studio のツールボックスへの Windows PowerShell アクティビティの追加](./adding-windows-powershell-activities-to-the-visual-studio-toolbox.md)」の手順に従っ[て、ワークフロー](/dotnet/api/Microsoft.PowerShell.Activities)プロジェクトを作成し、それらの[アクティビティを追加します。](/dotnet/api/Microsoft.PowerShell.Management.Activities)アセンブリをツールボックスに転送します。

2. 参照アセンブリとして、プロジェクトに対して、システムの管理、管理、および管理を行います。そのためには、「」を参照してください。

### <a name="adding-activities-to-the-workflow"></a>ワークフローへのアクティビティの追加

1. ワークフローに**Sequence**アクティビティを追加します。

2. 引数の型が `String[]` の `ComputerName` という名前の引数を作成します。 この引数は、確認して参加させるコンピューターの名前を表します。

3. @No__t-0 という名前の引数を[作成します](/dotnet/api/System.Management.Automation.PSCredential)。 この引数は、ドメインにコンピューターを参加させる権限を持つドメインアカウントのドメイン資格情報を表します。

4. @No__t-0 という名前の引数を[作成します](/dotnet/api/System.Management.Automation.PSCredential)。 この引数は、確認および参加するコンピューターの管理者の資格情報を表します。

5. **Sequence**アクティビティ内に**parallelforeach**アクティビティを追加します。 テキストボックスに `comp` と `ComputerName` を入力して、ループが `ComputerName` 配列の要素を反復処理するようにします。

6. **Parallelforeach**アクティビティの本文に**Sequence**アクティビティを追加します。 シーケンスの**DisplayName**プロパティを `JoinDomain` に設定します。

7. **GetWmiObject**アクティビティを**joindomain**シーケンスに追加します。

8. **GetWmiObject**アクティビティのプロパティを次のように編集します。

   |プロパティ|値|
   |--------------|-----------|
   |**講義**|"Win32_ComputerSystem"|
   |**PSComputerName**|コンペティション|
   |**PSCredential**|各の Ecred|

9. **GetWmiObject**アクティビティの後に、 **Addcomputer**アクティビティを**joindomain**シーケンスに追加します。

10. 次のように、 **Addcomputer**アクティビティのプロパティを編集します。

    |プロパティ|値|
    |--------------|-----------|
    |**コンピューター名**|コンペティション|
    |**DomainCredential**|DomainCred|

11. **Addcomputer**アクティビティの後に、 **RestartComputer**アクティビティを**joindomain**シーケンスに追加します。

12. **RestartComputer**アクティビティのプロパティを次のように編集します。

    |プロパティ|値|
    |--------------|-----------|
    |**コンピューター名**|コンペティション|
    |**証明**|各の Ecred|
    |**の**|Microsoft. PowerShell. WaitForServiceTypes. PowerShell|
    |**必ず**|True|
    |Wait|True|
    |PSComputerName|{""}|

13. **RestartComputer**アクティビティの後に、 **GetWmiObject**アクティビティを**joindomain**シーケンスに追加します。 前の**GetWmiObject**アクティビティと同じになるように、プロパティを編集します。

    手順を完了すると、ワークフローデザインウィンドウは次のようになります。

    ワークフローデザイナーでの @no__t 0JoinDomain XAML ワークフローデザイナーでの no__t![joindomain](../media/joindomainworkflow.png "workflow")