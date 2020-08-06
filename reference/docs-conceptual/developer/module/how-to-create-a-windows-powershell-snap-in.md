---
title: Windows PowerShell スナップインを作成する方法 |Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- snap-ins [PowerShell SDK], examples
ms.openlocfilehash: 4150ba582544d1daa4a898f0ff20b169c24a0ee0
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787327"
---
# <a name="how-to-create-a-windows-powershell-snap-in"></a>Windows PowerShell スナップインを作成する方法

Windows PowerShell スナップインは、一連のコマンドレットと別の Windows PowerShell プロバイダーをシェルに登録するためのメカニズムを提供します。これにより、シェルの機能が拡張されます。 Windows PowerShell スナップインでは、すべてのコマンドレットとプロバイダーを1つのアセンブリに登録したり、特定のコマンドレットとプロバイダーの一覧を登録したりできます。

スナップインアセンブリは、他のオペレーティングシステムと同様に、保護されたディレクトリにインストールする必要があります。 そうしないと、悪意のあるユーザーがアセンブリを安全でないコードに置き換えることができます。

## <a name="windows-powershell-snap-in-classes"></a>Windows PowerShell スナップインクラス

すべての Windows PowerShell スナップインクラスは、 [add-pssnapin](/dotnet/api/System.Management.Automation.PSSnapIn)クラスまたは[Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn)クラスから派生しています。

## <a name="examples"></a>例

[Windows PowerShell スナップインの記述](./writing-a-windows-powershell-snap-in.md): この例では、アセンブリ内のすべてのコマンドレットとプロバイダーを登録するために使用されるスナップインを作成する方法を示します。

[カスタム Windows PowerShell スナップ](./writing-a-custom-windows-powershell-snap-in.md)インの作成: この例では、単一のアセンブリに存在する可能性がある特定のコマンドレットとプロバイダーのセットを登録するために使用されるカスタムスナップインを作成する方法を示します。

## <a name="see-also"></a>参照

[Add-pssnapin (システム管理)](/dotnet/api/System.Management.Automation.PSSnapIn)

[Custompssnapin (システム管理)](/dotnet/api/System.Management.Automation.CustomPSSnapIn)

[コマンドレットを登録する](./registering-cmdlets.md)

[Windows PowerShell Shell SDK](../windows-powershell-reference.md)
