---
title: 'Lync Server 2013: Roteamento de chamadas E9-1-1 usando tronco SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Routing E9-1-1 calls by using a SIP trunk
ms:assetid: 157753c3-fe74-4e2c-81da-ee06911d4cc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204701(v=OCS.15)
ms:contentKeyID: 48183492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c537b66883ab786bc28e3cc808874c0fcb79b92d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822311"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-a-sip-trunk-in-lync-server-2013"></a>Roteamento de chamadas E9-1-1 usando tronco SIP no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-29_

Usar um tronco SIP para conectar-se a um provedor de serviços de E9-1-1 qualificado é um modo pelo qual você pode implantar E9-1-1. Para obter detalhes sobre como usar um gateway ELIN para se conectar a um provedor de serviços de rede telefônica pública comutada (PSTN) E9-1, consulte [Roteamento E9-1-1 chamadas usando um gateway Elin no Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md).

O diagrama a seguir mostra como uma chamada de emergência é roteada do Lync Server para o ponto de resposta de segurança pública (PSAP) quando você usa um tronco SIP e um provedor de serviços E9-1 qualificado.

**Encaminhamento de chamadas E9-1-1 através de um tronco SIP**

![Roteamento de chamadas de emergência do Lync Server para PSAP] (images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "Roteamento de chamadas de emergência do Lync Server para PSAP")

Quando uma chamada de emergência é feita de um cliente compatível com o Lync Server:

1.  Um convite SIP que contém o local, o número de retorno de chamada do chamador e a URL de notificação (opcional) e o número de retorno de chamada de conferência é roteado para o Lync Server.

2.  O Lync Server corresponde ao número de emergência e roteia a chamada (com base no valor de **uso de PSTN** definido na política de localização aplicável) para um servidor de mediação e, a partir daí, em um tronco SIP para o provedor de serviços E9-1-1.

3.  O provedor de serviços E9-1-1 encaminha a chamada de emergência ao PSAP correto baseado no local que é fornecido com a chamada. Quando o cliente inclui um ERL (local de resposta de emergência) com a chamada de emergência, o provedor automaticamente encaminha a chamada ao PSAP adequado. Caso o local tenha sido manualmente inserido pelo usuário, o ECRC (centro de resposta de chamadas de emergência) primeiro verifica verbalmente a precisão do local com o chamador antes de encaminhar a chamada de emergência ao PSAP.

4.  Se você configurou a política de localização para notificações, um ou mais gerentes de segurança da sua organização receberão uma mensagem de chat especial de notificação de emergência do Lync. Essa mensagem sempre aparecerá na(s) tela(s) dos funcionários de segurança e contém o nome, o número de telefone, a hora e o local do chamador, permitindo que a equipe de segurança atenda rapidamente ao chamador de emergência usando uma mensagem instantânea ou voz.

5.  Caso tenha configurado a política de local para conferências e ela seja suportada pelo provedor de serviços E9-1-1, um Suporte de Segurança é colocado na chamada com áudio uni ou bidirecional.

6.  Caso a chamada seja interrompida prematuramente, o PSAP usa o número de retorno de chamada para entrar em contato diretamente com o chamador.

</div>

<span> </span>

</div>

</div>

</div>

