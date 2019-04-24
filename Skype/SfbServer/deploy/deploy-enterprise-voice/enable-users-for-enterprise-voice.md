---
title: Habilitar usuários para o Enterprise Voice no Skype para Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
description: 'Resumo: Saiba como permitir que os usuários façam e recebam chamadas usando o Enterprise Voice no Skype para Business Server.'
ms.openlocfilehash: b02155f424e8b3f29881caf8c4a29db6f76cb807
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212471"
---
# <a name="enable-users-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="ded24-103">Habilitar usuários para o Enterprise Voice no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="ded24-103">Enable users for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="ded24-104">**Resumo:** Saiba como permitir que os usuários façam e recebam chamadas usando o Enterprise Voice no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="ded24-104">**Summary:** Learn how to enable users to make and receive calls by using Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="ded24-105">Após a implantação do Enterprise Voice ou chamada Via trabalho, você pode usar os procedimentos a seguir para habilitar um usuário fazer chamadas usando o Enterprise Voice:</span><span class="sxs-lookup"><span data-stu-id="ded24-105">After you deploy Enterprise Voice or Call Via Work, you can use the following procedures to enable a user to make calls by using Enterprise Voice:</span></span>
  
> [!NOTE]
> <span data-ttu-id="ded24-106">Dos procedimentos a seguir, somente a primeira pode ser realizada usando Skype para o painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="ded24-106">Of the following procedures, only the first can be performed by using Skype for Business Server Control Panel.</span></span> <span data-ttu-id="ded24-107">Para os demais procedimentos, você pode usar somente Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="ded24-107">For the remaining procedures, you can use only Skype for Business Server Management Shell.</span></span> 
  
- <span data-ttu-id="ded24-108">Habilite a conta de usuário para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="ded24-108">Enable the user account for Enterprise Voice.</span></span>
    
- <span data-ttu-id="ded24-109">(Opcional) Atribuir a conta de usuário com uma política de voz específica do usuário.</span><span class="sxs-lookup"><span data-stu-id="ded24-109">(Optional) Assign the user account a user-specific voice policy.</span></span>
    
- <span data-ttu-id="ded24-110">(Opcional) Atribuir a conta do usuário com um plano de discagem específico do usuário.</span><span class="sxs-lookup"><span data-stu-id="ded24-110">(Optional) Assign the user account a user-specific dial plan.</span></span>
    
### <a name="to-enable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="ded24-111">Para habilitar uma conta de usuário para o Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="ded24-111">To enable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="ded24-112">Faça logon no computador como membro do grupo **RTCUniversalServerAdmins** ou como membro da função administrativa **CsVoiceAdministrator**, **CsServerAdministrator**, ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="ded24-112">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="ded24-113">Abra o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="ded24-113">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="ded24-114">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="ded24-114">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="ded24-115">Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário que deseja habilitar e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="ded24-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="ded24-116">Na tabela, clique na conta de usuário que você deseja habilitar para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="ded24-116">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="ded24-117">No menu **Editar**, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="ded24-117">On the **Edit** menu, click **Show details**.</span></span>
    
7. <span data-ttu-id="ded24-118">Na página **Editar Skype para usuário de servidor de negócios** , em **telefonia**, clique em **Enterprise Voice**.</span><span class="sxs-lookup"><span data-stu-id="ded24-118">On the **Edit Skype for Business Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>
    
8. <span data-ttu-id="ded24-119">Clique em **URI de linha** e digite um número de telefone único e normalizado (por exemplo, tel:+14255550200).</span><span class="sxs-lookup"><span data-stu-id="ded24-119">Click **Line URI**, and then type a unique, normalized phone number (for example, tel:+14255550200).</span></span>
    
9. <span data-ttu-id="ded24-120">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="ded24-120">Click **Commit**.</span></span>
    
<span data-ttu-id="ded24-121">Para finalizar a habilitação de um usuário para o Enterprise Voice, certifique-se que o usuário é atribuído a uma política de voz e um plano de discagem, global (atribuído por padrão) ou específico do usuário. Por padrão, todos os usuários recebem uma política de voz global e plano de discagem.</span><span class="sxs-lookup"><span data-stu-id="ded24-121">To finish enabling a user for Enterprise Voice, be sure that the user is assigned a voice policy and a dial plan, whether global (assigned by default) or user-specific.By default, all users are assigned a global voice policy and dial plan.</span></span> <span data-ttu-id="ded24-122">Se um plano de discagem ou política de voz existir no nível do site para o site no qual a conta de usuário está hospedada, as políticas de site serão automaticamente aplicadas ao usuário.</span><span class="sxs-lookup"><span data-stu-id="ded24-122">If a voice policy or dial plan exists at the site level for the site on which the user account is homed, those site policies will automatically apply to the user.</span></span> <span data-ttu-id="ded24-123">Para aplicar uma política de voz por usuário ou plano a um usuário de discagem, você deve executar os cmdlets **Grant-CsVoicePolicy** e **Grant-CsDialPlan** .</span><span class="sxs-lookup"><span data-stu-id="ded24-123">To apply a per-user voice policy or dial plan to a user, you must run the **Grant-CsVoicePolicy** and **Grant-CsDialPlan** cmdlets.</span></span> <span data-ttu-id="ded24-124">Para obter detalhes, consulte os seguintes procedimentos neste tópico.</span><span class="sxs-lookup"><span data-stu-id="ded24-124">For details, see the following procedures in this topic.</span></span>
## <a name="voice-policy-assignment"></a><span data-ttu-id="ded24-125">Atribuição de política de voz</span><span class="sxs-lookup"><span data-stu-id="ded24-125">Voice Policy Assignment</span></span>

