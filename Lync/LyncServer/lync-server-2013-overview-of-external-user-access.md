---
title: 'Lync Server 2013: visão geral do acesso de usuário externo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of external user access
ms:assetid: 97aded6c-5fa3-4225-95a6-9ad094d61654
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398775(v=OCS.15)
ms:contentKeyID: 48184934
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cdf596a16fbed1cab1b622b373febb0f173344cb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216427"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-external-user-access-in-lync-server-2013"></a>Visão geral do acesso de usuário externo no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-11-07_

Nesta documentação, usamos o termo *usuário externo* para definir uma grande categoria de usuários que se comunicam com seus usuários do lync Server 2013 e Lync 2013 de fora do firewall. Usuários externos que você pode autorizar a comunicar o Lync Server 2013 com usuários internos (ou seja, os usuários que entram no Lync Server de dentro do firewall) podem incluir o seguinte:

  - **Usuários remotos**   usuários da sua organização que entram no Lync Server de fora do firewall.

  - **Usuários federados**   usuários que têm uma conta com um cliente ou uma organização de parceiro confiável, como o Lync Server 2010, o Lync Server 2013 ou o Office Communications Server 2007 R2. Os usuários federados também podem ser membros de organizações parceiras definidas usando o protocolo XMPP (Extensible Messaging and Presence Protocol) por meio do proxy XMPP no servidor de borda e no Gateway XMPP do servidor front-end ou pool. Uma relação de confiança definida, chamada de Federação, não está relacionada ou dependente da relação de confiança dos serviços de domínio do Active Directory.
    
    <div>
    

    > [!NOTE]  
    > Uma data de fim de vida de junho de 2014 para AOL e Yahoo! foi anunciado. Para obter detalhes, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">support for Public Instant Messenger Connectivity in Lync Server 2013</A>.

    
    </div>

  - **Usuários de conectividade de mensagens instantâneas públicas**   contatos que seus usuários estabelecem por meio de serviços públicos de conectividade de mensagens instantâneas (Windows Live, Yahoo\! e AOL).

  - **Usuários móveis**   usuários que são membros de sua organização que usam um telefone inteligente ou Tablet executando um cliente móvel Lync entram em sua implantação interna e podem se comunicar com outras classes de usuários. O usuário móvel usa serviços de mobilidade publicados por meio do proxy reverso para acessar a implantação interna. Para obter detalhes sobre os recursos e recursos disponíveis para o Lync Mobile, consulte as tabelas de [https://go.microsoft.com/fwlink/p/?LinkID=234777](https://go.microsoft.com/fwlink/p/?linkid=234777)comparação de clientes móveis em.

  - **Usuários anônimos**   usuários que não têm uma conta de usuário nos serviços de domínio do Active Directory da sua organização ou em um domínio federado suportado, mas que receberam convites para participar remotamente em uma conferência local.

Sua implantação de borda fornece acesso externo para os seguintes tipos de comunicação:

  - ****   Os usuários externos autorizados de IM e presença podem participar de conversas e conferências de mensagens instantâneas e podem obter informações sobre o status de presença de outro. Os usuários de provedores de serviço de mensagens instantâneas públicos podem participar de conversas de mensagens instantâneas com usuários individuais do Lync Server em sua organização e acessar informações de presença, mas não podem participar de conferências com vários participantes de IM usando o Lync Server. É estritamente comunicação ponto a ponto. Não há suporte para a transferência de arquivos para os usuários de provedores de serviço de mensagens instantâneas públicos e áudio/vídeo em comunicações ponto a ponto são compatíveis com os usuários do Windows Messenger 2011, mas não com outros usuários de provedores de serviços de mensagens instantâneas públicos.
    
    Há suporte para os protocolos SIP e XMPP. Para fornecer serviços para o XMPP, consulte [Planning for SIP, Federation XMPP e mensagens instantâneas públicas no Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md).

  - **Webconferências**   usuários externos autorizados podem participar de conferências hospedadas na sua implantação do Lync Server. Usuários remotos, usuários federados e usuários anônimos podem ser habilitados para participação em webconferências, mas os usuários públicos de IM não podem participar de conferências. Dependendo das opções selecionadas, os usuários habilitados para webconferências podem participar da área de trabalho e compartilhamento de aplicativos e podem atuar como organizadores ou apresentadores da reunião.

  - ****   Os usuários externos autorizados de conferência A/V podem participar de conferências de áudio e vídeo que sua implantação do Lync Server hospeda. O áudio/vídeo em comunicações ponto a ponto é suportado para usuários do Windows Messenger 2011, mas não para outros usuários de provedores de serviços públicos de IM.

Para controlar as comunicações, você pode configurar uma ou mais políticas que definem como os usuários dentro e fora da sua organização se comunicam entre si. Você também pode definir as configurações e aplicar políticas para usuários internos individuais ou para tipos específicos de usuários externos para controlar as comunicações com usuários externos.

Lync Server 2013 funções que são usadas para fornecer acesso externo:

**Servidor de borda**   o servidor de borda é um servidor ou um pool de servidores que executam os serviços que permitem acesso externo a mensagens instantâneas e presença, conferência, áudio/vídeo e outros serviços de mídia (por exemplo, transferência de arquivos). Opcionalmente, você pode configurar o servidor de borda para federar com outras implantações do Lync Server ou do Office Communications Server 2007 R2 e outras implantações do XMPP. O recurso opcional de conectividade de IM pública é habilitado e configurado por meio do servidor de borda.

**Diretor**   o diretor é um servidor opcional ou um pool de servidores que executa a função de diretor do Lync Server 2013 que autentica previamente as solicitações do usuário e roteia as solicitações para o servidor front-end inicial dos usuários ou o pool de front-ends, mas não hospeda nenhuma conta de usuário.

**Proxy reverso**   um proxy reverso é um termo geral para servidores especializados que publicam recursos disponíveis na rede interna e recuperam informações de clientes do recurso publicado. O Lync Server 2013 usa o proxy reverso para publicar vários recursos, como reuniões de conferência, locais de ingresso em conferência, o catálogo de endereços, expansão da lista de distribuição, download de conteúdo da reunião, atualizações de dispositivo, serviços de mobilidade e muito mais. É possível usar qualquer proxy reverso que possa atender aos requisitos para publicação dos locais de recursos necessários. O Microsoft Forefront Threat Management Gateway (TMG) 2010 é usado como um exemplo para ilustrar as regras de publicação necessárias, mas o Forefront TMG 2010 não é necessário.

<div>


> [!IMPORTANT]  
> O Lync Server 2013 oferece suporte a IPv4 e IPv6. O Windows&nbsp;Server&nbsp;2008 R2, o Windows Server 2012 e o Windows Server 2012 R2 usam uma pilha dupla que pode usar IPv4 e IPv6 simultaneamente. Isso é importante devido à natureza de transição de uma implantação que se move de IPv4 para IPv6. O IPv4 pode ser suportado em algumas áreas, onde em outras áreas da implantação, IPv6 podem ser usados. Isso é especialmente importante quando a Internet e as implantações internas estão envolvidas. Os clientes externos devem se comunicar através do proxy reverso para usar serviços como mobilidade, reuniões, download do catálogo de endereços e outros. Atualmente, o Forefront Threat Management Gateway 2010 e o Internet Security and Acceleration Server 2006 não oferecem suporte ao endereçamento IPv6, independentemente da versão do sistema operacional em que eles são implantados. Você deve planejar adequadamente em relação ao uso de IPv6 e IPv4 conforme eles se relacionam com clientes externos.



</div>

</div>

<span> </span>

</div>

</div>

</div>

