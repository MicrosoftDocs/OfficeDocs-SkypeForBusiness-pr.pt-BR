---
title: 'Lync Server 2013: processo de agendamento de reunião grande'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Large-meeting scheduling process
ms:assetid: de267458-885f-4176-a8d7-1a218e67640e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205334(v=OCS.15)
ms:contentKeyID: 48185639
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2cfe26b70db612249ca840c86b41fb3d60db663
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738211"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="large-meeting-scheduling-process-in-lync-server-2013"></a>Processo de agendamento de reunião grande no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-22_

Como só há suporte para uma reunião grande por vez no pool de reunião grande dedicado, recomendamos implementar um processo de agendamento de reunião grande para ajudar a evitar conflitos de reunião grandes. A finalidade desse processo de agendamento é facilitar a configuração de reuniões grandes. Essa funcionalidade não é fornecida diretamente pelo Lync Server ou clientes do Lync Server. Uma forma de implementar tal processo é usar o sistema de tickets da equipe de suporte da sua organização, se disponível.

Para os organizadores de reuniões grandes, agendar uma reunião grande envolve completar as seguintes etapas:

1.  O organizador da reunião ou representante determina a hora, a duração e o tamanho da uma próxima reunião, além da lista de apresentadores. Se o tamanho da reunião antecipado excede 250 usuários ou para garantir a melhor experiência do usuário para uma reunião com menos de 250 usuários, o organizador ou representante envia uma solicitação para uma grande reunião.

2.  A equipe de programação verifica para ver se a data e hora solicitada está disponível. Como suportamos apenas uma única grande reunião em um pool exclusivo por vez, a equipe de programação precisa verificar o calendário de grandes reuniões para determinar se há outra reunião programada para a data e hora solicitada. Se a hora da reunião está disponível, a equipe aprova a solicitação da reunião.

3.  Se a solicitação for aprovada, a equipe de agendamento (usando credenciais no pool dedicado) usará o suplemento de reunião online para o Lync 2013 com o Outlook para configurar uma reunião no pool de reunião grande dedicado. A URL a ser usada para participar da reunião é fornecida ao requisitante como parte do prompt de aprovação.

4.  O organizador ou representante da reunião usa o Outlook para programar a próxima reunião, adicionando ao convite a URL para participar da reunião. O organizador da reunião ou representante especifica os usuários a serem convidados e envia o convite.
    
    A figura a seguir ilustra um fluxo de trabalho de solicitação e aprovação típico para agendar reuniões grandes.
    
    ![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")  

</div>

<span> </span>

</div>

</div>

</div>

