---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/get-cimclass?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CimClass
ms.openlocfilehash: e5700af4ff3f238d347e2c367416af08caf148ff
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212459"
---
# <span data-ttu-id="57fe2-103">Get-CimClass</span><span class="sxs-lookup"><span data-stu-id="57fe2-103">Get-CimClass</span></span>

## <span data-ttu-id="57fe2-104">概要</span><span class="sxs-lookup"><span data-stu-id="57fe2-104">SYNOPSIS</span></span>
<span data-ttu-id="57fe2-105">特定の名前空間にある CIM クラスのリストを取得します。</span><span class="sxs-lookup"><span data-stu-id="57fe2-105">Gets a list of CIM classes in a specific namespace.</span></span>

## <span data-ttu-id="57fe2-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="57fe2-106">SYNTAX</span></span>

### <span data-ttu-id="57fe2-107">ComputerSet (既定)</span><span class="sxs-lookup"><span data-stu-id="57fe2-107">ComputerSet (Default)</span></span>

```
Get-CimClass [[-ClassName] <String>] [[-Namespace] <String>] [-OperationTimeoutSec <UInt32>]
 [-ComputerName <String[]>] [-MethodName <String>] [-PropertyName <String>]
 [-QualifierName <String>] [<CommonParameters>]
```

### <span data-ttu-id="57fe2-108">SessionSet</span><span class="sxs-lookup"><span data-stu-id="57fe2-108">SessionSet</span></span>

```
Get-CimClass [[-ClassName] <String>] [[-Namespace] <String>] [-OperationTimeoutSec <UInt32>]
 -CimSession <CimSession[]> [-MethodName <String>] [-PropertyName <String>]
 [-QualifierName <String>] [<CommonParameters>]
```

## <span data-ttu-id="57fe2-109">Description</span><span class="sxs-lookup"><span data-stu-id="57fe2-109">DESCRIPTION</span></span>

<span data-ttu-id="57fe2-110">`Get-CimClass`コマンドレットは、特定の名前空間にある CIM クラスのリストを取得します。</span><span class="sxs-lookup"><span data-stu-id="57fe2-110">The `Get-CimClass` cmdlet retrieves a list of CIM classes in a specific namespace.</span></span> <span data-ttu-id="57fe2-111">クラス名が指定されていない場合、コマンドレットは名前空間内のすべてのクラスを返します。</span><span class="sxs-lookup"><span data-stu-id="57fe2-111">If there is no class name supplied, then the cmdlet returns all the classes in the namespace.</span></span> <span data-ttu-id="57fe2-112">Cim インスタンスとは異なり、CIM クラスには、取得元の cim セッションまたはコンピューター名は含まれません。</span><span class="sxs-lookup"><span data-stu-id="57fe2-112">Unlike a CIM instance, CIM classes do not contain the CIM session or computer name from which they are retrieved.</span></span>

## <span data-ttu-id="57fe2-113">例</span><span class="sxs-lookup"><span data-stu-id="57fe2-113">EXAMPLES</span></span>

### <span data-ttu-id="57fe2-114">例 1: すべてのクラス定義を取得する</span><span class="sxs-lookup"><span data-stu-id="57fe2-114">Example 1: Get all the class definitions</span></span>

<span data-ttu-id="57fe2-115">この例では、名前空間 **root/cimv2** の下にあるすべてのクラス定義を取得します。</span><span class="sxs-lookup"><span data-stu-id="57fe2-115">This example gets all the class definitions under the namespace **root/cimv2** .</span></span>

```powershell
Get-CimClass
```

### <span data-ttu-id="57fe2-116">例 2: 特定の名前を持つクラスを取得する</span><span class="sxs-lookup"><span data-stu-id="57fe2-116">Example 2: Get the classes with a specific name</span></span>

<span data-ttu-id="57fe2-117">この例では、名前に **disk** という単語を含むクラスを取得します。</span><span class="sxs-lookup"><span data-stu-id="57fe2-117">This example gets the classes that contain the word **disk** in their names.</span></span>

```powershell
Get-CimClass -ClassName *disk*
```

### <span data-ttu-id="57fe2-118">例 3: 特定のメソッド名を持つクラスを取得する</span><span class="sxs-lookup"><span data-stu-id="57fe2-118">Example 3: Get the classes with a specific method name</span></span>