<span data-ttu-id="ded24-126">Políticas de voz global e no nível do site são automaticamente atribuídas a todas as contas de usuário que estão habilitadas para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="ded24-126">Global and site-level voice policies are automatically assigned to all user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="ded24-127">Você também pode criar políticas de voz que se aplicam a usuários ou grupos específicos.</span><span class="sxs-lookup"><span data-stu-id="ded24-127">You can also create voice policies that apply to specific users or groups.</span></span> <span data-ttu-id="ded24-128">Essas políticas por usuário devem ser explicitamente atribuídas a usuários ou grupos.</span><span class="sxs-lookup"><span data-stu-id="ded24-128">These per-user policies must be explicitly assigned to the users or groups.</span></span> <span data-ttu-id="ded24-129">Se desejar usar o modelo global ou de site de política de voz para todos os usuários habilitados para o Enterprise Voice, você pode pular esta seção e continuam a [Atribuição de plano de discagem](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) seção mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="ded24-129">If you want to use the global or site voice policy for all users who are enabled for Enterprise Voice, you can skip this section and continue to [Dial Plan Assignment](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) section later in this topic.</span></span>
  
### <a name="to-assign-a-user-specific-voice-policy"></a><span data-ttu-id="ded24-130">Para atribuir uma política de voz específica do usuário</span><span class="sxs-lookup"><span data-stu-id="ded24-130">To assign a user-specific voice policy</span></span>

1. <span data-ttu-id="ded24-131">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="ded24-131">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="ded24-132">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="ded24-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="ded24-133">Para atribuir uma política de voz de usuário existente a um usuário, execute o seguinte no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="ded24-133">To assign an existing user voice policy to a user, run the following at the command prompt:</span></span>
    
   ```
   Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="ded24-134">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="ded24-134">For example:</span></span>
    
   ```
   Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
   ```

    <span data-ttu-id="ded24-135">Neste exemplo, o usuário com o nome de exibição Bob Kelly é atribuído a política de voz com o nome **VoicePolicyJapan**.</span><span class="sxs-lookup"><span data-stu-id="ded24-135">In this example, the user with the display name Bob Kelly is assigned the voice policy with the name **VoicePolicyJapan**.</span></span>
    
## <a name="dial-plan-assignment"></a><span data-ttu-id="ded24-136">Atribuição de plano de discagem</span><span class="sxs-lookup"><span data-stu-id="ded24-136">Dial Plan Assignment</span></span>
<span data-ttu-id="ded24-137"><a name="BKMK_DialPlanAssignment"> </a></span><span class="sxs-lookup"><span data-stu-id="ded24-137"></span></span>

<span data-ttu-id="ded24-138">Para concluir a configuração da conta de usuário para usuários do Enterprise Voice ou usuários de conferência discada, o usuário deve ser atribuído um plano de discagem.</span><span class="sxs-lookup"><span data-stu-id="ded24-138">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan.</span></span> <span data-ttu-id="ded24-139">Contas de usuário usarão o plano de discagem global automaticamente ou, se houver, o plano de discagem de nível de site, quando você não atribuir explicitamente um plano de discagem por usuário existente.</span><span class="sxs-lookup"><span data-stu-id="ded24-139">User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan, when you do not explicitly assign an existing per-user dial plan.</span></span> <span data-ttu-id="ded24-140">Se você deseja usar global ou de site de plano de discagem para todos os usuários habilitados para o Enterprise Voice, você poderá ignorar esta seção.</span><span class="sxs-lookup"><span data-stu-id="ded24-140">If you want to use the global or site dial plan for all users who are enabled for Enterprise Voice, you can skip this section.</span></span>
  
### <a name="to-assign-a-user-specific-dial-plan"></a><span data-ttu-id="ded24-141">Para atribuir um plano de discagem específico do usuário</span><span class="sxs-lookup"><span data-stu-id="ded24-141">To assign a user-specific dial plan</span></span>

1. <span data-ttu-id="ded24-142">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="ded24-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="ded24-143">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="ded24-143">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="ded24-144">Para atribuir um plano de discagem específico do usuário, execute o seguinte no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="ded24-144">To assign a user-specific dial plan, run the following at the command prompt:</span></span>
    
   ```
   Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="ded24-145">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="ded24-145">For example:</span></span>
    
   ```
   Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
   ```

    <span data-ttu-id="ded24-146">Neste exemplo, o usuário com o nome de exibição Bob Kelly é atribuído o plano de discagem do usuário **chamado dialplanjapan**.</span><span class="sxs-lookup"><span data-stu-id="ded24-146">In this example, the user with the display name Bob Kelly is assigned the user dial plan with the name **DialPlanJapan**.</span></span>
    

