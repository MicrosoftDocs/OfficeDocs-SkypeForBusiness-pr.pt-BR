---
title: Gerenciar configurações do Serviço de Log Centralizado no Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
description: 'Resumo: Saiba como recuperar, atualizar e criar definições de configuração para o serviço de registro em log centralizado no Skype para Business Server 2015.'
ms.openlocfilehash: 0c4d03119a61fccd062e650c38815bee069852f5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a>Gerenciar configurações do Serviço de Log Centralizado no Skype for Business Server 2015
 
**Resumo:** Saiba como recuperar, atualizar e criar definições de configuração para o serviço de registro em log centralizado no Skype para Business Server 2015.
  
The Centralized Logging Service é controlado e configurado pelas configurações e os parâmetros que são criados e usados pelo Centralized Logging Service controlador (CLSController) para enviar comandos ao (de agente do serviço de registro em log centralizados do computador individual Com o CLSAgent). O agente processa os comandos enviados a ele e (no caso de um comando Iniciar) usa a configuração dos cenários, provedores, tamanho de log, duração de rastreamento e sinalizadores para começar a coletar logs de rastreamento de acordo com as informações de configuração fornecidas.
  
> [!IMPORTANT]
>  Nem todos os cmdlets do Windows PowerShell listados para o serviço de registro em log centralizados servem para uso com Skype para implantações em instalações de negócios Server 2015. Embora eles podem aparecer funcione, os cmdlets a seguir não foram projetados para funcionar com Skype para implantações em instalações de 2015 do servidor de negócios:

-  **Cmdlets CsClsRegion:** [Get-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)e [Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps). 
-  **Cmdlets CsClsSearchTerm:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) e [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).  
-  **Cmdlets CsClsSecurityGroup:** [Get-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps), [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)e [Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps). 

As configurações definidas nesses cmdlets não prejudicar ou causar qualquer comportamento adverso, mas eles foram projetados para uso com o Microsoft Office 365 e não produzirá os resultados esperados em implantações de local. Isso não quer dizer que não há uso para esses cmdlets em implantações locais, mas sua utilização é um tópico mais avançado, que não é abordado nesta documentação.
  
The Centralized Logging Service pode ser executado em um escopo que inclui um único computador ou um pool de computadores, em um escopo de site (ou seja, um site definido como o site Redmond que contém uma coleção de computador e os pools na sua implantação) ou em um escopo global (ou seja todos os computadores e pools na sua implantação).
  
Para configurar o escopo do serviço de registro em log centralizado em log usando o Skype do Shell de gerenciamento do servidor de negócios, você deve ser um membro do CsAdministrator ou os grupos de segurança CsServerAdministrator acesso baseado em função (RBAC) de controle ou uma função RBAC personalizada que contém um desses dois grupos. Para retornar uma lista de todas as funções RBAC que este cmdlet foi atribuído ao (incluindo qualquer funções de RBAC personalizadas que você criou a mesmo), execute o seguinte comando do Skype para Business Server Management Shell ou o prompt do Windows PowerShell:
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

Por exemplo:
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> Há algumas diferenças fundamentais entre os comandos de linha de comando que podem ser executados no Windows PowerShell ou CLSController. Windows PowerShell fornece um método avançado para configurar e definir cenários e reutilizar esses cenários de forma significativa para seus cenários de solução de problemas. Embora o CLSController forneça uma maneira rápida e eficiente para emitir comandos e obter resultados, o conjunto de comandos do CLSController está limitado aos comandos finitos que você tem disponível na linha de comando. Ao contrário de cmdlets do Windows PowerShell, CLSController não é possível definir novos cenários, gerenciar escopo em um site ou nível global e muitos outras limitações de um conjunto de comandos finita que não pode ser configurado dinamicamente. Enquanto CLSController fornece os meios para execução fast, o Windows PowerShell fornece um meio para estender a funcionalidade de Centralized Logging Service, além do que é possível com CLSController. 
  
Escopo de um único computador pode ser definido durante a execução de um [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps), [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), [Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps), [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) e [Update-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) comando usando o parâmetro-Computers. -Computadores parâmetro aceita uma lista separada por vírgulas de nomes de domínio totalmente qualificados (FQDNs) para o computador de destino.
  
> [!TIP]
> Você também pode definir - Pools e uma lista separada por vírgulas de pools que você deseja executar os comandos de log em. 
  
Escopos de site e Global forem definidos nos cmdlets **New -**, **Set -**e **Remove -** Centralized Logging Service. Os exemplos a seguir demonstram como definir o escopo global ou de um site.
  
> [!IMPORTANT]
> Os comandos mostrados podem conter parâmetros e conceitos que são abordados em outras seções. Os comandos de exemplo destinam-se a demonstrar o uso do **-Identity** parâmetro para definir o escopo e os outros parâmetros são incluídos para preservar a integridade e para especificar o escopo. Para obter detalhes sobre os cmdlets **Set-CsClsConfiguration** , consulte [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) na documentação operações.
  
### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>Para recuperar a configuração atual do Centralized Logging Service

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
2. Digite o seguinte no prompt de linha de comando:
    
  ```
  Get-CsClsConfiguration
  ```

