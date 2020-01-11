---
title: Windows PowerShell スクリプトを使用したワークフローの作成 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 70532e7e-9cac-43c3-9687-e77011ecc878
caps.latest.revision: 4
ms.openlocfilehash: 5720200ce32f114cd4965d961b9e2804bd154b2e
ms.sourcegitcommit: d97b200e7a49315ce6608cd619e3e2fd99193edd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/10/2020
ms.locfileid: "75870848"
---
# <a name="creating-a-workflow-by-using-a-windows-powershell-script"></a>Windows PowerShell スクリプトを利用してワークフローを作成する

Windows PowerShell スクリプトを記述することで、ワークフローを作成できます。 ワークフローを作成するには、スクリプトの本文の前に workflow キーワードを使用し、その後にワークフローの名前を指定します。 たとえば次のようになります。

```powershell

workflow Invoke-HelloWorld {"Hello World from workflow"}
```

ワークフローは、他の Windows PowerShell コマンドと同じ方法で検索できます。

## <a name="implementing-parallel-and-sequence"></a>並列とシーケンスの実装

[Windows Workflow Foundation](/previous-versions/dotnet/netframework-3.5/ms735967(v=vs.90))は、アクティビティの並列実行をサポートします。 Windows PowerShell スクリプトでこの機能を実装するには、スクリプトブロックの前に `parallel` キーワードを使用します。 また、`foreach -parallel` の構築を使用して、オブジェクトのコレクションを並列に反復処理することもできます。 並列ブロック内で連続した順序でアクティビティのグループを実行するには、そのアクティビティのグループをスクリプトブロックで囲み、ブロックの前に sequence キーワードを付けます。

## <a name="joining-computers-to-a-domain"></a>ドメインへのコンピューターの参加

次のスクリプトは、ユーザー指定のコンピューターのグループのドメインの状態を確認し、まだ参加していない場合はドメインに参加させるワークフローを作成してから、状態を再度確認します。
これは、「 [Windows PowerShell アクティビティを使用したワークフローの作成](./creating-a-workflow-with-windows-powershell-activities.md)」で説明されている XAML ワークフローのスクリプトバージョンです。

```powershell
workflow Join-Domain
{
    param([string[]] $ComputerName, [PSCredential] $DomainCred, [PsCredential] $MachineCred)

    foreach -parallel($Computer in $ComputerName)
    {
        sequence {
        Get-WmiObject -PSComputerName $Computer -PSCredential $MachineCred
        Add-Computer -PSComputerName $Computer -PSCredential $DomainCred
        Restart-Computer -ComputerName $Computer -Credential $MachineCred -For PowerShell -Force -Wait -PSComputerName ""
        Get-WmiObject -PSComputerName $Computer -PSCredential $MachineCred
        }
    }
}
```