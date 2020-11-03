---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/30/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-webserviceproxy?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-WebServiceProxy
ms.openlocfilehash: aea656bc8ad4416673a7abb7d32a58d45dd3cc4f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214600"
---
# <span data-ttu-id="ca7d5-103">New-WebServiceProxy</span><span class="sxs-lookup"><span data-stu-id="ca7d5-103">New-WebServiceProxy</span></span>

## <span data-ttu-id="ca7d5-104">概要</span><span class="sxs-lookup"><span data-stu-id="ca7d5-104">SYNOPSIS</span></span>
<span data-ttu-id="ca7d5-105">PowerShell で Web サービスを使用および管理できる Web サービスプロキシオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="ca7d5-105">Creates a Web service proxy object that lets you use and manage the Web service in PowerShell.</span></span>

## <span data-ttu-id="ca7d5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ca7d5-106">SYNTAX</span></span>

### <span data-ttu-id="ca7d5-107">NoCredentials (既定値)</span><span class="sxs-lookup"><span data-stu-id="ca7d5-107">NoCredentials (Default)</span></span>

```
New-WebServiceProxy [-Uri] <Uri> [[-Class] <String>] [[-Namespace] <String>] [<CommonParameters>]
```

### <span data-ttu-id="ca7d5-108">資格情報</span><span class="sxs-lookup"><span data-stu-id="ca7d5-108">Credential</span></span>

```
New-WebServiceProxy [-Uri] <Uri> [[-Class] <String>] [[-Namespace] <String>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### <span data-ttu-id="ca7d5-109">UseDefaultCredential</span><span class="sxs-lookup"><span data-stu-id="ca7d5-109">UseDefaultCredential</span></span>

```
New-WebServiceProxy [-Uri] <Uri> [[-Class] <String>] [[-Namespace] <String>] [-UseDefaultCredential]
 [<CommonParameters>]
```

## <span data-ttu-id="ca7d5-110">Description</span><span class="sxs-lookup"><span data-stu-id="ca7d5-110">DESCRIPTION</span></span>

<span data-ttu-id="ca7d5-111">`New-WebServiceProxy`コマンドレットを使用すると、PowerShell で Web サービスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ca7d5-111">The `New-WebServiceProxy` cmdlet lets you use a Web service in PowerShell.</span></span> <span data-ttu-id="ca7d5-112">コマンドレットは、Web サービスに接続し、PowerShell に Web サービスプロキシオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="ca7d5-112">The cmdlet connects to a Web service and creates a Web service proxy object in PowerShell.</span></span> <span data-ttu-id="ca7d5-113">プロキシ オブジェクトを使用して Web サービスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="ca7d5-113">You can use the proxy object to manage the Web service.</span></span>

<span data-ttu-id="ca7d5-114">Web サービスは、特にインターネット経由でネットワーク経由でデータを交換する XML ベースのプログラムです。</span><span class="sxs-lookup"><span data-stu-id="ca7d5-114">A Web service is an XML-based program that exchanges data over a network, especially over the Internet.</span></span> <span data-ttu-id="ca7d5-115">Microsoft .NET Framework には Web サービス プロキシ オブジェクトが用意されており、Web サービスを .NET Framework オブジェクトとして表します。</span><span class="sxs-lookup"><span data-stu-id="ca7d5-115">The Microsoft .NET Framework provides Web service proxy objects that represent the Web service as a .NET Framework object.</span></span>

## <span data-ttu-id="ca7d5-116">例</span><span class="sxs-lookup"><span data-stu-id="ca7d5-116">EXAMPLES</span></span>

### <span data-ttu-id="ca7d5-117">例 1: Web サービスのプロキシを作成する</span><span class="sxs-lookup"><span data-stu-id="ca7d5-117">Example 1: Create a proxy for a Web service</span></span>

<span data-ttu-id="ca7d5-118">この例では、Windows PowerShell で電卓 Web サービスの .NET Framework プロキシを作成します。</span><span class="sxs-lookup"><span data-stu-id="ca7d5-118">This example creates a .NET Framework proxy of the calculator Web service in Windows PowerShell.</span></span>

```powershell
$calc = New-WebServiceProxy -Uri "http://www.dneonline.com/calculator.asmx?wsdl"
```

### <span data-ttu-id="ca7d5-119">例 2: Web サービスのプロキシを作成し、名前空間とクラスを指定する</span><span class="sxs-lookup"><span data-stu-id="ca7d5-119">Example 2: Create a proxy for a Web service and specify namespace and class</span></span>

<span data-ttu-id="ca7d5-120">この例では、コマンドレットを使用して、 `New-WebServiceProxy` 電卓 Web サービスの .NET Framework プロキシを作成します。</span><span class="sxs-lookup"><span data-stu-id="ca7d5-120">This example uses the `New-WebServiceProxy` cmdlet to create a .NET Framework proxy of the calculator Web service.</span></span>

```powershell
$URI = "http://www.dneonline.com/calculator.asmx?wsdl"
$calc = New-WebServiceProxy -Uri $URI -Namespace "WSProxy" -Class "Calculator"
```

<span data-ttu-id="ca7d5-121">このコマンドは、 **uri** パラメーターを使用して uri を指定し、 **名前空間** と **クラス** パラメーターを使用してオブジェクトの名前空間とクラスを指定します。</span><span class="sxs-lookup"><span data-stu-id="ca7d5-121">The command uses the **Uri** parameter to specify the URI and the **Namespace** and **Class** parameters to specify the namespace and class of the object.</span></span>

### <span data-ttu-id="ca7d5-122">例 3: Web サービスプロキシのメソッドを表示する</span><span class="sxs-lookup"><span data-stu-id="ca7d5-122">Example 3: Display methods of a Web service proxy</span></span>

```powershell
$calc | Get-Member -MemberType method
```

```Output
   TypeName: WSProxy.Calculator

