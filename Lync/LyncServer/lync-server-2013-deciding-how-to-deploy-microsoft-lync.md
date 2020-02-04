---
title: 'Lync Server 2013: Decidindo como implantar o Microsoft Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deciding how to deploy Microsoft Lync
ms:assetid: 6ca677d3-745d-4935-8f05-19274a8bccf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204979(v=OCS.15)
ms:contentKeyID: 48184423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aef6ac76b6c0e8a6fb3c0444ab219acf78119ecd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728551"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deciding-how-to-deploy-lync-server-2013"></a>Decidindo como implantar o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-03_

Ao planejar o Lync, a primeira decisão importante é como implantar o Microsoft Lync: como o Lync Server 2013 local ou o Lync Online com o Microsoft Office 365 na nuvem.

  - **Lync Server 2013 local** : esta opção fornece o conjunto de recursos completo do Lync e fornece a flexibilidade máxima para configurar, personalizar e operar a implantação. Todos os servidores são instalados no local e mantidos pela sua organização. Uma implantação local fornece a gama completa de recursos do Lync Server.

  - **Lync Online na nuvem** O Lync Online foi projetado para organizações que desejam os benefícios de custo e agilidade das mensagens instantâneas, presença e reuniões em nuvem sem sacrificar os recursos de classe empresarial do Lync Server. Com o Lync Online, a Microsoft implanta e mantém a infraestrutura de servidor necessária e manipula manutenção, patches e atualizações contínuas. Alguns recursos disponíveis em uma implantação local não estão disponíveis no Lync Online.

Qual tipo de implantação seria melhor para você depende das cargas de trabalho que você deseja implantar e o status geográfico e comercial da sua organização.

<div>

## <a name="lync-server"></a>Servidor Lync

Uma implantação do Lync Server local é melhor para os seguintes cenários:

  - **Recursos de voz de toda a empresa**   se você planeja implantar uma solução completa de voz empresarial para substituir seu PBX ou que usa recursos de chamada avançados, uma implantação do Lync Server local é necessária. O local é compatível com a conectividade direta com sistemas PBX e troncos e recursos de telefone avançados, como grupos de resposta e estacionamento de chamadas. No momento, o Lync Online não oferece suporte a esses recursos.

  - **Controles de qualidade de mídia**   se você quiser uma gama completa de recursos de garantia de qualidade de mídia, como o controle de admissão de chamadas (CAC) e os recursos de qualidade do serviço (QoS), será necessário uma implantação local.

  - **Chat persistente se**   você precisar implantar o chat persistente para a sua organização, você deve escolher uma implantação local.

  - **aplicativos de servidor de terceiros**   somente implantações locais podem funcionar com aplicativos de terceiros confiáveis que usam a API gerenciada de comunicação unificada da Microsoft (UCMA).

  - **Empresas multinacionais/multinacionais que precisam de suporte**   regional se você tiver datacenters em vários países ou regiões e precisar que os servidores sejam implantados e gerenciados de forma regional, uma implantação local é melhor, pois oferece esse tipo de recursos de gerenciamento regional.

  - **Controle completo sobre políticas, relatórios e atualizações**   com uma implantação local do Lync Server, você tem acesso ao conjunto completo de políticas de servidor e de cliente, monitoramento e outros relatórios e tempo de atualizações. O Lync Online fornece um subconjunto de relatórios e configurações de política e fornece uma janela limitada, embora significativa, para aceitar atualizações.

</div>

<div>

## <a name="lync-online"></a>Lync Online

Se nenhum dos fatores na lista anterior for essencial para você, talvez você queira escolher o Lync Online, para implantação e gerenciamento mais simples. O Lync Online oferece um conjunto robusto de recursos de chat, presença e conferência e também permite chamadas de voz e vídeo por IP entre os usuários da sua organização.

</div>

</div>

<span> </span>

</div>

</div>

</div>

