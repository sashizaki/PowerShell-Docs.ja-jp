---
title: 確認を求めるユーザー |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6f337498-c534-40ed-968a-09d4d9ca3849
caps.latest.revision: 8
ms.openlocfilehash: ed9ff9fc1668a89e1ac0ceac8f0800a15b349226
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369251"
---
# <a name="users-requesting-confirmation"></a>ユーザーの確認要求

コマンドレットの属性宣言の `SupportsShouldProcess` パラメーターに値 `true` を指定すると、ユーザーはコマンドプロンプトで `Confirm` パラメーターを指定できます。

既定の環境では、ユーザーは `Confirm` パラメーターまたは `"-Confirm:$true` を指定できます。これにより、[システム](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)のメソッドが呼び出されたときに確認が要求されます。 これは、システムの管理をバイパス[します。](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)影響の大きい操作の場合でも、確認要求を処理します。

@No__t-0 が指定されていない場合は、@no__t 2 つのユーザー設定変数が、コマンドレットまたはプロバイダーの `ConfirmImpact` の設定以上であるかどうかの確認を求めるメッセージ[が呼び出されます。](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) @No__t-0 の既定の設定は High です。 そのため、既定の環境では、影響の大きいアクション要求の確認を指定するコマンドレットとプロバイダーのみが対象となります。

@No__t-0 が false の場合、または `"-Confirm:$false` を指定した場合[は、ユーザー](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)からの確認が要求され、@no__t 3 つのシェル変数は無視されます。

## <a name="remarks"></a>コメント

- @No__t-1 ではなく `SupportsShouldProcess` を指定するコマンドレットとプロバイダーでは、これらのアクションは "中程度の影響" アクションとして処理され、既定ではプロンプトは表示されません。 影響レベルは、@no__t のユーザー設定変数の既定の設定よりも小さくなっています。

- ユーザーが `Verbose` パラメーターを指定した場合、確認メッセージが表示されなくても操作が通知されます。

## <a name="see-also"></a>参照

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
