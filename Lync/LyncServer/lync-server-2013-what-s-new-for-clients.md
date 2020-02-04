---
title: 'Lync Server 2013: Novidades para clientes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: What's new for clients
ms:assetid: 5c144677-4d58-4fc3-8445-74b76c9fcf07
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204933(v=OCS.15)
ms:contentKeyID: 48184253
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f938ccc4e4a040307a7cf86a8084353c480cfdca
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758481"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="whats-new-for-clients-in-lync-server-2013"></a><span data-ttu-id="78f6f-102">Novidades para clientes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78f6f-102">What's new for clients in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78f6f-103">_**Tópico da última modificação:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="78f6f-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="78f6f-104">O Microsoft Lync 2013 tem uma interface de usuário reprojetada e novos recursos importantes.</span><span class="sxs-lookup"><span data-stu-id="78f6f-104">Microsoft Lync 2013 has a redesigned user interface and important new features.</span></span> <span data-ttu-id="78f6f-105">Para administradores, o cliente agora está incluído no programa de instalação do Office, fornecendo uma abordagem mais simplificada para implantar o Office e personalizar clientes em sua organização.</span><span class="sxs-lookup"><span data-stu-id="78f6f-105">For administrators, the client is now included with the Office setup program, providing a more streamlined approach to deploying Office and customizing clients in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="78f6f-106">Para ver uma exibição ilustrada das atualizações da interface do usuário do Lync 2013, consulte "novidades do Lync <A href="http://go.microsoft.com/fwlink/?linkid=273885">http://go.microsoft.com/fwlink/?LinkId=273885</A>2013" em.</span><span class="sxs-lookup"><span data-stu-id="78f6f-106">For an illustrated view of Lync 2013 user interface updates, see “What’s New in Lync 2013” at <A href="http://go.microsoft.com/fwlink/?linkid=273885">http://go.microsoft.com/fwlink/?LinkId=273885</A>.</span></span>



</div>

<div>

## <a name="integration-with-office-setup"></a><span data-ttu-id="78f6f-107">Integração com a instalação do Office</span><span class="sxs-lookup"><span data-stu-id="78f6f-107">Integration with Office Setup</span></span>

<span data-ttu-id="78f6f-108">O cliente do Lync 2013 e o suplemento de reunião online do Lync 2013, que dá suporte ao gerenciamento de reuniões, dentro do cliente de mensagens e colaboração do Outlook, agora estão incluídos no programa de instalação do Office 2013.</span><span class="sxs-lookup"><span data-stu-id="78f6f-108">The Lync 2013 client and the Online Meeting Add-in for Lync 2013—which supports meeting management from within the Outlook messaging and collaboration client—are now both included with the Office 2013 Setup program.</span></span>

<span data-ttu-id="78f6f-109">Em versões anteriores do Lync e do Office Communicator, você pode usar as propriedades do Windows Installer para personalizar e controlar a instalação do Office.</span><span class="sxs-lookup"><span data-stu-id="78f6f-109">In previous versions of Lync and Office Communicator, you could use Windows Installer properties to customize and control the Office installation.</span></span> <span data-ttu-id="78f6f-110">Como o Lync 2013 está integrado à instalação do Office, você pode usar os seguintes métodos para personalizar a configuração do Lync 2013:</span><span class="sxs-lookup"><span data-stu-id="78f6f-110">Because Lync 2013 is integrated with Office setup, you can use the following methods to customize Lync 2013 setup:</span></span>

  - <span data-ttu-id="78f6f-111">Usar a OCT (Ferramenta de Personalização do Office)</span><span class="sxs-lookup"><span data-stu-id="78f6f-111">Use the Office Customization Tool (OCT)</span></span>

  - <span data-ttu-id="78f6f-112">Use o config. xml para executar tarefas de instalação</span><span class="sxs-lookup"><span data-stu-id="78f6f-112">Use the Config.xml to perform installation tasks</span></span>

  - <span data-ttu-id="78f6f-113">Usar opções de linha de comando de configuração</span><span class="sxs-lookup"><span data-stu-id="78f6f-113">Use Setup Command-Line Options</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="78f6f-114">O programa de instalação do Lync 2013 não desinstala versões anteriores do Lync ou do Office Communicator.</span><span class="sxs-lookup"><span data-stu-id="78f6f-114">The Lync 2013 setup program does not uninstall previous versions of Lync or Office Communicator.</span></span> <span data-ttu-id="78f6f-115">O cliente do Lync 2013 é instalado lado a lado com outros clientes do Lync ou do Office Communicator</span><span class="sxs-lookup"><span data-stu-id="78f6f-115">The Lync 2013 client installs side-by-side with other Lync or Office Communicator clients</span></span>



</div>

<span data-ttu-id="78f6f-116">Para obter detalhes, consulte [implantando clientes do Lync no Lync Server 2013](lync-server-2013-deploying-lync-clients.md).</span><span class="sxs-lookup"><span data-stu-id="78f6f-116">For details, see [Deploying Lync clients in Lync Server 2013](lync-server-2013-deploying-lync-clients.md).</span></span>

</div>

<div>

## <a name="group-policy-deployment"></a><span data-ttu-id="78f6f-117">Implantação de política de grupo</span><span class="sxs-lookup"><span data-stu-id="78f6f-117">Group Policy Deployment</span></span>

