---
description: '`enum`ステートメントは、列挙型を宣言するために使用されます。 列挙体は、列挙子リストと呼ばれる一連の名前付きラベルで構成される別個の型です。'
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 11/27/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_enum?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Enum
ms.openlocfilehash: 2b363f1d2dfcf45ec69d863a50f5f359ddf8e284
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221688"
---
# <a name="about-enum"></a><span data-ttu-id="273b2-105">列挙型について</span><span class="sxs-lookup"><span data-stu-id="273b2-105">About Enum</span></span>

## <a name="short-description"></a><span data-ttu-id="273b2-106">概要</span><span class="sxs-lookup"><span data-stu-id="273b2-106">SHORT DESCRIPTION</span></span>
<span data-ttu-id="273b2-107">`enum`ステートメントは、列挙型を宣言するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="273b2-107">The `enum` statement is used to declare an enumeration.</span></span> <span data-ttu-id="273b2-108">列挙体は、列挙子リストと呼ばれる一連の名前付きラベルで構成される別個の型です。</span><span class="sxs-lookup"><span data-stu-id="273b2-108">An enumeration is a distinct type that consists of a set of named labels called the enumerator list.</span></span>

## <a name="long-description"></a><span data-ttu-id="273b2-109">詳細説明</span><span class="sxs-lookup"><span data-stu-id="273b2-109">LONG DESCRIPTION</span></span>

<span data-ttu-id="273b2-110">`enum`ステートメントを使用すると、厳密に型指定されたラベルのセットを作成できます。</span><span class="sxs-lookup"><span data-stu-id="273b2-110">The `enum` statement allows you to create a strongly typed set of labels.</span></span> <span data-ttu-id="273b2-111">この列挙体は、解析やスペルミスの確認を必要とせずに、コード内で使用できます。</span><span class="sxs-lookup"><span data-stu-id="273b2-111">That enumeration can be used in the code without having to parse or check for spelling errors.</span></span>

<span data-ttu-id="273b2-112">列挙体は、内部的には0の開始値を持つ整数として表現されます。</span><span class="sxs-lookup"><span data-stu-id="273b2-112">Enumerations are internally represented as integers with a starting value of zero.</span></span> <span data-ttu-id="273b2-113">リストの最初のラベルには、0という値が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="273b2-113">The first label in the list is assigned the value zero.</span></span> <span data-ttu-id="273b2-114">残りのラベルは、連続した数値で割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="273b2-114">The remaining labels are assigned with consecutive numbers.</span></span>

<span data-ttu-id="273b2-115">定義では、ラベルに任意の整数値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="273b2-115">In the definition, labels can be given any integer value.</span></span> <span data-ttu-id="273b2-116">値が割り当てられていないラベルは、次の整数値を取得します。</span><span class="sxs-lookup"><span data-stu-id="273b2-116">Labels with no value assigned take the next integer value.</span></span>

## <a name="syntax-basic"></a><span data-ttu-id="273b2-117">構文 (基本)</span><span class="sxs-lookup"><span data-stu-id="273b2-117">Syntax (basic)</span></span>

```syntax
enum <enum-name> {
    <label> [= <int-value>]
    ...
}
```

## <a name="usage-example"></a><span data-ttu-id="273b2-118">使用例</span><span class="sxs-lookup"><span data-stu-id="273b2-118">Usage example</span></span>

<span data-ttu-id="273b2-119">次の例は、メディアファイルとして表示できるオブジェクトの列挙を示しています。</span><span class="sxs-lookup"><span data-stu-id="273b2-119">The following example shows an enumeration of objects that can be seen as media files.</span></span> <span data-ttu-id="273b2-120">定義により、、、の基になる値に明示的な値が割り当てられ `music` `picture` `video` ます。</span><span class="sxs-lookup"><span data-stu-id="273b2-120">The definition assigns explicit values to the underlying values of `music`, `picture`, `video`.</span></span> <span data-ttu-id="273b2-121">明示的な代入の直後にあるラベルは、次の整数値を取得します。</span><span class="sxs-lookup"><span data-stu-id="273b2-121">Labels immediately following an explicit assignment get the next integer value.</span></span> <span data-ttu-id="273b2-122">シノニムは、別のラベルに同じ値を割り当てることによって作成できます。、、 `ogg` `oga` `mogg` 、または `jpg` 、、 `jpeg` または `mpg` `mpeg` の構築された値を確認します。</span><span class="sxs-lookup"><span data-stu-id="273b2-122">Synonyms can be created by assigning the same value to another label; see the constructed values for: `ogg`, `oga`, `mogg`, or `jpg`, `jpeg`, or `mpg`, `mpeg`.</span></span>

```powershell
enum MediaTypes {
    unknown
    music = 10
    mp3
    aac
    ogg = 15
    oga = 15
    mogg = 15
    picture = 20
    jpg
    jpeg = 21
    png
    video = 40
    mpg
    mpeg = 41
    avi
    m4v
}
```

<span data-ttu-id="273b2-123">メソッドは、 `GetEnumNames()` 列挙体のラベルの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="273b2-123">The `GetEnumNames()` method returns the list of the labels for the enumeration.</span></span>

```powershell
[MediaTypes].GetEnumNames()
unknown
music
mp3
aac
ogg
oga
mogg
picture
jpg
jpeg
png
video
mpg
mpeg
avi
m4v
```

