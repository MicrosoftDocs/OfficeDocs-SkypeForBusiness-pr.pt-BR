---
title: 'Lync Server 2013: Topologia e componentes para mobilidade'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Topologies and components for mobility
ms:assetid: be3cae7a-095d-4785-91ba-6fac99eba92a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690037(v=OCS.15)
ms:contentKeyID: 48185282
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 537eda14f2587e06bd8a1112f2a6a44299b0b78e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-mobility-in-lync-server-2013"></a>Topologia e componentes para mobilidade no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-17_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Para dar suporte a aplicativos móveis do Lync em dispositivos móveis, o Lync Server 2013 oferece três serviços: Lync Server 2013 MCX Mobility Service, Lync Server 2013 autodiscover Service e Lync Server 2013 Push Notification Service. As atualizações cumulativas do Lync Server 2013:2013 de fevereiro adicionam um serviço gratuito, mas avançado, para clientes móveis do Lync 2013 — suporte à mobilidade por meio do uso da API da Web de comunicação unificada ou UCWA. Esta seção descreve brevemente esses componentes e identifica as topologias do Lync Server 2013 que dão suporte à mobilidade.

<div>


> [!NOTE]  
> Serviços de mobilidade também estão disponíveis em implantações híbridas. Você não é obrigado a implantar serviços para oferecer suporte à mobilidade se seus usuários estiverem em casa online. Você precisa definir uma configuração para o serviço de descoberta automática para permitir que os usuários móveis encontrem sua identidade online.



</div>

<div>


> [!IMPORTANT]  
> Se você estiver planejando qualquer conectividade de usuário externa (por exemplo, Federação, acesso de usuário externo ou recursos de mobilidade), você deve usar servidores de borda com o servidor Standard Edition e o servidor front-end ou o pool de front-end. O servidor Standard Edition e o servidor front-end ou o pool de front-end não têm os componentes necessários para permitir que os usuários externos acessem sua implantação interna ou para que a implantação interna se comunique com os usuários externos. Para todos os cenários que incluem usuários externos que colaboram ou se comunicam com usuários internos, incluindo mobilidade, você deve implantar pelo menos um servidor de borda e um proxy reverso.<BR>A <EM>notificação por push</EM> usa um tipo de Federação para os serviços do Lync Online, que hospeda a casa de compensação de notificação por push (PNCH). A notificação por Push se refere a alertas sonoros, alertas na tela (texto) e selos que são enviados por aplicativos para o iPhone, iPad e Windows Phone da Apple, quando o dispositivo móvel está inativo. O PNCH recebe notificações por push do Lync Server. Quando o PNCH recebe uma notificação de uma mensagem, o PNCH encaminha uma notificação para clientes móveis por meio do serviço de notificação por push do Apple ou do Lync Server 2013, com base no cliente móvel para o qual a mensagem se destina. O PNCH é um serviço obrigatório para esses clientes móveis. Para federar o Lync Online, o PNCH usa servidores de borda e certificados para garantir confidencialidade e autenticação, políticas e registros DNS (Domain Name System) configurados corretamente. Os clientes móveis do Lync Symbian e Android baseados em Android não usam o PNCH. Para obter detalhes sobre o planejamento e a implantação de servidores de borda, consulte <A href="lync-server-2013-planning-for-external-user-access.md">planejando o acesso de usuários externos no Lync server 2013</A> e implantando o <A href="lync-server-2013-deploying-external-user-access.md">acesso de usuários externos no Lync Server 2013</A>.<BR>Os clientes móveis do Lync 2013 para dispositivos Apple introduzidos com as atualizações cumulativas do Lync Server 2013: fevereiro de 2013 não usam mais a notificação por Push ou a casa de compensação de notificação por push (PNCH). Os clientes móveis do Lync 2013 no Windows Phone ainda usam a notificação por push e o (PNCH).



</div>

<div>

## <a name="mobility-components"></a>Componentes da mobilidade

