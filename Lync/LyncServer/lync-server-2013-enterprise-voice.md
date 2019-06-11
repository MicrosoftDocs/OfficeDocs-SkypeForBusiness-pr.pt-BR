---
title: 'Lync Server 2013: Enterprise Voice'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enterprise Voice
ms:assetid: c9da8099-6f4f-4346-ac67-f041bb96072c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417163(v=OCS.15)
ms:contentKeyID: 48185404
ms.date: 04/08/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7c8131c2f52dfc7ab061d8dec46ee34b62f89e2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829215"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="202d0-102">Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="202d0-102">Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="202d0-103">_**Tópico da última modificação:** 2015-04-08_</span><span class="sxs-lookup"><span data-stu-id="202d0-103">_**Topic Last Modified:** 2015-04-08_</span></span>

<span data-ttu-id="202d0-104">Com o Enterprise Voice, o Lync Server oferece uma oferta de protocolo de voz (VoIP) autônoma para aprimorar ou substituir sistemas PBX (Private Branch Exchange) tradicionais.</span><span class="sxs-lookup"><span data-stu-id="202d0-104">With Enterprise Voice, Lync Server delivers a stand-alone Voice over Internet Protocol (VoIP) offering to enhance or replace traditional private branch exchange (PBX) systems.</span></span> <span data-ttu-id="202d0-105">Os usuários do Enterprise Voice podem chamar colegas na rede VoIP ou PBX da sua organização, e podem ligar para números de telefone tradicionais fora de sua organização.</span><span class="sxs-lookup"><span data-stu-id="202d0-105">Enterprise Voice users can call colleagues on your organization’s VoIP network or PBX, and they can call traditional phone numbers outside your organization.</span></span> <span data-ttu-id="202d0-106">A solução Enterprise Voice inclui recursos de chamadas comuns, como atender, encaminhar, transferir, suspender, reenvio, lançamento e estacionamento, e 9-1-1 (E9-1-1) de chamadas (E9-1-1 está disponível somente nos Estados Unidos.) O Enterprise Voice também oferece suporte a uma ampla gama de dispositivos IP e USB atuais e mais antigos.</span><span class="sxs-lookup"><span data-stu-id="202d0-106">The Enterprise Voice solution includes common calling features such as answer, forward, transfer, hold, divert, release and park, and Enhanced 9-1-1 (E9-1-1) calling (E9-1-1 is available only in the United States.) Enterprise Voice also supports a broad range of current and older IP and USB devices.</span></span>

<div>

## <a name="placing-and-receiving-calls"></a><span data-ttu-id="202d0-107">Fazendo e recebendo chamadas</span><span class="sxs-lookup"><span data-stu-id="202d0-107">Placing and Receiving Calls</span></span>

<span data-ttu-id="202d0-108">Usando o Lync, os usuários podem fazer chamadas digitando um nome ou número de telefone no teclado ou usando um teclado de discagem exibido na tela.</span><span class="sxs-lookup"><span data-stu-id="202d0-108">Using Lync, users can place calls by typing a name or phone number on their keyboard, or using a dial pad displayed on their screen.</span></span> <span data-ttu-id="202d0-109">Os usuários também podem iniciar chamadas diretamente da lista de contatos.</span><span class="sxs-lookup"><span data-stu-id="202d0-109">Users can also initiate calls directly from their Contacts list.</span></span> <span data-ttu-id="202d0-110">Você também pode implantar os dispositivos do Lync Phone Edition, que são dispositivos de telefonia IP autônomos fornecidos pelos parceiros da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="202d0-110">You can also deploy Lync Phone Edition devices, which are stand-alone IP phone devices provided by Microsoft partners.</span></span>

<span data-ttu-id="202d0-111">Os usuários podem ter vários dispositivos telefônicos registrados no Lync Server e podem alternar entre eles facilmente.</span><span class="sxs-lookup"><span data-stu-id="202d0-111">Users can have multiple phone devices registered with Lync Server, and can switch between them easily.</span></span>

<span data-ttu-id="202d0-112">Os usuários são alertados sobre chamadas de entrada em todos os seus dispositivos simultaneamente, com toques personalizáveis em dispositivos de telefone IP e uma notificação semelhante a uma mensagem de chat em seu PC.</span><span class="sxs-lookup"><span data-stu-id="202d0-112">Users are alerted to incoming calls on all their devices simultaneously, with customizable ringtones on IP phone devices and a notification similar to an instant message on their PC.</span></span>

<span data-ttu-id="202d0-113">Os usuários também podem definir um único número de telefone que se conecta ao telefone de mesa, ao PC e ao celular, para que eles possam ser acessados onde quer que estejam.</span><span class="sxs-lookup"><span data-stu-id="202d0-113">Users can also set a single telephone number that connects to their desk phone, PC and mobile phone, so they can be reached no matter where they are.</span></span>

</div>

<div>

## <a name="basic-call-features"></a><span data-ttu-id="202d0-114">Recursos de chamada básica</span><span class="sxs-lookup"><span data-stu-id="202d0-114">Basic Call Features</span></span>

