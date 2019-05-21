---
title: Considerações sobre migração do Sistema de Salas do Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: Leia este tópico para saber mais sobre como implantar o sistema de sala do Skype em um ambiente com várias versões do Skype for Business Server e do Lync Server.
ms.openlocfilehash: 35dd7cff34134791ebaf62bf4d0fcd1cf3b83a4c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293519"
---
# <a name="skype-room-system-migration-considerations"></a><span data-ttu-id="8fc96-103">Considerações sobre migração do Sistema de Salas do Skype</span><span class="sxs-lookup"><span data-stu-id="8fc96-103">Skype Room System migration considerations</span></span>
 
<span data-ttu-id="8fc96-104">Leia este tópico para saber mais sobre como implantar o sistema de sala do Skype em um ambiente com várias versões do Skype for Business Server e do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8fc96-104">Read this topic to learn about how to deploy Skype Room System in an environment that has multiple versions of Skype for Business Server and Lync Server.</span></span>
  
## <a name="migration-considerations"></a><span data-ttu-id="8fc96-105">Considerações sobre migração</span><span class="sxs-lookup"><span data-stu-id="8fc96-105">Migration considerations</span></span>

<span data-ttu-id="8fc96-106">Esta seção fornece orientação se você estiver implantando o sistema de sala da Skype em um ambiente com vários pools que inclua versões diferentes do Skype for Business Server ou do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8fc96-106">This section provides guidance if you are deploying Skype Room System in a multi-pool environment that includes different versions of Skype for Business Server, or Lync Server.</span></span> 
  
<span data-ttu-id="8fc96-107">O componente User Replicator (UR) no Lync Server obtém objetos de usuário do Active Directory e os coloca no back-end do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8fc96-107">The User Replicator (UR) component in Lync Server gets user objects from Active Directory and places them into the Lync Server back-end SQL Server database.</span></span> <span data-ttu-id="8fc96-108">Somente o UR no Lync Server 2013 reconhece os objetos do sistema de sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="8fc96-108">Only the UR in Lync Server 2013 is aware of Skype Room System objects.</span></span> <span data-ttu-id="8fc96-109">O UR em versões anteriores do Lync Server e do Office Communications Server não detecta os atributos do Active Directory que designam os objetos LRS e, portanto, não tinha conhecimento deles.</span><span class="sxs-lookup"><span data-stu-id="8fc96-109">The UR in previous versions of Lync Server and Office Communications Server do not detect the Active Directory attributes that designate LRS objects, and therefore was not aware of them.</span></span> 
  
<span data-ttu-id="8fc96-110">Se uma conta do sistema de sala do Skype tentar entrar no Lync e executar a descoberta automática com base no registro SRV ou DNS A procurar por um registro e se essas contas apontarem para uma versão anterior do Lync Server ou Office Communications Server, o LRS receberá uma resposta do 404 não encontrada do  o pool herdado.</span><span class="sxs-lookup"><span data-stu-id="8fc96-110">If a Skype Room System account tries to sign in to Lync , and performs auto discovery based on SRV record or DNS A record look up, and if those accounts point to a previous version of Lync Server or Office Communications Server, LRS will receive a 404 Not Found response from the legacy pool.</span></span> <span data-ttu-id="8fc96-111">O pool herdado não poderá redirecionar o sistema de sala da Skype para o pool Home do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8fc96-111">The legacy pool will not be able to redirect Skype Room System to its Lync Server 2013 home pool.</span></span> 
  
<span data-ttu-id="8fc96-112">Você pode resolver este problema com as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="8fc96-112">You can address this problem with the following options:</span></span> 
  
- <span data-ttu-id="8fc96-113">Nomeie o registro SRV de descoberta automática (_sipinternaltls._tcp.contoso.com) para o pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8fc96-113">Point your autodiscover SRV record (_sipinternaltls._tcp.contoso.com) to Lync Server 2013 pool.</span></span>
    
- <span data-ttu-id="8fc96-114">Se a primeira opção não for possível, você deve configurar manualmente o LRS e fornecer o endereço do pool do Lync Server 2013, configurando-o diretamente no aplicativo de console do sistema de sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="8fc96-114">If the first option isn't possible, you must manually configure LRS and provide the Lync Server 2013 pool address by directly configuring it in the Skype Room System console application.</span></span> 
    