Name                      MemberType Definition
----                      ---------- ----------
Abort                     Method     void Abort()
Add                       Method     int Add(int intA, int intB)
AddAsync                  Method     void AddAsync(int intA, int intB), void AddAsync(int intA,
BeginAdd                  Method     System.IAsyncResult BeginAdd(int intA, int intB, System.Asy
BeginDivide               Method     System.IAsyncResult BeginDivide(int intA, int intB, System.
BeginMultiply             Method     System.IAsyncResult BeginMultiply(int intA, int intB, Syste
BeginSubtract             Method     System.IAsyncResult BeginSubtract(int intA, int intB, Syste
CancelAsync               Method     void CancelAsync(System.Object userState)
CreateObjRef              Method     System.Runtime.Remoting.ObjRef CreateObjRef(type requestedT
Discover                  Method     void Discover()
Dispose                   Method     void Dispose(), void IDisposable.Dispose()
Divide                    Method     int Divide(int intA, int intB)
DivideAsync               Method     void DivideAsync(int intA, int intB), void DivideAsync(int
EndAdd                    Method     int EndAdd(System.IAsyncResult asyncResult)
EndDivide                 Method     int EndDivide(System.IAsyncResult asyncResult)
EndMultiply               Method     int EndMultiply(System.IAsyncResult asyncResult)
EndSubtract               Method     int EndSubtract(System.IAsyncResult asyncResult)
Equals                    Method     bool Equals(System.Object obj)
GetHashCode               Method     int GetHashCode()
GetLifetimeService        Method     System.Object GetLifetimeService()
GetType                   Method     type GetType()
InitializeLifetimeService Method     System.Object InitializeLifetimeService()
Multiply                  Method     int Multiply(int intA, int intB)
MultiplyAsync             Method     void MultiplyAsync(int intA, int intB), void MultiplyAsync(
Subtract                  Method     int Subtract(int intA, int intB)
SubtractAsync             Method     void SubtractAsync(int intA, int intB), void SubtractAsync(
ToString                  Method     string ToString()
```

<span data-ttu-id="ca7d5-123">この例では、コマンドレットを使用して、 `Get-Member` 変数内の Web サービスプロキシオブジェクトのメソッドを表示し `$calc` ます。</span><span class="sxs-lookup"><span data-stu-id="ca7d5-123">This example uses the `Get-Member` cmdlet to display the methods of the Web service proxy object in the `$calc` variable.</span></span> <span data-ttu-id="ca7d5-124">次の例では、これらのメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="ca7d5-124">We uses these methods in the following example.</span></span>

<span data-ttu-id="ca7d5-125">プロキシオブジェクトの **TypeName** (webserviceproxy) には、前の例で指定した名前空間とクラス名が反映されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ca7d5-125">Notice that the **TypeName** of the proxy object, WebServiceProxy, reflects the namespace and class names that were specified in the previous example.</span></span>

### <span data-ttu-id="ca7d5-126">例 4: Web サービスプロキシを使用する</span><span class="sxs-lookup"><span data-stu-id="ca7d5-126">Example 4: Use a Web service proxy</span></span>

```powershell
PS> $calc.Multiply(6,7)
42
```

<span data-ttu-id="ca7d5-127">この例では、変数に格納されている Web サービスプロキシを使用し `$calc` ます。</span><span class="sxs-lookup"><span data-stu-id="ca7d5-127">This example uses the Web service proxy stored in the `$calc` variable.</span></span> <span data-ttu-id="ca7d5-128">このコマンドは、プロキシの **乗算** メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="ca7d5-128">The command uses the **Multiply** method of the proxy.</span></span>

## <span data-ttu-id="ca7d5-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ca7d5-129">PARAMETERS</span></span>

### <span data-ttu-id="ca7d5-130">-クラス</span><span class="sxs-lookup"><span data-stu-id="ca7d5-130">-Class</span></span>

<span data-ttu-id="ca7d5-131">コマンドレットが Web サービス用に作成したプロキシ クラスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ca7d5-131">Specifies a name for the proxy class that the cmdlet creates for the Web service.</span></span> <span data-ttu-id="ca7d5-132">このパラメーターの値を **Namespace** パラメーターと共に使用して、クラスの完全修飾名を指定します。</span><span class="sxs-lookup"><span data-stu-id="ca7d5-132">The value of this parameter is used together with the **Namespace** parameter to provide a fully qualified name for the class.</span></span> <span data-ttu-id="ca7d5-133">既定値は、Uniform Resource Identifier (URI) から生成されます。</span><span class="sxs-lookup"><span data-stu-id="ca7d5-133">The default value is generated from the Uniform Resource Identifier (URI).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: FileName, FN

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ca7d5-134">-Credential</span><span class="sxs-lookup"><span data-stu-id="ca7d5-134">-Credential</span></span>

<span data-ttu-id="ca7d5-135">この処理を実行するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="ca7d5-135">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="ca7d5-136">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="ca7d5-136">The default is the current user.</span></span> <span data-ttu-id="ca7d5-137">これは、 **UseDefaultCredential** パラメーターの使用に代わる方法です。</span><span class="sxs-lookup"><span data-stu-id="ca7d5-137">This is an alternative to using the **UseDefaultCredential** parameter.</span></span>

<span data-ttu-id="ca7d5-138">User01 や Domain01\user01」などのユーザー名を入力するか、コマンドレットによって生成されるような **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="ca7d5-138">Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="ca7d5-139">ユーザー名を入力すると、このコマンドレットによってパスワードの入力が求められます。</span><span class="sxs-lookup"><span data-stu-id="ca7d5-139">If you type a user name, this cmdlet prompts you for a password.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Credential
Aliases: Cred

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ca7d5-140">-Namespace</span><span class="sxs-lookup"><span data-stu-id="ca7d5-140">-Namespace</span></span>

<span data-ttu-id="ca7d5-141">新しいクラスの名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="ca7d5-141">Specifies a namespace for the new class.</span></span>

<span data-ttu-id="ca7d5-142">このパラメーターの値 **は、クラスパラメーターの** 値と共に使用して、クラスの完全修飾名を生成します。</span><span class="sxs-lookup"><span data-stu-id="ca7d5-142">The value of this parameter is used together with the value of the **Class** parameter to generate a fully qualified name for the class.</span></span> <span data-ttu-id="ca7d5-143">既定値は、URI から生成された型に加えて、" **Microsoft. PowerShell. NewWebserviceProxy. autogenerated types** " になります。</span><span class="sxs-lookup"><span data-stu-id="ca7d5-143">The default value is **Microsoft.PowerShell.Commands.NewWebserviceProxy.AutogeneratedTypes** plus a type that is generated from the URI.</span></span>

<span data-ttu-id="ca7d5-144">名前 **空間** パラメーターの値を設定して、同じ名前を持つ複数の Web サービスにアクセスできるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="ca7d5-144">You can set the value of the **Namespace** parameter so that you can access multiple Web services that have the same name.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: NS

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ca7d5-145">-Uri</span><span class="sxs-lookup"><span data-stu-id="ca7d5-145">-Uri</span></span>

<span data-ttu-id="ca7d5-146">Web サービスの URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="ca7d5-146">Specifies the URI of the Web service.</span></span> <span data-ttu-id="ca7d5-147">サービスの説明が含まれているファイルの URI またはパスとファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="ca7d5-147">Enter a URI or the path and filename of a file that contains a service description.</span></span>

<span data-ttu-id="ca7d5-148">URI は、サービスの `.asmx` 説明を返すページまたはページを返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca7d5-148">The URI must return an `.asmx` page or to a page that returns a service description.</span></span> <span data-ttu-id="ca7d5-149">ASP.NET を使用して作成された Web サービスのサービスの説明を返すには、「?」と追加します。WSDL "を Web サービスの URL (など `http://www.contoso.com/MyWebService.asmx?WSDL` ) にします。</span><span class="sxs-lookup"><span data-stu-id="ca7d5-149">To return a service description of a Web service that was created using ASP.NET, append "?WSDL" to the URL of the Web service (for example, `http://www.contoso.com/MyWebService.asmx?WSDL`).</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases: WL, WSDL, Path

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ca7d5-150">-UseDefaultCredential</span><span class="sxs-lookup"><span data-stu-id="ca7d5-150">-UseDefaultCredential</span></span>

<span data-ttu-id="ca7d5-151">このコマンドレットが既定の資格情報を使用することを示します。</span><span class="sxs-lookup"><span data-stu-id="ca7d5-151">Indicates that this cmdlet uses the default credential.</span></span> <span data-ttu-id="ca7d5-152">このコマンドレットは、結果として得られるプロキシオブジェクトの **Usedefaultcredential** プロパティを True に設定します。</span><span class="sxs-lookup"><span data-stu-id="ca7d5-152">This cmdlet sets the **UseDefaultCredential** property in the resulting proxy object to True.</span></span> <span data-ttu-id="ca7d5-153">これは、 **Credential** パラメーターの使用に代わる方法です。</span><span class="sxs-lookup"><span data-stu-id="ca7d5-153">This is an alternative to using the **Credential** parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: UseDefaultCredential
Aliases: UDC

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ca7d5-154">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="ca7d5-154">CommonParameters</span></span>

<span data-ttu-id="ca7d5-155">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="ca7d5-155">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ca7d5-156">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca7d5-156">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ca7d5-157">入力</span><span class="sxs-lookup"><span data-stu-id="ca7d5-157">INPUTS</span></span>

### <span data-ttu-id="ca7d5-158">なし</span><span class="sxs-lookup"><span data-stu-id="ca7d5-158">None</span></span>

<span data-ttu-id="ca7d5-159">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="ca7d5-159">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="ca7d5-160">出力</span><span class="sxs-lookup"><span data-stu-id="ca7d5-160">OUTPUTS</span></span>

### <span data-ttu-id="ca7d5-161">Web サービスプロキシオブジェクト</span><span class="sxs-lookup"><span data-stu-id="ca7d5-161">A Web service proxy object</span></span>

<span data-ttu-id="ca7d5-162">このコマンドレットは、Web サービスプロキシオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="ca7d5-162">This cmdlet returns a Web service proxy object.</span></span> <span data-ttu-id="ca7d5-163">オブジェクトの名前空間とクラスは、コマンドのパラメーターによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="ca7d5-163">The namespace and class of the object are determined by the parameters of the command.</span></span> <span data-ttu-id="ca7d5-164">既定値は入力 URI から生成されます。</span><span class="sxs-lookup"><span data-stu-id="ca7d5-164">The default is generated from the input URI.</span></span>

## <span data-ttu-id="ca7d5-165">注</span><span class="sxs-lookup"><span data-stu-id="ca7d5-165">NOTES</span></span>

<span data-ttu-id="ca7d5-166">`New-WebServiceProxy` は、 **システムの .net の WebClient** クラスを使用して、指定された Web サービスを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="ca7d5-166">`New-WebServiceProxy` uses the **System.Net.WebClient** class to load the specified Web service.</span></span>

## <span data-ttu-id="ca7d5-167">関連リンク</span><span class="sxs-lookup"><span data-stu-id="ca7d5-167">RELATED LINKS</span></span>

[<span data-ttu-id="ca7d5-168">New-Service</span><span class="sxs-lookup"><span data-stu-id="ca7d5-168">New-Service</span></span>](New-Service.md)
