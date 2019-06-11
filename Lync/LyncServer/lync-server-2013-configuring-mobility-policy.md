---
title: 'Lync Server 2013: Configurando a política de mobilidade'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring mobility policy
ms:assetid: 595536e0-9bb3-49a3-8d13-1a77351ebc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690018(v=OCS.15)
ms:contentKeyID: 48184204
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7f71252064cef521058aba17a3c220a948e23c7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836203"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-policy-in-lync-server-2013"></a><span data-ttu-id="70084-102">Configurando a política de mobilidade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70084-102">Configuring mobility policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70084-103">_**Tópico da última modificação:** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="70084-103">_**Topic Last Modified:** 2013-02-13_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="70084-104">O Lync Server 2013 fornece políticas de mobilidade que determinam quem pode usar recursos de mobilidade, chamadas por meio de trabalho, voz sobre IP (VoIP) ou vídeo e se o WiFi será necessário para VoIP ou vídeo.</span><span class="sxs-lookup"><span data-stu-id="70084-104">Lync Server 2013 provides mobility policies that determine who can use mobility features, Call via Work, voice over IP (VoIP) or video, and whether WiFi will be required for either VoIP or video.</span></span> <span data-ttu-id="70084-105">A chamada via recurso de trabalho permite que um usuário móvel faça e receba chamadas em um celular usando um número de telefone comercial, em vez do número de telefone celular.</span><span class="sxs-lookup"><span data-stu-id="70084-105">The Call via Work feature enables a mobile user to make and receive calls on a mobile phone by using a work phone number instead of the mobile phone number.</span></span> <span data-ttu-id="70084-106">Esse recurso impede que a parte chamada Veja o número de telefone celular do chamador e permite que um usuário Evite cobranças de chamadas de saída.</span><span class="sxs-lookup"><span data-stu-id="70084-106">This feature prevents the called party from seeing the caller's mobile phone number and enables a user to avoid outbound calling charges.</span></span> <span data-ttu-id="70084-107">A configuração de VoIP e vídeo possibilita que os usuários recebam e façam chamadas e vídeos de VoIP.</span><span class="sxs-lookup"><span data-stu-id="70084-107">Configuring VoIP and video makes it possible for users to receive and make VoIP calls and video.</span></span> <span data-ttu-id="70084-108">Configurações para uso WiFi defina se o dispositivo de um usuário será necessário para usar uma rede WiFi em uma rede de dados da rede celular.</span><span class="sxs-lookup"><span data-stu-id="70084-108">Settings for WiFi usage define if a user’s device will be required to use a WiFi network over a cellular data network.</span></span>

<span data-ttu-id="70084-109">Por padrão, a mobilidade, a chamada por meio do trabalho e os recursos de vídeo e VoIP são habilitados.</span><span class="sxs-lookup"><span data-stu-id="70084-109">By default, mobility, Call via Work, and the VoIP and video features are enabled.</span></span> <span data-ttu-id="70084-110">As configurações para exigir WiFi para VoIp e vídeo estão desativadas.</span><span class="sxs-lookup"><span data-stu-id="70084-110">The settings to require WiFi for VoIp and video are disabled.</span></span> <span data-ttu-id="70084-111">Os administradores podem determinar quem tem acesso a esses recursos executando um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="70084-111">Administrators can determine who has access to these features by running a cmdlet.</span></span> <span data-ttu-id="70084-112">Você pode desativar as opções de modo global, por site ou por usuário.</span><span class="sxs-lookup"><span data-stu-id="70084-112">You can turn options off globally, by site, or by user.</span></span>

<span data-ttu-id="70084-113">Para poder usar os recursos de mobilidade e ligar pelo trabalho, os usuários devem atender aos seguintes pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="70084-113">To be able to use mobility features and Call via Work, users must meet the following prerequisites:</span></span>

  - <span data-ttu-id="70084-114">Os usuários devem ser habilitados para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="70084-114">Users must be enabled for Lync Server 2013.</span></span>

  - <span data-ttu-id="70084-115">Os usuários devem ser habilitados para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="70084-115">Users must be enabled for Enterprise Voice.</span></span>

  - <span data-ttu-id="70084-116">Os usuários devem receber uma política de mobilidade com a opção **EnableMobility** definida como true.</span><span class="sxs-lookup"><span data-stu-id="70084-116">Users must be assigned a mobility policy that has the **EnableMobility** option set to True.</span></span>

