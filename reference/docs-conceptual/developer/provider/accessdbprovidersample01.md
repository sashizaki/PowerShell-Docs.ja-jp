---
title: AccessDBProviderSample01 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 50ec218e8d0fe6b2be5c8ac00956f72c6723f84a
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786919"
---
# <a name="accessdbprovidersample01"></a>AccessDBProviderSample01

このサンプルでは、system.servicemodel[プロバイダー](/dotnet/api/System.Management.Automation.Provider.CmdletProvider)クラスから直接派生するプロバイダークラスを宣言する方法を示します。 すべてを網羅しておく目的でここに含めておきます。

## <a name="demonstrates"></a>対象

> [!IMPORTANT]
> プロバイダークラスは、ほとんどの場合、次のいずれかのクラスから派生し、他のプロバイダーインターフェイスを実装する可能性があります。
>
> - ...........[プロバイダー](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)クラス。 「 [AccessDBProviderSample03](./accessdbprovidersample03.md)」を参照してください。
> - [Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)クラスを提供します。 「 [AccessDBProviderSample04](./accessdbprovidersample04.md)」を参照してください。
> - ...... [.。](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) 「 [AccessDBProviderSample05](./accessdbprovidersample05.md)」を参照してください。
>
> プロバイダーの機能に基づいて派生するプロバイダークラスを選択する方法の詳細については、「 [Windows PowerShell プロバイダーの設計](./provider-types.md)」を参照してください。

このサンプルでは、次の方法を示します。

- 属性を宣言 `CmdletProvider` しています。

- [システム](/dotnet/api/System.Management.Automation.Provider.CmdletProvider)の.......................................

## <a name="example"></a>例

このサンプルでは、プロバイダークラスを定義する方法と、属性を宣言する方法を示し `CmdletProvider` ます。

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample01/AccessDBProviderSample01.cs" range="11-30":::

## <a name="see-also"></a>参照

[システムの................](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[Containercmdletprovider (システム管理)](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[システムの管理...。](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[Windows PowerShell プロバイダーを設計する](./provider-types.md)
