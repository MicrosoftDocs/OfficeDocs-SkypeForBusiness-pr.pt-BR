---
title: 'Lync Server 2013: Conferência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conferencing
ms:assetid: 6129b7e0-9abd-488e-a54e-86094eb9df7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417161(v=OCS.15)
ms:contentKeyID: 48184274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00f368a375a73eddc78b858c0d85a1bc21a1bd04
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836471"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-in-lync-server-2013"></a><span data-ttu-id="a2488-102">Conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2488-102">Conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2488-103">_**Tópico da última modificação:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="a2488-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="a2488-104">Com a conferência unificada no Lync Server 2013, os usuários podem colaborar, compartilhar informações e coordenar seus esforços em tempo real.</span><span class="sxs-lookup"><span data-stu-id="a2488-104">With unified conferencing in Lync Server 2013, users can collaborate, share information, and coordinate their efforts in real time.</span></span> <span data-ttu-id="a2488-105">Todos os seus usuários podem usar a ampla variedade de colaboração espontaneal, reuniões agendadas e ferramentas de reunião.</span><span class="sxs-lookup"><span data-stu-id="a2488-105">All your users can use the full breadth of spontaneous collaboration, scheduled meetings, and meeting tools.</span></span> <span data-ttu-id="a2488-106">Os recursos de voz e videoconferência podem ser usados em qualquer local com uma conexão à Internet, e os usuários longe de um computador podem participar de conferências de áudio discando com um telefone PSTN (rede telefônica pública comutada).</span><span class="sxs-lookup"><span data-stu-id="a2488-106">Voice and video conferencing capabilities can be used from any location with an Internet connection, and users away from a computer can participate in audio conferences by dialing in with a public switched telephone network (PSTN) phone.</span></span>

<span data-ttu-id="a2488-107">Ferramentas de reunião integradas ao Outlook permitem que os organizadores agendem uma reunião ou iniciem uma conferência improvisada com um único clique, e também o tornam mais fácil para os participantes ingressarem.</span><span class="sxs-lookup"><span data-stu-id="a2488-107">Meeting tools integrated into Outlook enable organizers to schedule a meeting or start an impromptu conference with a single click, and also make it just as easy for attendees to join.</span></span> <span data-ttu-id="a2488-108">Um cliente da Web amplia recursos de conferência avançados para os participantes que não estão executando a versão para área de trabalho do Lync.</span><span class="sxs-lookup"><span data-stu-id="a2488-108">A web client extends rich conference features to participants who are not running the desktop version of Lync.</span></span>

<div>

## <a name="audio-and-video-conferencing"></a><span data-ttu-id="a2488-109">Conferência de áudio e vídeo</span><span class="sxs-lookup"><span data-stu-id="a2488-109">Audio and Video Conferencing</span></span>

<span data-ttu-id="a2488-110">O Lync Server oferece uma experiência do usuário que é familiar aos usuários dos serviços tradicionais de ponte de áudio, incluindo os serviços de discagem PSTN com comandos de controle de chamada de Tom de toque.</span><span class="sxs-lookup"><span data-stu-id="a2488-110">Lync Server provides a user experience that is familiar to users of traditional audio bridge services including PSTN dial-in services with touch-tone call control commands.</span></span> <span data-ttu-id="a2488-111">Ao mesmo tempo, incorpora recursos avançados de agendamento, associação e gerenciamento disponíveis apenas com uma plataforma integrada de comunicação unificada.</span><span class="sxs-lookup"><span data-stu-id="a2488-111">At the same time, it incorporates powerful scheduling, joining, and management features available only with an integrated unified communications platform.</span></span>

<span data-ttu-id="a2488-112">Com um único clique, os usuários podem agendar uma reunião no Outlook.</span><span class="sxs-lookup"><span data-stu-id="a2488-112">With a single click, users can schedule a meeting from Outlook.</span></span> <span data-ttu-id="a2488-113">Detalhes, como o horário da reunião, o local e os participantes, seguem o modelo conhecido do Outlook.</span><span class="sxs-lookup"><span data-stu-id="a2488-113">Details, such as meeting time, location, and attendees, follow the familiar Outlook template.</span></span> <span data-ttu-id="a2488-114">Além disso, informações específicas de chamadas em conferência, como número de discagem, IDs de reunião e lembretes de PIN (número de identificação pessoal), são automaticamente preenchidas.</span><span class="sxs-lookup"><span data-stu-id="a2488-114">Additionally, conference call-specific information, such as dial-in number, meeting IDs, and personal identification number (PIN) reminders, are automatically populated.</span></span>

