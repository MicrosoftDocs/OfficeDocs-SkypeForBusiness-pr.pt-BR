---
title: Considerações sobre migração do Sistema de Salas do Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: Leia este tópico para saber mais sobre como implantar o sistema de sala Skype em um ambiente que possui várias versões do Skype para Business Server e o Lync Server.
ms.openlocfilehash: f71c6557a8b9a98f712541c4424ba57a49536164
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-migration-considerations"></a><span data-ttu-id="bc086-103">Considerações sobre migração do Sistema de Salas do Skype</span><span class="sxs-lookup"><span data-stu-id="bc086-103">Skype Room System migration considerations</span></span>
 
<span data-ttu-id="bc086-104">Leia este tópico para saber mais sobre como implantar o sistema de sala Skype em um ambiente que possui várias versões do Skype para Business Server e o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bc086-104">Read this topic to learn about how to deploy Skype Room System in an environment that has multiple versions of Skype for Business Server and Lync Server.</span></span>
  
## <a name="migration-considerations"></a><span data-ttu-id="bc086-105">Considerações sobre migração</span><span class="sxs-lookup"><span data-stu-id="bc086-105">Migration considerations</span></span>

<span data-ttu-id="bc086-106">Esta seção fornece orientação se você estiver implantando o sistema de sala Skype em um ambiente de várias pool que inclui versões diferentes do Skype para Business Server, o Lync Server ou o Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="bc086-106">This section provides guidance if you are deploying Skype Room System in a multi-pool environment that includes different versions of Skype for Business Server, Lync Server, or Office Communications Server 2007 R2.</span></span> 
  
<span data-ttu-id="bc086-107">O componente User Replicator (UR) no Lync Server obtém objetos de usuário do Active Directory e os coloca no back-end do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bc086-107">The User Replicator (UR) component in Lync Server gets user objects from Active Directory and places them into the Lync Server back-end SQL Server database.</span></span> <span data-ttu-id="bc086-108">Somente o UR no Lync Server 2013 está ciente dos objetos do sistema do Skype sala.</span><span class="sxs-lookup"><span data-stu-id="bc086-108">Only the UR in Lync Server 2013 is aware of Skype Room System objects.</span></span> <span data-ttu-id="bc086-109">O UR em versões anteriores do Lync Server e do Office Communications Server não detecta os atributos do Active Directory que designam os objetos LRS e, portanto, não tinha conhecimento deles.</span><span class="sxs-lookup"><span data-stu-id="bc086-109">The UR in previous versions of Lync Server and Office Communications Server do not detect the Active Directory attributes that designate LRS objects, and therefore was not aware of them.</span></span> 
  
<span data-ttu-id="bc086-110">Se uma conta do sistema do Skype sala tenta entrar no Lync e realiza a descoberta automática com base no registro SRV ou aparência de registro DNS A para cima, e essas contas apontem para uma versão anterior do Lync Server ou o Office Communications Server, LRS receberá uma resposta não encontrado 404 do  o pool herdado.</span><span class="sxs-lookup"><span data-stu-id="bc086-110">If a Skype Room System account tries to sign in to Lync , and performs auto discovery based on SRV record or DNS A record look up, and if those accounts point to a previous version of Lync Server or Office Communications Server, LRS will receive a 404 Not Found response from the legacy pool.</span></span> <span data-ttu-id="bc086-111">O pool herdado não poderão redirecionar o sistema de sala Skype para seu pool doméstico do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bc086-111">The legacy pool will not be able to redirect Skype Room System to its Lync Server 2013 home pool.</span></span> 
  
<span data-ttu-id="bc086-112">Você pode resolver este problema com as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="bc086-112">You can address this problem with the following options:</span></span> 
  
- <span data-ttu-id="bc086-113">Nomeie o registro SRV de descoberta automática (_sipinternaltls._tcp.contoso.com) para o pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bc086-113">Point your autodiscover SRV record (_sipinternaltls._tcp.contoso.com) to Lync Server 2013 pool.</span></span>
    
- <span data-ttu-id="bc086-114">Se a primeira opção não for possível, você deve configurar LRS manualmente e forneça o endereço de pool do Lync Server 2013 definindo-lo diretamente no aplicativo de console do sistema de sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="bc086-114">If the first option isn't possible, you must manually configure LRS and provide the Lync Server 2013 pool address by directly configuring it in the Skype Room System console application.</span></span> 
    
