---
title: 資格情報の属性の宣言 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 96a5dcad-faed-44d8-8c80-321f10499710
caps.latest.revision: 6
ms.openlocfilehash: 49a62ccb09f06f77862d4737199e58293e7fbe0a
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58059254"
---
# <a name="credential-attribute-declaration"></a>資格情報属性の宣言

資格情報の属性は、型の資格情報パラメーターで使用できる省略可能な属性[System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential)をパラメーターに文字列が引数として渡すこともできます。 Windows PowerShell がへの文字列入力を変換パラメーター宣言には、この属性を追加するときに、 [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential)オブジェクト。 たとえば、 [Get-credential](/powershell/module/Microsoft.PowerShell.Security/Get-Credential)コマンドレットでは、この属性を使用して、Windows PowerShell の生成、 [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential)コマンドレットによって返されるオブジェクト。

## <a name="syntax"></a>構文

```csharp
[Credential]
```

## <a name="remarks"></a>コメント

- 型のパラメーターでこの属性を使用する通常[System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential)をパラメーターに文字列が引数として渡すこともできます。 ときに、 [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential)オブジェクトがパラメーターに渡されると、Windows PowerShell は何も行いません。

- 作成するときに、 [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential)オブジェクト、Windows PowerShell は、現在のホストを使用して、ユーザーに適切な指示を表示します。 たとえば、既定のホストが表示されますユーザー名とパスワードを入力するプロンプトこの属性を使用する場合。 ただし、カスタム ホストを使用している場合は、さまざまなプロンプトを定義するし、プロンプトが表示されます。

- この属性は、パラメーターの属性で使用されます。 その属性の詳細については、[パラメーター属性宣言](./parameter-attribute-declaration.md)を参照してください。

- 資格情報の属性を定義した、 [System.Management.Automation.Credentialattribute](/dotnet/api/System.Management.Automation.CredentialAttribute)クラス。

## <a name="see-also"></a>参照

[パラメーターのエイリアス](./parameter-aliases.md)

[パラメーター属性の宣言](./parameter-attribute-declaration.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
