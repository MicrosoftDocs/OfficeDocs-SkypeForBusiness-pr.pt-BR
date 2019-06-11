---
title: 'Lync Server 2013: Configurando a Unificação de Mensagens no Microsoft Exchange Server para funcionar com o Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Unified Messaging on Microsoft Exchange Server to work with Lync Server 2013
ms:assetid: 058da9c4-23af-4ddb-9f63-70133a8aafc6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398106(v=OCS.15)
ms:contentKeyID: 48183289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 461d822862e837879f1feb2d3f980b816aae5280
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-unified-messaging-on-microsoft-exchange-server-to-work-with-lync-server-2013"></a>Configurando a Unificação de Mensagens no Microsoft Exchange Server para funcionar com o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-11_

<div>


> [!IMPORTANT]  
> Se você quiser usar a UM (Unificação de mensagens) do Exchange para fornecer atendimento de chamada, Outlook Voice Access ou serviços de atendedor automático para usuários de Enterprise Voice, leia <A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">planejando a integração de Unificação de mensagens do Exchange no Lync Server 2013</A> no Planning documentação e siga as instruções desta seção.



</div>

Para configurar a UM (Exchange Unified Messaging) para funcionar com o Enterprise Voice, você precisará executar as seguintes tarefas:

  - Configurar certificados no servidor que executa os serviços da Unificação de mensagens (UM) do Exchange
    
    <div>
    

    > [!NOTE]  
    > Adicione todos os servidores de caixa de correio e acesso de cliente a todos os planos de discagem URI de UM SIP. Caso contrário, o roteamento de chamadas de saída não funcionará como esperado.

    
    </div>

  - Crie um ou mais planos de discagem de URI SIP do UM, juntamente com os números de telefone de acesso do Assinante, conforme necessário e, em seguida, crie os planos de discagem do Lync Server correspondentes.

  - Use o script **ExchUCUtil. ps1** para:
    
      - Crie gateways IP de UM.
    
      - Criar grupos de números coletivos da UM.
    
      - Conceder ao Lync Server 2013 permissão para ler objetos dos serviços de domínio do Active Directory da UM.

  - Criar um objeto de atendedor automático da UM.

  - Crie um objeto de acesso do Assinante.

  - Crie um URI SIP para cada usuário e associando os usuários a um plano de discagem URI do UM SIP.

<div>

## <a name="requirements-and-recommendations"></a>Requisitos e recomendações

Antes de começar, a documentação desta seção pressupõe que você implantou as seguintes funções do Exchange 2013: acesso de cliente e caixa de correio. No Microsoft Exchange Server 2013, o Exchange UM é executado como um serviço nesses servidores.

Para obter detalhes sobre a implantação do Exchange 2013, consulte a biblioteca do Exchange 2013 TechNet em[http://go.microsoft.com/fwlink/p/?LinkId=266637](http://go.microsoft.com/fwlink/p/?linkid=266637)

Observe também o seguinte:

  - Se o Exchange UM estiver instalado em várias florestas, as etapas de integração do Exchange Server deverão ser realizadas para cada floresta do UM. Além disso, cada floresta do UM deve ser configurada para confiar na floresta na qual o Lync Server 2013 é implantado, e a floresta em que o Lync Server 2013 é implantado deve ser configurada para confiar em cada floresta do UM.

  - As etapas de integração são executadas nas funções do Exchange Server em que os serviços de mensagens unificadas estão em execução e no servidor que executa o Lync Server 2013. Você deve executar as etapas de integração de Unificação de mensagens do Exchange Server antes de executar as etapas de integração do Lync Server 2013.
    
    <div>
    

    > [!NOTE]  
    > Para ver quais etapas de integração são executadas em quais servidores e com quais funções de administrador, consulte <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">processo de implantação para integrar a Unificação de mensagens locais e Lync Server 2013</A>.

    
    </div>

As seguintes ferramentas devem estar disponíveis em cada servidor que executa o Exchange UM:

  - Shell de gerenciamento do Exchange

  - O script **ExchUCUtil. ps1**, que executa as seguintes tarefas:
    
      - Cria um gateway IP de UM para cada Lync Server 2013.
    
      - Cria um grupo coletivo para cada gateway. O identificador piloto de cada número coletivo especifica o plano de discagem do URI SIP usado pelo pool de front-ends ou do servidor Standard Edition associado ao gateway.
    
      - Concede permissão do Lync Server 2013 para ler objetos do Exchange UM nos serviços de domínio do Active Directory.

</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Configurar certificados no servidor que executa o Microsoft Exchange Server Unified Messaging](lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md)

  - [Configurar a Unificação de mensagens no Microsoft Exchange para o Lync Server 2013](lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

