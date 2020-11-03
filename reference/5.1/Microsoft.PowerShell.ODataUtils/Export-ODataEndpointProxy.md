---
external help file: Microsoft.PowerShell.ODataUtils-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.ODataUtils
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.odatautils/export-odataendpointproxy?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-ODataEndpointProxy
ms.openlocfilehash: 7550e2df319e5f195e65609ae29ebb00830ec8d2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214291"
---
# <span data-ttu-id="8840c-103">Export-ODataEndpointProxy</span><span class="sxs-lookup"><span data-stu-id="8840c-103">Export-ODataEndpointProxy</span></span>

## <span data-ttu-id="8840c-104">概要</span><span class="sxs-lookup"><span data-stu-id="8840c-104">SYNOPSIS</span></span>
<span data-ttu-id="8840c-105">OData エンドポイントを管理するコマンドレットを含むモジュールを生成します。</span><span class="sxs-lookup"><span data-stu-id="8840c-105">Generates a module that contains cmdlets to manage an OData endpoint.</span></span>

## <span data-ttu-id="8840c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8840c-106">SYNTAX</span></span>

```
Export-ODataEndpointProxy [-Uri] <String> [-OutputModule] <String> [[-MetadataUri] <String>]
 [[-Credential] <PSCredential>] [[-CreateRequestMethod] <String>] [[-UpdateRequestMethod] <String>]
 [[-CmdletAdapter] <String>] [[-ResourceNameMapping] <Hashtable>] [-Force] [[-CustomData] <Hashtable>]
 [-AllowClobber] [-AllowUnsecureConnection] [[-Headers] <Hashtable>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="8840c-107">Description</span><span class="sxs-lookup"><span data-stu-id="8840c-107">DESCRIPTION</span></span>

<span data-ttu-id="8840c-108">`Export-ODataEndpointProxy`コマンドレットは、odata エンドポイントのメタデータを使用して、その odata エンドポイントの管理に使用できるコマンドレットを含むモジュールを生成します。</span><span class="sxs-lookup"><span data-stu-id="8840c-108">The `Export-ODataEndpointProxy` cmdlet uses the metadata of an OData endpoint to generate a module that contains cmdlets you can use to manage that OData endpoint.</span></span> <span data-ttu-id="8840c-109">モジュールは、CDXML に基づいています。</span><span class="sxs-lookup"><span data-stu-id="8840c-109">The module is based on CDXML.</span></span> <span data-ttu-id="8840c-110">このコマンドレットによってモジュールが生成された後、 **OutputModule** パラメーターで指定したパスとファイル名にモジュールが保存されます。</span><span class="sxs-lookup"><span data-stu-id="8840c-110">After this cmdlet generates the module, it saves that module to the path and file name specified by the **OutputModule** parameter.</span></span>

<span data-ttu-id="8840c-111">`Export-ODataEndpointProxy` 作成、読み取り、更新、および削除 (CRUD) 操作、非 CRUD アクション、およびアソシエーション操作のためのコマンドレットを生成します。</span><span class="sxs-lookup"><span data-stu-id="8840c-111">`Export-ODataEndpointProxy` generates cmdlets for create, read, update, and delete (CRUD) operations, non-CRUD actions, and association manipulation.</span></span>

<span data-ttu-id="8840c-112">`Export-ODataEndpointProxy` エンドポイントリソースごとに1つの CDXML ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="8840c-112">`Export-ODataEndpointProxy` generates one CDXML file per endpoint resource.</span></span> <span data-ttu-id="8840c-113">これらの CDXML ファイルは、モジュールが生成された後で編集できます。</span><span class="sxs-lookup"><span data-stu-id="8840c-113">You can edit these CDXML files after the module is generated.</span></span> <span data-ttu-id="8840c-114">たとえば、Windows PowerShell コマンドレットの名前付けガイドラインに合わせてコマンドレットの名詞または動詞の名前を変更する場合は、ファイルを変更できます。</span><span class="sxs-lookup"><span data-stu-id="8840c-114">For example, if you want to change the noun or verb names of the cmdlets to align with Windows PowerShell cmdlet naming guidelines, you can modify the file.</span></span>

<span data-ttu-id="8840c-115">生成されたモジュールのすべてのコマンドレットには、モジュールが管理するエンドポイントに接続するために **Connectionuri** パラメーターを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="8840c-115">Every cmdlet in a generated module must include a **ConnectionURI** parameter in order to connect to the endpoint that the module manages.</span></span>

## <span data-ttu-id="8840c-116">例</span><span class="sxs-lookup"><span data-stu-id="8840c-116">EXAMPLES</span></span>

### <span data-ttu-id="8840c-117">例 1: 製品版 web サービスエンドポイントを管理するモジュールを生成する</span><span class="sxs-lookup"><span data-stu-id="8840c-117">Example 1: Generate a module to manage a retail web service endpoint</span></span>

```powershell
PS C:\> Export-ODataEndpointProxy -Uri 'http://services.odata.org/v3/(S(snyobsk1hhutkb2yulwldgf1))/odata/odata.svc' -MetadataUri 'http://services.odata.org/v3/(S(snyobsk1hhutkb2yulwldgf1))/odata/odata.svc/$metadata' -AllowUnsecureConnection -OutputModule 'C:\Users\user\GeneratedScript.psm1' -ResourceNameMapping @{Products = 'Merchandise'}
```

<span data-ttu-id="8840c-118">このコマンドは、リテールサービスエンドポイントを管理するモジュールを生成します。</span><span class="sxs-lookup"><span data-stu-id="8840c-118">This command generates a module to manage a retail service endpoint.</span></span> <span data-ttu-id="8840c-119">このコマンドでは、エンドポイントの URI とエンドポイントメタデータの URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="8840c-119">The command specifies the URI of the endpoint and the URI of the endpoint metadata.</span></span> <span data-ttu-id="8840c-120">また、このコマンドは、 **OutputModule** パラメーターの値として出力パスとスクリプトモジュール名も提供します。</span><span class="sxs-lookup"><span data-stu-id="8840c-120">The command also provides an output path and script module name as the value of the **OutputModule** parameter.</span></span> <span data-ttu-id="8840c-121">**ResourceNameMapping** パラメーターの値に対して、コマンドは、リソースコレクション名をコマンドレットセットの目的の名詞にマップするハッシュテーブルを提供します。</span><span class="sxs-lookup"><span data-stu-id="8840c-121">For the value of the **ResourceNameMapping** parameter, the command provides a hashtable that maps the resource collection name to the desired noun for the cmdlet set.</span></span> <span data-ttu-id="8840c-122">この例では、Products はリソースコレクションの名前、 **商品** は名詞です。</span><span class="sxs-lookup"><span data-stu-id="8840c-122">In this example, Products is the resource collection name and **Merchandise** is the noun.</span></span> <span data-ttu-id="8840c-123">HTTPS ではなく、SSL 以外のサイトへの接続を許可するには、 **Allowunsecureconnection** パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="8840c-123">To allow connections to non-SSL sites, HTTP, as opposed to HTTPS, add the **AllowUnsecureConnection** parameter.</span></span>

## <span data-ttu-id="8840c-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8840c-124">PARAMETERS</span></span>

### <span data-ttu-id="8840c-125">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="8840c-125">-AllowClobber</span></span>

<span data-ttu-id="8840c-126">このコマンドレットが既存のモジュールを置き換えることを示します。</span><span class="sxs-lookup"><span data-stu-id="8840c-126">Indicates that this cmdlet replaces an existing module.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 10
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8840c-127">-AllowUnsecureConnection</span><span class="sxs-lookup"><span data-stu-id="8840c-127">-AllowUnsecureConnection</span></span>

<span data-ttu-id="8840c-128">このモジュールが、SSL で保護されていない Uri に接続できることを示します。</span><span class="sxs-lookup"><span data-stu-id="8840c-128">Indicates that this module can connect to URIs that are not SSL-secured.</span></span> <span data-ttu-id="8840c-129">このモジュールは、HTTPS サイトに加えて HTTP サイトも管理できます。</span><span class="sxs-lookup"><span data-stu-id="8840c-129">The module can manage HTTP sites in addition to HTTPS sites.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 11
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8840c-130">--のアダプター</span><span class="sxs-lookup"><span data-stu-id="8840c-130">-CmdletAdapter</span></span>

<span data-ttu-id="8840c-131">コマンドレットアダプターを指定します。</span><span class="sxs-lookup"><span data-stu-id="8840c-131">Specifies the cmdlet adapter.</span></span> <span data-ttu-id="8840c-132">このパラメーターに指定できる値は、ODataAdapter と NetworkControllerAdapter です。</span><span class="sxs-lookup"><span data-stu-id="8840c-132">The acceptable values for this parameter are: ODataAdapter and NetworkControllerAdapter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: ODataAdapter, NetworkControllerAdapter, ODataV4Adapter

Required: False
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8840c-133">-CreateRequestMethod</span><span class="sxs-lookup"><span data-stu-id="8840c-133">-CreateRequestMethod</span></span>

<span data-ttu-id="8840c-134">要求メソッドを指定します。</span><span class="sxs-lookup"><span data-stu-id="8840c-134">Specifies the request method.</span></span> <span data-ttu-id="8840c-135">このパラメーターに指定できる値は、PUT、POST、PATCH です。</span><span class="sxs-lookup"><span data-stu-id="8840c-135">The acceptable values for this parameter are: PUT, POST, and PATCH.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Put, Post, Patch

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8840c-136">-Credential</span><span class="sxs-lookup"><span data-stu-id="8840c-136">-Credential</span></span>

<span data-ttu-id="8840c-137">OData エンドポイントへのアクセス権を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="8840c-137">Specifies a user account that has access to the OData endpoint.</span></span> <span data-ttu-id="8840c-138">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="8840c-138">The default value is the current user.</span></span> <span data-ttu-id="8840c-139">リモートコンピューターで windows Vista 以降のバージョンの Windows オペレーティングシステムが実行されている場合、コマンドレットによって資格情報の入力が求められます。</span><span class="sxs-lookup"><span data-stu-id="8840c-139">If a remote computer runs Windows Vista or a later release of the Windows operating system, the cmdlet prompts you for credentials.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8840c-140">-CustomData</span><span class="sxs-lookup"><span data-stu-id="8840c-140">-CustomData</span></span>

<span data-ttu-id="8840c-141">カスタムデータのハッシュテーブルを指定します。</span><span class="sxs-lookup"><span data-stu-id="8840c-141">Specifies a hash table of custom data.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 9
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8840c-142">-Force</span><span class="sxs-lookup"><span data-stu-id="8840c-142">-Force</span></span>

<span data-ttu-id="8840c-143">このコマンドレットが、既存のフォルダー内の同じ名前の既存の生成されたモジュールを上書きすることを示し `Modules` ます。</span><span class="sxs-lookup"><span data-stu-id="8840c-143">Indicates that this cmdlet overwrites an existing generated module of the same name in an existing `Modules` folder.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 8
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8840c-144">-ヘッダー</span><span class="sxs-lookup"><span data-stu-id="8840c-144">-Headers</span></span>

<span data-ttu-id="8840c-145">Web 要求のヘッダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="8840c-145">Specifies the headers of the web request.</span></span> <span data-ttu-id="8840c-146">ハッシュ テーブルまたは辞書を入力します。</span><span class="sxs-lookup"><span data-stu-id="8840c-146">Enter a hash table or dictionary.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 12
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8840c-147">-MetadataUri</span><span class="sxs-lookup"><span data-stu-id="8840c-147">-MetadataUri</span></span>

<span data-ttu-id="8840c-148">エンドポイントのメタデータの URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="8840c-148">Specifies the URI of the metadata of the endpoint.</span></span>

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

### <span data-ttu-id="8840c-149">-OutputModule</span><span class="sxs-lookup"><span data-stu-id="8840c-149">-OutputModule</span></span>

<span data-ttu-id="8840c-150">このコマンドレットによって生成されたプロキシコマンドのモジュールを保存するパスとモジュール名を指定します。</span><span class="sxs-lookup"><span data-stu-id="8840c-150">Specifies the path and module name to which this cmdlet saves the generated module of proxy commands.</span></span>

<span data-ttu-id="8840c-151">このコマンドレットは、バイナリモジュール、モジュールマニフェスト、およびフォーマットファイル (該当する場合) を指定されたフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="8840c-151">This cmdlet copies a binary module, module manifest, and formatting file, if applicable, to the specified folder.</span></span> <span data-ttu-id="8840c-152">モジュールの名前のみを指定すると、はその `Export-ODataEndpointProxy` モジュールをフォルダーに保存し `$home\Documents\WindowsPowerShell\Modules` ます。</span><span class="sxs-lookup"><span data-stu-id="8840c-152">If you specify only the name of the module, `Export-ODataEndpointProxy` saves the module in the `$home\Documents\WindowsPowerShell\Modules` folder.</span></span> <span data-ttu-id="8840c-153">パスを指定すると、コマンドレットによってそのパスにモジュールフォルダーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="8840c-153">If you specify a path, the cmdlet creates the module folder in that path.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8840c-154">-ResourceNameMapping</span><span class="sxs-lookup"><span data-stu-id="8840c-154">-ResourceNameMapping</span></span>

<span data-ttu-id="8840c-155">生成されたコマンドレットをカスタマイズできるようにするマッピングを含むハッシュテーブルを指定します。</span><span class="sxs-lookup"><span data-stu-id="8840c-155">Specifies a hashtable that contains mappings that let you customize the generated cmdlets.</span></span> <span data-ttu-id="8840c-156">このハッシュテーブルでは、リソースコレクション名はキーです。</span><span class="sxs-lookup"><span data-stu-id="8840c-156">In this hashtable, the resource collection name is the key.</span></span> <span data-ttu-id="8840c-157">目的のコマンドレットの名詞は、値です。</span><span class="sxs-lookup"><span data-stu-id="8840c-157">The desired cmdlet noun is the value.</span></span>

<span data-ttu-id="8840c-158">たとえば、ハッシュテーブルでは、 `@{Products = 'Merchandise'}` **Products** はキーとして機能するリソースコレクション名です。</span><span class="sxs-lookup"><span data-stu-id="8840c-158">For example, in the hash table `@{Products = 'Merchandise'}`, **Products** is the resource collection name that serves as the key.</span></span> <span data-ttu-id="8840c-159">**商品** は、結果のコマンドレットの名詞です。</span><span class="sxs-lookup"><span data-stu-id="8840c-159">**Merchandise** is the resulting cmdlet noun.</span></span> <span data-ttu-id="8840c-160">生成されたコマンドレット名は、Windows PowerShell コマンドレットの名前付けガイドラインに一致しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="8840c-160">The generated cmdlet names might not align to Windows PowerShell cmdlet naming guidelines.</span></span> <span data-ttu-id="8840c-161">このコマンドレットでモジュールを作成した後で、リソースの CDXML ファイルを変更してコマンドレット名を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="8840c-161">You can modify the resource CDXML file to change the cmdlet names after this cmdlet creates the module.</span></span> <span data-ttu-id="8840c-162">詳細については、「 [開発に関する](/powershell/scripting/developer/cmdlet/strongly-encouraged-development-guidelines)推奨事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8840c-162">For more information, see [Strongly Encouraged Development Guidelines](/powershell/scripting/developer/cmdlet/strongly-encouraged-development-guidelines).</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 7
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8840c-163">-UpdateRequestMethod</span><span class="sxs-lookup"><span data-stu-id="8840c-163">-UpdateRequestMethod</span></span>

<span data-ttu-id="8840c-164">更新要求メソッドを指定します。</span><span class="sxs-lookup"><span data-stu-id="8840c-164">Specifies the update request method.</span></span> <span data-ttu-id="8840c-165">このパラメーターに指定できる値は、PUT、POST、PATCH です。</span><span class="sxs-lookup"><span data-stu-id="8840c-165">The acceptable values for this parameter are: PUT, POST, and PATCH.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Put, Post, Patch

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8840c-166">-Uri</span><span class="sxs-lookup"><span data-stu-id="8840c-166">-Uri</span></span>

<span data-ttu-id="8840c-167">エンドポイントの URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="8840c-167">Specifies the URI of the endpoint.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="8840c-168">-Confirm</span><span class="sxs-lookup"><span data-stu-id="8840c-168">-Confirm</span></span>

<span data-ttu-id="8840c-169">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8840c-169">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8840c-170">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="8840c-170">-WhatIf</span></span>

<span data-ttu-id="8840c-171">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="8840c-171">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="8840c-172">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="8840c-172">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8840c-173">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="8840c-173">CommonParameters</span></span>

<span data-ttu-id="8840c-174">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="8840c-174">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8840c-175">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8840c-175">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8840c-176">入力</span><span class="sxs-lookup"><span data-stu-id="8840c-176">INPUTS</span></span>

## <span data-ttu-id="8840c-177">出力</span><span class="sxs-lookup"><span data-stu-id="8840c-177">OUTPUTS</span></span>

## <span data-ttu-id="8840c-178">注</span><span class="sxs-lookup"><span data-stu-id="8840c-178">NOTES</span></span>

## <span data-ttu-id="8840c-179">関連リンク</span><span class="sxs-lookup"><span data-stu-id="8840c-179">RELATED LINKS</span></span>

<span data-ttu-id="8840c-180">[OData ライブラリ](https://technet.microsoft.com/windowsserver/hh525392(v=vs.85).aspx?f=255&MSPPError=-2147217396)</span><span class="sxs-lookup"><span data-stu-id="8840c-180">[OData Library](https://technet.microsoft.com/windowsserver/hh525392(v=vs.85).aspx?f=255&MSPPError=-2147217396)</span></span>

[<span data-ttu-id="8840c-181">OData プロトコルとは</span><span class="sxs-lookup"><span data-stu-id="8840c-181">What is the OData Protocol?</span></span>](https://www.odata.org/)

[<span data-ttu-id="8840c-182">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="8840c-182">Invoke-RestMethod</span></span>](../Microsoft.PowerShell.Utility/Invoke-RestMethod.md)
