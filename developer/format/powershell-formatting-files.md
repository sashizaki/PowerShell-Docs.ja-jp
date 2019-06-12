---
title: Windows PowerShell の書式設定ファイル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5d4c8f84-ebd2-4405-bb10-cfc5400d4ad6
caps.latest.revision: 6
ms.openlocfilehash: 3ec127d5ff60754de5d7f1ac73f2965524228b9c
ms.sourcegitcommit: 4ec9e10647b752cc62b1eabb897ada3dc03c93eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2019
ms.locfileid: "66830261"
---
# <a name="windows-powershell-formatting-files"></a>Windows PowerShell 書式設定ファイル

Windows PowerShell には、いくつかの書式設定ファイルが用意されています (. format.ps1xml) のインストール ディレクトリ内にある (`$pshome`)。 これらの各ファイルには、特定の一連の .NET オブジェクトの既定の表示を定義します。 これらのファイルを変更しない必要があります。 ただし、独自のカスタム書式設定ファイルを作成するための参照としてそれらを使用することができます。

`Certificate.Format.ps1xml` X.509 証明書などの証明書ストアと証明書ストア内のオブジェクトの表示を定義します。

`DotNetTypes.Format.ps1xml` CultureInfo、FileVersionInfo、および EventLogEntry オブジェクトなどの他の .NET オブジェクトの表示を定義します。

`FileSystem.Format.ps1xml` ファイルとディレクトリのオブジェクトなどのファイル システム オブジェクトの表示を定義します。

`Help.Format.ps1xml` 使用されるさまざまなビューを定義、 [Get-help](/powershell/module/Microsoft.PowerShell.Core/Get-Help)フル、パラメーター、および例の詳細なビューなどのコマンドレット。

`PowerShellCore.Format.ps1xml` によって返されるオブジェクトなどの Windows PowerShell コア コマンドレットによって生成されたオブジェクトの表示を定義、 [Get-member](/powershell/module/Microsoft.PowerShell.Utility/Get-Member)と[Get-history](/powershell/module/Microsoft.PowerShell.Core/Get-History)コマンドレット。

`PowerShellTrace.Format.ps1xml` トレース オブジェクトによって生成されるものなどの表示を定義、 [Trace-command](/powershell/module/Microsoft.PowerShell.Utility/Trace-Command)コマンドレット。

`Registry.Format.ps1xml` キーとエントリのオブジェクトなど、レジストリ オブジェクトの表示を定義します。

## <a name="see-also"></a>参照

[Windows PowerShell コマンドレットの記述](../cmdlet/writing-a-windows-powershell-cmdlet.md)
