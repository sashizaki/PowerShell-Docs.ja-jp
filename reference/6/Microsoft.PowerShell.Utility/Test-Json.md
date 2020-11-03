---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/19/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/test-json?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Json
ms.openlocfilehash: 618e00d8db5eadfa8658203ef435a23cfea25be3
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216203"
---
# <span data-ttu-id="3a904-103">Test-Json</span><span class="sxs-lookup"><span data-stu-id="3a904-103">Test-Json</span></span>

## <span data-ttu-id="3a904-104">概要</span><span class="sxs-lookup"><span data-stu-id="3a904-104">SYNOPSIS</span></span>
<span data-ttu-id="3a904-105">文字列が有効な JSON ドキュメントであるかどうかをテストします</span><span class="sxs-lookup"><span data-stu-id="3a904-105">Tests whether a string is a valid JSON document</span></span>

## <span data-ttu-id="3a904-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3a904-106">SYNTAX</span></span>

```
Test-Json [-Json] <string> [[-Schema] <string>] [<CommonParameters>]
```

## <span data-ttu-id="3a904-107">Description</span><span class="sxs-lookup"><span data-stu-id="3a904-107">DESCRIPTION</span></span>

<span data-ttu-id="3a904-108">この `Test-Json` コマンドレットは、文字列が有効な json (JavaScript Object Notation) ドキュメントであるかどうかをテストし、必要に応じて、指定されたスキーマに対して json ドキュメントを検証することができます。</span><span class="sxs-lookup"><span data-stu-id="3a904-108">The `Test-Json` cmdlet tests whether a string is a valid JavaScript Object Notation (JSON) document and can optionally verify that JSON document against a provided schema.</span></span>

<span data-ttu-id="3a904-109">検証された文字列をコマンドレットで使用すると、json `ConvertFrom-Json` 形式の文字列を json オブジェクトに変換できます。 json オブジェクトは、PowerShell で簡単に管理することも、json 入力にアクセスする別のプログラムや web サービスに送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="3a904-109">The verified string can then be used with the `ConvertFrom-Json` cmdlet convert a JSON-formatted string to a JSON object, which is easily managed in PowerShell or sent to another program or web service that access JSON input.</span></span>

<span data-ttu-id="3a904-110">多くの Web サイトが、サーバーと Web ベースのアプリ間の通信のために、XML ではなく JSON を使用してデータをシリアル化しています。</span><span class="sxs-lookup"><span data-stu-id="3a904-110">Many web sites use JSON instead of XML to serialize data for communication between servers and web-based apps.</span></span>

<span data-ttu-id="3a904-111">このコマンドレットは、PowerShell 6.1 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3a904-111">This cmdlet was introduced in PowerShell 6.1</span></span>

## <span data-ttu-id="3a904-112">例</span><span class="sxs-lookup"><span data-stu-id="3a904-112">EXAMPLES</span></span>

### <span data-ttu-id="3a904-113">例 1: オブジェクトが有効な JSON であるかどうかをテストする</span><span class="sxs-lookup"><span data-stu-id="3a904-113">Example 1: Test if an object is valid JSON</span></span>

<span data-ttu-id="3a904-114">この例では、入力文字列が有効な JSON ドキュメントであるかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="3a904-114">This example tests whether the input string is a valid JSON document.</span></span>

```powershell
"{'name': 'Ashley', 'age': 25}" | Test-Json
```

```Output
True
```

### <span data-ttu-id="3a904-115">例 2: 指定されたスキーマに対してオブジェクトをテストする</span><span class="sxs-lookup"><span data-stu-id="3a904-115">Example 2: Test an object against a provided schema</span></span>

<span data-ttu-id="3a904-116">この例では、JSON スキーマを含む文字列を取得し、それを入力文字列と比較します。</span><span class="sxs-lookup"><span data-stu-id="3a904-116">This example takes a string containing a JSON schema and compares it to an input string.</span></span>

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

<span data-ttu-id="3a904-117">この例では、スキーマには **age** の整数が必要ですが、テストした JSON 入力では文字列値が使用されているため、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="3a904-117">In this example, we get an error because the schema expects an integer for **age** but the JSON input we tested uses a string value instead.</span></span>

