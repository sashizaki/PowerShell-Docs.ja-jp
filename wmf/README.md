---
title: Windows Management Framework (WMF)
ms.date: 2016-12-07
keywords: "PowerShell、WMF"
description: 
ms.topic: article
author: keithb
manager: dongill
ms.prod: powershell
ms.technology: WMF
ms.openlocfilehash: b652613561655c4cbd63342b0fcc495195f83a80
ms.sourcegitcommit: b88151841dd44c8ee9296d0855d8b322cbf16076
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

- [WMF 5.1 (プレビュー)](5.1/release-notes.md)
- [WMF 5.0](5.0/releasenotes.md)

## <a name="wmf-availability-across-windows-operating-systems"></a>Windows オペレーティング システム全体の WMF 可用性

| オペレーティング システムのバージョン | [WMF 5.1](https://aka.ms/wmf51download) | [WMF 5.0](https://aka.ms/wmf5download) | [WMF 4.0](https://aka.ms/wmf4download) |  [WMF 3.0](https://aka.ms/wmf3download) | [WMF 2.0](https://aka.ms/wmf2download) |
| ------------------------ | ----------- | ----------- | ----------- | ------------ |  ------------- |
| Windows Server 2016 | 箱で出荷 |  |  |  |  |
| Windows 10 | 箱で出荷 | 箱で出荷  | | | |  
| Windows Server 2012 R2| はい | はい | 箱で出荷 |  |  |
| Windows 8.1 | はい | はい |  箱で出荷 |  |  |
| Windows Server 2012 | はい | はい | はい |  箱で出荷 | |
| Windows 8 |  |  |  | 箱で出荷 | |
| Windows Server 2008 R2 SP1 | はい | はい | はい |  はい| 箱で出荷 |
| Windows 7 SP1  | はい | はい | はい | はい | 箱で出荷 |
| Windows Server 2008 SP2 | | | | はい | はい |
| Windows Vista | | | | | はい |
| Windows Server 2003| | | |  | はい |
| Windows XP | | | |  | はい |

**"箱で出荷"**: `specified WMF` の機能は、示されているバージョンの Windows および Windows Server に付属しています。
したがって、示されているオペレーティング システムのバージョンには、`specified WMF` をインストールする必要はありません。
