---
title: 'Lync Server 2013: Componentes obrigatórios para acesso de usuário externo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components required for external user access
ms:assetid: 2d0f9817-14e7-4109-95dc-62420e3c29e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425779(v=OCS.15)
ms:contentKeyID: 48183711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 895f2d4837eb465f0eead2b70cf1d603504699ba
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836518"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-required-for-external-user-access-in-lync-server-2013"></a>Componentes obrigatórios para acesso de usuário externo no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-05-29_

A maioria dos componentes de Borda é implantada em uma rede de perímetro. Os componentes a seguir compõem a topologia de borda da rede de perímetro. Exceto onde observado, os componentes fazem parte dos [cenários para o acesso de usuários externos no Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) e na rede de perímetro. Os componentes de Borda incluem o seguinte:

  - Edge Servers

  - Reverse proxies

  - Firewalls

  - Diretores (opcional e logicamente localizado na rede interna)

  - Balanceamento de carga para Topologias de Borda Dimensionadas (balanceamento de carga DNS ou um balanceador de carga de hardware)
    
    <div>
    

    > [!IMPORTANT]  
    > O uso do balanceamento de carga de DNS em uma interface e do balanceamento de carga de hardware na outra não é suportado. É preciso usar o balanceamento de carga de hardware ou de DNS nas duas interfaces.

    
    </div>

<div>

## <a name="edge-servers"></a>Servidores de Borda

Os servidores de borda enviam e recebem tráfego de rede para os serviços oferecidos pela implantação interna por usuários externos. O servidor de borda executa os seguintes serviços:

  - **Serviço de borda de acesso**   o serviço de borda de acesso fornece um ponto de conexão confiável e único para tráfego de protocolo de iniciação de sessão (SIP) de entrada e saída.

  - **Serviço de borda**   de Webconferência o serviço de borda de Webconferência permite que usuários externos ingressem em reuniões hospedadas em sua implantação interna do Lync Server 2013.

  - **Serviço de borda**   a/v o serviço de borda a/v torna o áudio, o vídeo, o compartilhamento de aplicativos e a transferência de arquivos disponíveis para usuários externos. Seus usuários podem adicionar áudio e vídeo a reuniões que incluam participantes externos, e eles podem se comunicar usando áudio e/ou vídeo diretamente com um usuário externo em sessões ponto a ponto. O serviço de borda a/V também oferece suporte para compartilhamento de área de trabalho e transferência de arquivos.

  - **Serviço de proxy XMPP**   o serviço de proxy do XMPP aceita e envia mensagens de protocolo de presença e mensagens extensível (XMPP) para e a partir de parceiros federados XMPP configurados.

Usuários externos autorizados podem acessar os servidores de borda para se conectar à implantação interna do Lync Server 2013, mas os servidores de borda não fornecem meios para qualquer outro acesso à rede interna.

<div>


> [!NOTE]  
> Os servidores de borda são implantados para fornecer conexões para clientes Lync habilitados e outros servidores Microsoft Edge (como em cenários de Federação). Elas não são projetadas para permitir conexões de outros tipos de cliente ou servidor de ponto final. O servidor de Gateway XMPP pode ser implantado para permitir conexões com os parceiros do XMPP configurados. O servidor de borda e o Gateway XMPP só podem dar suporte a conexões de ponto de extremidade desses tipos de cliente e de Federação.



</div>

</div>

<div>

## <a name="reverse-proxy"></a>Proxy reverso

O proxy reverso é necessário para o seguinte:

  - Para permitir que os usuários se conectem a reuniões ou conferências discadas usando URLs simples

  - Para habilitar usuários externos para baixar o conteúdo da reunião

  - Para permitir que usuários externos expandam grupos de distribuição

  - Para permitir que o usuário obtenha um certificado baseado em usuário para autenticação baseada em certificado de cliente

  - Para habilitar usuários remotos a baixar arquivos do servidor de catálogo de endereços ou enviar consultas para o serviço de consulta à Web do catálogo de endereços

  - Para permitir que os usuários remotos obtenham atualizações para software cliente e dispositivo

  - Para habilitar dispositivos móveis para detectar automaticamente servidores front-end que oferecem serviços de mobilidade

  - Para habilitar as notificações por push para dispositivos móveis do Office 365 ou dos serviços de notificação por push da Apple

Para obter informações adicionais relacionadas a proxies invertidos e os requisitos que os proxies inversos devem atender, consulte os detalhes em [requisitos de configuração para o proxy inverso no Lync Server 2013](lync-server-2013-configuration-requirements-for-reverse-proxy.md).

<div>


> [!NOTE]  
> Os usuários externos não precisam de uma conexão de rede virtual privada (VPN) à sua organização para participar de comunicações usando o Lync Server 2013. Se você implementou a tecnologia VPN em sua organização e seus usuários usam a VPN para o Lync, o tráfego de mídia (como videoconferência) pode ser afetado negativamente. Você deve considerar o fornecimento de um meio para tráfego de mídia para se conectar ao serviço de borda de AV diretamente e ignorar a VPN. Para obter detalhes, consulte o artigo sobre o blog NextHop, "Ativando o Lync Media para ignorar um <A href="http://go.microsoft.com/fwlink/p/?linkid=256532">http://go.microsoft.com/fwlink/p/?LinkId=256532</A>túnel VPN".



</div>

</div>

<div>

## <a name="firewall"></a>Firewall

Você pode implantar a topologia de borda com apenas um firewall externo ou firewalls internos e externos. As arquiteturas de cenário incluem dois firewalls. Usar dois firewalls é a abordagem recomendada porque garante um roteamento estrito de uma borda de rede para a outra e protege sua implantação interna atrás de dois níveis de firewall.

</div>

<div>

## <a name="director"></a>Diretor

Um diretor é uma função de servidor opcional separada no Lync Server 2013 que não hospeda contas de usuário nem fornece serviços de presença ou conferência. Ele funciona como um servidor de um próximo salto interno ao qual um servidor de Borda roteia o tráfego SIP de entrada destinado para servidores internos. O diretor autentica solicitações de entrada e as redireciona para o pool ou servidor primário do usuário. Ao autenticar no director, você pode descartar solicitações de contas de usuários desconhecidas para a implantação.

Um diretor ajuda a isolar servidores de front-end do Enterprise Edition em pools front-end do Enterprise Edition contra tráfego mal-intencionado, como ataques de negação de serviço (DoS). Se a rede estiver inundada com tráfego externo inválido nesse tipo de ataque, o tráfego terminará no diretor. Para obter detalhes sobre o uso de directors, consulte [cenários do diretor do Lync Server 2013](lync-server-2013-scenarios-for-the-director.md).

</div>

<div>

## <a name="see-also"></a>Confira também


[Requisitos do balanceador de carga do hardware para Lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