<span data-ttu-id="3a904-118">詳細については、「 [JSON スキーマ](https://json-schema.org/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a904-118">For more information, see [JSON Schema](https://json-schema.org/).</span></span>

## <span data-ttu-id="3a904-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3a904-119">PARAMETERS</span></span>

### <span data-ttu-id="3a904-120">-Json</span><span class="sxs-lookup"><span data-stu-id="3a904-120">-Json</span></span>

<span data-ttu-id="3a904-121">有効性をテストする JSON 文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="3a904-121">Specifies the JSON string to test for validity.</span></span> <span data-ttu-id="3a904-122">文字列が格納されている変数を入力するか、文字列を取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="3a904-122">Enter a variable that contains the string, or type a command or expression that gets the string.</span></span> <span data-ttu-id="3a904-123">パイプを使用して文字列をにパイプすることもでき `Test-Json` ます。</span><span class="sxs-lookup"><span data-stu-id="3a904-123">You can also pipe a string to `Test-Json`.</span></span>

<span data-ttu-id="3a904-124">**Json** パラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="3a904-124">The **Json** parameter is required.</span></span>

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

### <span data-ttu-id="3a904-125">-スキーマ</span><span class="sxs-lookup"><span data-stu-id="3a904-125">-Schema</span></span>

<span data-ttu-id="3a904-126">JSON 入力を検証するスキーマを指定します。</span><span class="sxs-lookup"><span data-stu-id="3a904-126">Specifies a Schema to validate the JSON input against.</span></span> <span data-ttu-id="3a904-127">渡された場合 `Test-Json` は、Json 入力が **スキーマ** パラメーターで指定された仕様に準拠しているかどうかを検証し、 `$True` 入力が指定されたスキーマに準拠している場合にのみ、を返します。</span><span class="sxs-lookup"><span data-stu-id="3a904-127">If passed `Test-Json` will validate that the Json input conforms to the spec specified by the **Schema** parameter and return `$True` only if the input conforms to the provided Schema.</span></span>

<span data-ttu-id="3a904-128">詳細については、「 [JSON スキーマ](https://json-schema.org/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a904-128">For more information, see [JSON Schema](https://json-schema.org/).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3a904-129">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="3a904-129">CommonParameters</span></span>

<span data-ttu-id="3a904-130">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="3a904-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3a904-131">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a904-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3a904-132">入力</span><span class="sxs-lookup"><span data-stu-id="3a904-132">INPUTS</span></span>

### <span data-ttu-id="3a904-133">System.String</span><span class="sxs-lookup"><span data-stu-id="3a904-133">System.String</span></span>

<span data-ttu-id="3a904-134">パイプを使用して、JSON 文字列をにパイプすることができ `Test-Json` ます。</span><span class="sxs-lookup"><span data-stu-id="3a904-134">You can pipe a JSON string to `Test-Json`.</span></span>

## <span data-ttu-id="3a904-135">出力</span><span class="sxs-lookup"><span data-stu-id="3a904-135">OUTPUTS</span></span>

### <span data-ttu-id="3a904-136">Boolean</span><span class="sxs-lookup"><span data-stu-id="3a904-136">Boolean</span></span>

## <span data-ttu-id="3a904-137">注</span><span class="sxs-lookup"><span data-stu-id="3a904-137">NOTES</span></span>

<span data-ttu-id="3a904-138">`Test-Json`コマンドレットは、 [Njsonschema クラス](https://github.com/RSuter/NJsonSchema)を使用して実装されます。</span><span class="sxs-lookup"><span data-stu-id="3a904-138">The `Test-Json` cmdlet is implemented by using the [NJsonSchema Class](https://github.com/RSuter/NJsonSchema).</span></span>

## <span data-ttu-id="3a904-139">関連リンク</span><span class="sxs-lookup"><span data-stu-id="3a904-139">RELATED LINKS</span></span>

<span data-ttu-id="3a904-140">[JavaScript および .NET での JavaScript Object Notation (JSON) の概要](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="3a904-140">[An Introduction to JavaScript Object Notation (JSON) in JavaScript and .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span></span>

[<span data-ttu-id="3a904-141">追加の JSON スキーマの詳細</span><span class="sxs-lookup"><span data-stu-id="3a904-141">Additional JSON Schema Details</span></span>](https://json-schema.org/)

[<span data-ttu-id="3a904-142">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="3a904-142">ConvertTo-Json</span></span>](ConvertTo-Json.md)

[<span data-ttu-id="3a904-143">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="3a904-143">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)

[<span data-ttu-id="3a904-144">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="3a904-144">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)