<span data-ttu-id="a2488-115">Para ajudar a garantir que apenas as pessoas autorizadas participem de uma chamada, o Lync Server oferece vários níveis de autenticação para os participantes.</span><span class="sxs-lookup"><span data-stu-id="a2488-115">To help ensure that only the authorized people participate in a call, Lync Server provides multiple levels of authentication for participants.</span></span> <span data-ttu-id="a2488-116">Os usuários que ingressarem usando o Lync já serão autenticados pelos serviços de domínio Active Directory e não precisarão inserir um PIN, passar código ou ID de reunião.</span><span class="sxs-lookup"><span data-stu-id="a2488-116">Users who join by using Lync are already authenticated by the Active Directory Domain Services and do not need to enter a PIN, pass code, or meeting ID.</span></span>

<span data-ttu-id="a2488-117">O Lync simplifica a experiência do usuário de videoconferência ao incorporar vídeo ao cliente unificado para que o agendamento de uma reunião com vídeo ou o escalonamento de vídeo espontaneamente seja perfeito e fácil.</span><span class="sxs-lookup"><span data-stu-id="a2488-117">Lync simplifies the video conferencing user experience by incorporating video into the unified client so that scheduling a meeting with video or escalating to video spontaneously is seamless and easy.</span></span>

<span data-ttu-id="a2488-118">O Lync Server torna mais fácil adicionar vídeo a uma chamada telefônica padrão em apenas um clique.</span><span class="sxs-lookup"><span data-stu-id="a2488-118">Lync Server makes it easy to add video to a standard phone call in just one click.</span></span> <span data-ttu-id="a2488-119">Quando há vários participantes em uma chamada com vídeo ou uma conferência, cada usuário pode ver vídeos de até cinco outros usuários simultaneamente, ou um apresentador pode escolher apenas uma fonte de vídeo para ser vista exclusivamente por todos.</span><span class="sxs-lookup"><span data-stu-id="a2488-119">When there are multiple participants in a video call or a conference, each user can see video from up to five other users simultaneously, or a presenter can choose just one video source to be seen exclusively by everyone.</span></span>

<span data-ttu-id="a2488-120">Vídeo de alta definição (resolução 1270 x 720; taxa de proporção 16:9) e vídeo VGA (resolução 640 x 480; taxa de proporção 4:3) são compatíveis com chamadas ponto a ponto entre usuários que executam o Lync em computadores high-end.</span><span class="sxs-lookup"><span data-stu-id="a2488-120">High-definition video (resolution 1270 x 720; aspect ratio 16:9) and VGA video (resolution 640 x 480; aspect ratio 4:3) are supported for peer-to-peer calls between users running Lync on high-end computers.</span></span> <span data-ttu-id="a2488-121">A resolução exibida por cada participante de uma única conversa pode ser diferente, dependendo dos recursos de vídeo do respectivo hardware de cada usuário.</span><span class="sxs-lookup"><span data-stu-id="a2488-121">The resolution viewed by each participant in a single conversation may differ, depending on the video capabilities of each user’s respective hardware.</span></span>

<span data-ttu-id="a2488-122">Os administradores de ti podem definir políticas para restringir ou desabilitar o vídeo em alta definição ou VGA em clientes, dependendo da funcionalidade do computador, da largura de banda da rede e da presença de uma câmera que possa fornecer a resolução necessária.</span><span class="sxs-lookup"><span data-stu-id="a2488-122">IT administrators can set policies to restrict or disable high-definition or VGA video on clients, depending on computer capability, network bandwidth, and the presence of a camera able to deliver the required resolution.</span></span> <span data-ttu-id="a2488-123">Essas políticas são impostas por meio de provisionamento em banda.</span><span class="sxs-lookup"><span data-stu-id="a2488-123">These policies are enforced through in-band provisioning.</span></span>

</div>

<div>

## <a name="web-conferencing"></a><span data-ttu-id="a2488-124">Webconferência</span><span class="sxs-lookup"><span data-stu-id="a2488-124">Web conferencing</span></span>

<span data-ttu-id="a2488-125">O Lync Server integra recursos de compartilhamento de conferência, como área de trabalho, aplicativo, anexo, quadro de comunicações, votação e PowerPoint no Lync otimizado.</span><span class="sxs-lookup"><span data-stu-id="a2488-125">Lync Server integrates conferencing sharing features such as desktop, application, attachment, whiteboard, poll and PowerPoint into the streamlined Lync.</span></span> <span data-ttu-id="a2488-126">Combinadas com videoconferências ou videoconferências, o resultado é uma sessão de alto nível e colaboração que é simples de facilitar.</span><span class="sxs-lookup"><span data-stu-id="a2488-126">Combined with audio or video conferencing, the result is a highly immersive and collaborative session that is simple to facilitate.</span></span>

