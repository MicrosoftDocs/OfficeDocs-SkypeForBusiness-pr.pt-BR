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
ms.openlocfilehash: 035279fe9c87b7901092408941538871f1c663fb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201167"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-a-sip-trunk-in-lync-server-2013"></a><span data-ttu-id="507b9-102">Roteamento de chamadas E9-1-1 usando um tronco SIP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="507b9-102">Routing E9-1-1 calls by using a SIP trunk in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="507b9-103">_**Última modificação do tópico:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="507b9-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="507b9-104">Usar um tronco SIP para conectar-se a um provedor de serviço E9-1-1 qualificado é uma maneira que pode ser usada para implantar o E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="507b9-104">Using a SIP trunk to connect to a qualified E9-1-1 service provider is one way that you can deploy E9-1-1.</span></span> <span data-ttu-id="507b9-105">Para obter detalhes sobre como usar um gateway ELIN para se conectar a um provedor de serviços E9-1-1 baseado em PSTN (rede telefônica pública comutada), consulte [Routing E9-1-1 calls by using a Elin gateway in Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md).</span><span class="sxs-lookup"><span data-stu-id="507b9-105">For details about using an ELIN gateway to connect to a public switched telephone network (PSTN)-based E9-1-1 service provider, see [Routing E9-1-1 calls by using an ELIN gateway in Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md).</span></span>

<span data-ttu-id="507b9-106">O diagrama a seguir mostra como uma chamada de emergência é roteada do Lync Server para o ponto de resposta de segurança pública (PSAP) quando você usa um tronco SIP e um provedor de serviço E9-1-1 qualificado.</span><span class="sxs-lookup"><span data-stu-id="507b9-106">The following diagram shows how an emergency call is routed from Lync Server to the Public Safety Answering Point (PSAP) when you use a SIP trunk and qualified E9-1-1 service provider.</span></span>

<span data-ttu-id="507b9-107">**Encaminhando chamadas do E9-1-1 por meio de um tronco SIP**</span><span class="sxs-lookup"><span data-stu-id="507b9-107">**Routing E9-1-1 calls through a SIP trunk**</span></span>

<span data-ttu-id="507b9-108">![Roteamento de chamadas de emergência do Lync Server para PSAP](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "Roteamento de chamadas de emergência do Lync Server para PSAP")</span><span class="sxs-lookup"><span data-stu-id="507b9-108">![Emergency Call Routing from Lync Server to PSAP](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "Emergency Call Routing from Lync Server to PSAP")</span></span>

<span data-ttu-id="507b9-109">Quando uma chamada de emergência é feita de um cliente compatível do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="507b9-109">When an emergency call is placed from a compatible Lync Server client:</span></span>

1.  <span data-ttu-id="507b9-110">Um SIP INVITE que contém o local, o número de retorno de chamada do chamador e a URL de notificação (opcional) e o número de retorno de chamada de conferência é roteado para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="507b9-110">A SIP INVITE that contains the location, the caller's callback number, and the (optional) Notification URL and conference callback number is routed to Lync Server.</span></span>

2.  <span data-ttu-id="507b9-111">O Lync Server corresponde ao número de emergência e roteia a chamada (com base no valor de **uso do PSTN** definido na política de local aplicável) para um servidor de mediação e, a partir daí, em um tronco SIP para o provedor de serviços E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="507b9-111">Lync Server matches the emergency number and routes the call (based on the **PSTN Usage** value that is defined in the applicable location policy) to a Mediation Server, and from there, over a SIP trunk to the E9-1-1 service provider.</span></span>

3.  <span data-ttu-id="507b9-p102">O provedor de serviços E9-1-1 encaminha as chamadas de emergência para o PSAP correto com base na localização que é fornecida com a chamada. Quando o cliente inclui um ERL (Local da resposta de emergência) com a chamada de emergência, o provedor automaticamente encaminha a chamada para o PSAP apropriado. Se a localização foi inserida manualmente pelo usuário, o ECRC (Centro de resposta de chamada de emergência) primeiro verifica verbalmente a precisão da localização com o chamador antes do encaminhamento da chamada de emergência para o PSAP.</span><span class="sxs-lookup"><span data-stu-id="507b9-p102">The E9-1-1 service provider routes the emergency call to the correct PSAP based on the location that is provided with the call. When the client includes a validated Emergency Response Location (ERL) with the emergency call, the provider automatically routes the call to the appropriate PSAP. If the location was manually entered by the user, the Emergency Call Response Center (ECRC) first verbally verifies the accuracy of the location with the caller before routing the emergency call to the PSAP.</span></span>

4.  <span data-ttu-id="507b9-115">Se você configurou a política de local para notificações, um ou mais gerentes de segurança da sua organização receberão uma mensagem instantânea especial de notificação de emergência do Lync.</span><span class="sxs-lookup"><span data-stu-id="507b9-115">If you configured the location policy for notifications, one or more of your organization’s security officers are sent a special Lync emergency notification instant message.</span></span> <span data-ttu-id="507b9-116">Essa mensagem é sempre aberta na(s) tela(s) de seus oficiais de segurança, contendo o nome, número de telefone, horário e local do chamador, permitindo que o pessoal de segurança respondam rapidamente ao chamador de emergência usando uma mensagem instantânea ou voz.</span><span class="sxs-lookup"><span data-stu-id="507b9-116">This message always pops up on the security officers’ screen(s) and contains the caller’s name, phone number, time, and location, enabling security personnel to quickly respond to the emergency caller by using an instant message or voice.</span></span>

5.  <span data-ttu-id="507b9-117">Caso tenha configurado a política de local para conferências e ela seja suportada pelo provedor de serviço de E9-1-1, um Suporte de Segurança é colocado na chamada com áudio uni ou bidirecional.</span><span class="sxs-lookup"><span data-stu-id="507b9-117">If you configured the location policy for conferencing and it is supported by the E9-1-1 service provider, an internal Security Desk is conferenced into the call with either one-way audio or two-way audio.</span></span>

6.  <span data-ttu-id="507b9-118">Se a chamada for interrompida prematuramente, o PSAP usa o número de retorno de chamada para entrar em contato com o chamador diretamente.</span><span class="sxs-lookup"><span data-stu-id="507b9-118">If the call is broken prematurely, the PSAP uses the callback number to contact the caller directly.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

