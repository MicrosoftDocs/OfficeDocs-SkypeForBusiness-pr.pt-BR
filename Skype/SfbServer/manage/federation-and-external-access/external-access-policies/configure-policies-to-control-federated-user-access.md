---
title: Configurar políticas para controlar acesso de usuário federado
ms.reviewer: ''
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Quando você configura políticas para dar suporte a comunicações com parceiros federados, as políticas se aplicam a usuários de domínios federados. '
ms.openlocfilehash: d9192589191590cd96f72323681ef4df6513e36d
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991756"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a><span data-ttu-id="93542-103">Configurar políticas para controlar o acesso de usuários federados no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="93542-103">Configure policies to control federated user access in Skype for Business Server</span></span>

<span data-ttu-id="93542-104">Quando você configura políticas para dar suporte a comunicações com parceiros federados, as políticas se aplicam a usuários de domínios federados.</span><span class="sxs-lookup"><span data-stu-id="93542-104">When you configure policies to support communications with federated partners, the policies apply to users of federated domains.</span></span> <span data-ttu-id="93542-105">Você pode configurar uma ou mais políticas de acesso de usuários externos para controlar se os usuários de domínios federados podem colaborar com os usuários do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="93542-105">You can configure one or more external user access policies to control whether users of federated domains can collaborate with your Skype for Business Server users.</span></span> <span data-ttu-id="93542-106">Para controlar o acesso do usuário federado, você pode configurar políticas nos níveis global, de site e de usuário.</span><span class="sxs-lookup"><span data-stu-id="93542-106">To control federated user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="93542-107">As configurações de política do Skype for Business Server aplicadas em um nível de política podem substituir as configurações aplicadas em outro nível de política.</span><span class="sxs-lookup"><span data-stu-id="93542-107">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="93542-108">A precedência de política do Skype for Business Server é: a política do usuário (maior influência) substitui uma política do site e, em seguida, uma política de site substitui uma política global (influência mínima).</span><span class="sxs-lookup"><span data-stu-id="93542-108">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="93542-109">Isso significa que, quanto mais perto a definição de política estiver do objeto que ela está afetando, maior será sua influência sobre o objeto.</span><span class="sxs-lookup"><span data-stu-id="93542-109">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>


