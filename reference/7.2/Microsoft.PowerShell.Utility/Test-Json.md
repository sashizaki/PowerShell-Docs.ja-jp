---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/19/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/test-json?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Json
ms.openlocfilehash: a29eab449e567f78d1e54a6716ca91d87aa08405
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600106"
---
# <span data-ttu-id="e9313-102">Test-Json</span><span class="sxs-lookup"><span data-stu-id="e9313-102">Test-Json</span></span>

## <span data-ttu-id="e9313-103">概要</span><span class="sxs-lookup"><span data-stu-id="e9313-103">SYNOPSIS</span></span>
<span data-ttu-id="e9313-104">文字列が有効な JSON ドキュメントであるかどうかをテストします</span><span class="sxs-lookup"><span data-stu-id="e9313-104">Tests whether a string is a valid JSON document</span></span>

## <span data-ttu-id="e9313-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e9313-105">SYNTAX</span></span>

### <span data-ttu-id="e9313-106">__AllParameterSets (既定値)</span><span class="sxs-lookup"><span data-stu-id="e9313-106">__AllParameterSets (Default)</span></span>
```
Test-Json [-Json] <String> [<CommonParameters>]
```

### <span data-ttu-id="e9313-107">SchemaString</span><span class="sxs-lookup"><span data-stu-id="e9313-107">SchemaString</span></span>
```
Test-Json [-Json] <String> [[-Schema] <String>] [<CommonParameters>]
```

### <span data-ttu-id="e9313-108">SchemaFile</span><span class="sxs-lookup"><span data-stu-id="e9313-108">SchemaFile</span></span>
```
Test-Json [-Json] <String> [-SchemaFile <String>] [<CommonParameters>]
```

## <span data-ttu-id="e9313-109">Description</span><span class="sxs-lookup"><span data-stu-id="e9313-109">DESCRIPTION</span></span>

<span data-ttu-id="e9313-110">この `Test-Json` コマンドレットは、文字列が有効な json (JavaScript Object Notation) ドキュメントであるかどうかをテストし、必要に応じて、指定されたスキーマに対して json ドキュメントを検証することができます。</span><span class="sxs-lookup"><span data-stu-id="e9313-110">The `Test-Json` cmdlet tests whether a string is a valid JavaScript Object Notation (JSON) document and can optionally verify that JSON document against a provided schema.</span></span>

<span data-ttu-id="e9313-111">検証された文字列をコマンドレットで使用すると、json `ConvertFrom-Json` 形式の文字列を json オブジェクトに変換できます。 json オブジェクトは、PowerShell で簡単に管理することも、json 入力にアクセスする別のプログラムや web サービスに送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="e9313-111">The verified string can then be used with the `ConvertFrom-Json` cmdlet convert a JSON-formatted string to a JSON object, which is easily managed in PowerShell or sent to another program or web service that access JSON input.</span></span>

<span data-ttu-id="e9313-112">多くの Web サイトが、サーバーと Web ベースのアプリ間の通信のために、XML ではなく JSON を使用してデータをシリアル化しています。</span><span class="sxs-lookup"><span data-stu-id="e9313-112">Many web sites use JSON instead of XML to serialize data for communication between servers and web-based apps.</span></span>

<span data-ttu-id="e9313-113">このコマンドレットは、PowerShell 6.1 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="e9313-113">This cmdlet was introduced in PowerShell 6.1</span></span>

## <span data-ttu-id="e9313-114">例</span><span class="sxs-lookup"><span data-stu-id="e9313-114">EXAMPLES</span></span>

### <span data-ttu-id="e9313-115">例 1: オブジェクトが有効な JSON であるかどうかをテストする</span><span class="sxs-lookup"><span data-stu-id="e9313-115">Example 1: Test if an object is valid JSON</span></span>

<span data-ttu-id="e9313-116">この例では、入力文字列が有効な JSON ドキュメントであるかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="e9313-116">This example tests whether the input string is a valid JSON document.</span></span>

```powershell
"{'name': 'Ashley', 'age': 25}" | Test-Json
```

```Output
True
```

### <span data-ttu-id="e9313-117">例 2: 指定されたスキーマに対してオブジェクトをテストする</span><span class="sxs-lookup"><span data-stu-id="e9313-117">Example 2: Test an object against a provided schema</span></span>

<span data-ttu-id="e9313-118">この例では、JSON スキーマを含む文字列を取得し、それを入力文字列と比較します。</span><span class="sxs-lookup"><span data-stu-id="e9313-118">This example takes a string containing a JSON schema and compares it to an input string.</span></span>

