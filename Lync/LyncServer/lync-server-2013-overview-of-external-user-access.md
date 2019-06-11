---
title: 'Lync Server 2013: Visão geral de acesso de usuário externo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of external user access
ms:assetid: 97aded6c-5fa3-4225-95a6-9ad094d61654
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398775(v=OCS.15)
ms:contentKeyID: 48184934
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a527df5a3bc7b296d17860c7a02876dbc31fbc4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825517"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-external-user-access-in-lync-server-2013"></a>Visão geral de acesso de usuário externo no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-11-07_

Nesta documentação, usamos o termo *usuário externo* para definir uma grande categoria de usuários que se comunicam com os usuários do lync Server 2013 e do Lync 2013 de fora do firewall. Os usuários externos que você pode autorizar a comunicar ao Lync Server 2013 com usuários internos (ou seja, os usuários que se conectarem ao Lync Server de dentro do firewall) podem incluir o seguinte:

  - **Usuários remotos**   usuários da sua organização que se conectarem ao Lync Server de fora do firewall.

  - **Usuários federados usuários**   que têm uma conta com uma organização de cliente ou parceiro confiável, como o Lync Server 2010, o Lync Server 2013 ou o Office Communications Server 2007 R2. Os usuários federados também podem ser membros de organizações parceiras definidas usando o protocolo de mensagens extensíveis (XMPP) por meio do proxy XMPP no servidor de borda e do XMPP gateway do servidor ou pool de front-end. Uma relação de confiança definida, chamada de Federação, não está relacionada a ou dependente de uma relação de confiança dos serviços de domínio Active Directory.
    
    <div>
    

    > [!NOTE]  
    > Uma data de fim da vida útil de junho de 2014 para AOL e Yahoo! foi anunciado. Para obter detalhes, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">suporte para conectividade de mensagens instantâneas públicas no Lync Server 2013</A>.

    
    </div>

  - **Usuários de conectividade de mensagens instantâneas públicas usuários**   contatos que seus usuários estabelecem por meio de serviços públicos de conectividade de mensagens instantâneas (Windows Live, Yahoo\! e AOL).

  - **Usuários móveis usuários**   que são membros da sua organização que usam um telefone inteligente ou Tablet executando um cliente Lync móvel entram em sua implantação interna e podem se comunicar com as outras classes de usuários. O usuário móvel usa os serviços de mobilidade publicados por meio do proxy reverso para acessar a implantação interna. Para obter detalhes sobre os recursos e as funcionalidades disponíveis para o Lync Mobile, consulte as tabelas [http://go.microsoft.com/fwlink/p/?LinkID=234777](http://go.microsoft.com/fwlink/p/?linkid=234777)de comparação de clientes móveis em.

  - **Usuários anônimos**   usuários que não têm uma conta de usuário nos serviços de domínio do Active Directory da sua organização ou em um domínio federado com suporte, mas que receberam convites para participarem remotamente em uma conferência local.

Sua implantação de borda oferece acesso externo para os seguintes tipos de comunicação:

  - **Mensagens instantâneas e de presença**   os usuários externos autorizados podem participar de conversas e conferências de mensagens instantâneas, e eles podem obter informações sobre o status de presença de um outro. Os usuários de provedores de serviços públicos de mensagens instantâneas podem participar de conversas de mensagens instantâneas com usuários individuais do Lync Server em sua organização e acessar as informações de presença, mas não podem participar de conferências com vários participantes usando o Lync Server. É estritamente comunicação ponto a ponto. Não há suporte para a transferência de arquivos para os usuários de provedores de serviços públicos de mensagens instantâneas e áudio/vídeo em comunicações ponto a ponto são compatíveis com usuários do Windows Messenger 2011, mas não para outros usuários de provedores de serviços públicos de mensagens instantâneas.
    
    Há suporte para os protocolos SIP e XMPP. Para fornecer serviços para o XMPP, consulte [planejando o SIP, a Federação do XMPP e mensagens instantâneas públicas no Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md).

  - **Webconferência**   os usuários externos autorizados podem participar de conferências hospedadas em sua implantação do Lync Server. Usuários remotos, usuários federados e usuários anônimos podem ser habilitados para a participação na Web conferência, mas os usuários de mensagens de chat públicas não podem participar de conferências. Dependendo das opções que você selecionar, os usuários habilitados para Webconferência podem participar do compartilhamento de área de trabalho e aplicativos e podem atuar como organizadores ou apresentadores da reunião.

  - **A/V Conferência**   usuários externos autorizados podem participar de conferências de áudio e vídeo que a implantação do Lync Server hospeda. O áudio/vídeo em comunicações ponto a ponto é compatível com usuários do Windows Messenger 2011, mas não para outros usuários de provedores de serviços públicos de mensagens instantâneas.

Para controlar a comunicação, você pode configurar uma ou mais políticas que definem como os usuários dentro e fora da sua organização se comunicam. Você também pode definir as configurações e aplicar políticas para usuários internos individuais ou para tipos específicos de usuários externos para controlar a comunicação com usuários externos.

Funções do Lync Server 2013 usadas para fornecer acesso externo:

**Servidor de borda**   o servidor de borda é um servidor ou um pool de servidores que executam os serviços que permitem acesso externo a mensagens instantâneas e presença, conferência, áudio/vídeo e outros tipos de mídia (por exemplo, transferência de arquivos). Opcionalmente, você pode configurar o servidor de borda para federar outras implantações do Lync Server ou do Office Communications Server 2007 R2 e outras implantações do XMPP. O recurso opcional de conectividade de mensagem instantânea pública está habilitado e configurado por meio do servidor de borda.

**Director**   o diretor é um servidor opcional ou um pool de servidores que executa a função de diretor do Lync Server 2013, que autentica previamente solicitações de usuário e roteia solicitações para o servidor front-end do usuário ou o pool de front-end, mas não hospeda nenhuma conta de usuário.

**Proxy reverso**   um proxy reverso é um termo genérico para servidores especializados que publicam recursos disponíveis na rede interna e recuperam informações para clientes do recurso publicado. O Lync Server 2013 usa o proxy inverso para publicar vários recursos, como reuniões de conferência, locais de ingresso em conferência, catálogo de endereços, expansão da lista de distribuição, download de conteúdo da reunião, atualizações de dispositivo, serviços de mobilidade e muito mais. Qualquer proxy reverso que possa atender aos requisitos para publicação dos locais de recursos necessários pode ser usado. O Microsoft Forefront Threat Management Gateway (TMG) 2010 é usado como um exemplo para a finalidade de ilustrar as regras de publicação necessárias, mas o Forefront TMG 2010 não é necessário.

<div>


> [!IMPORTANT]  
> O Lync Server 2013 dá suporte a IPv4 e IPv6. O Windows&nbsp;Server&nbsp;2008 R2, o Windows Server 2012 e o Windows Server 2012 R2 usam uma pilha dupla que pode usar o IPv4 e o IPv6 simultaneamente. Isso é importante porque a natureza Transitional de uma implantação está migrando do IPv4 para o IPv6. O IPv4 pode ser compatível em algumas áreas, em que em outras áreas da implantação, o IPv6 pode ser usado. Isso é especialmente importante quando a Internet e as implantações internas se preocupam. Os clientes externos devem se comunicar pelo proxy reverso para usar serviços como mobilidade, reuniões, download do catálogo de endereços e outros. Atualmente, o Forefront Threat Management Gateway 2010 e o Internet Security and Acceleration Server 2006 não dão suporte ao endereçamento IPv6, independentemente da versão do sistema operacional em que eles são implantados. Você deve planejar adequadamente em relação ao uso do IPv6 e do IPv4, pois eles estão relacionados a clientes externos.



</div>

</div>

<span> </span>

</div>

</div>

</div>

