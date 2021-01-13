---
title: Configurar políticas para controlar acesso de usuário federado
ms.reviewer: ''
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Quando você configurar políticas para fornecer suporte às comunicações de parceiros federados, as políticas se aplicam aos usuários de domínios federados. '
ms.openlocfilehash: 2b7976492fe4f789c2f3130fb51deaaef44af701
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817296"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a><span data-ttu-id="03030-103">Configurar políticas para controlar o acesso de usuário federado no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="03030-103">Configure policies to control federated user access in Skype for Business Server</span></span>

<span data-ttu-id="03030-104">Quando você configurar políticas para fornecer suporte às comunicações de parceiros federados, as políticas se aplicam aos usuários de domínios federados.</span><span class="sxs-lookup"><span data-stu-id="03030-104">When you configure policies to support communications with federated partners, the policies apply to users of federated domains.</span></span> <span data-ttu-id="03030-105">Você pode configurar uma ou mais políticas de acesso de usuário externo para controlar se os usuários de domínios federados podem colaborar com seus usuários do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="03030-105">You can configure one or more external user access policies to control whether users of federated domains can collaborate with your Skype for Business Server users.</span></span> <span data-ttu-id="03030-106">Para controlar o acesso de usuários federados, você pode configurar políticas no nível global, de site e de usuário.</span><span class="sxs-lookup"><span data-stu-id="03030-106">To control federated user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="03030-107">As configurações de política do Skype for Business Server aplicadas em um nível de política podem substituir as configurações aplicadas em outro nível de política.</span><span class="sxs-lookup"><span data-stu-id="03030-107">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="03030-108">A precedência da política do Skype for Business Server é: políticas de usuário (maior influência) substituem políticas de site, e políticas de site substituem políticas globais (menor influência).</span><span class="sxs-lookup"><span data-stu-id="03030-108">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="03030-109">Isso significa que quanto mais próxima a configuração da política estiver do objeto que a política estiver afetando, maior será a influência sobre o objeto.</span><span class="sxs-lookup"><span data-stu-id="03030-109">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>


