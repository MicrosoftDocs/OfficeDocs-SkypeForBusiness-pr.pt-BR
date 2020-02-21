---
title: Lync Server 2013 Enterprise Voice
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enterprise Voice
ms:assetid: c9da8099-6f4f-4346-ac67-f041bb96072c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417163(v=OCS.15)
ms:contentKeyID: 48185404
ms.date: 04/08/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 924e15aae9590b6148864084aa68924e4c080f7c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213337"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="abf5b-102">Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="abf5b-102">Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="abf5b-103">_**Última modificação do tópico:** 2015-04-08_</span><span class="sxs-lookup"><span data-stu-id="abf5b-103">_**Topic Last Modified:** 2015-04-08_</span></span>

<span data-ttu-id="abf5b-104">Com o Enterprise Voice, o Lync Server fornece uma oferta de protocolo VoIP para aprimorar ou substituir sistemas PBX (Private Branch Exchange) tradicionais.</span><span class="sxs-lookup"><span data-stu-id="abf5b-104">With Enterprise Voice, Lync Server delivers a stand-alone Voice over Internet Protocol (VoIP) offering to enhance or replace traditional private branch exchange (PBX) systems.</span></span> <span data-ttu-id="abf5b-105">Os usuários do Enterprise Voice podem ligar para colegas na sua rede VoIP da organização ou PBX e podem ligar para números tradicionais fora da organização.</span><span class="sxs-lookup"><span data-stu-id="abf5b-105">Enterprise Voice users can call colleagues on your organization’s VoIP network or PBX, and they can call traditional phone numbers outside your organization.</span></span> <span data-ttu-id="abf5b-106">A solução Enterprise Voice inclui recursos de chamada comuns como resposta, encaminhamento, transferência, retenção, reenvio, lançamento e estacionamento, e Enhanced 9-1-1 (E9-1-1) chamada (E9-1-1 está disponível somente nos Estados Unidos). O Enterprise Voice também oferece suporte a uma ampla variedade de dispositivos IP e USB atuais e antigos.</span><span class="sxs-lookup"><span data-stu-id="abf5b-106">The Enterprise Voice solution includes common calling features such as answer, forward, transfer, hold, divert, release and park, and Enhanced 9-1-1 (E9-1-1) calling (E9-1-1 is available only in the United States.) Enterprise Voice also supports a broad range of current and older IP and USB devices.</span></span>

<div>

## <a name="placing-and-receiving-calls"></a><span data-ttu-id="abf5b-107">Fazendo e recebendo chamadas</span><span class="sxs-lookup"><span data-stu-id="abf5b-107">Placing and Receiving Calls</span></span>

<span data-ttu-id="abf5b-108">Usando o Lync, os usuários podem fazer chamadas digitando um nome ou número de telefone no teclado ou usando um teclado de discagem exibido na tela.</span><span class="sxs-lookup"><span data-stu-id="abf5b-108">Using Lync, users can place calls by typing a name or phone number on their keyboard, or using a dial pad displayed on their screen.</span></span> <span data-ttu-id="abf5b-109">Os usuários podem iniciar chamadas diretamente da sua lista de Contatos.</span><span class="sxs-lookup"><span data-stu-id="abf5b-109">Users can also initiate calls directly from their Contacts list.</span></span> <span data-ttu-id="abf5b-110">Você também pode implantar dispositivos do Lync Phone Edition, que são dispositivos de telefone IP autônomos fornecidos por parceiros da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="abf5b-110">You can also deploy Lync Phone Edition devices, which are stand-alone IP phone devices provided by Microsoft partners.</span></span>

<span data-ttu-id="abf5b-111">Os usuários podem ter vários dispositivos telefônicos registrados no Lync Server e podem alternar entre eles facilmente.</span><span class="sxs-lookup"><span data-stu-id="abf5b-111">Users can have multiple phone devices registered with Lync Server, and can switch between them easily.</span></span>

<span data-ttu-id="abf5b-112">Os usuários são alertados sobre chamadas recebidas em todos seus dispositivos simultaneamente, com toques personalizados em telefones IP e uma notificação parecida com uma mensagem instantânea no PC.</span><span class="sxs-lookup"><span data-stu-id="abf5b-112">Users are alerted to incoming calls on all their devices simultaneously, with customizable ringtones on IP phone devices and a notification similar to an instant message on their PC.</span></span>

<span data-ttu-id="abf5b-113">Os usuários também podem definir um único número de telefone que fica conectado ao telefone de mesa, PC e celular, de modo que possam ser encontrados não importa onde estejam.</span><span class="sxs-lookup"><span data-stu-id="abf5b-113">Users can also set a single telephone number that connects to their desk phone, PC and mobile phone, so they can be reached no matter where they are.</span></span>

</div>

<div>

## <a name="basic-call-features"></a><span data-ttu-id="abf5b-114">Recursos básicos de chamada</span><span class="sxs-lookup"><span data-stu-id="abf5b-114">Basic Call Features</span></span>

