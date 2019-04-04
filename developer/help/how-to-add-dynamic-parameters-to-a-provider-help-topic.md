---
title: プロバイダーのヘルプ トピックに動的パラメーターを追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e20e5ad6-a6e6-4a63-9d42-1ac54214f748
caps.latest.revision: 5
ms.openlocfilehash: cc4877242a16a9caa99564aeaae985f85e38791e
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859878"
---
# <a name="how-to-add-dynamic-parameters-to-a-provider-help-topic"></a>プロバイダーのヘルプ トピックに動的パラメーターを追加する方法

このセクションを設定する方法を説明します、**動的パラメーター**プロバイダーのヘルプ トピックの「します。

*動的パラメーター*コマンドレットのパラメーターまたは指定された条件の下にのみ利用できる関数です。

プロバイダーのヘルプ トピックで説明されている動的パラメーターは、コマンドレットまたは関数を使用して、プロバイダー ドライブでコマンドレットまたは関数にプロバイダーを追加する動的パラメーターです。

動的パラメーターは、プロバイダーのカスタム コマンドレット ヘルプにも記載されていることができます。 プロバイダーのヘルプとカスタム コマンドレット ヘルプの両方のプロバイダーを記述する場合は、ドキュメントの両方で動的パラメーターのドキュメントが含まれます。 カスタム コマンドレット ヘルプの詳細については、[書き込み Windows PowerShell のカスタム コマンドレット ヘルプのプロバイダー](./writing-custom-cmdlet-help-for-windows-powershell-providers.md)を参照してください。

プロバイダーのヘルプ トピックにはプロバイダーが動的パラメーターを実装していない場合、空が含まれています`DynamicParameters`要素。

### <a name="to-add-dynamic-parameters"></a>動的パラメーターを追加するには

1. *AssemblyName*.dll help.xml ファイル内で、`providerHelp`要素を追加、`DynamicParameters`要素。 `DynamicParameters`後に要素が表示されます、`Tasks`要素とする前に、`RelatedLinks`要素。

   たとえば、次のように入力します。

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

   プロバイダーは、動的パラメーターを実装していない場合、`DynamicParameters`要素を空にすることができます。

2. 内で、`DynamicParameters`要素、各動的パラメーターの追加、`DynamicParameter`要素。

   たとえば、次のように入力します。

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
        </DynamicParameter>
    </DynamicParameters>
    ```

3. 各`DynamicParameter`要素を追加、`Name`と`CmdletSupported`要素。

   |要素名|説明|
   |------------------|-----------------|
   |名前|パラメーター名を指定します。|
   |CmdletSupported|パラメーターの有効なコマンドレットを指定します。 コマンドレット名のコンマ区切りの一覧を入力します。|

   次の XML ドキュメントなど、`Encoding`に、Windows PowerShell FileSystem プロバイダーを追加する動的パラメーター、 `Add-Content`、 `Get-Content`、`Set-Content`コマンドレット。

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
            <Name> Encoding </Name>
            <CmdletSupported> Add-Content, Get-Content, Set-Content </CmdletSupported>
    </DynamicParameters>

    ```

4. 各`DynamicParameter`要素を追加、`Type`要素。 `Type`要素は、コンテナー、`Name`動的パラメーターの値の .NET 型を含む要素。

   たとえば、次の XML を .NET の種類を表示、`Encoding`動的パラメーターとは、 [Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding](/dotnet/api/microsoft.powershell.commands.filesystemcmdletproviderencoding)列挙体。

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

5. 追加、`Description`要素で、動的パラメーターの簡単な説明が含まれています。 説明を作成するときは、すべてのコマンドレット パラメーターで規定されているガイドラインを使用して[パラメーター情報を追加する方法](./how-to-add-parameter-information.md)します。

   たとえば、次の XML には、説明が含まれます。、`Encoding`動的パラメーターです。

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

6. 追加、`PossibleValues`要素とその子要素。 同時に、これらの要素には、動的パラメーターの値について説明します。 この要素は、列挙値に適しています。 など、スイッチ パラメーターの場合は、または値を列挙することはできません、空を追加する動的パラメーターが値を受け取らない場合`PossibleValues`要素。

   次の表を示し、`PossibleValues`要素とその子要素。

   |要素名|説明|
   |------------------|-----------------|
   |PossibleValues|この要素は、コンテナーです。 その子要素を以下に示します。 1 つ追加`PossibleValues`各プロバイダーのヘルプ トピックへの要素。 要素を空にすることができます。|
   |PossibleValue|この要素は、コンテナーです。 その子要素を以下に示します。 1 つ追加`PossibleValue`動的パラメーターの値ごとの要素。|
   |値|値の名前を指定します。|
   |説明|この要素が含まれています、`Para`要素。 内のテキスト、`Para`要素で指定されている値を記述する、`Value`要素。|

   たとえば、次の XML では 1 つ`PossibleValue`の要素、`Encoding`動的パラメーターです。

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

次の例は、`DynamicParameters`の要素、`Encoding`動的パラメーターです。

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