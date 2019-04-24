---
title: Configurar provedores para Serviço de Log Centralizado no Skype for Business Server 2015
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
description: 'Resumo: Aprenda a configurar provedores de cenário para o serviço de registro em log centralizado no Skype para Business Server 2015.'
ms.openlocfilehash: 36eb16eb1aea584e1ca28670ea75bd3a262ceb1a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32217499"
---
# <a name="configure-providers-for-centralized-logging-service-in-skype-for-business-server-2015"></a>Configurar provedores para Serviço de Log Centralizado no Skype for Business Server 2015
 
**Resumo:** Saiba como configurar provedores de cenário para o serviço de registro em log centralizado no Skype para Business Server 2015.
  
Os conceitos e a configuração de provedores de Centralized Logging Service é uma das mais importantes para entender. Mapa de Theproviders diretamente ao Skype para componentes de função de servidor de Business Server no Skype para o modelo de rastreamento do servidor de negócios. O provedor define os componentes de um Skype para Business Server 2015 que serão rastreados, o tipo de mensagens (por exemplo, fatal, erro ou aviso) para coletar e os sinalizadores (por exemplo, TF_Connection ou TF_Diag). Provedores são os componentes rastreável em cada Skype para a função de servidor de Business Server. Usando provedores, você define o nível e o tipo de rastreamento nos componentes (por exemplo, S4, SIPStack, mensagens instantâneas e presença). O provedor definido é usado em um cenário para agrupar todos os provedores de um determinado conjunto lógico que tratam de um problema específico.
  
Para executar as funções Centralized Logging Service usando o Skype do Shell de gerenciamento do servidor de negócios, você deve ser um membro do CsAdministrator ou os grupos de segurança CsServerAdministrator acesso baseado em função (RBAC) de controle ou uma função RBAC personalizada que contém um desses dois grupos. Para retornar uma lista de todas as funções RBAC (controle) de acesso baseado em função este cmdlet foi atribuído aos (incluindo qualquer funções de RBAC personalizadas que você criou a mesmo), execute o seguinte comando do Skype para Business Server Management Shell ou o Windows PowerShell Avisar:
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Por exemplo:
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

O restante deste tópico concentra-se em como definir provedores, modificar um provedor e no que contém uma definição de provedor para otimizar a solução de problemas. Há duas maneiras para emitir comandos Centralized Logging Service. Você pode usar o CLSController.exe, que está localizado por padrão no diretório C:\Program Files\Common Files\Skype for Business Server 2015\CLSAgent. Ou então, você pode usar o Skype do Shell de gerenciamento do servidor de negócios para emitir comandos do Windows PowerShell. Usando o Windows PowerShell, você pode definir novos provedores para uso em sessões de log e têm controle completo sobre sua criação, o que coletam e em que nível coletam dados.
  
> [!IMPORTANT]
> Como mencionado, os provedores são muito sofisticados. No entanto, os cenários são ainda mais sofisticados, pois incorporam todas as informações necessárias para definir e executar o rastreamento nos componentes que os provedores representam. Como os cenários são um conjunto de provedores, é possível fazer uma comparação livre com a execução de um arquivo de lote que contém centenas de comandos para coletar muitas informações e a emissão de centenas de comandos, um de cada vez, na linha de comando. 
  
Em vez de exigir que você aprofundar os detalhes dos provedores profundo, the Centralized Logging Service fornece vários cenários que já estão definidos para você. Os cenários fornecidos cobrem a maioria dos possíveis problemas que você poderá encontrar. Raramente, você talvez precise criar e definir provedores e atribuí-los a cenários. Recomendamos que você se familiarize com cada um dos cenários fornecidos antes de investigar a necessidade de criar novos provedores e cenários. Embora este artigo traga informações sobre a criação de provedores para você se familiarizar com a maneira como os cenários usam os elementos de provedor para coletar informações de rastreamento, por enquanto, não serão fornecidos detalhes sobre os provedores em si. 
  
Introduzidos em [Centralized Logging Service no Skype para negócios 2015](centralized-logging-service.md), os principais elementos da definição de um provedor para uso em um cenário são:
  
