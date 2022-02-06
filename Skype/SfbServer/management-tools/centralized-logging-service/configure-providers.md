---
title: Configurar provedores para o Serviço de Log Centralizado Skype for Business Server 2015
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
description: 'Resumo: saiba como configurar provedores de cenário para o Serviço de Registro Em Log Centralizado Skype for Business Server 2015.'
---

# <a name="configure-providers-for-centralized-logging-service-in-skype-for-business-server-2015"></a>Configurar provedores para o Serviço de Log Centralizado Skype for Business Server 2015
 
**Resumo:** Saiba como configurar provedores de cenário para o Serviço de Log Centralizado Skype for Business Server 2015.
  
Os conceitos e a configuração de provedores no Serviço de Log Centralizado é um dos mais importantes a compreender. Osproviders mapeiam diretamente para Skype for Business Server de função de servidor no modelo Skype for Business Server de rastreamento. O provedor define os componentes de um Skype for Business Server 2015 que será rastreado, o tipo de mensagens (por exemplo, fatal, erro ou aviso) a serem coletadas e os sinalizadores (por exemplo, TF_Connection ou TF_Diag). Os provedores são os componentes rastreáveis em cada função Skype for Business Server servidor. Usando provedores, você define o nível e o tipo de rastreamento nos componentes (por exemplo, S4, SIPStack, mensagens instantâneas e presença). O provedor definido é usado em um cenário para agrupar todos os provedores de um determinado conjunto lógico que tratam de um problema específico.
  
Para executar as funções de Serviço de Log Centralizado usando o Shell de Gerenciamento do Skype for Business Server, você deve ser membro dos grupos de segurança CsAdministrator ou CsServerAdministrator de controle de acesso baseado em função (RBAC) ou uma função RBAC personalizada que contenha um desses dois grupos. Para retornar uma lista de todas as funções de controle de acesso baseado em função (RBAC) às quais este cmdlet foi atribuído (incluindo quaisquer funções RBAC personalizadas que você mesmo tenha criado), execute o seguinte comando no Shell de Gerenciamento do Skype for Business Server ou no prompt Windows PowerShell:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Por exemplo:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

O restante deste tópico se concentra em como definir provedores, modificar um provedor e o que uma definição de provedor contém para otimizar sua solução de problemas. Há duas maneiras de emitir comandos de Serviço de Log Centralizado. Você pode usar o CLSController.exe localizado, por padrão, no diretório C:\Program Files\Common Files\Skype for Business Server 2015\CLSAgent. Ou você pode usar o Shell de Gerenciamento Skype for Business Server para emitir Windows PowerShell comandos. Usando Windows PowerShell, você pode definir novos provedores para uso em suas sessões de registro em log e ter controle total sobre sua criação, o que eles coletam e em que nível eles coletam dados.
  
> [!IMPORTANT]
> Como mencionado, os provedores são muito sofisticados. No entanto, os cenários são ainda mais sofisticados, pois incorporam todas as informações necessárias para definir e executar o rastreamento nos componentes que os provedores representam. Como os cenários são um conjunto de provedores, é possível fazer uma comparação livre com a execução de um arquivo de lote que contém centenas de comandos para coletar muitas informações e a emissão de centenas de comandos, um de cada vez, na linha de comando. 
  
Em vez de exigir que você veja profundamente os detalhes dos provedores, o Serviço de Registro Em Log Centralizado fornece uma série de cenários que já estão definidos para você. Os cenários fornecidos cobrem a maioria dos possíveis problemas que você poderá encontrar. Raramente, você talvez precise criar e definir provedores e atribuí-los a cenários. Recomendamos que você se familiarize com cada um dos cenários fornecidos antes de investigar a necessidade de criar novos provedores e cenários. Embora este artigo traga informações sobre a criação de provedores para você se familiarizar com a maneira como os cenários usam os elementos de provedor para coletar informações de rastreamento, por enquanto, não serão fornecidos detalhes sobre os provedores em si. 
  
Introduzido no Serviço de Log Centralizado [no Skype for Business 2015](centralized-logging-service.md), os principais elementos da definição de um provedor para uso em um cenário são:
  
