---
title: Topologia de referência do Lync Server 2013 para pequenas organizações
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
ms.openlocfilehash: 7e0171d9678d5d890cf4ecb81f6de25f9b558b05
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746861"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-small-organizations"></a>Topologia de referência para o Lync Server 2013 em pequenas organizações

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-10-07_

A topologia de referência para pequenas organizações mostra como você pode implantar uma solução robusta e altamente disponível implantando apenas três servidores que executam o Lync Server.

**Topologia de referência em pequenas organizações**

![Topologia de referência implantando três servidores diagrama](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "Topologia de referência implantando três servidores diagrama")

  - **Par de servidores de edição padrão implantados**     esta organização tem usuários do 4.000 em seu site central. A organização implantou dois servidores de edição padrão e os emparelharam para permitir alta disponibilidade e recuperação de desastres. Each server homes 2,000 users, but information about all users is synchronized between the two servers. If one goes down, an administrator can fail over those users to be served by the other server, with a minimum of disruption to users. Para obter mais informações sobre alta disponibilidade e recursos de recuperação de desastre no Lync Server 2013, consulte [planejando alta disponibilidade e recuperação de desastres no Lync server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

  - **A implantação do servidor de borda é recomendada.**    Embora a implantação de um servidor de borda não seja necessária para mensagens instantâneas, presença e conferência internas, recomendamos que isso seja possível para pequenas implantações. Você pode maximizar o investimento do Lync Server implantando um servidor de borda para fornecer serviço para os usuários que estão fora de firewalls da sua organização. Veja alguns dos benefícios:
    
      - Os próprios usuários da sua organização podem usar a funcionalidade do Lync Server, se estiverem trabalhando em casa ou estiverem em trânsito.
    
      - Os usuários da sua organização poderão convidar outros usuários para reuniões.
    
      - Se você tiver um parceiro, fornecedor ou organização do cliente que também usa o Lync Server, você pode formar uma *relação federada* com essa organização. A implantação do Lync Server reconheceria os usuários dessa organização federada, levando a uma melhor colaboração.
    
      - Seus usuários podem trocar mensagens de chat com usuários de serviços públicos de mensagens de chat, incluindo qualquer um dos itens a seguir ou todos eles\!: Windows Live, AOL, Yahoo e Google Talk. Uma licença separada pode ser necessária para conectividade de IM pública com esses serviços.
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P>A partir de 1º de setembro de 2012, a licença de assinatura de usuário da conectividade de mensagem de chat pública do Microsoft Lync ("PIC USL") não está mais disponível para compra de contratos novos ou de renovação. Os clientes com licenças ativas poderão continuar a federar-se com o Yahoo! Messenger até a data de encerramento do serviço. Uma data de fim da vida útil de junho de 2014 para AOL e Yahoo! foi anunciado. Para obter detalhes, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">suporte para conectividade de mensagens instantâneas públicas no Lync Server 2013</A>.</P>
        > <LI>
        > <P>O PIC USL é uma licença de assinatura por usuário por mês necessária para o Lync Server ou o Office Communications Server se federar com o Yahoo! Spam. A capacidade da Microsoft de oferecer esse serviço por meio do suporte do Yahoo!, o contrato subjacente para o qual está prestes a ser enrolado.</P>
        > <LI>
        > <P>Mais do que nunca, o Lync é uma ferramenta poderosa para a conexão entre organizações e pessoas ao redor do mundo. A Federação com o Windows Live Messenger não requer licenças de usuário/dispositivo adicionais além da CAL padrão do Lync. A Federação do Skype será adicionada a essa lista, permitindo que os usuários do Lync atinjam centenas de milhões de pessoas com mensagens instantâneas e voz.</P></LI></UL>

        
        </div>

  - **Sustentabilidade do site da filial.**    Esta organização está executando um programa piloto do recurso Enterprise Voice do Lync Server. Alguns usuários estão usando o Lync Server como uma única solução de voz. Alguns desses usuários pilotos de voz estão localizados no site da filial. O site de filial não tem um link de rede de longa distância (WAN) confiável para o site central, para que um aparelho de ramificação sobreviventes seja implantado. Com essa implantação, mesmo que o link de WAN fique inativo, os usuários do site de filial ainda poderão fazer e receber chamadas (tanto chamadas dentro da organização quanto chamadas PSTN), contar com a funcionalidade de caixa postal e comunicar-se por mensagens instantâneas entre duas partes. Os usuários também poderão ser autenticados quando o link de WAN estiver indisponível.

  - **Implantação de UM do Exchange.** Esta topologia de referência inclui um servidor de UM (Unificação de mensagens) do Exchange, que executa o Microsoft Exchange Server, não o Lync Server.
    
    Para obter detalhes sobre o Exchange UM, consulte [planejando a integração de Unificação de mensagens do Exchange no Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) e [integração de Unificação de mensagens do Exchange no Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) na documentação de planejamento.

  - **Servidor do Office Web Apps.** Recomendamos implantar um servidor ou farm de servidores do Office Web Apps em todas as organizações que usem webconferência. O Office Web Apps Server permite que slides do PowerPoint sejam apresentados em conferências Web. Para obter mais informações, consulte [Configurando a integração com o servidor do Office Web Apps e o Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

</div>

<span> </span>

</div>

</div>

</div>