- **Provedores** Se você está familiarizado com OCSLogger, provedores são os componentes que você escolheu para informar OCSLogger que o mecanismo de rastreamento deve coletar logs do. Os provedores são os mesmos componentes e, em muitos casos, têm o mesmo nome que os componentes do OCSLogger. Se você não estiver familiarizado com OCSLogger, provedores são a função de servidor componentes específicos que the Centralized Logging Service pode coletar logs do. No caso de the Centralized Logging Service, o com o CLSAgent é a parte de arquitetura da the Centralized Logging Service que está fazendo o rastreamento dos componentes que você define a configuração de provedores.
    
- **Níveis de log** OCSLogger fornecida a opção para escolher um número de níveis de detalhes para os dados coletados. Esse recurso é uma parte integrante dos Centralized Logging Service e cenários e é definido pelo parâmetro **Type** . As seguintes opções estão disponíveis:
    
  - **Todos os** Coleta mensagens do tipo fatal, erro, aviso, detalhado e depurar informações no log de rastreamento do provedor definido.
    
  - **Fatal** Coleta somente as mensagens de rastreamento definidas como "Fatal".
    
  - **Erro** Coleta somente as mensagens de rastreamento definidas como "Erro" ou "Fatal".
    
  - **Aviso** Coleta somente as mensagens de rastreamento do tipo "Warning", "Erro" e "Fatal".
    
  - **Info** Coleta somente as mensagens de rastreamento que indicam uma mensagem informativa do provedor definido, bem fatal, erro e mensagens de aviso.
    
  - **Verbose** Coleta todas as mensagens de rastreamento de erro fatal, tipo, aviso e detalhado do provedor definido.
    
  - **Depurar** este é essencialmente um equivalente do 'Todos' - coleta de rastreamentos do tipo Fatal, erro, aviso, informações, detalhado e depurar do provedor definido.
    
- **Sinalizadores** OCSLogger fornecida a opção de escolher sinalizadores para cada provedor que definidos que tipo de informação que você pode recuperar a partir de arquivos de rastreamento. Você pode escolher os seguintes sinalizadores, com base no provedor:
    
  - **TF_Connection** Fornece as entradas do log de conexão. Esses logs incluem informações sobre as conexões estabelecidas com e a partir de um componente específico. Isso também pode incluir informações significativas no nível da rede (ou seja, para componentes sem o conceito de uma conexão).
    
  - **TF_Security** Fornece todas as entradas de log de eventos/relacionadas à segurança. Por exemplo, para SipStack, são eventos de segurança como falha na validação do domínio e falhas de autenticação/autorização do cliente.
    
  - **TF_Diag** Fornece eventos de diagnóstico que você pode usar para diagnosticar ou solucionar o componente. Por exemplo, para SipStack, são falhas de certificado e avisos/erros de DNS.
    
  - **TF_Protocol** Fornece mensagens de protocolo como mensagens SIP e o pacote de Codec de comunidade combinados.
    
  - **TF_Component** Permite o logon dos componentes especificados como parte dos provedores.
    
  - **Todos os** Define todos os sinalizadores disponíveis disponíveis para o provedor.
    
### <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a>Examine as informações sobre provedores de cenário Centralized Logging Service existentes

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
2. Para exibir a configuração dos provedores existentes, digite o seguinte:
    
   ```
   Get-CsClsScenario -Identity <scope and scenario name>
   ```

    Por exemplo, para exibir informações sobre o participante de conferência global, digite:
    
   ```
   Get-CsClsScenario -Identity "global/CAA"
   ```

    O comando exibe uma lista dos provedores com os sinalizadores, as configurações e os componentes associados. Se as informações exibidas não são suficiente ou a lista é muito longa para o formato de lista padrão do Windows PowerShell, você pode exibir informações adicionais, definindo um método de saída diferente. Para isso, digite:
    
   ```
   Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
   ```

    A saída deste comando exibe cada provedor em um formato de cinco linhas com o nome do provedor, o tipo de log, o nível de log, os sinalizadores, o GUID e a função, cada um em uma linha separada. 
    
