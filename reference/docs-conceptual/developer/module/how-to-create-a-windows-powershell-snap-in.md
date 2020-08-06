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
# <a name="how-to-create-a-windows-powershell-snap-in"></a><span data-ttu-id="bad02-102">Windows PowerShell スナップインを作成する方法</span><span class="sxs-lookup"><span data-stu-id="bad02-102">How to Create a Windows PowerShell Snap-in</span></span>

<span data-ttu-id="bad02-103">Windows PowerShell スナップインは、一連のコマンドレットと別の Windows PowerShell プロバイダーをシェルに登録するためのメカニズムを提供します。これにより、シェルの機能が拡張されます。</span><span class="sxs-lookup"><span data-stu-id="bad02-103">A Windows PowerShell snap-in provides a mechanism for registering sets of cmdlets and another Windows PowerShell provider with the shell, thus extending the functionality of the shell.</span></span> <span data-ttu-id="bad02-104">Windows PowerShell スナップインでは、すべてのコマンドレットとプロバイダーを1つのアセンブリに登録したり、特定のコマンドレットとプロバイダーの一覧を登録したりできます。</span><span class="sxs-lookup"><span data-stu-id="bad02-104">A Windows PowerShell snap-in can register all the cmdlets and providers in a single assembly, or it can register a specific list of cmdlets and providers.</span></span>

<span data-ttu-id="bad02-105">スナップインアセンブリは、他のオペレーティングシステムと同様に、保護されたディレクトリにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bad02-105">Snap-in assemblies should be installed in a protected directory, just as they would be with other operating systems.</span></span> <span data-ttu-id="bad02-106">そうしないと、悪意のあるユーザーがアセンブリを安全でないコードに置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="bad02-106">Otherwise, malicious users can replace an assembly with unsafe code.</span></span>

## <a name="windows-powershell-snap-in-classes"></a><span data-ttu-id="bad02-107">Windows PowerShell スナップインクラス</span><span class="sxs-lookup"><span data-stu-id="bad02-107">Windows PowerShell Snap-in Classes</span></span>

<span data-ttu-id="bad02-108">すべての Windows PowerShell スナップインクラスは、 [add-pssnapin](/dotnet/api/System.Management.Automation.PSSnapIn)クラスまたは[Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn)クラスから派生しています。</span><span class="sxs-lookup"><span data-stu-id="bad02-108">All Windows PowerShell snap-in classes derive from the [System.Management.Automation.PSSnapIn](/dotnet/api/System.Management.Automation.PSSnapIn) or [System.Management.Automation.Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn) classes.</span></span>

## <a name="examples"></a><span data-ttu-id="bad02-109">例</span><span class="sxs-lookup"><span data-stu-id="bad02-109">Examples</span></span>

<span data-ttu-id="bad02-110">[Windows PowerShell スナップインの記述](./writing-a-windows-powershell-snap-in.md): この例では、アセンブリ内のすべてのコマンドレットとプロバイダーを登録するために使用されるスナップインを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bad02-110">[Writing a Windows PowerShell Snap-in](./writing-a-windows-powershell-snap-in.md): This example shows how to create a snap-in that is used to register all the cmdlets and providers in an assembly.</span></span>

<span data-ttu-id="bad02-111">[カスタム Windows PowerShell スナップ](./writing-a-custom-windows-powershell-snap-in.md)インの作成: この例では、単一のアセンブリに存在する可能性がある特定のコマンドレットとプロバイダーのセットを登録するために使用されるカスタムスナップインを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bad02-111">[Writing a Custom Windows PowerShell Snap-in](./writing-a-custom-windows-powershell-snap-in.md): This example shows how to create a custom snap-in that is used to register a specific set of cmdlets and providers that might or might not exist in a single assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="bad02-112">参照</span><span class="sxs-lookup"><span data-stu-id="bad02-112">See Also</span></span>

[<span data-ttu-id="bad02-113">Add-pssnapin (システム管理)</span><span class="sxs-lookup"><span data-stu-id="bad02-113">System.Management.Automation.PSSnapIn</span></span>](/dotnet/api/System.Management.Automation.PSSnapIn)

[<span data-ttu-id="bad02-114">Custompssnapin (システム管理)</span><span class="sxs-lookup"><span data-stu-id="bad02-114">System.Management.Automation.Custompssnapin</span></span>](/dotnet/api/System.Management.Automation.CustomPSSnapIn)

[<span data-ttu-id="bad02-115">コマンドレットを登録する</span><span class="sxs-lookup"><span data-stu-id="bad02-115">Registering Cmdlets</span></span>](./registering-cmdlets.md)

[<span data-ttu-id="bad02-116">Windows PowerShell Shell SDK</span><span class="sxs-lookup"><span data-stu-id="bad02-116">Windows PowerShell Shell SDK</span></span>](../windows-powershell-reference.md)
