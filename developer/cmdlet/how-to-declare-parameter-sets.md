---
title: パラメーター セットを宣言する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 46905eb9-64d7-4c55-9c2a-7bc7bf04e14b
caps.latest.revision: 10
ms.openlocfilehash: 6c2e5891a8e3f24969c12a2e57dc5ae8caa68e41
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859698"
---
# <a name="how-to-declare-parameter-sets"></a>パラメーター セットを宣言する方法

この例では、コマンドレットのパラメーターを宣言するときに、2 つのパラメーター セットを定義する方法を示します。 各パラメーター セットは、一意のパラメーターと両方のパラメーター セットによって使用される共有パラメーターの両方を持っています。 既定のパラメーター セットを指定する方法などのパラメーター セットの詳細については、次を参照してください。[コマンドレット パラメーター設定](./cmdlet-parameter-sets.md)します。

> [!IMPORTANT]
> 可能であれば、パラメーターとして必要なパラメーター セットの一意のパラメーターを定義します。 ただし、コマンドレット、パラメーターを指定せずに実行する場合は、一意のパラメーターは、オプションのパラメーターをできます。 一意のパラメーターなど、`Get-Command`コマンドレットは省略可能です。

## <a name="how-to-define-two-parameter-sets"></a>2 つのパラメーター セットを定義する方法

1. 追加、`ParameterSet`最初のパラメーター セットの一意のパラメーターのパラメーター属性にキーワード。

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

2. 追加、`ParameterSet`キーワードを 2 番目のパラメーター セットの一意のパラメーターのパラメーター属性。

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

3. 両方のパラメーター セットに属するパラメーターには、各パラメーター セットのパラメーター属性を追加し、追加、`ParameterSet`キーワードごとにします。 各パラメーター属性では、そのパラメーターを定義する方法を指定できます。 1 つのセットで省略可能で、別の必須パラメーターができます。

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

[コマンドレットのパラメーター セット](./cmdlet-parameter-sets.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
