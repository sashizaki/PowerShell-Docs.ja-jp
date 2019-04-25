---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: プリンターの操作
ms.assetid: 4f29ead3-f83b-4706-ac3e-f2154ff38dc5
ms.openlocfilehash: 77ebb26369b6a40e9c8c7bbbc52347d614cbf083
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62058541"
---
# <a name="working-with-printers"></a><span data-ttu-id="4c50c-103">プリンターの操作</span><span class="sxs-lookup"><span data-stu-id="4c50c-103">Working with Printers</span></span>

<span data-ttu-id="4c50c-104">Windows PowerShell を使用してプリンターを管理するには、WMI を使用する方法と WSH から WScript.Network COM オブジェクトを使用する方法があります。</span><span class="sxs-lookup"><span data-stu-id="4c50c-104">You can use Windows PowerShell to manage printers by using WMI and the WScript.Network COM object from WSH.</span></span> <span data-ttu-id="4c50c-105">ここでは、両方のツールを組み合わせて使用して、特定のタスクの実行方法を紹介します。</span><span class="sxs-lookup"><span data-stu-id="4c50c-105">We will use a mix of both tools to demonstrate specific tasks.</span></span>

## <a name="listing-printer-connections"></a><span data-ttu-id="4c50c-106">プリンター接続の一覧表示</span><span class="sxs-lookup"><span data-stu-id="4c50c-106">Listing Printer Connections</span></span>

<span data-ttu-id="4c50c-107">コンピューターにインストールされているプリンターを一覧表示する最も簡単な方法は、WMI の **Win32_Printer** クラスを使用することです。</span><span class="sxs-lookup"><span data-stu-id="4c50c-107">The simplest way to list the printers installed on a computer is to use the WMI **Win32_Printer** class:</span></span>

```powershell
Get-WmiObject -Class Win32_Printer -ComputerName
```

<span data-ttu-id="4c50c-108">**WScript.Network** という COM オブジェクト (通常、WSH スクリプトで使用されます) を使用してプリンターを一覧表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="4c50c-108">You can also list the printers by using the **WScript.Network** COM object that is typically used in WSH scripts:</span></span>

```powershell
(New-Object -ComObject WScript.Network).EnumPrinterConnections()
```

<span data-ttu-id="4c50c-109">このコマンドは、ポート名とプリンター デバイス名の単純な文字列コレクションを返し、識別に役立つラベルがないため、分かりにくい場合があります。</span><span class="sxs-lookup"><span data-stu-id="4c50c-109">Because this command returns a simple string collection of port names and printer device names without any distinguishing labels, it is not easy to interpret.</span></span>

## <a name="adding-a-network-printer"></a><span data-ttu-id="4c50c-110">ネットワーク プリンターの追加</span><span class="sxs-lookup"><span data-stu-id="4c50c-110">Adding a Network Printer</span></span>

<span data-ttu-id="4c50c-111">新しいネットワーク プリンターを追加するには、**WScript.Network** を使用します。</span><span class="sxs-lookup"><span data-stu-id="4c50c-111">To add a new network printer, use **WScript.Network**:</span></span>

```powershell
(New-Object -ComObject WScript.Network).AddWindowsPrinterConnection("\\Printserver01\Xerox5")
```

## <a name="setting-a-default-printer"></a><span data-ttu-id="4c50c-112">通常使うプリンターの設定</span><span class="sxs-lookup"><span data-stu-id="4c50c-112">Setting a Default Printer</span></span>

<span data-ttu-id="4c50c-113">通常使うプリンターを WMI を使用して設定するには、**Win32_Printer** コレクションでプリンターを検索し、**SetDefaultPrinter** メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4c50c-113">To use WMI to set the default printer, find the printer in the **Win32_Printer** collection and then invoke the **SetDefaultPrinter** method:</span></span>

```powershell
(Get-WmiObject -ComputerName . -Class Win32_Printer -Filter "Name='HP LaserJet 5Si'").SetDefaultPrinter()
```

<span data-ttu-id="4c50c-114">**WScript.Network** の方が多少簡単に使用できます。これは、プリンター名のみを引数として取る **SetDefaultPrinter** メソッドを備えているためです。</span><span class="sxs-lookup"><span data-stu-id="4c50c-114">**WScript.Network** is a little simpler to use, because it has a **SetDefaultPrinter** method that takes only the printer name as an argument:</span></span>

```powershell
(New-Object -ComObject WScript.Network).SetDefaultPrinter('HP LaserJet 5Si')
```

## <a name="removing-a-printer-connection"></a><span data-ttu-id="4c50c-115">プリンター接続の削除</span><span class="sxs-lookup"><span data-stu-id="4c50c-115">Removing a Printer Connection</span></span>

<span data-ttu-id="4c50c-116">プリンター接続を削除するには、**WScript.Network RemovePrinterConnection** メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="4c50c-116">To remove a printer connection, use the **WScript.Network RemovePrinterConnection** method:</span></span>

```powershell
(New-Object -ComObject WScript.Network).RemovePrinterConnection("\\Printserver01\Xerox5")
```