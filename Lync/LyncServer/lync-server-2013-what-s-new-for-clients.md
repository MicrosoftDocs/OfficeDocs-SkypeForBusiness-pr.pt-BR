---
title: 'Lync Server 2013: o que há de novo para clientes'
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
ms.openlocfilehash: 9035ace6a3cfbb65c8effb786bcd6a7568f92252
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149100"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="whats-new-for-clients-in-lync-server-2013"></a><span data-ttu-id="8a204-102">O que há de novo para clientes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a204-102">What's new for clients in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a204-103">_**Última modificação do tópico:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="8a204-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="8a204-104">O Microsoft Lync 2013 tem uma interface do usuário reprojetada e novos recursos importantes.</span><span class="sxs-lookup"><span data-stu-id="8a204-104">Microsoft Lync 2013 has a redesigned user interface and important new features.</span></span> <span data-ttu-id="8a204-105">Para os administradores, o cliente agora está incluído no programa de instalação do Office, fornecendo uma abordagem mais simplificada para a implantação do Office e personalização de clientes em sua organização.</span><span class="sxs-lookup"><span data-stu-id="8a204-105">For administrators, the client is now included with the Office setup program, providing a more streamlined approach to deploying Office and customizing clients in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8a204-106">Para obter uma visão ilustrada das atualizações da interface de usuário do Lync 2013, consulte "What ' s <A href="https://go.microsoft.com/fwlink/?linkid=273885">https://go.microsoft.com/fwlink/?LinkId=273885</A>New in Lync 2013" em.</span><span class="sxs-lookup"><span data-stu-id="8a204-106">For an illustrated view of Lync 2013 user interface updates, see “What’s New in Lync 2013” at <A href="https://go.microsoft.com/fwlink/?linkid=273885">https://go.microsoft.com/fwlink/?LinkId=273885</A>.</span></span>



</div>

<div>

## <a name="integration-with-office-setup"></a><span data-ttu-id="8a204-107">Integração com a instalação do Office</span><span class="sxs-lookup"><span data-stu-id="8a204-107">Integration with Office Setup</span></span>

<span data-ttu-id="8a204-108">O cliente Lync 2013 e o suplemento online Meeting para Lync 2013, que oferece suporte ao gerenciamento de reuniões a partir do cliente de mensagens e colaboração do Outlook, estão agora incluídos no programa de instalação do Office 2013.</span><span class="sxs-lookup"><span data-stu-id="8a204-108">The Lync 2013 client and the Online Meeting Add-in for Lync 2013—which supports meeting management from within the Outlook messaging and collaboration client—are now both included with the Office 2013 Setup program.</span></span>

<span data-ttu-id="8a204-109">Nas versões anteriores do Lync e do Office Communicator, você pode usar as propriedades do Windows Installer para personalizar e controlar a instalação do Office.</span><span class="sxs-lookup"><span data-stu-id="8a204-109">In previous versions of Lync and Office Communicator, you could use Windows Installer properties to customize and control the Office installation.</span></span> <span data-ttu-id="8a204-110">Como o Lync 2013 está integrado à instalação do Office, você pode usar os seguintes métodos para personalizar a instalação do Lync 2013:</span><span class="sxs-lookup"><span data-stu-id="8a204-110">Because Lync 2013 is integrated with Office setup, you can use the following methods to customize Lync 2013 setup:</span></span>

  - <span data-ttu-id="8a204-111">Usar a OCT (Ferramenta de Personalização do Office)</span><span class="sxs-lookup"><span data-stu-id="8a204-111">Use the Office Customization Tool (OCT)</span></span>

  - <span data-ttu-id="8a204-112">Usar o Config.xml para executar tarefas de instalação</span><span class="sxs-lookup"><span data-stu-id="8a204-112">Use the Config.xml to perform installation tasks</span></span>

  - <span data-ttu-id="8a204-113">Usar as opções de linha de comando de instalação</span><span class="sxs-lookup"><span data-stu-id="8a204-113">Use Setup Command-Line Options</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8a204-114">O programa de instalação do Lync 2013 não desinstala versões anteriores do Lync ou Office Communicator.</span><span class="sxs-lookup"><span data-stu-id="8a204-114">The Lync 2013 setup program does not uninstall previous versions of Lync or Office Communicator.</span></span> <span data-ttu-id="8a204-115">O cliente do Lync 2013 é instalado lado a lado com outros clientes do Lync ou do Office Communicator</span><span class="sxs-lookup"><span data-stu-id="8a204-115">The Lync 2013 client installs side-by-side with other Lync or Office Communicator clients</span></span>



</div>

<span data-ttu-id="8a204-116">Para obter detalhes, consulte [Deploying Lync clients in Lync Server 2013](lync-server-2013-deploying-lync-clients.md).</span><span class="sxs-lookup"><span data-stu-id="8a204-116">For details, see [Deploying Lync clients in Lync Server 2013](lync-server-2013-deploying-lync-clients.md).</span></span>

</div>

<div>