<span data-ttu-id="78f6f-118">Como o Lync 2013 agora está incluído no programa de instalação do Office, o método de implantação das configurações da política de grupo do Lync foi alterado.</span><span class="sxs-lookup"><span data-stu-id="78f6f-118">Because Lync 2013 is now included in Office setup, the method for deploying Lync Group Policy settings has changed.</span></span> <span data-ttu-id="78f6f-119">Em versões anteriores do Lync e do Office Communicator, você pode usar o Communicator. ADM para definir configurações de política de grupo, enquanto no Lync 2013 agora você pode usar os modelos administrativos do Lync e do ADML fornecidos juntamente com a política de grupo do Office Modelos administrativos.</span><span class="sxs-lookup"><span data-stu-id="78f6f-119">In previous versions of Lync and Office Communicator, you could use the Communicator.adm to define Group Policy settings, whereas in Lync 2013 you can now use the Lync ADMX and ADML administrative templates that are provided along with the Office Group Policy Administrative Templates.</span></span>

<span data-ttu-id="78f6f-120">Para obter detalhes, consulte [configurações de política de grupo para o Lync 2013](lync-server-2013-group-policy-settings-for-lync-2013.md).</span><span class="sxs-lookup"><span data-stu-id="78f6f-120">For details, see [Group Policy settings for Lync 2013](lync-server-2013-group-policy-settings-for-lync-2013.md).</span></span>

</div>

<div>

## <a name="outlook-scheduling-add-in-updates"></a><span data-ttu-id="78f6f-121">Atualizações do suplemento agendamento do Outlook</span><span class="sxs-lookup"><span data-stu-id="78f6f-121">Outlook Scheduling Add-in Updates</span></span>

