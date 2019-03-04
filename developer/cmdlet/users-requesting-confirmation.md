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
ms.openlocfilehash: e4abbb14b31406b845d9b6af6b6372338fb0d926
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856238"
---
# <a name="users-requesting-confirmation"></a>ユーザーの確認要求

値を指定すると`true`の`SupportsShouldProcess`コマンドレットの属性の宣言のパラメーターは、ユーザーを指定できます、`Confirm`コマンド プロンプト パラメーター。

既定の環境でユーザーを指定できます、`Confirm`パラメーターまたは`"-Confirm:$true`するので、確認が要求されるときに、 [System.Management.Automation.Cmdlet.Shouldprocess*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)メソッドが呼び出されます。 これをバイパスする[System.Management.Automation.Cmdlet.Shouldprocess*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)影響の大きい操作の場合でも、確認要求。

場合`Confirm`が指定されていない、 [System.Management.Automation.Cmdlet.Shouldprocess*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)呼び出し要求の確認の場合、`$ConfirmPreference`ユーザー設定変数が同じか、またはより大きい、`ConfirmImpact`の設定、コマンドレットまたはプロバイダー。 既定値の`$ConfirmPreference`高です。 そのため、既定の環境で唯一のコマンドレットとプロバイダー、影響の大きい操作を指定する要求の確認。

場合`Confirm`が false の場合、または`"-Confirm:$false`が指定されている、 [System.Management.Automation.Cmdlet.Shouldprocess*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)呼び出しが、ユーザーに確認を要求、`$ConfirmPreference`シェル変数は無視されます。

## <a name="remarks"></a>コメント

- 指定されているコマンドレットとプロバイダーの`SupportsShouldProcess`、なく`ConfirmImpact`「中程度の影響」アクションでは、これらのアクションの処理、および、既定では確認できません。 その影響のレベルが既定の設定より小さい、`$ConfirmPreference`ユーザー設定変数。

- ユーザーが指定されている場合、`Verbose`パラメーター、確認を求められましていない場合でも、操作が通知されます。

## <a name="see-also"></a>参照

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
