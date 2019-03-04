---
title: Windows PowerShell プロパティ プロバイダーを作成する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- property providers [PowerShell Programmer's Guide]
- providers [PowerShell Programmer's Guide], property provider
ms.assetid: a6adca44-b94b-4103-9970-a9b414355e60
caps.latest.revision: 5
ms.openlocfilehash: ade8fbd38e4f4a675e825b0d8850af0379c9d211
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858898"
---
# <a name="creating-a-windows-powershell-property-provider"></a>Windows PowerShell プロパティ プロバイダーを作成する

このトピックでは、データ ストア内のアイテムのプロパティを操作するユーザーを有効にするプロバイダーを作成する方法について説明します。 その結果、この種類のプロバイダーは、Windows PowerShell プロパティ プロバイダーとしてに呼ばれます。 たとえば、レジストリ プロバイダー レジストリ キーの項目のプロパティとして Windows PowerShell ハンドル レジストリ キーの値によって提供されます。 この種類のプロバイダーを追加する必要があります、 [System.Management.Automation.Provider.Ipropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider) .NET クラスの実装へのインターフェイス。

> [!NOTE]
> Windows PowerShell では、Windows PowerShell プロバイダーの開発に使用できるテンプレート ファイルを提供します。 TemplateProvider.cs ファイルでは、Microsoft Windows ソフトウェア開発キットの Windows Vista と .NET Framework 3.0 ランタイム コンポーネントで使用できます。 ダウンロードの手順については、次を参照してください。 [Windows PowerShell のインストールと、Windows PowerShell SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)します。
> Windows PowerShell では、Windows PowerShell プロバイダーの開発に使用できるテンプレート ファイルを提供します。 TemplateProvider.cs ファイルでは、Microsoft Windows ソフトウェア開発キットの Windows Vista と .NET Framework 3.0 ランタイム コンポーネントで使用できます。 ダウンロードの手順については、次を参照してください。 [Windows PowerShell のインストールと、Windows PowerShell SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)します。
>
> ダウンロードしたテンプレートが表示されます、  **\<PowerShell のサンプル >** ディレクトリ。 このファイルのコピーを作成して、必要のないすべての機能を削除する、新しい Windows PowerShell プロバイダーを作成するため、コピーを使用する必要があります。
>
> その他の Windows PowerShell プロバイダーの実装の詳細については、次を参照してください。 [Your Windows PowerShell プロバイダーの設計](./designing-your-windows-powershell-provider.md)します。

> [!CAUTION]
> プロパティ プロバイダーのメソッドを使用して任意のオブジェクトを書き込む必要があります、 [System.Management.Automation.Provider.Cmdletprovider.Writepropertyobject*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WritePropertyObject)メソッド。

次の一覧には、このトピックのセクションが含まれています。 Windows PowerShell プロパティ プロバイダーの記述に慣れていない場合は、出現する順序では、この情報を読み込みます。 ただし、Windows PowerShell プロパティ プロバイダーの作成に習熟する場合は、直接」に進んでください必要な情報。

- [Windows PowerShell プロバイダーを定義します。](#Defining-the-Windows-PowerShell-provider)

- [基本機能を定義します。](#Defining-Base-Functionality)

- [プロパティを取得します。](#Retrieving-Properties)

- [動的パラメーターをアタッチ、`Get-ItemProperty`コマンドレット](#Attaching-Dynamic-Parameters-to-the-Get-ItemProperty-Cmdlet)

- [プロパティの設定](#Setting-Properties)

- [動的パラメーターをアタッチ、`Set-ItemProperty`コマンドレット](#Attaching-Dynamic-Parameters-for-the-Set-ItemProperty-Cmdlet)

- [プロパティをクリアします。](#Clearing-Properties)

- [動的パラメーターをアタッチ、`Clear-ItemProperty`コマンドレット](#Attaching-Dynamic-Parameters-to-the-Clear-ItemProperty-Cmdlet)

- [Windows PowerShell プロバイダーのビルド](#Building-the-Windows-PowerShell-provider)

## <a name="defining-the-windows-powershell-provider"></a>Windows PowerShell プロバイダーを定義します。

プロパティ プロバイダーがサポートする .NET クラスを作成する必要があります、 [System.Management.Automation.Provider.Ipropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider)インターフェイス。 Windows PowerShell によって提供される TemplateProvider.cs ファイルから既定のクラス宣言を次に示します。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testcmdletspropertyproviderclassdeclaration](Msh_samplestestcmdlets#testcmdletspropertyproviderclassdeclaration)]  -->

## <a name="defining-base-functionality"></a>基本機能を定義します。

[System.Management.Automation.Provider.Ipropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider)インターフェイスは、例外としてプロバイダーの基本クラスのいずれかに接続する、 [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)クラス。 使用する基本クラスで必要な基本機能を追加します。 基底クラスの詳細については、次を参照してください。 [Your Windows PowerShell プロバイダーの設計](./designing-your-windows-powershell-provider.md)します。

## <a name="retrieving-properties"></a>プロパティを取得します。

プロパティを取得するには、プロバイダーを実装する必要があります、 [System.Management.Automation.Provider.Ipropertycmdletprovider.Getproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty)メソッドからの呼び出しをサポートするために、`Get-ItemProperty`コマンドレット。 このメソッドは、(完全修飾)、指定したプロバイダーの内部パスにある項目のプロパティを取得します。

`providerSpecificPickList`パラメーターを取得するプロパティを示します。 このパラメーターが場合`null`または空の場合、メソッドはすべてのプロパティを取得する必要があります。 さらに、 [System.Management.Automation.Provider.Ipropertycmdletprovider.Getproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty)のインスタンスを書き込み、 [System.Management.Automation.Psobject](/dotnet/api/System.Management.Automation.PSObject)を表すオブジェクトを取得したプロパティのプロパティ バッグ。 メソッドは、何も返す必要があります。

お勧めの実装[System.Management.Automation.Provider.Ipropertycmdletprovider.Getproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty)選択リスト内の各要素のプロパティ名のワイルドカードの展開をサポートしています。 これを行うには、使用、 [System.Management.Automation.Wildcardpattern](/dotnet/api/System.Management.Automation.WildcardPattern)ワイルドカードによるパターン照合を実行するクラス。

既定の実装を次に示します[System.Management.Automation.Provider.Ipropertycmdletprovider.Getproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty) TemplateProvider.cs ファイルを Windows PowerShell によって提供されるからです。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testcmdletspropertyprovidergetproperty](Msh_samplestestcmdlets#testcmdletspropertyprovidergetproperty)]  -->

#### <a name="things-to-remember-about-implementing-getproperty"></a>GetProperty の実装に関する注意点

実装に、次の条件が適用[System.Management.Automation.Provider.Ipropertycmdletprovider.Getproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty):

- Windows PowerShell プロパティ プロバイダーがから ExpandWildcards、フィルター、インクルード、または除外するには、プロバイダーの機能を宣言可能性があります、プロバイダー クラスを定義するときに、 [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)列挙体。 これらのケースの実装で、 [System.Management.Automation.Provider.Ipropertycmdletprovider.Getproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty)メソッドは、メソッドに渡されるパスが指定した要件を満たしていることを確認する必要があります機能。 これを行うには、メソッドがプロパティにアクセス適切なたとえば、 [System.Management.Automation.Provider.Cmdletprovider.Exclude*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude)と[System.Management.Automation.Provider.Cmdletprovider.Include*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include)プロパティ。

- 既定では、このメソッドのオーバーライドを取得しないようにしない限り、ユーザーが非表示オブジェクト用のリーダー、 [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)プロパティに設定されて`true`します。 パスが、ユーザーが非表示の項目を表すかどうかエラーを記述する必要がありますと[System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)に設定されている`false`します。

## <a name="attaching-dynamic-parameters-to-the-get-itemproperty-cmdlet"></a>Get-itemproperty コマンドレットへの動的パラメーター

`Get-ItemProperty`コマンドレットは、実行時に動的に指定されている追加のパラメーターを必要があります。 これらの動的パラメーターを提供する Windows PowerShell プロパティ プロバイダーを実装する必要があります、 [System.Management.Automation.Provider.Ipropertycmdletprovider.Getpropertydynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetPropertyDynamicParameters)メソッド。 `path`パラメーターは、完全修飾プロバイダー-内部のパスを示します。 中に、`providerSpecificPickList`パラメーターをコマンドラインで入力したプロバイダー固有のプロパティを指定します。 このパラメーターがあります`null`または空の場合は、プロパティをコマンドレットにパイプします。 この場合、このメソッドは、プロパティと、コマンドレット クラスのように属性を解析してフィールドを持つオブジェクトを返しますまたは[System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)オブジェクト。 Windows PowerShell ランタイムでは、返されたオブジェクトを使用して、パラメーターをコマンドレットに追加します。

既定の実装を次に示します[System.Management.Automation.Provider.Ipropertycmdletprovider.Getpropertydynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetPropertyDynamicParameters) TemplateProvider.cs ファイルを Windows PowerShell によって提供されるからです。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testcmdletspropertyprovidergetpropertydynamicparameters](Msh_samplestestcmdlets#testcmdletspropertyprovidergetpropertydynamicparameters)]  -->

## <a name="setting-properties"></a>設定のプロパティ

プロパティを設定する、Windows PowerShell プロパティ プロバイダーを実装する必要があります、 [System.Management.Automation.Provider.Ipropertycmdletprovider.Setproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty)メソッドからの呼び出しをサポートするために、`Set-ItemProperty`コマンドレット。 このメソッドは、指定したパスにある項目の 1 つまたは複数のプロパティを設定し、必要に応じて指定されたプロパティを上書きします。 [System.Management.Automation.Provider.Ipropertycmdletprovider.Setproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty)も書き込みますのインスタンスを[System.Management.Automation.Psobject](/dotnet/api/System.Management.Automation.PSObject) 、更新のプロパティ バッグを表すオブジェクトを。プロパティ。

既定の実装を次に示します[System.Management.Automation.Provider.Ipropertycmdletprovider.Setproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty) TemplateProvider.cs ファイルを Windows PowerShell によって提供されるからです。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testcmdletspropertyprovidersetproperty](Msh_samplestestcmdlets#testcmdletspropertyprovidersetproperty)]  -->

#### <a name="things-to-remember-about-implementing-set-itemproperty"></a>Set-itemproperty の実装に関する注意点

実装を次の条件が適用[System.Management.Automation.Provider.Ipropertycmdletprovider.Setproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty):

- Windows PowerShell プロパティ プロバイダーがから ExpandWildcards、フィルター、インクルード、または除外するには、プロバイダーの機能を宣言可能性があります、プロバイダー クラスを定義するときに、 [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)列挙体。 これらのケースの実装で、 [System.Management.Automation.Provider.Ipropertycmdletprovider.Setproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty)メソッドがメソッドに渡されたパスが指定した要件を満たしていることを確認する必要があります機能。 これを行うには、メソッドがプロパティにアクセス適切なたとえば、 [System.Management.Automation.Provider.Cmdletprovider.Exclude*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude)と[System.Management.Automation.Provider.Cmdletprovider.Include*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include)プロパティ。

- 既定では、このメソッドのオーバーライドを取得しないようにしない限り、ユーザーが非表示オブジェクト用のリーダー、 [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)プロパティに設定されて`true`します。 パスが、ユーザーが非表示の項目を表すかどうかエラーを記述する必要がありますと[System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)に設定されている`false`します。

- 実装、 [System.Management.Automation.Provider.Ipropertycmdletprovider.Setproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty)メソッドを呼び出す必要があります[System.Management.Automation.Provider.Cmdletprovider.Shouldprocess*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)をデータ ストアに変更を加える前に、その戻り値を確認します。 このメソッドは、変更が行われるとシステムの状態にたとえば、ファイルの名前を変更する操作の実行の確認に使用されます。 [System.Management.Automation.Provider.Cmdletprovider.Shouldprocess*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) Windows PowerShell ランタイムと任意のコマンドライン設定やユーザー設定変数での処理で、ユーザーに変更するリソースの名前を送信します。何を表示するかを決定します。

  呼び出し後[System.Management.Automation.Provider.Cmdletprovider.Shouldprocess*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)返します`true`危険性のあるシステムの変更ができる場合、 [System.Management.Automation.Provider.Ipropertycmdletprovider.Setproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty)メソッドを呼び出す必要があります、 [System.Management.Automation.Provider.Cmdletprovider.Shouldcontinue*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue)メソッド。 このメソッドは、操作を続行することを示す追加のフィードバックを許可するユーザーに確認メッセージを送信します。

## <a name="attaching-dynamic-parameters-for-the-set-itemproperty-cmdlet"></a>Set-itemproperty コマンドレットの動的パラメーターをアタッチします。

`Set-ItemProperty`コマンドレットは、実行時に動的に指定されている追加のパラメーターを必要があります。 これらの動的パラメーターを提供する Windows PowerShell プロパティ プロバイダーを実装する必要があります、 [System.Management.Automation.Provider.Ipropertycmdletprovider.Setpropertydynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetPropertyDynamicParameters)メソッド。 このメソッドは、プロパティと、コマンドレット クラスのように属性を解析してフィールドを持つオブジェクトを返しますまたは[System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)オブジェクト。 `null`を追加する動的パラメーターがない場合、値が返されることができます。

既定の実装を次に示します[System.Management.Automation.Provider.Ipropertycmdletprovider.Getpropertydynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetPropertyDynamicParameters) TemplateProvider.cs ファイルを Windows PowerShell によって提供されるからです。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testcmdletspropertyprovidersetpropertydynamicparameters](Msh_samplestestcmdlets#testcmdletspropertyprovidersetpropertydynamicparameters)]  -->

## <a name="clearing-properties"></a>プロパティをクリアします。

プロパティをクリアする Windows PowerShell プロパティ プロバイダーを実装する必要があります、 [System.Management.Automation.Provider.Ipropertycmdletprovider.Clearproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty)メソッドからの呼び出しをサポートするために、`Clear-ItemProperty`コマンドレット。 このメソッドは、指定されたパスにある項目の 1 つまたは複数のプロパティを設定します。

既定の実装を次に示します[System.Management.Automation.Provider.Ipropertycmdletprovider.Clearproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty) TemplateProvider.cs ファイルを Windows PowerShell によって提供されるからです。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testcmdletspropertyproviderclearproperty](Msh_samplestestcmdlets#testcmdletspropertyproviderclearproperty)]  -->

#### <a name="thing-to-remember-about-implementing-clearproperty"></a>ClearProperty の実装に関する注意点

実装に、次の条件が適用[System.Management.Automation.Provider.Ipropertycmdletprovider.Clearproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty):

- Windows PowerShell プロパティ プロバイダーがから ExpandWildcards、フィルター、インクルード、または除外するには、プロバイダーの機能を宣言可能性があります、プロバイダー クラスを定義するときに、 [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)列挙体。 これらのケースの実装で、 [System.Management.Automation.Provider.Ipropertycmdletprovider.Clearproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty)メソッドは、メソッドに渡されるパスが指定した要件を満たしていることを確認する必要があります機能。 これを行うには、メソッドがプロパティにアクセス適切なたとえば、 [System.Management.Automation.Provider.Cmdletprovider.Exclude*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude)と[System.Management.Automation.Provider.Cmdletprovider.Include*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include)プロパティ。

- 既定では、このメソッドのオーバーライドを取得しないようにしない限り、ユーザーが非表示オブジェクト用のリーダー、 [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)プロパティに設定されて`true`します。 パスが、ユーザーが非表示の項目を表すかどうかエラーを記述する必要がありますと[System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)に設定されている`false`します。

- 実装、 [System.Management.Automation.Provider.Ipropertycmdletprovider.Clearproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty)メソッドを呼び出す必要があります[System.Management.Automation.Provider.Cmdletprovider.Shouldprocess*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)をデータ ストアに変更を加える前に、その戻り値を確認します。 このメソッドは、コンテンツをクリアするなどのシステム状態の変更前に、操作の実行の確認に使用されます。 [System.Management.Automation.Provider.Cmdletprovider.Shouldprocess*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)コマンドライン設定や ユーザー設定変数を考慮して、Windows PowerShell ランタイムで、ユーザーに変更するリソースの名前を送信します。何を表示するかを決定します。

  呼び出し後[System.Management.Automation.Provider.Cmdletprovider.Shouldprocess*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)返します`true`危険性のあるシステムの変更ができる場合、 [System.Management.Automation.Provider.Ipropertycmdletprovider.Clearproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty)メソッドを呼び出す必要があります、 [System.Management.Automation.Provider.Cmdletprovider.Shouldcontinue*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue)メソッド。 このメソッドは、危険性のある操作を続行することを示す追加のフィードバックを許可するユーザーに確認メッセージを送信します。

## <a name="attaching-dynamic-parameters-to-the-clear-itemproperty-cmdlet"></a>Clear-itemproperty コマンドレットへの動的パラメーター

`Clear-ItemProperty`コマンドレットは、実行時に動的に指定されている追加のパラメーターを必要があります。 これらの動的パラメーターを提供する Windows PowerShell プロパティ プロバイダーを実装する必要があります、 [System.Management.Automation.Provider.Ipropertycmdletprovider.Clearpropertydynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearPropertyDynamicParameters)メソッド。 このメソッドは、プロパティと、コマンドレット クラスのように属性を解析してフィールドを持つオブジェクトを返しますまたは[System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)オブジェクト。 `null`を追加する動的パラメーターがない場合、値が返されることができます。

既定の実装を次に示します[System.Management.Automation.Provider.Ipropertycmdletprovider.Clearpropertydynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearPropertyDynamicParameters) TemplateProvider.cs ファイルを Windows PowerShell によって提供されるからです。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testcmdletspropertyproviderclearpropertydynamicparameters](Msh_samplestestcmdlets#testcmdletspropertyproviderclearpropertydynamicparameters)]  -->

## <a name="building-the-windows-powershell-provider"></a>Windows PowerShell プロバイダーの構築

参照してください[登録コマンドレット、プロバイダー、およびアプリケーションをホストする方法](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)します。
参照してください[登録コマンドレット、プロバイダー、およびアプリケーションをホストする方法](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)します。

## <a name="see-also"></a>参照

[Windows PowerShell プロバイダー](./designing-your-windows-powershell-provider.md)

[デザイン、Windows PowerShell プロバイダー](./designing-your-windows-powershell-provider.md)

[オブジェクトの種類を拡張して、書式設定](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[オブジェクトの種類を拡張して、書式設定](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[登録のコマンドレット、プロバイダー、およびアプリケーションをホストする方法](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[登録のコマンドレット、プロバイダー、およびアプリケーションをホストする方法](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)