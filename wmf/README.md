---
title: Windows Management Framework (WMF)
ms.date: 2017-02-14
keywords: "PowerShell、WMF"
description: 
ms.topic: article
author: keithb
manager: dongill
ms.prod: powershell
ms.technology: WMF
ms.openlocfilehash: 749dd8b19592cb5f40a5aed32d28edeb5cb2dfc9
ms.sourcegitcommit: bb2c52577a519c0599a0b3c961f749fe0df70a45
translationtype: HT
---
# <a name="windows-management-framework"></a>Windows Management Framework

Windows Management Framework (WMF) は配信メカニズムであり、さまざまな種類の Windows や Windows Server に一貫した管理インターフェイスを提供します。
WMF をインストールすると、お客様はご利用の環境で OS をシームレスにミックスし、相互運用できます。
WMF は一部の Windows や Windows Server の管理機能を更新します。以前のバージョンの Windows と Windows Server でインストールできます (通常、2 つ下のバージョンまで)。

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

| オペレーティング システムのバージョン | [WMF 5.1](https://aka.ms/wmf51download) | [WMF 5.0](https://aka.ms/wmf5download) | [WMF 4.0](https://aka.ms/wmf4download) |  [WMF 3.0](https://aka.ms/wmf3download) | [WMF 2.0](https://aka.ms/wmf2download) |
| ------------------------ | ----------- | ----------- | ----------- | ------------ |  ------------- |
| Windows Server 2016 | 出荷時にインストール済み |  |  |  |  |
| Windows 10 | 出荷時にインストール済み | 出荷時にインストール済み  | | | |  
| Windows Server 2012 R2| 可 | 可 | 出荷時にインストール済み |  |  |
| Windows 8.1 | 可 | 可 |  出荷時にインストール済み |  |  |
| Windows Server 2012 | 可 | 可 | 可 |  出荷時にインストール済み | |
| Windows 8 |  |  |  | 出荷時にインストール済み | |
| Windows Server 2008 R2 SP1 | 可 | 可 | 可 |  可| 出荷時にインストール済み |
| Windows 7 SP1  | 可 | 可 | 可 | 可 | 出荷時にインストール済み |
| Windows Server 2008 SP2 | | | | 可 | 可 |
| Windows Vista | | | | | 可 |
| Windows Server 2003| | | |  | 可 |
| Windows XP | | | |  | 可 |

**"出荷時にインストール済み"**: `specified WMF` の機能は、示されているバージョンの Windows および Windows Server に付属しています。
したがって、示されているオペレーティング システムのバージョンには、`specified WMF` をインストールする必要はありません。