<span data-ttu-id="57fe2-119">この例では、 **Win32** という名前で始まり、 **Term** で始まるメソッド名を持つクラスを取得します。</span><span class="sxs-lookup"><span data-stu-id="57fe2-119">This example gets the classes that start with the name **Win32** and have a method name that starts with **Term** .</span></span>

```powershell
Get-CimClass -ClassName Win32* -MethodName Term*
```

### <span data-ttu-id="57fe2-120">例 4: 特定のプロパティ名を持つクラスを取得する</span><span class="sxs-lookup"><span data-stu-id="57fe2-120">Example 4: Get the classes with a specific property name</span></span>

<span data-ttu-id="57fe2-121">この例では、 **Win32** という名前で始まり、 **Handle** という名前のプロパティを持つクラスを取得します。</span><span class="sxs-lookup"><span data-stu-id="57fe2-121">This example gets the classes that start with the name **Win32** and have a property named **Handle** .</span></span>

```powershell
Get-CimClass -ClassName Win32* -PropertyName Handle
```

### <span data-ttu-id="57fe2-122">例 5: 特定の修飾子名を持つクラスを取得する</span><span class="sxs-lookup"><span data-stu-id="57fe2-122">Example 5: Get the classes with a specific qualifier name</span></span>

<span data-ttu-id="57fe2-123">この例では、 **Win32** という名前で始まるクラスを取得し、名前に **Disk** という単語を含め、指定された修飾子の **関連付け** を使用します。</span><span class="sxs-lookup"><span data-stu-id="57fe2-123">This example gets the classes that start with the name **Win32** , contain the word **Disk** in their names and have the specified qualifier **Association** .</span></span>

```powershell
Get-CimClass -ClassName Win32*Disk* -QualifierName Association
```

### <span data-ttu-id="57fe2-124">例 6: 特定の名前空間からクラス定義を取得する</span><span class="sxs-lookup"><span data-stu-id="57fe2-124">Example 6: Get the class definitions from a specific namespace</span></span>

<span data-ttu-id="57fe2-125">この例では、指定された名前空間 **root/standardCimv2** から、名前に **Net** という単語を含むクラス定義を取得します。</span><span class="sxs-lookup"><span data-stu-id="57fe2-125">This example gets the class definitions that contain the word **Net** in their names from the specified namespace **root/standardCimv2** .</span></span>

```powershell
Get-CimClass -Namespace root/standardCimv2 -ClassName *Net*
```

### <span data-ttu-id="57fe2-126">例 7: リモートサーバーからクラス定義を取得する</span><span class="sxs-lookup"><span data-stu-id="57fe2-126">Example 7: Get the class definitions from a remote server</span></span>

<span data-ttu-id="57fe2-127">この例では、指定されたリモートサーバー **Server01** と **Server02** から、名前に **disk** という単語が含まれているクラス定義を取得します。</span><span class="sxs-lookup"><span data-stu-id="57fe2-127">This example gets the class definitions that contain the word **disk** in their names from the specified remote servers **Server01** and **Server02** .</span></span>

```powershell
Get-CimClass -ClassName *disk* -ComputerName Server01, Server02
```

### <span data-ttu-id="57fe2-128">例 8: CIM セッションを使用してクラスを取得する</span><span class="sxs-lookup"><span data-stu-id="57fe2-128">Example 8: Get the classes by using a CIM session</span></span>

```powershell
$s = New-CimSession -ComputerName Server01, Server02
Get-CimClass -ClassName *disk* -CimSession $s
```

<span data-ttu-id="57fe2-129">この一連のコマンドは、複数のコンピューターを含むセッションを作成し、コマンドレットを使用して変数に格納した `$s` `New-CimSession` 後、コマンドレットを使用してクラスを取得し `Get-CimClass` ます。</span><span class="sxs-lookup"><span data-stu-id="57fe2-129">This set of commands creates a session with multiple computers and stores it into a variable `$s` using the `New-CimSession` cmdlet, and then gets the classes using the `Get-CimClass` cmdlet.</span></span>

## <span data-ttu-id="57fe2-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="57fe2-130">PARAMETERS</span></span>

