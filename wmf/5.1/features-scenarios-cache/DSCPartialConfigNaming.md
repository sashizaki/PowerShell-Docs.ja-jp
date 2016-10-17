---
title: "部分構成命名規則のプル"
author: jaimeo
contributor: berheabrha
translationtype: Human Translation
ms.sourcegitcommit: dfa487a11528e26faf5b0e8637b75983abe0b1c8
ms.openlocfilehash: 368c26766961e760fd2de8c99057121bea076158

---

##部分構成命名規則のプル
以前のリリースでは、部分構成の命名規則は、プル サーバー/サービスの mof ファイル名はローカル構成マネージャー設定に指定されている部分構成名に一致する必要があり、ローカル構成マネージャー設定は MOF ファイルに組み込まれている構成名に一致する必要があるというものでした。 下のスナップショットを参照してください:- •   ローカル構成設定により、あるノードに受信を許可する部分構成が定義されます。

![サンプルのメタ構成](../../images/MetaConfigPartialOne.png)

•   サンプルの部分構成定義 

```Powershell
Configuration PartialOne
{
    Node('localhost')
    {
        File test 
        {
            DestinationPath = "$env:TEMP\partialconfigexample.txt"
            Contents = 'Partial Config Example'
        }
    }
}
PartialOne
```

•   生成された MOF ファイルに組み込まれている ‘ConfigurationName’。

![生成された mof ファイルのサンプル](../../images/PartialGeneratedMof.png)

•   プル構成リポジトリの FileName 

![構成リポジトリの FileName](../../images/PartialInConfigRepository.png)

Azure Automation サービス名により、MOF ファイルが ``<ConfigurationName>.<NodeName>.mof`` として生成されました。 そのため、下の構成は PartialOne.Localhost.mof にコンパイルされます。  
これで、Azure Automation サービスから部分構成をプルできなくなりました。

```Powershell
Configuration PartialOne
{
    Node('localhost')
    {
        File test 
        {
            DestinationPath = "$env:TEMP\partialconfigexample.txt"
            Contents = 'Partial Config Example'
        }
    }
}
PartialOne
```

WMF 5.1 では、プル サーバー/サービスの部分構成の名前を ``<ConfigurationName>.<NodeName>.mof`` にできます。 さらに、コンピューターがプル サーバー/サービスから 1 つの構成をプルする場合、プル サーバー構成リポジトリの構成ドキュメントに任意の名前を与えることができます。 この名前によって、オンプレミス、Azure Automation プル サービスの両方を使用して、ノードの部分構成を柔軟に管理することができます。 たとえば、'基本の' 部分構成はローカルでプッシュし、別の部分構成を Azure Automation サービスからプルすることができます。

以下のメタ構成では、ローカルと Azure Automation サービスの両方で管理されるようにノードが設定されます。

```Powershell
  [DscLocalConfigurationManager()]
   Configuration RegistrationMetaConfig
   {
        Settings
        {
            RefreshFrequencyMins = 30;
            RefreshMode = "PULL";            
        }

        ConfigurationRepositoryWeb web
        {
            ServerURL =  $endPoint
            RegistrationKey = $registrationKey
            ConfigurationNames = $configurationName
        }

        # Partial configuration managed by Azure Automation Service.
        PartialConfiguration PartialCOnfigurationManagedByAzureAutomation
        {
            ConfigurationSource = "[ConfigurationRepositoryWeb]Web"   
        }
    
        # This partial configuration is managed locally.
        PartialConfiguration OnPremConfig
        {
            RefreshMode = "PUSH"
            ExclusiveResources = @("Script")
        }

   }

   RegistrationMetaConfig
   slcm -Path .\RegistrationMetaConfig -Verbose
 ```





<!--HONumber=Aug16_HO3-->


