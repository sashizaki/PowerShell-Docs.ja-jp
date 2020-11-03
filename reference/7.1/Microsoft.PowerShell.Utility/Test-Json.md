---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/19/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/test-json?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Json
ms.openlocfilehash: 79cf0d9a8107cbf843eba5c58e4b4e9ad30ad285
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211752"
---
# <span data-ttu-id="0e244-103">Test-Json</span><span class="sxs-lookup"><span data-stu-id="0e244-103">Test-Json</span></span>

## <span data-ttu-id="0e244-104">概要</span><span class="sxs-lookup"><span data-stu-id="0e244-104">SYNOPSIS</span></span>
<span data-ttu-id="0e244-105">文字列が有効な JSON ドキュメントであるかどうかをテストします</span><span class="sxs-lookup"><span data-stu-id="0e244-105">Tests whether a string is a valid JSON document</span></span>

## <span data-ttu-id="0e244-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0e244-106">SYNTAX</span></span>

### <span data-ttu-id="0e244-107">__AllParameterSets (既定値)</span><span class="sxs-lookup"><span data-stu-id="0e244-107">__AllParameterSets (Default)</span></span>
```
Test-Json [-Json] <String> [<CommonParameters>]
```

### <span data-ttu-id="0e244-108">SchemaString</span><span class="sxs-lookup"><span data-stu-id="0e244-108">SchemaString</span></span>
```
Test-Json [-Json] <String> [[-Schema] <String>] [<CommonParameters>]
```

### <span data-ttu-id="0e244-109">SchemaFile</span><span class="sxs-lookup"><span data-stu-id="0e244-109">SchemaFile</span></span>
```
Test-Json [-Json] <String> [-SchemaFile <String>] [<CommonParameters>]
```

## <span data-ttu-id="0e244-110">Description</span><span class="sxs-lookup"><span data-stu-id="0e244-110">DESCRIPTION</span></span>

<span data-ttu-id="0e244-111">この `Test-Json` コマンドレットは、文字列が有効な json (JavaScript Object Notation) ドキュメントであるかどうかをテストし、必要に応じて、指定されたスキーマに対して json ドキュメントを検証することができます。</span><span class="sxs-lookup"><span data-stu-id="0e244-111">The `Test-Json` cmdlet tests whether a string is a valid JavaScript Object Notation (JSON) document and can optionally verify that JSON document against a provided schema.</span></span>

<span data-ttu-id="0e244-112">検証された文字列をコマンドレットで使用すると、json `ConvertFrom-Json` 形式の文字列を json オブジェクトに変換できます。 json オブジェクトは、PowerShell で簡単に管理することも、json 入力にアクセスする別のプログラムや web サービスに送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="0e244-112">The verified string can then be used with the `ConvertFrom-Json` cmdlet convert a JSON-formatted string to a JSON object, which is easily managed in PowerShell or sent to another program or web service that access JSON input.</span></span>

<span data-ttu-id="0e244-113">多くの Web サイトが、サーバーと Web ベースのアプリ間の通信のために、XML ではなく JSON を使用してデータをシリアル化しています。</span><span class="sxs-lookup"><span data-stu-id="0e244-113">Many web sites use JSON instead of XML to serialize data for communication between servers and web-based apps.</span></span>

<span data-ttu-id="0e244-114">このコマンドレットは、PowerShell 6.1 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0e244-114">This cmdlet was introduced in PowerShell 6.1</span></span>

## <span data-ttu-id="0e244-115">例</span><span class="sxs-lookup"><span data-stu-id="0e244-115">EXAMPLES</span></span>

### <span data-ttu-id="0e244-116">例 1: オブジェクトが有効な JSON であるかどうかをテストする</span><span class="sxs-lookup"><span data-stu-id="0e244-116">Example 1: Test if an object is valid JSON</span></span>

<span data-ttu-id="0e244-117">この例では、入力文字列が有効な JSON ドキュメントであるかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="0e244-117">This example tests whether the input string is a valid JSON document.</span></span>

```powershell
"{'name': 'Ashley', 'age': 25}" | Test-Json
```

