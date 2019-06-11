---
title: 'Lync Server 2013: Configurar política de conferência para discagem'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure conferencing policy for dial-in
ms:assetid: 9bf926d6-0248-4352-98c3-9c5a333debbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398810(v=OCS.15)
ms:contentKeyID: 48184979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74621fee97a1e6721f8772b265761b62b1b9f266
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836406"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-conferencing-policy-for-dial-in-in-lync-server-2013"></a><span data-ttu-id="13caa-102">Configurar política de conferência para discagem no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13caa-102">Configure conferencing policy for dial-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13caa-103">_**Tópico da última modificação:** 2014-03-21_</span><span class="sxs-lookup"><span data-stu-id="13caa-103">_**Topic Last Modified:** 2014-03-21_</span></span>

<span data-ttu-id="13caa-p101">A política de conferência é uma configuração de conta de usuário que especifica a experiência de conferência para os participantes. Você pode criar políticas de conferência com um escopo de site ou um escopo de usuário. As configurações de política de conferência englobam vários aspectos do agendamento da conferência e da participação. Várias configurações de política de conferência oferecem suporte à conferência discada para participantes. Ao configurar a conferência discada, você deve verificar se estes campos foram definidos adequadamente para sua organização e modificá-los conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="13caa-p101">Conferencing policy is a user account setting that specifies the conferencing experience for participants. You can create conferencing policies with a site scope or a user scope. Conferencing policy settings encompass many aspects of conference scheduling and participation. Several conferencing policy settings support dial-in conferencing for participants. When you configure dial-in conferencing, you should verify that these fields are set appropriately for your organization, and modify them as necessary.</span></span>

<span data-ttu-id="13caa-109">Verifique os seguintes campos na sua política de conferência:</span><span class="sxs-lookup"><span data-stu-id="13caa-109">Verify the following fields in your conferencing policy:</span></span>

  - <span data-ttu-id="13caa-110">**Permitir que os participantes convidem usuários**   anônimos essa configuração permite que os organizadores de reunião convidem participantes anônimos (ou seja, não autenticados) para reuniões.</span><span class="sxs-lookup"><span data-stu-id="13caa-110">**Allow participants to invite anonymous users**   This setting allows meeting organizers to invite anonymous (that is, unauthenticated) participants to meetings.</span></span> <span data-ttu-id="13caa-111">Essa configuração é opcional para conferência discada.</span><span class="sxs-lookup"><span data-stu-id="13caa-111">This setting is optional for dial-in conferencing.</span></span> <span data-ttu-id="13caa-112">Essa configuração é selecionada por padrão na política de conferência global padrão.</span><span class="sxs-lookup"><span data-stu-id="13caa-112">This setting is selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="13caa-113">**Habilitar a conferência**   discada PSTN essa configuração permite que os usuários ingressem na parte de áudio de uma conferência discando da PSTN.</span><span class="sxs-lookup"><span data-stu-id="13caa-113">**Enable PSTN dial-in conferencing**   This setting allows users to join the audio portion of a conference by dialing in from the PSTN.</span></span> <span data-ttu-id="13caa-114">Essa configuração é necessária para conferência discada.</span><span class="sxs-lookup"><span data-stu-id="13caa-114">This setting is required for dial-in conferencing.</span></span> <span data-ttu-id="13caa-115">Essa configuração é selecionada por padrão na política de conferência global padrão.</span><span class="sxs-lookup"><span data-stu-id="13caa-115">This setting is selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="13caa-116">**Permitir que participantes anônimos disquem**   essa configuração permite que usuários anônimos que já tenham ingressado na reunião disquem para um número de telefone para ingressar na parte de áudio da conferência.</span><span class="sxs-lookup"><span data-stu-id="13caa-116">**Allow anonymous participants to dial out**   This setting allows anonymous users who are already joined to the meeting to dial out to a phone number to join the audio portion of the conference.</span></span> <span data-ttu-id="13caa-117">Essa configuração é opcional para conferência discada.</span><span class="sxs-lookup"><span data-stu-id="13caa-117">This setting is optional for dial-in conferencing.</span></span> <span data-ttu-id="13caa-118">Essa configuração não é selecionada por padrão na política de conferência global padrão.</span><span class="sxs-lookup"><span data-stu-id="13caa-118">This setting is not selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="13caa-119">**Permitir que os participantes que não estão habilitados para**   o recurso de discagem para chamadas do Enterprise Voice permitam que os participantes da reunião e os organizadores não estejam habilitados para o Enterprise Voice para discar para um número de telefone para ingressar na parte de áudio da conferência.</span><span class="sxs-lookup"><span data-stu-id="13caa-119">**Allow participants not enabled for Enterprise Voice to dial out**   This setting allows meeting participants and organizers that are not enabled for Enterprise Voice to dial out to a phone number to join the audio portion of the conference.</span></span> <span data-ttu-id="13caa-120">A chamada de discagem está autorizada com base na política de voz atribuída do organizador.</span><span class="sxs-lookup"><span data-stu-id="13caa-120">The dial-out call is authorized based on the organizer’s assigned voice policy.</span></span> <span data-ttu-id="13caa-121">Essa configuração não é selecionada por padrão na política de conferência global padrão.</span><span class="sxs-lookup"><span data-stu-id="13caa-121">This setting is not selected by default in the default global conferencing policy.</span></span> <span data-ttu-id="13caa-122">A configuração do valor padrão é desabilitada.</span><span class="sxs-lookup"><span data-stu-id="13caa-122">The setting default value is disabled.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="13caa-123">Para habilitar esse recurso, o organizador da reunião que não está habilitado para o Enterprise Voice deve ter uma política de voz apropriada atribuída a ele para autorizar qualquer discagem de uma conferência organizada por esse usuário.</span><span class="sxs-lookup"><span data-stu-id="13caa-123">To enable this capability, a meeting organizer that is not enabled for Enterprise Voice should have an appropriate voice policy assigned to them to authorize any dial-out from a conference organized by that user.</span></span> <span data-ttu-id="13caa-124">Uma política de voz pode ser atribuída a um usuário que não está habilitado para o Enterprise Voice do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="13caa-124">A voice policy can be assigned to a user that is not enabled for Enterprise Voice from the Lync Server Management Shell.</span></span> <span data-ttu-id="13caa-125">Se o usuário não tiver uma política de voz explicitamente atribuída a ele, a política de voz do site será usada para autorizar a solicitação de discagem.</span><span class="sxs-lookup"><span data-stu-id="13caa-125">If the user does not have a voice policy explicitly assigned to him, the site voice policy will be used to authorize the dial-out request.</span></span> <span data-ttu-id="13caa-126">Se não houver uma política de voz do site, a política de voz global será usada.&nbsp;</span><span class="sxs-lookup"><span data-stu-id="13caa-126">If there is no site voice policy, the global voice policy will be used.&nbsp;</span></span>

    
    </div>