- **Provedores** Se você estiver familiarizado com o OCSLogger, os provedores são os componentes que você escolhe para dizer ao OCSLogger de que o mecanismo de rastreamento deve coletar logs. Os provedores são os mesmos componentes e, em muitos casos, têm o mesmo nome que os componentes do OCSLogger. Se você não estiver familiarizado com o OCSLogger, os provedores são componentes específicos de função de servidor dos que o Serviço de Log Centralizado pode coletar logs. No caso do Serviço de Log Centralizado, o CLSAgent é a parte arquitetônica do Serviço de Log Centralizado que está fazendo o rastreamento dos componentes que você define na configuração de provedores.
    
- **Níveis de registro em log** O OCSLogger forneceu a opção de escolher vários níveis de detalhes para os dados coletados. Esse recurso é uma parte integrante do Serviço de Log Centralizado e cenários e é definido pelo **parâmetro Type** . Você pode escolher entre estas opções:
    
  - **Todos** Coleta mensagens de rastreamento do tipo fatal, erro, aviso, detalhado e informações de depuração para o log do provedor definido.
    
  - **Fatal** Coleta apenas as mensagens de rastreamento definidas como "Fatal".
    
  - **Erro** Coleta apenas as mensagens de rastreamento definidas como "Erro" ou "Fatal".
    
  - **Aviso** Coleta apenas as mensagens de rastreamento do tipo "Aviso", "Erro" e "Fatal".
    
  - **Informações** Coleta apenas as mensagens de rastreamento que indicam uma mensagem informacional para o provedor definido, além de mensagens fatais, de erro e de aviso.
    
  - **Verbose** Coleta todas as mensagens de rastreamento do tipo fatal, erro, aviso e detalhado para o provedor definido.
    
  - **Depurar** isso é essencialmente um equivalente a 'All' - coleta rastreamentos do tipo Fatal, Error, Warning, Info, Verbose e Debug para o provedor definido.
    
- **Sinalizadores** O OCSLogger forneceu a opção de escolher sinalizadores para cada provedor que definia que tipo de informação você poderia recuperar dos arquivos de rastreamento. Você pode escolher os seguintes sinalizadores, com base no provedor:
    
  - **TF_Connection** Fornece entradas de log relacionadas à conexão. Esses logs incluem informações sobre as conexões estabelecidas com e a partir de um componente específico. Isso também pode incluir informações significativas no nível da rede (ou seja, para componentes sem o conceito de uma conexão).
    
  - **TF_Security** Fornece todos os eventos/entradas de log relacionadas à segurança. Por exemplo, para SipStack, são eventos de segurança como falha na validação do domínio e falhas de autenticação/autorização do cliente.
    
  - **TF_Diag** Fornece eventos de diagnóstico que você pode usar para diagnosticar ou solucionar problemas do componente. Por exemplo, para SipStack, são falhas de certificado e avisos/erros de DNS.
    
  - **TF_Protocol** Fornece mensagens de protocolo, como SIP e Combined Community Codec Pack.
    
  - **TF_Component** Habilita o registro em log nos componentes especificados como parte dos provedores.
    
  - **Todos** Define todos os sinalizadores disponíveis disponíveis para o provedor.
    
### <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a>Para revisar informações sobre provedores de cenários de Serviço de Log Centralizado existentes

1. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar, em** Todos os **Programas, em** Skype for Business **2015** e em Skype for Business Server **Gerenciamento**.
    
2. Para exibir a configuração dos provedores existentes, digite o seguinte:
    
   ```PowerShell
   Get-CsClsScenario -Identity <scope and scenario name>
   ```

    Por exemplo, para exibir informações sobre o participante de conferência global, digite:
    
   ```PowerShell
   Get-CsClsScenario -Identity "global/CAA"
   ```

    O comando exibe uma lista dos provedores com os sinalizadores, as configurações e os componentes associados. Se as informações exibidas não são suficientes ou a lista é muito longa para o formato de lista de Windows PowerShell padrão, você pode exibir informações adicionais definindo um método de saída diferente. Para isso, digite:
    
   ```PowerShell
   Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
   ```

    A saída deste comando exibe cada provedor em um formato de cinco linhas com o nome do provedor, o tipo de log, o nível de log, os sinalizadores, o GUID e a função, cada um em uma linha separada. 
    
### <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a>Para definir um novo provedor de cenário de Serviço de Log Centralizado

1. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar, em** Todos os **Programas, em** Skype for Business **2015** e em Skype for Business Server **Gerenciamento**.
    
