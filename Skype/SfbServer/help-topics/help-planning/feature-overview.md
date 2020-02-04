---
title: Feature Overview (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/6/2016
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.plan.FeatureOverview
- ms.lync.plan.FeatureOverview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44783b37-c87f-41f2-9de1-39176f1856ab
description: Skype for Business Server 2015 Planning Tool
ms.openlocfilehash: 81b674f55098f22f2bbff2db65219226c195e0f2
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685454"
---
# <a name="feature-overview-planning-tool"></a><span data-ttu-id="1d706-103">Feature Overview (Planning Tool)</span><span class="sxs-lookup"><span data-stu-id="1d706-103">Feature Overview (Planning Tool)</span></span>
 
<span data-ttu-id="1d706-104">Skype for Business Server 2015 Planning Tool</span><span class="sxs-lookup"><span data-stu-id="1d706-104">Skype for Business Server 2015 Planning Tool</span></span>
  
<span data-ttu-id="1d706-105">Você pode usar a página **sites centrais** da ferramenta de planejamento para criar a implantação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="1d706-105">You can use the **Central Sites** page of the Planning Tool to design the Skype for Business Server deployment.</span></span> <span data-ttu-id="1d706-106">Você pode criar tanto uma implantação centralizada quanto um distribuída.</span><span class="sxs-lookup"><span data-stu-id="1d706-106">You can create two either a centralized or distributed deployment.</span></span> <span data-ttu-id="1d706-107">Uma implantação centralizada tem apenas um site central, que se refere a todos os usuários do Skype for Business em sua organização.</span><span class="sxs-lookup"><span data-stu-id="1d706-107">A centralized deployment only has one central site, which homes all Skype for Business users in your organization.</span></span> <span data-ttu-id="1d706-108">Uma implantação distribuída possui mais de um site central.</span><span class="sxs-lookup"><span data-stu-id="1d706-108">A distributed deployment has more than one central site.</span></span> <span data-ttu-id="1d706-109">Se você implantar o Skype for Business Server em vários sites centrais, será inserido o número de usuários em cada site central na ferramenta de planejamento.</span><span class="sxs-lookup"><span data-stu-id="1d706-109">If you deploy Skype for Business Server at multiple central sites, then you will enter the number of users at each central site in the Planning Tool.</span></span>
  
<span data-ttu-id="1d706-110">Para completar a definição do site central, primeiro você precisa fornecer as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="1d706-110">To complete the definition of the central site, you first need to provide the following information:</span></span>
  
- <span data-ttu-id="1d706-111">\*\*Nome do site \*\* Insira o nome do Site central.</span><span class="sxs-lookup"><span data-stu-id="1d706-111">**Site Name** Enter the name of the Central Site.</span></span>
    
- <span data-ttu-id="1d706-112">**Número de Usuários** Insira o número de usuários, incluindo usuários em sites de filial que estão hospedados no site central.</span><span class="sxs-lookup"><span data-stu-id="1d706-112">**Number of Users** Enter the number of users, including users at branch sites who are homed into the central site.</span></span>
    
- <span data-ttu-id="1d706-113">**Usuários hospedados na nuvem** Digite o número de usuários que são hospedados no site central pelo Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="1d706-113">**Cloud Homed Users** Enter the number of users that are homed into the central site from Skype for Business Online.</span></span>
    
## <a name="ui-elements"></a><span data-ttu-id="1d706-114">Elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="1d706-114">UI Elements</span></span>

<span data-ttu-id="1d706-115">Os elementos restantes foram populados com respostas que você forneceu às perguntas apresentadas no assistente da **Introdução** ou, se você tiver pulado o assistente, será populado automaticamente pela ferramenta de planejamento.</span><span class="sxs-lookup"><span data-stu-id="1d706-115">The remaining elements have either been populated with the answers you provided to the questions presented in the **Get Started** wizard, or, if you skipped the wizard, automatically populated by the planning tool.</span></span>
  
### <a name="online-collaboration"></a><span data-ttu-id="1d706-116">Colaboração online</span><span class="sxs-lookup"><span data-stu-id="1d706-116">Online Collaboration</span></span>

 <span data-ttu-id="1d706-117">A  **Colaboração online** contém as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="1d706-117">**Online Collaboration** contains the following options:</span></span>
  
- <span data-ttu-id="1d706-118">**Mensagens instantâneas e presença**</span><span class="sxs-lookup"><span data-stu-id="1d706-118">**IM and Presence**</span></span>
    
    <span data-ttu-id="1d706-119">A mensagem instantânea permite que os usuários se comuniquem entre si em tempo real em seus computadores usando mensagens de texto.</span><span class="sxs-lookup"><span data-stu-id="1d706-119">Instant Messaging (IM) enables users to communicate with each other in real time on their computers using text-based messages.</span></span> <span data-ttu-id="1d706-120">Tanto as sessões de mensagem instantânea entre duas partes como as entre várias partes são suportadas.</span><span class="sxs-lookup"><span data-stu-id="1d706-120">Both two-party and multiparty IM sessions are supported.</span></span> <span data-ttu-id="1d706-121">A presença fornece informações a usuários sobre o status de outros na rede.</span><span class="sxs-lookup"><span data-stu-id="1d706-121">Presence provides information to users about the status of others on the network.</span></span> <span data-ttu-id="1d706-122">O status de presença de um usuário fornece informações para ajudar outras pessoas a determinarem se o usuário está online e como entrar em contato com ele melhor.</span><span class="sxs-lookup"><span data-stu-id="1d706-122">A user's presence status provides information to help others determine whether the user is online and how to best contact the user.</span></span> <span data-ttu-id="1d706-123">Por exemplo, a melhor forma de contatar um usuário que está em uma reunião é via email.</span><span class="sxs-lookup"><span data-stu-id="1d706-123">For example, a user who is in a meeting is best contacted by email.</span></span>
    
- <span data-ttu-id="1d706-124">**Conferência de áudio e vídeo**</span><span class="sxs-lookup"><span data-stu-id="1d706-124">**Audio and Video Conferencing**</span></span>
    
    <span data-ttu-id="1d706-125">A conferência de áudio/vídeo (A/V) permite conferências de áudio e vídeo em tempo real.</span><span class="sxs-lookup"><span data-stu-id="1d706-125">Audio/Video (A/V) conferencing enables real-time audio and video conferences.</span></span>
    
- <span data-ttu-id="1d706-126">**Conferência discada**</span><span class="sxs-lookup"><span data-stu-id="1d706-126">**Dial-in Conferencing**</span></span>
    
    <span data-ttu-id="1d706-p103">A conferência discada permite que os usuários participem de uma A/V a partir de um telefone na PSTN. A conferência discada requer a implantação dos aplicativos Atendedor de Conferência e Serviço de Comunicado de Conferência.</span><span class="sxs-lookup"><span data-stu-id="1d706-p103">Dial-in conferencing enables users to join an A/V from a telephone on the PSTN. Dial-in conferencing requires that you deploy the Conferencing Attendant and Conferencing Announcement Service applications.</span></span>
    
- <span data-ttu-id="1d706-129">**Webconferência**</span><span class="sxs-lookup"><span data-stu-id="1d706-129">**Web Conferencing**</span></span>
    
    <span data-ttu-id="1d706-130">A Webconferência permite que os usuários empresariais internos e externos ao firewall criem e participem de conferências em tempo real hospedados nos servidores internos.</span><span class="sxs-lookup"><span data-stu-id="1d706-130">Web conferencing enables enterprise users inside and outside of the firewall to create and join real-time conferences that are hosted on your internal servers.</span></span>
    
- <span data-ttu-id="1d706-131">**Chat Persistente**</span><span class="sxs-lookup"><span data-stu-id="1d706-131">**Persistent Chat**</span></span>
    
    <span data-ttu-id="1d706-p104">O Chat persistente permite que vários usuários participem de conversas nas quais eles postam e acessam conteúdo sobre tópicos específicos, incluindo texto, links e arquivos. Embora os usuários possam se comunicar em tempo real durante uma sessão, o conteúdo de cada sessão é persistente, o que significa que continua disponível após o fim de uma sessão.</span><span class="sxs-lookup"><span data-stu-id="1d706-p104">Persistent Chat enables multiple users to participate in conversations in which they post and access content about specific topics, including text, links, and files. Although users can communicate in real time during a session, the content of each session is persistent, which means it continues to be available after a session ends.</span></span>
    
### <a name="users"></a><span data-ttu-id="1d706-134">Usuários</span><span class="sxs-lookup"><span data-stu-id="1d706-134">Users</span></span>

 <span data-ttu-id="1d706-135">**Usuários** com as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="1d706-135">**Users** contains the following options:</span></span>
  
- <span data-ttu-id="1d706-136">**Organização interna**</span><span class="sxs-lookup"><span data-stu-id="1d706-136">**Internal organization**</span></span>
    
- <span data-ttu-id="1d706-137">**Federação com outras organizações**</span><span class="sxs-lookup"><span data-stu-id="1d706-137">**Federation with other organizations**</span></span>
    
- <span data-ttu-id="1d706-138">**Federação com versões anteriores**</span><span class="sxs-lookup"><span data-stu-id="1d706-138">**Federation with previous versions**</span></span>
    
- <span data-ttu-id="1d706-p105">**Federação com provedores de serviços de mensagem instantânea públicos** Permite que os usuários na organização estabeleçam comunicação com provedores públicos de serviço de mensagem instantânea, como MSN, Yahoo! e AOL. Uma licença separada é necessária para estabelecer federação com redes públicas de mensagem instantânea.</span><span class="sxs-lookup"><span data-stu-id="1d706-p105">**Federation with public IM services providers** Allows users in your organization to establish communication with public instant messaging service providers such as MSN, Yahoo!, and AOL. A separate license is required to establish federation with public instant messaging networks.</span></span>
    
- <span data-ttu-id="1d706-141">**Federação com provedor de serviço com base XMPP**</span><span class="sxs-lookup"><span data-stu-id="1d706-141">**Federation with XMPP-based service provider**</span></span>
    
    <span data-ttu-id="1d706-142">O Skype for Business Server 2015 apresenta um proxy XMPP totalmente integrado (implantado nos servidores de borda) e um Gateway XMPP implantado em seus servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="1d706-142">Skype for Business Server 2015 introduces a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway deployed on your Front End Servers.</span></span> <span data-ttu-id="1d706-143">Você pode implantar a adição e a configuração do XMPP proxy e do XMPP gateway permitirá que os usuários do Skype for Business Server 2015 adicionem contatos de parceiros baseados em XMPP para mensagens instantâneas (IM) e presença.</span><span class="sxs-lookup"><span data-stu-id="1d706-143">You can deploy Adding and configuring the XMPP proxy and XMPP gateway will allow your Skype for Business Server 2015 users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>
    
- <span data-ttu-id="1d706-144">**Mobilidade**</span><span class="sxs-lookup"><span data-stu-id="1d706-144">**Mobility**</span></span>
    
    <span data-ttu-id="1d706-145">Ao implantar o serviço de mobilidade do Skype for Business Server 2015, os usuários podem usar dispositivos móveis Apple iOS, Android, Windows Phone ou Nokia para executar tais atividades como enviar e receber mensagens instantâneas, ver contatos e ver a presença.</span><span class="sxs-lookup"><span data-stu-id="1d706-145">When you deploy the Skype for Business Server 2015 Mobility Service, users can use supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform such activities as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span>
    
- <span data-ttu-id="1d706-146">**Caixa de correio W15 Exchange**</span><span class="sxs-lookup"><span data-stu-id="1d706-146">**W15 Exchange mailbox**</span></span>
    
    <span data-ttu-id="1d706-147">O Skype for Business Server 2015 permite que você tenha mensagens de correio de voz armazenadas no Exchange Unified Messaging (UM); essas mensagens de correio de voz serão exibidas como mensagens de email nas caixas de entrada dos usuários.</span><span class="sxs-lookup"><span data-stu-id="1d706-147">Skype for Business Server 2015 enables you to have voicemail messages stored in Exchange Unified Messaging (UM); those voicemail messages will then appear as email messages in your users' Inboxes.</span></span>
    
### <a name="voice"></a><span data-ttu-id="1d706-148">Voz</span><span class="sxs-lookup"><span data-stu-id="1d706-148">Voice</span></span>

 <span data-ttu-id="1d706-149">**Voz** contém as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="1d706-149">**Voice** contains the following options:</span></span>
  
- <span data-ttu-id="1d706-150">**Enterprise Voice**</span><span class="sxs-lookup"><span data-stu-id="1d706-150">**Enterprise Voice**</span></span>
    
    <span data-ttu-id="1d706-151">O Enterprise Voice é uma solução VoIP com o software da Microsft.</span><span class="sxs-lookup"><span data-stu-id="1d706-151">Enterprise voice is Microsft's software-powered VoIP solution.</span></span> <span data-ttu-id="1d706-152">O Enterprise Voice permite que os usuários usem o Skype for Business para fazer uma chamada telefônica do computador.</span><span class="sxs-lookup"><span data-stu-id="1d706-152">Enterprise voice enables users to use Skype for Business to place a phone call from their computer.</span></span>
    
- <span data-ttu-id="1d706-153">**Unificação de Mensagens do Exchange**</span><span class="sxs-lookup"><span data-stu-id="1d706-153">**Exchange Unified Messaging**</span></span>
    
    <span data-ttu-id="1d706-154">A Unificação de mensagens do Exchange combina correio de voz e e-mail em uma única infra-estrutura de mensagens.</span><span class="sxs-lookup"><span data-stu-id="1d706-154">Exchange Unified Messaging (UM) combines voice mail and email into a single messaging infrastructure.</span></span> <span data-ttu-id="1d706-155">O Skype for Business Server 2015 usa o Exchange UM para fornecer atendimento de chamadas, acesso ao Assinante, notificação de chamada e serviços de atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="1d706-155">Skype for Business Server 2015 uses Exchange UM to provide call answering, subscriber access, call notification, and auto attendant services.</span></span> <span data-ttu-id="1d706-156">Se você usar esses serviços, será necessário integrar o Exchange UM e o Skype for Business Server em uma topologia compartilhada do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1d706-156">If you use these services, you will need to integrate Exchange UM and Skype for Business Server in a shared Active Directory topology.</span></span>
    
### <a name="additional-deployment-options"></a><span data-ttu-id="1d706-157">Opções de implantação adicionais</span><span class="sxs-lookup"><span data-stu-id="1d706-157">Additional Deployment Options</span></span>

 <span data-ttu-id="1d706-158">**Opções de implantação adicionais** com as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="1d706-158">**Additional Deployment Options** contains the following options:</span></span>
  
- <span data-ttu-id="1d706-159">**Alta disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="1d706-159">**High Availability**</span></span>
    
    <span data-ttu-id="1d706-160">A alta disponibilidade permite servidores em espera para suporte contra failover.</span><span class="sxs-lookup"><span data-stu-id="1d706-160">High availability enables standby servers for failover support.</span></span>
    
- <span data-ttu-id="1d706-161">**Recuperação de desastres**</span><span class="sxs-lookup"><span data-stu-id="1d706-161">**Disaster Recovery**</span></span>
    
    <span data-ttu-id="1d706-162">As medidas de recuperação de desastres permitem emparelhar pools de front-end localizados em dois datacenters.</span><span class="sxs-lookup"><span data-stu-id="1d706-162">Disaster recovery measures enable you to pair Front End pools located in two datacenters.</span></span>
    
- <span data-ttu-id="1d706-163">**Monitoramento**</span><span class="sxs-lookup"><span data-stu-id="1d706-163">**Monitoring**</span></span>
    
    <span data-ttu-id="1d706-164">O monitoramento captura registros de detalhe de chamada relacionados a sessões de comunicação.</span><span class="sxs-lookup"><span data-stu-id="1d706-164">Monitoring captures call detail records related to communication sessions.</span></span> <span data-ttu-id="1d706-165">Também coleta métricas de sessões de áudio e vídeo nas extremidades dos participantes.</span><span class="sxs-lookup"><span data-stu-id="1d706-165">It also collects metrics from audio and video sessions at the participant endpoints.</span></span> <span data-ttu-id="1d706-166">O Monitoring Server fornece estatísticas de uso, tendências e estatísticas de qualidade de mídia.</span><span class="sxs-lookup"><span data-stu-id="1d706-166">Monitoring Server provides usage statistics, trends, and media quality statistics.</span></span>
    
- <span data-ttu-id="1d706-167">**Archiving**</span><span class="sxs-lookup"><span data-stu-id="1d706-167">**Archiving**</span></span>
    
    <span data-ttu-id="1d706-168">O arquivamento armazena conversas de mensagem instantânea e conferências.</span><span class="sxs-lookup"><span data-stu-id="1d706-168">Archiving stores instant messaging conversations and conferences.</span></span>
    
- <span data-ttu-id="1d706-169">**Integração com arquivamento do Exchange**</span><span class="sxs-lookup"><span data-stu-id="1d706-169">**Exchange Archiving Integration**</span></span>
    
    <span data-ttu-id="1d706-170">Se você tiver usuários hospedados no Exchange 2013 e suas caixas de correio tiverem sido colocadas no bloqueio in-loco, você poderá selecionar a opção para integrar o armazenamento do Skype for Business Server 2015 ao armazenamento do Exchange.</span><span class="sxs-lookup"><span data-stu-id="1d706-170">If you have users who are homed on Exchange 2013 and their mailboxes have been put on In-Place Hold, you can select the option to integrate Skype for Business Server 2015 storage with Exchange storage.</span></span>
    
- <span data-ttu-id="1d706-171">**IPv4**</span><span class="sxs-lookup"><span data-stu-id="1d706-171">**IPv4**</span></span>
    
    <span data-ttu-id="1d706-p110">Os endereços IPv4 são endereços 32 bits que permitem a um computador se comunicar pela Internet. Devido ao número cada vez maior de dispositivos no mundo todo, os endereços IPv4 disponíveis podem se esgotar. Por isso, muitos dispositivos novos estão passando a usar endereços IPv6.</span><span class="sxs-lookup"><span data-stu-id="1d706-p110">IPv4 addresses are 32-bit addresses that allow a computer to communicate over the Internet. Due to the increasing number of devices worldwide, the available IPv4 addresses have run out. Because of this, many new devices are moving to using IPv6 addresses.</span></span>
    
- <span data-ttu-id="1d706-174">**IPv6**</span><span class="sxs-lookup"><span data-stu-id="1d706-174">**IPv6**</span></span>
    
    <span data-ttu-id="1d706-p111">Os endereços IPv6 executam a mesma função que os endereços IPv4 (com alguns recursos adicionais), mas em vez de usar somente 32 bits, os endereços IPv6 usam 128 bits. Isso fornece não apenas um novo conjunto de endereços, mas também um número muito maior deles.</span><span class="sxs-lookup"><span data-stu-id="1d706-p111">IPv6 addresses perform the same function as IPv4 addresses (with some additional features), but instead of using only 32-bits, IPv6 addresses use 128-bits. This provides not only a new set of addresses, but also a much larger number of them.</span></span>
    
- <span data-ttu-id="1d706-177">**Serviço Web de Atualização de Dispositivos**</span><span class="sxs-lookup"><span data-stu-id="1d706-177">**Device Update Web service**</span></span>
    
    <span data-ttu-id="1d706-178">O serviço Web de atualização de dispositivo oferece uma maneira automatizada de atualizar todos os dispositivos, como o Skype for Business para Windows Phone, que são implantados fora de sua organização.</span><span class="sxs-lookup"><span data-stu-id="1d706-178">The Device Update Web service provides an automated way to update all devices, such as Skype for Business for Windows Phone, that are deployed outside of your organization.</span></span>
    
### <a name="server-applications"></a><span data-ttu-id="1d706-179">Aplicativos de servidor</span><span class="sxs-lookup"><span data-stu-id="1d706-179">Server Applications</span></span>

 <span data-ttu-id="1d706-180">**Aplicativos de servidor** contém as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="1d706-180">**Server Applications** contains the following options:</span></span>
  
- <span data-ttu-id="1d706-181">**Grupo de Resposta**</span><span class="sxs-lookup"><span data-stu-id="1d706-181">**Response Group**</span></span>
    
    <span data-ttu-id="1d706-182">O aplicativo de grupo de resposta automaticamente atende e distribui chamadas para um agente disponível do helpdesk.</span><span class="sxs-lookup"><span data-stu-id="1d706-182">The Response Group application automatically answers and distributes calls to an available helpdesk agent.</span></span>
    
- <span data-ttu-id="1d706-183">**Comunicado**</span><span class="sxs-lookup"><span data-stu-id="1d706-183">**Announcement**</span></span>
    
    <span data-ttu-id="1d706-184">Se você planeja implantar o Enterprise Voice, talvez queira configurar o modo como as chamadas telefônicas são manipuladas se o número discado for válido, mas não atribuído a uma área comum do usuário.</span><span class="sxs-lookup"><span data-stu-id="1d706-184">If you plan to deploy Enterprise Voice, you might want to be able to configure how phone calls are handled if the dialed number is valid but not assigned to a user common area.</span></span> <span data-ttu-id="1d706-185">Os administradores podem configurar o Serviço de Comunicado para que essas chamadas sejam transferidas para um destino predeterminado (número telefônico ou URI SIP) ou reproduzir um comunicado em áudio ou ambos.</span><span class="sxs-lookup"><span data-stu-id="1d706-185">Administrators can configure Announcement Service so that these calls transfer to a predetermined destination (phone number or SIP URI) or play an audio announcement or both.</span></span> <span data-ttu-id="1d706-186">O aplicativo de Anúncio ajuda a evitar situações em que o chamador disca para um número errado e ouve um tom de ocupado ou em que o cliente SIP recebe uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="1d706-186">Using Announcement Service avoids the situation in which a caller misdials and hears a busy tone or the SIP client receives an error message.</span></span> <span data-ttu-id="1d706-187">A funcionalidade de Serviço de Comunicado é um recurso típico de PBX.</span><span class="sxs-lookup"><span data-stu-id="1d706-187">Announcement Service functionality is a typical PBX feature.</span></span> 
    
- <span data-ttu-id="1d706-188">**Estacionamento de Chamada**</span><span class="sxs-lookup"><span data-stu-id="1d706-188">**Call Park**</span></span>
    
    <span data-ttu-id="1d706-189">O aplicativo de estacionamento de chamadas permite que um usuário de voz empresarial Coloque uma chamada em espera de um telefone e, em seguida, receba a chamada de outro telefone sem precisar ligar os recursos do telefone que recebeu a chamada.</span><span class="sxs-lookup"><span data-stu-id="1d706-189">Call Park application enables an Enterprise Voice user to put a call on hold from one telephone, and then receive the call from another telephone without tying up resources on the phone that received the call.</span></span> <span data-ttu-id="1d706-190">O aplicativo de estacionamento de chamadas é útil quando um usuário precisa transferir uma chamada, mas o destinatário específico é desconhecido.</span><span class="sxs-lookup"><span data-stu-id="1d706-190">Call Park application is useful when a user needs to transfer a call, but the specific recipient is unknown.</span></span> 
    
- <span data-ttu-id="1d706-191">**Atendedor de conferência**</span><span class="sxs-lookup"><span data-stu-id="1d706-191">**Conference Attendant**</span></span>
    
    <span data-ttu-id="1d706-192">O aplicativo atendedor de conferências fornece recursos de audioconferência para usuários telefônicos sem o serviço de um provedor de serviços de audioconferência de terceiros.</span><span class="sxs-lookup"><span data-stu-id="1d706-192">Conferencing Attendant application provides audio conferencing capabilities to phone users without the service of a third-party audio conferencing provider.</span></span>
    
- <span data-ttu-id="1d706-193">**Comunicado de conferência**</span><span class="sxs-lookup"><span data-stu-id="1d706-193">**Conferencing Announcement**</span></span>
    
    <span data-ttu-id="1d706-194">O aplicativo de anúncio de conferência produz toques que se sinalizam quando os usuários inserem ou saem de uma conferência, bem como as notificações para os usuários de telefones quando eles têm mudo ou mudo.</span><span class="sxs-lookup"><span data-stu-id="1d706-194">Conferencing Announcement application produces tones that signal when users enter or leave a conference, as well as notifications to phone users when they are muted or unmuted.</span></span>
    
- <span data-ttu-id="1d706-195">**Serviço de Controle de Admissão de Chamadas**</span><span class="sxs-lookup"><span data-stu-id="1d706-195">**Call Admission Control**</span></span>
    
    <span data-ttu-id="1d706-196">O Controle de admissão de chamada (CAC), também conhecido como gerenciador de largura de banda WAN, ajuda a evitar a experiência de baixa qualidade para usuários em redes congestionadas ao determinar, com base na largura de banda disponível, se permite que sessões de comunicação novas e em tempo real sejam estabelecidas.</span><span class="sxs-lookup"><span data-stu-id="1d706-196">Call Admission Control (CAC), also known as WAN bandwidth management, helps to prevent poor quality of experience for users on congested networks by determining, based on available bandwidth, whether to allow and new real-time communications sessions to be established.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="1d706-197">O CAC controla apenas o tráfego em tempo real e não afeta o tráfego de dados.</span><span class="sxs-lookup"><span data-stu-id="1d706-197">CAC only controls real-time traffic and does not affect data traffic.</span></span> 
  
    <span data-ttu-id="1d706-198">Se uma nova voz ou sessão de vídeo exceder os limites de largura de banda alocados em um WAN, a sessão é bloqueada ou, somente para chamadas de telefone, redirecionada ao PSTN.</span><span class="sxs-lookup"><span data-stu-id="1d706-198">If a new voice or video session exceeds the bandwidth limits that you have allocated on a WAN, the session is either blocked or (for phone calls only) rerouted to the PSTN.</span></span>
    

