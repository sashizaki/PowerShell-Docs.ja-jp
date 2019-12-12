---
title: プロバイダーに動的パラメーターを追加する方法に関するヘルプトピック |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e20e5ad6-a6e6-4a63-9d42-1ac54214f748
caps.latest.revision: 5
ms.openlocfilehash: 59839e9b8b6f2a56f2f1a9c755f2f1a85deb34aa
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361261"
---
# <a name="how-to-add-dynamic-parameters-to-a-provider-help-topic"></a>プロバイダーのヘルプ トピックに動的パラメーターを追加する方法

このセクションでは、プロバイダーヘルプトピックの**動的パラメーター**セクションにデータを設定する方法について説明します。

*動的パラメーター*とは、指定された条件下でのみ使用可能なコマンドレットまたは関数のパラメーターです。

プロバイダーのヘルプトピックに記載されている動的パラメーターは、プロバイダーのドライブでコマンドレットまたは関数が使用されている場合に、プロバイダーがコマンドレットまたは関数に追加する動的パラメーターです。

動的パラメーターは、プロバイダーのカスタムコマンドレットのヘルプにも記載されています。 プロバイダーのヘルプとカスタムコマンドレットのヘルプの両方を作成するときは、両方のドキュメントに動的パラメーターのドキュメントを含めてください。

プロバイダーが動的パラメーターを実装していない場合、プロバイダーヘルプトピックには空の `DynamicParameters` 要素が含まれます。

### <a name="to-add-dynamic-parameters"></a>動的パラメーターを追加するには

1. Dll-help ファイル*の `providerHelp`* 要素内に、`DynamicParameters` 要素を追加します。 `DynamicParameters` 要素は、`Tasks` 要素の後、`RelatedLinks` 要素の前に表示されます。

   たとえば、次のようになります。

    ```xml
    <providerHelp>
        <Tasks>
        </Tasks>
        <DynamicParameters>
        </DynamicParameters>
        <RelatedLinks>
        </RelatedLinks>
    </providerHelp>
    ```

   プロバイダーが動的パラメーターを実装していない場合は、`DynamicParameters` 要素を空にすることができます。

2. `DynamicParameters` 要素内で、各動的パラメーターに `DynamicParameter` 要素を追加します。

   たとえば、次のようになります。

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
        </DynamicParameter>
    </DynamicParameters>
    ```

3. 各 `DynamicParameter` 要素に、`Name` と `CmdletSupported` 要素を追加します。

   |要素名|[説明]|
   |------------------|-----------------|
   |名前|パラメーター名を指定します。|
   |サポートされているもの|パラメーターが有効なコマンドレットを指定します。 コマンドレット名のコンマ区切りリストを入力します。|

   たとえば、次の XML ドキュメントでは、Windows PowerShell FileSystem プロバイダーによって `Add-Content`、`Get-Content`、`Set-Content` コマンドレットに追加される `Encoding` 動的パラメーターについて説明しています。

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
            <Name> Encoding </Name>
            <CmdletSupported> Add-Content, Get-Content, Set-Content </CmdletSupported>
    </DynamicParameters>

    ```

4. 各 `DynamicParameter` 要素に、`Type` 要素を追加します。 `Type` 要素は、動的パラメーターの値の .NET 型を含む `Name` 要素のコンテナーです。

   たとえば、次の XML は、`Encoding` 動的パラメーターの .NET 型が、 [Microsoft. PowerShell コマンドレット](/dotnet/api/microsoft.powershell.commands.filesystemcmdletproviderencoding)であることを示しています。

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
            <Name> Encoding </Name>
            <CmdletSupported> Add-Content, Get-Content, Set-Content </CmdletSupported>
            <Type>
                <Name> Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding </Name>
            <Type>
    ...
    </DynamicParameters>
    ```

5. `Description` 要素を追加します。この要素には、動的パラメーターの簡単な説明が含まれています。 説明を作成する場合は、「[パラメーター情報を追加する方法](./how-to-add-parameter-information.md)」のすべてのコマンドレットパラメーターに指定されているガイドラインを使用します。

   たとえば、次の XML には `Encoding` 動的パラメーターの説明が含まれています。

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
            <Name> Encoding </Name>
            <CmdletSupported> Add-Content, Get-Content, Set-Content </CmdletSupported>
            <Type>
                <Name> Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding </Name>
            <Type>
            <Description> Specifies the encoding of the output file that contains the content. </Description>
    ...
    </DynamicParameters>
    ```

6. `PossibleValues` 要素とその子要素を追加します。 これらの要素には、動的パラメーターの値が記述されています。 この要素は、列挙値用に設計されています。 スイッチパラメーターの場合など、動的パラメーターに値がない場合、または値を列挙できない場合は、空の `PossibleValues` 要素を追加します。

   次の表に、`PossibleValues` 要素とその子要素の一覧とその説明を示します。

   |要素名|[説明]|
   |------------------|-----------------|
   |指定した値|この要素はコンテナーです。 その子要素について以下に説明します。 各プロバイダーヘルプトピックに `PossibleValues` 要素を1つ追加します。 要素は空にすることができます。|
   |指定した値|この要素はコンテナーです。 その子要素について以下に説明します。 動的パラメーターの値ごとに1つの `PossibleValue` 要素を追加します。|
   |値|値の名前を指定します。|
   |[説明]|この要素には、`Para` 要素が含まれています。 `Para` 要素内のテキストは、`Value` 要素で指定された値を表します。|

   たとえば、次の XML は、`Encoding` 動的パラメーターの1つの `PossibleValue` 要素を示しています。

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
    ...
            <Description> Specifies the encoding of the output file that contains the content. </Description>
            <PossibleValues>
                <PossibleValue>
                    <Value> ASCII </Value>
                    <Description>
                        <para> Uses the encoding for the ASCII (7-bit) character set. </para>
                    </Description>
                </PossibleValue>
    ...
            </PossibleValues>
    </DynamicParameters>
    ```

## <a name="example"></a>例

次の例は、`Encoding` 動的パラメーターの `DynamicParameters` 要素を示しています。

```xml
<DynamicParameters/>
    <DynamicParameter>
        <Name> Encoding </Name>
        <CmdletSupported> Add-Content, Get-Content, Set-Content </CmdletSupported>
        <Type>
            <Name> Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding </Name>
        <Type>
        <Description> Specifies the encoding of the output file that contains the content. </Description>
        <PossibleValues>
            <PossibleValue>
                <Value> ASCII </Value>
                <Description>
                    <para> Uses the encoding for the ASCII (7-bit) character set. </para>
                </Description>
            </PossibleValue>
            <PossibleValue>
                <Value> Unicode </Value>
                <Description>
                    <para> Encodes in UTF-16 format using the little-endian byte order. </para>
                </Description>
            </PossibleValue>
        </PossibleValues>
</DynamicParameters>
```