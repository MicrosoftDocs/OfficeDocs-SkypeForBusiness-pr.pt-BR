---
title: 'Lync Server 2013: componentes e topologias para Unificação de mensagens local'
description: 'Lync Server 2013: componentes e topologias para Unificação de mensagens local.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for on-premises Unified Messaging
ms:assetid: 22fc87cf-a7e5-4c8c-bb9b-101e5380cdcf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425711(v=OCS.15)
ms:contentKeyID: 48183619
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8fe2ca16ec9fbd39e9245fd366e1f7046dd16d42
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576817"
---
# <a name="components-and-topologies-for-on-premises-unified-messaging-in-lync-server-2013"></a>Componentes e topologias para Unificação de mensagens no local no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-25_

Este tópico descreve os componentes do Microsoft Exchange Server 2013 necessários para fornecer os recursos da UM (Unificação de mensagens) do Exchange à implantação 2013 do Lync Server. Também descreve as topologias com suporte para a integração de UM do Exchange local.

<div>

## <a name="exchange-server-components"></a>Componentes do Exchange Server

Para fornecer os recursos e serviços de UM do Exchange descritos em [recursos de Unificação de mensagens integrada e Lync Server 2013](lync-server-2013-features-of-integrated-unified-messaging.md) para usuários do Enterprise Voice em sua organização, você deve implantar um servidor de caixa de correio do Microsoft Exchange e um servidor de acesso para cliente, que hospeda caixas de correio de usuários e fornece um único local de armazenamento para email e caixa postal. O UM do Exchange é executado como um serviço nos servidores de caixa de correio do Exchange e de acesso para cliente.

Para obter detalhes sobre os componentes UM do Exchange no Microsoft Exchange Server 2007 e Microsoft Exchange Server 2010, consulte [Deploying on-premises Exchange um para fornecer Lync Server 2013 voice mail](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) na documentação de implantação.

</div>

<div>

## <a name="supported-topologies"></a>Topologias suportadas

Você pode implantar o Lync Server 2013 e a UM (Unificação de mensagens) do Exchange na mesma floresta ou em várias florestas. Se a implantação abrange várias florestas, você deve executar as etapas de integração do Exchange para cada floresta de UM do Exchange. Além disso, você deve configurar cada floresta do Microsoft Exchange para confiar na floresta do Lync Server 2013 e na floresta 2013 do Lync Server para confiar em cada floresta do Exchange UM. Além dessa relação de confiança de floresta, as configurações de UM do Exchange para todos os usuários devem ser definidas nos objetos de usuário na floresta do Lync Server 2013.

O Lync Server 2013 suporta as seguintes topologias para a integração de UM do Exchange:

  - Floresta única

  - Domínio único (ou seja, uma única floresta com um único domínio). O Lync Server 2013, o Microsoft Exchange e os usuários residem no mesmo domínio.

  - Vários domínios (ou seja, um domínio raiz com um ou mais domínios filho). Lync Server 2013 e Microsoft Exchange Servers são implantados em domínios diferentes do domínio onde você cria usuários. Os servidores de UM do Exchange podem ser implantados em domínios diferentes do Lync Server 2013 pool que eles suportam.

  - Várias florestas (ou seja, floresta de recursos). O Lync Server 2013 é implantado em uma única floresta e os usuários são distribuídos entre várias florestas. Os atributos de UM do Exchange do usuário devem ser replicados para a floresta do Lync Server 2013.
    
    <div>
    

    > [!NOTE]  
    > O Exchange pode ser implantado em várias florestas. Cada organização do Exchange pode fornecer UM do Exchange para seus usuários ou o UM do Exchange pode ser implantado na mesma floresta do Lync Server 2013.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

