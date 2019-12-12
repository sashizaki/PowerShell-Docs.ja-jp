---
title: パラメーターセットを宣言する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 46905eb9-64d7-4c55-9c2a-7bc7bf04e14b
caps.latest.revision: 10
ms.openlocfilehash: 6c2e5891a8e3f24969c12a2e57dc5ae8caa68e41
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365611"
---
# <a name="how-to-declare-parameter-sets"></a>パラメーター セットを宣言する方法

この例では、コマンドレットのパラメーターを宣言するときに2つのパラメーターセットを定義する方法を示します。 各パラメーターセットには、一意のパラメーターと、両方のパラメーターセットで使用される共有パラメーターの両方があります。 既定のパラメーターセットの指定方法など、パラメーターセットの詳細については、「[コマンドレットパラメーターセット](./cmdlet-parameter-sets.md)」を参照してください。

> [!IMPORTANT]
> 可能な限り、パラメーターセットの一意のパラメーターを必須パラメーターとして定義します。 ただし、パラメーターを指定せずにコマンドレットを実行する場合は、unique パラメーターを省略可能なパラメーターにすることができます。 たとえば、`Get-Command` コマンドレットの unique パラメーターは省略可能です。

## <a name="how-to-define-two-parameter-sets"></a>2つのパラメーターセットを定義する方法

1. 最初のパラメーターセットの一意のパラメーターのパラメーター属性に `ParameterSet` キーワードを追加します。

   ```csharp
   [Parameter(Position = 0, Mandatory = true,
              ParameterSetName = "Test01")]
   public string UserName
   {
     get { return userName; }
     set { userName = value; }
   }
   private string userName;
   ```

2. 2番目のパラメーターセットの unique パラメーターの Parameter 属性に `ParameterSet` キーワードを追加します。

   ```csharp
   [Parameter(Position = 0, Mandatory = true,
              ParameterSetName = "Test02")]
   public string ComputerName
   {
     get { return computerName; }
     set { computerName = value; }
   }
   private string computerName;
   ```

3. 両方のパラメーターセットに属するパラメーターについては、各パラメーターセットにパラメーター属性を追加し、各セットに `ParameterSet` キーワードを追加します。 各パラメーター属性では、パラメーターの定義方法を指定できます。 パラメーターは、1つのセットでは省略可能であり、別のセットでは必須です。

   ```csharp
   [Parameter(Mandatory= true, ParameterSetName = "Test01")]
   [Parameter(ParameterSetName = "Test02")]
   public string SharedParam
   {
       get { return sharedParam; }
       set { sharedParam = value; }
   }
   private string sharedParam;
   ```

## <a name="see-also"></a>参照

[コマンドレットのパラメーターセット](./cmdlet-parameter-sets.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
