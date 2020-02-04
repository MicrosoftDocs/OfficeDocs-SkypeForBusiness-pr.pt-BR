---
title: Visão geral da conferência discada do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing overview
ms:assetid: 6e581cef-960a-4730-8b22-91b2129d34e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398524(v=OCS.15)
ms:contentKeyID: 48184436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a126e7e1ee61f48ff8857553b7677abf813a25e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762289"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="a8e03-102">Visão geral da conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8e03-102">Overview of dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8e03-103">_**Tópico da última modificação:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="a8e03-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="a8e03-104">Se a sua organização tiver usuários que precisem participar de conferências locais do Lync Server 2013 quando estiverem fora do escritório ou não tiverem acesso a um computador, você poderá implantar a conferência discada para que ela possa participar da conferência usando um telefone comutado público telefone de rede (PSTN).</span><span class="sxs-lookup"><span data-stu-id="a8e03-104">If your organization has users who need to attend Lync Server 2013 on-premises conferences when they are out of the office or do not have access to a computer, you can deploy dial-in conferencing so that they can join the conference by using a public switched telephone network (PSTN) phone.</span></span>

<span data-ttu-id="a8e03-105">A conferência discada é um recurso opcional que você pode configurar ao implantar a conferência do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a8e03-105">Dial-in conferencing is an optional feature that you can configure when you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="a8e03-106">Embora a conferência discada use alguns dos mesmos componentes do Lync Server 2013 que o Enterprise Voice usa, você pode implantar a conferência discada mesmo se não implantar o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="a8e03-106">Although dial-in conferencing uses some of the same Lync Server 2013 components that Enterprise Voice uses, you can deploy dial-in conferencing even if you do not deploy Enterprise Voice.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a8e03-107">Se você implantar a conferência discada, será necessário implantá-la em cada pool onde implantar a conferência do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a8e03-107">If you deploy dial-in conferencing, you must deploy it in every pool where you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="a8e03-108">Você não precisa atribuir números de acesso em cada pool, mas você deve implantar o recurso de discagem em cada pool.</span><span class="sxs-lookup"><span data-stu-id="a8e03-108">You do not need to assign access numbers in every pool, but you must deploy the dial-in feature in every pool.</span></span> <span data-ttu-id="a8e03-109">Esse requisito dá suporte ao recurso de nome registrado quando um usuário chama um número de acesso de um pool para ingressar em uma conferência do Lync Server 2013 em um pool diferente.</span><span class="sxs-lookup"><span data-stu-id="a8e03-109">This requirement supports the recorded name feature when a user calls an access number from one pool to join a Lync Server 2013 conference in a different pool.</span></span>



</div>

<span data-ttu-id="a8e03-110">As conferências devem estar habilitadas para acesso de discagem na política de reunião.</span><span class="sxs-lookup"><span data-stu-id="a8e03-110">Conferences must be enabled for dial-in access in meeting policy.</span></span> <span data-ttu-id="a8e03-111">Por padrão, as conferências que estão ativadas para o acesso de discagem incluem as seguintes informações na solicitação de conferência:</span><span class="sxs-lookup"><span data-stu-id="a8e03-111">By default, conferences that are enabled for dial-in access include the following information in the conference invitation:</span></span>

  - <span data-ttu-id="a8e03-112">Uma ID de conferência numérica que identifica a conferência.</span><span class="sxs-lookup"><span data-stu-id="a8e03-112">A numeric conference ID that identifies the conference.</span></span>

  - <span data-ttu-id="a8e03-113">Um ou mais números de acesso PSTN.</span><span class="sxs-lookup"><span data-stu-id="a8e03-113">One or more PSTN access numbers.</span></span>

  - <span data-ttu-id="a8e03-114">Um link para uma página de configurações de conferência discada, que contém uma lista completa de números de acesso com seus idiomas associados; um local para criar, redefinir ou desbloquear números de identificação pessoal (PINs); e outras informações, como controles DTMF (Multifrequency Multi-Frequency) de Tom duplo.</span><span class="sxs-lookup"><span data-stu-id="a8e03-114">A link to a Dial-in Conferencing Settings page, which contains a complete list of access numbers with their associated languages; a place to create, reset, or unblock personal identification numbers (PINs); and other information, such as dual-tone multi-frequency (DTMF) controls.</span></span>