```Output
True
```

### <span data-ttu-id="0e244-118">例 2: 指定されたスキーマに対してオブジェクトをテストする</span><span class="sxs-lookup"><span data-stu-id="0e244-118">Example 2: Test an object against a provided schema</span></span>

<span data-ttu-id="0e244-119">この例では、JSON スキーマを含む文字列を取得し、それを入力文字列と比較します。</span><span class="sxs-lookup"><span data-stu-id="0e244-119">This example takes a string containing a JSON schema and compares it to an input string.</span></span>

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

<span data-ttu-id="0e244-120">この例では、スキーマには **age** の整数が必要ですが、テストした JSON 入力では文字列値が使用されているため、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="0e244-120">In this example, we get an error because the schema expects an integer for **age** but the JSON input we tested uses a string value instead.</span></span>

<span data-ttu-id="0e244-121">詳細については、「 [JSON スキーマ](https://json-schema.org/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e244-121">For more information, see [JSON Schema](https://json-schema.org/).</span></span>

### <span data-ttu-id="0e244-122">例 3: ファイルからスキーマに対してオブジェクトをテストする</span><span class="sxs-lookup"><span data-stu-id="0e244-122">Example 3: Test an object against a schema from file</span></span>

<span data-ttu-id="0e244-123">JSON スキーマでは、キーワードを使用して定義を参照でき `$ref` ます。</span><span class="sxs-lookup"><span data-stu-id="0e244-123">JSON schema can reference definitions using `$ref` keyword.</span></span> <span data-ttu-id="0e244-124">は、 `$ref` 別のファイルを参照する URI に解決できます。</span><span class="sxs-lookup"><span data-stu-id="0e244-124">The `$ref` can resolve to a URI that references another file.</span></span> <span data-ttu-id="0e244-125">`SchemaFile`パラメーターは json スキーマファイルへのリテラルパスを受け入れ、そのようなスキーマに対して json ファイルを検証できるようにします。</span><span class="sxs-lookup"><span data-stu-id="0e244-125">The `SchemaFile` parameter accepts literal path to the JSON schema file and allows JSON files to be validated against such schemas.</span></span>

<span data-ttu-id="0e244-126">この例では、を `schema.json` 参照するファイルがあり `definitions.json` ます。</span><span class="sxs-lookup"><span data-stu-id="0e244-126">In this example we have `schema.json` file which references `definitions.json`.</span></span>

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

<span data-ttu-id="0e244-127">詳細については、「 [複合スキーマの](https://json-schema.org/understanding-json-schema/structuring.html)構成」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e244-127">For more information, see [Structuring a complex schema](https://json-schema.org/understanding-json-schema/structuring.html).</span></span>

## <span data-ttu-id="0e244-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0e244-128">PARAMETERS</span></span>

### <span data-ttu-id="0e244-129">-Json</span><span class="sxs-lookup"><span data-stu-id="0e244-129">-Json</span></span>

<span data-ttu-id="0e244-130">有効性をテストする JSON 文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="0e244-130">Specifies the JSON string to test for validity.</span></span> <span data-ttu-id="0e244-131">文字列が格納されている変数を入力するか、文字列を取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="0e244-131">Enter a variable that contains the string, or type a command or expression that gets the string.</span></span> <span data-ttu-id="0e244-132">パイプを使用して文字列をにパイプすることもでき `Test-Json` ます。</span><span class="sxs-lookup"><span data-stu-id="0e244-132">You can also pipe a string to `Test-Json`.</span></span>

<span data-ttu-id="0e244-133">**Json** パラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="0e244-133">The **Json** parameter is required.</span></span>

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

### <span data-ttu-id="0e244-134">-スキーマ</span><span class="sxs-lookup"><span data-stu-id="0e244-134">-Schema</span></span>

<span data-ttu-id="0e244-135">JSON 入力を検証するスキーマを指定します。</span><span class="sxs-lookup"><span data-stu-id="0e244-135">Specifies a Schema to validate the JSON input against.</span></span> <span data-ttu-id="0e244-136">渡された場合 `Test-Json` は、Json 入力が **スキーマ** パラメーターで指定された仕様に準拠しているかどうかを検証し、 `$True` 入力が指定されたスキーマに準拠している場合にのみ、を返します。</span><span class="sxs-lookup"><span data-stu-id="0e244-136">If passed `Test-Json` will validate that the Json input conforms to the spec specified by the **Schema** parameter and return `$True` only if the input conforms to the provided Schema.</span></span>

<span data-ttu-id="0e244-137">詳細については、「 [JSON スキーマ](https://json-schema.org/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e244-137">For more information, see [JSON Schema](https://json-schema.org/).</span></span>

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

### <span data-ttu-id="0e244-138">-SchemaFile</span><span class="sxs-lookup"><span data-stu-id="0e244-138">-SchemaFile</span></span>

<span data-ttu-id="0e244-139">JSON 入力の検証に使用するスキーマファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="0e244-139">Specifies a schema file used to validate the JSON input.</span></span> <span data-ttu-id="0e244-140">使用する場合、は、 `Test-Json` `$True` JSON 入力が **schemafile** パラメーターで指定されたファイルで定義されているスキーマに準拠している場合にのみを返します。</span><span class="sxs-lookup"><span data-stu-id="0e244-140">When used, the `Test-Json` returns `$True` only if the JSON input conforms to the Schema defined in the file specified by the **SchemaFile** parameter.</span></span>

<span data-ttu-id="0e244-141">詳細については、「 [JSON スキーマ](https://json-schema.org/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e244-141">For more information, see [JSON Schema](https://json-schema.org/).</span></span>

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

### <span data-ttu-id="0e244-142">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="0e244-142">CommonParameters</span></span>

<span data-ttu-id="0e244-143">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="0e244-143">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0e244-144">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e244-144">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0e244-145">入力</span><span class="sxs-lookup"><span data-stu-id="0e244-145">INPUTS</span></span>

### <span data-ttu-id="0e244-146">System.String</span><span class="sxs-lookup"><span data-stu-id="0e244-146">System.String</span></span>

<span data-ttu-id="0e244-147">パイプを使用して、JSON 文字列をにパイプすることができ `Test-Json` ます。</span><span class="sxs-lookup"><span data-stu-id="0e244-147">You can pipe a JSON string to `Test-Json`.</span></span>

## <span data-ttu-id="0e244-148">出力</span><span class="sxs-lookup"><span data-stu-id="0e244-148">OUTPUTS</span></span>

### <span data-ttu-id="0e244-149">Boolean</span><span class="sxs-lookup"><span data-stu-id="0e244-149">Boolean</span></span>

## <span data-ttu-id="0e244-150">注</span><span class="sxs-lookup"><span data-stu-id="0e244-150">NOTES</span></span>

<span data-ttu-id="0e244-151">`Test-Json`コマンドレットは、 [Njsonschema クラス](https://github.com/RSuter/NJsonSchema)を使用して実装されます。</span><span class="sxs-lookup"><span data-stu-id="0e244-151">The `Test-Json` cmdlet is implemented by using the [NJsonSchema Class](https://github.com/RSuter/NJsonSchema).</span></span>

## <span data-ttu-id="0e244-152">関連リンク</span><span class="sxs-lookup"><span data-stu-id="0e244-152">RELATED LINKS</span></span>

<span data-ttu-id="0e244-153">[JavaScript および .NET での JavaScript Object Notation (JSON) の概要](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="0e244-153">[An Introduction to JavaScript Object Notation (JSON) in JavaScript and .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span></span>

[<span data-ttu-id="0e244-154">追加の JSON スキーマの詳細</span><span class="sxs-lookup"><span data-stu-id="0e244-154">Additional JSON Schema Details</span></span>](https://json-schema.org/)

[<span data-ttu-id="0e244-155">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="0e244-155">ConvertTo-Json</span></span>](ConvertTo-Json.md)

[<span data-ttu-id="0e244-156">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="0e244-156">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)

[<span data-ttu-id="0e244-157">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="0e244-157">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)
