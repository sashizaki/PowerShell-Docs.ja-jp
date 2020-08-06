---
title: 拡張型システムメンバーセット
ms.date: 07/09/2020
ms.openlocfilehash: 3f4e44ed7b498bb7c4a71f7b131270ed4f2ef981
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786256"
---
# <a name="ets-member-sets"></a>メンバーセットの取得

メンバーセットを使用すると、 **PSObject**オブジェクトのメンバーを2つのサブセットに分割して、サブセットのメンバーをサブセット名でまとめて参照できるようにすることができます。 2種類のサブセットには、プロパティセットとメンバーセットが含まれます。 PowerShell がメンバーセットを使用する方法の例として、 **DefaultDisplayPropertySet**という名前の特定のプロパティセットがあります。これは、実行時に、指定された**PSObject**オブジェクトに対して表示するプロパティを決定するために使用されます。

## <a name="property-sets"></a>プロパティ セット

プロパティセットには、 **PSObject**型の任意の数のプロパティを含めることができます。 一般に、プロパティセットは、(同じ型の) プロパティのコレクションが必要な場合に使用できます。 プロパティセットは、 `PSPropertySet(System.String,System.Collections.Generic.IEnumerable{System.String})` プロパティセットの名前と参照されるプロパティの名前を指定してコンストラクターを呼び出すことによって作成されます。 作成された**PSPropertySet**オブジェクトは、セット内のプロパティを指す別名として使用できます。 [PSPropertySet](/dotnet/api/system.management.automation.pspropertyset)クラスには、次のプロパティとメソッドがあります。

- **Isinstance**プロパティ: プロパティのソースを示す**ブール**値を取得します。
- **MemberType** property: プロパティセット内のプロパティの型を取得します。
- **Name**プロパティ: プロパティセットの名前を取得します。
- **Referencedpropertynames**プロパティ: プロパティセット内のプロパティの名前を取得します。
- **TypeNameOfValue** property: このセットをプロパティセットとして定義する**PropertySet**列挙定数を取得します。
- **Value**プロパティ: **PSPropertySet**オブジェクトを取得します。値の設定もできます。
- `PSPropertySet.Copy`method: **PSPropertySet**オブジェクトの正確なコピーを作成します。
- `PSMemberSet.ToString`method: **PSPropertySet**オブジェクトを文字列に変換します。

## <a name="member-sets"></a>メンバーセット

メンバーセットには、任意の型の任意の数の拡張メンバーを含めることができます。 メンバーセットは、を呼び出すことによって作成されます。`PSMemberSet(System.String,System.Collections.Generic.IEnumerable{System.Management.Automation.PSMemberInfo})`
メンバーセットの名前と参照されるメンバーの名前を持つコンストラクター。 作成された**PSPropertySet**オブジェクトは、セット内のメンバーを指す別名として使用できます。 [Psmemberset](/dotnet/api/system.management.automation.psmemberset)クラスには、次のプロパティとメソッドがあります。

- **Isinstance**プロパティ: メンバーのソースを示す**ブール**値を取得します。
- **Members**プロパティ: メンバーセットのすべてのメンバーを取得します。
- **MemberType** property: このセットをメンバーセットとして定義**するメンバーセット列挙定数**を取得します。
- **メソッド**プロパティ: メンバーセットに含まれるメソッドを取得します。
- **Properties**プロパティ: メンバーセットに含まれるプロパティを取得します。
- **TypeNameOfValue** property: このセットをメンバーセットとして定義**するメンバーセット列挙定数**を取得します。
- **Value**プロパティ: **psmemberset セット**オブジェクトを取得します。
- `PSMemberSet.Copy`method: **Psmemberset セット**オブジェクトの正確なコピーを作成します。
- `PSMemberSet.ToString`method: **Psmemberset セット**オブジェクトを文字列に変換します。