<span data-ttu-id="70084-117">Para que os usuários possam usar a chamada por meio do trabalho, eles devem atender aos dois pré-requisitos adicionais a seguir:</span><span class="sxs-lookup"><span data-stu-id="70084-117">For users to be able to use Call via Work, they must meet the following two additional prerequisites:</span></span>

  - <span data-ttu-id="70084-118">Os usuários devem receber uma política de voz com a opção **habilitar o toque simultâneo de telefones** selecionada.</span><span class="sxs-lookup"><span data-stu-id="70084-118">Users must be assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>

  - <span data-ttu-id="70084-119">Os usuários devem receber uma política de mobilidade com a opção **EnableOutsideVoice** definida como true.</span><span class="sxs-lookup"><span data-stu-id="70084-119">Users must be assigned a mobility policy that has the **EnableOutsideVoice** option set to True.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="70084-120">Os usuários que não estão habilitados para o Enterprise Voice podem usar seus dispositivos móveis para fazer chamadas do Lync para o protocolo de voz sobre IP (VoIP) ou podem participar de conferências usando o link clicar para ingressar em seus dispositivos móveis, se você atribuir a esses usuários as opções apropriadas para a política de voz.</span><span class="sxs-lookup"><span data-stu-id="70084-120">Users who are not enabled for Enterprise Voice can use their mobile devices to make Lync to Lync Voice over IP (VoIP) calls, or can join conferences by using the Click to Join link on their mobile devices, if you assign those users the appropriate options for voice policy.</span></span> <span data-ttu-id="70084-121">Para obter detalhes, consulte <A href="lync-server-2013-defining-your-mobility-requirements.md">definindo seus requisitos de mobilidade para o Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="70084-121">For details, see <A href="lync-server-2013-defining-your-mobility-requirements.md">Defining your mobility requirements for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="70084-122">Para obter detalhes sobre como habilitar usuários do Lync Server 2013, consulte [desabilitar ou habilitar novamente a conta de usuário para o Lync server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="70084-122">For details about enabling users for Lync Server 2013, see [Disable or re-enable user account for Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span></span> <span data-ttu-id="70084-123">Para obter detalhes sobre como habilitar usuários do Enterprise Voice, consulte [habilitar usuários para Enterprise Voice no Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="70084-123">For details about enabling users for Enterprise Voice, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span> <span data-ttu-id="70084-124">Para obter detalhes sobre a configuração de opções de política de voz, consulte [modificar uma política de voz e configurar registros de uso de PSTN no Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md).</span><span class="sxs-lookup"><span data-stu-id="70084-124">For details about setting voice policy options, see [Modify a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md).</span></span>

<div>

## <a name="to-modify-global-mobility-policy"></a><span data-ttu-id="70084-125">Para modificar a política de mobilidade global</span><span class="sxs-lookup"><span data-stu-id="70084-125">To modify global mobility policy</span></span>

1.  <span data-ttu-id="70084-126">Faça logon em qualquer computador em que o Shell de gerenciamento do Lync Server e o OCScore são instalados como um membro da função CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="70084-126">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="70084-127">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="70084-127">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="70084-128">Desative o acesso à mobilidade e faça chamadas por meio do trabalho global.</span><span class="sxs-lookup"><span data-stu-id="70084-128">Turn off access to mobility and Call via Work globally.</span></span> <span data-ttu-id="70084-129">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="70084-129">At the command line, type:</span></span>
    
        Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="70084-130">Você pode desativar a chamada por meio de trabalho sem desativar o acesso à mobilidade.</span><span class="sxs-lookup"><span data-stu-id="70084-130">You can turn off Call via Work without turning off access to mobility.</span></span> <span data-ttu-id="70084-131">No entanto, você não pode desativar o Mobility sem também desativar a chamada por meio do trabalho.</span><span class="sxs-lookup"><span data-stu-id="70084-131">However, you cannot turn off mobility without also turning off Call via Work.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-mobility-policy-by-site"></a><span data-ttu-id="70084-132">Para modificar a política de mobilidade por site</span><span class="sxs-lookup"><span data-stu-id="70084-132">To modify mobility policy by site</span></span>

1.  <span data-ttu-id="70084-133">Faça logon em qualquer computador em que o Shell de gerenciamento do Lync Server e o OCScore são instalados como um membro da função CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="70084-133">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="70084-134">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="70084-134">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="70084-135">Crie uma política no nível do site e desative VoIP e vídeo, e habilite exigir WiFi para áudio IP e vídeo por IP por site.</span><span class="sxs-lookup"><span data-stu-id="70084-135">Create a site-level policy, and turn off VoIP and video, and enable Require WiFi for IP Audio and for IP Video by site.</span></span> <span data-ttu-id="70084-136">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="70084-136">At the command line, type:</span></span>
    
        New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $False -RequireWiFiForIPAudio $True -RequireWiFiForIPVideo $True

</div>

<div>

## <a name="to-modify-mobility-policy-by-user"></a><span data-ttu-id="70084-137">Para modificar a política de mobilidade por usuário</span><span class="sxs-lookup"><span data-stu-id="70084-137">To modify mobility policy by user</span></span>

1.  <span data-ttu-id="70084-138">Faça logon em qualquer computador em que o Shell de gerenciamento do Lync Server e o OCScore são instalados como um membro da função CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="70084-138">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="70084-139">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="70084-139">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="70084-140">Crie políticas de mobilidade em nível de usuário e desative a mobilidade e a chamada por meio do trabalho por usuário.</span><span class="sxs-lookup"><span data-stu-id="70084-140">Create user level mobility policies and turn off mobility and Call via Work by user.</span></span> <span data-ttu-id="70084-141">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="70084-141">At the command line, type:</span></span>
    
        New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
    
    <span data-ttu-id="70084-142">Você pode desativar a chamada por meio de trabalho sem desativar o acesso à mobilidade.</span><span class="sxs-lookup"><span data-stu-id="70084-142">You can turn off Call via Work without turning off access to mobility.</span></span> <span data-ttu-id="70084-143">No entanto, você não pode desativar o Mobility sem também desativar a chamada por meio do trabalho.</span><span class="sxs-lookup"><span data-stu-id="70084-143">However, you cannot turn off mobility without also turning off Call via Work.</span></span>
    
    <span data-ttu-id="70084-144">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="70084-144">For example:</span></span>
    
        New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity -MobileUser1@contoso.com -PolicyName Tag:disableOutsideVoice

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="70084-145">Confira também</span><span class="sxs-lookup"><span data-stu-id="70084-145">See Also</span></span>


[<span data-ttu-id="70084-146">Desabilitar ou habilitar novamente a conta de usuário para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70084-146">Disable or re-enable user account for Lync Server 2013</span></span>](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[<span data-ttu-id="70084-147">Habilitar usuários para Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70084-147">Enable users for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-enterprise-voice.md)  
[<span data-ttu-id="70084-148">Modificar uma política de voz e configurar registros de uso PSTN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70084-148">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  


[<span data-ttu-id="70084-149">Definindo seus requisitos de mobilidade para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70084-149">Defining your mobility requirements for Lync Server 2013</span></span>](lync-server-2013-defining-your-mobility-requirements.md)  


[<span data-ttu-id="70084-150">New-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="70084-150">New-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)  
[<span data-ttu-id="70084-151">Set-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="70084-151">Set-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)  
[<span data-ttu-id="70084-152">Get-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="70084-152">Get-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy)  
[<span data-ttu-id="70084-153">Grant-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="70084-153">Grant-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy)  
[<span data-ttu-id="70084-154">Remove-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="70084-154">Remove-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