## <a name="group-policy-deployment"></a><span data-ttu-id="8a204-117">Implantação da Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="8a204-117">Group Policy Deployment</span></span>

<span data-ttu-id="8a204-118">Como o Lync 2013 agora está incluído na instalação do Office, o método para implantar as configurações da política de grupo do Lync foi alterado.</span><span class="sxs-lookup"><span data-stu-id="8a204-118">Because Lync 2013 is now included in Office setup, the method for deploying Lync Group Policy settings has changed.</span></span> <span data-ttu-id="8a204-119">Nas versões anteriores do Lync e do Office Communicator, você poderia usar o Communicator. ADM para definir as configurações de política de grupo, enquanto no Lync 2013 agora você pode usar os modelos administrativos do Lync ADMX e ADML que são fornecidos junto com a política de grupo do Office Modelos administrativos.</span><span class="sxs-lookup"><span data-stu-id="8a204-119">In previous versions of Lync and Office Communicator, you could use the Communicator.adm to define Group Policy settings, whereas in Lync 2013 you can now use the Lync ADMX and ADML administrative templates that are provided along with the Office Group Policy Administrative Templates.</span></span>

<span data-ttu-id="8a204-120">Para obter detalhes, consulte [configurações de política de grupo para o Lync 2013](lync-server-2013-group-policy-settings-for-lync-2013.md).</span><span class="sxs-lookup"><span data-stu-id="8a204-120">For details, see [Group Policy settings for Lync 2013](lync-server-2013-group-policy-settings-for-lync-2013.md).</span></span>

</div>

<div>

## <a name="outlook-scheduling-add-in-updates"></a><span data-ttu-id="8a204-121">Atualizações do suplemento de agendamento do Outlook</span><span class="sxs-lookup"><span data-stu-id="8a204-121">Outlook Scheduling Add-in Updates</span></span>