2. Um provedor de cenário consiste em um componente a ser rastreado, sinalizadores a serem usados e um nível de detalhamento a ser coletado. Para isso, digite:
    
   ```PowerShell
   $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
   ```

    Por exemplo, uma definição de provedor de rastreamento que define o que será coletado e em qual nível de detalhamento do provedor Lyss seria semelhante ao seguinte:
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"
   ```

O -Level coleta mensagens fatais, de erro, de aviso e de informações. Os sinalizadores usados são todos aqueles definidos para o provedor do Lyss e incluem TF_Connection, TF_Diag e TF_Protocol.Depois que a variável $LyssProvider for definida, você poderá usá-la com o cmdlet **New-CsClsScenario** para coletar rastreamentos do provedor do Lyss. Para concluir a criação e a atribuição do provedor a um novo cenário, digite:

```PowerShell
New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
```

Em que $LyssProvider é a variável que contém o cenário definido criado com **New-CsClsProvider**.
### <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a>Para alterar um provedor de cenário do Serviço de Log Centralizado existente

1. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar, em** Todos os **Programas, em** Skype for Business **2015** e em Skype for Business Server **Gerenciamento**.
    
2. Para atualizar ou alterar a configuração de um provedor existente, digite:
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
   ```

    Em seguida, você atualiza o cenário para atribuir o provedor digitando o seguinte:
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
   ```

O resultado final do comando é que cenário site:Redmond/RedmondLyssInfo terá atualizado os sinalizadores e o nível do provedor atribuído a ele. Você pode exibir o novo cenário usando Get-CsClsScenario. Para obter detalhes, consulte [Get-CsClsScenario](/powershell/module/skype/get-csclsscenario?view=skype-ps).
> [!CAUTION]
> **New-ClsCsProvider** não faz uma verificação para determinar se os sinalizadores são válidos. Certifique-se de que os sinalizadores (por exemplo, TF_DIAG ou TF_CONNECTION) estejam grafados corretamente. Se os sinalizadores não estiverem grafados corretamente, o provedor não poderá retornar as informações de log esperadas.
  
Se você desejar adicionar mais provedores a esse cenário, digite o seguinte:

```PowerShell
Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}
```

Em que cada provedor definido com a diretiva Add já foi definido com o uso do processo **New-CsClsProvider**.
### <a name="to-remove-a-scenario-provider"></a>Para remover um provedor de cenário

1. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar, em** Todos os **Programas, em** Skype for Business **2015** e em Skype for Business Server **Gerenciamento**.
    
2. Os cmdlets fornecidos permitem que você atualize os provedores existentes e crie novos provedores. Para remover um provedor, você precisa usar a diretiva Replace do parâmetro Provider para **Set-CsClsScenario**. A única maneira de remover completamente um provedor é substituí-lo por um provedor redefinido com o mesmo nome e usar a diretiva Update. Por exemplo, nosso provedor LyssProvider está definido com o tipo de log WPP, o nível definido para Debug e os sinalizadores definidos como TF_CONNECTION e TF_DIAG. Você precisa alterar os sinalizadores para "Todos". Para alterar o provedor, digite o seguinte:
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"
   ```

   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}
   ```

3. Se você desejar remover completamente um cenário e os provedores associados a ele, digite o seguinte:
    
   ```PowerShell
   Remove-CsClsScenario -Identity <scope and name of scenario>
   ```

    Por exemplo:
    
   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
   ```

    > [!CAUTION]
    > O cmdlet **Remove-CsClsScenario** não solicita sua confirmação. O cenário será excluído junto com os provedores atribuídos a ele. Você pode recriar o cenário executando novamente os comandos usados para criá-lo inicialmente. Não há um procedimento para recuperar cenários ou provedores removidos.
  
Quando você remove um cenário usando o cmdlet **Remove-CsClsScenario**, ele é completamente removido do escopo. Para usar os cenários que você criou e os provedores que faziam parte dele, crie novos provedores e atribua-os a um novo cenário.
## <a name="see-also"></a>Confira também

[Get-CsClsScenario](/powershell/module/skype/get-csclsscenario?view=skype-ps)
  
[New-CsClsScenario](/powershell/module/skype/new-csclsscenario?view=skype-ps)
  
[Remove-CsClsScenario](/powershell/module/skype/remove-csclsscenario?view=skype-ps)
  
[Set-CsClsScenario](/powershell/module/skype/set-csclsscenario?view=skype-ps)
  
[New-CsClsProvider](/powershell/module/skype/new-csclsprovider?view=skype-ps)