---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 11/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/update-list?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-List
ms.openlocfilehash: eccee5ad302395116430006ed4dc0395946696b6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213624"
---
# <span data-ttu-id="7225d-103">Update-List</span><span class="sxs-lookup"><span data-stu-id="7225d-103">Update-List</span></span>

## <span data-ttu-id="7225d-104">概要</span><span class="sxs-lookup"><span data-stu-id="7225d-104">SYNOPSIS</span></span>
<span data-ttu-id="7225d-105">オブジェクトのコレクションを格納するプロパティ値の項目を追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="7225d-105">Adds items to and removes items from a property value that contains a collection of objects.</span></span>

## <span data-ttu-id="7225d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7225d-106">SYNTAX</span></span>

### <span data-ttu-id="7225d-107">AddRemoveSet (既定)</span><span class="sxs-lookup"><span data-stu-id="7225d-107">AddRemoveSet (Default)</span></span>

```
Update-List [-Add <Object[]>] [-Remove <Object[]>] [-InputObject <PSObject>] [[-Property] <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="7225d-108">ReplaceSet</span><span class="sxs-lookup"><span data-stu-id="7225d-108">ReplaceSet</span></span>

```
Update-List -Replace <Object[]> [-InputObject <PSObject>] [[-Property] <String>] [<CommonParameters>]
```

## <span data-ttu-id="7225d-109">Description</span><span class="sxs-lookup"><span data-stu-id="7225d-109">DESCRIPTION</span></span>

<span data-ttu-id="7225d-110">コマンドレットでは、 `Update-List` オブジェクトのプロパティ値の項目を追加、削除、または置換して、更新されたオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="7225d-110">The `Update-List` cmdlet adds, removes, or replaces items in a property value of an object and returns the updated object.</span></span> <span data-ttu-id="7225d-111">このコマンドレットは、オブジェクトのコレクションを格納するプロパティ用に設計されています。</span><span class="sxs-lookup"><span data-stu-id="7225d-111">This cmdlet is designed for properties that contain collections of objects.</span></span>

<span data-ttu-id="7225d-112">**Add** パラメーターと **remove** パラメーターは、個々の項目を追加し、コレクションから削除します。</span><span class="sxs-lookup"><span data-stu-id="7225d-112">The **Add** and **Remove** parameters add individual items to and remove them from the collection.</span></span>
<span data-ttu-id="7225d-113">**Replace** パラメーターは、コレクション全体を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="7225d-113">The **Replace** parameter replaces the entire collection.</span></span>

<span data-ttu-id="7225d-114">コマンドでプロパティを指定しない場合、はオブジェクトを更新する代わりに、 `Update-List` 更新を説明するオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="7225d-114">If you do not specify a property in the command, `Update-List` returns an object that describes the update instead of updating the object.</span></span> <span data-ttu-id="7225d-115">コマンドレットなどのオブジェクトを変更するコマンドレットに、更新オブジェクトを送信でき `Set` ます。</span><span class="sxs-lookup"><span data-stu-id="7225d-115">You can submit the update object to cmdlets that change objects, such as `Set` cmdlets.</span></span>

<span data-ttu-id="7225d-116">このコマンドレットは、更新中のプロパティがを使用する **IList** インターフェイスをサポートしている場合にのみ機能 `Update-List` します。</span><span class="sxs-lookup"><span data-stu-id="7225d-116">This cmdlet works only when the property that is being updated supports the **IList** interface that `Update-List` uses.</span></span> <span data-ttu-id="7225d-117">また、 `Set` 更新プログラムを受け入れるすべてのコマンドレットは、 **IList** インターフェイスをサポートしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7225d-117">Also, any `Set` cmdlets that accept an update must support the **IList** interface.</span></span>

<span data-ttu-id="7225d-118">PowerShell でインストールされるコアコマンドレットは、このインターフェイスをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="7225d-118">The core cmdlets that are installed with PowerShell do not support this interface.</span></span> <span data-ttu-id="7225d-119">コマンドレットがサポートしているかどうかを確認するには `Update-List` 、コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7225d-119">To determine whether a cmdlet supports `Update-List`, see the cmdlet Help topic.</span></span>

## <span data-ttu-id="7225d-120">例</span><span class="sxs-lookup"><span data-stu-id="7225d-120">EXAMPLES</span></span>

### <span data-ttu-id="7225d-121">例 1: プロパティ値に項目を追加する</span><span class="sxs-lookup"><span data-stu-id="7225d-121">Example 1: Add items to a property value</span></span>

<span data-ttu-id="7225d-122">この例では、カードを **リスト** コレクションオブジェクトとして格納するカードのデッキを表すクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="7225d-122">In this example we create a class that represents a deck of cards where the cards are stored as a **List** collection object.</span></span> <span data-ttu-id="7225d-123">**Newdeck ()** メソッドでは、を使用し `Update-List` てカードコレクションにカード値 **cards** の完全なデッキを追加します。</span><span class="sxs-lookup"><span data-stu-id="7225d-123">The **NewDeck()** method uses `Update-List`to add a complete deck of card values to the **cards** collection.</span></span>

```powershell
class Cards {

