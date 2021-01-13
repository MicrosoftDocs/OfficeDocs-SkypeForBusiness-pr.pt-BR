---
title: Habilitar usuários para o Enterprise Voice no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
description: 'Resumo: saiba como permitir que os usuários façam e recebam chamadas usando o Enterprise Voice no Skype for Business Server.'
ms.openlocfilehash: 3c18836f1c2b03d2c6d50712f33d9e3a900b43b3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830871"
---
# <a name="enable-users-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="9fe9e-103">Habilitar usuários para o Enterprise Voice no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9fe9e-103">Enable users for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="9fe9e-104">**Resumo:** Saiba como permitir que os usuários façam e recebam chamadas usando o Enterprise Voice no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9fe9e-104">**Summary:** Learn how to enable users to make and receive calls by using Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="9fe9e-105">Depois de implantar o Enterprise Voice ou o Call Via Work, você pode usar os procedimentos a seguir para permitir que um usuário faça chamadas usando o Enterprise Voice:</span><span class="sxs-lookup"><span data-stu-id="9fe9e-105">After you deploy Enterprise Voice or Call Via Work, you can use the following procedures to enable a user to make calls by using Enterprise Voice:</span></span>
  
> [!NOTE]
> <span data-ttu-id="9fe9e-106">Dos procedimentos a seguir, somente o primeiro pode ser realizado usando o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9fe9e-106">Of the following procedures, only the first can be performed by using Skype for Business Server Control Panel.</span></span> <span data-ttu-id="9fe9e-107">Para os demais procedimentos, você pode usar apenas o Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9fe9e-107">For the remaining procedures, you can use only Skype for Business Server Management Shell.</span></span> 
  
- <span data-ttu-id="9fe9e-108">Habilita a conta de usuário para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="9fe9e-108">Enable the user account for Enterprise Voice.</span></span>
    
- <span data-ttu-id="9fe9e-109">(Opcional) Atribuir a conta de usuário com uma política de voz específica do usuário.</span><span class="sxs-lookup"><span data-stu-id="9fe9e-109">(Optional) Assign the user account a user-specific voice policy.</span></span>
    
- <span data-ttu-id="9fe9e-110">(Opcional) Atribuir a conta do usuário com um plano de discagem específico do usuário.</span><span class="sxs-lookup"><span data-stu-id="9fe9e-110">(Optional) Assign the user account a user-specific dial plan.</span></span>
    
### <a name="to-enable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="9fe9e-111">Para habilitar uma conta de usuário para o Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="9fe9e-111">To enable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="9fe9e-112">Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função administrativa **CsVoiceAdministrator**, **CsServerAdministrator** ou **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="9fe9e-112">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="9fe9e-113">Abra o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9fe9e-113">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="9fe9e-114">Na barra de navegação à esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="9fe9e-114">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="9fe9e-115">Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário que deseja habilitar e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="9fe9e-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="9fe9e-116">Na tabela, clique na conta de usuário que você deseja habilitar para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="9fe9e-116">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="9fe9e-117">No painel **Ações**, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="9fe9e-117">On the **Edit** menu, click **Show details**.</span></span>
    
7. <span data-ttu-id="9fe9e-118">Na página **Editar Usuário do Skype for Business Server,** em **Telefonia,** clique em **Enterprise Voice.**</span><span class="sxs-lookup"><span data-stu-id="9fe9e-118">On the **Edit Skype for Business Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>
    
8. <span data-ttu-id="9fe9e-119">Clique em **URI de linha** e digite um número de telefone único e normalizado (por exemplo, tel:+14255550200).</span><span class="sxs-lookup"><span data-stu-id="9fe9e-119">Click **Line URI**, and then type a unique, normalized phone number (for example, tel:+14255550200).</span></span>
    
9. <span data-ttu-id="9fe9e-120">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="9fe9e-120">Click **Commit**.</span></span>
    
<span data-ttu-id="9fe9e-121">Para concluir a habilitação de um usuário para o Enterprise Voice, certifique-se de que o usuário recebe uma política de voz e um plano de discagem, sejam globais (atribuídos por padrão) ou específicos do usuário. Por padrão, todos os usuários são atribuídos com uma política de voz global e um plano de discagem.</span><span class="sxs-lookup"><span data-stu-id="9fe9e-121">To finish enabling a user for Enterprise Voice, be sure that the user is assigned a voice policy and a dial plan, whether global (assigned by default) or user-specific.By default, all users are assigned a global voice policy and dial plan.</span></span> <span data-ttu-id="9fe9e-122">Se uma política de voz ou plano de discagem existe no nível do site para o site na qual a conta do usuário está hospedada, estas políticas de site serão aplicadas automaticamente ao usuário.</span><span class="sxs-lookup"><span data-stu-id="9fe9e-122">If a voice policy or dial plan exists at the site level for the site on which the user account is homed, those site policies will automatically apply to the user.</span></span> <span data-ttu-id="9fe9e-123">Para aplicar uma política de voz por usuário ou plano de discagem para um usuário, você deve executar os cmdlets **Grant-CsVoicePolicy** e **Grant-CsDialPlan**.</span><span class="sxs-lookup"><span data-stu-id="9fe9e-123">To apply a per-user voice policy or dial plan to a user, you must run the **Grant-CsVoicePolicy** and **Grant-CsDialPlan** cmdlets.</span></span> <span data-ttu-id="9fe9e-124">Para obter detalhes, consulte os procedimentos a seguir neste tópico.</span><span class="sxs-lookup"><span data-stu-id="9fe9e-124">For details, see the following procedures in this topic.</span></span>
## <a name="voice-policy-assignment"></a><span data-ttu-id="9fe9e-125">Atribuição da política de voz</span><span class="sxs-lookup"><span data-stu-id="9fe9e-125">Voice Policy Assignment</span></span>