<span data-ttu-id="abf5b-p103">Durante uma chamada, um usuário pode atender a outras chamadas ou iniciar chamadas de saída, e a chamada ativa atual é colocada automaticamente em espera. As chamadas podem ser transferidas de um usuário para outro, diretamente ou após o primeiro usuário falar em particular com o segundo usuário. Os usuários também podem transferir chamadas para outro dispositivo; por exemplo, eles podem transferir uma chamada ativa para seus celulares enquanto saem de seus escritórios.</span><span class="sxs-lookup"><span data-stu-id="abf5b-p103">While on a call, a user can answer additional incoming calls or initiate outgoing calls, and the existing active call is automatically put on hold. Calls can be transferred from one user to another, either directly or after the first user speaks privately with the second user. Users can also transfer calls to another device; for example, they could transfer an active call to their mobile phone as they walk out the door of their office.</span></span>

</div>

<div>

## <a name="richer-communications"></a><span data-ttu-id="abf5b-118">Comunicações mais ricas</span><span class="sxs-lookup"><span data-stu-id="abf5b-118">Richer Communications</span></span>

<span data-ttu-id="abf5b-119">Ao falar com outro usuário com o Lync, os usuários podem facilmente adicionar o compartilhamento de texto, vídeo ou área de trabalho à chamada.</span><span class="sxs-lookup"><span data-stu-id="abf5b-119">When talking to another user with Lync, users can easily add text, video, or desktop sharing to the call.</span></span> <span data-ttu-id="abf5b-120">O recurso do-not-perturbe é integrado às configurações de presença no Lync.</span><span class="sxs-lookup"><span data-stu-id="abf5b-120">The Do-Not-Disturb feature is integrated with the presence settings in Lync.</span></span>

<span data-ttu-id="abf5b-121">Com a Unificação de mensagens (UM) do Exchange, o Lync e o Lync Server se integram com o Microsoft Exchange Server 2013 e o Microsoft Outlook 2013.</span><span class="sxs-lookup"><span data-stu-id="abf5b-121">With Exchange Unified Messaging (UM), Lync and Lync Server integrate with Microsoft Exchange Server 2013 and Microsoft Outlook 2013.</span></span> <span data-ttu-id="abf5b-122">Os usuários podem ver se têm novas mensagens de voz na janela do Lync e no email.</span><span class="sxs-lookup"><span data-stu-id="abf5b-122">Users can see if they have new voice mail both in their Lync window and in email.</span></span> <span data-ttu-id="abf5b-123">Enquanto estiverem no email, podem clicar para reproduzir o áudio da caixa postal em uma mensagem de email ou exibir uma transcrição da mensagem de caixa postal.</span><span class="sxs-lookup"><span data-stu-id="abf5b-123">While in email they can click to play the voice mail audio in an email message, or view a transcript of the voice mail message.</span></span>

</div>

<div>

## <a name="advanced-calling-features"></a><span data-ttu-id="abf5b-124">Recursos avançados de chamada</span><span class="sxs-lookup"><span data-stu-id="abf5b-124">Advanced Calling Features</span></span>

<span data-ttu-id="abf5b-125">O Enterprise Voice também inclui vários recursos de chamadas avançados, como a delegação de chamada do Lync, chamada em equipe, recebimento de chamadas em grupo e grupos de resposta.</span><span class="sxs-lookup"><span data-stu-id="abf5b-125">Enterprise Voice includes several advanced calling features as well, such as Lync call delegation, team calling, Group Call Pickup, and Response Groups.</span></span>

<span data-ttu-id="abf5b-126">A delegação de chamadas do Lync permite que os usuários deleguem o tratamento de chamadas a um \*\*\*\* \> ou mais assistentes, acessando as **configurações de atendimento de chamadas das** **Opções** \> .</span><span class="sxs-lookup"><span data-stu-id="abf5b-126">Lync call delegation enables users to delegate call handling to one or more assistants, by going to **Tools** \> **Options** \> **Call Forwarding Settings**.</span></span> <span data-ttu-id="abf5b-127">O representante pode executar diversas tarefas de chamada em nome do usuário, incluindo camadas filtragem de chamadas, realização de chamadas e início de conferências.</span><span class="sxs-lookup"><span data-stu-id="abf5b-127">The delegate can perform multiple calling tasks on behalf of the user, including screening calls, placing calls, and initiating conferences.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="abf5b-128">Você pode estar procurando outro recurso de nome similar, delegação de calendário do Lync.</span><span class="sxs-lookup"><span data-stu-id="abf5b-128">You may be looking for another similarly named feature, Lync calendar delegation.</span></span> <span data-ttu-id="abf5b-129">Ele não exige o recurso Enterprise Voice e permite que os usuários agendem reuniões online do Lync a partir do Outlook.</span><span class="sxs-lookup"><span data-stu-id="abf5b-129">It doesn't require the Enterprise Voice feature and does allow users to schedule online Lync meetings from Outlook.</span></span> <span data-ttu-id="abf5b-130">Se você vir aqui procurando essas informações, recomendamos o check-out do <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">set-CsClientPolicy</A> para obter informações sobre como habilitar a sincronização de representante do Exchange.</span><span class="sxs-lookup"><span data-stu-id="abf5b-130">If you've come here looking for that info, we recommend checking out <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A> for information on enabling Exchange delegate sync.</span></span>



