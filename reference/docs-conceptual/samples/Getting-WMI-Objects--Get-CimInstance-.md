---
ms.date: 12/23/2019
keywords: powershell,コマンドレット
title: WMI オブジェクトの取得 Get CimInstance
ms.openlocfilehash: 4ff47844fd367a49f554c7c05c491bdddf28eabc
ms.sourcegitcommit: bc9a4904c2b1561386d748fc9ac242699d2f1694
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "77002652"
---
# <a name="getting-wmi-objects-get-ciminstance"></a>WMI オブジェクトの取得 (Get-CimInstance)

## <a name="getting-wmi-objects-get-ciminstance"></a>WMI オブジェクトの取得 (Get-CimInstance)

Windows Management Instrumentation (WMI) は、Windows システム管理のための中核となるテクノロジであり、幅広い種類の情報を一貫した方法で公開します。 WMI によって可能になるタスクが非常に多いことから、WMI オブジェクトにアクセスするための PowerShell コマンドレットである `Get-CimInstance` は、実際の作業を行うための最も便利なコマンドレットの 1 つと言えます。 ここでは、CimCmdlets を使って WMI オブジェクトにアクセスする方法と、WMI オブジェクトを使って特定の作業を行う方法について説明します。

### <a name="listing-wmi-classes"></a>WMI クラスの一覧を取得する

WMI のほとんどのユーザーが直面する最初の問題は、WMI で何ができるかを調べることです。 WMI クラスは、管理できるリソースを記述しています。 何百もの WMI クラスがあり、その中には数十個のプロパティを持つクラスもあります。

この問題に対処するため、`Get-CimClass` では WMI を探索可能にしました。 ローカル コンピューター上で使える WMI クラスの一覧を取得するには、次のように入力します。

```powershell
Get-CimClass -Namespace root/CIMV2 |
  Where-Object CimClassName -like Win32* |
    Select-Object CimClassName
```

```Output
CimClassName
------------
Win32_DeviceChangeEvent
Win32_SystemConfigurationChangeEvent
Win32_VolumeChangeEvent
Win32_SystemTrace
Win32_ProcessTrace
Win32_ProcessStartTrace
Win32_ProcessStopTrace
Win32_ThreadTrace
Win32_ThreadStartTrace
Win32_ThreadStopTrace
...
```

同じ情報をリモート コンピューターから取得するには、次のように、**ComputerName** パラメーターにコンピューター名や IP アドレスを指定します。

```powershell
Get-CimClass -Namespace root/CIMV2 -ComputerName 192.168.1.29
```

リモート コンピューターから返されるクラスの一覧は、そのコンピューターで実行されている特定のオペレーティング システムや、インストールされているアプリケーションによって追加された特定の WMI 拡張機能に応じて異なることがあります。

> [!NOTE]
> CIM コマンドレットを使用してリモート コンピューターに接続するときは、リモート コンピューターで WMI が実行されていて、使用するアカウントがリモート コンピューターのローカル管理者グループに属している必要があります。
> リモート システムに PowerShell をインストールする必要はありません。 そのため、WMI が利用可能であれば、PowerShell を実行していないオペレーティング システムであっても管理できます。

### <a name="displaying-wmi-class-details"></a>WMI クラスの詳細を表示する

WMI クラスの名前がわかっている場合は、その名前を使って情報をすぐに取得できます。 たとえば、コンピューターに関する情報を取得するためによく使われる WMI クラスの 1 つに、**Win32_OperatingSystem** があります。

```powershell
Get-CimInstance -Class Win32_OperatingSystem
```

```Output
SystemDirectory     Organization BuildNumber RegisteredUser SerialNumber            Version
---------------     ------------ ----------- -------------- ------------            -------
C:\WINDOWS\system32 Microsoft    18362       USER1          00330-80000-00000-AA175 10.0.18362
```

ここでは、すべてのパラメーターを示しましたが、このコマンドはもっと簡潔に表現できます。
**ComputerName** パラメーターは、ローカル システムに接続するときには必要ありません。 最も一般的なケースを示し、このパラメーターを思い出してもらうために使いました。 **Namespace** の既定値は `root/CIMV2` であるため、これも省略できます。 最後に、ほとんどのコマンドレットでは、共通のパラメーターの名前を省略できます。 `Get-CimInstance` の場合、最初のパラメーターで名前を指定しないと、PowerShell ではそれが **Class** パラメーターとして扱われます。 したがって、先ほどのコマンドは、次のように入力することもできました。

```powershell
Get-CimInstance Win32_OperatingSystem
```

**Win32_OperatingSystem** クラスには、ここで紹介した以外にも多数のプロパティがあります。 Get-Member を使うと、すべてのプロパティを参照できます。 WMI クラスのプロパティは、他のオブジェクト プロパティと同じように自動的に取得できます。

```powershell
Get-CimInstance -Class Win32_OperatingSystem | Get-Member -MemberType Property
```

```Output
   TypeName: Microsoft.Management.Infrastructure.CimInstance#root/cimv2/Win32_OperatingSystem
Name                                      MemberType Definition
----                                      ---------- ----------
BootDevice                                Property   string BootDevice {get;}
BuildNumber                               Property   string BuildNumber {get;}
BuildType                                 Property   string BuildType {get;}
Caption                                   Property   string Caption {get;}
CodeSet                                   Property   string CodeSet {get;}
CountryCode                               Property   string CountryCode {get;}
CreationClassName                         Property   string CreationClassName {get;}
CSCreationClassName                       Property   string CSCreationClassName {get;}
CSDVersion                                Property   string CSDVersion {get;}
CSName                                    Property   string CSName {get;}
CurrentTimeZone                           Property   short CurrentTimeZone {get;}
DataExecutionPrevention_32BitApplications Property   bool DataExecutionPrevention_32BitApplications {get;}
DataExecutionPrevention_Available         Property   bool DataExecutionPrevention_Available {get;}
...
```

#### <a name="displaying-non-default-properties-with-format-cmdlets"></a>既定以外のプロパティを Format コマンドレットで表示する

**Win32_OperatingSystem** クラスに含まれている情報のうち、既定では表示されない情報を表示するには、**Format** コマンドレットを使います。 たとえば、利用可能なメモリのデータを表示するには、次のように入力します。

```powershell
Get-CimInstance -Class Win32_OperatingSystem |
  Format-Table -Property TotalVirtualMemorySize, TotalVisibleMemorySize,
    FreePhysicalMemory, FreeVirtualMemory, FreeSpaceInPagingFiles
```

```Output
TotalVirtualMemorySize TotalVisibleMemorySize FreePhysicalMemory FreeVirtualMemory FreeSpaceInPagingFiles
---------------------- ---------------------- ------------------ ----------------- ----------------------
              33449088               16671872            6451868          18424496               16285032
```

> [!NOTE]
> `Format-Table` のプロパティ名にはワイルドカードを指定できるので、最後のパイプライン要素は `Format-Table -Property Total*Memory*, Free*` のように省略できます

メモリのデータは、次のように入力して一覧の形式にすると、さらに読みやすくなります。

```powershell
Get-CimInstance -Class Win32_OperatingSystem | Format-List Total*Memory*, Free*
```

```Output
TotalVirtualMemorySize : 33449088
TotalVisibleMemorySize : 16671872
FreePhysicalMemory     : 6524456
FreeSpaceInPagingFiles : 16285808
FreeVirtualMemory      : 18393668
Name                   : Microsoft Windows 10 Pro|C:\WINDOWS|\Device\Harddisk0\Partition2
```
