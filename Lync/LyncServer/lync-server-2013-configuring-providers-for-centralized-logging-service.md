---
title: 'Lync Server 2013: Configurando provedores para o serviço de log centralizado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring providers for Centralized Logging Service
ms:assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688082(v=OCS.15)
ms:contentKeyID: 49733678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2428bd11e656d0f1b6295e63ca6106fa7edcbb15
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-providers-for-centralized-logging-service-in-lync-server-2013"></a>Configurando provedores para o serviço de log centralizado no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-03-19_

Os conceitos e a configuração de *provedores* no serviço de log centralizado são um dos mais importantes para entender. Os *provedores* mapeiam diretamente para os componentes da função de servidor do Lync Server no modelo de rastreamento do Lync Server. O provedor define os componentes de um Lync Server 2013 que serão rastreados, o tipo de mensagens (por exemplo, fatal, erro ou aviso) a serem coletadas e os sinalizadores (por exemplo, TF\_conexão ou TF\_diag). Provedores são os componentes rastreáveis em cada função de servidor do Lync Server. Usando provedores, você define o nível e o tipo de rastreamento nos componentes (por exemplo, S4, SIPStack, mensagens instantâneas e presença). O provedor definido é usado em um cenário para agrupar todos os provedores de um determinado conjunto lógico que tratam de um problema específico.

Para executar as funções do serviço de log centralizado usando o Shell de gerenciamento do Lync Server, você deve ser membro do grupo de segurança CsAdministrator ou do controle de acesso baseado em função do CsServerAdministrator (RBAC), ou uma função RBAC personalizada que contém um dos esses dois grupos. Para retornar uma lista de todas as funções de controle de acesso baseado em função (RBAC) às quais esse cmdlet foi atribuído (incluindo qualquer função RBAC personalizada que você criou), execute o seguinte comando no Shell de gerenciamento do Lync Server ou no prompt do Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

Por exemplo:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

O restante deste tópico concentra-se em como definir provedores, modificar um provedor e no que contém uma definição de provedor para otimizar a solução de problemas. Há duas maneiras de emitir comandos de serviço de log centralizado. Você pode usar o CLSController. exe localizado, por padrão, no\\diretório C: Arquivos de programas\\comuns\\Microsoft Lync Server 2013\\CLSAgent. Ou você pode usar o Shell de gerenciamento do Lync Server para emitir comandos do Windows PowerShell. A diferença importante é que, quando você usa CLSController. exe na linha de comando, há uma seleção finita de cenários disponíveis em que os provedores já estão definidos e não podem ser alterados, mas você pode definir o nível de log. Usando o Windows PowerShell, você pode definir novos provedores para usar em suas sessões de log e ter controle total sobre a criação, o que elas coletam e em que nível elas coletam dados.

<div class="">


> [!IMPORTANT]  
> Como mencionado, os provedores são muito sofisticados. No entanto, os cenários são ainda mais sofisticados, pois incorporam todas as informações necessárias para definir e executar o rastreamento nos componentes que os provedores representam. Como os cenários são um conjunto de provedores, é possível fazer uma comparação livre com a execução de um arquivo de lote que contém centenas de comandos para coletar muitas informações e a emissão de centenas de comandos, um de cada vez, na linha de comando.<BR>Em vez de exigir que você se aprofunde profundamente nos detalhes dos provedores, o serviço de registro em log centralizado oferece vários cenários que já estão definidos para você. Os cenários fornecidos cobrem a maioria dos possíveis problemas que você poderá encontrar. Raramente, você talvez precise criar e definir provedores e atribuí-los a cenários. Recomendamos que você se familiarize com cada um dos cenários fornecidos antes de investigar a necessidade de criar novos provedores e cenários. Embora este artigo traga informações sobre a criação de provedores para você se familiarizar com a maneira como os cenários usam os elementos de provedor para coletar informações de rastreamento, por enquanto, não serão fornecidos detalhes sobre os provedores em si.



</div>

