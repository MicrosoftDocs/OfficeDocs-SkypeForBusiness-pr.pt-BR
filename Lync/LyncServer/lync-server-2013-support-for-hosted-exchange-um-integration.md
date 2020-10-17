---
title: Lync Server 2013 suporte para integração de UM do Exchange hospedado
description: Lync Server 2013 suporte para integração de UM do Exchange hospedado.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Support for hosted Exchange UM integration
ms:assetid: c7573ec3-013c-48d9-b59b-2a5427e6da35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398821(v=OCS.15)
ms:contentKeyID: 48185376
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88920667d703bc634921903e8e3995cb65db6873
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546316"
---
# <a name="support-for-hosted-exchange-um-integration-in-lync-server-2013"></a>Suporte à integração de UM do Exchange hospedado no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-21_

O aplicativo de roteamento ExUM do Lync Server 2013 oferece suporte à integração com a Unificação de mensagens (UM) do Exchange em um ambiente local, onde o Lync Server 2013 e o Exchange UM estão instalados localmente em sua empresa ou em com um do Exchange hospedado por um provedor de serviços, conforme mostrado no diagrama a seguir.

![Implantação de UM do Exchange do Lync Server local](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "Implantação de UM do Exchange do Lync Server local")

Os modos a seguir são suportados:

  - **Modo**     no local O Lync Server 2013 e o Exchange UM são implantados em servidores locais dentro de sua empresa.

  - **Modo**     entre locais O Lync Server 2013 é implantado em servidores locais dentro de sua empresa e o UM do Exchange é hospedado em um recurso do provedor de serviços online, como um data center do Microsoft Exchange Online.

  - **Modo misto**     Sua implantação do Lync Server 2013 tem algumas caixas de correio de usuário hospedadas em servidores locais que executam o Microsoft Exchange Server em sua empresa e algumas caixas de correio hospedadas em um data center de serviço do Exchange hospedado.
    
    <div>
    

    > [!NOTE]  
    > O modo misto pode ser usado como uma solução de transição durante a avaliação e em etapas a migração de usuários para o UM do Exchange hospedado ou como uma solução permanente se você optar por manter os serviços de UM do Exchange da UM no local após a migração de outros.

    
    </div>

Para integrar o Lync Server 2013 à UM do Exchange hospedado, você deve configurar um *espaço de endereçamento SIP compartilhado* (também chamado de *domínio dividido*). Nessa configuração, o Lync Server 2013 e o provedor de serviços UM do Exchange hospedado por terceiros podem acessar o mesmo espaço de endereço de domínio SIP. Para obter detalhes, consulte [arquitetura de integração da um do Exchange hospedado no Lync Server 2013](lync-server-2013-hosted-exchange-um-integration-architecture.md) na documentação de planejamento.

</div>

<span> </span>

</div>

</div>

</div>

