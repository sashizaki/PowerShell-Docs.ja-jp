---
title: Windows PowerShell のフォーマットファイル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5d4c8f84-ebd2-4405-bb10-cfc5400d4ad6
caps.latest.revision: 6
ms.openlocfilehash: 3ec127d5ff60754de5d7f1ac73f2965524228b9c
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365011"
---
# <a name="windows-powershell-formatting-files"></a>Windows PowerShell 書式設定ファイル

Windows PowerShell には、インストールディレクトリ (`$pshome`) に格納されているいくつかの書式設定ファイル (types.ps1xml) が用意されています。 これらの各ファイルは、.NET オブジェクトの特定のセットの既定の表示を定義します。 これらのファイルは変更しないでください。 ただし、独自のカスタム書式設定ファイルを作成するためのリファレンスとして使用することもできます。

`Certificate.Format.ps1xml` は、x.509 証明書や証明書ストアなど、証明書ストア内のオブジェクトの表示を定義します。

`DotNetTypes.Format.ps1xml` は、CultureInfo、FileVersionInfo、EventLogEntry など、その他の .NET オブジェクトの表示を定義します。

`FileSystem.Format.ps1xml` は、ファイルおよびディレクトリオブジェクトなどのファイルシステムオブジェクトの表示を定義します。

`Help.Format.ps1xml` は、詳細、完全、パラメーター、例ビューなど、 [get-help](/powershell/module/Microsoft.PowerShell.Core/Get-Help)コマンドレットで使用されるさまざまなビューを定義します。

`PowerShellCore.Format.ps1xml` は、 [Get Member](/powershell/module/Microsoft.PowerShell.Utility/Get-Member)コマンドレットおよび[get-help](/powershell/module/Microsoft.PowerShell.Core/Get-History)コマンドレットによって返されるオブジェクトなど、Windows PowerShell コアコマンドレットによって生成されるオブジェクトの表示を定義します。

`PowerShellTrace.Format.ps1xml` は、trace[コマンド](/powershell/module/Microsoft.PowerShell.Utility/Trace-Command)レットによって生成されるトレースオブジェクトなどのトレースオブジェクトの表示を定義します。

`Registry.Format.ps1xml` は、キーオブジェクトやエントリオブジェクトなどのレジストリオブジェクトの表示を定義します。

## <a name="see-also"></a>参照

[Windows PowerShell コマンドレットの記述](../cmdlet/writing-a-windows-powershell-cmdlet.md)
