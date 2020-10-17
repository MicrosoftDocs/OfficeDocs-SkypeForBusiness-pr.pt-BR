---
title: 'Lync Server 2013: decidindo como implantar o Microsoft Lync'
description: 'Lync Server 2013: decidindo como implantar o Microsoft Lync.'
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
ms.openlocfilehash: a800b51dfddc6f2c99e42c8f117056ed4091b6a5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558097"
---
# <a name="deciding-how-to-deploy-lync-server-2013"></a>Decidindo como implantar o Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-03_

Ao planejar o Lync, a primeira decisão importante é como implantar o Microsoft Lync: como Lync Server 2013 local ou Lync Online com Microsoft 365 ou Office 365 na nuvem.

  - **Lync Server 2013 local** : essa opção oferece o conjunto de recursos completo do Lync e oferece a maior flexibilidade na configuração, personalização e operação da implantação. Todos os servidores são instalados no local e mantidos por sua organização. Uma implantação local fornece a gama completa de recursos do Lync Server.

  - **Lync Online na nuvem** O Lync Online foi projetado para organizações que desejam os benefícios de custo e agilidade de mensagens instantâneas, presença e reuniões em nuvem sem sacrificar os recursos de classe de negócios do Lync Server. Com o Lync Online, a Microsoft implanta e mantém a infraestrutura de servidor necessária e lida com manutenção, patches e atualizações em andamento. Alguns recursos disponíveis em uma implantação local não estão disponíveis no Lync Online.

O melhor tipo de implantação para você depende das cargas de trabalho que deseja implantar e da situação geográfica e de negócios de sua organização.

<div>

## <a name="lync-server"></a>Lync Server

Uma implantação do Lync Server no local é melhor nas seguintes situações:

  - Recursos completos do **Enterprise Voice**     Se você planeja implantar uma solução Enterprise Voice completa para substituir seu PBX ou que usa recursos avançados de chamada, uma implantação do Lync Server local é necessária. Esse tipo de implantação oferece suporte a conectividade direta com sistemas e troncos PBX, além de recursos de telefonia avançados como grupos de resposta e estacionamento de chamada. No momento, o Lync Online não dá suporte a esses recursos.

  - Controles de qualidade de **mídia**     Se você quiser a gama completa de recursos de garantia de qualidade de mídia, como o CAC (controle de admissão de chamadas) e os recursos de qualidade de serviço (QoS), será necessário uma implantação local.

  - **Chat persistente**     Se você precisar implantar o chat persistente para sua organização, você deve escolher uma implantação local.

  - Aplicativos de servidor **de terceiros**     Somente as implantações locais podem funcionar com aplicativos de terceiros confiáveis que usam o Microsoft Unified Communications Managed API (UCMA).

  - **Empresas multinacionais/Multiregionals que precisam de suporte regional**     Se você tem data centers em vários países ou regiões e precisa que os servidores sejam implantados e gerenciados de forma regional, uma implantação local é melhor, pois fornece esse tipo de recurso de gerenciamento regional.

  - **Controle completo sobre políticas, relatórios e atualizações**     Com uma implantação do Lync Server local, você tem acesso ao conjunto completo de políticas de servidor e cliente, monitoramento e outros relatórios e tempo de atualização. O Lync Online fornece um subconjunto de relatórios e configuração de política e fornece uma janela limitada, embora significativa, para aceitar atualizações.

</div>

<div>

## <a name="lync-online"></a>Lync Online

Caso nenhum dos fatores na lista anterior seja essencial para você, escolha o Lync Online, que possui implantação e gerenciamento mais simples. O Lync Online fornece um conjunto de recursos robusto de IM, presença e conferência, além de permitir chamadas de vídeo e voz sobre IP entre usuários em sua organização.

</div>

</div>

<span> </span>

</div>

</div>

</div>