    [System.Collections.Generic.List[string]]$cards
    [string]$name

    Cards([string]$_name) {
        $this.name = $_name
        $this.cards = [System.Collections.Generic.List[string]]::new()
    }

    NewDeck() {
        $_suits = [char]0x2663,[char]0x2666,[char]0x2665,[char]0x2660
        $_values = 'A',2,3,4,5,6,7,8,9,10,'J','Q','K'
        $_deck = foreach ($s in $_suits){ foreach ($v in $_values){ "$v$s"} }
        $this | Update-List -Property cards -Add $_deck | Out-Null
    }

    Show() {
        Write-Host
        Write-Host $this.name ": " $this.cards[0..12]
        if ($this.cards.count -gt 13) {
            Write-Host (' ' * ($this.name.length+3)) $this.cards[13..25]
        }
        if ($this.cards.count -gt 26) {
            Write-Host (' ' * ($this.name.length+3)) $this.cards[26..38]
        }
        if ($this.cards.count -gt 39) {
            Write-Host (' ' * ($this.name.length+3)) $this.cards[39..51]
        }
    }

    Shuffle() { $this.cards = Get-Random -InputObject $this.cards -Count 52 }

    Sort() { $this.cards.Sort() }
}
```

> [!NOTE]
> <span data-ttu-id="7225d-124">`Update-List`コマンドレットは、更新されたオブジェクトをパイプラインに出力します。</span><span class="sxs-lookup"><span data-stu-id="7225d-124">The `Update-List` cmdlet outputs the updated object to the pipeline.</span></span> <span data-ttu-id="7225d-125">出力をにパイプして、 `Out-Null` 不要な表示を抑制します。</span><span class="sxs-lookup"><span data-stu-id="7225d-125">We pipe the output to `Out-Null` to suppress the unwanted display.</span></span>

### <span data-ttu-id="7225d-126">例 2: コレクションプロパティの項目を追加および削除する</span><span class="sxs-lookup"><span data-stu-id="7225d-126">Example 2: Add and remove items of a collection property</span></span>

<span data-ttu-id="7225d-127">例1のコードを続けて、カードと2人のプレーヤーが保持するカードのデッキを表す **カード** クラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="7225d-127">Continuing with the code in Example 1, we will create instances of the **Cards** class to represent a deck of cards and the cards held by two players.</span></span> <span data-ttu-id="7225d-128">コマンドレットを使用して、 `Update-List` プレーヤーにカードを追加し、デッキからカードを削除します。</span><span class="sxs-lookup"><span data-stu-id="7225d-128">We use the `Update-List` cmdlet to add cards to the players' hands and to remove cards from the deck.</span></span>

```powershell
$player1 = [Cards]::new('Player 1')
$player2 = [Cards]::new('Player 2')

$deck = [Cards]::new('Deck')
$deck.NewDeck()
$deck.Shuffle()
$deck.Show()

# Deal two hands
$player1 | Update-List -Property cards -Add $deck.cards[0,2,4,6,8] | Out-Null
$player2 | Update-List -Property cards -Add $deck.cards[1,3,5,7,9] | Out-Null
$deck | Update-List -Property cards -Remove $player1.cards | Out-Null
$deck | Update-List -Property cards -Remove $player2.cards | Out-Null

