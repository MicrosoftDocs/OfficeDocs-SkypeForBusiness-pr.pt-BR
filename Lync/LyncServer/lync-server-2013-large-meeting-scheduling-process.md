---
title: 'Lync Server 2013: processo de agendamento de grandes reuniões'
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
ms.openlocfilehash: 3ccbe1735d92d510f4e5016cc2e52b62e1c82bb7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034973"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="large-meeting-scheduling-process-in-lync-server-2013"></a>Processo de agendamento de reunião grande no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-22_

Como só há suporte para uma grande reunião por vez no pool dedicado de reunião grande, recomendamos a implementação de um grande processo de agendamento de reunião para ajudar a evitar grandes conflitos de reunião. O objetivo desse processo de agendamento é facilitar a configuração de reuniões grandes. Esse recurso não é fornecido diretamente por clientes do Lync Server ou do Lync Server. Uma maneira de implementar tal processo é usar o sistema de tíquete da equipe de suporte da sua organização, se disponível.

Para organizadores de grandes reuniões, agendar uma grande reunião envolve concluir as seguintes etapas:

1.  O organizador ou representante da reunião determina o tempo, a duração e o tamanho de uma reunião futura, além da lista de apresentadores. Se o tamanho previsto da reunião exceder 250 usuários ou para garantir a melhor experiência do usuário para uma reunião de menos de 250 usuários, o organizador ou o representante enviará uma solicitação para uma reunião grande.

2.  A equipe de agendamento verifica se a data e hora solicitada estão disponíveis. Como damos suporte apenas a uma única reunião grande no pool dedicado por vez, a equipe de agendamento precisa verificar o calendário de reunião grande para determinar se há outra reunião agendada para a data e hora solicitadas. Se a hora solicitada estiver disponível, a equipe aprovará a solicitação de reunião.

3.  Se a solicitação for aprovada, a equipe de agendamento (usando credenciais no pool dedicado) usará o suplemento reunião online para Lync 2013 com o Outlook para configurar uma reunião no pool dedicado de grandes reuniões. A URL a ser usada para ingressar na reunião é fornecida ao solicitante como parte do aviso de aprovação.

4.  O organizador ou representante da reunião usa o Outlook para agendar a próxima reunião, adicionando a URL para participar da reunião ao convite da reunião. O organizador ou o representante da reunião especificará os usuários a serem convidados e enviarão o convite da reunião.
    
    A figura a seguir ilustra um fluxo de trabalho de solicitação e aprovação típico para agendar grandes reuniões.
    
    ![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")  

</div>

<span> </span>

</div>

</div>

</div>