<span data-ttu-id="9fe9e-126">As políticas de voz globais e de nível de site são atribuídas automaticamente a todas as contas de usuário habilitadas para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="9fe9e-126">Global and site-level voice policies are automatically assigned to all user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="9fe9e-127">Também é possível criar políticas de voz que são aplicadas a usuários ou grupos específicos.</span><span class="sxs-lookup"><span data-stu-id="9fe9e-127">You can also create voice policies that apply to specific users or groups.</span></span> <span data-ttu-id="9fe9e-128">Estas políticas por usuário devem ser atribuídas explicitamente aos usuários ou grupos.</span><span class="sxs-lookup"><span data-stu-id="9fe9e-128">These per-user policies must be explicitly assigned to the users or groups.</span></span> <span data-ttu-id="9fe9e-129">Se você quiser usar a política de voz global ou de site para todos os [](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) usuários habilitados para o Enterprise Voice, poderá ignorar esta seção e continuar para a seção Atribuição de Plano de Discagem posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="9fe9e-129">If you want to use the global or site voice policy for all users who are enabled for Enterprise Voice, you can skip this section and continue to [Dial Plan Assignment](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) section later in this topic.</span></span>
  
### <a name="to-assign-a-user-specific-voice-policy"></a><span data-ttu-id="9fe9e-130">Para atribuir uma política de voz específica do usuário</span><span class="sxs-lookup"><span data-stu-id="9fe9e-130">To assign a user-specific voice policy</span></span>

1. <span data-ttu-id="9fe9e-131">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="9fe9e-131">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="9fe9e-132">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="9fe9e-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="9fe9e-133">Para atribuir uma política de voz do usuário existente para um usuário, execute o seguinte no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="9fe9e-133">To assign an existing user voice policy to a user, run the following at the command prompt:</span></span>
    
   ```powershell
   Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="9fe9e-134">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9fe9e-134">For example:</span></span>
    
   ```powershell
   Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
   ```

    <span data-ttu-id="9fe9e-135">Neste exemplo, o usuário com o nome de exibição Bob Kelly recebe a política de voz com o nome **VoicePolicyJapan**.</span><span class="sxs-lookup"><span data-stu-id="9fe9e-135">In this example, the user with the display name Bob Kelly is assigned the voice policy with the name **VoicePolicyJapan**.</span></span>
    
## <a name="dial-plan-assignment"></a><span data-ttu-id="9fe9e-136">Atribuição do plano de discagem</span><span class="sxs-lookup"><span data-stu-id="9fe9e-136">Dial Plan Assignment</span></span>
<span data-ttu-id="9fe9e-137"><a name="BKMK_DialPlanAssignment"> </a></span><span class="sxs-lookup"><span data-stu-id="9fe9e-137"><a name="BKMK_DialPlanAssignment"> </a></span></span>

<span data-ttu-id="9fe9e-138">Para concluir a configuração da conta de usuário para usuários do Enterprise Voice ou usuários de conferência discada, o usuário deve ter um plano de discagem atribuído.</span><span class="sxs-lookup"><span data-stu-id="9fe9e-138">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan.</span></span> <span data-ttu-id="9fe9e-139">As contas do usuário usarão automaticamente o plano de discagem global ou, se existir, o plano de discagem a nível do site quando você não atribuir explicitamente um plano de discagem por usuário existente.</span><span class="sxs-lookup"><span data-stu-id="9fe9e-139">User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan, when you do not explicitly assign an existing per-user dial plan.</span></span> <span data-ttu-id="9fe9e-140">Se você quiser usar o plano de discagem global ou de site para todos os usuários habilitados para o Enterprise Voice, ignore esta seção.</span><span class="sxs-lookup"><span data-stu-id="9fe9e-140">If you want to use the global or site dial plan for all users who are enabled for Enterprise Voice, you can skip this section.</span></span>
  
### <a name="to-assign-a-user-specific-dial-plan"></a><span data-ttu-id="9fe9e-141">Para atribuir um plano de discagem específico do usuário</span><span class="sxs-lookup"><span data-stu-id="9fe9e-141">To assign a user-specific dial plan</span></span>

1. <span data-ttu-id="9fe9e-142">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="9fe9e-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="9fe9e-143">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="9fe9e-143">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="9fe9e-144">Para atribuir um plano de discagem específico do usuário, execute o seguinte no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="9fe9e-144">To assign a user-specific dial plan, run the following at the command prompt:</span></span>
    
   ```powershell
   Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="9fe9e-145">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9fe9e-145">For example:</span></span>
    
   ```powershell
   Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
   ```

    <span data-ttu-id="9fe9e-146">Neste exemplo, o usuário com o nome de exibição Bob Kelly é atribuído ao plano de discagem do usuário com o nome **DialPlanJapan**.</span><span class="sxs-lookup"><span data-stu-id="9fe9e-146">In this example, the user with the display name Bob Kelly is assigned the user dial plan with the name **DialPlanJapan**.</span></span>
    

