---
description: Windows Management Instrumentation (WMI) は、Common Information Model (CIM) を使用して、先進企業のシステム、アプリケーション、ネットワーク、デバイス、およびその他の管理可能なコンポーネントを表します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_wmi?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_WMI
ms.openlocfilehash: d24b952ee167e51815d6d9920e95bbc9a6bb9608
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223208"
---
# <a name="about-wmi"></a>WMI について

## <a name="short-description"></a>概要

Windows Management Instrumentation (WMI) は、Common Information Model (CIM) を使用して、先進企業のシステム、アプリケーション、ネットワーク、デバイス、およびその他の管理可能なコンポーネントを表します。

## <a name="long-description"></a>詳細説明

Windows Management Instrumentation (WMI) は、業界標準の Web-Based Enterprise Management (WBEM) を Microsoft が実装したものです。

従来の WMI は、DCOM を使用してネットワークデバイスと通信し、リモートシステムを管理します。 Windows PowerShell 3.0 では、WinRM を使用して DCOM の依存関係を削除する CIM プロバイダーモデルが導入されています。 また、この CIM プロバイダーモデルでは、開発者がネイティブコード (C) で Windows PowerShell コマンドレットを記述できるようにする新しい WMI プロバイダー Api も使用 \+ \+ します。

WMI プロバイダーと Windows PowerShell プロバイダーを混同しないようにしてください。 多くの Windows 機能には、管理機能を公開する WMI プロバイダーが関連付けられています。 WMI プロバイダーを取得するには、次のクエリのように __Provider WMI クラスのインスタンスを取得する WMI クエリを実行します。

```powershell
Get-WmiObject -Class __Provider
```

## <a name="three-components-of-wmi"></a>WMI の3つのコンポーネント

WMI の次の3つのコンポーネントは、Windows PowerShell と対話します。名前空間、プロバイダー、およびクラスです。

Wmi 名前空間は、WMI プロバイダーと WMI クラスを関連コンポーネントのグループに整理します。 このようにして、.NET Framework 名前空間に似ています。
名前空間は物理的な場所ではありませんが、論理データベースに似ています。
すべての WMI 名前空間は、__Namespace システムクラスのインスタンスです。 既定の WMI 名前空間は、ルート \/ CIMV2 (Microsoft Windows 2000 以降) です。 Windows PowerShell を使用して現在のセッションで WMI 名前空間を取得するには、次の形式のコマンドを使用します。

```powershell
Get-WmiObject -Class __Namespace
```

他の名前空間の WMI 名前空間を取得するには、Namespace パラメーターを使用して検索の場所を変更します。 次のコマンドは、Root/Cimv2/Applications 名前空間に存在する WMI 名前空間を検索します。

```powershell
Get-WmiObject -Class __Namespace -Namespace root/CIMv2/applications
```

WMI 名前空間は階層構造です。 したがって、特定のシステム上のすべての名前空間の一覧を取得するには、ルート名前空間から開始する再帰クエリを実行する必要があります。

WMI プロバイダーは、Windows の管理可能なオブジェクトに関する情報を公開します。 プロバイダーは、コンポーネントからデータを取得し、WMI を介して Windows PowerShell などの管理アプリケーションにそのデータを渡します。 ほとんどの WMI プロバイダーは動的プロバイダーです。つまり、管理アプリケーションから要求されたときにデータを動的に取得します。

## <a name="finding-wmi-classes"></a>検索 (WMI クラスを)

Windows 8 の既定のインストールでは、1100を超える WMI クラスがルート Cimv2 に存在 \/ します。 この多くの WMI クラスを使用すると、特定のタスクを実行するために使用する適切な WMI クラスを特定することが困難になります。 Windows PowerShell 3.0 には、特定のトピックに関連する WMI クラスを見つけるための2つの方法が用意されています。

たとえば、 \\ ディスクに関連付けられているルート CIMV2 wmi 名前空間内の WMI クラスを検索するには、次に示すようなクエリを使用できます。

```powershell
Get-WmiObject -List *disk*
```

メモリに関連する WMI クラスを検索するには、次に示すようなクエリを使用することができます。

```powershell
Get-WmiObject -List *memory*
```

CIM コマンドレットには、WMI クラスを検出する機能も用意されています。 これを行うには、Get-CIMClass コマンドレットを使用します。 ここに示すコマンドは、ビデオに関連する WMI クラスの一覧です。

```powershell
Get-CimClass *video*
```

タブ拡張は、WMI 名前空間を変更するときに機能します。したがって、タブ拡張を使用すると、サブ WMI 名前空間を簡単に検出できるようになります。 次の例では、Get-CimClass コマンドレットを使用して、電源設定に関連する WMI クラスを一覧表示します。
検索するには、名前空間を入力し、 `root/CIMV2/` tab キーを何度か押して、power 名前空間が表示されるようにします。 次にコマンドを示します。

```powershell
Get-CimClass *power* -Namespace root/cimv2/power
```
