---
title: 'Lync Server 2013: Recursos de Unificação de Mensagens integrada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Features of integrated Unified Messaging and Lync Server
ms:assetid: 094f549d-fccc-43ab-9f39-6ddd18130915
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398144(v=OCS.15)
ms:contentKeyID: 48183353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69726c614df344c76b06cf68e4d844c0514af7dd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765139"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="features-of-integrated-unified-messaging-and-lync-server-2013"></a>Recursos de Unificação de Mensagens integrada e do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-01_

Lync Server 2013, o Enterprise Voice usa a infraestrutura de Unificação de mensagens do Exchange para fornecer atendimento de chamada, notificação de chamada, acesso de voz (incluindo caixa postal) e serviços de atendedor automático.

<div>

## <a name="call-answering"></a>Atendimento de Chamadas

O atendimento de chamadas é o recebimento das mensagens de voz em favor dos usuários cujas ligações não são atendidas ou estão ocupados. Ele inclui uma saudação pessoal, a gravação de uma mensagem e seu envio ao Transporte de Hub do Exchange Server para ficar na fila de entrega à caixa de correio do usuário, que está armazenada no servidor de caixa de correio do Exchange.

Se o chamador deixar uma mensagem, está é roteada até a Caixa de entrada do usuário. Se o chamador optar por não deixar uma mensagem, uma notificação de chamada perdida será armazenada na caixa de correio do usuário. Os usuários podem, então, acessar sua Caixa de entrada usando o cliente de mensagem e de colaboração do Microsoft Outlook, o Outlook Web Access, a tecnologia Exchange ActiveSync ou o Outlook Voice Access. O assunto e a prioridade das chamadas podem ser exibidos de uma maneira muito semelhante àquela do e-mail.

</div>

<div>

## <a name="outlook-voice-access"></a>Outlook Voice Access

O Outlook Voice Access permite que um usuário do Enterprise Voice tenha acesso não apenas à caixa postal, mas também à caixa de entrada do Exchange, incluindo email, calendário e contatos de uma interface de telefonia. O número de acesso do assinante é atribuído por um administrador de UM do Exchange.

</div>

<div>

## <a name="auto-attendant"></a>Atendedor automático

O atendedor automático é um recurso do Exchange UM que pode ser usado para configurar um número de telefone que os usuários externos podem discar para acessar os representantes da empresa. Especificamente, ele fornece uma série de avisos de voz que auxiliam um chamador externo a navegar por um sistema de menus. A lista de opções disponíveis é configurada no servidor do Exchange UM pelo administrador de UM do Exchange.

</div>

<div>

## <a name="fax-services"></a>Serviços de fax

O Exchange UM inclui recursos de fax, que permitem que os usuários recebam faxes de entrada nas caixas de correio do Exchange. Para obter detalhes, consulte "Unified Messaging" na documentação do Microsoft Exchange [http://go.microsoft.com/fwlink/p/?linkId=135652](http://go.microsoft.com/fwlink/p/?linkid=135652)Server em.

<div>


> [!NOTE]  
> Os serviços de fax fornecidos pelo Exchange UM servidor não estão disponíveis nas implantações do Lync Server integradas ao Microsoft Exchange Server 2010, Exchange 2010 com o Service Pack mais recente ou Exchange 2013.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