</div>

<span data-ttu-id="abf5b-131">A chamada em equipe permite que um usuário tenha chamadas de entrada para ligar simultaneamente os telefones dos colegas de equipe, de forma que qualquer pessoa da equipe possa responder à chamada.</span><span class="sxs-lookup"><span data-stu-id="abf5b-131">Team calling enables a user to have incoming calls simultaneously ring the phones of teammates so that anyone on the team can answer the call.</span></span>

<span data-ttu-id="abf5b-132">Atendimento de chamadas em grupo, um novo recurso em atualizações cumulativas do Lync Server 2013:2013 de fevereiro, permite que os usuários respondam chamadas de entrada para seus colegas de seus próprios telefones.</span><span class="sxs-lookup"><span data-stu-id="abf5b-132">Group Call Pickup, a new feature in Cumulative Updates for Lync Server 2013: February 2013, lets users answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="abf5b-133">O recebimento de chamadas de grupo difere da chamada de equipe, principalmente, quando uma chamada de entrada entra apenas no telefone do destinatário, mas qualquer outro usuário pode optar por respondê-lo discando um número de grupo de recebimento de chamada.</span><span class="sxs-lookup"><span data-stu-id="abf5b-133">Group Call Pickup differs from team calling primarily in that an incoming call rings only at the intended recipient's phone, but any other user can choose to answer it by dialing a call pickup group number.</span></span>

<span data-ttu-id="abf5b-p109">Os Grupos de Resposta podem ser definidos para enfileiramento e roteamento inteligente de chamadas aos agentes designados. Entre os usos comuns estão assistência técnica de TI, linde atendimento dos recursos humanos e outros centros de contato internos.</span><span class="sxs-lookup"><span data-stu-id="abf5b-p109">Response Groups can be set up for queuing and intelligently routing calls to designated agents. Common uses include IT helpdesks, human resources hotlines, and other internal contact centers.</span></span>

</div>

<div>

## <a name="enterprise-voice-administration"></a><span data-ttu-id="abf5b-136">Administração do Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="abf5b-136">Enterprise Voice Administration</span></span>

<span data-ttu-id="abf5b-137">O Lync Server usa padrões e interfaces publicadas para interoperar com a infraestrutura existente.</span><span class="sxs-lookup"><span data-stu-id="abf5b-137">Lync Server uses standards and published interfaces to interoperate with existing infrastructure.</span></span> <span data-ttu-id="abf5b-138">Ele suporta as opções de gateway e SIP (como tronco SIP) para interconexão com sistemas IP PBX e as redes PSTN, de modo que você possa migrar os usuários para o Enterprise Voice com o tempo, minimizando as interrupções.</span><span class="sxs-lookup"><span data-stu-id="abf5b-138">It supports both gateway and SIP options (such as SIP trunking) for interconnection to IP PBX systems and the PSTN networks, so that you can migrate users to Enterprise Voice over time, while minimizing disruption.</span></span> <span data-ttu-id="abf5b-139">O Lync Server oferece suporte a codecs tradicionais como G. 711, G. 722 e G. 723.1 para interoperabilidade com as soluções tradicionais de VoIP.</span><span class="sxs-lookup"><span data-stu-id="abf5b-139">Lync Server supports traditional codecs such as G.711, G.722, and G.723.1 for interoperability with traditional VoIP solutions.</span></span>

<span data-ttu-id="abf5b-140">Com o controle de admissão de chamadas (CAC), os administradores podem definir limites na quantidade de tráfego de voz e vídeo do Lync Server transportada em links de rede restritos e especificar a ação a ser tomada se uma nova chamada exceder o limite.</span><span class="sxs-lookup"><span data-stu-id="abf5b-140">With call admission control (CAC), administrators can set limits on the amount of Lync Server voice and video traffic carried on constrained network links, and specify the action to be taken if a new call would exceed the limit.</span></span> <span data-ttu-id="abf5b-141">As ações poderiam incluir roteamento por um caminho alternativo ou a recusa da chamada.</span><span class="sxs-lookup"><span data-stu-id="abf5b-141">The actions could include routing by an alternate path, or refusing the call.</span></span>

<span data-ttu-id="abf5b-142">O Lync Server funciona com aparelhos de filial persistente de terceiros para fornecer serviços de chamada local e conexão com PSTN em filiais, em caso de falha de WAN no site central.</span><span class="sxs-lookup"><span data-stu-id="abf5b-142">Lync Server works with third-party Survivable Branch Appliances to provide local calling services and connection to PSTN at branch offices, in case of WAN failure at the central site.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

