---
title: 'Lync Server 2013: habilitar usuários do Enterprise Voice'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable users for Enterprise Voice
ms:assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413011(v=OCS.15)
ms:contentKeyID: 48185800
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d94b2ad348bc1d086716deed2beef0dcfbe78e2b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829285"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="b5252-102">Habilitar usuários para Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5252-102">Enable users for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5252-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="b5252-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="b5252-104">Depois de instalar arquivos para um ou mais servidores de mediação, configurar o roteamento de chamadas de saída e, opcionalmente, implantar um ou mais recursos avançados do Enterprise Voice, você pode usar os seguintes procedimentos para permitir que um usuário faça chamadas usando o Enterprise Voice:</span><span class="sxs-lookup"><span data-stu-id="b5252-104">After you install files for one or more Mediation Servers, configure outbound call routing, and optionally deploy one or more advanced Enterprise Voice features, you can use the following procedures to enable a user to make calls by using Enterprise Voice:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b5252-105">Dos procedimentos a seguir, somente o primeiro pode ser executado usando o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b5252-105">Of the following procedures, only the first can be performed by using Lync Server Control Panel.</span></span> <span data-ttu-id="b5252-106">Para obter os procedimentos restantes, você pode usar apenas o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b5252-106">For the remaining procedures, you can use only Lync Server Management Shell.</span></span>



</div>

  - <span data-ttu-id="b5252-107">Habilite a conta de usuário do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="b5252-107">Enable the user account for Enterprise Voice.</span></span>

  - <span data-ttu-id="b5252-108">(Opcional) Atribuir a conta de usuário com uma política de voz específica do usuário.</span><span class="sxs-lookup"><span data-stu-id="b5252-108">(Optional) Assign the user account a user-specific voice policy.</span></span>

  - <span data-ttu-id="b5252-109">(Opcional) Atribuir a conta do usuário com um plano de discagem específico do usuário.</span><span class="sxs-lookup"><span data-stu-id="b5252-109">(Optional) Assign the user account a user-specific dial plan.</span></span>

<div>

## <a name="to-enable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="b5252-110">Para habilitar uma conta de usuário para o Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="b5252-110">To enable a user account for Enterprise Voice</span></span>

1.  <span data-ttu-id="b5252-111">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="b5252-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b5252-112">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b5252-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b5252-113">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b5252-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b5252-114">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="b5252-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="b5252-115">Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário que deseja habilitar e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="b5252-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="b5252-116">Na tabela, clique na conta de usuário que você deseja habilitar para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="b5252-116">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6.  <span data-ttu-id="b5252-117">No menu **Editar**, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="b5252-117">On the **Edit** menu, click **Show details**.</span></span>

7.  <span data-ttu-id="b5252-118">Na página **Editar usuário do Lync Server** , em **telefonia**, clique em **Enterprise Voice**.</span><span class="sxs-lookup"><span data-stu-id="b5252-118">On the **Edit Lync Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>

8.  <span data-ttu-id="b5252-119">Clique em **URI de linha** e digite um número de telefone único e normalizado (por exemplo, tel:+14255550200).</span><span class="sxs-lookup"><span data-stu-id="b5252-119">Click **Line URI**, and then type a unique, normalized phone number (for example, tel:+14255550200).</span></span>

9.  <span data-ttu-id="b5252-120">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="b5252-120">Click **Commit**.</span></span>

<span data-ttu-id="b5252-121">Para concluir a habilitação de um usuário para o Enterprise Voice, certifique-se de que o usuário tenha atribuído uma política de voz e um plano de discagem, seja global (atribuído por padrão) ou específico ao usuário.</span><span class="sxs-lookup"><span data-stu-id="b5252-121">To finish enabling a user for Enterprise Voice, be sure that the user is assigned a voice policy and a dial plan, whether global (assigned by default) or user-specific.</span></span>

<span data-ttu-id="b5252-122">Por padrão, todos os usuários recebem uma política de voz global e um plano de discagem.</span><span class="sxs-lookup"><span data-stu-id="b5252-122">By default, all users are assigned a global voice policy and dial plan.</span></span> <span data-ttu-id="b5252-123">Se houver uma política de voz ou um plano de discagem no nível do site no qual a conta de usuário é hospedada, essas políticas do site serão aplicadas automaticamente ao usuário.</span><span class="sxs-lookup"><span data-stu-id="b5252-123">If a voice policy or dial plan exists at the site level for the site on which the user account is homed, those site policies will automatically apply to the user.</span></span> <span data-ttu-id="b5252-124">Para aplicar uma política de voz por usuário ou um plano de discagem a um usuário, você deve executar os cmdlets **Grant-CsVoicePolicy** e **Grant-CsDialPlan** .</span><span class="sxs-lookup"><span data-stu-id="b5252-124">To apply a per-user voice policy or dial plan to a user, you must run the **Grant-CsVoicePolicy** and **Grant-CsDialPlan** cmdlets.</span></span> <span data-ttu-id="b5252-125">Para obter detalhes, consulte a documentação do [Shell de gerenciamento do Lync Server 2013](lync-server-2013-lync-server-management-shell.md) .</span><span class="sxs-lookup"><span data-stu-id="b5252-125">For details, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

<div>

## <a name="voice-policy-assignment"></a><span data-ttu-id="b5252-126">Atribuição de política de voz</span><span class="sxs-lookup"><span data-stu-id="b5252-126">Voice Policy Assignment</span></span>

