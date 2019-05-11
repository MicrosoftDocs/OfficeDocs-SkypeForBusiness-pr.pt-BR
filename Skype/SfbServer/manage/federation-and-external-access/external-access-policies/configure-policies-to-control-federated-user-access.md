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
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Quando você configura políticas para suportar a comunicação com parceiros federados, as diretivas serão aplicadas aos usuários de domínios federados. '
ms.openlocfilehash: 81eced8db10c9ffd017b5b79a54980b773b300bb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920655"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a><span data-ttu-id="6cac2-103">Configurar políticas para controlar o acesso de usuário federado na Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="6cac2-103">Configure policies to control federated user access in Skype for Business Server</span></span>

<span data-ttu-id="6cac2-104">Quando você configura políticas para suportar a comunicação com parceiros federados, as diretivas serão aplicadas aos usuários de domínios federados.</span><span class="sxs-lookup"><span data-stu-id="6cac2-104">When you configure policies to support communications with federated partners, the policies apply to users of federated domains.</span></span> <span data-ttu-id="6cac2-105">Você pode configurar uma ou mais políticas de acesso de usuário externo para controlar se os usuários de domínios federados podem colaborar com sua Skype para usuários corporativos Server.</span><span class="sxs-lookup"><span data-stu-id="6cac2-105">You can configure one or more external user access policies to control whether users of federated domains can collaborate with your Skype for Business Server users.</span></span> <span data-ttu-id="6cac2-106">Para controlar o acesso de usuário federado, você pode configurar políticas no nível global, site e nível de usuário.</span><span class="sxs-lookup"><span data-stu-id="6cac2-106">To control federated user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="6cac2-107">Skype para configurações de diretiva de servidor de negócios que são aplicados em um nível de política pode substituir as configurações que são aplicadas no nível de política de outro.</span><span class="sxs-lookup"><span data-stu-id="6cac2-107">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="6cac2-108">Skype para precedência da diretiva Business Server é: política de usuário (maior influência) substitui uma política de Site e, em seguida, uma política de Site substitui uma política Global (influência mínimos).</span><span class="sxs-lookup"><span data-stu-id="6cac2-108">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="6cac2-109">Isso significa que, quanto mais perto a definição de política estiver do objeto que ela está afetando, maior será sua influência sobre o objeto.</span><span class="sxs-lookup"><span data-stu-id="6cac2-109">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>


