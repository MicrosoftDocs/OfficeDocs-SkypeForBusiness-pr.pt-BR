---
title: 'Lync Server 2013: componentes necessários para acesso de usuário externo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components required for external user access
ms:assetid: 2d0f9817-14e7-4109-95dc-62420e3c29e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425779(v=OCS.15)
ms:contentKeyID: 48183711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a97635c66d66703fc2e9879024004a95c2c09eb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502448"
---
# <a name="components-required-for-external-user-access-in-lync-server-2013"></a>Componentes necessários para acesso de usuário externo no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-05-29_

A maioria dos componentes de borda é implantada em uma rede de perímetro. Os componentes a seguir compõem a topologia de borda da rede de perímetro. Exceto onde observado, os componentes fazem parte dos [cenários para acesso de usuário externo no Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) e estão na rede de perímetro. Os componentes de Borda incluem:

  - Servidores de Borda

  - Proxies reversos

  - Firewalls

  - Diretores (opcionais e logicamente localizados na rede interna)

  - Balanceamento de carga para Topologias de Borda Dimensionadas (balanceamento de carga DNS ou um balanceador de carga de hardware)
    
    <div>
    

    > [!IMPORTANT]  
    > O uso do balanceamento de carga de DNS em uma interface e do balanceamento de carga de hardware na outra não é suportado. É preciso usar o balanceamento de carga de hardware ou de DNS nas duas interfaces.

    
    </div>

<div>

## <a name="edge-servers"></a>Servidores de Borda

Os servidores de borda enviam e recebem tráfego de rede para os serviços oferecidos pela implantação interna por usuários externos. O Servidor de Borda executa os seguintes serviços:

  - Serviço de borda de **acesso**     O serviço de borda de acesso fornece um ponto de conexão único e confiável para o tráfego do protocolo SIP (Session Initiation Protocol) de entrada e saída.

  - Serviço de borda de **Webconferência**     O serviço de borda de Webconferência permite que usuários externos ingressem em reuniões hospedadas na sua implantação interna do Lync Server 2013.

  - Serviço de borda **A/V**     O serviço de borda A/V disponibiliza áudio, vídeo, compartilhamento de aplicativos e transferência de arquivos para usuários externos. Os usuários podem adicionar áudio e vídeo a reuniões que incluem participantes externos e podem se comunicar usando áudio e/ou vídeo diretamente com um usuário externo em sessões ponto a ponto. O Serviço de Borda A/V também fornece suporte para compartilhamento de área de trabalho e transferência de arquivo.

  - Serviço de proxy **XMPP**     O serviço de proxy do XMPP aceita e envia mensagens de XMPP (Extensible Messaging and Presence Protocol) para e de parceiros federados XMPP configurados.

Usuários externos autorizados podem acessar os servidores de borda para se conectar à sua implantação interna do Lync Server 2013, mas os servidores de borda não fornecem meios para qualquer outro acesso à rede interna.

<div>


> [!NOTE]  
> Os servidores de borda são implantados para fornecer conexões para clientes Lync habilitados e outros servidores do Microsoft Edge (como em cenários de Federação). Eles não são projetados para permitir conexões a partir de outros tipos de cliente ou servidor de ponto final. O servidor Gateway XMPP pode ser implantado para permitir conexões com parceiros XMPP configurados. O servidor de borda e Gateway XMPP somente pode suportar conexões de ponto final a partir desses tipos de clientes e federação.



</div>

</div>

<div>

## <a name="reverse-proxy"></a>Proxy reverso

O proxy reverso é necessário para o seguinte:

  - Permitir que os usuários se conectem às reuniões ou conferências discadas usando URLs simples

  - Permitir que os usuários externos baixem o conteúdo da reunião

  - Habilitar os usuários externos a expandir grupos de distribuição

  - Permitir que o usuário obtenha um certificado baseado no usuário para autenticação com base no certificado cliente

  - Permitir que os usuários remotos baixem arquivos do Servidor de Catálogo de Endereço ou enviem consultas ao serviço Address Book Web Query

  - Permitir que os usuários remotos obtenham atualizações para softwares clientes ou de dispositivo

  - Permitir que os dispositivos móveis descubram automaticamente os Servidores Front-End que oferecem serviços de mobilidade

  - Para habilitar as notificações por push para dispositivos móveis dos serviços de notificação por push da Microsoft 365, do Office 365 ou Apple push

Para obter informações adicionais relacionadas a proxies reversos e os requisitos que os proxies reverso devem atender, consulte os detalhes em [requisitos de configuração para o proxy reverso no Lync Server 2013](lync-server-2013-configuration-requirements-for-reverse-proxy.md).

<div>


> [!NOTE]  
> Os usuários externos não precisam de uma conexão VPN (rede virtual privada) à sua organização para participar de comunicações usando o Lync Server 2013. Se você tiver implementado a tecnologia VPN em sua organização e seus usuários usarem a VPN para o Lync, o tráfego de mídia (como videoconferência) poderá ser afetado de forma adversa. Considere fornecer um meio de tráfego de mídia para se conectar ao serviço de borda AV diretamente e ignorar a VPN. Para obter detalhes, consulte o artigo de blog NextHop, "Habilitando o Lync Media para ignorar um túnel VPN" em <A href="https://go.microsoft.com/fwlink/p/?linkid=256532">https://go.microsoft.com/fwlink/p/?LinkId=256532</A> .



</div>

</div>

<div>

## <a name="firewall"></a>Firewall

É possível implantar sua topologia de borda com apenas um firewall externo ou com firewalls internos e externos. As arquiteturas de cenário incluem dois firewalls. O uso de dois firewalls é a abordagem recomendada, pois garante o roteamento estrito de uma borda de rede para a outra, e protege sua implantação interna atrás de dois níveis de firewall.

</div>

<div>

## <a name="director"></a>Diretor

Um diretor é uma função de servidor opcional e separada no Lync Server 2013 que não hospeda contas de usuário ou fornece serviços de presença ou conferência. Ele serve como um servidor de próximo salto interno para o qual um servidor de Borda roteia o tráfego SIP de entrada destinado a servidores internos. O diretor autentica solicitações de entrada e as redireciona para o pool ou servidor de casa do usuário. Ao autenticar no diretor, você pode descartar solicitações de contas de usuário que são desconhecidas para a implantação.

Um diretor ajuda a isolar servidores Standard Edition e servidores front-end em pools de front-ends Enterprise Edition de tráfego mal-intencionado, como ataques de negação de serviço (DoS). Se a rede estiver inundada com tráfego externo inválido nesse ataque, o tráfego terminará no diretor. Para obter detalhes sobre o uso de diretores, consulte [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md).

</div>

<div>

## <a name="see-also"></a>Confira também


[Requisitos do balanceador de carga de hardware para Lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

