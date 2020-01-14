---
ms.date: 12/23/2019
keywords: powershell,コマンドレット
title: コンピューターに関する情報の収集
ms.openlocfilehash: 9407ff15b3c3ca6b3adab60d4d01d957c599e79e
ms.sourcegitcommit: 058a6e86eac1b27ca57a11687019df98709ed709
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "75737238"
---
# <a name="collecting-information-about-computers"></a>コンピューターに関する情報の収集

**CimCmdlets** モジュールのコマンドレットは、一般的なシステム管理タスクに最も重要なコマンドレットです。 サブシステムの重要なすべての設定は、WMI を介して公開されています。 さらに、WMI では、データは 1 つまたは複数の項目が集まったオブジェクトとして扱われます。 Windows PowerShell の操作の対象もオブジェクトです。パイプラインを使用することにより、1 つまたは複数のオブジェクトを同じ方法で処理できます。このため、一般的な WMI アクセスにより、高度なタスクを最小限の労力で実行できるようになります。

## <a name="listing-desktop-settings"></a>デスクトップの設定を一覧表示する

まず、ローカル コンピューターのデスクトップに関する情報を収集するコマンドについて説明します。

```powershell
Get-CimInstance -ClassName Win32_Desktop
```

このコマンドを実行すると、使用中であるかどうかに関係なく、すべてのデスクトップの情報が返されます。

> [!NOTE]
> WMI のクラスによっては、非常に詳しい情報が返されます。その WMI クラスのメタデータが含まれる場合もあります。

こうしたメタデータのプロパティには、通常、**Cim** で始まる名前が付いているため、`Select-Object` を使用することでこれらのプロパティをフィルター処理できます。 **-ExcludeProperty** パラメーターと値に "Cim*" を指定します。 次に例を示します。

```powershell
Get-CimInstance -ClassName Win32_Desktop | Select-Object -ExcludeProperty "CIM*"
```

メタデータをフィルターで除外するには、パイプライン演算子 (|) を使用して、`Get-CimInstance` コマンドの結果を `Select-Object -ExcludeProperty "CIM*"` に渡します。

## <a name="listing-bios-information"></a>BIOS 情報を一覧表示する

WMI **Win32_BIOS** クラスは、ローカル コンピューターのシステム BIOS について、詳細な情報を凝縮して返します。

```powershell
Get-CimInstance -ClassName Win32_BIOS
```

## <a name="listing-processor-information"></a>プロセッサ情報を一覧表示する

WMI の **Win32_Processor** クラスを使用すると (通常はフィルター処理を併用)、プロセッサ全般に関する情報を取得できます。

```powershell
Get-CimInstance -ClassName Win32_Processor | Select-Object -ExcludeProperty "CIM*"
```

**SystemType** プロパティを返すことで、プロセッサ ファミリの一般的な説明を表示できます。

```powershell
Get-CimInstance -ClassName Win32_ComputerSystem | Select-Object -Property SystemType

SystemType
----------
X86-based PC
```

## <a name="listing-computer-manufacturer-and-model"></a>コンピューターの製造元および型番を一覧表示する

コンピューターの型番情報も **Win32_ComputerSystem** から取得できます。 OEM データを取得するのであれば、標準の表示出力で十分です。フィルター処理は不要です。

```powershell
Get-CimInstance -ClassName Win32_ComputerSystem
```

```Output
Name PrimaryOwnerName Domain    TotalPhysicalMemory Model                   Manufacturer
---- ---------------- ------    ------------------- -----                   ------------
MyPC Jane Doe         WORKGROUP 804765696           DA243A-ABA 6415cl NA910 Compaq Presario 06
```

このようなコマンドからの出力結果はハードウェアから直接情報が取得されますが、詳しい情報は含まれていません。 ハードウェアの製造元によって正しく構成されていないために利用できない情報もあります。

## <a name="listing-installed-hotfixes"></a>インストールされている修正プログラムを一覧表示する

インストールされているすべての修正プログラムを一覧表示するには **Win32_QuickFixEngineering** を使用します。

```powershell
Get-CimInstance -ClassName Win32_QuickFixEngineering
```

このクラスからは、次のような修正プログラムの一覧が返されます。

```Output
Source Description     HotFixID  InstalledBy   InstalledOn PSComputerName
------ -----------     --------  -----------   ----------- --------------
       Security Update KB4048951 Administrator 12/16/2017  .
```

より簡潔な出力を得るには、いくつかのプロパティを除外します。 `Get-CimInstance` の **Property** パラメーターを使用して **HotFixID** だけを選ぶこともできますが、その場合は非常に多くの情報が返されます。既定では、すべてのメタデータが表示されるためです。

```powershell
Get-CimInstance -ClassName Win32_QuickFixEngineering -Property HotFixID
```

```Output
InstalledOn           :
Caption               :
Description           :
InstallDate           :
Name                  :
Status                :
CSName                :
FixComments           :
HotFixID              : KB4533002
InstalledBy           :
ServicePackInEffect   :
PSComputerName        :
CimClass              : root/cimv2:Win32_QuickFixEngineering
CimInstanceProperties : {Caption, Description, InstallDate, Name…}
CimSystemProperties   : Microsoft.Management.Infrastructure.CimSystemProperties
...
```

`Get-CimInstance` の **Property** パラメーターによって制限されるのは、WMI クラスのインスタンスから返されるプロパティです。PowerShell に返されるオブジェクトが制限されるわけではありません。実際、上の例を見ると、余分なデータが返されていることがわかります。 出力結果を減らすためには、`Select-Object` を使用します。

