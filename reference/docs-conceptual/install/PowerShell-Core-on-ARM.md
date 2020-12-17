---
title: Arm に PowerShell Core をインストールする
description: Arm ベースのシステムへの PowerShell Core のインストール
ms.date: 11/11/2020
ms.openlocfilehash: 85a2cccb18341ffee8c81430bc8490e5d3e97b41
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "94892074"
---
# <a name="powershell-core-on-arm"></a>Arm 上の PowerShell Core

Arm での PowerShell のサポートは、 **.NET Core でサポートされている OS ライフサイクル ポリシー** に基づいています。

PowerShell 7.1 は、[.NET Core 3.1 でサポートされている OS ライフサイクル ポリシー](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md)に基づいており、次のプラットフォームをサポートしています。

|         OS          |          バージョン           | アーキテクチャ |          ライフサイクル           |
| ------------------- | -------------------------- | ------------- | ---------------------------- |
| Windows Nano Server | バージョン 1803+              | Arm32         | [Windows][Windows-lifecycle] |
| Alpine Linux        | 3.10+                      | Arm64         | [Alpine][Alpine-lifecycle]   |
| Debian              | 9+                         | Arm32、Arm64  | [Debian][Debian-lifecycle]   |
| Ubuntu              | 20.10、20.04、18.04、16.04 | Arm32、Arm64  | [Ubuntu][Ubuntu-lifecycle]   |

PowerShell 7.0 は、[.NET Core 5.0 でサポートされている OS ライフサイクル ポリシー](https://github.com/dotnet/core/blob/master/release-notes/5.0/5.0-supported-os.md)に基づいており、次のプラットフォームをサポートしています。

|        OS         |          バージョン           | アーキテクチャ |          ライフサイクル           |
| ----------------- | -------------------------- | ------------- | ---------------------------- |
| Windows 10 クライアント | バージョン 1607+              | Arm64         | [Windows][Windows-lifecycle] |
| Alpine Linux      | 3.11+                      | Arm64         | [Alpine][Alpine-lifecycle]   |
| Debian            | 9+                         | Arm32、Arm64  | [Debian][Debian-lifecycle]   |
| Ubuntu            | 20.10、20.04、18.04、16.04 | Arm32、Arm64  | [Ubuntu][Ubuntu-lifecycle]   |

[Windows-lifecycle]: https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet
[Alpine-lifecycle]: https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases
[Debian-lifecycle]: https://wiki.debian.org/DebianReleases
[Ubuntu-lifecycle]: https://wiki.ubuntu.com/Releases

インストール手順については、次の記事を参照してください。

- [Arm 上の Windows 10](installing-powershell-core-on-windows.md#installing-the-zip-package)
- [Windows 10 IoT Enterprise](installing-powershell-core-on-windows.md#deploying-on-windows-10-iot-enterprise)
- [Windows 10 IoT Core](installing-powershell-core-on-windows.md#deploying-on-windows-10-iot-core)
- [Raspbian](installing-powershell-core-on-linux.md#raspbian)
