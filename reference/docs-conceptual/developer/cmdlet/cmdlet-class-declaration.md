---
title: コマンドレットクラス宣言 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- cmdlets [PowerShell SDK], declaring
- declaring cmdlets [PowerShell SDK]
ms.assetid: 1fcc4c5e-0c75-496c-a712-5f844e310576
caps.latest.revision: 14
ms.openlocfilehash: 0de49d979c31b0e8d111323a2e1899d97868ec3f
ms.sourcegitcommit: 7f2479edd329dfdc55726afff7019d45e45f9156
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2020
ms.locfileid: "80978714"
---
# <a name="cmdlet-class-declaration"></a>コマンドレットのクラス宣言

Microsoft .NET Framework クラスは、クラスのメタデータとして**コマンドレット**属性を指定することで、コマンドレットとして宣言されます。 (**コマンドレット**属性は、すべてのコマンドレットに必要な唯一の属性です)。
**コマンドレット**の属性を指定する場合は、コマンドレットを識別する動詞と名詞のペアをユーザーに指定する必要があります。 また、コマンドレットがサポートする Windows PowerShell の機能について説明する必要があります。 **コマンドレット**属性の指定に使用される宣言構文の詳細については、「[コマンドレット属性の宣言](./cmdlet-attribute-declaration.md)」を参照してください。

> [!NOTE]
> **コマンドレット**属性は、system.servicemodel[属性](/dotnet/api/System.Management.Automation.CmdletAttribute)クラスによって定義されます。 このクラスのプロパティは、属性を宣言するときに使用される宣言パラメーターに対応します。

## <a name="nouns"></a>名詞

コマンドレットの名詞は、コマンドレットが処理するリソースを指定します。 名詞は、コマンドレットを他のコマンドレットと区別します。

コマンドレット名の名詞は固有である必要があります。また、*サーバー*などの汎用名詞の場合は、リソースを他の類似リソースと区別する短いプレフィックスを追加することをお勧めします。 たとえば、プレフィックスを持つ名詞を含むコマンドレット名は `Get-SQLServer`です。 特定の名詞とより一般的な動詞を組み合わせることで、ユーザーはコマンドレットをアクションですばやく検索し、不要なコマンドレット名の重複を回避して、コマンドレットをリソースで識別できます。

コマンドレット名に使用できない特殊文字の一覧については、「[必要な開発ガイドライン](./required-development-guidelines.md)」を参照してください。

## <a name="verbs"></a>動詞

動詞を指定する場合、開発ガイドラインでは、Windows PowerShell によって提供される定義済み動詞のいずれかを使用する必要があります。 これらの定義済み動詞のいずれかを使用すると、作成したコマンドレットと、Microsoft によって作成されたコマンドレットと他のコマンドレットとの間の一貫性が確保されます。 たとえば、データを取得するコマンドレットには、"Get" 動詞を使用します。

動詞のガイドラインの詳細については、「[コマンドレットの動詞名](./approved-verbs-for-windows-powershell-commands.md)」を参照してください。 コマンドレット名に使用できない特殊文字の一覧については、「[必要な開発ガイドライン](./required-development-guidelines.md)」を参照してください。

## <a name="supporting-windows-powershell-functionality"></a>Windows PowerShell の機能のサポート

**コマンドレット**属性では、コマンドレットが Windows PowerShell によって提供されるいくつかの一般的な機能をサポートするように指定することもできます。 これには、ユーザーフィードバックの確認 ("ユーザーの操作" 機能のサポートと呼ばれます) などの一般的な機能のサポートと、トランザクションのサポートが含まれます。 (トランザクションのサポートは、Windows PowerShell 2.0 で導入されました)。

**コマンドレット**属性の指定に使用される宣言構文の詳細については、「[コマンドレット属性の宣言](./cmdlet-attribute-declaration.md)」を参照してください。

## <a name="cmdlet-class-definition"></a>コマンドレットのクラス定義

次のコードは、GetProc cmdlet クラスの定義です。 Pascal の大文字と小文字の区別が使用され、クラスの名前にはコマンドレットの動詞と名詞が含まれていることに注意してください。

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample01/GetProcessSample01.cs" range="33-34":::

## <a name="pascal-casing"></a>Pascal 形式の文字種

コマンドレットに名前を指定する場合は、Pascal 形式を使用します。 たとえば、コマンドレットに名前を付けるときに、`Get-Item` および `Get-ItemProperty` のコマンドレットを使用すると、大文字小文字を正しく使用することができます。

## <a name="see-also"></a>参照

[....... の属性](/dotnet/api/System.Management.Automation.CmdletAttribute)

[属性の宣言](./cmdlet-attribute-declaration.md)

[コマンドレットの動詞名](./approved-verbs-for-windows-powershell-commands.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
