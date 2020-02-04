---
title: 'Lync Server 2013: suporte à integração do Exchange e do SharePoint'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exchange and SharePoint integration support
ms:assetid: 72bf8aa5-55b1-4851-8a59-c96bf85d215a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205005(v=OCS.15)
ms:contentKeyID: 48184504
ms.date: 01/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 198df79f63415affa4fb9b41d55265b58ae00a8a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756255"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exchange-and-sharepoint-integration-support-in-lync-server-2013"></a><span data-ttu-id="18a6c-102">Suporte à integração do Exchange e do SharePoint no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18a6c-102">Exchange and SharePoint integration support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18a6c-103">_**Tópico da última modificação:** 2017-01-18_</span><span class="sxs-lookup"><span data-stu-id="18a6c-103">_**Topic Last Modified:** 2017-01-18_</span></span>

<span data-ttu-id="18a6c-104">O Lync Server 2013 e o Lync 2013 podem comunicar-se com segurança com outros aplicativos e produtos de servidor, incluindo o Office 2013, o Exchange Server 2013, o Exchange Server 2016 e o SharePoint, caso você integre esses produtos.</span><span class="sxs-lookup"><span data-stu-id="18a6c-104">Lync Server 2013 and Lync 2013 can securely and seamlessly communicate with other applications and server products, including Office 2013, Exchange Server 2013, Exchange Server 2016, and SharePoint, if you integrate these products.</span></span> <span data-ttu-id="18a6c-105">A integração do Lync Server 2013 e do Office oferece aos usuários acesso ao contexto às funcionalidades de mensagens instantâneas (IM), presença avançada, telefonia e conferência do Lync.</span><span class="sxs-lookup"><span data-stu-id="18a6c-105">Integrating Lync Server 2013 and Office provides users with in-context access to the instant messaging (IM), enhanced presence, telephony, and conferencing capabilities of Lync.</span></span> <span data-ttu-id="18a6c-106">Os usuários do Office podem acessar os recursos do Lync no cliente de mensagens e colaboração do Outlook 2013 e em outros programas do Office ou em uma página do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="18a6c-106">Office users can access Lync features from within the Outlook 2013 messaging and collaboration client and other Office programs or from a SharePoint page.</span></span> <span data-ttu-id="18a6c-107">Os usuários também podem exibir um registro de conversas do Lync na pasta histórico da conversa do Outlook.</span><span class="sxs-lookup"><span data-stu-id="18a6c-107">Users can also view a record of Lync conversations in the Outlook Conversation History folder.</span></span> <span data-ttu-id="18a6c-108">Quando integrado com o Exchange 2013, o Exchange 2016 ou o Exchange Online, o Lync Server 2013 também é compatível com o seguinte:</span><span class="sxs-lookup"><span data-stu-id="18a6c-108">When integrated with Exchange 2013, Exchange 2016, or Exchange Online, Lync Server 2013 also supports the following:</span></span>

  - <span data-ttu-id="18a6c-109">Repositório de contatos unificado, que permite aos usuários armazenar todas as informações de contato no Exchange ou no Exchange Online para que as informações estejam disponíveis globalmente no Lync 2013, Exchange, Outlook e Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="18a6c-109">Unified contact store, which enables users to store all contact information in Exchange or Exchange Online so that the information is available globally across Lync 2013, Exchange, Outlook, and Outlook Web App.</span></span>

  - <span data-ttu-id="18a6c-110">Histórico de conversas e histórico de webconferências, que é armazenado nas pastas de usuário do Exchange.</span><span class="sxs-lookup"><span data-stu-id="18a6c-110">Conversation history and Web conferencing history, which is stored in Exchange user folders.</span></span>

  - <span data-ttu-id="18a6c-111">O conteúdo arquivado do Lync, como mensagens instantâneas e conteúdo da reunião, pode ser armazenado no armazenamento do Exchange.</span><span class="sxs-lookup"><span data-stu-id="18a6c-111">Archived content from Lync, such as IM and meeting content, can be stored in Exchange storage.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="18a6c-112">O Lync Server 2013 dá suporte à integração com versões anteriores do Microsoft Exchange Server e do SharePoint Server, mas nem toda a funcionalidade tem suporte com essas versões anteriores, como a integração do armazenamento de arquivamento com o Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="18a6c-112">Lync Server 2013 supports integration with previous versions of Microsoft Exchange Server and SharePoint Server, but not all functionality is supported with these previous versions, such as integration of Archiving storage with Microsoft Exchange.</span></span><BR><span data-ttu-id="18a6c-113">Se você estiver migrando seus usuários para o Exchange 2013 ou o Exchange 2016, poderá usar o armazenamento do Exchange e o armazenamento do Lync Server de forma provisória enquanto concluir a migração.</span><span class="sxs-lookup"><span data-stu-id="18a6c-113">If you are migrating your users to Exchange 2013 or Exchange 2016, you can use both Exchange storage and Lync Server storage on an interim basis, while you complete the migration.</span></span> <span data-ttu-id="18a6c-114">Não há suporte para o uso permanente do armazenamento do Exchange e do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="18a6c-114">Permanent use of both Exchange and Lync Server storage is not supported.</span></span>