### <span data-ttu-id="57fe2-131">-CimSession</span><span class="sxs-lookup"><span data-stu-id="57fe2-131">-CimSession</span></span>

<span data-ttu-id="57fe2-132">リモート セッションまたはリモート コンピューターでコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="57fe2-132">Runs the cmdlet in a remote session or on a remote computer.</span></span> <span data-ttu-id="57fe2-133">またはコマンドレットの出力など、コンピューター名またはセッションオブジェクトを入力し `New-CimSession` `Get-CimSession` ます。</span><span class="sxs-lookup"><span data-stu-id="57fe2-133">Enter a computer name or a session object, such as the output of a `New-CimSession` or `Get-CimSession` cmdlet.</span></span> <span data-ttu-id="57fe2-134">既定値は、ローカル コンピューターで実行中の現在のセッションです。</span><span class="sxs-lookup"><span data-stu-id="57fe2-134">The default is the current session on the local computer.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: SessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="57fe2-135">-ClassName</span><span class="sxs-lookup"><span data-stu-id="57fe2-135">-ClassName</span></span>

<span data-ttu-id="57fe2-136">操作を実行する CIM クラスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="57fe2-136">Specifies the name of the CIM class for which to perform the operation.</span></span> <span data-ttu-id="57fe2-137">タブ補完を使用してクラスの一覧を参照することができます。これは、クラス名の一覧を提供するために、PowerShell がローカル WMI サーバーからクラスの一覧を取得するためです。</span><span class="sxs-lookup"><span data-stu-id="57fe2-137">You can use tab completion to browse the list of classes, because PowerShell gets a list of classes from the local WMI server to provide a list of class names.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="57fe2-138">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="57fe2-138">-ComputerName</span></span>

<span data-ttu-id="57fe2-139">CIM 操作を実行するコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="57fe2-139">Specifies the computer on which you want to run the CIM operation.</span></span> <span data-ttu-id="57fe2-140">完全修飾ドメイン名 (FQDN)、NetBIOS 名、または IP アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="57fe2-140">You can specify a fully qualified domain name (FQDN) a NetBIOS name, or an IP address.</span></span>

<span data-ttu-id="57fe2-141">このパラメーターを指定すると、コマンドレットは WsMan プロトコルを使用して、指定されたコンピューターへの一時的なセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="57fe2-141">If you specify this parameter, the cmdlet creates a temporary session to the specified computer using the WsMan protocol.</span></span>

<span data-ttu-id="57fe2-142">このパラメーターを指定しない場合、コマンドレットはコンポーネントオブジェクトモデル (COM) を使用してローカルコンピューター上で操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="57fe2-142">If you do not specify this parameter, the cmdlet performs the operation on the local computer using Component Object Model (COM).</span></span>

<span data-ttu-id="57fe2-143">複数の操作が同じコンピューター上で実行されている場合、CIM セッションを使用するとパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="57fe2-143">If multiple operations are being performed on the same computer, using a CIM session gives better performance.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerSet
Aliases: CN, ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="57fe2-144">-MethodName</span><span class="sxs-lookup"><span data-stu-id="57fe2-144">-MethodName</span></span>

<span data-ttu-id="57fe2-145">この名前と一致するメソッドを持つクラスを検索します。</span><span class="sxs-lookup"><span data-stu-id="57fe2-145">Finds the classes that have a method matching this name.</span></span> <span data-ttu-id="57fe2-146">このパラメーターには、ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="57fe2-146">You can use wildcard characters with this parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="57fe2-147">-Namespace</span><span class="sxs-lookup"><span data-stu-id="57fe2-147">-Namespace</span></span>

<span data-ttu-id="57fe2-148">CIM 操作の名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="57fe2-148">Specifies the namespace for CIM operation.</span></span> <span data-ttu-id="57fe2-149">既定の名前空間は **root/cimv2** です。</span><span class="sxs-lookup"><span data-stu-id="57fe2-149">The default namespace is **root/cimv2** .</span></span> <span data-ttu-id="57fe2-150">タブ補完を使用して名前空間の一覧を参照することができます。これは、名前空間の一覧を提供するために、PowerShell がローカル WMI サーバーから名前空間の一覧を取得するためです。</span><span class="sxs-lookup"><span data-stu-id="57fe2-150">You can use tab completion to browse the list of namespaces, because PowerShell gets a list of namespaces from the local WMI server to provide the list of namespaces.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="57fe2-151">-OperationTimeoutSec</span><span class="sxs-lookup"><span data-stu-id="57fe2-151">-OperationTimeoutSec</span></span>