> [!NOTE]  
> <span data-ttu-id="6cac2-110">Você pode configurar políticas para controlar o acesso de usuário federado, mesmo se você não tiver habilitado a federação para sua organização.</span><span class="sxs-lookup"><span data-stu-id="6cac2-110">You can configure policies to control federated user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="6cac2-111">No entanto, as políticas que você definir estão em vigor somente quando você tem a federação habilitada para sua organização.</span><span class="sxs-lookup"><span data-stu-id="6cac2-111">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="6cac2-112">Para obter detalhes sobre como habilitar a federação, consulte [Habilitar ou desabilitar o acesso de usuário remoto](../access-edge/enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="6cac2-112">For details about enabling federation, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>  <span data-ttu-id="6cac2-113">Além disso, se você especificar uma política de usuário para controlar o acesso de usuário federado, a política se aplica somente aos usuários que estão habilitados para Skype para Business Server e configurados para usar a política.</span><span class="sxs-lookup"><span data-stu-id="6cac2-113">Additionally, if you specify a user policy to control federated user access, the policy applies only to users that are enabled for Skype for Business Server and configured to use the policy.</span></span>


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="6cac2-114">Para configurar uma política para suportar o acesso por usuários de domínios federados</span><span class="sxs-lookup"><span data-stu-id="6cac2-114">To configure a policy to support access by users of federated domains</span></span>

1.  <span data-ttu-id="6cac2-115">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="6cac2-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6cac2-116">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="6cac2-116">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="6cac2-117">Na barra de navegação à esquerda, clique em **Acesso de usuário externo**e, em seguida, clique em **Política de acesso externo**.</span><span class="sxs-lookup"><span data-stu-id="6cac2-117">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="6cac2-118">Na página **Política de acesso externo** , siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="6cac2-118">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="6cac2-119">Para configurar a política global para suportar o acesso de usuário federado, clique na política global, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="6cac2-119">To configure the global policy to support federated user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="6cac2-120">Para criar uma nova política de site, clique em **novo**e, em seguida, clique em **política de Site**.</span><span class="sxs-lookup"><span data-stu-id="6cac2-120">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="6cac2-121">Em **Selecionar um Site**, clique no local apropriado na lista e clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="6cac2-121">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="6cac2-122">Para criar uma nova política de usuário, clique em **novo**e clique em **política de usuário**.</span><span class="sxs-lookup"><span data-stu-id="6cac2-122">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="6cac2-123">Na **Nova política de acesso externo**, crie um nome exclusivo no campo **nome** que indica que o usuário política abrange (por exemplo, **EnableFederatedUsers** para uma política de usuário que permite a comunicação aos usuários de domínio federado).</span><span class="sxs-lookup"><span data-stu-id="6cac2-123">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableFederatedUsers** for a user policy that enables communications for federated domain users).</span></span>
    
      - <span data-ttu-id="6cac2-124">Para alterar uma política existente, clique na política adequada listada na tabela, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="6cac2-124">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="6cac2-125">(Opcional) Se você deseja adicionar ou editar uma descrição, especifique as informações para a política em **Descrição**.</span><span class="sxs-lookup"><span data-stu-id="6cac2-125">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="6cac2-126">Siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="6cac2-126">Do one of the following:</span></span>
    
      - <span data-ttu-id="6cac2-127">Para habilitar o acesso de usuário federado para a política, marque a caixa de seleção **Habilitar comunicações com usuários federados** .</span><span class="sxs-lookup"><span data-stu-id="6cac2-127">To enable federated user access for the policy, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="6cac2-128">Para desabilitar o acesso de usuário federado para a política, desmarque a caixa de seleção **Habilitar comunicações com usuários federados** .</span><span class="sxs-lookup"><span data-stu-id="6cac2-128">To disable federated user access for the policy, clear the **Enable communications with federated users** check box.</span></span>

7.  <span data-ttu-id="6cac2-129">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="6cac2-129">Click **Commit**.</span></span>

