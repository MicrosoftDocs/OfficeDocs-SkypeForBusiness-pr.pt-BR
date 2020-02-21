---
title: Lync Server 2013 referência topologia para pequenas organizações
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reference topology for small organizations
ms:assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398095(v=OCS.15)
ms:contentKeyID: 48183272
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 726056b63dfa37864171a77913b5126c23b27045
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215137"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-small-organizations"></a>Topologia de referência para Lync Server 2013 em pequenas organizações

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-10-07_

A topologia de referência para pequenas organizações mostra como você pode implantar uma solução robusta e altamente disponível implantando apenas três servidores que executam o Lync Server.

**Topologia de referência para pequenas organizações**

![Diagrama da topologia de referência de implantação de três servidores](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "Diagrama da topologia de referência de implantação de três servidores")

  - **Par de servidores Standard Edition implantado**     esta organização tem 4.000 usuários no site central. A organização implantou dois servidores Standard Edition e os combinaram para permitir alta disponibilidade e recuperação de desastre. Cada servidor casa 2.000 usuários, mas as informações sobre todos os usuários são sincronizadas entre os dois servidores. Se um for desativado, um administrador pode fazer o failover desses usuários para ser servido pelo outro servidor, com o mínimo de interrupção para os usuários. Para obter mais informações sobre recursos de alta disponibilidade e recuperação de desastre no Lync Server 2013, consulte [Planning for High Availability and Disaster Recovery in Lync server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

  - **A implantação do servidor de borda é recomendada.**    Embora a implantação de um servidor de borda não seja necessária para im, presença e conferência internas, recomendamos que ele seja mesmo para pequenas implantações. Você pode maximizar seu investimento no Lync Server implantando um servidor de borda para fornecer serviço aos usuários fora dos firewalls da sua organização. Os benefícios são os seguintes:
    
      - Os usuários da sua organização podem usar a funcionalidade do Lync Server, se estiverem trabalhando de casa ou estão em trânsito.
    
      - Seus usuários podem convidar usuários de fora para participar de reuniões.
    
      - Se você tiver uma organização de parceiro, fornecedor ou cliente que também usa o Lync Server, você pode formar uma *relação federada* com essa organização. A implantação do Lync Server reconhecerá os usuários dessa organização federada, levando à melhor colaboração.
    
      - Seus usuários podem trocar mensagens instantâneas com usuários de serviços públicos de IM, incluindo qualquer uma das seguintes opções: Windows Live, AOL,\!Yahoo e Google Talk. Uma licença separada pode ser necessária para conectividade de IM pública com esses serviços.
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P>A partir de 1º de setembro de 2012, a licença de assinatura de usuário da conectividade de IM pública do Microsoft Lync ("PIC USL") não está mais disponível para compra de contratos novos ou de renovação. Os clientes com licenças ativas poderão continuar a se federar com o Yahoo! Messenger até a data de encerramento do serviço. Uma data de fim de vida de junho de 2014 para AOL e Yahoo! foi anunciado. Para obter detalhes, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">support for Public Instant Messenger Connectivity in Lync Server 2013</A>.</P>
        > <LI>
        > <P>O PIC USL é uma licença de assinatura por usuário por mês, necessária para o Lync Server ou o Office Communications Server federar-se com o Yahoo! Instantânea. A capacidade da Microsoft de fornecer esse serviço tem sido contingente o suporte da Yahoo!, o contrato subjacente para o qual está se enrolando para baixo.</P>
        > <LI>
        > <P>Mais do que nunca, o Lync é uma poderosa ferramenta para a conexão entre organizações e pessoas em todo o mundo. A Federação com o Windows Live Messenger não requer licenças de usuário/dispositivo adicionais além da CAL padrão do Lync. A Federação do Skype será adicionada à lista, permitindo que os usuários do Lync atinjam centenas de milhões de pessoas com IM e voz.</P></LI></UL>

        
        </div>

  - **Sustentabilidade do site de filial.**    Esta organização está executando um programa piloto do recurso Enterprise Voice do Lync Server. Alguns usuários estão usando o Lync Server como sua única solução de voz. Alguns desses usuários do piloto de voz estão localizados no site de filial. O site de filial não tem um link de rede de longa distância (WAN) confiável para o site central, portanto, um aparelho de filial persistente é implantado. Com isso implantado, se o link de WAN ficar inativo, os usuários no site de filial ainda poderão fazer e receber chamadas (ambas as chamadas dentro da organização e chamadas PSTN), ter funcionalidade de caixa postal e se comunicar com mensagens instantâneas de dois participantes. Os usuários ainda podem ser autenticados quando um link WAN estiver indisponível.

  - **Implantação do Exchange do UM.** Essa topologia de referência inclui um servidor de UM (Unificação de mensagens) do Exchange, que executa o Microsoft Exchange Server, e não o Lync Server.
    
    Para obter detalhes sobre a UM do Exchange, consulte [Planning for Exchange Unified Messaging Integration in Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) e [Hosted Exchange Unified Messaging Integration in Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) na documentação de planejamento.

  - **Servidor do Office Web Apps.** Recomendamos a implantação de um servidor do Office Web Apps ou do farm do servidor do Office Web Apps em todas as organizações que usam a conferência da Web. O servidor do Office Web Apps possibilita a apresentação de slides do PowerPoint em webconferências. Para obter mais informações, consulte [Configurando a integração com o servidor do Office Web Apps e o Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

</div>

<span> </span>

</div>

</div>

</div>

