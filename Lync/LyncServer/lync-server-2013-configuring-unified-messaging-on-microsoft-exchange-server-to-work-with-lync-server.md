---
title: 'Lync Server 2013: Configurando a Unificação de mensagens no Microsoft Exchange Server para funcionar com o Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Unified Messaging on Microsoft Exchange Server to work with Lync Server 2013
ms:assetid: 058da9c4-23af-4ddb-9f63-70133a8aafc6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398106(v=OCS.15)
ms:contentKeyID: 48183289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2cbb859a3cd9f49791eb7b959a59c00c38db6336
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41995966"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-unified-messaging-on-microsoft-exchange-server-to-work-with-lync-server-2013"></a>Configurando a Unificação de mensagens no Microsoft Exchange Server para funcionar com o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-11_

<div>


> [!IMPORTANT]  
> Se você quiser usar a Unificação de mensagens (UM) do Exchange para fornecer atendimento de chamadas, Outlook Voice Access ou serviços de atendedor automático para usuários do Enterprise Voice, leia <A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">planejamento para a integração de Unificação de mensagens do Exchange no Lync Server 2013</A> na documentação de planejamento e siga as instruções desta seção.



</div>

Para configurar a Unificação de mensagens (UM) do Exchange para trabalhar com o Enterprise Voice, você precisará executar as seguintes tarefas:

  - Configurar certificados no servidor que executa os serviços de Unificação de mensagens (UM) do Exchange
    
    <div>
    

    > [!NOTE]  
    > Adicione todos os servidores de acesso para cliente e caixa de correio a todos os planos de discagem URI SIP. Caso contrário, o roteamento de chamadas de saída não funcionará conforme o esperado.

    
    </div>

  - Crie um ou mais planos de discagem de URI SIP de UM, junto com os números de telefone de acesso do Assinante, conforme necessário, e crie planos de discagem do Lync Server correspondentes.

  - Use o script **ExchUCUtil. ps1** para:
    
      - Criar gateways IP da UM.
    
      - Criar grupos de busca da UM.
    
      - Conceder ao Lync Server 2013 permissão para ler objetos dos serviços de domínio de UM Active Directory.

  - Criar um objeto de atendedor automático da UM.

  - Criar um objeto de acesso ao Assinante.

  - Criar um URI SIP para cada usuário e associar usuários a um plano de discagem URI SIP de UM.

<div>

## <a name="requirements-and-recommendations"></a>Requisitos e recomendações

Antes de começar, a documentação desta seção pressupõe que você implantou as seguintes funções do Exchange 2013: acesso para cliente e caixa de correio. No Microsoft Exchange Server 2013, o UM do Exchange é executado como um serviço nesses servidores.

Para obter detalhes sobre a implantação do Exchange 2013, consulte a biblioteca do Exchange 2013 TechNet em[http://go.microsoft.com/fwlink/p/?LinkId=266637](http://go.microsoft.com/fwlink/p/?linkid=266637)

Também observe o seguinte:

  - Se o UM do Exchange estiver instalado em várias florestas, as etapas de integração do Exchange Server deverão ser realizadas para cada floresta da UM. Além disso, cada floresta de UM deve ser configurada para confiar na floresta em que o Lync Server 2013 está implantado e a floresta na qual o Lync Server 2013 está implantado deve ser configurada para confiar em cada floresta da UM.

  - As etapas de integração são realizadas nas funções de servidor do Exchange em que os serviços de Unificação de mensagens estão sendo executados e no servidor que executa o Lync Server 2013. Você deve executar as etapas de integração de Unificação de mensagens do Exchange Server antes de realizar as etapas de integração do Lync Server 2013.
    
    <div>
    

    > [!NOTE]  
    > Para ver quais etapas de integração são executadas em quais servidores e por quais funções de administrador, consulte <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">processo de implantação para integração de Unificação de mensagens local e Lync Server 2013</A>.

    
    </div>

As seguintes ferramentas devem estar disponíveis em cada servidor que executa o UM do Exchange:

  - Shell de Gerenciamento do Exchange

  - O script **exchucutil.ps1**, o qual realiza as tarefas a seguir:
    
      - Cria um gateway IP da UM para cada Lync Server 2013.
    
      - Cria um grupo de busca para cada gateway. O identificador piloto de cada grupo de busca especifica o plano de discagem de URI SIP de UM usado pelo pool de front-ends ou servidor Standard Edition associado ao gateway.
    
      - Concede permissão do Lync Server 2013 para ler objetos da UM do Exchange nos serviços de domínio do Active Directory.

</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Configurar certificados no servidor que executa a Unificação de mensagens do Microsoft Exchange Server](lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md)

  - [Configurar a Unificação de mensagens no Microsoft Exchange para o Lync Server 2013](lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

