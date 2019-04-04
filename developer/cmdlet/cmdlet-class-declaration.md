---
title: コマンドレット クラスの宣言 |Microsoft Docs
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
ms.openlocfilehash: 3168275423dc65fcb2e41dedd9bea275ede58397
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58055089"
---
# <a name="cmdlet-class-declaration"></a>コマンドレットのクラス宣言

Microsoft .NET Framework クラスが指定することでコマンドレットとして宣言されている、**コマンドレット**属性として、クラスのメタデータ。 (、**コマンドレット**属性は、すべてのコマンドレットの唯一の必須属性)。 指定した場合、**コマンドレット**属性、ユーザーにコマンドレットを識別する動詞-名詞形式のペアを指定する必要があります。 また、このコマンドレットをサポートする Windows PowerShell の機能を記述する必要があります。 指定に使用される宣言の構文の詳細については、**コマンドレット**属性は、「[コマンドレット属性宣言](./cmdlet-attribute-declaration.md)します。

> [!NOTE]
> **コマンドレット**属性を定義した、 [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute)クラス。 このクラスのプロパティは、属性を宣言するときに使用されるパラメーターの宣言に対応します。

## <a name="nouns"></a>名詞

コマンドレットの名詞には、コマンドレットの処理となるリソースを指定します。 名詞では、他のコマンドレットから、コマンドレットが区別されます。

コマンドレットの名前に名詞などでなければなりません具体的である場合は、汎用の名詞と*server*、他の同様のリソースからリソースを識別する短いプレフィックスを追加することをお勧めします。 たとえば、プレフィックス付きの名詞を含むコマンドレット名は`Get-SQLServer`します。 一般的な動詞を使用して特定の名詞を組み合わせたには、その操作によって、コマンドレットをすばやく検索し、そのリソースによって不要なコマンドレット名の重複を回避しながら、コマンドレットを識別するユーザーができるようにします。

コマンドレット名では使用できませんの特殊文字の一覧は、[開発ガイドラインのために必要な](./required-development-guidelines.md)を参照してください。

## <a name="verbs"></a>[動詞]

動詞を指定すると、開発のガイドラインでは、Windows PowerShell によって提供される定義済みの動詞のいずれかを使用する必要があります。 これらの定義済みの動詞のいずれかは、作成したコマンドレットと Microsoft によっては他のユーザーが記述されたコマンドレット一貫性が確保されます。 たとえば、"Get"動詞は、データを取得するコマンドレットが使用されます。

動詞に関するガイドラインの詳細については、[コマンドレット動詞名](./approved-verbs-for-windows-powershell-commands.md)を参照してください。 コマンドレット名では使用できませんの特殊文字の一覧は、[開発ガイドラインのために必要な](./required-development-guidelines.md)を参照してください。

## <a name="supporting-windows-powershell-functionality"></a>Windows PowerShell の機能をサポートしています。

**コマンドレット**属性では、コマンドレットがいくつかの Windows PowerShell によって提供される一般的な機能をサポートしているを指定することもできます。 これには、ユーザーのフィードバックの確認 (ShouldProcess 機能のサポートと呼ばれます) などの一般的な機能をサポートし、トランザクションのサポートが含まれます。 (トランザクションのサポートは、Windows PowerShell 2.0 で導入されました。)

指定に使用される宣言の構文の詳細については、**コマンドレット**属性は、「[コマンドレット属性宣言](./cmdlet-attribute-declaration.md)します。

## <a name="cmdlet-class-definition"></a>コマンドレット クラスの定義

次のコードは、GetProc コマンドレット クラスの定義です。 大文字と小文字を使用する pascal 形式と、クラスの名前には、コマンドレットの名詞と動詞が含まれることに注意してください。

[!code-csharp[GetProcessSample01.cs](../../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample01/GetProcessSample01.cs#L33-L34 "GetProcessSample01.cs")]

## <a name="pascal-casing"></a>Pascal 形式の大文字小文字の区別

Pascal 形式を使用して、コマンドレットの名前を入力するとき大文字小文字の区別します。 たとえば、`Get-Item`と`Get-ItemProperty`コマンドレットは、コマンドレットに名前を付けるときに、大文字と小文字を使用する正しい方法を紹介します。

## <a name="see-also"></a>参照

[System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute)

[CmdletAttribute 宣言](./cmdlet-attribute-declaration.md)

[コマンドレットの動詞名](./approved-verbs-for-windows-powershell-commands.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
