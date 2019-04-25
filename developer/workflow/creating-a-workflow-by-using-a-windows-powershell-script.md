---
title: Windows PowerShell スクリプトを使用してワークフローを作成する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 70532e7e-9cac-43c3-9687-e77011ecc878
caps.latest.revision: 4
ms.openlocfilehash: 5eb2186cbceee21f8b4a8c88b812e9c71f15e0af
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62080375"
---
# <a name="creating-a-workflow-by-using-a-windows-powershell-script"></a>Windows PowerShell スクリプトを利用してワークフローを作成する

Windows PowerShell スクリプトを記述して、ワークフローを作成することができます。 ワークフローを作成するには、ワークフロー キーワードの後に、スクリプトの本体の前にワークフローの名前を使用します。 たとえば、次のように入力します。

```powershell

workflow Invoke-HelloWorld {"Hello World from workflow"}
```

ワークフローは、他の Windows PowerShell コマンドのと同じ方法で検索します。

## <a name="implementing-parallel-and-sequence"></a>並列シーケンスを実装します。

[Windows Workflow Foundation](https://msdn.microsoft.com/en-us/library/ms735967.aspx)並列アクティビティの実行をサポートしています。 Windows PowerShell スクリプトでこの機能を実装するために使用して、`parallel`スクリプト ブロックの前にキーワード。 使用することも、`foreach -parallel`構造を使用して並列でオブジェクトのコレクションを反復処理します。 アクティビティのグループを並列ブロック内で順番に実行するには、スクリプト ブロックでそのグループのアクティビティを囲むし、シーケンス キーワードを使用して、ブロックの前にします。

## <a name="joining-computers-to-a-domain"></a>コンピューターをドメインに参加させる

次のスクリプトは、ユーザーが指定したコンピューターのグループのドメインの状態を確認、状態をもう一度確認し、既に参加していない場合に、ドメインに参加するワークフローを作成します。 これは、スクリプトのバージョンで説明されている XAML ワークフローの[Windows PowerShell のアクティビティとワークフローを作成する](./creating-a-workflow-with-windows-powershell-activities.md)します。

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