---
title: 'Lync Server 2013: IM e presença'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IM and presence
ms:assetid: 6a93ae95-3b64-410b-ab72-74dea232f065
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417162(v=OCS.15)
ms:contentKeyID: 48184398
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57f57d4fae488a7d4946a0adb1f8350d02114a7d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742381"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="im-and-presence-in-lync-server-2013"></a><span data-ttu-id="ebda6-102">IM e presença no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ebda6-102">IM and presence in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ebda6-103">_**Tópico da última modificação:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="ebda6-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="ebda6-104">As mensagens instantâneas (IM) e a presença são instaladas automaticamente em qualquer implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ebda6-104">Instant messaging (IM) and presence are automatically installed in any Lync Server deployment.</span></span>

<span data-ttu-id="ebda6-105">As informações de *presença* permitem que os usuários adotem os colegas no momento certo com a forma certa de comunicação, para levar a um ambiente de trabalho mais produtivo.</span><span class="sxs-lookup"><span data-stu-id="ebda6-105">*Presence* information enables users to approach colleagues at the right time with the right form of communication, to lead to a more productive work environment.</span></span> <span data-ttu-id="ebda6-106">A presença de um usuário é um conjunto de informações que inclui disponibilidade, disposição para se comunicar, anotações adicionais (como local e status) e como o usuário pode ser contatado.</span><span class="sxs-lookup"><span data-stu-id="ebda6-106">A user’s presence is a collection of information that includes availability, willingness to communicate, additional notes (such as location and status), and how the user can be contacted.</span></span> <span data-ttu-id="ebda6-107">A presença é aprimorada no Lync Server com imagens, informações de localização e um conjunto rico de Estados de presença que inclui "fora do trabalho", "não incomodar" e "retomar logo", além de Estados básicos, como "disponível," "ocupado" e "em uma conferência".</span><span class="sxs-lookup"><span data-stu-id="ebda6-107">Presence is enhanced in Lync Server with pictures, location information, and a rich set of presence states that includes “Off Work,” “Do Not Disturb,” and “Be Right Back,” in addition to basic states such as “Available,” “Busy,” and “In a Conference.”</span></span> <span data-ttu-id="ebda6-108">Os administradores também podem definir Estados de presença personalizados e específicos da organização.</span><span class="sxs-lookup"><span data-stu-id="ebda6-108">Administrators can also define customized, organization-specific presence states.</span></span>

<span data-ttu-id="ebda6-109">As opções de gerenciamento de contatos e acesso do usuário permitem que os usuários controlem quais informações outras pessoas podem ver.</span><span class="sxs-lookup"><span data-stu-id="ebda6-109">Contact management and user access options enable users to control what information others can see.</span></span> <span data-ttu-id="ebda6-110">Os usuários podem definir diferentes níveis de contatos, cada um podendo exibir diferentes níveis de informações de presença.</span><span class="sxs-lookup"><span data-stu-id="ebda6-110">Users can set different levels of contacts, each of which can view different levels of presence information.</span></span>

<span data-ttu-id="ebda6-111">Simplesmente olhando para uma lista de contatos, os usuários podem encontrar tudo o que precisa saber em um relance.</span><span class="sxs-lookup"><span data-stu-id="ebda6-111">By simply looking at a Contacts list, users can find everything they need to know at a glance.</span></span> <span data-ttu-id="ebda6-112">Ícones coloridos simples indicam o status de presença de outros usuários, e a imagem e a localização também são mostradas.</span><span class="sxs-lookup"><span data-stu-id="ebda6-112">Simple colored icons indicate other users’ presence status, and picture and location are also shown.</span></span>

<span data-ttu-id="ebda6-113">Com a integração entre o Lync Server e outros produtos, como o Outlook e o SharePoint, sempre que o nome de um contato for exibido, como em uma mensagem de email ou em um site de equipe, as informações de status e contato também serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="ebda6-113">With the integration between Lync Server and other products such as Outlook and SharePoint, whenever a contact’s name appears, such as in an email message or on a team website, the status and contact information is also displayed.</span></span> <span data-ttu-id="ebda6-114">Além disso, se você implantar o Exchange 2013, o Lync Server e o Exchange 2013 podem compartilhar um repositório de contatos unificado, que pode ser acessado por clientes de qualquer um dos produtos.</span><span class="sxs-lookup"><span data-stu-id="ebda6-114">Additionally, if you deploy Exchange 2013, Lync Server and Exchange 2013 can share a unified contact store, which can be accessed by clients of either product.</span></span>

