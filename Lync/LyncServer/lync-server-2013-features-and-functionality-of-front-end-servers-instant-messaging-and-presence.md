---
title: 'Lync Server 2013: Recursos e funcionalidades de servidores front-end, mensagens instantâneas e presença'
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
ms.openlocfilehash: 4a76dfed553e85838739c7c348e5bc53fc9943a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765149"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="features-and-functionality-of-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="568d5-102">Recursos e funcionalidades de servidores front-end, mensagens instantâneas e presença no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="568d5-102">Features and functionality of Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="568d5-103">_**Tópico da última modificação:** 2013-03-17_</span><span class="sxs-lookup"><span data-stu-id="568d5-103">_**Topic Last Modified:** 2013-03-17_</span></span>

<span data-ttu-id="568d5-104">Os servidores front-end fornecem a maioria das funcionalidades do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="568d5-104">Front End Servers provide most Lync Server functionality.</span></span> <span data-ttu-id="568d5-105">Há duas edições disponíveis: Lync Server Enterprise Edition, projetada principalmente para organizações maiores e Lync Server Standard Edition, projetada principalmente para organizações menores que desejam uma Investement de hardware menor e não requer alta disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="568d5-105">There are two editions available: Lync Server Enterprise Edition, which is designed primarily for larger organizations, and Lync Server Standard Edition, which is designed primarily for smaller organizations which want a smaller hardware investement and do not require high availability.</span></span> <span data-ttu-id="568d5-106">Ambas as edições dão suporte a todas as cargas de trabalho do Lync Server, incluindo IM, presença, conferência e Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="568d5-106">Both editions support all Lync Server workloads including IM, presence, conferencing, and Enterprise Voice.</span></span>

<span data-ttu-id="568d5-107">Mensagens instantâneas (IM) permitem que os usuários se comuniquem entre si em tempo real em seus computadores usando mensagens textuais.</span><span class="sxs-lookup"><span data-stu-id="568d5-107">Instant messaging (IM) enables your users to communicate with each other in real time on their computers using text-based messages.</span></span> <span data-ttu-id="568d5-108">Tanto sessões de IM de duas partes como as multipartes são suportadas.</span><span class="sxs-lookup"><span data-stu-id="568d5-108">Both two-party and multiparty IM sessions are supported.</span></span> <span data-ttu-id="568d5-109">Um participante de uma conversa via IM de duas partes pode adicionar um terceiro participante à conversa a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="568d5-109">A participant in a two-party IM conversation can add a third participant to the conversation at any time.</span></span> <span data-ttu-id="568d5-110">Quando isso acontece, a janela de conversa muda para dar suporte aos recursos de conferência.</span><span class="sxs-lookup"><span data-stu-id="568d5-110">When this happens, the Conversation window changes to support conferencing features.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="568d5-111">Os clientes do Lync e do Communicator, quando envolvidos em uma comunicação de um para um, geralmente são chamados de ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="568d5-111">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="568d5-112">Tecnicamente, os dois clientes estão se comunicando em uma conversa de uma ou uma, com a IMMCU (unidade de controle Multipoint) do chat no meio.</span><span class="sxs-lookup"><span data-stu-id="568d5-112">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="568d5-113">O IMMCU é um componente do servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="568d5-113">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="568d5-114">Colocar o IMMCU no fluxo de trabalho de comunicação necessário permite a gravação de detalhes da chamada e outros recursos que o servidor de front-end permite.</span><span class="sxs-lookup"><span data-stu-id="568d5-114">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="568d5-115">A comunicação é de uma porta de origem dinâmica no cliente para a porta de servidor front-end TLS/TCP/5061 (pressupondo o uso da segurança da camada de transporte recomendada).</span><span class="sxs-lookup"><span data-stu-id="568d5-115">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="568d5-116">Por design, a comunicação ponto a ponto (bem como mensagens instantâneas de vários participantes) só é possível quando o Lync Server e o IMMCU estão ativos e disponíveis.</span><span class="sxs-lookup"><span data-stu-id="568d5-116">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<span data-ttu-id="568d5-117">A *presença* fornece informações aos usuários sobre o status de outros na rede.</span><span class="sxs-lookup"><span data-stu-id="568d5-117">*Presence* provides information to users about the status of other on the network.</span></span> <span data-ttu-id="568d5-118">O status de presença de um usuário fornece informações para ajudar outros usuários a decidir se devem tentar entrar em contato com o usuário e se devem fazê-lo por mensagem instantânea, telefone ou email.</span><span class="sxs-lookup"><span data-stu-id="568d5-118">A user’s presence status provides information to help others decide whether they should try to contact the user and whether to use instant messaging, phone, or email.</span></span> <span data-ttu-id="568d5-119">A Presença encoraja a comunicação instantânea quando possível, mas também dá informações sobre se um usuário está em reunião ou fora do escritório, indicando que a comunicação instantânea não é possível.</span><span class="sxs-lookup"><span data-stu-id="568d5-119">Presence encourages instant communication when possible, but it also provides information about whether a user is in a meeting or out of the office, indicating that instant communication is not possible.</span></span> <span data-ttu-id="568d5-120">Esse status de presença é exibido como um ícone de presença no Lync e outros aplicativos compatíveis com presença, incluindo o cliente de mensagens e colaboração do Microsoft Outlook, as tecnologias do Microsoft SharePoint, o Microsoft Word e a planilha do Microsoft Excel softwares.</span><span class="sxs-lookup"><span data-stu-id="568d5-120">This presence status is displayed as a presence icon in Lync and other presence-aware applications, including the Microsoft Outlook messaging and collaboration client, Microsoft SharePoint technologies, Microsoft Word, and Microsoft Excel spreadsheet software.</span></span> <span data-ttu-id="568d5-121">O ícone de presença representa a disponibilidade e a propensão do usuário para se comunicar naquele momento.</span><span class="sxs-lookup"><span data-stu-id="568d5-121">The presence icon represents the user’s current availability and willingness to communicate.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

