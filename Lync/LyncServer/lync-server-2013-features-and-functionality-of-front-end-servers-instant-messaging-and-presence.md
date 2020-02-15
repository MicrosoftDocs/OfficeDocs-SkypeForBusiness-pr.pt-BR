---
title: 'Lync Server 2013: recursos e funcionalidade de servidores front-end, mensagens instantâneas e presença'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Features and functionality of Front End Servers, instant messaging, and presence
ms:assetid: 05b29536-dcd7-49b5-934a-2ebf20ddc45c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398109(v=OCS.15)
ms:contentKeyID: 48183294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8e25a74dcffe76f16b12a8c80f8ad8f980370dc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041030"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="features-and-functionality-of-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Recursos e funcionalidade de servidores front-end, mensagens instantâneas e presença no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-03-17_

Os servidores front-end fornecem a maioria da funcionalidade do Lync Server. Há duas edições disponíveis: Lync Server Enterprise Edition, que é projetado principalmente para organizações maiores, e Lync Server Standard Edition, que é projetado principalmente para organizações menores que desejam um Investement de hardware menor e não requer alta disponibilidade. Ambas as edições dão suporte a todas as cargas de trabalho do Lync Server, incluindo IM, presença, conferência e Enterprise Voice.

A mensagem instantânea (IM) permite que os usuários se comuniquem entre si em tempo real em seus computadores usando mensagens textuais. Tanto as sessões de IM de duas partes como as multipartes são suportadas. Um participante de uma conversa por IM de duas partes pode adicionar um terceiro participante à conversa a qualquer momento. Quando isso acontece, a janela de conversa muda para dar suporte aos recursos de conferência.

<div>


> [!IMPORTANT]
> Os clientes do Lync e do Communicator, quando envolvidos em uma comunicação de um para um, costumam ser chamados de ponto a ponto. Tecnicamente, os dois clientes estão se comunicando em uma única conversa, com a unidade de controle multiponto (IMMCU) do sistema de mensagens instantâneas no meio. O IMMCU é um componente do servidor front-end. Colocar o IMMCU no fluxo de trabalho de comunicação necessário permite a gravação de detalhes da chamada e outros recursos que o servidor front-end habilita. A comunicação é de uma porta de origem dinâmica no cliente para a porta de servidor front-end TLS/TCP/5061 (supondo que o uso da segurança da camada de transporte recomendada). Por design, a comunicação ponto a ponto (bem como mensagens instantâneas de vários participantes) só é possível quando o Lync Server e o IMMCU estão ativos e disponíveis.



</div>

A *Presença* fornece informações a usuários sobre o status de outros na rede. O status de presença de um usuário fornece informações para ajudar outros usuários a decidir se devem tentar entrar em contato com o usuário e se devem fazê-lo por mensagem instantânea, telefone ou e-mail. A Presença encoraja a comunicação instantânea quando possível, mas também dá informações sobre se um usuário está em reunião ou fora do escritório, indicando que a comunicação instantânea não é possível. Este status de presença é exibido como um ícone de presença no Lync e outros aplicativos com reconhecimento de presença, incluindo o cliente de mensagens e colaboração do Microsoft Outlook, tecnologias do Microsoft SharePoint, Microsoft Word e planilha do Microsoft Excel software. O ícone de presença representa a disponibilidade e a propensão do usuário para se comunicar naquele momento.

</div>

<span> </span>

</div>

</div>

</div>