<span data-ttu-id="273b2-124">メソッドは、 `GetEnumValues()` 列挙体の値のリストを返します。</span><span class="sxs-lookup"><span data-stu-id="273b2-124">The `GetEnumValues()` method returns the list of the values for the enumeration.</span></span>

```powershell
[MediaTypes].GetEnumValues()
unknown
music
mp3
aac
oga
oga
oga
picture
jpeg
jpeg
png
video
mpeg
mpeg
avi
m4v
```

<span data-ttu-id="273b2-125">**注** : getenumnames () と Getenumnames () は、同じ結果を返すように見えます。</span><span class="sxs-lookup"><span data-stu-id="273b2-125">**Note** : GetEnumNames() and GetEnumValues() seem to return the same results.</span></span>
<span data-ttu-id="273b2-126">ただし、内部的には、PowerShell は値をラベルに変更します。</span><span class="sxs-lookup"><span data-stu-id="273b2-126">However, internally, PowerShell is changing values into labels.</span></span> <span data-ttu-id="273b2-127">リストを注意深く読んで `oga` `mogg` ください。とは ' get Names ' の結果の下に記載されてい `jpg` ますが、、、およびに対する "値の取得" のような出力の下にはありません `jpeg` `mpg` `mpeg` 。</span><span class="sxs-lookup"><span data-stu-id="273b2-127">Read the list carefully and you'll notice that `oga` and `mogg` are mentioned under the 'Get Names' results, but not under the 'Get Values' similar output for `jpg`, `jpeg`, and `mpg`, `mpeg`.</span></span>

```powershell
[MediaTypes].GetEnumName(15)
oga

[MediaTypes].GetEnumNames() | ForEach-Object {
  "{0,-10} {1}" -f $_,[int]([MediaTypes]::$_)
}
unknown    0
music      10
mp3        11
aac        12
ogg        15
oga        15
mogg       15
picture    20
jpg        21
jpeg       21
png        22
video      40
mpg        41
mpeg       41
avi        42
m4v        43
```

## <a name="enumerations-as-flags"></a><span data-ttu-id="273b2-128">フラグとしての列挙型</span><span class="sxs-lookup"><span data-stu-id="273b2-128">Enumerations as flags</span></span>

<span data-ttu-id="273b2-129">列挙は、ビットフラグのコレクションとして定義できます。</span><span class="sxs-lookup"><span data-stu-id="273b2-129">Enumerations can be defined as a collection of bit flags.</span></span>
<span data-ttu-id="273b2-130">ここで、列挙は、有効になっている1つ以上のフラグを表します。</span><span class="sxs-lookup"><span data-stu-id="273b2-130">Where, at any given point the enumeration represents one or more of those flags turned on.</span></span>

<span data-ttu-id="273b2-131">フラグが適切に機能するように列挙するには、各ラベルに2つの値の累乗が必要です。</span><span class="sxs-lookup"><span data-stu-id="273b2-131">For enumerations as flags to work properly, each label should have a power of two value.</span></span>

## <a name="syntax-flags"></a><span data-ttu-id="273b2-132">構文 (flags)</span><span class="sxs-lookup"><span data-stu-id="273b2-132">Syntax (flags)</span></span>

```syntax
[Flags()] enum <enum-name> {
    <label 0> [= 1]
    <label 1> [= 2]
    <label 2> [= 4]
    <label 3> [= 8]
    ...
}
```

## <a name="flags-usage-example"></a><span data-ttu-id="273b2-133">Flags の使用例</span><span class="sxs-lookup"><span data-stu-id="273b2-133">Flags usage example</span></span>

<span data-ttu-id="273b2-134">次の例では、 *Fileattributes* 列挙が作成されます。</span><span class="sxs-lookup"><span data-stu-id="273b2-134">In the following example the *FileAttributes* enumeration is created.</span></span>

```powershell
[Flags()] enum FileAttributes {
    Archive = 1
    Compressed = 2
    Device = 4
    Directory = 8
    Encrypted = 16
    Hidden = 32
}

[FileAttributes]$file1 = [FileAttributes]::Archive
[FileAttributes]$file1 +=[FileAttributes]::Compressed
[FileAttributes]$file1 +=  [FileAttributes]::Device
"file1 attributes are: $file1"

[FileAttributes]$file2 = [FileAttributes]28 ## => 16 + 8 + 4
"file2 attributes are: $file2"
```

```output
file1 attributes are: Archive, Compressed, Device
file2 attributes are: Device, Directory, Encrypted
```

<span data-ttu-id="273b2-135">特定のが設定されていることをテストするには、バイナリ比較演算子を使用し `-band` ます。</span><span class="sxs-lookup"><span data-stu-id="273b2-135">To test that a specific is set, you can use the binary comparison operator `-band`.</span></span> <span data-ttu-id="273b2-136">この例では、の値で **デバイス** と **アーカイブ** 属性をテストし `$file2` ます。</span><span class="sxs-lookup"><span data-stu-id="273b2-136">In this example, we test for the **Device** and the **Archive** attributes in the value of `$file2`.</span></span>

```
PS > ($file2 -band [FileAttributes]::Device) -eq [FileAttributes]::Device
True

PS > ($file2 -band [FileAttributes]::Archive) -eq [FileAttributes]::Archive
False
```
