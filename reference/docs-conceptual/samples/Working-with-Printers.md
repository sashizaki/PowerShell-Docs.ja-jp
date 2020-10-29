---
ms.date: 12/23/2019
keywords: powershell,コマンドレット
title: プリンターの操作
description: この記事では、WMI オブジェクトと COM インターフェイスを使用して Windows でプリンターを管理する方法を示します。
ms.openlocfilehash: 2606753783043eeae8e9d461e56f0901149cb8e3
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "92501084"
---
# <a name="working-with-printers-in-windows"></a><span data-ttu-id="e6fef-104">Windows でのプリンターの操作</span><span class="sxs-lookup"><span data-stu-id="e6fef-104">Working with Printers in Windows</span></span>

<span data-ttu-id="e6fef-105">PowerShell を使用してプリンターを管理するには、WMI を使用する方法と WSH から **WScript.Network** COM オブジェクトを使用する方法があります。</span><span class="sxs-lookup"><span data-stu-id="e6fef-105">You can use PowerShell to manage printers by using WMI and the **WScript.Network** COM object from WSH.</span></span> <span data-ttu-id="e6fef-106">ここでは、両方のツールを組み合わせて使用して、特定のタスクの実行方法を紹介します。</span><span class="sxs-lookup"><span data-stu-id="e6fef-106">We will use a mix of both tools to demonstrate specific tasks.</span></span>

## <a name="listing-printer-connections"></a><span data-ttu-id="e6fef-107">プリンター接続の一覧表示</span><span class="sxs-lookup"><span data-stu-id="e6fef-107">Listing Printer Connections</span></span>

<span data-ttu-id="e6fef-108">コンピューターにインストールされているプリンターを一覧表示する最も簡単な方法は、WMI の **Win32_Printer** クラスを使用することです。</span><span class="sxs-lookup"><span data-stu-id="e6fef-108">The simplest way to list the printers installed on a computer is to use the WMI **Win32_Printer** class:</span></span>

```powershell
Get-CimInstance -Class Win32_Printer
```

<span data-ttu-id="e6fef-109">**WScript.Network** という COM オブジェクト (通常、WSH スクリプトで使用されます) を使用してプリンターを一覧表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="e6fef-109">You can also list the printers by using the **WScript.Network** COM object that is typically used in WSH scripts:</span></span>

```powershell
(New-Object -ComObject WScript.Network).EnumPrinterConnections()
```

<span data-ttu-id="e6fef-110">このコマンドは、ポート名とプリンター デバイス名の単純な文字列コレクションを返し、識別に役立つラベルがないため、分かりにくい場合があります。</span><span class="sxs-lookup"><span data-stu-id="e6fef-110">Because this command returns a simple string collection of port names and printer device names without any distinguishing labels, it is not easy to interpret.</span></span>

## <a name="adding-a-network-printer"></a><span data-ttu-id="e6fef-111">ネットワーク プリンターの追加</span><span class="sxs-lookup"><span data-stu-id="e6fef-111">Adding a Network Printer</span></span>

<span data-ttu-id="e6fef-112">新しいネットワーク プリンターを追加するには、 **WScript.Network** を使用します。</span><span class="sxs-lookup"><span data-stu-id="e6fef-112">To add a new network printer, use **WScript.Network** :</span></span>

```powershell
(New-Object -ComObject WScript.Network).AddWindowsPrinterConnection("\\Printserver01\Xerox5")
```

## <a name="setting-a-default-printer"></a><span data-ttu-id="e6fef-113">通常使うプリンターの設定</span><span class="sxs-lookup"><span data-stu-id="e6fef-113">Setting a Default Printer</span></span>

<span data-ttu-id="e6fef-114">通常使うプリンターを WMI を使用して設定するには、 **Win32_Printer** コレクションでプリンターを検索し、 **SetDefaultPrinter** メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e6fef-114">To use WMI to set the default printer, find the printer in the **Win32_Printer** collection and then invoke the **SetDefaultPrinter** method:</span></span>

```powershell
$printer = Get-CimInstance -Class Win32_Printer -Filter "Name='HP LaserJet 5Si'"
Invoke-CimMethod -InputObject $printer -MethodName SetDefaultPrinter
```

<span data-ttu-id="e6fef-115">**WScript.Network** の方が多少簡単に使用できます。これは、プリンター名のみを引数として取る **SetDefaultPrinter** メソッドを備えているためです。</span><span class="sxs-lookup"><span data-stu-id="e6fef-115">**WScript.Network** is a little simpler to use, because it has a **SetDefaultPrinter** method that takes only the printer name as an argument:</span></span>

```powershell
(New-Object -ComObject WScript.Network).SetDefaultPrinter('HP LaserJet 5Si')
```

## <a name="removing-a-printer-connection"></a><span data-ttu-id="e6fef-116">プリンター接続の削除</span><span class="sxs-lookup"><span data-stu-id="e6fef-116">Removing a Printer Connection</span></span>

<span data-ttu-id="e6fef-117">プリンター接続を削除するには、 **WScript.Network RemovePrinterConnection** メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="e6fef-117">To remove a printer connection, use the **WScript.Network RemovePrinterConnection** method:</span></span>

```powershell
(New-Object -ComObject WScript.Network).RemovePrinterConnection("\\Printserver01\Xerox5")
```