<span data-ttu-id="a2488-127">Para melhorar a experiência geral dos usuários de apresentar ou exibir apresentações do PowerPoint, o Lync Server 2013 emprega os Office Web Apps para manipular apresentações do PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="a2488-127">To improve the overall experience of users presenting or viewing PowerPoint presentations, Lync Server 2013 employs Office Web Apps to handle PowerPoint presentations.</span></span> <span data-ttu-id="a2488-128">Os usuários podem compartilhar uma imagem ou copiar e colar texto usando um quadro de comunicações na reunião do Lync.</span><span class="sxs-lookup"><span data-stu-id="a2488-128">Users can share a picture or copy and paste text using a Whiteboard in the Lync meeting.</span></span> <span data-ttu-id="a2488-129">Os apresentadores podem conduzir sondagens na reunião do Lync para solicitar comentários dos participantes.</span><span class="sxs-lookup"><span data-stu-id="a2488-129">Presenters can conduct polls in the Lync meeting to solicit feedback from the attendees.</span></span>

<span data-ttu-id="a2488-130">O compartilhamento de área de trabalho habilita apresentadores para transmitir qualquer visual, aplicativo, página da Web, documentos, software ou parte de seus computadores de mesa para participantes remotos em tempo real, diretamente do Lync.</span><span class="sxs-lookup"><span data-stu-id="a2488-130">Desktop sharing enables presenters to broadcast any visuals, applications, webpages, documents, software, or part of their desktops to remote participants in real time, right from Lync.</span></span> <span data-ttu-id="a2488-131">Os membros do público podem acompanhar os movimentos do mouse e a entrada do teclado.</span><span class="sxs-lookup"><span data-stu-id="a2488-131">Audience members can follow along with mouse movements and keyboard input.</span></span> <span data-ttu-id="a2488-132">Os apresentadores podem optar por compartilhar a tela inteira ou apenas uma parte.</span><span class="sxs-lookup"><span data-stu-id="a2488-132">Presenters can choose to share the entire screen or only a portion.</span></span> <span data-ttu-id="a2488-133">Ao compartilhar suas áreas de trabalho, os apresentadores podem se associar a seus públicos em demonstrações interativas de produtos ou softwares em qualquer local.</span><span class="sxs-lookup"><span data-stu-id="a2488-133">By sharing their desktops, presenters are able to engage with their audiences in interactive product or software demos from any location.</span></span>

<span data-ttu-id="a2488-134">O compartilhamento de aplicativos permite que os apresentadores compartilhem o controle de software em suas áreas de trabalho sem perder a visão do comentário do participante ou perguntas de texto.</span><span class="sxs-lookup"><span data-stu-id="a2488-134">Application sharing enables presenters to share control of software on their desktops without losing sight of participant feedback or text questions.</span></span> <span data-ttu-id="a2488-135">Os apresentadores também podem delegar o controle do aplicativo aos participantes da reunião.</span><span class="sxs-lookup"><span data-stu-id="a2488-135">Presenters can also delegate control of the application to meeting participants.</span></span>

</div>

<div>

## <a name="dial-in-conferencing"></a><span data-ttu-id="a2488-136">Conferência discada</span><span class="sxs-lookup"><span data-stu-id="a2488-136">Dial-in Conferencing</span></span>

<span data-ttu-id="a2488-137">Para os usuários que não estão usando um computador pessoal, há vários métodos disponíveis para ingressar em uma chamada em conferência do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a2488-137">For users that are not using a personal computer, there are several methods available for joining a Lync Server conference call.</span></span> <span data-ttu-id="a2488-138">Um usuário PSTN pode discar um número de acesso, acessar a ponte de reunião e digitar a ID da reunião.</span><span class="sxs-lookup"><span data-stu-id="a2488-138">A PSTN user can dial an access number, access the meeting bridge, and then enter the meeting ID.</span></span> <span data-ttu-id="a2488-139">Para reuniões mais seguras, o usuário também pode ser solicitado a digitar seu PIN para autenticar-se no Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a2488-139">For more secure meetings, the user can also be required to enter his or her PIN to authenticate against Active Directory.</span></span> <span data-ttu-id="a2488-140">O Lync Server também dá suporte a dispositivos Lync Phone Edition, que são dispositivos de telefonia IP autônomos fornecidos pelos parceiros da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a2488-140">Lync Server also supports Lync Phone Edition devices, which are stand-alone IP phone devices provided by Microsoft partners.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