<span data-ttu-id="202d0-115">Durante uma chamada, um usuário pode atender a chamadas de entrada adicionais ou iniciar chamadas feitas, e a chamada ativa existente é automaticamente colocada em espera.</span><span class="sxs-lookup"><span data-stu-id="202d0-115">While on a call, a user can answer additional incoming calls or initiate outgoing calls, and the existing active call is automatically put on hold.</span></span> <span data-ttu-id="202d0-116">As chamadas podem ser transferidas de um usuário para outro, diretamente ou após o primeiro usuário falar de forma privada com o segundo usuário.</span><span class="sxs-lookup"><span data-stu-id="202d0-116">Calls can be transferred from one user to another, either directly or after the first user speaks privately with the second user.</span></span> <span data-ttu-id="202d0-117">Os usuários também podem transferir chamadas para outro dispositivo; por exemplo, eles podem transferir uma chamada ativa para o seu celular à medida que eles orientam a porta do escritório.</span><span class="sxs-lookup"><span data-stu-id="202d0-117">Users can also transfer calls to another device; for example, they could transfer an active call to their mobile phone as they walk out the door of their office.</span></span>

</div>

<div>

## <a name="richer-communications"></a><span data-ttu-id="202d0-118">Comunicações mais sofisticadas</span><span class="sxs-lookup"><span data-stu-id="202d0-118">Richer Communications</span></span>

<span data-ttu-id="202d0-119">Ao conversar com outro usuário com o Lync, os usuários podem facilmente adicionar texto, vídeo ou compartilhamento de área de trabalho à chamada.</span><span class="sxs-lookup"><span data-stu-id="202d0-119">When talking to another user with Lync, users can easily add text, video, or desktop sharing to the call.</span></span> <span data-ttu-id="202d0-120">O recurso do-not-incomodar está integrado às configurações de presença no Lync.</span><span class="sxs-lookup"><span data-stu-id="202d0-120">The Do-Not-Disturb feature is integrated with the presence settings in Lync.</span></span>

<span data-ttu-id="202d0-121">Com o Exchange Unified Messaging (UM), o Lync e o Lync Server se integram com o Microsoft Exchange Server 2013 e o Microsoft Outlook 2013.</span><span class="sxs-lookup"><span data-stu-id="202d0-121">With Exchange Unified Messaging (UM), Lync and Lync Server integrate with Microsoft Exchange Server 2013 and Microsoft Outlook 2013.</span></span> <span data-ttu-id="202d0-122">Os usuários podem ver se têm novas mensagens de voz na janela do Lync e em email.</span><span class="sxs-lookup"><span data-stu-id="202d0-122">Users can see if they have new voice mail both in their Lync window and in email.</span></span> <span data-ttu-id="202d0-123">No email, eles podem clicar para reproduzir o áudio da caixa postal em uma mensagem de email ou exibir uma transcrição da mensagem da caixa postal.</span><span class="sxs-lookup"><span data-stu-id="202d0-123">While in email they can click to play the voice mail audio in an email message, or view a transcript of the voice mail message.</span></span>

</div>

<div>

## <a name="advanced-calling-features"></a><span data-ttu-id="202d0-124">Recursos de chamada avançados</span><span class="sxs-lookup"><span data-stu-id="202d0-124">Advanced Calling Features</span></span>

<span data-ttu-id="202d0-125">O Enterprise Voice também inclui vários recursos de chamada avançados, como a delegação de chamadas do Lync, a chamada de equipe, a retirada de chamadas em grupo e grupos de resposta.</span><span class="sxs-lookup"><span data-stu-id="202d0-125">Enterprise Voice includes several advanced calling features as well, such as Lync call delegation, team calling, Group Call Pickup, and Response Groups.</span></span>

<span data-ttu-id="202d0-126">A delegação de chamadas do Lync permite aos usuários delegar a manipulação de chamadas a um ou mais assistentes acessando **ferramentas** \> **Opções** \> **configurações**de encaminhamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="202d0-126">Lync call delegation enables users to delegate call handling to one or more assistants, by going to **Tools** \> **Options** \> **Call Forwarding Settings**.</span></span> <span data-ttu-id="202d0-127">O representante pode executar várias tarefas de chamada em nome do usuário, incluindo chamadas de filtragem, inserção de chamadas e início de conferências.</span><span class="sxs-lookup"><span data-stu-id="202d0-127">The delegate can perform multiple calling tasks on behalf of the user, including screening calls, placing calls, and initiating conferences.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="202d0-128">Você pode estar procurando outro recurso de nome semelhante, delegação de calendário do Lync.</span><span class="sxs-lookup"><span data-stu-id="202d0-128">You may be looking for another similarly named feature, Lync calendar delegation.</span></span> <span data-ttu-id="202d0-129">Ele não requer o recurso Enterprise Voice e permite que os usuários agendem reuniões online do Lync a partir do Outlook.</span><span class="sxs-lookup"><span data-stu-id="202d0-129">It doesn't require the Enterprise Voice feature and does allow users to schedule online Lync meetings from Outlook.</span></span> <span data-ttu-id="202d0-130">Se você vir aqui procurando essas informações, recomendamos o check-out <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">set-CsClientPolicy</A> para obter informações sobre como habilitar a sincronização de representante do Exchange.</span><span class="sxs-lookup"><span data-stu-id="202d0-130">If you've come here looking for that info, we recommend checking out <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A> for information on enabling Exchange delegate sync.</span></span>