- <span data-ttu-id="8fc96-115">Se o sistema de salas da Skype for implantado fora da rede corporativa e um servidor de borda do Lync tiver sido implantado e configurado para apontar para um pool ou diretor herdado, será necessário um site de servidor de borda secundário que aponte para o pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8fc96-115">If Skype Room System is deployed outside the corporate network, and a Lync Edge Server has been deployed and configured to point to a legacy pool or director, a secondary Edge Server site is required, which points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="8fc96-116">Consulte a documentação de implantação do Edge Server para obter mais informações sobre a implantação de um Edge Server secundário.</span><span class="sxs-lookup"><span data-stu-id="8fc96-116">Refer to the Edge Server deployment documentation for more information about deploying a secondary Edge Server.</span></span> 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a><span data-ttu-id="8fc96-117">Interoperabilidade do sistema de sala do Skype com um pool do Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="8fc96-117">Skype Room System Interoperability with a Lync Server 2010 Pool</span></span>

<span data-ttu-id="8fc96-118">Durante a migração, se um usuário que estiver hospedado em um pool do Lync Server 2010 agendar uma reunião e convidar a conta do sistema de sala do Skype, o cliente do sistema da sala do Skype terá funcionalidade limitada enquanto participará da reunião.</span><span class="sxs-lookup"><span data-stu-id="8fc96-118">During migration, if a user who is homed on a Lync Server 2010 pool schedules a meeting and invites the Skype Room System account, the Skype Room System client will have limited functionality while attending the meeting.</span></span> 
  
<span data-ttu-id="8fc96-119">Quando o cliente do sistema de sala do Skype ingressa em uma chamada em conferência programada que foi organizada por um usuário hospedado no Lync Server 2010, o sistema de sala do Skype tem as seguintes limitações na reunião:</span><span class="sxs-lookup"><span data-stu-id="8fc96-119">When the Skype Room System client joins a scheduled conference call that has been organized by a user homed on Lync Server 2010, Skype Room System has the following in-meeting limitations:</span></span> 
  
- <span data-ttu-id="8fc96-120">O sistema de sala da Skype não pode mostrar a Galeria de vídeos de várias exibições.</span><span class="sxs-lookup"><span data-stu-id="8fc96-120">Skype Room System cannot show the multi-view video gallery.</span></span>
    
- <span data-ttu-id="8fc96-121">Se o cliente do sistema de sala do Skype for o apresentador, ele não poderá aplicar bloqueio de vídeo aos participantes.</span><span class="sxs-lookup"><span data-stu-id="8fc96-121">If the Skype Room System client is the presenter, it cannot apply video lock on participants.</span></span>
    
- <span data-ttu-id="8fc96-122">O sistema de sala da Skype não pode mostrar a resolução de vídeo de 1080p (entrada ou saída), mesmo se a política de conferência do Lync Server 2013 permitir, devido ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="8fc96-122">Skype Room System cannot show 1080p video resolution (inbound or outbound), even if the Lync Server 2013 conferencing policy allows it, because of the following:</span></span> 
    
  - <span data-ttu-id="8fc96-123">O Lync Server 2010 não é compatível com a resolução de 1080p.</span><span class="sxs-lookup"><span data-stu-id="8fc96-123">Lync Server 2010 doesn't support 1080p resolution.</span></span>
    
  - <span data-ttu-id="8fc96-124">O sistema de sala do Skype é sempre limitado pela política de conferência do organizador para resolução de vídeo.</span><span class="sxs-lookup"><span data-stu-id="8fc96-124">Skype Room System is always limited by the organizer's conferencing policy for video resolution.</span></span> <span data-ttu-id="8fc96-125">Portanto, mesmo que o pool do Lync 2010 dê suporte à resolução de 720p, o sistema de sala da Skype não poderá tirar proveito da resolução de 720p, desde que a política do organizador não seja compatível.</span><span class="sxs-lookup"><span data-stu-id="8fc96-125">Therefore, even if the Lync 2010 pool supports 720p resolution, Skype Room System will not be able to take advantage of 720p resolution as long as organizer's policy doesn't support it.</span></span> 
    
- <span data-ttu-id="8fc96-p105">Os clientes do Lync 2013 detectam a presença de LRS na sala de reunião e eles são silenciados automaticamente para evitar eco na sala de reunião física. Esse recurso não funciona em reuniões hospedadas no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8fc96-p105">Lync 2013 clients detect LRS presence in the meeting room, and they auto-mute themselves to avoid echo in the physical meeting room. This feature does not work in meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="8fc96-128">Existem limites quanto ao desempenho de compartilhamento da área de trabalho para reuniões hospedadas no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8fc96-128">There are limitations on desktop sharing performance for meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="8fc96-129">Os usuários não poderão ingressar em reuniões privadas (restritas) hospedadas no Lync 2010 com o sistema de sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="8fc96-129">Users won't be able to join private (restricted) meetings that are hosted on Lync 2010 with Skype Room System.</span></span>
    