</div>

<span data-ttu-id="18a6c-115">A integração do Lync Server 2013 com o Exchange Server e do SharePoint Server requer a autenticação de servidor para servidor entre servidores que executam o Lync Server 2013, o Exchange Server e o SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="18a6c-115">Integration of Lync Server 2013 with Exchange Server and SharePoint Server requires server-to-server authentication between servers running Lync Server 2013, Exchange Server, and SharePoint Server.</span></span> <span data-ttu-id="18a6c-116">O Lync Server 2013 oferece suporte ao protocolo OAuth (autorização aberta) para autenticação e autorização de servidor para servidor.</span><span class="sxs-lookup"><span data-stu-id="18a6c-116">Lync Server 2013 supports OAuth (Open Authorization) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="18a6c-117">Para a autenticação de servidor para servidor local entre dois servidores da Microsoft, não é necessário usar um servidor de token de terceiros.</span><span class="sxs-lookup"><span data-stu-id="18a6c-117">For on-premises server-to-server authentication between two Microsoft servers, there is no need to use a third-party token server.</span></span> <span data-ttu-id="18a6c-118">O Lync Server 2013, o Exchange Server e o SharePoint Server têm um servidor de token interno que pode ser usado para fins de autenticação entre si.</span><span class="sxs-lookup"><span data-stu-id="18a6c-118">Lync Server 2013, Exchange Server, and SharePoint Server have a built-in token server that can be used for authentication purposes with each other.</span></span> <span data-ttu-id="18a6c-119">Por exemplo, o Lync Server 2013 pode emitir e assinar um token de segurança por si só e usar esse token ao se comunicar com o Exchange.</span><span class="sxs-lookup"><span data-stu-id="18a6c-119">For example, Lync Server 2013 can issue and sign a security token by itself, and use that token when communicating with Exchange.</span></span> <span data-ttu-id="18a6c-120">Nesse caso, não é necessário usar um servidor de token de terceiros.</span><span class="sxs-lookup"><span data-stu-id="18a6c-120">In this case, there is no need to use a third-party token server.</span></span>

<span data-ttu-id="18a6c-121">O Lync Server 2013 dá suporte a dois cenários de autenticação de servidor para servidor.</span><span class="sxs-lookup"><span data-stu-id="18a6c-121">Lync Server 2013 supports the two server-to-server authentication scenarios.</span></span> <span data-ttu-id="18a6c-122">Isso inclui configuração de autenticação de servidor para servidor entre os seguintes:</span><span class="sxs-lookup"><span data-stu-id="18a6c-122">These include configuration of server-to-server authentication between the following:</span></span>

  - <span data-ttu-id="18a6c-123">Uma instalação local do Lync Server 2013 e uma instalação local do Exchange Server 2013, Exchange Server 2016 e/ou SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="18a6c-123">An on-premise installation of Lync Server 2013 and an on-premises installation of Exchange Server 2013, Exchange Server 2016, and/or SharePoint Server.</span></span>

  - <span data-ttu-id="18a6c-124">Um par de componentes do Office (por exemplo, entre o Microsoft Exchange 365 e o Microsoft Lync Server 365 ou entre o Microsoft Lync Server 365 e o Microsoft SharePoint 365).</span><span class="sxs-lookup"><span data-stu-id="18a6c-124">A pair of Office components (for example, between Microsoft Exchange 365 and Microsoft Lync Server 365, or between Microsoft Lync Server 365 and Microsoft SharePoint 365).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="18a6c-125">Não há suporte para a autenticação de servidor para servidor entre um servidor local e um componente do Office 365 neste lançamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="18a6c-125">Server-to-server authentication between an on-premises server and an Office 365 component is not supported in this Lync Server 2013 release.</span></span> <span data-ttu-id="18a6c-126">Entre outras coisas, isso significa que você não pode configurar a autenticação de servidor para servidor entre uma instalação local do Lync Server 2013 e do Microsoft Exchange 365.</span><span class="sxs-lookup"><span data-stu-id="18a6c-126">Among other things, this means that you cannot set up server-to-server authentication between an on-premises installation of Lync Server 2013 and Microsoft Exchange 365.</span></span>



</div>

<span data-ttu-id="18a6c-127">Para obter detalhes sobre a autenticação de servidor para servidor, consulte [Gerenciando a autenticação de servidor para servidor (OAuth) e aplicativos de parceiros no Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) na documentação de implantação ou documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="18a6c-127">For details about server-to-server authentication, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or Operations documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

