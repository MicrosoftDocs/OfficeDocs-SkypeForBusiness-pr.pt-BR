---
title: 'Lync Server 2013: topologias e componentes para mobilidade'
description: 'Lync Server 2013: topologias e componentes para mobilidade.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies and components for mobility
ms:assetid: be3cae7a-095d-4785-91ba-6fac99eba92a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690037(v=OCS.15)
ms:contentKeyID: 48185282
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 731991c3395bd3014270430483c6047dd5487185
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576017"
---
# <a name="topologies-and-components-for-mobility-in-lync-server-2013"></a>Topologias e componentes para mobilidade no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-17_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Para oferecer suporte a aplicativos móveis do Lync em dispositivos móveis, o Lync Server 2013 fornece três serviços: Lync Server 2013 MCX Mobility Service, Lync Server 2013 autodiscover Service e Lync Server 2013 Push Notification Service. As atualizações cumulativas do Lync Server 2013: fevereiro de 2013 adiciona um serviço gratuito, mas avançado para clientes móveis do Lync 2013, para obter suporte de mobilidade por meio do uso da API Web de comunicações unificadas ou UCWA. Esta seção descreve brevemente esses componentes e identifica as topologias do Lync Server 2013 que dão suporte à mobilidade.

<div>


> [!NOTE]  
> Os serviços de mobilidade também estão disponíveis em implantações híbridas. Não é necessário implantar serviços para suportar a mobilidade se os seus usuários estão hospedados online. Você precisa definir uma configuração para o serviço de descoberta automática para permitir que os usuários móveis encontrem sua identidade online.



</div>

<div>


> [!IMPORTANT]  
> Se você estiver planejando qualquer conectividade de usuário externa (por exemplo, Federação, acesso de usuário externo ou recursos de mobilidade), deverá usar servidores de borda com o servidor Standard Edition e o servidor front-end ou o pool de front-ends. O servidor Standard Edition e o servidor front-end ou o pool de front-ends não têm os componentes necessários para permitir que usuários externos acessem sua implantação interna ou para a implantação interna se comunicarem com os usuários externos. Para todos os cenários que incluem usuários externos que colaboram ou se comunicam com usuários internos, incluindo mobilidade, você deve implantar pelo menos um servidor de borda e um proxy reverso.<BR>A <EM>notificação por push</EM> usa um tipo de Federação para os serviços do Lync Online, que hospeda a câmara de compensação de notificação por push (PNCH). A notificação por push refere-se aos alertas sonoros, alertas na tela (texto) e selos que são enviados por aplicativos ao Apple iPhone, iPad e Windows Phone, quando o dispositivo móvel está inativo. PNCH recebe notificações por push do Lync Server. Quando o PNCH recebe uma notificação de uma mensagem, o PNCH encaminha uma notificação para clientes móveis através do Apple Push Notification Services ou do Lync Server 2013 Push Notification Service, com base no cliente móvel para o qual a mensagem é destinada. A PNCH é um serviço necessário para esses cliente móveis. Para federar o Lync Online, o PNCH usa servidores de borda e certificados para garantir confidencialidade e autenticação, políticas e registros de DNS (sistema de nomes de domínio) configurados corretamente. Os clientes móveis do Lync Symbian e com base em Android da Nokia não usam o PNCH. Para obter detalhes sobre como planejar e implantar servidores de borda, consulte <A href="lync-server-2013-planning-for-external-user-access.md">Planning for External User Access in Lync server 2013</A> e <A href="lync-server-2013-deploying-external-user-access.md">Deploying external User Access in Lync Server 2013</A>.<BR>Os clientes móveis do Lync 2013 para dispositivos Apple introduzidos com as atualizações cumulativas do Lync Server 2013: fevereiro de 2013 não usam mais a notificação por Push ou a casa de compensação de notificação por push (PNCH). Os clientes móveis do Lync 2013 no Windows Phone ainda usam a notificação por push e o (PNCH).



</div>

<div>

## <a name="mobility-components"></a>Componentes de mobilidade