Use os cmdlets **New-CsClsConfiguration** e **Set-CsClsConfiguration** para criar uma nova configuração ou para atualizar uma configuração existente. Quando você executar **Get-CsClsConfiguration**, ele exibe informações similares a seguinte captura de tela, onde a implantação atualmente tem a configuração Global, mas nenhuma configuração de site definida:
  
![Amostra de saída do Get-CsClsConfiguration.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)
  
### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>Para recuperar a configuração atual do serviço de log centralizado em log do repositório local do computador

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
2. Digite o seguinte no prompt de linha de comando:
    
  ```
  Get-CsClsConfiguration -LocalStore
  ```

Quando você usa o primeiro exemplo onde **Get-CsClsConfiguration** não especifica nenhum parâmetro, as referências de comando repositório de gerenciamento Central para os dados. Se você especificar o parâmetro - LocalStore, o comando referencia o computador LocalStore em vez de repositório de gerenciamento Central.
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>Para recuperar uma lista de cenários definidos no momento

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
2. Digite o seguinte no prompt de linha de comando:
    
  ```
  Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
  ```

    Por exemplo, para recuperar os cenários definidos no escopo global:
    
  ```
  Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
  ```

O cmdlet **Get-CsClsConfiguration** sempre exibe os cenários que fazem parte da configuração de um determinado escopo. Na maioria dos casos, nem todos os cenários são exibidos e estão truncados. O comando usado aqui lista todos os cenários e as informações parciais sobre quais provedores, configurações e sinalizadores são usados.
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Para atualizar um escopo global para o serviço de registro em log centralizado em log usando o Windows PowerShell

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
2. Digite o seguinte no prompt de linha de comando:
    
  ```
  Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
  ```

  Por exemplo:
    
  ```
  Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
  ```

O comando diz ao CLSAgent em cada computador e pool na implantação para definir o tamanho do valor de sobreposição no arquivo de rastreamento para 40 megabytes. Os computadores e pools em todos os sites são afetados pelo comando, e definirão seu valor configurado de sobreposição de log de rastreamento para 40 megabytes.
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Para atualizar um escopo de site para o serviço de registro em log centralizado em log usando o Windows PowerShell

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
2. Digite o seguinte no prompt de linha de comando:
    
  ```
  Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
  ```

  Por exemplo:
    
  ```
  Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40  
  ```

> [!NOTE]
> Como observado no exemplo, o local padrão dos arquivos de log é %TEMP%\Tracing. No entanto, como é o CLSAgent que está gravando o arquivo, e o CSLAgent é executado no Serviço de Rede, a variável %TEMP% expande para %WINDIR%\ServiceProfiles\NetworkService\AppData\Local. 
  
O comando diz ao CLSAgent em cada computador e pool no site da Redmond para definir o tamanho do valor de sobreposição no arquivo de rastreamento para 40 megabytes. Os computadores e pools em outros sites não serão afetados pelo comando, e continuarão a usar o valor atualmente configurado de sobreposição de log de rastreamento definido pelo padrão (20 megabytes) ou durante o início da sessão de log.
### <a name="to-create-a-new-centralized-logging-service-configuration"></a>Para criar uma nova configuração de Centralized Logging Service

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
2. Digite o seguinte no prompt de linha de comando:
    
  ```
  New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
  ```

    > [!NOTE]
    > New-CsClsConfiguration fornece acesso a um grande número de definições de configuração adicionais. Para obter detalhes sobre as opções de configuração, consulte [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) e [Noções básicas sobre Centralized Logging Service definições de configuração](http://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx). 
  
Por exemplo, para criar uma nova configuração que defina uma pasta de rede para arquivos de cache, o período de tempo de sobreposição dos arquivos de log e tamanho de sobreposição dos arquivos de log, você deverá digitar:
    
  ```
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

Você deverá planejar cuidadosamente a criação de novas configurações e como definir novas propriedades para o serviço de registro em log centralizado. Você deve ter cuidado ao fazer alterações e ter certeza que compreende o impacto da sua capacidade de registrar cenários de problema corretamente. Você deve fazer alterações na configuração que melhorarão sua capacidade de gerenciar logs para um tamanho e período de sobreposição que permita resolver problemas, quando surgirem.
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>Para remover uma configuração Centralized Logging Service existente

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
2. Digite o seguinte no prompt de linha de comando:
    
  ```
  Remove-CsClsConfiguration -Identity <scope and name>
  ```

Por exemplo, para remover uma configuração de Centralized Logging Service que você criou para aumentar o tempo de sobreposição de arquivo de log, aumentar o tamanho de arquivo de log de sobreposição e definir o local de cache do arquivo de log para um compartilhamento de rede da seguinte maneira:
    
  ```
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> Esta é a nova configuração que foi criada no procedimento "para criar uma nova configuração de serviço de registro em log centralizado." 
  
Se decidir remover a configuração no nível do site, o site usará as configurações globais.
## <a name="see-also"></a>Consulte também

#### 

[Configurar provedores para Centralized Logging Service no Skype para Business Server 2015](configure-providers.md)
  
[Configurar cenários para o serviço de registro em log centralizado no Skype para Business Server 2015](configure-scenarios.md)
#### 

[Serviço de registro em log centralizado no Skype para negócios 2015](centralized-logging-service.md)
#### 

[Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)
  
[Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)
  
[New-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)
  
[Remove-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)