<span data-ttu-id="8a204-122">O suplemento reunião online do Lync 2013 inclui a personalização do convite de reunião e as novas opções de reunião.</span><span class="sxs-lookup"><span data-stu-id="8a204-122">The Online Meeting Add-in for Lync 2013 includes meeting invite customization and new meeting options.</span></span>

  - <span data-ttu-id="8a204-123">Os administradores podem personalizar os convites de reunião da organização adicionando um logotipo personalizado, uma URL de suporte, uma URL do aviso de isenção legal ou um texto de rodapé personalizado.</span><span class="sxs-lookup"><span data-stu-id="8a204-123">Administrators can customize the organization’s meeting invitations by adding a custom logo, a support URL, a legal disclaimer URL, or custom footer text.</span></span> <span data-ttu-id="8a204-124">Para obter detalhes, consulte [Personalizando o suplemento de reunião online no Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="8a204-124">For details, see [Customizing the Online Meeting Add-in in Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md).</span></span>

  - <span data-ttu-id="8a204-125">Os novos controles de ativação de mudo para participantes permitem que os organizadores de reuniões agendem conferências ativando por padrão o mudo para o áudio e o vídeo dos participantes.</span><span class="sxs-lookup"><span data-stu-id="8a204-125">New attendee mute controls allow meeting organizers to schedule conferences that have attendee audio and video muted by default.</span></span>

</div>

<div>

## <a name="virtual-desktop-infrastructure-plug-in"></a><span data-ttu-id="8a204-126">Plug-in de Virtual Desktop Infrastructure</span><span class="sxs-lookup"><span data-stu-id="8a204-126">Virtual Desktop Infrastructure Plug-in</span></span>

<span data-ttu-id="8a204-127">O cliente Lync 2013 agora oferece suporte a áudio e vídeo em um ambiente de infraestrutura de área de trabalho virtual (VDI).</span><span class="sxs-lookup"><span data-stu-id="8a204-127">The Lync 2013 client now supports audio and video in a Virtual Desktop Infrastructure (VDI) environment.</span></span> <span data-ttu-id="8a204-128">Um usuário pode conectar um dispositivo de áudio ou vídeo (por exemplo, um fone de ouvido ou uma câmera) ao computador local (por exemplo, um computador cliente fino ou realocado).</span><span class="sxs-lookup"><span data-stu-id="8a204-128">A user can connect an audio or video device (for example, a headset or a camera) to the local computer (for example, a thin client or repurposed computer).</span></span> <span data-ttu-id="8a204-129">O usuário pode se conectar à máquina virtual, entrar no cliente do Lync 2013 que está sendo executado na máquina virtual e participar da comunicação de áudio e vídeo em tempo real, como se o cliente estivesse sendo executado localmente.</span><span class="sxs-lookup"><span data-stu-id="8a204-129">The user can connect to the virtual machine, sign in to the Lync 2013 client that is running on the virtual machine, and participate in real-time audio and video communication as though the client is running locally.</span></span> <span data-ttu-id="8a204-130">Os recursos a seguir têm suporte em um ambiente de área de trabalho virtual:</span><span class="sxs-lookup"><span data-stu-id="8a204-130">The following features are supported in a virtual desktop environment:</span></span>

  - <span data-ttu-id="8a204-131">Integração de dispositivos de áudio e vídeo, incluindo:</span><span class="sxs-lookup"><span data-stu-id="8a204-131">Device integration for audio and video, including the following:</span></span>
    
      - <span data-ttu-id="8a204-132">Controles de chamada do dispositivo</span><span class="sxs-lookup"><span data-stu-id="8a204-132">Call controls from the device</span></span>
    
      - <span data-ttu-id="8a204-133">Integração de presença no dispositivo</span><span class="sxs-lookup"><span data-stu-id="8a204-133">Presence integration on the device</span></span>
    
      - <span data-ttu-id="8a204-134">Suporte á vários HIDs (dispositivos de interface humana)</span><span class="sxs-lookup"><span data-stu-id="8a204-134">Multiple HID (human interface device) support</span></span>

  - <span data-ttu-id="8a204-135">Suporte a serviços de local e emergência.</span><span class="sxs-lookup"><span data-stu-id="8a204-135">Location and emergency services support.</span></span>

  - <span data-ttu-id="8a204-136">Suporte para todas as modalidades do Lync, incluindo mensagens instantâneas, áudio, vídeo, compartilhamento de aplicativos, compartilhamento de área de trabalho, compartilhamento do PowerPoint, quadro de comunicações e transferência de arquivos.</span><span class="sxs-lookup"><span data-stu-id="8a204-136">Support for all Lync modalities, including IM, audio, video, application sharing, desktop sharing, PowerPoint sharing, whiteboard, and file transfer.</span></span>

  - <span data-ttu-id="8a204-137">Suporte a áudio e vídeo em chamadas entre duas pessoas e chamadas em conferência.</span><span class="sxs-lookup"><span data-stu-id="8a204-137">Audio and video support in person-to-person calls and conference calls.</span></span>

<span data-ttu-id="8a204-138">Para obter informações sobre a implantação do plug-in VDI, consulte [implantando o plug-in do LYNC VDI no Lync Server 2013](lync-server-2013-deploying-the-lync-vdi-plug-in.md).</span><span class="sxs-lookup"><span data-stu-id="8a204-138">For information about deploying the VDI plug-in, see [Deploying the Lync VDI plug-in in Lync Server 2013](lync-server-2013-deploying-the-lync-vdi-plug-in.md).</span></span>

</div>

<div>

## <a name="video-enhancements"></a><span data-ttu-id="8a204-139">Melhorias de vídeo</span><span class="sxs-lookup"><span data-stu-id="8a204-139">Video Enhancements</span></span>

<span data-ttu-id="8a204-140">Vários novos recursos melhoram consideravelmente a experiência de vídeo dos participantes de conferências.</span><span class="sxs-lookup"><span data-stu-id="8a204-140">Several new features significantly enhance the video experience for conference participants.</span></span>

  - <span data-ttu-id="8a204-141">O vídeo foi aprimorado com detecção facial e enquadramento inteligente para que o vídeo do participante se desloque para mantê-lo centralizado no quadro.</span><span class="sxs-lookup"><span data-stu-id="8a204-141">Video is enhanced with face detection and smart framing, so that a participant’s video moves to help keep them centered in the frame.</span></span>

  - <span data-ttu-id="8a204-p107">Agora há suporte a vídeo de alta definição em chamadas entre duas pessoas e conferências com vários participantes. Os usuários podem visualizar resoluções de até 1080P HD.</span><span class="sxs-lookup"><span data-stu-id="8a204-p107">High-definition video is now supported in two-party calls and multiparty conferences. Users can experience resolutions up to HD 1080P.</span></span>

  - <span data-ttu-id="8a204-144">Os participantes podem selecionar entre vários layouts de reunião: o Modo de Exibição de Galeria mostra as fotos e os vídeos de todos os participantes; o Modo de Exibição do Orador mostra o conteúdo da reunião e apenas a foto e o vídeo do orador atual; o Modo de Exibição de Apresentação mostra somente o conteúdo da reunião; e o Modo de Exibição Compacto mostra somente os controles da reunião.</span><span class="sxs-lookup"><span data-stu-id="8a204-144">Participants can select from different meeting layouts: Gallery View shows all participants’ pictures or videos; Speaker View shows the meeting content and only the current speaker’s video or picture; Presentation View shows meeting content only; Compact View shows just the meeting controls.</span></span>

  - <span data-ttu-id="8a204-p108">Com o novo recurso de Galeria, os participantes podem ver várias transmissões de vídeo ao mesmo tempo. Se houver mais de cinco participantes na conferência, as transmissões de vídeo somente dos participantes mais ativos aparecerão na linha superior e as fotos dos outros participantes serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="8a204-p108">With the new Gallery feature, participants can see multiple video feeds at the same time. If the conference has more than five participants, video feeds of only the most active participants appear in the top row, and pictures appear for the other participants.</span></span>

  - <span data-ttu-id="8a204-147">Os participantes podem usar o recurso de fixar vídeo para selecionar uma ou mais das transmissões de vídeo disponíveis para que fiquem sempre visíveis.</span><span class="sxs-lookup"><span data-stu-id="8a204-147">Participants can use video pinning to select one or more of the available video feeds to be visible at all times.</span></span>

  - <span data-ttu-id="8a204-148">Os apresentadores podem usar o recurso Destaque de Vídeo para selecionar o vídeo de uma pessoa para que todos os participantes da reunião vejam somente esse participante.</span><span class="sxs-lookup"><span data-stu-id="8a204-148">Presenters can use the Video Spotlight feature to select one person’s video feed so that every participant in the meeting sees that participant only.</span></span>

</div>

<div>

## <a name="chat-room-integration"></a><span data-ttu-id="8a204-149">Integração da sala de chat</span><span class="sxs-lookup"><span data-stu-id="8a204-149">Chat Room Integration</span></span>

<span data-ttu-id="8a204-150">O Lync 2013 agora integra os recursos anteriormente fornecidos pelo Lync 2010 Group Chat.</span><span class="sxs-lookup"><span data-stu-id="8a204-150">Lync 2013 now integrates the features previously provided by Lync 2010 Group Chat.</span></span> <span data-ttu-id="8a204-151">Não há mais necessidade de um cliente de chat em grupo separado.</span><span class="sxs-lookup"><span data-stu-id="8a204-151">A separate group chat client is no longer required.</span></span>

  - <span data-ttu-id="8a204-152">No Lync 2013, os usuários podem pesquisar salas de chat, adicionar salas de chat a seus contatos, monitorar a atividade de sala de chat e ler e postar mensagens.</span><span class="sxs-lookup"><span data-stu-id="8a204-152">From within Lync 2013, users can search for chat rooms, add chat rooms to their contacts, monitor chat room activity, and read and post messages.</span></span>

  - <span data-ttu-id="8a204-153">Os usuários podem criar feeds de tópicos para serem notificados se algum participante de uma de suas salas de chat adicionar uma postagem que contenha palavras-chave específicas.</span><span class="sxs-lookup"><span data-stu-id="8a204-153">Users can create topic feeds so that they’ll be notified if someone in one of their chat rooms adds a post containing specific keywords.</span></span>

  - <span data-ttu-id="8a204-154">Com a nova página de opções **Chat Persistente**, os usuários podem definir sons e alertas de notificação que são acionados quando alguém posta mensagens em suas salas de chat.</span><span class="sxs-lookup"><span data-stu-id="8a204-154">With the new **Persistent Chat** options page, users can set notification alerts and sounds that apply when people post messages to their chat rooms.</span></span>

</div>

<div>

## <a name="lync-web-app-updates"></a><span data-ttu-id="8a204-155">Atualizações do Lync Web App</span><span class="sxs-lookup"><span data-stu-id="8a204-155">Lync Web App Updates</span></span>

<span data-ttu-id="8a204-156">Lync Web App é o cliente de conferência baseado na Web para reuniões do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8a204-156">Lync Web App is the web-based conferencing client for Lync Server 2013 meetings.</span></span> <span data-ttu-id="8a204-157">Nesta versão, a adição de áudio e vídeo do computador ao Lync Web App oferece uma experiência completa de reunião para qualquer pessoa que não tenha um cliente Lync instalado localmente.</span><span class="sxs-lookup"><span data-stu-id="8a204-157">In this release, the addition of computer audio and video to Lync Web App provides a complete in-meeting experience for anyone who doesn’t have a Lync client installed locally.</span></span> <span data-ttu-id="8a204-158">Os participantes da reunião têm acesso a todos os recursos de colaboração e compartilhamento e controles de reunião de apresentador.</span><span class="sxs-lookup"><span data-stu-id="8a204-158">Meeting participants have access to all collaboration and sharing features and presenter meeting controls.</span></span>

<span data-ttu-id="8a204-159">Quando um usuário tenta ingressar em uma reunião, mas não tem um cliente instalado localmente, o Lync Web App é aberto.</span><span class="sxs-lookup"><span data-stu-id="8a204-159">When a user tries to join a meeting but doesn’t have a locally installed client, Lync Web App opens.</span></span> <span data-ttu-id="8a204-160">Se você deseja permitir opções adicionais para ingressar na reunião, é possível configurar a página de ingresso na reunião; consulte [Configurando a página de ingresso na reunião no Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="8a204-160">If you want to allow additional options for joining the meeting, you can configure the Meeting Join page; see [Configuring the meeting join page in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md) in the Deployment documentation.</span></span>

<span data-ttu-id="8a204-161">Devido aos aprimoramentos do Lync Web App, uma versão atualizada do participante não está disponível para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8a204-161">Because of the enhancements to Lync Web App, an updated version of Attendee isn’t available for Lync Server 2013.</span></span> <span data-ttu-id="8a204-162">O Lync Web App é o cliente escolhido para participantes de fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="8a204-162">Lync Web App is the client of choice for participants outside your organization.</span></span> <span data-ttu-id="8a204-163">Não é necessária a instalação local de um cliente, mas recursos de áudio, vídeo e compartilhamento exigem que um plug-in seja instalado na primeira utilização.</span><span class="sxs-lookup"><span data-stu-id="8a204-163">No local client installation is required, although audio, video, and sharing features require a plug-in to be installed at first use.</span></span>

</div>

<div>

## <a name="lync-2013-for-mobile-clients-updates"></a><span data-ttu-id="8a204-164">Lync 2013 para atualizações de clientes móveis</span><span class="sxs-lookup"><span data-stu-id="8a204-164">Lync 2013 for Mobile Clients Updates</span></span>

<span data-ttu-id="8a204-165">Além de recursos avançados de presença, contatos e mensagens instantâneas, os clientes móveis do Lync 2013 agora fornecem chamadas de voz e vídeo através da Internet e conexões de dados da rede celular.</span><span class="sxs-lookup"><span data-stu-id="8a204-165">In addition to enhanced presence, contacts, and IM capabilities, Lync 2013 mobile clients now provide voice and video calling over the Internet and cellular data connections.</span></span> <span data-ttu-id="8a204-166">Com um único toque do link de reunião em um item de calendário, os usuários móveis podem ingressar em reuniões de vídeo e voz do Lync.</span><span class="sxs-lookup"><span data-stu-id="8a204-166">With a single tap of the meeting link in a calendar item, mobile users can join Lync voice and video meetings.</span></span> <span data-ttu-id="8a204-167">Para obter mais informações sobre clientes móveis do Lync 2013, consulte [Planning for Mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span><span class="sxs-lookup"><span data-stu-id="8a204-167">For more information about Lync 2013 mobile clients, see [Planning for mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span></span>

</div>

<div>

## <a name="lync-2013-user-interface-updates"></a><span data-ttu-id="8a204-168">Atualizações da interface de usuário do Lync 2013</span><span class="sxs-lookup"><span data-stu-id="8a204-168">Lync 2013 User Interface Updates</span></span>

<div>

## <a name="accessibility-updates"></a><span data-ttu-id="8a204-169">Atualizações de acessibilidade</span><span class="sxs-lookup"><span data-stu-id="8a204-169">Accessibility Updates</span></span>

<span data-ttu-id="8a204-170">O Lync 2013 incorpora vários novos recursos de acessibilidade.</span><span class="sxs-lookup"><span data-stu-id="8a204-170">Lync 2013 incorporates several new accessibility features.</span></span>

  - <span data-ttu-id="8a204-171">O Lync 2013 oferece suporte a alta resolução de DPI, permitindo que os usuários dimensionem texto e gráficos para 125% e 150% de pontos por polegada.</span><span class="sxs-lookup"><span data-stu-id="8a204-171">Lync 2013 supports high DPI resolution, enabling users to scale text and graphics for 125% and 150% dots per inch.</span></span>

  - <span data-ttu-id="8a204-172">O Lync oferece suporte de alto contraste para que a interface do usuário permaneça totalmente funcional quando usada com temas de alto contraste no Windows.</span><span class="sxs-lookup"><span data-stu-id="8a204-172">Lync provides high-contrast support so that the user interface remains fully functional when used with high contrast themes in Windows.</span></span>

  - <span data-ttu-id="8a204-173">O Lync oferece mais de 100 atalhos de teclado para que os usuários possam acessar funções importantes sem um mouse.</span><span class="sxs-lookup"><span data-stu-id="8a204-173">Lync offers more than 100 keyboard shortcuts so that users can access important functions without a mouse.</span></span> <span data-ttu-id="8a204-174">Por exemplo, eles podem pressionar Alt+C para aceitar uma chamada ou Alt+I para ignorá-la sem precisar alternar ou definir o foco.</span><span class="sxs-lookup"><span data-stu-id="8a204-174">For example, users can press Alt+C to accept a call, or Alt + I to ignore it, without having to tab or set the focus.</span></span> <span data-ttu-id="8a204-175">A combinação de teclas Alt+Q encerra uma chamada, Ctrl+N inicia o OneNote e Alt+T abre o menu Ferramentas.</span><span class="sxs-lookup"><span data-stu-id="8a204-175">Pressing (Alt+Q) ends a call, (Ctrl+N) starts OneNote, and (Alt+T) opens the Tools menu.</span></span>

  - <span data-ttu-id="8a204-176">O amplo suporte ao leitor de tela no Lync 2013 garante que todas as notificações, solicitações de entrada e mensagens instantâneas sejam lidas em voz alta quando um leitor de tela estiver habilitado.</span><span class="sxs-lookup"><span data-stu-id="8a204-176">Extensive screen reader support in Lync 2013 ensures that all notifications, incoming requests, and instant messages are read aloud when a screen reader is enabled.</span></span>

</div>

<div>

## <a name="presence-while-sharing"></a><span data-ttu-id="8a204-177">Presença durante o compartilhamento</span><span class="sxs-lookup"><span data-stu-id="8a204-177">Presence While Sharing</span></span>

<span data-ttu-id="8a204-178">Quando o Lync detecta que um usuário está compartilhando, o Lync atribui automaticamente o usuário a apresentar o status de presença.</span><span class="sxs-lookup"><span data-stu-id="8a204-178">When Lync detects that a user is sharing, Lync automatically assigns the user a Presenting presence status.</span></span> <span data-ttu-id="8a204-179">Esse status bloqueia todas as comunicações de entrada, a menos que a relação de privacidade Grupo de Trabalho tenha sido atribuída ao remetente.</span><span class="sxs-lookup"><span data-stu-id="8a204-179">This status blocks all incoming communications unless the sender is assigned the Workgroup privacy relationship.</span></span> <span data-ttu-id="8a204-180">Se o usuário estiver usando o recurso de compartilhamento totalmente em um monitor secundário, o Lync não atribuirá um status de presença de apresentação.</span><span class="sxs-lookup"><span data-stu-id="8a204-180">If the user is using the sharing feature entirely on a secondary monitor, Lync does not assign a Presenting presence status.</span></span>

</div>

<div>

## <a name="conversation-window-updates"></a><span data-ttu-id="8a204-181">Atualizações da janela Conversa</span><span class="sxs-lookup"><span data-stu-id="8a204-181">Conversation Window Updates</span></span>

<span data-ttu-id="8a204-182">A janela Conversa reformulada oferece acesso mais rápido a recursos importantes.</span><span class="sxs-lookup"><span data-stu-id="8a204-182">The redesigned Conversation window provides quicker access to important features.</span></span>

  - <span data-ttu-id="8a204-p116">Com o novo recurso de conversas com guias, os usuários agora podem manter todas as suas IMs e salas de chat em uma única janela Conversa. As guias na lateral esquerda da janela Conversa permite que os usuários naveguem facilmente entre todas as conversas ativas.</span><span class="sxs-lookup"><span data-stu-id="8a204-p116">With the new tabbed conversations feature, users can now keep all their IMs and chat rooms in one Conversation window. The tabs along the left side of the Conversation window let users navigate easily among all active conversations.</span></span>

  - <span data-ttu-id="8a204-p117">Os usuários podem destacar uma conversa individual em uma janela separada e redimensioná-la. Além disso, também podem reinserir a janela na janela Conversa principal.</span><span class="sxs-lookup"><span data-stu-id="8a204-p117">Users can pop out an individual conversation into a separate window, and then resize the window. They can also pop the window back into the main Conversation window.</span></span>

  - <span data-ttu-id="8a204-187">O Lync 2013 reabre as conversas de um usuário quando o usuário se desconecta e entra novamente no Lync.</span><span class="sxs-lookup"><span data-stu-id="8a204-187">Lync 2013 reopens a user’s conversations when the user signs out and signs back in to Lync.</span></span>

  - <span data-ttu-id="8a204-188">Os usuários podem rapidamente adicionar a qualquer conversa ferramentas de IM, vídeo, compartilhamento de programas, compartilhamento de área de trabalho ou webconferência (quadro de comunicações, notas de reunião, blocos de anotações compartilhados e anexos).</span><span class="sxs-lookup"><span data-stu-id="8a204-188">Users can quickly add IM, video, program sharing, desktop sharing, or web conferencing tools (whiteboard, meeting notes, shared notebooks, and attachments) to any conversation.</span></span>

  - <span data-ttu-id="8a204-189">Em uma reunião em que vídeo ou conteúdo está sendo compartilhado, os usuários podem destacar o vídeo da reunião ou o conteúdo compartilhado em uma janela separada e redimensioná-la.</span><span class="sxs-lookup"><span data-stu-id="8a204-189">In a meeting where video or content is being shared, users can pop out the meeting video or shared content, and then resize the window.</span></span>

</div>

<div>

## <a name="lync-main-window-updates"></a><span data-ttu-id="8a204-190">Atualizações da janela principal do Lync</span><span class="sxs-lookup"><span data-stu-id="8a204-190">Lync Main Window Updates</span></span>

<span data-ttu-id="8a204-191">A nova aparência simplificada mantém recursos conhecidos, como o campo de notas **O que está acontecendo hoje?**, o seletor de status e o seletor **Defina o local**.</span><span class="sxs-lookup"><span data-stu-id="8a204-191">The new streamlined look retains familiar features such as the **What’s happening today?** note field, the status selector, and the **Set Your Location** selector.</span></span>

  - <span data-ttu-id="8a204-192">Quando as salas de chat estão habilitadas, os usuários visualizam um novo ícone de **salas de chat** na página principal do Lync.</span><span class="sxs-lookup"><span data-stu-id="8a204-192">When chat rooms are enabled, users see a new **Chat Rooms** icon on the main Lync page.</span></span> <span data-ttu-id="8a204-193">Com o ícone **Salas de Chat**, eles podem rapidamente acessar suas salas de chat e filtros.</span><span class="sxs-lookup"><span data-stu-id="8a204-193">With the **Chat Rooms** icon, users can quickly access their chat rooms and filters.</span></span>

  - <span data-ttu-id="8a204-194">Os usuários podem clicar nos ícones de modo de exibição para alternar entre os modos **Contatos**, **Salas de Chat**, **Conversas** ou **Telefone**.</span><span class="sxs-lookup"><span data-stu-id="8a204-194">Users can click the view icons to switch to the **Contacts** view, **Chat Rooms** view, **Conversations** view, or **Phone** view.</span></span>

  - <span data-ttu-id="8a204-195">Se os usuários tiverem sido migrados para o Exchange 2013, poderão carregar uma imagem de alta resolução.</span><span class="sxs-lookup"><span data-stu-id="8a204-195">If users have been migrated to Exchange 2013, they can upload a high resolution picture.</span></span>

</div>

<div>

## <a name="contacts-view-and-contact-card-updates"></a><span data-ttu-id="8a204-196">Atualizações do modo de exibição Contatos e do Cartão de Visita</span><span class="sxs-lookup"><span data-stu-id="8a204-196">Contacts View and Contact Card Updates</span></span>

<span data-ttu-id="8a204-197">O Lync 2013 oferece aos usuários maneiras diferentes de exibir contatos e grupos no modo de exibição de **contatos** .</span><span class="sxs-lookup"><span data-stu-id="8a204-197">Lync 2013 gives users different ways to view contacts and groups in their **Contacts** view.</span></span>

  - <span data-ttu-id="8a204-198">Com o novo repositório unificado de contatos, depois que os contatos do Lync dos usuários são migrados para o Exchange 2013, os usuários podem acessar e gerenciar seus contatos do Lync 2013, Outlook ou Outlook Web App e seus favoritos permanecem sincronizados.</span><span class="sxs-lookup"><span data-stu-id="8a204-198">With the new unified contact store, after users' Lync contacts are migrated to Exchange 2013, the users can access and manage their contacts from Lync 2013, Outlook, or Outlook Web App, and their Favorites stay synchronized.</span></span> <span data-ttu-id="8a204-199">Por exemplo, se um usuário adicionar um contato a favoritos no Outlook, o contato aparecerá no grupo favoritos no Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="8a204-199">For example, if a user adds a contact to Favorites in Outlook, the contact appears in the Favorites group in Lync 2013.</span></span>

  - <span data-ttu-id="8a204-200">Se você tiver adicionado e configurado o proxy XMPP e o gateway XMPP, os usuários poderão adicionar contatos de parceiros XMPP para mensagens instantâneas e presença.</span><span class="sxs-lookup"><span data-stu-id="8a204-200">If you have added and configured the XMPP proxy and XMPP gateway, users can add contacts from XMPP-based partners for instant messaging and presence.</span></span>

  - <span data-ttu-id="8a204-201">O novo recurso **Adicionar um contato que não é da minha organização** oferece aos usuários uma maneira fácil de adicionar pessoas de fora da organização.</span><span class="sxs-lookup"><span data-stu-id="8a204-201">A new **Add a Contact That’s Not in My Organization** feature gives users an easy way to add people who are external to the organization.</span></span>

  - <span data-ttu-id="8a204-202">O novo grupo **Favoritos** permite que os usuários criem uma lista de pessoas que contatam com mais frequência para agilizar o acesso.</span><span class="sxs-lookup"><span data-stu-id="8a204-202">A new **Favorites** group lets users build a list of people users contact most often for quicker access.</span></span>

  - <span data-ttu-id="8a204-p120">Os usuários podem usar a nova página de opções **Lista de Contatos** para escolher como desejam classificar e exibir os contatos. Eles podem selecionar um modo de exibição expandido de duas linhas, que mostra as fotos dos contatos, ou um modo de exibição compacto de uma única linha. Os usuários também podem classificar os contatos por ordem alfabética ou por disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="8a204-p120">Users can use the new **Contacts List** options page to choose how users want to sort and display contacts. Users can select an expanded, two-line view that shows contacts’ pictures, or a condensed one-line view. Users can also sort contacts alphabetically or by availability.</span></span>

</div>

<div>

## <a name="conferencing-updates"></a><span data-ttu-id="8a204-206">Atualizações de conferências</span><span class="sxs-lookup"><span data-stu-id="8a204-206">Conferencing Updates</span></span>

<span data-ttu-id="8a204-207">O Lync 2013 oferece vários aprimoramentos aos recursos de conferência.</span><span class="sxs-lookup"><span data-stu-id="8a204-207">Lync 2013 offers several enhancements to conferencing features.</span></span>

  - <span data-ttu-id="8a204-p121">Dependendo do tipo de reunião, os usuários agora podem ativar o mudo para os participantes e permitir ou bloquear o compartilhamento de vídeo ao agendarem a reunião. Essas opções estão disponíveis na página **Opções de Reunião** e são recomendadas para reuniões grandes com mais de 20 participantes.</span><span class="sxs-lookup"><span data-stu-id="8a204-p121">Depending on the type of meeting, users can now mute the audience and allow or block video sharing when scheduling the meeting. These options are available on the **Meeting Options** page and are recommended for large meetings with more than 20 participants.</span></span>

  - <span data-ttu-id="8a204-210">Controles de áudio fáceis de usar na sala de reunião permitem que o usuário controle as opções de áudio, como ativar mudo, desativar mudo, alterar dispositivo etc.</span><span class="sxs-lookup"><span data-stu-id="8a204-210">Easy to use audio controls in the meeting room allow the user to control audio options, such as mute, unmute, change device, and so on.</span></span>

  - <span data-ttu-id="8a204-211">Ao compartilhar programas, os usuários podem selecionar vários programas para compartilhamento se precisarem trabalhar com mais de um ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="8a204-211">When sharing programs, users can select multiple programs to share if they need to work with more than one program.</span></span>

  - <span data-ttu-id="8a204-212">Os usuários agora podem carregar apresentações que contêm clipes de vídeo carregando o arquivo do PowerPoint e apontando o mouse sobre o slide para exibir os controles de vídeo, como reproduzir e pausar, bem como os controles de áudio.</span><span class="sxs-lookup"><span data-stu-id="8a204-212">Users can now upload presentations that contain video clips by uploading the PowerPoint file, and pointing the mouse over the slide to display video controls, such as play, pause, and audio controls.</span></span>

  - <span data-ttu-id="8a204-213">Durante uma reunião, os usuários podem incorporar outra conversa aberta à reunião usando o comando **Mesclar esta Conversa em** no menu **Mais Opções** (**…**).</span><span class="sxs-lookup"><span data-stu-id="8a204-213">While in a meeting, users can merge another open conversation into the meeting by using **Merge This Call Into** on the **More Options** (**…**) menu.</span></span>

  - <span data-ttu-id="8a204-214">Para ver os nomes dos participantes, os usuários podem passar o mouse sobre o botão **Exibir Participantes** ou clicar em **Mostrar Lista de Participantes** para encaixar o painel na reunião.</span><span class="sxs-lookup"><span data-stu-id="8a204-214">To see the participants’ names, users can hover the mouse over the **View Participants** button, or click **Show Participant List** to dock the panel in the meeting.</span></span>

  - <span data-ttu-id="8a204-215">Dependendo do tipo de reunião, os usuários podem selecionar entre vários modos de exibição de participantes e conteúdo.</span><span class="sxs-lookup"><span data-stu-id="8a204-215">Depending on the meeting type, users can select from several different content and participant views.</span></span>

  - <span data-ttu-id="8a204-p122">As gravações de reuniões são automaticamente salvas em um formato que pode ser reproduzido no Windows Media Player (MP4). Os usuários podem facilmente compartilhar o arquivo com qualquer pessoa ou usar o recurso **Publicar** do gerenciador de gravações para postar a gravação em um local compartilhado.</span><span class="sxs-lookup"><span data-stu-id="8a204-p122">Meeting recordings are automatically saved in a format that plays in Windows Media Player (MP4). Users can easily share the file with anyone, or use the **Publish** feature in recording manager to post the recording on a shared location.</span></span>

  - <span data-ttu-id="8a204-p123">O OneNote permite novas maneiras de colaborar em uma reunião. Durante uma reunião, os usuários podem fazer anotações com o OneNote para uso pessoal após a reunião ou usar os blocos de anotações compartilhados e realizar edições em conjunto com os participantes da reunião em tempo real. Todos os membros da equipe podem acessar as anotações compartilhadas para contribuir com informações, desenvolver ideias ou usar as páginas do bloco de anotações como um quadro de comunicações virtual. As pessoas e o conteúdo compartilhado na reunião são automaticamente adicionados às anotações.</span><span class="sxs-lookup"><span data-stu-id="8a204-p123">OneNote enables new ways to collaborate in a meeting. During a meeting, users can take notes with OneNote for personal use after the meeting, or use shared notebooks and co-edit with meeting participants in real time. All team members can access the shared notes to contribute information, brainstorm ideas, or use the notebook pages as a virtual whiteboard. People and content shared in the meeting are automatically added to the Notes.</span></span>

  - <span data-ttu-id="8a204-p124">Os usuários podem alternar entre os tipos de conteúdo usando a opção **Compartilhar conteúdo e liderar atividades da reunião** na parte inferior da sala de reunião. Eles também podem usar o menu **Gerenciar Conteúdo Apresentável** para escolher qual conteúdo desejam compartilhar.</span><span class="sxs-lookup"><span data-stu-id="8a204-p124">Users can switch between content types using **Share content and lead meeting activities** at the bottom of the meeting room. Users can also use the **Manage Presentable Content** menu to choose which content they want to share.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8a204-224">Confira também</span><span class="sxs-lookup"><span data-stu-id="8a204-224">See Also</span></span>


[<span data-ttu-id="8a204-225">Planejamento de clientes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a204-225">Planning for clients in Lync Server 2013</span></span>](lync-server-2013-planning-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