> [!NOTE]  
> <span data-ttu-id="93542-110">Você pode configurar políticas para controlar o acesso do usuário federado, mesmo se você não tiver habilitado a Federação para sua organização.</span><span class="sxs-lookup"><span data-stu-id="93542-110">You can configure policies to control federated user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="93542-111">No entanto, as políticas que você configura são efetivadas apenas quando você tem a Federação habilitada para sua organização.</span><span class="sxs-lookup"><span data-stu-id="93542-111">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="93542-112">Para obter detalhes sobre como habilitar a Federação, consulte [habilitar ou desabilitar o acesso de usuários remotos](../access-edge/enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="93542-112">For details about enabling federation, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>  <span data-ttu-id="93542-113">Além disso, se você especificar uma política de usuário para controlar o acesso do usuário federado, a política se aplicará somente aos usuários habilitados para o Skype for Business Server e configurados para usar a política.</span><span class="sxs-lookup"><span data-stu-id="93542-113">Additionally, if you specify a user policy to control federated user access, the policy applies only to users that are enabled for Skype for Business Server and configured to use the policy.</span></span>


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="93542-114">Para configurar uma política para dar suporte ao acesso por usuários de domínios federados</span><span class="sxs-lookup"><span data-stu-id="93542-114">To configure a policy to support access by users of federated domains</span></span>

1.  <span data-ttu-id="93542-115">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="93542-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="93542-116">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="93542-116">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="93542-117">Na barra de navegação à esquerda, clique em **acesso ao usuário externo**e, em seguida, clique em **política de acesso externo**.</span><span class="sxs-lookup"><span data-stu-id="93542-117">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="93542-118">Na página **política de acesso externo** , siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="93542-118">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="93542-119">Para configurar a política global para dar suporte ao acesso de usuário federado, clique na política global, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="93542-119">To configure the global policy to support federated user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="93542-120">Para criar uma nova política de site, clique em **novo**e, em seguida, clique em **política do site**.</span><span class="sxs-lookup"><span data-stu-id="93542-120">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="93542-121">Em **selecionar um site**, clique no site apropriado na lista e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="93542-121">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="93542-122">Para criar uma nova política de usuário, clique em **novo**e, em seguida, clique em **política de usuário**.</span><span class="sxs-lookup"><span data-stu-id="93542-122">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="93542-123">Em **nova política de acesso externo**, crie um nome exclusivo no campo **nome** que indica o conteúdo da política do usuário (por exemplo, **EnableFederatedUsers** para uma política de usuário que permite comunicações para usuários do domínio federado).</span><span class="sxs-lookup"><span data-stu-id="93542-123">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableFederatedUsers** for a user policy that enables communications for federated domain users).</span></span>
    
      - <span data-ttu-id="93542-124">Para alterar uma política existente, clique na política apropriada listada na tabela, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="93542-124">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="93542-125">Adicionais Se você quiser adicionar ou editar uma descrição, especifique as informações da política em **Descrição**.</span><span class="sxs-lookup"><span data-stu-id="93542-125">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="93542-126">Siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="93542-126">Do one of the following:</span></span>
    
      - <span data-ttu-id="93542-127">Para habilitar o acesso de usuário federado para a política, marque a caixa de seleção **habilitar comunicações com usuários federados** .</span><span class="sxs-lookup"><span data-stu-id="93542-127">To enable federated user access for the policy, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="93542-128">Para desabilitar o acesso de usuário federado para a política, desmarque a caixa de seleção **habilitar comunicações com usuários federados** .</span><span class="sxs-lookup"><span data-stu-id="93542-128">To disable federated user access for the policy, clear the **Enable communications with federated users** check box.</span></span>

7.  <span data-ttu-id="93542-129">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="93542-129">Click **Commit**.</span></span>

<span data-ttu-id="93542-130">Para habilitar o acesso de usuário federado, você também deve habilitar o suporte para Federação em sua organização.</span><span class="sxs-lookup"><span data-stu-id="93542-130">To enable federated user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="93542-131">Para obter detalhes, consulte [habilitar ou desabilitar a conectividade de mensagens de chat públicas e de Federação](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="93542-131">For details, see [Enable or disable federation and public IM connectivity](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="93542-132">Se esta for uma política de usuário, você também deverá aplicar a política aos usuários que você deseja que possam colaborar com os usuários federados.</span><span class="sxs-lookup"><span data-stu-id="93542-132">If this is a user policy, you must also apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="93542-133">Para obter detalhes, consulte [atribuir uma política de acesso de usuário externo](assign-an-external-user-access-policy.md).</span><span class="sxs-lookup"><span data-stu-id="93542-133">For details, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="93542-134">Para configurar uma política existente usando o Windows PowerShell para dar suporte ao acesso por usuários de domínios federados</span><span class="sxs-lookup"><span data-stu-id="93542-134">To configure an existing policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="93542-135">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="93542-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="93542-136">Inicie o Shell de gerenciamento do Skype para visita Server: clique em **Iniciar**, clique em **todos os programas**, clique em **Skype for Business Server**e, em seguida, clique em **Shell de gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="93542-136">Start the Skype for Busines Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="93542-137">Digite o seguinte no Shell de gerenciamento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="93542-137">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```PowerShell
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > <span data-ttu-id="93542-138">O parâmetro "EnablePublicCloudAudioVideoAccess" não tem uma seleção correspondente no painel de controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="93542-138">The parameter “EnablePublicCloudAudioVideoAccess” does not have a corresponding selection in the Skype for Business Server Control Panel</span></span>


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="93542-139">Para criar uma nova política usando o Windows PowerShell para dar suporte ao acesso por usuários de domínios federados</span><span class="sxs-lookup"><span data-stu-id="93542-139">To create a new policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="93542-140">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="93542-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="93542-141">Inicie o Shell de gerenciamento do Skype for Business Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Skype for Business Server**e, em seguida, clique em **Shell de gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="93542-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="93542-142">Digite o seguinte no Shell de gerenciamento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="93542-142">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```PowerShell
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    <span data-ttu-id="93542-143">Um exemplo de como criar uma nova política de site:</span><span class="sxs-lookup"><span data-stu-id="93542-143">An example of creating a new site policy:</span></span>
    
    ```PowerShell
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="93542-144">Para excluir ou redefinir uma política usando o Windows PowerShell para dar suporte ao acesso por usuários de domínios federados</span><span class="sxs-lookup"><span data-stu-id="93542-144">To delete or reset a policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="93542-145">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="93542-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="93542-146">Digite o seguinte no Shell de gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="93542-146">Type the following in the Skype for Business Server Management Shell</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    <span data-ttu-id="93542-147">Um exemplo de como redefinir a política global (a política global pode ter apenas sua configuração removida.</span><span class="sxs-lookup"><span data-stu-id="93542-147">An example of resetting the global policy (The global policy can only have its setting removed.</span></span> <span data-ttu-id="93542-148">A política não pode ser excluída):</span><span class="sxs-lookup"><span data-stu-id="93542-148">The policy cannot be deleted):</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    <span data-ttu-id="93542-149">Para remover uma política de site, digite:</span><span class="sxs-lookup"><span data-stu-id="93542-149">To remove a site policy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    <span data-ttu-id="93542-150">Exclui a política do site Redmond.</span><span class="sxs-lookup"><span data-stu-id="93542-150">Deletes the site policy Redmond.</span></span> <span data-ttu-id="93542-151">Para excluir uma política de usuário chamada UserEAPPolicy, digite:</span><span class="sxs-lookup"><span data-stu-id="93542-151">To delete a user policy named UserEAPPolicy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a><span data-ttu-id="93542-152">Confira também</span><span class="sxs-lookup"><span data-stu-id="93542-152">See Also</span></span>


[<span data-ttu-id="93542-153">Habilitar ou desabilitar federação e conectividade de IM pública</span><span class="sxs-lookup"><span data-stu-id="93542-153">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[<span data-ttu-id="93542-154">Atribuir uma política de acesso de usuário externo</span><span class="sxs-lookup"><span data-stu-id="93542-154">Assign an external user access policy</span></span>](assign-an-external-user-access-policy.md)

[<span data-ttu-id="93542-155">Gerenciar domínios SIP federados para sua organização</span><span class="sxs-lookup"><span data-stu-id="93542-155">Manage SIP federated domains for your organization</span></span>](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[<span data-ttu-id="93542-156">Gerenciar fornecedores SIP federados para sua organização</span><span class="sxs-lookup"><span data-stu-id="93542-156">Manage SIP federated providers for your organization</span></span>](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[<span data-ttu-id="93542-157">Set-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="93542-157">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="93542-158">New-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="93542-158">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="93542-159">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="93542-159">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="93542-160">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="93542-160">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="93542-161">Grant CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="93542-161">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