```powershell
$schema = @'
{
  "definitions": {},
  "$schema": "http://json-schema.org/draft-07/schema#",
  "$id": "http://example.com/root.json",
  "type": "object",
  "title": "The Root Schema",
  "required": [
    "name",
    "age"
  ],
  "properties": {
    "name": {
      "$id": "#/properties/name",
      "type": "string",
      "title": "The Name Schema",
      "default": "",
      "examples": [
        "Ashley"
      ],
      "pattern": "^(.*)$"
    },
    "age": {
      "$id": "#/properties/age",
      "type": "integer",
      "title": "The Age Schema",
      "default": 0,
      "examples": [
        25
      ]
    }
  }
}
'@
"{'name': 'Ashley', 'age': '25'}" | Test-Json -Schema $schema
```

```Output
Test-Json : IntegerExpected: #/age
At line:1 char:37
+ "{'name': 'Ashley', 'age': '25'}" | Test-Json -Schema $schema
+                                     ~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : InvalidData: (:) [Test-Json], Exception
+ FullyQualifiedErrorId : InvalidJsonAgainstSchema,Microsoft.PowerShell.Commands.TestJsonCommand
False
```

<span data-ttu-id="e9313-119">この例では、スキーマには **age** の整数が必要ですが、テストした JSON 入力では文字列値が使用されているため、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="e9313-119">In this example, we get an error because the schema expects an integer for **age** but the JSON input we tested uses a string value instead.</span></span>