### <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a>Para definir um novo provedor de cenário Centralized Logging Service

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
2. Um provedor de cenário consiste em um componente a ser rastreado, sinalizadores a serem usados e um nível de detalhamento a ser coletado. Para isso, digite:
    
   ```
   $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
   ```

    Por exemplo, uma definição de provedor de rastreamento que define o que será coletado e em qual nível de detalhamento do provedor Lyss seria semelhante ao seguinte:
    
   ```
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"
   ```

-Coletados pelo nível fatal, erro, aviso e informações de mensagens. Os sinalizadores usados são todos aqueles que são definidos para o provedor Lyss e incluem TF_Connection, TF_Diag e TF_Protocol.After a variável $LyssProvider estiver definida, você pode usá-lo com o cmdlet **New-CsClsScenario** para coletar rastreamentos do provedor Lyss. Para concluir a criação e a atribuição do provedor a um novo cenário, digite:

```
New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
```

Em que $LyssProvider é a variável que contém o cenário definido criado com **New-CsClsProvider**.
### <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a>Para alterar um provedor de cenário Centralized Logging Service existente

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
2. Para atualizar ou alterar a configuração de um provedor existente, digite:
    
   ```
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
   ```

    Em seguida, você atualiza o cenário para atribuir o provedor digitando o seguinte:
    
   ```
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
   ```

O resultado final do comando é que cenário site:Redmond/RedmondLyssInfo terá atualizado os sinalizadores e o nível do provedor atribuído a ele. Você pode exibir o novo cenário usando Get-CsClsScenario. Para obter detalhes, consulte [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).
> [!CAUTION]
> **New-ClsCsProvider** não faz uma verificação para determinar se os sinalizadores são válidos. Certifique-se de que os sinalizadores (por exemplo, TF_DIAG ou TF_CONNECTION) estejam grafados corretamente. Se os sinalizadores não estiverem grafados corretamente, o provedor não poderá retornar as informações de log esperadas.
  
Se você quiser adicionar mais provedores a esse cenário, digite:

```
Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}
```

Onde cada provedor definido com a diretiva Add já foi definido com o uso do processo **New-CsClsProvider**.
### <a name="to-remove-a-scenario-provider"></a>Para remover um provedor de cenário

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
2. Os cmdlets fornecidos permitem que você atualize os provedores existentes e crie novos provedores. Para remover um provedor, você precisa usar a diretiva Replace do parâmetro Provider para **Set-CsClsScenario**. A única maneira de remover completamente um provedor é substituí-lo por um provedor redefinido com o mesmo nome e usar a diretiva Update. Por exemplo, nosso provedor LyssProvider está definido com o tipo de log WPP, o nível definido para Debug e os sinalizadores definidos como TF_CONNECTION e TF_DIAG. Você precisa alterar os sinalizadores como "All". Para alterar o provedor, digite o seguinte:
    
   ```
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"
   ```

   ```
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}
   ```

3. Se você desejar remover completamente um cenário e os provedores associados a ele, digite o seguinte:
    
   ```
   Remove-CsClsScenario -Identity <scope and name of scenario>
   ```

    Por exemplo:
    
   ```
   Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
   ```

    > [!CAUTION]
    > O cmdlet **Remove-CsClsScenario** não solicita sua confirmação. O cenário será excluído junto com os provedores atribuídos a ele. Você pode recriar o cenário executando novamente os comandos usados para criá-lo inicialmente. Não há um procedimento para recuperar cenários ou provedores removidos.
  
Quando você remove um cenário usando o cmdlet **Remove-CsClsScenario**, ele é completamente removido do escopo. Para usar os cenários que você criou e os provedores que faziam parte dele, crie novos provedores e atribua-os a um novo cenário.
## <a name="see-also"></a>Confira também

[Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)
  
[New-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/new-csclsscenario?view=skype-ps)
  
[Remove-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/remove-csclsscenario?view=skype-ps)
  
[Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)
  
[New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps)