Apresentado em [visão geral do serviço de log centralizado no Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), os principais elementos da definição de um provedor para uso em um cenário são:

  - **Provedores**   se você estiver familiarizado com o OCSLogger, os provedores são os componentes que você escolhe para OCSLogger o que o mecanismo de rastreamento deve coletar logs. Os provedores são os mesmos componentes e, em muitos casos, têm o mesmo nome que os componentes do OCSLogger. Se você não estiver familiarizado com o OCSLogger, os provedores são componentes específicos de função do servidor que o serviço de log centralizado pode coletar logs. No caso do serviço de log centralizado, o CLSAgent é a parte da arquitetura do serviço de log centralizado que está fazendo o rastreamento dos componentes definidos na configuração de provedores.

  - **Níveis de registro**   de OCSLogger fornece a opção de escolher um número de níveis de detalhes para os dados coletados. Esse recurso é uma parte integral do serviço e cenários de registro centralizado e é definido pelo parâmetro de **tipo** . As seguintes opções estão disponíveis:
    
      - **All**   coleta mensagens de rastreamento do tipo fatal, erro, aviso e informações para o log do provedor definido.
    
      - **Fatal**   coleta apenas as mensagens de rastreamento que indicam uma falha para o provedor definido.
    
      - **Erro**   coleta apenas as mensagens de rastreamento que indicam um erro para o provedor definido, além de mensagens fatais.
    
      - **Aviso**   coleta apenas as mensagens de rastreamento que indicam um aviso para o provedor definido, além de mensagens fatais e de erro.
    
      - **Info**   coleta apenas as mensagens de rastreamento que indicam uma mensagem informativa para o provedor definido, além de mensagens de aviso, de erro e fatais.
    
      - **Verbose**   coleta todas as mensagens de rastreamento do tipo fatal, erro, aviso e informações para o provedor definido.

  - **Flags**   OCSLogger ofereceu a opção de escolher sinalizadores para cada provedor que definia o tipo de informação que você pode recuperar dos arquivos de rastreamento. Você pode escolher os seguintes sinalizadores, com base no provedor:
    
      - **TF\_conexão**   fornece entradas de log relacionadas a conexão. Esses logs incluem informações sobre as conexões estabelecidas com e a partir de um componente específico. Isso também pode incluir informações significativas no nível da rede (ou seja, para componentes sem o conceito de uma conexão).
    
      - **O\_TF Security**   fornece todos os eventos/entradas de log relacionados à segurança. Por exemplo, para SipStack, são eventos de segurança como falha na validação do domínio e falhas de autenticação/autorização do cliente.
    
      - **O\_TF diag**   fornece eventos de diagnóstico que você pode usar para diagnosticar ou solucionar problemas do componente. Por exemplo, para SipStack, são falhas de certificado e avisos/erros de DNS.
    
      - **O\_protocolo**   TF fornece mensagens de protocolo como SIP e mensagens de pacote de codec de comunidade combinadas.
    
      - **O\_componente**   TF habilita o registro em log dos componentes especificados como parte dos provedores.
    
      - **Todos**   os conjuntos de todos os sinalizadores disponíveis para o provedor.

<div>

## <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a>Para revisar informações sobre provedores de cenário de serviço de log centralizado existentes

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  Para exibir a configuração dos provedores existentes, digite o seguinte:
    
        Get-CsClsScenario -Identity <scope and scenario name> 
    
    Por exemplo, para exibir informações sobre o participante de conferência global, digite:
    
        Get-CsClsScenario -Identity "global/CAA"
    
    O comando exibe uma lista dos provedores com os sinalizadores, as configurações e os componentes associados. Se as informações exibidas não forem suficientes ou se a lista for muito longa para o formato de lista padrão do Windows PowerShell, você pode exibir informações adicionais definindo um método de saída diferente. Para isso, digite:
    
        Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
    
    A saída deste comando exibe cada provedor em um formato de cinco linhas com o nome do provedor, o tipo de log, o nível de log, os sinalizadores, o GUID e a função, cada um em uma linha separada.

