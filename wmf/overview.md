---
ms.date: 06/12/2018
keywords: WMF, PowerShell, セットアップ
title: Windows Management Framework (WMF)
ms.openlocfilehash: 17011f88c364cb56a0c87f092873ccd99db450bc
ms.sourcegitcommit: 68093cc12a7a22c53d11ce7d33c18622921a0dd1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36943608"
---
# <a name="windows-management-framework"></a>Windows Management Framework

Windows Management Framework (WMF) では、Windows の一貫した管理インターフェイスが提供されます。 WMF では、さまざまなバージョンの Windows クライアントおよび Windows Server を管理するためのシームレスな方法が提供されます。 WMF インストーラー パッケージには、管理機能の更新プログラムが含まれており、以前のバージョンの Windows で使用できます。

WMF をインストールすると、次の機能が追加または更新されます。

- Windows PowerShell
- Windows PowerShell Desired State Configuration (DSC)
- Windows PowerShell Integrated Script Environment (ISE)
- Windows リモート管理 (WinRM)
- Windows Management Instrumentation (WMI)
- Windows PowerShell Web サービス (Management OData IIS 拡張機能)
- ソフトウェア インベントリ ログ (SIL)
- Server Manager CIM Provider

## <a name="wmf-release-notes"></a>WMF リリース ノート

PowerShell と特定の WMF のその他のコンポーネントのさまざまな拡張に関する詳細については、下のリンクにアクセスし、リリース ノートを参照してください。

- [WMF 5.1](5.1/release-notes.md)
- [WMF 5.0](5.0/releasenotes.md)
- [WMF 4.0](https://download.microsoft.com/download/3/D/6/3D61D262-8549-4769-A660-230B67E15B25/Windows%20Management%20Framework%204%200%20Release%20Notes.docx)
- [WMF 3.0](https://download.microsoft.com/download/E/7/6/E76850B8-DA6E-4FF5-8CCE-A24FC513FD16/WMF%203%20Release%20Notes.docx)

## <a name="wmf-availability-across-windows-operating-systems"></a>Windows オペレーティング システム全体の WMF 可用性

|オペレーティング システムのバージョン  |[WMF 5.1][] |[WMF 5.0][] |[WMF 4.0][] |[WMF 3.0][]  |[WMF 2.0][] |
|--------------------------|------------|------------|------------|-------------|------------|
|Windows Server 2016       |出荷時にインストール済み|            |            |             |            |
|Windows 10                |出荷時にインストール済み|出荷時にインストール済み|            |             |            |
|Windows Server 2012 R2    |可         |可         |出荷時にインストール済み|             |            |
|Windows 8.1               |可         |可         |出荷時にインストール済み|             |            |
|Windows Server 2012       |可         |可         |可         |出荷時にインストール済み |            |
|Windows 8                 |            |            |            |出荷時にインストール済み |            |
|Windows Server 2008 R2 SP1|可         |可         |可         |可          |出荷時にインストール済み|
|Windows 7 SP1             |可         |可         |可         |可          |出荷時にインストール済み|
|Windows Server 2008 SP2   |            |            |            |可          |可         |
|Windows Vista             |            |            |            |             |可         |
|Windows Server 2003       |            |            |            |             |可         |
|Windows XP                |            |            |            |可          |            |

**出荷時にインストール済み**: 指定されたバージョンの WMF の機能は、示されているバージョンの Windows クライアントおよび Windows Server に付属しています。

[WMF 5.1]: https://aka.ms/wmf51download
[WMF 5.0]: https://aka.ms/wmf5download
[WMF 4.0]: https://aka.ms/wmf4download
[WMF 3.0]: https://aka.ms/wmf3download
[WMF 2.0]: https://aka.ms/wmf2download