<span data-ttu-id="a8e03-115">A conferência discada é compatível com usuários corporativos e anônimos.</span><span class="sxs-lookup"><span data-stu-id="a8e03-115">Dial-in conferencing supports both enterprise and anonymous users.</span></span> <span data-ttu-id="a8e03-116">Os usuários empresariais têm as credenciais dos serviços de domínio Active Directory e do Lync Server 2013 em sua organização.</span><span class="sxs-lookup"><span data-stu-id="a8e03-116">Enterprise users have Active Directory Domain Services credentials and Lync Server 2013 accounts within their organization.</span></span> <span data-ttu-id="a8e03-117">Os usuários anônimos não têm credenciais da empresa dentro de sua organização.</span><span class="sxs-lookup"><span data-stu-id="a8e03-117">Anonymous users do not have enterprise credentials within your organization.</span></span> <span data-ttu-id="a8e03-118">No contexto de conferência de discagem, um usuário em uma organização de um parceiro federado que usa o PSTN para se conectar a uma conferência é tratado como usuário anônimo.</span><span class="sxs-lookup"><span data-stu-id="a8e03-118">In the dial-in conferencing context, a user in a federated partner’s organization who uses the PSTN to connect to a conference is treated like an anonymous user.</span></span> <span data-ttu-id="a8e03-119">Diferentemente de em outros contextos, para a conferência discagem os usuários federados não são autenticados.</span><span class="sxs-lookup"><span data-stu-id="a8e03-119">For dial-in conferencing, unlike other contexts, federated users are not authenticated.</span></span>

<span data-ttu-id="a8e03-p105">Os usuários corporativos ou líderes de conferência que ingressam em uma conferência estão habilitados para o acesso de discagem discam um dos números de acesso de conferência e, em seguida, são solicitados a inserir o ID de conferência. Se um líder ainda não ingressou na reunião, os usuários podem digitar a sua extensão de comunicações unificadas (UC) (ou número de telefone completo) e PIN ou aguardar para ser admitidos pelo líder. Os organizadores de reuniões podem ingressar na reunião como líderes apenas digitando o seu PIN. O Servidor de Front-End usa a combinação do número completo ou extensão de telefone e o PIN, para mapear exclusivamente os usuários corporativos para as credenciais do Active Directory. Como resultado, os usuários corporativos são autenticados e identificados pelo nome da conferência. Os usuários corporativos também podem assumir um papel de conferência predefinido pelo organizador.</span><span class="sxs-lookup"><span data-stu-id="a8e03-p105">Enterprise users or conference leaders who join a conference that is enabled for dial-in access dial one of the conference access numbers and then are prompted to enter the conference ID. If a leader has not yet joined the meeting, users can either enter their unified communications (UC) extension (or full phone number) and PIN or wait to be admitted by a leader. The Meeting organizer can join the meeting as a leader by entering just their PIN. The Front End Server uses the combination of full phone number or extension, and PIN, to uniquely map enterprise users to their Active Directory credentials. As a result, enterprise users are authenticated and identified by name in the conference. Enterprise users can also assume a conference role predefined by the organizer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a8e03-126">Os usuários da empresa que discam de um telefone IP do Office ou do Lync Server 2013 ou Lync 2010 Attendant não são solicitados para seu número de telefone porque já estão autenticados.</span><span class="sxs-lookup"><span data-stu-id="a8e03-126">Enterprise users who dial in from an office IP phone or from Lync Server 2013 or Lync 2010 Attendant are not prompted for their phone number because they are already authenticated.</span></span>



</div>

<span data-ttu-id="a8e03-p106">Os usuários anônimos que desejem ingressar em uma conferência de discagem discam um dos números de acesso de conferência e, em seguida, são solicitado a inserir o ID de conferência. Os usuários anônimos não autenticados também têm que registrar o seu nome. O nome gravado identifica os usuários não autenticados na conferência. Os usuários anônimos não são admitidos na conferência até que pelo menos um líder ou usuário autenticado ingresse e não é possível atribuir uma função predefinida.</span><span class="sxs-lookup"><span data-stu-id="a8e03-p106">Anonymous users who want to join a dial-in conference dial one of the conference access numbers and then they are prompted to enter the conference ID. Unauthenticated anonymous users are also prompted to record their name. The recorded name identifies unauthenticated users in the conference. Anonymous users are not admitted to the conference until at least one leader or authenticated user has joined, and they cannot be assigned a predefined role.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a8e03-p107">Os usuários corporativos que optam por não inserir o número de telefone e o PIN não são autenticados. Eles serão solicitados a registrar seu nome e são tratados como usuários anônimos na conferência.</span><span class="sxs-lookup"><span data-stu-id="a8e03-p107">Enterprise users who choose not to enter their phone number and PIN are not authenticated. They are prompted to record their name and are treated as anonymous users in the conference.</span></span>