- <span data-ttu-id="bc086-115">Se o sistema de sala do Skype for implantado fora da rede corporativa e um servidor de borda do Lync foi implantado e configurado para apontar para um pool herdado ou diretor, um site secundário do servidor de borda será necessário, que aponta para o pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bc086-115">If Skype Room System is deployed outside the corporate network, and a Lync Edge Server has been deployed and configured to point to a legacy pool or director, a secondary Edge Server site is required, which points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="bc086-116">Consulte a documentação de implantação do Edge Server para obter mais informações sobre a implantação de um Edge Server secundário.</span><span class="sxs-lookup"><span data-stu-id="bc086-116">Refer to the Edge Server deployment documentation for more information about deploying a secondary Edge Server.</span></span> 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a><span data-ttu-id="bc086-117">Interoperabilidade de sistema do Skype sala com um Pool do Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="bc086-117">Skype Room System Interoperability with a Lync Server 2010 Pool</span></span>

<span data-ttu-id="bc086-118">Durante a migração, se um usuário hospedado em um pool do Lync Server 2010 agenda uma reunião e convida a conta de sistema do Skype sala, cliente do sistema de sala Skype será têm recursos limitados ao participar da reunião.</span><span class="sxs-lookup"><span data-stu-id="bc086-118">During migration, if a user who is homed on a Lync Server 2010 pool schedules a meeting and invites the Skype Room System account, the Skype Room System client will have limited functionality while attending the meeting.</span></span> 
  
<span data-ttu-id="bc086-119">Quando o cliente do sistema de sala Skype ingressa em uma chamada em conferência agendada que foi organizada por um usuário hospedado no Lync Server 2010, o sistema de sala Skype tem as seguintes limitações de reunião:</span><span class="sxs-lookup"><span data-stu-id="bc086-119">When the Skype Room System client joins a scheduled conference call that has been organized by a user homed on Lync Server 2010, Skype Room System has the following in-meeting limitations:</span></span> 
  
- <span data-ttu-id="bc086-120">Sistema de sala Skype não é possível exibir a Galeria de vídeo com multi-view.</span><span class="sxs-lookup"><span data-stu-id="bc086-120">Skype Room System cannot show the multi-view video gallery.</span></span>
    
- <span data-ttu-id="bc086-121">Se o cliente do sistema de sala Skype for o apresentador, ele não é possível aplicar o bloqueio de vídeo em participantes.</span><span class="sxs-lookup"><span data-stu-id="bc086-121">If the Skype Room System client is the presenter, it cannot apply video lock on participants.</span></span>
    
- <span data-ttu-id="bc086-122">Sistema de sala Skype não é possível exibir 1080p resolução de vídeo (entrada ou saída), mesmo se a política de conferência do Lync Server 2013 permite que ele, devido a estes motivos:</span><span class="sxs-lookup"><span data-stu-id="bc086-122">Skype Room System cannot show 1080p video resolution (inbound or outbound), even if the Lync Server 2013 conferencing policy allows it, because of the following:</span></span> 
    
  - <span data-ttu-id="bc086-123">Lync Server 2010 não oferece suporte a resolução de 1080p.</span><span class="sxs-lookup"><span data-stu-id="bc086-123">Lync Server 2010 doesn't support 1080p resolution.</span></span>
    
  - <span data-ttu-id="bc086-124">Sistema de sala Skype sempre é limitado pela política de conferência do organizador para resolução de vídeo.</span><span class="sxs-lookup"><span data-stu-id="bc086-124">Skype Room System is always limited by the organizer's conferencing policy for video resolution.</span></span> <span data-ttu-id="bc086-125">Portanto, mesmo se o pool do Lync 2010 oferece suporte a resolução 720 pixels, Skype sala sistema não será capaz de aproveitar resolução 720 pixels desde que ele não oferece suporte a política do organizador.</span><span class="sxs-lookup"><span data-stu-id="bc086-125">Therefore, even if the Lync 2010 pool supports 720p resolution, Skype Room System will not be able to take advantage of 720p resolution as long as organizer's policy doesn't support it.</span></span> 
    
- <span data-ttu-id="bc086-p105">Os clientes do Lync 2013 detectam a presença de LRS na sala de reunião e eles são silenciados automaticamente para evitar eco na sala de reunião física. Esse recurso não funciona em reuniões hospedadas no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bc086-p105">Lync 2013 clients detect LRS presence in the meeting room, and they auto-mute themselves to avoid echo in the physical meeting room. This feature does not work in meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="bc086-128">Existem limites quanto ao desempenho de compartilhamento da área de trabalho para reuniões hospedadas no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bc086-128">There are limitations on desktop sharing performance for meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="bc086-129">Os usuários não poderão ingressar em particulares (restritas) reuniões hospedadas no Lync 2010 com o sistema de sala Skype.</span><span class="sxs-lookup"><span data-stu-id="bc086-129">Users won't be able to join private (restricted) meetings that are hosted on Lync 2010 with Skype Room System.</span></span>
    