<span data-ttu-id="78f6f-122">O suplemento reunião online do Lync 2013 inclui a personalização de convites de reunião e as novas opções de reunião.</span><span class="sxs-lookup"><span data-stu-id="78f6f-122">The Online Meeting Add-in for Lync 2013 includes meeting invite customization and new meeting options.</span></span>

  - <span data-ttu-id="78f6f-123">Os administradores podem personalizar os convites para reunião da organização adicionando um logotipo personalizado, uma URL de suporte, uma URL de isenção de responsabilidade legal ou texto de rodapé personalizado.</span><span class="sxs-lookup"><span data-stu-id="78f6f-123">Administrators can customize the organization’s meeting invitations by adding a custom logo, a support URL, a legal disclaimer URL, or custom footer text.</span></span> <span data-ttu-id="78f6f-124">Para obter detalhes, consulte [Personalizando o suplemento de reunião online no Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="78f6f-124">For details, see [Customizing the Online Meeting Add-in in Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md).</span></span>

  - <span data-ttu-id="78f6f-125">Novos controles de mudo para participantes permitir que os organizadores da reunião agendem conferências que tenham áudio e vídeo de participantes com mudo ativado por padrão.</span><span class="sxs-lookup"><span data-stu-id="78f6f-125">New attendee mute controls allow meeting organizers to schedule conferences that have attendee audio and video muted by default.</span></span>

</div>

<div>

## <a name="virtual-desktop-infrastructure-plug-in"></a><span data-ttu-id="78f6f-126">Plug-in de infraestrutura de área de trabalho virtual</span><span class="sxs-lookup"><span data-stu-id="78f6f-126">Virtual Desktop Infrastructure Plug-in</span></span>

<span data-ttu-id="78f6f-127">O cliente Lync 2013 agora dá suporte a áudio e vídeo em um ambiente VDI (infraestrutura de área de trabalho virtual).</span><span class="sxs-lookup"><span data-stu-id="78f6f-127">The Lync 2013 client now supports audio and video in a Virtual Desktop Infrastructure (VDI) environment.</span></span> <span data-ttu-id="78f6f-128">Um usuário pode conectar um dispositivo de áudio ou de vídeo (por exemplo, um fone de ouvido com microfone ou uma câmera) ao computador local (por exemplo, um cliente leve ou um computador redefinido).</span><span class="sxs-lookup"><span data-stu-id="78f6f-128">A user can connect an audio or video device (for example, a headset or a camera) to the local computer (for example, a thin client or repurposed computer).</span></span> <span data-ttu-id="78f6f-129">O usuário pode se conectar à máquina virtual, entrar no cliente do Lync 2013 que está em execução na máquina virtual e participar de comunicações de áudio e vídeo em tempo real, como se o cliente estivesse em execução localmente.</span><span class="sxs-lookup"><span data-stu-id="78f6f-129">The user can connect to the virtual machine, sign in to the Lync 2013 client that is running on the virtual machine, and participate in real-time audio and video communication as though the client is running locally.</span></span> <span data-ttu-id="78f6f-130">Os recursos a seguir são suportados em um ambiente de área de trabalho virtual:</span><span class="sxs-lookup"><span data-stu-id="78f6f-130">The following features are supported in a virtual desktop environment:</span></span>

  - <span data-ttu-id="78f6f-131">Integração de dispositivos para áudio e vídeo, incluindo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="78f6f-131">Device integration for audio and video, including the following:</span></span>
    
      - <span data-ttu-id="78f6f-132">Controles de chamada do dispositivo</span><span class="sxs-lookup"><span data-stu-id="78f6f-132">Call controls from the device</span></span>
    
      - <span data-ttu-id="78f6f-133">Integração de presença no dispositivo</span><span class="sxs-lookup"><span data-stu-id="78f6f-133">Presence integration on the device</span></span>
    
      - <span data-ttu-id="78f6f-134">Suporte a vários HID (dispositivo de interface humana)</span><span class="sxs-lookup"><span data-stu-id="78f6f-134">Multiple HID (human interface device) support</span></span>

  - <span data-ttu-id="78f6f-135">Suporte a locais e serviços de emergência.</span><span class="sxs-lookup"><span data-stu-id="78f6f-135">Location and emergency services support.</span></span>

  - <span data-ttu-id="78f6f-136">Suporte para todas as modalidades do Lync, incluindo mensagens instantâneas, áudio, vídeo, compartilhamento de aplicativos, compartilhamento de área de trabalho, compartilhamento do PowerPoint, quadro de comunicações e transferência de arquivos.</span><span class="sxs-lookup"><span data-stu-id="78f6f-136">Support for all Lync modalities, including IM, audio, video, application sharing, desktop sharing, PowerPoint sharing, whiteboard, and file transfer.</span></span>

  - <span data-ttu-id="78f6f-137">Suporte a áudio e vídeo em chamadas de pessoa para pessoa e chamadas em conferência.</span><span class="sxs-lookup"><span data-stu-id="78f6f-137">Audio and video support in person-to-person calls and conference calls.</span></span>

<span data-ttu-id="78f6f-138">Para obter informações sobre a implantação do plug-in VDI, consulte [implantação do plug-in VDI do Lync no Lync Server 2013](lync-server-2013-deploying-the-lync-vdi-plug-in.md).</span><span class="sxs-lookup"><span data-stu-id="78f6f-138">For information about deploying the VDI plug-in, see [Deploying the Lync VDI plug-in in Lync Server 2013](lync-server-2013-deploying-the-lync-vdi-plug-in.md).</span></span>

</div>

<div>

## <a name="video-enhancements"></a><span data-ttu-id="78f6f-139">Melhorias de vídeo</span><span class="sxs-lookup"><span data-stu-id="78f6f-139">Video Enhancements</span></span>

<span data-ttu-id="78f6f-140">Vários novos recursos melhoram significativamente a experiência com vídeo para participantes de conferências.</span><span class="sxs-lookup"><span data-stu-id="78f6f-140">Several new features significantly enhance the video experience for conference participants.</span></span>

  - <span data-ttu-id="78f6f-141">Vídeo aprimorado com detecção de rosto e enquadramento inteligente, para que o vídeo de um participante se movimente para ajudar a mantê-los centralizados no quadro.</span><span class="sxs-lookup"><span data-stu-id="78f6f-141">Video is enhanced with face detection and smart framing, so that a participant’s video moves to help keep them centered in the frame.</span></span>

  - <span data-ttu-id="78f6f-142">O vídeo de alta definição agora é compatível com chamadas de dois participantes e conferências de vários participantes.</span><span class="sxs-lookup"><span data-stu-id="78f6f-142">High-definition video is now supported in two-party calls and multiparty conferences.</span></span> <span data-ttu-id="78f6f-143">Os usuários podem experimentar resoluções de até HD 1080P.</span><span class="sxs-lookup"><span data-stu-id="78f6f-143">Users can experience resolutions up to HD 1080P.</span></span>

  - <span data-ttu-id="78f6f-144">Os participantes podem selecionar um layout de reunião diferente: o modo de exibição de galeria mostra as imagens ou vídeos dos participantes; O modo de exibição do orador mostra o conteúdo da reunião e somente o vídeo ou a imagem atual do orador; Modo de exibição de apresentação mostra o conteúdo da reunião somente; O modo de exibição compacto mostra apenas os controles da reunião.</span><span class="sxs-lookup"><span data-stu-id="78f6f-144">Participants can select from different meeting layouts: Gallery View shows all participants’ pictures or videos; Speaker View shows the meeting content and only the current speaker’s video or picture; Presentation View shows meeting content only; Compact View shows just the meeting controls.</span></span>

  - <span data-ttu-id="78f6f-145">Com o novo recurso de galeria, os participantes podem ver várias alimentações de vídeo ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="78f6f-145">With the new Gallery feature, participants can see multiple video feeds at the same time.</span></span> <span data-ttu-id="78f6f-146">Se a conferência tiver mais de cinco participantes, as alimentações de vídeo apenas dos participantes ativos serão exibidos na linha superior e as imagens serão exibidas para os outros participantes.</span><span class="sxs-lookup"><span data-stu-id="78f6f-146">If the conference has more than five participants, video feeds of only the most active participants appear in the top row, and pictures appear for the other participants.</span></span>

  - <span data-ttu-id="78f6f-147">Os participantes podem usar a fixação de vídeo para selecionar um ou mais dos feeds de vídeo disponíveis para ficarem visíveis o tempo todo.</span><span class="sxs-lookup"><span data-stu-id="78f6f-147">Participants can use video pinning to select one or more of the available video feeds to be visible at all times.</span></span>

  - <span data-ttu-id="78f6f-148">Os apresentadores podem usar o recurso de Spotlight em vídeo para selecionar o feed de vídeo de uma pessoa para que todos os participantes da reunião vejam apenas esse participante.</span><span class="sxs-lookup"><span data-stu-id="78f6f-148">Presenters can use the Video Spotlight feature to select one person’s video feed so that every participant in the meeting sees that participant only.</span></span>

</div>

<div>

## <a name="chat-room-integration"></a><span data-ttu-id="78f6f-149">Integração da sala de chat</span><span class="sxs-lookup"><span data-stu-id="78f6f-149">Chat Room Integration</span></span>

<span data-ttu-id="78f6f-150">O Lync 2013 agora integra os recursos fornecidos anteriormente pelo Lync 2010 Group Chat.</span><span class="sxs-lookup"><span data-stu-id="78f6f-150">Lync 2013 now integrates the features previously provided by Lync 2010 Group Chat.</span></span> <span data-ttu-id="78f6f-151">Um cliente de chat em grupo separado não é mais necessário.</span><span class="sxs-lookup"><span data-stu-id="78f6f-151">A separate group chat client is no longer required.</span></span>

  - <span data-ttu-id="78f6f-152">De dentro do Lync 2013, os usuários podem procurar salas de chat, adicionar salas de chat a seus contatos, monitorar a atividade de salas de chat e ler e postar mensagens.</span><span class="sxs-lookup"><span data-stu-id="78f6f-152">From within Lync 2013, users can search for chat rooms, add chat rooms to their contacts, monitor chat room activity, and read and post messages.</span></span>

  - <span data-ttu-id="78f6f-153">Os usuários podem criar feeds de tópico para que sejam notificados se alguém em uma das salas de chat adicionar uma postagem contendo palavras-chave específicas.</span><span class="sxs-lookup"><span data-stu-id="78f6f-153">Users can create topic feeds so that they’ll be notified if someone in one of their chat rooms adds a post containing specific keywords.</span></span>

  - <span data-ttu-id="78f6f-154">Com a nova página de opções de **chat persistente** , os usuários podem definir alertas de notificação e sons que se aplicam quando as pessoas publicam mensagens em suas salas de chat.</span><span class="sxs-lookup"><span data-stu-id="78f6f-154">With the new **Persistent Chat** options page, users can set notification alerts and sounds that apply when people post messages to their chat rooms.</span></span>

</div>

<div>

## <a name="lync-web-app-updates"></a><span data-ttu-id="78f6f-155">Atualizações do Lync Web App</span><span class="sxs-lookup"><span data-stu-id="78f6f-155">Lync Web App Updates</span></span>

<span data-ttu-id="78f6f-156">O Lync Web App é o cliente de conferência baseado na Web para reuniões do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="78f6f-156">Lync Web App is the web-based conferencing client for Lync Server 2013 meetings.</span></span> <span data-ttu-id="78f6f-157">Nesta versão, a adição de áudio e vídeo do computador ao Lync Web App oferece uma experiência completa na reunião para qualquer pessoa que não tenha um cliente do Lync instalado localmente.</span><span class="sxs-lookup"><span data-stu-id="78f6f-157">In this release, the addition of computer audio and video to Lync Web App provides a complete in-meeting experience for anyone who doesn’t have a Lync client installed locally.</span></span> <span data-ttu-id="78f6f-158">Os participantes de reunião têm acesso a todos os recursos de colaboração e compartilhamento e aos controles de reunião do apresentador.</span><span class="sxs-lookup"><span data-stu-id="78f6f-158">Meeting participants have access to all collaboration and sharing features and presenter meeting controls.</span></span>

<span data-ttu-id="78f6f-159">Quando um usuário tenta ingressar em uma reunião, mas não tem um cliente instalado localmente, o Lync Web App é aberto.</span><span class="sxs-lookup"><span data-stu-id="78f6f-159">When a user tries to join a meeting but doesn’t have a locally installed client, Lync Web App opens.</span></span> <span data-ttu-id="78f6f-160">Se quiser permitir opções adicionais para ingressar na reunião, você pode configurar a página ingressar na reunião; consulte [Configurando a página ingressar na reunião no Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="78f6f-160">If you want to allow additional options for joining the meeting, you can configure the Meeting Join page; see [Configuring the meeting join page in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md) in the Deployment documentation.</span></span>

<span data-ttu-id="78f6f-161">Devido aos aprimoramentos do Lync Web App, uma versão atualizada do participante não está disponível para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="78f6f-161">Because of the enhancements to Lync Web App, an updated version of Attendee isn’t available for Lync Server 2013.</span></span> <span data-ttu-id="78f6f-162">O Lync Web App é o cliente escolhido para participantes de fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="78f6f-162">Lync Web App is the client of choice for participants outside your organization.</span></span> <span data-ttu-id="78f6f-163">Não é necessária nenhuma instalação de cliente local, embora os recursos de áudio, vídeo e compartilhamento exijam que um plug-in seja instalado na primeira utilização.</span><span class="sxs-lookup"><span data-stu-id="78f6f-163">No local client installation is required, although audio, video, and sharing features require a plug-in to be installed at first use.</span></span>

</div>

<div>

## <a name="lync-2013-for-mobile-clients-updates"></a><span data-ttu-id="78f6f-164">Lync 2013 para atualizações de clientes móveis</span><span class="sxs-lookup"><span data-stu-id="78f6f-164">Lync 2013 for Mobile Clients Updates</span></span>

<span data-ttu-id="78f6f-165">Além de recursos avançados de presença, contatos e mensagens instantâneas, agora os clientes móveis do Lync 2013 fornecem chamadas de voz e vídeo pela Internet e conexões de dados da rede celular.</span><span class="sxs-lookup"><span data-stu-id="78f6f-165">In addition to enhanced presence, contacts, and IM capabilities, Lync 2013 mobile clients now provide voice and video calling over the Internet and cellular data connections.</span></span> <span data-ttu-id="78f6f-166">Com um único toque do link da reunião em um item de calendário, os usuários móveis podem ingressar em reuniões com voz e vídeo do Lync.</span><span class="sxs-lookup"><span data-stu-id="78f6f-166">With a single tap of the meeting link in a calendar item, mobile users can join Lync voice and video meetings.</span></span> <span data-ttu-id="78f6f-167">Para obter mais informações sobre clientes móveis do Lync 2013, consulte [planejando para clientes móveis no Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span><span class="sxs-lookup"><span data-stu-id="78f6f-167">For more information about Lync 2013 mobile clients, see [Planning for mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span></span>

</div>

<div>

## <a name="lync-2013-user-interface-updates"></a><span data-ttu-id="78f6f-168">Atualizações da interface do usuário do Lync 2013</span><span class="sxs-lookup"><span data-stu-id="78f6f-168">Lync 2013 User Interface Updates</span></span>

<div>

## <a name="accessibility-updates"></a><span data-ttu-id="78f6f-169">Atualizações de acessibilidade</span><span class="sxs-lookup"><span data-stu-id="78f6f-169">Accessibility Updates</span></span>

<span data-ttu-id="78f6f-170">O Lync 2013 incorpora vários novos recursos de acessibilidade.</span><span class="sxs-lookup"><span data-stu-id="78f6f-170">Lync 2013 incorporates several new accessibility features.</span></span>

  - <span data-ttu-id="78f6f-171">O Lync 2013 suporta resolução de alta DPI, permitindo que os usuários dimensionem o texto e os elementos gráficos para 125% e 150% de pontos por polegada.</span><span class="sxs-lookup"><span data-stu-id="78f6f-171">Lync 2013 supports high DPI resolution, enabling users to scale text and graphics for 125% and 150% dots per inch.</span></span>

  - <span data-ttu-id="78f6f-172">O Lync fornece suporte de alto contraste para que a interface do usuário permaneça totalmente funcional quando usada com temas de alto contraste no Windows.</span><span class="sxs-lookup"><span data-stu-id="78f6f-172">Lync provides high-contrast support so that the user interface remains fully functional when used with high contrast themes in Windows.</span></span>

  - <span data-ttu-id="78f6f-173">O Lync oferece mais de 100 atalhos de teclado para que os usuários possam acessar funções importantes sem um mouse.</span><span class="sxs-lookup"><span data-stu-id="78f6f-173">Lync offers more than 100 keyboard shortcuts so that users can access important functions without a mouse.</span></span> <span data-ttu-id="78f6f-174">Por exemplo, os usuários podem pressionar Alt + C para aceitar uma chamada ou ALT + I para ignorá-la, sem precisar fazer a Tabulação ou definir o foco.</span><span class="sxs-lookup"><span data-stu-id="78f6f-174">For example, users can press Alt+C to accept a call, or Alt + I to ignore it, without having to tab or set the focus.</span></span> <span data-ttu-id="78f6f-175">Pressionar (ALT + Q) Finaliza uma chamada, (Ctrl + N) inicia o OneNote e (Alt + T) abre o menu ferramentas.</span><span class="sxs-lookup"><span data-stu-id="78f6f-175">Pressing (Alt+Q) ends a call, (Ctrl+N) starts OneNote, and (Alt+T) opens the Tools menu.</span></span>

  - <span data-ttu-id="78f6f-176">O suporte a leitor de tela extensivo no Lync 2013 garante que todas as notificações, solicitações de entrada e mensagens instantâneas sejam lidas em voz alta quando um leitor de tela estiver habilitado.</span><span class="sxs-lookup"><span data-stu-id="78f6f-176">Extensive screen reader support in Lync 2013 ensures that all notifications, incoming requests, and instant messages are read aloud when a screen reader is enabled.</span></span>

</div>

<div>

## <a name="presence-while-sharing"></a><span data-ttu-id="78f6f-177">Presença durante o compartilhamento</span><span class="sxs-lookup"><span data-stu-id="78f6f-177">Presence While Sharing</span></span>

<span data-ttu-id="78f6f-178">Quando o Lync detecta que um usuário está compartilhando, o Lync atribui automaticamente ao usuário um status de presença apresentando.</span><span class="sxs-lookup"><span data-stu-id="78f6f-178">When Lync detects that a user is sharing, Lync automatically assigns the user a Presenting presence status.</span></span> <span data-ttu-id="78f6f-179">Esse status bloqueia todas as comunicações de entrada, a menos que o remetente tenha atribuído a relação de privacidade do grupo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="78f6f-179">This status blocks all incoming communications unless the sender is assigned the Workgroup privacy relationship.</span></span> <span data-ttu-id="78f6f-180">Se o usuário estiver usando o recurso de compartilhamento totalmente em um monitor secundário, o Lync não atribuirá um status de presença de apresentação.</span><span class="sxs-lookup"><span data-stu-id="78f6f-180">If the user is using the sharing feature entirely on a secondary monitor, Lync does not assign a Presenting presence status.</span></span>

</div>

<div>

## <a name="conversation-window-updates"></a><span data-ttu-id="78f6f-181">Atualizações da janela de conversa</span><span class="sxs-lookup"><span data-stu-id="78f6f-181">Conversation Window Updates</span></span>

<span data-ttu-id="78f6f-182">A janela de conversa reformulada fornece acesso mais rápido a recursos importantes.</span><span class="sxs-lookup"><span data-stu-id="78f6f-182">The redesigned Conversation window provides quicker access to important features.</span></span>

  - <span data-ttu-id="78f6f-183">Com o novo recurso conversas com guias, os usuários agora podem manter todas as salas de chat e chats em uma janela de conversa.</span><span class="sxs-lookup"><span data-stu-id="78f6f-183">With the new tabbed conversations feature, users can now keep all their IMs and chat rooms in one Conversation window.</span></span> <span data-ttu-id="78f6f-184">As guias no lado esquerdo da janela de conversa permitem que os usuários naveguem facilmente entre todas as conversas ativas.</span><span class="sxs-lookup"><span data-stu-id="78f6f-184">The tabs along the left side of the Conversation window let users navigate easily among all active conversations.</span></span>

  - <span data-ttu-id="78f6f-185">Os usuários podem mostrar uma conversa individual em uma janela separada e, em seguida, redimensionar a janela.</span><span class="sxs-lookup"><span data-stu-id="78f6f-185">Users can pop out an individual conversation into a separate window, and then resize the window.</span></span> <span data-ttu-id="78f6f-186">Eles também podem retornar a janela de volta à janela de conversa principal.</span><span class="sxs-lookup"><span data-stu-id="78f6f-186">They can also pop the window back into the main Conversation window.</span></span>

  - <span data-ttu-id="78f6f-187">O Lync 2013 reabre as conversas de um usuário quando o usuário se desconecta e entra novamente no Lync.</span><span class="sxs-lookup"><span data-stu-id="78f6f-187">Lync 2013 reopens a user’s conversations when the user signs out and signs back in to Lync.</span></span>

  - <span data-ttu-id="78f6f-188">Os usuários podem adicionar rapidamente mensagens instantâneas, vídeo, compartilhamento de programas, compartilhamento de área de trabalho ou ferramentas de Webconferência (quadro de comunicações, anotações da reunião, blocos de anotações compartilhados e anexos) a qualquer conversa.</span><span class="sxs-lookup"><span data-stu-id="78f6f-188">Users can quickly add IM, video, program sharing, desktop sharing, or web conferencing tools (whiteboard, meeting notes, shared notebooks, and attachments) to any conversation.</span></span>

  - <span data-ttu-id="78f6f-189">Em uma reunião na qual um vídeo ou conteúdo está sendo compartilhado, os usuários podem exibir o vídeo da reunião ou o conteúdo compartilhado e, em seguida, redimensionar a janela.</span><span class="sxs-lookup"><span data-stu-id="78f6f-189">In a meeting where video or content is being shared, users can pop out the meeting video or shared content, and then resize the window.</span></span>

</div>

<div>

## <a name="lync-main-window-updates"></a><span data-ttu-id="78f6f-190">Atualizações da janela principal do Lync</span><span class="sxs-lookup"><span data-stu-id="78f6f-190">Lync Main Window Updates</span></span>

<span data-ttu-id="78f6f-191">A nova aparência simplificada retém recursos conhecidos, como o **que está acontecendo hoje?** , o seletor de status e o seletor de **local definir seu local** .</span><span class="sxs-lookup"><span data-stu-id="78f6f-191">The new streamlined look retains familiar features such as the **What’s happening today?** note field, the status selector, and the **Set Your Location** selector.</span></span>

  - <span data-ttu-id="78f6f-192">Quando salas de chat estiverem habilitadas, os usuários verão um novo ícone de **salas de chat** na página principal do Lync.</span><span class="sxs-lookup"><span data-stu-id="78f6f-192">When chat rooms are enabled, users see a new **Chat Rooms** icon on the main Lync page.</span></span> <span data-ttu-id="78f6f-193">Com o ícone de **salas de chat** , os usuários podem acessar rapidamente seus respectivos filtros e salas de chat.</span><span class="sxs-lookup"><span data-stu-id="78f6f-193">With the **Chat Rooms** icon, users can quickly access their chat rooms and filters.</span></span>

  - <span data-ttu-id="78f6f-194">Os usuários podem clicar nos ícones de exibição para alternar para o modo de exibição **contatos** , o modo de exibição **salas de chat** , o modo de exibição **conversas** ou o modo de exibição **telefone**</span><span class="sxs-lookup"><span data-stu-id="78f6f-194">Users can click the view icons to switch to the **Contacts** view, **Chat Rooms** view, **Conversations** view, or **Phone** view.</span></span>

  - <span data-ttu-id="78f6f-195">Se os usuários foram migrados para o Exchange 2013, eles podem carregar uma imagem de alta resolução.</span><span class="sxs-lookup"><span data-stu-id="78f6f-195">If users have been migrated to Exchange 2013, they can upload a high resolution picture.</span></span>

</div>

<div>

## <a name="contacts-view-and-contact-card-updates"></a><span data-ttu-id="78f6f-196">Modo de exibição contatos e atualizações de cartão de contato</span><span class="sxs-lookup"><span data-stu-id="78f6f-196">Contacts View and Contact Card Updates</span></span>

<span data-ttu-id="78f6f-197">O Lync 2013 oferece aos usuários diferentes maneiras de exibir contatos e grupos no modo de exibição **contatos** .</span><span class="sxs-lookup"><span data-stu-id="78f6f-197">Lync 2013 gives users different ways to view contacts and groups in their **Contacts** view.</span></span>

  - <span data-ttu-id="78f6f-198">Com o novo repositório de contatos unificado, após a migração dos contatos do Lync dos usuários para o Exchange 2013, os usuários podem acessar e gerenciar seus contatos no Lync 2013, no Outlook ou no Outlook Web App, e seus favoritos ficam sincronizados.</span><span class="sxs-lookup"><span data-stu-id="78f6f-198">With the new unified contact store, after users' Lync contacts are migrated to Exchange 2013, the users can access and manage their contacts from Lync 2013, Outlook, or Outlook Web App, and their Favorites stay synchronized.</span></span> <span data-ttu-id="78f6f-199">Por exemplo, se um usuário adicionar um contato aos favoritos no Outlook, o contato aparecerá no grupo favoritos no Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="78f6f-199">For example, if a user adds a contact to Favorites in Outlook, the contact appears in the Favorites group in Lync 2013.</span></span>

  - <span data-ttu-id="78f6f-200">Se você adicionou e configurou o proxy XMPP e o Gateway XMPP, os usuários podem adicionar contatos de parceiros baseados no XMPP para mensagens instantâneas e presença.</span><span class="sxs-lookup"><span data-stu-id="78f6f-200">If you have added and configured the XMPP proxy and XMPP gateway, users can add contacts from XMPP-based partners for instant messaging and presence.</span></span>

  - <span data-ttu-id="78f6f-201">Um novo recurso **Adicionar um contato que não está em minha organização** proporciona aos usuários uma maneira fácil de adicionar pessoas de fora da organização.</span><span class="sxs-lookup"><span data-stu-id="78f6f-201">A new **Add a Contact That’s Not in My Organization** feature gives users an easy way to add people who are external to the organization.</span></span>

  - <span data-ttu-id="78f6f-202">Um novo grupo **favoritos** permite que os usuários criem uma lista de pessoas que os usuários contatam com mais frequência para obter um acesso mais rápido.</span><span class="sxs-lookup"><span data-stu-id="78f6f-202">A new **Favorites** group lets users build a list of people users contact most often for quicker access.</span></span>

  - <span data-ttu-id="78f6f-203">Os usuários podem usar a nova página Opções da **lista de contatos** para escolher como os usuários desejam classificar e exibir contatos.</span><span class="sxs-lookup"><span data-stu-id="78f6f-203">Users can use the new **Contacts List** options page to choose how users want to sort and display contacts.</span></span> <span data-ttu-id="78f6f-204">Os usuários podem selecionar uma exibição expandida de duas linhas que mostre as imagens dos contatos ou uma exibição condensada de uma linha.</span><span class="sxs-lookup"><span data-stu-id="78f6f-204">Users can select an expanded, two-line view that shows contacts’ pictures, or a condensed one-line view.</span></span> <span data-ttu-id="78f6f-205">Os usuários também podem classificar os contatos em ordem alfabética ou por disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="78f6f-205">Users can also sort contacts alphabetically or by availability.</span></span>

</div>

<div>

## <a name="conferencing-updates"></a><span data-ttu-id="78f6f-206">Atualizações de conferência</span><span class="sxs-lookup"><span data-stu-id="78f6f-206">Conferencing Updates</span></span>

<span data-ttu-id="78f6f-207">O Lync 2013 oferece vários aprimoramentos em recursos de conferência.</span><span class="sxs-lookup"><span data-stu-id="78f6f-207">Lync 2013 offers several enhancements to conferencing features.</span></span>

  - <span data-ttu-id="78f6f-208">Dependendo do tipo de reunião, os usuários podem agora ativar o mudo da audiência e permitir ou bloquear o compartilhamento de vídeo ao agendar a reunião.</span><span class="sxs-lookup"><span data-stu-id="78f6f-208">Depending on the type of meeting, users can now mute the audience and allow or block video sharing when scheduling the meeting.</span></span> <span data-ttu-id="78f6f-209">Essas opções estão disponíveis na página **Opções de reunião** e são recomendadas para reuniões grandes com mais de 20 participantes.</span><span class="sxs-lookup"><span data-stu-id="78f6f-209">These options are available on the **Meeting Options** page and are recommended for large meetings with more than 20 participants.</span></span>

  - <span data-ttu-id="78f6f-210">Os controles de áudio fáceis de usar na sala de reuniões permitem que o usuário controle opções de áudio, como ativar mudo, desativar mudo, alterar dispositivo e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="78f6f-210">Easy to use audio controls in the meeting room allow the user to control audio options, such as mute, unmute, change device, and so on.</span></span>

  - <span data-ttu-id="78f6f-211">Ao compartilhar programas, os usuários podem selecionar vários programas para compartilhar se precisarem trabalhar com mais de um programa.</span><span class="sxs-lookup"><span data-stu-id="78f6f-211">When sharing programs, users can select multiple programs to share if they need to work with more than one program.</span></span>

  - <span data-ttu-id="78f6f-212">Agora os usuários podem carregar apresentações que contenham clipes de vídeo carregando o arquivo do PowerPoint e apontando o mouse sobre o slide para exibir controles de vídeo, como controles de reprodução, pausa e áudio.</span><span class="sxs-lookup"><span data-stu-id="78f6f-212">Users can now upload presentations that contain video clips by uploading the PowerPoint file, and pointing the mouse over the slide to display video controls, such as play, pause, and audio controls.</span></span>

  - <span data-ttu-id="78f6f-213">Durante uma reunião, os usuários podem mesclar outra conversa aberta na reunião usando **mesclar esta chamada** no menu **mais opções** (**...**).</span><span class="sxs-lookup"><span data-stu-id="78f6f-213">While in a meeting, users can merge another open conversation into the meeting by using **Merge This Call Into** on the **More Options** (**…**) menu.</span></span>

  - <span data-ttu-id="78f6f-214">Para ver os nomes dos participantes, os usuários podem focalizar o mouse sobre o botão **Exibir participantes** ou clicar em **Mostrar lista de participantes** para encaixar o painel na reunião.</span><span class="sxs-lookup"><span data-stu-id="78f6f-214">To see the participants’ names, users can hover the mouse over the **View Participants** button, or click **Show Participant List** to dock the panel in the meeting.</span></span>

  - <span data-ttu-id="78f6f-215">Dependendo do tipo de reunião, os usuários podem selecionar entre vários modos de exibição de conteúdo e de participantes diferentes.</span><span class="sxs-lookup"><span data-stu-id="78f6f-215">Depending on the meeting type, users can select from several different content and participant views.</span></span>

  - <span data-ttu-id="78f6f-216">As gravações de reunião são salvas automaticamente em um formato que é reproduzido no Windows Media Player (MP4).</span><span class="sxs-lookup"><span data-stu-id="78f6f-216">Meeting recordings are automatically saved in a format that plays in Windows Media Player (MP4).</span></span> <span data-ttu-id="78f6f-217">Os usuários podem compartilhar facilmente o arquivo com qualquer pessoa ou usar o recurso **publicar** no Gerenciador de gravação para postar a gravação em um local compartilhado.</span><span class="sxs-lookup"><span data-stu-id="78f6f-217">Users can easily share the file with anyone, or use the **Publish** feature in recording manager to post the recording on a shared location.</span></span>

  - <span data-ttu-id="78f6f-218">O OneNote permite novas maneiras de colaborar em uma reunião.</span><span class="sxs-lookup"><span data-stu-id="78f6f-218">OneNote enables new ways to collaborate in a meeting.</span></span> <span data-ttu-id="78f6f-219">Durante uma reunião, os usuários podem fazer anotações com o OneNote para uso pessoal após a reunião ou usar blocos de anotações compartilhados e coedição com participantes da reunião em tempo real.</span><span class="sxs-lookup"><span data-stu-id="78f6f-219">During a meeting, users can take notes with OneNote for personal use after the meeting, or use shared notebooks and co-edit with meeting participants in real time.</span></span> <span data-ttu-id="78f6f-220">Todos os membros da equipe podem acessar as anotações compartilhadas em informações do Contribute, ideias ou usar as páginas do bloco de anotações como um quadro de comunicações virtual.</span><span class="sxs-lookup"><span data-stu-id="78f6f-220">All team members can access the shared notes to contribute information, brainstorm ideas, or use the notebook pages as a virtual whiteboard.</span></span> <span data-ttu-id="78f6f-221">As pessoas e o conteúdo compartilhado na reunião são adicionados automaticamente às anotações.</span><span class="sxs-lookup"><span data-stu-id="78f6f-221">People and content shared in the meeting are automatically added to the Notes.</span></span>

  - <span data-ttu-id="78f6f-222">Os usuários podem alternar entre tipos de conteúdo usando o **recurso compartilhar conteúdo e conduzir atividades da reunião** na parte inferior da sala de reunião.</span><span class="sxs-lookup"><span data-stu-id="78f6f-222">Users can switch between content types using **Share content and lead meeting activities** at the bottom of the meeting room.</span></span> <span data-ttu-id="78f6f-223">Os usuários também podem usar o menu **gerenciar conteúdo apresentável** para escolher o conteúdo que deseja compartilhar.</span><span class="sxs-lookup"><span data-stu-id="78f6f-223">Users can also use the **Manage Presentable Content** menu to choose which content they want to share.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="78f6f-224">Confira também</span><span class="sxs-lookup"><span data-stu-id="78f6f-224">See Also</span></span>


[<span data-ttu-id="78f6f-225">Planejamento de clientes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78f6f-225">Planning for clients in Lync Server 2013</span></span>](lync-server-2013-planning-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

