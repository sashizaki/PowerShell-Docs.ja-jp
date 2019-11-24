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

コマンドレットの属性宣言の `SupportsShouldProcess` パラメーターに `true` の値を指定すると、ユーザーはコマンドプロンプトで `Confirm` パラメーターを指定できます。

既定の環境では、ユーザーは `Confirm` パラメーターまたは `"-Confirm:$true` を指定できます。これにより、[システム](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)のメソッドが呼び出されたときに確認が要求されます。 これは、システムの管理をバイパス[します。](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)影響の大きい操作の場合でも、確認要求を処理します。

`Confirm` が指定されていない場合は、`$ConfirmPreference` ユーザー設定変数がコマンドレットまたはプロバイダーの `ConfirmImpact` 設定以上であるかどうかを確認するために、[システム](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)の呼び出し要求が呼び出されます。 `$ConfirmPreference` の既定の設定は [高] です。 そのため、既定の環境では、影響の大きいアクション要求の確認を指定するコマンドレットとプロバイダーのみが対象となります。

`Confirm` が false の場合、または `"-Confirm:$false` が指定されている場合は、ユーザーからの確認要求[が呼び出され](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)、`$ConfirmPreference` シェル変数は無視されます。

## <a name="remarks"></a>コメント

- `ConfirmImpact`ではなく `SupportsShouldProcess`を指定するコマンドレットとプロバイダーでは、これらのアクションは "中程度の影響" アクションとして処理され、既定ではプロンプトは表示されません。 影響レベルは、`$ConfirmPreference` ユーザー設定変数の既定の設定よりも小さくなります。

- ユーザーが `Verbose` パラメーターを指定すると、確認メッセージが表示されない場合でも、操作が通知されます。

## <a name="see-also"></a>関連項目

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