<span data-ttu-id="ebda6-115">Com o recurso de mensagens instantâneas no Lync Server, os usuários podem rapidamente enviar uma mensagem para a outra com informações oportunas.</span><span class="sxs-lookup"><span data-stu-id="ebda6-115">With instant messaging in Lync Server, users can quickly message each other with timely information.</span></span> <span data-ttu-id="ebda6-116">Se você preferir, os usuários também poderão se comunicar com usuários de redes públicas de mensagens instantâneas, como MSN/\!Windows Live, Yahoo e AOL.</span><span class="sxs-lookup"><span data-stu-id="ebda6-116">If you prefer, your users can also communicate with users of public IM networks such as MSN/Windows Live, Yahoo\!, and AOL.</span></span> <span data-ttu-id="ebda6-117">Observe que uma licença separada pode ser necessária para conectividade de IM pública com o Windows Live, AOL e Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="ebda6-117">Note that a separate license might be required for public IM connectivity with Windows Live, AOL, and Yahoo\!</span></span> <span data-ttu-id="ebda6-118">O Lync Server também inclui compatibilidade com o protocolo de presença e mensagens extensíveis (XMPP), para que os usuários possam trocar mensagens INSTANTÂNEAs e informações de presença com usuários do XMPP Services, como o Google Talk.</span><span class="sxs-lookup"><span data-stu-id="ebda6-118">Lync Server also includes Extensible Messaging and Presence Protocol (XMPP) compatibility, so your users can exchange IM messages and presence information with users of XMPP services such as Google Talk.</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="ebda6-119">A partir de 1º de setembro de 2012, a licença de assinatura de usuário da conectividade de mensagem de chat pública do Microsoft Lync ("PIC USL") não está mais disponível para compra de contratos novos ou de renovação.</span><span class="sxs-lookup"><span data-stu-id="ebda6-119">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="ebda6-120">Os clientes com licenças ativas poderão continuar a federar-se com o Yahoo!</span><span class="sxs-lookup"><span data-stu-id="ebda6-120">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="ebda6-121">Messenger até a data de encerramento do serviço.</span><span class="sxs-lookup"><span data-stu-id="ebda6-121">Messenger until the service shut down date.</span></span> <span data-ttu-id="ebda6-122">Uma data de fim da vida útil de junho de 2014 para AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="ebda6-122">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="ebda6-123">foi anunciado.</span><span class="sxs-lookup"><span data-stu-id="ebda6-123">has been announced.</span></span> <span data-ttu-id="ebda6-124">Para obter detalhes, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">suporte para conectividade de mensagens instantâneas públicas no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ebda6-124">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="ebda6-125">O PIC USL é uma licença de assinatura por usuário por mês necessária para o Lync Server ou o Office Communications Server se federar com o Yahoo!</span><span class="sxs-lookup"><span data-stu-id="ebda6-125">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="ebda6-126">Spam.</span><span class="sxs-lookup"><span data-stu-id="ebda6-126">Messenger.</span></span> <span data-ttu-id="ebda6-127">A capacidade da Microsoft de oferecer esse serviço por meio do suporte do Yahoo!, o contrato subjacente para o qual está prestes a ser enrolado.</span><span class="sxs-lookup"><span data-stu-id="ebda6-127">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="ebda6-128">Mais do que nunca, o Lync é uma ferramenta poderosa para a conexão entre organizações e pessoas ao redor do mundo.</span><span class="sxs-lookup"><span data-stu-id="ebda6-128">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="ebda6-129">A Federação com o Windows Live Messenger não requer licenças de usuário/dispositivo adicionais além da CAL padrão do Lync.</span><span class="sxs-lookup"><span data-stu-id="ebda6-129">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="ebda6-130">A Federação do Skype será adicionada a essa lista, permitindo que os usuários do Lync atinjam centenas de milhões de pessoas com mensagens instantâneas e voz.</span><span class="sxs-lookup"><span data-stu-id="ebda6-130">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="ebda6-131">O histórico de conversas permite que os usuários acompanhem as conversas de mensagens instantâneas antigas e recuperem as informações que podem ter sido comunicadas por meses de mensagens instantâneas atrás.</span><span class="sxs-lookup"><span data-stu-id="ebda6-131">Conversation history enables users to keep track of old IM conversations, and retrieve information that may have been communicated by IM months ago.</span></span>

<span data-ttu-id="ebda6-132">O recurso de chat persistente permite que os usuários participem de um meio de conversas com base em um tópico que persistem ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="ebda6-132">The Persistent Chat feature enables users to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="ebda6-133">As mensagens postadas em salas de chat (fóruns de discussão) podem ser persistentes (ou seja, disponíveis ao longo do tempo), para que as pessoas de locais e departamentos diferentes possam participar, mesmo quando não estiverem online ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="ebda6-133">Messages posted to chat rooms (discussion forums) can be persistent (that is, available over time), so that people from different locations and departments can participate, even when they are not all online at the same time.</span></span>

<span data-ttu-id="ebda6-134">Se a sua organização deve seguir as normas de conformidade, você pode implantar um recurso de arquivamento de mensagens para arquivar o conteúdo de mensagens instantâneas para todos os usuários em sua organização ou somente para determinados usuários que você especificar.</span><span class="sxs-lookup"><span data-stu-id="ebda6-134">If your organization must follow compliance regulations, you can deploy a message archiving feature to archive the content of instant messages for all users in your organization, or for only certain users you specify.</span></span> <span data-ttu-id="ebda6-135">Se você também implantar o Exchange 2013, o arquivamento de mensagens instantâneas poderá ser integrado ao recurso bloqueio in-loco do Exchange para fornecer uma única experiência de administração para a conformidade.</span><span class="sxs-lookup"><span data-stu-id="ebda6-135">If you also deploy Exchange 2013, your IM archive can be integrated with the In-Place Hold feature of Exchange, to provide a single administration experience for your compliance.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

