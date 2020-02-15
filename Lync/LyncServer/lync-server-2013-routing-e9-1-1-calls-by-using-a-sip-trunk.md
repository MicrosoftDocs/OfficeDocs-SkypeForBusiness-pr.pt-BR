---
title: 'Lync Server 2013: roteamento de chamadas E9-1-1 usando um tronco SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Routing E9-1-1 calls by using a SIP trunk
ms:assetid: 157753c3-fe74-4e2c-81da-ee06911d4cc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204701(v=OCS.15)
ms:contentKeyID: 48183492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f45bd91eade0de6f290fd87e52effb25c669999a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037321"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-a-sip-trunk-in-lync-server-2013"></a>Roteamento de chamadas E9-1-1 usando um tronco SIP no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-29_

Usar um tronco SIP para conectar-se a um provedor de serviço E9-1-1 qualificado é uma maneira que pode ser usada para implantar o E9-1-1. Para obter detalhes sobre como usar um gateway ELIN para se conectar a um provedor de serviços E9-1-1 baseado em PSTN (rede telefônica pública comutada), consulte [Routing E9-1-1 calls by using a Elin gateway in Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md).

O diagrama a seguir mostra como uma chamada de emergência é roteada do Lync Server para o ponto de resposta de segurança pública (PSAP) quando você usa um tronco SIP e um provedor de serviço E9-1-1 qualificado.

**Encaminhando chamadas do E9-1-1 por meio de um tronco SIP**

![Roteamento de chamadas de emergência do Lync Server para PSAP](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "Roteamento de chamadas de emergência do Lync Server para PSAP")

Quando uma chamada de emergência é feita de um cliente compatível do Lync Server:

1.  Um SIP INVITE que contém o local, o número de retorno de chamada do chamador e a URL de notificação (opcional) e o número de retorno de chamada de conferência é roteado para o Lync Server.

2.  O Lync Server corresponde ao número de emergência e roteia a chamada (com base no valor de **uso do PSTN** definido na política de local aplicável) para um servidor de mediação e, a partir daí, em um tronco SIP para o provedor de serviços E9-1-1.

3.  O provedor de serviços E9-1-1 encaminha as chamadas de emergência para o PSAP correto com base na localização que é fornecida com a chamada. Quando o cliente inclui um ERL (Local da resposta de emergência) com a chamada de emergência, o provedor automaticamente encaminha a chamada para o PSAP apropriado. Se a localização foi inserida manualmente pelo usuário, o ECRC (Centro de resposta de chamada de emergência) primeiro verifica verbalmente a precisão da localização com o chamador antes do encaminhamento da chamada de emergência para o PSAP.

4.  Se você configurou a política de local para notificações, um ou mais gerentes de segurança da sua organização receberão uma mensagem instantânea especial de notificação de emergência do Lync. Essa mensagem é sempre aberta na(s) tela(s) de seus oficiais de segurança, contendo o nome, número de telefone, horário e local do chamador, permitindo que o pessoal de segurança respondam rapidamente ao chamador de emergência usando uma mensagem instantânea ou voz.

5.  Caso tenha configurado a política de local para conferências e ela seja suportada pelo provedor de serviço de E9-1-1, um Suporte de Segurança é colocado na chamada com áudio uni ou bidirecional.

6.  Se a chamada for interrompida prematuramente, o PSAP usa o número de retorno de chamada para entrar em contato com o chamador diretamente.

</div>

<span> </span>

</div>

</div>

</div>