</div>

<div>

## <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a>Para definir um novo provedor de cenário de serviço de log centralizado

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  Um provedor de cenário consiste em um componente a ser rastreado, sinalizadores a serem usados e um nível de detalhamento a ser coletado. Para isso, digite:
    
        $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
    
    Por exemplo, uma definição de provedor de rastreamento que define o que será coletado e em qual nível de detalhamento do provedor Lyss seria semelhante ao seguinte:
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"

–Level coleta mensagens fatais, de erro, aviso e informações. Os sinalizadores usados são todos aqueles definidos para o provedor Lyss e incluem a conexão de\_TF, TF\_diag and TF\_Protocol.

Depois que a variável $LyssProvider for definida, você poderá usá-la com o cmdlet **New-CsClsScenario** para coletar rastreamentos do provedor Lyss. Para concluir a criação e a atribuição do provedor a um novo cenário, digite:

    New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

Em que $LyssProvider é a variável que contém o cenário definido criado com **New-CsClsProvider**.

</div>

<div>

## <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a>Para alterar um provedor de cenário de serviço de log centralizado existente

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  Para atualizar ou alterar a configuração de um provedor existente, digite:
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
    
    Em seguida, você atualiza o cenário para atribuir o provedor digitando o seguinte:
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

O resultado final do comando é que cenário site:Redmond/RedmondLyssInfo terá atualizado os sinalizadores e o nível do provedor atribuído a ele. Você pode exibir o novo cenário usando Get-CsClsScenario. Para obter detalhes, consulte [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario).

<div class="">


> [!WARNING]  
> <STRONG>New-ClsCsProvider</STRONG> não faz uma verificação para determinar se os sinalizadores são válidos. Certifique-se de que os sinalizadores (por exemplo, TF_DIAG ou TF_CONNECTION) estejam grafados corretamente. Se os sinalizadores não estiverem grafados corretamente, o provedor não poderá retornar as informações de log esperadas.



</div>

Se você quiser adicionar mais provedores a esse cenário, digite:

    Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}

Onde cada provedor definido com a diretiva Add já foi definido com o uso do processo **New-CsClsProvider**.

</div>

<div>

## <a name="to-remove-a-scenario-provider"></a>Para remover um provedor de cenário

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  Os cmdlets fornecidos permitem que você atualize os provedores existentes e crie novos provedores. Para remover um provedor, você precisa usar a diretiva Replace do parâmetro Provider para **Set-CsClsScenario**. A única maneira de remover completamente um provedor é substituí-lo por um provedor redefinido com o mesmo nome e usar a diretiva Update. Por exemplo, nosso provedor LyssProvider é definido com WPP como o tipo de log, o nível definido para depurar e os sinalizadores definidos\_são TF conexão\_e TF diag. Você precisa alterar os sinalizadores para "All". Para alterar o provedor, digite o seguinte:
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"

     &nbsp;
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}

3.  Se você desejar remover completamente um cenário e os provedores associados a ele, digite o seguinte:
    
        Remove-CsClsScenario -Identity <scope and name of scenario>
    
    Por exemplo:
    
        Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
    
    <div class="">
    

    > [!WARNING]  
    > O cmdlet <STRONG>Remove-CsClsScenario</STRONG> não solicita sua confirmação. O cenário será excluído junto com os provedores atribuídos a ele. Você pode recriar o cenário executando novamente os comandos usados para criá-lo inicialmente. Não há um procedimento para recuperar cenários ou provedores removidos.

    
    </div>

Quando você remove um cenário usando o cmdlet **Remove-CsClsScenario**, ele é completamente removido do escopo. Para usar os cenários que você criou e os provedores que faziam parte dele, crie novos provedores e atribua-os a um novo cenário.

</div>

<div>

## <a name="see-also"></a>Confira também


[Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario)  
[New-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/New-CsClsScenario)  
[Remove-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Remove-CsClsScenario)  
[Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario)  
[New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