$player1.Show()
$player2.Show()
$deck.Show()
```

```Output
Deck :  4♦ 7♥ J♦ 5♣ A♣ 8♦ J♣ Q♥ 6♦ 3♦ 9♦ 6♣ 2♣
        K♥ 4♠ 10♥ 8♠ 10♦ 9♠ 6♠ K♦ 7♣ 3♣ Q♣ A♥ Q♠
        3♥ 5♥ 2♦ 5♠ J♥ J♠ 10♣ 4♥ Q♦ 10♠ 4♣ 2♠ 2♥
        6♥ 7♦ A♠ 5♦ 8♣ 9♥ K♠ 7♠ 3♠ 9♣ A♦ K♣ 8♥

Player 1 :  4♦ J♦ A♣ J♣ 6♦

Player 2 :  7♥ 5♣ 8♦ Q♥ 3♦

Deck :  9♦ 6♣ 2♣ K♥ 4♠ 10♥ 8♠ 10♦ 9♠ 6♠ K♦ 7♣ 3♣
        Q♣ A♥ Q♠ 3♥ 5♥ 2♦ 5♠ J♥ J♠ 10♣ 4♥ Q♦ 10♠
        4♣ 2♠ 2♥ 6♥ 7♦ A♠ 5♦ 8♣ 9♥ K♠ 7♠ 3♠ 9♣
        A♦ K♣ 8♥
```

<span data-ttu-id="7225d-129">出力には、カードがプレーヤーに向けられる前のデッキの状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7225d-129">The output shows the state of the deck before the cards were dealt to the players.</span></span> <span data-ttu-id="7225d-130">各プレーヤーがデッキから5枚のカードを受け取ったことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="7225d-130">You can see that each player received five cards from the deck.</span></span> <span data-ttu-id="7225d-131">最終的な出力は、カードをプレーヤーに処理した後のデッキの状態を示しています。</span><span class="sxs-lookup"><span data-stu-id="7225d-131">The final output shows the state of the deck after dealing the cards to the players.</span></span> <span data-ttu-id="7225d-132">`Update-List` は、デッキからカードを選択してプレイヤーのコレクションに追加するために使用されました。</span><span class="sxs-lookup"><span data-stu-id="7225d-132">`Update-List` was used to select the cards from the deck and add them to the players' collection.</span></span> <span data-ttu-id="7225d-133">次に、を使用して、プレイヤーのカードがデッキから削除されました `Update-List` 。</span><span class="sxs-lookup"><span data-stu-id="7225d-133">Then the players' cards were removed from the deck using `Update-List`.</span></span>

### <span data-ttu-id="7225d-134">例 3: 1 つのコマンドで項目を追加および削除する</span><span class="sxs-lookup"><span data-stu-id="7225d-134">Example 3: Add and remove items in a single command</span></span>

<span data-ttu-id="7225d-135">`Update-List` では、1つのコマンドで **Add** パラメーターと **Remove** パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7225d-135">`Update-List` allows you to use the **Add** and **Remove** parameters in a single command.</span></span> <span data-ttu-id="7225d-136">この例では、プレーヤー1がとを `4♦` 破棄 `6♦` し、2つの新しいカードを取得します。</span><span class="sxs-lookup"><span data-stu-id="7225d-136">In this example, Player 1 wants to discard the `4♦` and `6♦` and get two new cards.</span></span>

```powershell
# Player 1 wants two new cards - remove 2 cards & add 2 cards
$player1 | Update-List -Property cards -Remove $player1.cards[0,4] -Add $deck.cards[0..1] | Out-Null
$player1.Show()

# remove dealt cards from deck
$deck | Update-List -Property cards -Remove $deck.cards[0..1] | Out-Null
$deck.Show()
```

```Output
Player 1 :  J♦ A♣ J♣ 9♦ 6♣

Deck :  2♣ K♥ 4♠ 10♥ 8♠ 10♦ 9♠ 6♠ K♦ 7♣ 3♣ Q♣ A♥
        Q♠ 3♥ 5♥ 2♦ 5♠ J♥ J♠ 10♣ 4♥ Q♦ 10♠ 4♣ 2♠
        2♥ 6♥ 7♦ A♠ 5♦ 8♣ 9♥ K♠ 7♠ 3♠ 9♣ A♦ K♣
        8♥