<span data-ttu-id="57fe2-152">コマンドレットがコンピューターからの応答を待機する時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="57fe2-152">Specifies the amount of time that the cmdlet waits for a response from the computer.</span></span> <span data-ttu-id="57fe2-153">既定では、このパラメーターの値は0です。これは、コマンドレットがサーバーの既定のタイムアウト値を使用することを意味します。</span><span class="sxs-lookup"><span data-stu-id="57fe2-153">By default, the value of this parameter is 0, which means that the cmdlet uses the default timeout value for the server.</span></span>

<span data-ttu-id="57fe2-154">**Operationtimeoutsec** パラメーターが、堅牢な接続再試行タイムアウトの3分未満の値に設定されている場合、 **operationtimeoutsec** パラメーターの値を超えるネットワークエラーは復旧できません。これは、クライアントが再接続する前に、サーバー上の操作がタイムアウトになるためです。</span><span class="sxs-lookup"><span data-stu-id="57fe2-154">If the **OperationTimeoutSec** parameter is set to a value less than the robust connection retry timeout of 3 minutes, network failures that last more than the value of the **OperationTimeoutSec** parameter are not recoverable, because the operation on the server times out before the client can reconnect.</span></span>

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases: OT

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="57fe2-155">-PropertyName</span><span class="sxs-lookup"><span data-stu-id="57fe2-155">-PropertyName</span></span>

<span data-ttu-id="57fe2-156">この名前と一致するプロパティを持つクラスを検索します。</span><span class="sxs-lookup"><span data-stu-id="57fe2-156">Finds the classes which have a property matching this name.</span></span> <span data-ttu-id="57fe2-157">このパラメーターには、ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="57fe2-157">You can use wildcard characters with this parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="57fe2-158">-QualifierName</span><span class="sxs-lookup"><span data-stu-id="57fe2-158">-QualifierName</span></span>

<span data-ttu-id="57fe2-159">クラスをクラスレベルの修飾子名でフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="57fe2-159">Filters the classes by class level qualifier name.</span></span> <span data-ttu-id="57fe2-160">このパラメーターには、ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="57fe2-160">You can use wildcard characters with this parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="57fe2-161">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="57fe2-161">CommonParameters</span></span>

<span data-ttu-id="57fe2-162">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="57fe2-162">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="57fe2-163">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57fe2-163">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="57fe2-164">入力</span><span class="sxs-lookup"><span data-stu-id="57fe2-164">INPUTS</span></span>

### <span data-ttu-id="57fe2-165">なし</span><span class="sxs-lookup"><span data-stu-id="57fe2-165">None</span></span>

<span data-ttu-id="57fe2-166">このコマンドレットは、入力オブジェクトを受け入れません。</span><span class="sxs-lookup"><span data-stu-id="57fe2-166">This cmdlet accepts no input objects.</span></span>

## <span data-ttu-id="57fe2-167">出力</span><span class="sxs-lookup"><span data-stu-id="57fe2-167">OUTPUTS</span></span>

### <span data-ttu-id="57fe2-168">CimClass (Microsoft 管理)</span><span class="sxs-lookup"><span data-stu-id="57fe2-168">Microsoft.Management.Infrastructure.CimClass</span></span>

<span data-ttu-id="57fe2-169">このコマンドレットは、CIM クラスオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="57fe2-169">This cmdlet returns a CIM class object.</span></span>

## <span data-ttu-id="57fe2-170">注</span><span class="sxs-lookup"><span data-stu-id="57fe2-170">NOTES</span></span>

## <span data-ttu-id="57fe2-171">関連リンク</span><span class="sxs-lookup"><span data-stu-id="57fe2-171">RELATED LINKS</span></span>

[<span data-ttu-id="57fe2-172">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="57fe2-172">New-CimSession</span></span>](New-CimSession.md)