Os serviços que suportam a mobilidade são:

  - **API Web de comunicações unificadas do Lync Server 2013 (UCWA)**     Fornece serviços para comunicação em tempo real com clientes móveis e da Web no Lync Server 2013. Ao implantar as atualizações cumulativas do Lync Server 2013: fevereiro de 2013 para o servidor front-end e diretor, a instalação cria um diretório virtual nos serviços Web internos e externos (Ucwa). Um componente da Web que faz parte do diretório virtual do Ucwa aceita chamadas de clientes habilitados para UCWA. Os aplicativos cliente se comunicam por uma interface REST para presença, contatos, mensagens instantâneas, VoIP, conferência de vídeo e colaboração. O UCWA usa um canal baseado em P-GET para enviar eventos, como uma chamada de entrada, uma mensagem instantânea de entrada ou uma mensagem para o aplicativo cliente.
    
    <div>
    

    > [!NOTE]  
    > <EM>REST</EM> ou Representational State Transfer, é um estilo de arquitetura de software para sistemas distribuídos que foram amplamente adotados em muitos formulários e é bem adequado para os requisitos de serviços Web em geral.

    
    </div>

  - **Lync Server 2013 Mobility Service (MCX)**     Este serviço oferece suporte à funcionalidade do Lync, como mensagens instantâneas (IM), presença e contatos, em dispositivos móveis. O serviço de mobilidade é instalado em todos os servidores front-end em cada pool que oferece suporte à funcionalidade do Lync em dispositivos móveis. Quando você instala o Lync Server 2013, um novo diretório virtual (MCX) é criado tanto no site interno quanto no site externo em seus servidores front-end.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 2013 com as atualizações cumulativas para Lync Server 2013: fevereiro de 2013 suporta o serviço de mobilidade introduzido na atualização cumulativa do Lync Server 2010: novembro de 2011, comumente conhecido como MCX e o componente da Web do UCWA. A combinação desses dois serviços de mobilidade oferece interoperabilidade e uso por usuários com clientes móveis do Lync 2010 e Lync 2013 no Lync Server 2013.

    
    </div>

  - Serviço de descoberta **automática do Lync Server 2013**     Este serviço identifica o local do usuário e permite que dispositivos móveis e outros clientes do Lync localizem recursos, como as URLs internas e externas para os serviços Web do Lync Server 2013 e a URL do MCX ou do UCWA, independentemente do local da rede. A descoberta automática usa nomes de host codificados (lyncdiscoverinternal para usuários dentro da rede; lyncdiscover para usuários fora da rede) e o domínio SIP do usuário. Ele oferece suporte a conexões de clientes que usam HTTP ou HTTPS.
    
    O serviço de descoberta automática é instalado em todos os servidores front-end e em cada diretor de cada pool que oferece suporte à funcionalidade do Lync em dispositivos móveis. Quando você instala o serviço de descoberta automática, um novo diretório virtual (descoberta automática) é criado no site interno e no site externo, em servidores front-end e diretores.
    
    <div>
    

    > [!NOTE]  
    > O serviço de descoberta automática está listado aqui porque continua sendo um componente crítico ao fornecer serviços de cliente móvel. A função de descoberta automática no Lync Server 2013 foi expandida para fornecer serviços para todos os clientes. Para obter detalhes sobre o planejamento do serviço de descoberta automática, consulte <A href="lync-server-2013-planning-for-autodiscover.md">Planning for autodiscover in Lync Server 2013</A>.

    
    </div>

  - Serviço de notificação **por push**     Este serviço é um serviço baseado em nuvem localizado no data center do Lync Online. Quando o aplicativo móvel do Lync em um dispositivo Apple iOS com suporte ou no Windows Phone está inativo, ele não pode responder a novos eventos, como um novo convite de mensagens instantâneas (IM), uma mensagem instantânea perdida, uma chamada perdida ou uma caixa postal, porque esses dispositivos não dão suporte a aplicativos móveis executados em segundo plano. Nesses casos, uma notificação do novo evento – chamada de *notificação por push*, é enviada ao dispositivo móvel. O serviço de mobilidade envia a notificação para o serviço de notificação por push baseado em nuvem, que envia a notificação ao Apple Push Notification Service (APNS) (para dispositivos Apple iOS suportados) ou ao Microsoft Push Notification Service (MPNS) (para Windows Phone), que o envia para o dispositivo móvel. Em seguida, o usuário pode responder à notificação no dispositivo móvel para ativar o aplicativo.
    
    O Lync 2010 Mobile no Apple e dispositivos Windows Phone usam notificações por push. O cliente móvel do Lync 2013 para dispositivos Apple apresentou as atualizações cumulativas do Lync Server 2013: fevereiro de 2013 não usa mais a notificação por Push ou a casa de compensação de notificação por push (PNCH).

O diagrama a seguir ilustra como o serviço de notificação por Push se enquadra em uma topologia do Lync Server 2013 que usa clientes móveis UCWA e Lync 2013.

![166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae")

Introduzido na atualização cumulativa do Lync Server 2010: novembro de 2011, o serviço MCX fornece serviços para clientes móveis do Lync 2010. O diagrama a seguir ilustra o serviço de notificação por push como ele se aplica a uma topologia usando clientes móveis do MCX e Lync 2010.

![3081634e-60e7-4348-b24e-bbbf05a90f5f](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "3081634e-60e7-4348-b24e-bbbf05a90f5f")

</div>

<div>

## <a name="supported-topologies"></a>Topologias suportadas

Aplicando as atualizações cumulativas do Lync Server 2013: fevereiro 2013 adiciona os componentes Web do UCWA para suportar a mobilidade para os recursos do cliente móvel do Lync 2013 nas seguintes topologias:

  - Lync Server 2013 Standard Edition

  - Lync Server 2013 Enterprise Edition

O servidor de borda pode ser um servidor de borda do Lync Server 2010.

Uma implantação do Lync Server 2013 sem as atualizações cumulativas do Lync Server 2013: fevereiro de 2013 usará o serviço de mobilidade do MCX e só poderá fornecer serviços para o Lync 2010 Mobile.

<div>


> [!IMPORTANT]  
> O serviço de mobilidade é suportado em servidores front-end posicionados com a função de servidor de mediação com duas interfaces de rede, mas você deve seguir as etapas apropriadas para configurar as interfaces. Você deve atribuir os endereços IP à interface específica que se comunicará como o servidor de mediação e o IP da interface de rede que se comunicará como o servidor front-end. Você pode fazer isso no construtor de topologias selecionando o endereço IP correto para cada serviço, em vez de usar o padrão <STRONG>usar todos os endereços IP configurados</STRONG>.



</div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Planejamento para acesso de usuário externo no Lync Server 2013](lync-server-2013-planning-for-external-user-access.md)  
[Implantando o acesso de usuário externo no Lync Server 2013](lync-server-2013-deploying-external-user-access.md)  
[Planejamento para descoberta automática no Lync Server 2013](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