Os serviços que dão suporte à mobilidade são os seguintes:

  - **A API da Web de comunicação unificada do Lync Server 2013 (UCWA)**   fornece serviços para comunicações em tempo real com clientes móveis e Web no Lync Server 2013. Ao implantar as atualizações cumulativas do Lync Server 2013:2013 de fevereiro para o servidor e diretor de front-end, a instalação cria um diretório virtual nos serviços Web internos e externos (Ucwa). Um componente da Web que faz parte do diretório virtual Ucwa aceita chamadas de clientes habilitados para UCWA. Os aplicativos cliente se comunicam em uma interface REST para presença, contatos, mensagens instantâneas, VoIP, videoconferência e colaboração. O UCWA usa um canal baseado em P para enviar eventos, como uma chamada recebida, mensagem de chat recebida ou uma mensagem para o aplicativo cliente.
    
    <div>
    

    > [!NOTE]  
    > A transferência de estado <EM>REST</EM> ou Representational é um estilo arquitetônico de software para sistemas distribuídos que foram amplamente adotados em muitos formatos e é bem adequado aos requisitos dos serviços Web em geral.

    
    </div>

  - **Serviço de mobilidade do Lync Server 2013 (MCX)**   esse serviço é compatível com a funcionalidade do Lync, como mensagens instantâneas (IM), presença e contatos, em dispositivos móveis. O serviço de mobilidade está instalado em cada servidor front-end em cada pool que tem suporte à funcionalidade do Lync em dispositivos móveis. Quando você instala o Lync Server 2013, um novo diretório virtual (MCX) é criado em ambos os sites internos e externos em seus servidores front-end.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 2013 com as atualizações cumulativas do Lync Server 2013:2013 de fevereiro suporta o serviço de mobilidade apresentado na atualização cumulativa do Lync Server 2010: novembro de 2011, geralmente conhecida como MCX, e o componente da Web do UCWA. A combinação desses dois serviços de mobilidade fornece interoperabilidade e uso por usuários com os clientes Lync 2010 Mobile e Lync 2013 Mobile no Lync Server 2013.

    
    </div>

  - **Serviço de descoberta automática do Lync Server 2013**   esse serviço identifica a localização do usuário e permite que dispositivos móveis e outros clientes do Lync localizem recursos, como URLs internas e externas dos serviços da Web do Lync Server 2013 e a URL do MCX ou UCWA, independentemente do local de rede. A descoberta automática usa nomes de host codificados (lyncdiscoverinternal para usuários dentro da rede; lyncdiscover para usuários fora da rede) e o domínio SIP do usuário. Ela dá suporte a conexões de clientes que usam HTTP ou HTTPS.
    
    O serviço de descoberta automática está instalado em cada servidor front-end e em cada director em cada pool compatível com a funcionalidade do Lync em dispositivos móveis. Quando você instala o serviço de descoberta automática, um novo diretório virtual (descoberta automática) é criado no site interno e no site externo, em servidores e directors de front-end.
    
    <div>
    

    > [!NOTE]  
    > O serviço descoberta automática está listado aqui porque continua sendo um componente essencial ao oferecer serviços de cliente móvel. A função de descoberta automática no Lync Server 2013 foi expandida para fornecer serviços para todos os clientes. Para obter detalhes sobre o planejamento do serviço de descoberta automática, consulte <A href="lync-server-2013-planning-for-autodiscover.md">planejando para descoberta automática no Lync Server 2013</A>.

    
    </div>

  - **Serviço de notificação por push**   esse serviço é um serviço baseado em nuvem localizado no centro de dados do Lync Online. Quando o aplicativo móvel do Lync em um dispositivo Apple iOS compatível ou Windows Phone está inativo, ele não pode responder a novos eventos, como um novo convite de mensagens instantâneas (IM), uma mensagem instantânea perdida, uma chamada perdida ou caixa postal, pois esses dispositivos não dão suporte a aplicativos móveis em execução em segundo plano. Nesses casos, uma notificação do novo evento, chamada de *notificação por push*, é enviada para o dispositivo móvel. O serviço de mobilidade envia a notificação para o serviço de notificação por push baseado na nuvem, que envia a notificação para o serviço de notificação por push da Apple (APNS) (para dispositivos Apple iOS compatíveis) ou para o serviço de notificação por push da Microsoft (MPNS ) (para Windows Phone), que o envia para o dispositivo móvel. Em seguida, o usuário pode responder à notificação no dispositivo móvel para ativar o aplicativo.
    
    O Lync 2010 móvel no Apple e dispositivos Windows Phone usam notificações por push. O cliente móvel do Lync 2013 para dispositivos Apple introduzido com as atualizações cumulativas do Lync Server 2013: fevereiro de 2013 não usa mais a notificação por Push ou a casa de compensação de notificação por push (PNCH).

O diagrama a seguir ilustra como o serviço de notificação por Push se encaixa em uma topologia do Lync Server 2013 que usa UCWA e clientes móveis do Lync 2013.

![166d60fd-ff71-4FFE-9f66-3c8bbde0b5ae] (images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "166d60fd-ff71-4FFE-9f66-3c8bbde0b5ae")

Apresentado na atualização cumulativa do Lync Server 2010:2011 de novembro, o serviço MCX fornece serviços para clientes móveis do Lync 2010. O diagrama a seguir ilustra o serviço de notificação por push como ele se aplica a uma topologia usando clientes móveis MCX e Lync 2010.

![3081634e-60e7-4348-b24e-bbbf05a90f5f] (images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "3081634e-60e7-4348-b24e-bbbf05a90f5f")

</div>

<div>

## <a name="supported-topologies"></a>Topologias suportadas

Aplicar as atualizações cumulativas do Lync Server 2013: fevereiro de 2013 adiciona os componentes da Web do UCWA para dar suporte a mobilidade para recursos de cliente móvel do Lync 2013 nas seguintes topologias:

  - Lync Server 2013 Standard Edition

  - Lync Server 2013 Enterprise Edition

O servidor de borda pode ser um servidor de borda do Lync Server 2010.

Uma implantação do Lync Server 2013 sem as atualizações cumulativas do Lync Server 2013: fevereiro de 2013 usará o serviço de mobilidade do MCX e poderá fornecer serviços somente para o Lync 2010 Mobile.

<div>


> [!IMPORTANT]  
> O serviço de mobilidade tem suporte em servidores front-end posicionados com a função de servidor de mediação com duas interfaces de rede, mas você deve tomar as medidas adequadas para configurar as interfaces. Você deve atribuir os endereços IP para a interface específica que se comunicará como servidor de mediação e o IP da interface de rede que se comunicará como servidor front-end. Você pode fazer isso no construtor de topologias selecionando o endereço IP correto para cada serviço, em vez de usar o padrão <STRONG>usar todos os endereços IP</STRONG>configurados.



</div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Planejamento para acesso de usuário externo no Lync Server 2013](lync-server-2013-planning-for-external-user-access.md)  
[Implantação de acesso do usuário externo no Lync Server 2013](lync-server-2013-deploying-external-user-access.md)  
[Planejando a descoberta automática no Lync Server 2013](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