> [!NOTE]  
> <span data-ttu-id="03030-110">Você pode configurar políticas para controlar o acesso de usuário federado, mesmo se você não tiver habilitado a federação para sua organização.</span><span class="sxs-lookup"><span data-stu-id="03030-110">You can configure policies to control federated user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="03030-111">No entanto, as políticas que você configurar entram em vigor somente quando o federação é habilitada para sua organização.</span><span class="sxs-lookup"><span data-stu-id="03030-111">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="03030-112">Para obter detalhes sobre como habilitar a federação, [consulte Habilitar ou desabilitar o acesso de usuário remoto.](../access-edge/enable-or-disable-remote-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="03030-112">For details about enabling federation, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>  <span data-ttu-id="03030-113">Além disso, se você especificar uma política de usuário para controlar o acesso de usuário federado, a política se aplicará somente aos usuários habilitados para o Skype for Business Server e configurados para usar a política.</span><span class="sxs-lookup"><span data-stu-id="03030-113">Additionally, if you specify a user policy to control federated user access, the policy applies only to users that are enabled for Skype for Business Server and configured to use the policy.</span></span>


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="03030-114">Para configurar uma política para suportar o acesso por usuários de domínios federados</span><span class="sxs-lookup"><span data-stu-id="03030-114">To configure a policy to support access by users of federated domains</span></span>

1.  <span data-ttu-id="03030-115">Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="03030-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="03030-116">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="03030-116">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="03030-117">Na barra de navegação esquerda, clique em **Acesso do Usuário Externo** e em **Política de Acesso Externo**.</span><span class="sxs-lookup"><span data-stu-id="03030-117">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="03030-118">Na página **Política de Acesso Externo**, execute um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="03030-118">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="03030-119">Para configurar a política global para oferecer suporte ao acesso de usuário federado, clique na política global, clique em **Editar** e em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="03030-119">To configure the global policy to support federated user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="03030-p103">Para criar uma nova política de site, clique em **Nova** e em **Política de site**. Em **Selecionar um Site**, clique no site apropriado na lista e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="03030-p103">To create a new site policy, click **New**, and then click **Site policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="03030-p104">Para criar uma nova política de usuário, clique em **Nova** e em **Política de usuário**. Em **Nova Política de Acesso Externo**, crie um nome exclusivo no campo **Nome** que indica o a abrangência da política de usuário (por exemplo, **EnableFederatedUsers** para uma política de usuário que permite comunicações para usuários públicos).</span><span class="sxs-lookup"><span data-stu-id="03030-p104">To create a new user policy, click **New**, and then click **User policy**. In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableFederatedUsers** for a user policy that enables communications for federated domain users).</span></span>
    
      - <span data-ttu-id="03030-124">Para alterar uma política existente, clique na política adequada listada na tabela, clique em **Editar** e em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="03030-124">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="03030-125">(Opcional) Se você deseja adicionar ou editar uma descrição, especifique a informação da política em **Descrição**.</span><span class="sxs-lookup"><span data-stu-id="03030-125">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="03030-126">Siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="03030-126">Do one of the following:</span></span>
    
      - <span data-ttu-id="03030-127">Para habilitar o acesso de usuário federado na política, marque a caixa de seleção **Habilitar comunicações com usuários federados**.</span><span class="sxs-lookup"><span data-stu-id="03030-127">To enable federated user access for the policy, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="03030-128">Para desabilitar o acesso de usuário federado na política, desmarque a caixa de seleção **Habilitar comunicações com usuários federados**.</span><span class="sxs-lookup"><span data-stu-id="03030-128">To disable federated user access for the policy, clear the **Enable communications with federated users** check box.</span></span>

7.  <span data-ttu-id="03030-129">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="03030-129">Click **Commit**.</span></span>

<span data-ttu-id="03030-130">Para habilitar o acesso do usuário federado, você também deve habilitar o suporte para federação em sua organização.</span><span class="sxs-lookup"><span data-stu-id="03030-130">To enable federated user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="03030-131">Para obter detalhes, [consulte Habilitar ou desabilitar federação e conectividade de IM pública.](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="03030-131">For details, see [Enable or disable federation and public IM connectivity](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="03030-132">Se essa for uma política de usuário, você também deverá aplicar a política aos usuários que também devem ser capazes de colaborar com usuários federados.</span><span class="sxs-lookup"><span data-stu-id="03030-132">If this is a user policy, you must also apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="03030-133">Para obter detalhes, [consulte Atribuir uma política de acesso de usuário externo.](assign-an-external-user-access-policy.md)</span><span class="sxs-lookup"><span data-stu-id="03030-133">For details, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="03030-134">Para configurar uma política existente usando o Windows PowerShell para dar suporte ao acesso por usuários de domínios federados</span><span class="sxs-lookup"><span data-stu-id="03030-134">To configure an existing policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="03030-135">Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="03030-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="03030-136">Inicie o Shell de Gerenciamento do Skype for Busines Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business Server** e no Shell de Gerenciamento do Skype for Business **Server.**</span><span class="sxs-lookup"><span data-stu-id="03030-136">Start the Skype for Busines Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="03030-137">Digite o seguinte no Shell de Gerenciamento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="03030-137">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```PowerShell
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > <span data-ttu-id="03030-138">O parâmetro "EnablePublicCloudAudioVideoAccess" não tem uma seleção correspondente no Painel de Controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="03030-138">The parameter “EnablePublicCloudAudioVideoAccess” does not have a corresponding selection in the Skype for Business Server Control Panel</span></span>


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="03030-139">Para criar uma nova política usando o Windows PowerShell para dar suporte ao acesso por usuários de domínios federados</span><span class="sxs-lookup"><span data-stu-id="03030-139">To create a new policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="03030-140">Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="03030-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="03030-141">Inicie o Shell de Gerenciamento do Skype for Business Server: Clique em **Iniciar,** Em Todos os **Programas,** clique em **Microsoft Skype for Business Server** e, em seguida, clique no Shell de Gerenciamento do Skype for Business **Server.**</span><span class="sxs-lookup"><span data-stu-id="03030-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="03030-142">Digite o seguinte no Shell de Gerenciamento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="03030-142">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```PowerShell
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    <span data-ttu-id="03030-143">Um exemplo de criação de uma nova política de site:</span><span class="sxs-lookup"><span data-stu-id="03030-143">An example of creating a new site policy:</span></span>
    
    ```PowerShell
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="03030-144">Para excluir ou redefinir uma política usando o Windows PowerShell para dar suporte ao acesso por usuários de domínios federados</span><span class="sxs-lookup"><span data-stu-id="03030-144">To delete or reset a policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="03030-145">Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="03030-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="03030-146">Digite o seguinte no Shell de Gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="03030-146">Type the following in the Skype for Business Server Management Shell</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    <span data-ttu-id="03030-p107">Um exemplo de redefinição de política global (A política global somente pode ter sua configuração removida. A política não pode ser excluída):</span><span class="sxs-lookup"><span data-stu-id="03030-p107">An example of resetting the global policy (The global policy can only have its setting removed. The policy cannot be deleted):</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    <span data-ttu-id="03030-149">Para remover uma política de site, digite:</span><span class="sxs-lookup"><span data-stu-id="03030-149">To remove a site policy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    <span data-ttu-id="03030-150">Exclua a política de site de Redmond.</span><span class="sxs-lookup"><span data-stu-id="03030-150">Deletes the site policy Redmond.</span></span> <span data-ttu-id="03030-151">Para excluir uma política de usuário chamada UserEAPPolicy, digite:</span><span class="sxs-lookup"><span data-stu-id="03030-151">To delete a user policy named UserEAPPolicy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a><span data-ttu-id="03030-152">Confira também</span><span class="sxs-lookup"><span data-stu-id="03030-152">See Also</span></span>


[<span data-ttu-id="03030-153">Habilitar ou desabilitar federação e conectividade de IM pública</span><span class="sxs-lookup"><span data-stu-id="03030-153">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[<span data-ttu-id="03030-154">Atribuir uma política de acesso de usuário externo</span><span class="sxs-lookup"><span data-stu-id="03030-154">Assign an external user access policy</span></span>](assign-an-external-user-access-policy.md)

[<span data-ttu-id="03030-155">Gerenciar domínios SIP federados para sua organização</span><span class="sxs-lookup"><span data-stu-id="03030-155">Manage SIP federated domains for your organization</span></span>](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[<span data-ttu-id="03030-156">Gerenciar fornecedores SIP federados para sua organização</span><span class="sxs-lookup"><span data-stu-id="03030-156">Manage SIP federated providers for your organization</span></span>](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[<span data-ttu-id="03030-157">Set-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="03030-157">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="03030-158">New-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="03030-158">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="03030-159">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="03030-159">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="03030-160">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="03030-160">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="03030-161">Grant-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="03030-161">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