</div>

<span data-ttu-id="202d0-131">O recurso de chamada de equipe permite que o usuário tenha chamadas para ligar simultaneamente para os telefones dos colegas de equipe, para que qualquer pessoa da equipe possa atender a chamada.</span><span class="sxs-lookup"><span data-stu-id="202d0-131">Team calling enables a user to have incoming calls simultaneously ring the phones of teammates so that anyone on the team can answer the call.</span></span>

<span data-ttu-id="202d0-132">Recebimento de chamadas em grupo, um novo recurso em atualizações cumulativas para o Lync Server 2013:2013 de fevereiro, permite que os usuários atendam às chamadas recebidas para seus colegas pelos próprios telefones.</span><span class="sxs-lookup"><span data-stu-id="202d0-132">Group Call Pickup, a new feature in Cumulative Updates for Lync Server 2013: February 2013, lets users answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="202d0-133">A retirada de chamadas em grupo é diferente das chamadas de equipe principalmente porque uma chamada recebida só entra no telefone do destinatário, mas qualquer outro usuário pode optar por respondê-la ao discar um número de grupo de recebimento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="202d0-133">Group Call Pickup differs from team calling primarily in that an incoming call rings only at the intended recipient's phone, but any other user can choose to answer it by dialing a call pickup group number.</span></span>

<span data-ttu-id="202d0-134">Os grupos de resposta podem ser configurados para enfileiramento e encaminhamento inteligente de chamadas para agentes designados.</span><span class="sxs-lookup"><span data-stu-id="202d0-134">Response Groups can be set up for queuing and intelligently routing calls to designated agents.</span></span> <span data-ttu-id="202d0-135">Os usos comuns incluem helpdesks de ti, diretas de recursos humanos e outros centros de contato internos.</span><span class="sxs-lookup"><span data-stu-id="202d0-135">Common uses include IT helpdesks, human resources hotlines, and other internal contact centers.</span></span>

</div>

<div>

## <a name="enterprise-voice-administration"></a><span data-ttu-id="202d0-136">Administração do Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="202d0-136">Enterprise Voice Administration</span></span>

<span data-ttu-id="202d0-137">O Lync Server usa padrões e interfaces publicadas para interoperar com a infraestrutura existente.</span><span class="sxs-lookup"><span data-stu-id="202d0-137">Lync Server uses standards and published interfaces to interoperate with existing infrastructure.</span></span> <span data-ttu-id="202d0-138">Ele é compatível com as opções de gateway e SIP (como entroncamento SIP) para interconexão com sistemas IP PBX e redes PSTN, para que você possa migrar usuários para o Enterprise Voice ao longo do tempo, enquanto minimiza as interrupções.</span><span class="sxs-lookup"><span data-stu-id="202d0-138">It supports both gateway and SIP options (such as SIP trunking) for interconnection to IP PBX systems and the PSTN networks, so that you can migrate users to Enterprise Voice over time, while minimizing disruption.</span></span> <span data-ttu-id="202d0-139">O Lync Server tem suporte para codecs tradicionais como G. 711, G. 722 e G. 723.1 para interoperabilidade com soluções tradicionais de VoIP.</span><span class="sxs-lookup"><span data-stu-id="202d0-139">Lync Server supports traditional codecs such as G.711, G.722, and G.723.1 for interoperability with traditional VoIP solutions.</span></span>

<span data-ttu-id="202d0-140">Com o controle de admissão de chamadas (CAC), os administradores podem definir limites para a quantidade de tráfego de voz e vídeo do Lync Server transportados em links de rede restritos e especificam a ação a ser tomada se uma nova chamada excedesse o limite.</span><span class="sxs-lookup"><span data-stu-id="202d0-140">With call admission control (CAC), administrators can set limits on the amount of Lync Server voice and video traffic carried on constrained network links, and specify the action to be taken if a new call would exceed the limit.</span></span> <span data-ttu-id="202d0-141">As ações podem incluir roteamento por um caminho alternativo ou recusando a chamada.</span><span class="sxs-lookup"><span data-stu-id="202d0-141">The actions could include routing by an alternate path, or refusing the call.</span></span>

<span data-ttu-id="202d0-142">O Lync Server funciona com aparelhos de ramificação externos terceirizados para fornecer serviços de chamadas locais e conexão à PSTN em filiais, em caso de falha de WAN no site central.</span><span class="sxs-lookup"><span data-stu-id="202d0-142">Lync Server works with third-party Survivable Branch Appliances to provide local calling services and connection to PSTN at branch offices, in case of WAN failure at the central site.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