<span data-ttu-id="6cac2-130">Para habilitar o acesso de usuário federado, você também deve habilitar o suporte para federação na sua organização.</span><span class="sxs-lookup"><span data-stu-id="6cac2-130">To enable federated user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="6cac2-131">Para obter detalhes, consulte [Habilitar ou desabilitar a federação e conectividade IM pública](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="6cac2-131">For details, see [Enable or disable federation and public IM connectivity](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="6cac2-132">Se essa for uma política de usuário, você também deve aplicar a política aos usuários que você deseja pudessem colaborar com usuários federados.</span><span class="sxs-lookup"><span data-stu-id="6cac2-132">If this is a user policy, you must also apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="6cac2-133">Para obter detalhes, consulte [atribuir uma política de acesso de usuário externo](assign-an-external-user-access-policy.md).</span><span class="sxs-lookup"><span data-stu-id="6cac2-133">For details, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="6cac2-134">Para configurar uma política existente usando o Windows PowerShell para suportar o acesso pelos usuários de domínios federados</span><span class="sxs-lookup"><span data-stu-id="6cac2-134">To configure an existing policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="6cac2-135">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="6cac2-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6cac2-136">Inicie o Skype para visita do Shell de gerenciamento do servidor: clique em **Iniciar**, clique em **Todos os programas**, clique em **Skype para Business Server**e clique em **Skype do Shell de gerenciamento do servidor de Business**.</span><span class="sxs-lookup"><span data-stu-id="6cac2-136">Start the Skype for Busines Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="6cac2-137">Digite o seguinte no Skype do Shell de gerenciamento do servidor de negócios:</span><span class="sxs-lookup"><span data-stu-id="6cac2-137">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > <span data-ttu-id="6cac2-138">O parâmetro "EnablePublicCloudAudioVideoAccess" não possui uma seleção correspondente no Skype para painel de controle do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="6cac2-138">The parameter “EnablePublicCloudAudioVideoAccess” does not have a corresponding selection in the Skype for Business Server Control Panel</span></span>


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="6cac2-139">Para criar uma nova política utilizando o Windows PowerShell para suportar o acesso pelos usuários de domínios federados</span><span class="sxs-lookup"><span data-stu-id="6cac2-139">To create a new policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="6cac2-140">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="6cac2-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6cac2-141">Inicie o Skype do Shell de gerenciamento do servidor de negócios: clique em **Iniciar**, clique em **Todos os programas**, clique em **Microsoft Skype para Business Server**e clique em **Skype do Shell de gerenciamento do servidor de negócios**.</span><span class="sxs-lookup"><span data-stu-id="6cac2-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="6cac2-142">Digite o seguinte no Skype do Shell de gerenciamento do servidor de negócios:</span><span class="sxs-lookup"><span data-stu-id="6cac2-142">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    <span data-ttu-id="6cac2-143">Um exemplo de como criar uma nova política de site:</span><span class="sxs-lookup"><span data-stu-id="6cac2-143">An example of creating a new site policy:</span></span>
    
    ```
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="6cac2-144">Para excluir ou redefinir uma política utilizando o Windows PowerShell para suportar o acesso pelos usuários de domínios federados</span><span class="sxs-lookup"><span data-stu-id="6cac2-144">To delete or reset a policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="6cac2-145">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="6cac2-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6cac2-146">Digite o seguinte no Skype do Shell de gerenciamento do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="6cac2-146">Type the following in the Skype for Business Server Management Shell</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    <span data-ttu-id="6cac2-147">Um exemplo de redefinido a política global (a política global só pode ter sua configuração removidos.</span><span class="sxs-lookup"><span data-stu-id="6cac2-147">An example of resetting the global policy (The global policy can only have its setting removed.</span></span> <span data-ttu-id="6cac2-148">A diretiva não pode ser excluída):</span><span class="sxs-lookup"><span data-stu-id="6cac2-148">The policy cannot be deleted):</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    <span data-ttu-id="6cac2-149">Para remover uma política de site, digite:</span><span class="sxs-lookup"><span data-stu-id="6cac2-149">To remove a site policy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    <span data-ttu-id="6cac2-150">Exclui a política de site de Redmond.</span><span class="sxs-lookup"><span data-stu-id="6cac2-150">Deletes the site policy Redmond.</span></span> <span data-ttu-id="6cac2-151">Para excluir uma política de usuário chamada UserEAPPolicy, digite:</span><span class="sxs-lookup"><span data-stu-id="6cac2-151">To delete a user policy named UserEAPPolicy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a><span data-ttu-id="6cac2-152">Confira também</span><span class="sxs-lookup"><span data-stu-id="6cac2-152">See Also</span></span>


[<span data-ttu-id="6cac2-153">Habilitar ou desabilitar federação e conectividade de IM pública</span><span class="sxs-lookup"><span data-stu-id="6cac2-153">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[<span data-ttu-id="6cac2-154">Atribuir uma política de acesso de usuário externo</span><span class="sxs-lookup"><span data-stu-id="6cac2-154">Assign an external user access policy</span></span>](assign-an-external-user-access-policy.md)

[<span data-ttu-id="6cac2-155">Gerenciar domínios SIP federados para sua organização</span><span class="sxs-lookup"><span data-stu-id="6cac2-155">Manage SIP federated domains for your organization</span></span>](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[<span data-ttu-id="6cac2-156">Gerenciar fornecedores SIP federados para sua organização</span><span class="sxs-lookup"><span data-stu-id="6cac2-156">Manage SIP federated providers for your organization</span></span>](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[<span data-ttu-id="6cac2-157">Set-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="6cac2-157">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="6cac2-158">New-CsExternalAccessPolicy.</span><span class="sxs-lookup"><span data-stu-id="6cac2-158">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="6cac2-159">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="6cac2-159">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="6cac2-160">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="6cac2-160">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="6cac2-161">Grant-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="6cac2-161">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