```powershell
Get-CimInstance -ClassName Win32_QuickFixEngineering -Property HotFixId | Select-Object -Property HotFixId
```

```Output
HotFixId
--------
KB4048951
```

## <a name="listing-operating-system-version-information"></a>オペレーティング システムのバージョン情報を一覧表示する

**Win32_OperatingSystem** クラスのプロパティには、バージョンおよびサービス パックの情報が含まれます。 これらのプロパティだけを明示的に選ぶことによって、バージョン情報の概要を **Win32_OperatingSystem** から取得できます。

```powershell
Get-CimInstance -ClassName Win32_OperatingSystem |
  Select-Object -Property BuildNumber,BuildType,OSType,ServicePackMajorVersion,ServicePackMinorVersion
```

`Select-Object` の **Property** パラメーターでは、ワイルドカードも使用できます。 ここでは **Build** または **ServicePack** で始まるすべてのプロパティを使用することが重要であるため、次のように短く記述することもできます。

```powershell
Get-CimInstance -ClassName Win32_OperatingSystem | Select-Object -Property Build*,OSType,ServicePack*
```

```Output
BuildNumber             : 18362
BuildType               : Multiprocessor Free
OSType                  : 18
ServicePackMajorVersion : 0
ServicePackMinorVersion : 0
```

## <a name="listing-local-users-and-owner"></a>ローカル ユーザーと所有者を一覧表示する

ライセンスされたユーザー数、現在のユーザー数、所有者名など、ローカル ユーザーの全般的な情報は、**Win32_OperatingSystem** クラスのプロパティを選択することによって取得できます。 表示するプロパティを明示的に選ぶには、次のように入力します。

```powershell
Get-CimInstance -ClassName Win32_OperatingSystem |
  Select-Object -Property NumberOfLicensedUsers,NumberOfUsers,RegisteredUser
```

これをワイルドカードで簡潔に記述するには、次のように入力します。

```powershell
Get-CimInstance -ClassName Win32_OperatingSystem | Select-Object -Property *user*
```

## <a name="getting-available-disk-space"></a>使用可能なディスク領域を取得する

ローカル ドライブのディスク容量と空き領域を表示するには、Win32_LogicalDisk WMI クラスを使用します。
表示する必要があるのは、DriveType が 3 (WMI が固定ハード ディスクに使用する値) のインスタンスだけです。

```powershell
Get-CimInstance -ClassName Win32_LogicalDisk -Filter "DriveType=3"
```

```Output
DeviceID DriveType ProviderName VolumeName Size         FreeSpace   PSComputerName
-------- --------- ------------ ---------- ----         ---------   --------------
C:       3                      Local Disk 203912880128 65541357568 .
Q:       3                      New Volume 122934034432 44298250240 .
```

```powershell
Get-CimInstance -ClassName Win32_LogicalDisk -Filter "DriveType=3" |
  Measure-Object -Property FreeSpace,Size -Sum |
    Select-Object -Property Property,Sum
```

```Output
Property           Sum
--------           ---
FreeSpace 109839607808
Size      326846914560
```

## <a name="getting-logon-session-information"></a>ログオン セッション情報を取得する

ユーザーに関連付けられたログオン セッションの全般的な情報は、**Win32_LogonSession** WMI クラスを使って取得できます。

```powershell
Get-CimInstance -ClassName Win32_LogonSession
```

## <a name="getting-the-user-logged-on-to-a-computer"></a>コンピューターにログオンしたユーザーを取得する

特定のコンピューター システムにログオンしているユーザーを表示するには、Win32_ComputerSystem を使用します。 このコマンドで返されるのは、システムのデスクトップにログオンしているユーザーだけです。

```powershell
Get-CimInstance -ClassName Win32_ComputerSystem -Property UserName
```

## <a name="getting-local-time-from-a-computer"></a>コンピューターのローカル時刻を取得する

特定のコンピューターにおける現在のローカル時刻を取得するには、**Win32_LocalTime** WMI クラスを使用します。

```powershell
Get-CimInstance -ClassName Win32_LocalTime
```

```Output
Day            : 23
DayOfWeek      : 1
Hour           : 8
Milliseconds   :
Minute         : 52
Month          : 12
Quarter        : 4
Second         : 55
WeekInMonth    : 4
Year           : 2019
PSComputerName :
```

## <a name="displaying-service-status"></a>サービスの状態を表示する

特定のコンピューターを対象にすべてのサービスの状態を表示するには、ローカルで `Get-Service` コマンドレットを使用します。 リモート システムの場合は、**Win32_Service** WMI クラスを使用します。 `Select-Object` を併用して結果をフィルター処理し、**Status**、**Name**、**DisplayName** だけを抽出した場合は、`Get-Service` を実行した場合とほぼ同じ出力形式になります。

```powershell
Get-CimInstance -ClassName Win32_Service | Select-Object -Property Status,Name,DisplayName
```

非常に長い名前のサービスも存在します。こうしたサービスの名前全体を表示するには、`Format-Table` に **AutoSize** パラメーターと **Wrap** パラメーターを使用します。列幅が調整され、長い名前は切り詰められるのではなく折り返されます。

```powershell
Get-CimInstance -ClassName Win32_Service | Format-Table -Property Status,Name,DisplayName -AutoSize -Wrap
```