<span data-ttu-id="13caa-127">O procedimento nesta seção explica como modificar a política de conferência.</span><span class="sxs-lookup"><span data-stu-id="13caa-127">The procedure in this section explains how to modify conferencing policy.</span></span> <span data-ttu-id="13caa-128">Para obter detalhes sobre como configurar todas as configurações que definem a experiência do participante na política de conferência padrão, consulte [criar ou modificar uma coleção de definições de configuração de reunião no Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="13caa-128">For details about how to configure all of the settings that define the participant experience in the default conferencing policy, see [Create or modify a collection of meeting configuration settings in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span></span> <span data-ttu-id="13caa-129">Para obter detalhes sobre como criar uma política de conferência para um usuário ou grupo de usuários específico, consulte [criar ou modificar uma política de conferência no Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span><span class="sxs-lookup"><span data-stu-id="13caa-129">For details about how to create a conferencing policy for a specific user or group of users, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span></span> <span data-ttu-id="13caa-130">Para obter uma lista de todas as configurações de política de conferência disponíveis, consulte [referência de configurações de política de conferência para o Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span><span class="sxs-lookup"><span data-stu-id="13caa-130">For a list of all available conferencing policy settings, see [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>

## <a name="to-modify-the-conferencing-policy-for-dial-in"></a><span data-ttu-id="13caa-131">Para modificar a política de conferência para discagem</span><span class="sxs-lookup"><span data-stu-id="13caa-131">To modify the conferencing policy for dial-in</span></span>

1.  <span data-ttu-id="13caa-132">Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função **cs-ServerAdministrator** ou **CsAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="13caa-132">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="13caa-133">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="13caa-133">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="13caa-134">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="13caa-134">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="13caa-135">Na barra de navegação esquerda, clique em **Conferência**.</span><span class="sxs-lookup"><span data-stu-id="13caa-135">In the left navigation bar, click **Conferencing**.</span></span>

4.  <span data-ttu-id="13caa-136">Na guia **política de conferência** , clique duas vezes em um nome de política de conferência para abrir a caixa de diálogo **Editar política de conferência** .</span><span class="sxs-lookup"><span data-stu-id="13caa-136">On the **Conferencing Policy** tab, double-click a conferencing policy name to open the **Edit Conferencing Policy** dialog box.</span></span>

5.  <span data-ttu-id="13caa-137">Verifique se os campos para conferência discada são adequados para sua organização e modifique as configurações, se necessário.</span><span class="sxs-lookup"><span data-stu-id="13caa-137">Verify that the fields for dial-in conferencing are appropriate for your organization, and modify the settings if necessary.</span></span>

6.  <span data-ttu-id="13caa-138">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="13caa-138">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