<span data-ttu-id="e9313-120">詳細については、「 [JSON スキーマ](https://json-schema.org/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9313-120">For more information, see [JSON Schema](https://json-schema.org/).</span></span>

### <span data-ttu-id="e9313-121">例 3: ファイルからスキーマに対してオブジェクトをテストする</span><span class="sxs-lookup"><span data-stu-id="e9313-121">Example 3: Test an object against a schema from file</span></span>

<span data-ttu-id="e9313-122">JSON スキーマでは、キーワードを使用して定義を参照でき `$ref` ます。</span><span class="sxs-lookup"><span data-stu-id="e9313-122">JSON schema can reference definitions using `$ref` keyword.</span></span> <span data-ttu-id="e9313-123">は、 `$ref` 別のファイルを参照する URI に解決できます。</span><span class="sxs-lookup"><span data-stu-id="e9313-123">The `$ref` can resolve to a URI that references another file.</span></span> <span data-ttu-id="e9313-124">`SchemaFile`パラメーターは json スキーマファイルへのリテラルパスを受け入れ、そのようなスキーマに対して json ファイルを検証できるようにします。</span><span class="sxs-lookup"><span data-stu-id="e9313-124">The `SchemaFile` parameter accepts literal path to the JSON schema file and allows JSON files to be validated against such schemas.</span></span>

<span data-ttu-id="e9313-125">この例では、を `schema.json` 参照するファイルがあり `definitions.json` ます。</span><span class="sxs-lookup"><span data-stu-id="e9313-125">In this example we have `schema.json` file which references `definitions.json`.</span></span>

```powershell
PS> Get-Content schema.json

{
  "description":"A person",
  "type":"object",
  "properties":{
    "name":{
      "$ref":"definitions.json#/definitions/name"
    },
    "hobbies":{
      "$ref":"definitions.json#/definitions/hobbies"
    }
  }
}

PS> Get-Content definitions.json

{
  "definitions":{
    "name":{
      "type":"string"
    },
    "hobbies":{
      "type":"array",
      "items":{
        "type":"string"
      }
    }
  }
}

'{"name": "James", "hobbies": [".NET", "Blogging"]}' | Test-Json -SchemaFile 'schema.json'
```

```Output
True
```

<span data-ttu-id="e9313-126">詳細については、「 [複合スキーマの](https://json-schema.org/understanding-json-schema/structuring.html)構成」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9313-126">For more information, see [Structuring a complex schema](https://json-schema.org/understanding-json-schema/structuring.html).</span></span>

## <span data-ttu-id="e9313-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e9313-127">PARAMETERS</span></span>

### <span data-ttu-id="e9313-128">-Json</span><span class="sxs-lookup"><span data-stu-id="e9313-128">-Json</span></span>

<span data-ttu-id="e9313-129">有効性をテストする JSON 文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="e9313-129">Specifies the JSON string to test for validity.</span></span> <span data-ttu-id="e9313-130">文字列が格納されている変数を入力するか、文字列を取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="e9313-130">Enter a variable that contains the string, or type a command or expression that gets the string.</span></span> <span data-ttu-id="e9313-131">パイプを使用して文字列をにパイプすることもでき `Test-Json` ます。</span><span class="sxs-lookup"><span data-stu-id="e9313-131">You can also pipe a string to `Test-Json`.</span></span>

<span data-ttu-id="e9313-132">**Json** パラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="e9313-132">The **Json** parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="e9313-133">-スキーマ</span><span class="sxs-lookup"><span data-stu-id="e9313-133">-Schema</span></span>

<span data-ttu-id="e9313-134">JSON 入力を検証するスキーマを指定します。</span><span class="sxs-lookup"><span data-stu-id="e9313-134">Specifies a Schema to validate the JSON input against.</span></span> <span data-ttu-id="e9313-135">渡された場合 `Test-Json` は、Json 入力が **スキーマ** パラメーターで指定された仕様に準拠しているかどうかを検証し、 `$True` 入力が指定されたスキーマに準拠している場合にのみ、を返します。</span><span class="sxs-lookup"><span data-stu-id="e9313-135">If passed `Test-Json` will validate that the Json input conforms to the spec specified by the **Schema** parameter and return `$True` only if the input conforms to the provided Schema.</span></span>

<span data-ttu-id="e9313-136">詳細については、「 [JSON スキーマ](https://json-schema.org/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9313-136">For more information, see [JSON Schema](https://json-schema.org/).</span></span>

```yaml
Type: System.String
Parameter Sets: SchemaString
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e9313-137">-SchemaFile</span><span class="sxs-lookup"><span data-stu-id="e9313-137">-SchemaFile</span></span>

<span data-ttu-id="e9313-138">JSON 入力の検証に使用するスキーマファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="e9313-138">Specifies a schema file used to validate the JSON input.</span></span> <span data-ttu-id="e9313-139">使用する場合、は、 `Test-Json` `$True` JSON 入力が **schemafile** パラメーターで指定されたファイルで定義されているスキーマに準拠している場合にのみを返します。</span><span class="sxs-lookup"><span data-stu-id="e9313-139">When used, the `Test-Json` returns `$True` only if the JSON input conforms to the Schema defined in the file specified by the **SchemaFile** parameter.</span></span>

<span data-ttu-id="e9313-140">詳細については、「 [JSON スキーマ](https://json-schema.org/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9313-140">For more information, see [JSON Schema](https://json-schema.org/).</span></span>

```yaml
Type: System.String
Parameter Sets: SchemaFile
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e9313-141">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="e9313-141">CommonParameters</span></span>

<span data-ttu-id="e9313-142">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="e9313-142">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e9313-143">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9313-143">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e9313-144">入力</span><span class="sxs-lookup"><span data-stu-id="e9313-144">INPUTS</span></span>

### <span data-ttu-id="e9313-145">System.String</span><span class="sxs-lookup"><span data-stu-id="e9313-145">System.String</span></span>

<span data-ttu-id="e9313-146">パイプを使用して、JSON 文字列をにパイプすることができ `Test-Json` ます。</span><span class="sxs-lookup"><span data-stu-id="e9313-146">You can pipe a JSON string to `Test-Json`.</span></span>

## <span data-ttu-id="e9313-147">出力</span><span class="sxs-lookup"><span data-stu-id="e9313-147">OUTPUTS</span></span>

### <span data-ttu-id="e9313-148">Boolean</span><span class="sxs-lookup"><span data-stu-id="e9313-148">Boolean</span></span>

## <span data-ttu-id="e9313-149">注</span><span class="sxs-lookup"><span data-stu-id="e9313-149">NOTES</span></span>

<span data-ttu-id="e9313-150">`Test-Json`コマンドレットは、 [Njsonschema クラス](https://github.com/RSuter/NJsonSchema)を使用して実装されます。</span><span class="sxs-lookup"><span data-stu-id="e9313-150">The `Test-Json` cmdlet is implemented by using the [NJsonSchema Class](https://github.com/RSuter/NJsonSchema).</span></span>

## <span data-ttu-id="e9313-151">関連リンク</span><span class="sxs-lookup"><span data-stu-id="e9313-151">RELATED LINKS</span></span>

<span data-ttu-id="e9313-152">[JavaScript および .NET での JavaScript Object Notation (JSON) の概要](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="e9313-152">[An Introduction to JavaScript Object Notation (JSON) in JavaScript and .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span></span>

[<span data-ttu-id="e9313-153">追加の JSON スキーマの詳細</span><span class="sxs-lookup"><span data-stu-id="e9313-153">Additional JSON Schema Details</span></span>](https://json-schema.org/)

[<span data-ttu-id="e9313-154">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="e9313-154">ConvertTo-Json</span></span>](ConvertTo-Json.md)

[<span data-ttu-id="e9313-155">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="e9313-155">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)

[<span data-ttu-id="e9313-156">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="e9313-156">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)
