---
title: 'Lync Server 2013: planejamento de conferência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for conferencing
ms:assetid: 983a272a-e1b3-4d70-8f84-836b092fe526
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398781(v=OCS.15)
ms:contentKeyID: 48184937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bf1bf0ce10281bf4d31fc8fdb1be9251b72caf6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507018"
---
# <a name="planning-for-conferencing-in-lync-server-2013"></a>Planejamento de conferência no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-01-29_

O Lync Server 2013 oferece um avançado conjunto de recursos de conferência:

  - Webconferência, que inclui colaboração de documentos, compartilhamento de aplicativos e compartilhamento de área de trabalho. O Lync Server 2013 usa o Office Web Apps e o servidor do Office Web Apps para lidar com o compartilhamento e a renderização de apresentações do PowerPoint. Para obter detalhes sobre como instalar e configurar o servidor do Office Web Apps, consulte [Configurando a integração com o servidor do Office Web Apps e o Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - Conferência de áudio/vídeo (A/V), que permite que os usuários tenham conferências de áudio ou vídeo em tempo real sem a necessidade de serviços externos, como o serviço do Microsoft Live Meeting ou uma ponte de áudio de terceiros.

  - Conferência discada, que permite que os usuários ingressem na parte de áudio de uma conferência do Lync Server 2013 usando um telefone PSTN (rede telefônica pública comutada) sem exigir um provedor de conferência de áudio de terceiros.

  - Conferência de mensagens instantâneas (IM), em que mais de duas partes se comunicam em uma única sessão de IM. Para obter detalhes sobre a conferência de mensagens instantâneas, consulte [Planning for front end Servers, Instant Messaging e Presence no Lync Server 2013](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md).

O Lync Server 2013 suporta conferências agendadas e conferências improvisadas.

Ao implantar o Lync Server 2013, servidor front-end, você pode optar por implantar a conferência da Web, conferências A/V e recursos de conferência discada. Os recursos de conferência de mensagens instantâneas são sempre implantados automaticamente junto com os recursos de conversa de IM nos servidores front-end do Lync Server 2013

<div>


> [!NOTE]  
> Se sua implantação incluir reuniões organizadas usando o Office Communicator 2007 R2 clients (incluindo o console do Live Meeting ou o suplemento de conferência para Microsoft Office Outlook), as reuniões terão as seguintes limitações depois de serem migradas para o Lync Server 2013: 
> <UL>
> <LI>
> <P>Os usuários da reunião não poderão usar os recursos de colaboração de dados, incluindo colaboração de documentos, compartilhamento de aplicativos e compartilhamento de área de trabalho.</P>
> <LI>
> <P>Problemas de estabilidade podem surgir porque os clientes do Office Communicator 2007 R2 não têm suporte no Lync Server 2013.</P></LI></UL>Para evitar esses problemas, agende novamente todas as reuniões organizadas usando o Office Communicator 2007 R2 clients with Outlook 2010 ou o Outlook 2013 usando o suplemento de reunião online para Lync 2010 ou suplemento online Meeting para Lync 2013.



</div>

As seções a seguir descrevem o que é necessário para implantar os vários tipos de recursos de conferência, incluindo o processo de planejamento, componentes, requisitos de hardware e software e o processo de implantação.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Visão geral da conferência no Lync Server 2013](lync-server-2013-overview-of-conferencing.md)

  - [Definindo seus requisitos de conferência no Lync Server 2013](lync-server-2013-defining-your-requirements-for-conferencing.md)

  - [Componentes e topologias para conferências no Lync Server 2013](lync-server-2013-components-and-topologies-for-conferencing.md)

  - [Requisitos técnicos para conferência no Lync Server 2013](lync-server-2013-technical-requirements-for-conferencing.md)

  - [Lista de verificação de implantação para conferência no Lync Server 2013](lync-server-2013-deployment-checklist-for-conferencing.md)

  - [Suporte para grandes reuniões no Lync Server 2013](lync-server-2013-support-for-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

