---
title: 'Lync Server 2013: Componentes e topologias para o Sistema de Mensagens Instantâneas local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components and topologies for on-premises Unified Messaging
ms:assetid: 22fc87cf-a7e5-4c8c-bb9b-101e5380cdcf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425711(v=OCS.15)
ms:contentKeyID: 48183619
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cdaf33a230f2663e9fc8b541aafb47c362d0ac97
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836514"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-on-premises-unified-messaging-in-lync-server-2013"></a>Componentes e topologias para o Sistema de Mensagens Instantâneas local no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-25_

Este tópico descreve os componentes do Microsoft Exchange Server 2013 necessários para fornecer recursos de UM (Unificação de mensagens) do Exchange à implantação do Lync Server 2013. Ele também descreve as topologias com suporte para a integração de UM local do Exchange UM.

<div>

## <a name="exchange-server-components"></a>Componentes de Exchange Server

Para fornecer os recursos e os serviços do Exchange UM descritos em [recursos de Unificação de mensagens integrada e Lync Server 2013](lync-server-2013-features-of-integrated-unified-messaging.md) para usuários do Enterprise Voice em sua organização, você deve implantar um servidor de caixa de correio do Microsoft Exchange e um servidor de acesso para cliente, que hospeda caixas de correio de usuário e fornece um único local de armazenamento para email e caixa postal. O Exchange UM é executado como um serviço na caixa de correio do Exchange e nos servidores de acesso para cliente.

Para obter detalhes sobre os componentes de UM do Exchange no Microsoft Exchange Server 2007 e no Microsoft Exchange Server 2010, consulte Implantando o [Exchange um local para fornecer o Lync Server 2013 voice mail](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) na documentação de implantação.

</div>

<div>

## <a name="supported-topologies"></a>Topologias suportadas

Você pode implantar o Lync Server 2013 e o Exchange Unified Messaging (UM) na mesma floresta ou em várias florestas. Se a implantação abranger várias florestas, você deve executar as etapas de integração do Exchange para cada floresta do Exchange UM. Além disso, você deve configurar cada floresta do Microsoft Exchange para confiar na floresta do Lync Server 2013 e na floresta do Lync Server 2013 para confiar em cada floresta do Exchange UM. Além dessa relação de confiança de floresta, as configurações de UM do Exchange UM para todos os usuários devem ser definidas nos objetos de usuário da floresta do Lync Server 2013.

O Lync Server 2013 oferece suporte às seguintes topologias para a integração de UM do Exchange UM:

  - Floresta única

  - Domínio único (ou seja, uma única floresta com um único domínio). O Lync Server 2013, o Microsoft Exchange e os usuários residem no mesmo domínio.

  - Vários domínios (ou seja, um domínio raiz com um ou mais domínios filhos). O Lync Server 2013 e o Microsoft Exchange Server são implantados em domínios diferentes do domínio em que você cria usuários. Os servidores Exchange UM podem ser implantados em diferentes domínios do Lync Server 2013 pool suportados.

  - Várias floresta (ou seja, floresta de recursos). O Lync Server 2013 é implantado em uma única floresta e os usuários são distribuídos em várias florestas. Os atributos de UM dos usuários do Exchange devem ser replicados para a floresta do Lync Server 2013.
    
    <div>
    

    > [!NOTE]  
    > O Exchange pode ser implantado em várias florestas. Cada organização do Exchange pode fornecer ao Exchange UM para seus usuários ou o Exchange UM pode ser implantado na mesma floresta do Lync Server 2013.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