</div>

<span data-ttu-id="a8e03-133">No momento do cronograma, o organizador da reunião pode optar por restringir o acesso à reunião fazendo com que a reunião seja fechada ou bloqueada.</span><span class="sxs-lookup"><span data-stu-id="a8e03-133">At schedule time, the meeting organizer can choose to restrict access to the meeting by making the meeting closed or locked.</span></span> <span data-ttu-id="a8e03-134">Nesse caso, os usuários de discagem devem ser autenticados.</span><span class="sxs-lookup"><span data-stu-id="a8e03-134">In this case, dial-in users are requested to authenticate.</span></span> <span data-ttu-id="a8e03-135">Se os usuários de discagem falharem ou optarem por não autenticar, eles serão transferidos para o lobby.</span><span class="sxs-lookup"><span data-stu-id="a8e03-135">If dial-in users fail or choose not to authenticate, they are transferred to the lobby.</span></span> <span data-ttu-id="a8e03-136">Elas esperam no lobby até que um líder a aceite ou rejeite, ou que o tempo limite e seja desconectado.</span><span class="sxs-lookup"><span data-stu-id="a8e03-136">They wait in the lobby until a leader accepts or rejects them, or they time out and are disconnected.</span></span> <span data-ttu-id="a8e03-137">Os usuários de discagem ouvirão música se estiverem aguardando para serem admitidos na conferência.</span><span class="sxs-lookup"><span data-stu-id="a8e03-137">Dial-in users hear music if they are waiting to be admitted to the conference.</span></span> <span data-ttu-id="a8e03-138">Depois de serem admitidos em uma conferência, os usuários de discagem podem participar do áudio da conferência e executar comandos de multifrequência de tom dual (DTMF) com o teclado do telefone.</span><span class="sxs-lookup"><span data-stu-id="a8e03-138">After they are admitted to a conference, dial-in users can participate in the audio portion of the conference and can exercise dual-tone multi-frequency (DTMF) commands by using the phone keypad.</span></span> <span data-ttu-id="a8e03-139">Líderes de discagem podem executar comandos DTMF para ativar ou desativar a capacidade dos participantes de desativar Mudo, bloquear ou desbloquear a conferência, admitir pessoas do lobby e ativar ou desativar os anúncios de entrada/saída.</span><span class="sxs-lookup"><span data-stu-id="a8e03-139">Dial-in leaders can exercise DTMF commands to turn participants' ability to unmute on or off, lock or unlock the conference, admit people from the lobby, and turn entry and exit announcements on or off.</span></span> <span data-ttu-id="a8e03-140">Os líderes também podem usar um comando DTMF para admitir todos do lobby, o que altera as permissões de reunião para permitir qualquer um que participe depois.</span><span class="sxs-lookup"><span data-stu-id="a8e03-140">Leaders can also use a DTMF command to admit everyone from the lobby, which changes the permissions of the meeting to allow anyone who subsequently joins.</span></span> <span data-ttu-id="a8e03-141">Todos os participantes de discagem podem executar comandos DTMF par ouvir a Ajuda, ouvir os participantes da conferência e ativar Mudo para si próprios.</span><span class="sxs-lookup"><span data-stu-id="a8e03-141">All dial-in participants can exercise DTMF commands to hear Help, listen to the conference roster, and mute themselves.</span></span>

<span data-ttu-id="a8e03-142">Participantes de discagem (ou seja, se eles discarem da PSTN), ouvirão comunicados pessoais durante a conferência, como se estivessem com mudo ativado ou mudo, se a reunião está sendo gravada ou se alguém está aguardando no lobby.</span><span class="sxs-lookup"><span data-stu-id="a8e03-142">Dial-in participants (that is, whether or not they dial from the PSTN), hear personal announcements during the conference, such as whether they have been muted or unmuted, the meeting is being recorded, or someone is waiting in the lobby.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a8e03-143">Os participantes que ingressam na conferência clicando em um link, em vez de discando, não ouvem os comunicados pessoais.</span><span class="sxs-lookup"><span data-stu-id="a8e03-143">Participants who join the conference by clicking a link instead of dialing in do not hear personal announcements.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