```

## <span data-ttu-id="7225d-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7225d-137">PARAMETERS</span></span>

### <span data-ttu-id="7225d-138">-Add</span><span class="sxs-lookup"><span data-stu-id="7225d-138">-Add</span></span>

<span data-ttu-id="7225d-139">コレクションに追加するプロパティ値を指定します。</span><span class="sxs-lookup"><span data-stu-id="7225d-139">Specifies the property values to be added to the collection.</span></span> <span data-ttu-id="7225d-140">コレクションに表示する順序で値を入力します。</span><span class="sxs-lookup"><span data-stu-id="7225d-140">Enter the values in the order that they should appear in the collection.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: AddRemoveSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7225d-141">-InputObject</span><span class="sxs-lookup"><span data-stu-id="7225d-141">-InputObject</span></span>

<span data-ttu-id="7225d-142">更新するオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="7225d-142">Specifies the objects to be updated.</span></span> <span data-ttu-id="7225d-143">パイプを使用して、更新するオブジェクトをにパイプすることもでき `Update-List` ます。</span><span class="sxs-lookup"><span data-stu-id="7225d-143">You can also pipe the object to be updated to `Update-List`.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="7225d-144">-プロパティ</span><span class="sxs-lookup"><span data-stu-id="7225d-144">-Property</span></span>

<span data-ttu-id="7225d-145">更新するコレクションを含むプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="7225d-145">Specifies the property that contains the collection that is being updated.</span></span> <span data-ttu-id="7225d-146">このパラメーターを省略すると、はオブジェクトを変更する代わりに、 `Update-List` 変更を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="7225d-146">If you omit this parameter, `Update-List` returns an object that represents the change instead of changing the object.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7225d-147">-Remove</span><span class="sxs-lookup"><span data-stu-id="7225d-147">-Remove</span></span>

<span data-ttu-id="7225d-148">コレクションから削除するプロパティ値を指定します。</span><span class="sxs-lookup"><span data-stu-id="7225d-148">Specifies the property values to be removed from the collection.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: AddRemoveSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7225d-149">-Replace</span><span class="sxs-lookup"><span data-stu-id="7225d-149">-Replace</span></span>

<span data-ttu-id="7225d-150">新しいコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="7225d-150">Specifies a new collection.</span></span> <span data-ttu-id="7225d-151">このパラメーターは、元のコレクション内のすべての項目を、このパラメーターで指定された項目で置き換えます。</span><span class="sxs-lookup"><span data-stu-id="7225d-151">This parameter replaces all items in the original collection with the items specified by this parameter.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: ReplaceSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7225d-152">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="7225d-152">CommonParameters</span></span>

<span data-ttu-id="7225d-153">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="7225d-153">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7225d-154">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7225d-154">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7225d-155">入力</span><span class="sxs-lookup"><span data-stu-id="7225d-155">INPUTS</span></span>

### <span data-ttu-id="7225d-156">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="7225d-156">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="7225d-157">パイプを使用して、更新するオブジェクトをにパイプすることができ `Update-List` ます。</span><span class="sxs-lookup"><span data-stu-id="7225d-157">You can pipe the objects to be updated to `Update-List`.</span></span>

## <span data-ttu-id="7225d-158">出力</span><span class="sxs-lookup"><span data-stu-id="7225d-158">OUTPUTS</span></span>

### <span data-ttu-id="7225d-159">オブジェクトまたは PSListModifier。</span><span class="sxs-lookup"><span data-stu-id="7225d-159">Objects or System.Management.Automation.PSListModifier</span></span>

<span data-ttu-id="7225d-160">`Update-List` 更新されたオブジェクトを返すか、更新アクションを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="7225d-160">`Update-List` returns the updated object, or it returns an object that represents the update action.</span></span>

## <span data-ttu-id="7225d-161">注</span><span class="sxs-lookup"><span data-stu-id="7225d-161">NOTES</span></span>

## <span data-ttu-id="7225d-162">関連リンク</span><span class="sxs-lookup"><span data-stu-id="7225d-162">RELATED LINKS</span></span>

[<span data-ttu-id="7225d-163">Format-List</span><span class="sxs-lookup"><span data-stu-id="7225d-163">Format-List</span></span>](Format-List.md)

[<span data-ttu-id="7225d-164">Select-Object</span><span class="sxs-lookup"><span data-stu-id="7225d-164">Select-Object</span></span>](Select-Object.md)