<span data-ttu-id="b5252-127">Políticas de voz globais e no nível do site são automaticamente atribuídas a todas as contas de usuário habilitadas para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="b5252-127">Global and site-level voice policies are automatically assigned to all user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="b5252-128">Você também pode criar políticas de voz que se aplicam a usuários ou grupos específicos.</span><span class="sxs-lookup"><span data-stu-id="b5252-128">You can also create voice policies that apply to specific users or groups.</span></span> <span data-ttu-id="b5252-129">Essas políticas por usuário devem ser explicitamente atribuídas aos usuários ou grupos.</span><span class="sxs-lookup"><span data-stu-id="b5252-129">These per-user policies must be explicitly assigned to the users or groups.</span></span> <span data-ttu-id="b5252-130">Se quiser usar a política de voz global ou de site para todos os usuários habilitados para o Enterprise Voice, você poderá ignorar esta seção e continuar a discagem da seção de atribuição de plano posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="b5252-130">If you want to use the global or site voice policy for all users who are enabled for Enterprise Voice, you can skip this section and continue to Dial Plan Assignment section later in this topic.</span></span>

<div>

## <a name="to-assign-a-user-specific-voice-policy"></a><span data-ttu-id="b5252-131">Para atribuir uma política de voz específica do usuário</span><span class="sxs-lookup"><span data-stu-id="b5252-131">To assign a user-specific voice policy</span></span>

1.  <span data-ttu-id="b5252-132">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="b5252-132">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b5252-133">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b5252-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="b5252-134">Para atribuir uma política de voz de usuário existente a um usuário, execute o seguinte no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="b5252-134">To assign an existing user voice policy to a user, run the following at the command prompt:</span></span>
    
        Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
    
    <span data-ttu-id="b5252-135">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="b5252-135">For example:</span></span>
    
        Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
    
    <span data-ttu-id="b5252-136">Neste exemplo, o usuário com o nome para exibição Bob está atribuído à política de voz com o nome **VoicePolicyJapan**.</span><span class="sxs-lookup"><span data-stu-id="b5252-136">In this example, the user with the display name Bob Kelly is assigned the voice policy with the name **VoicePolicyJapan**.</span></span>

<span data-ttu-id="b5252-137">Para obter detalhes sobre como atribuir uma política de voz específica do usuário ou sobre como executar o cmdlet **Grant-CsVoicePolicy** , consulte a documentação do [Shell de gerenciamento do Lync Server 2013](lync-server-2013-lync-server-management-shell.md) .</span><span class="sxs-lookup"><span data-stu-id="b5252-137">For details about assigning a user-specific voice policy or about running the **Grant-CsVoicePolicy** cmdlet, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

</div>

<span id="BKMK_DialPlanAssignment"></span>

<div>

## <a name="dial-plan-assignment"></a><span data-ttu-id="b5252-138">Atribuição de plano de discagem</span><span class="sxs-lookup"><span data-stu-id="b5252-138">Dial Plan Assignment</span></span>

<span data-ttu-id="b5252-139">Para concluir a configuração da conta de usuário para usuários do Enterprise Voice ou usuários de conferências discadas, o usuário deve receber um plano de discagem.</span><span class="sxs-lookup"><span data-stu-id="b5252-139">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan.</span></span> <span data-ttu-id="b5252-140">As contas de usuário usarão automaticamente o plano de discagem global ou, se houver, o plano de discagem no nível do site, quando você não atribui explicitamente um plano de discagem por usuário existente.</span><span class="sxs-lookup"><span data-stu-id="b5252-140">User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan, when you do not explicitly assign an existing per-user dial plan.</span></span> <span data-ttu-id="b5252-141">Se quiser usar o plano global ou de discagem de site para todos os usuários que estão habilitados para o Enterprise Voice, você pode ignorar esta seção.</span><span class="sxs-lookup"><span data-stu-id="b5252-141">If you want to use the global or site dial plan for all users who are enabled for Enterprise Voice, you can skip this section.</span></span>

<div>

## <a name="to-assign-a-dial-plan"></a><span data-ttu-id="b5252-142">Para atribuir um plano de discagem</span><span class="sxs-lookup"><span data-stu-id="b5252-142">To assign a dial plan</span></span>

1.  <span data-ttu-id="b5252-143">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="b5252-143">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b5252-144">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b5252-144">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="b5252-145">Para atribuir um plano de discagem específico do usuário, execute o seguinte no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="b5252-145">To assign a user-specific dial plan, run the following at the command prompt:</span></span>
    
        Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
    
    <span data-ttu-id="b5252-146">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="b5252-146">For example:</span></span>
    
        Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
    
    <span data-ttu-id="b5252-147">Neste exemplo, o usuário com o nome para exibição Bob está atribuído ao plano de discagem do usuário com o nome **DialPlanJapan**.</span><span class="sxs-lookup"><span data-stu-id="b5252-147">In this example, the user with the display name Bob Kelly is assigned the user dial plan with the name **DialPlanJapan**.</span></span>

<span data-ttu-id="b5252-148">Para obter detalhes sobre como atribuir um plano de discagem do usuário ou sobre como executar o cmdlet **Grant-CsDialPlan** , consulte a documentação do [Shell de gerenciamento do Lync Server 2013](lync-server-2013-lync-server-management-shell.md) .</span><span class="sxs-lookup"><span data-stu-id="b5252-148">For details about assigning a user dial plan or about running the **Grant-CsDialPlan** cmdlet, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b5252-149">Confira também</span><span class="sxs-lookup"><span data-stu-id="b5252-149">See Also</span></span>


[<span data-ttu-id="b5252-150">Desabilitar um usuário para o Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5252-150">Disable a user for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-disable-a-user-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

