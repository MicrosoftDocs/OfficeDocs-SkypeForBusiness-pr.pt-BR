---
title: 'Lync Server 2013: Configurar políticas para controlar acesso de usuário federado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure policies to control federated user access
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8fb009561c36395ee31a49986f2db0103cbe096b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836347"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-federated-user-access-in-lync-server-2013"></a><span data-ttu-id="56ff1-102">Configurar políticas para controlar acesso de usuário federado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56ff1-102">Configure policies to control federated user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56ff1-103">_**Tópico da última modificação:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="56ff1-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="56ff1-104">Quando você configura políticas para dar suporte a comunicações com parceiros federados, as políticas se aplicam a usuários de domínios federados.</span><span class="sxs-lookup"><span data-stu-id="56ff1-104">When you configure policies to support communications with federated partners, the policies apply to users of federated domains.</span></span> <span data-ttu-id="56ff1-105">Você pode configurar uma ou mais políticas de acesso de usuários externos para controlar se os usuários de domínios federados podem colaborar com os usuários do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="56ff1-105">You can configure one or more external user access policies to control whether users of federated domains can collaborate with your Lync Server 2013 users.</span></span> <span data-ttu-id="56ff1-106">Para controlar o acesso do usuário federado, você pode configurar políticas nos níveis global, de site e de usuário.</span><span class="sxs-lookup"><span data-stu-id="56ff1-106">To control federated user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="56ff1-107">As configurações de política do Lync Server aplicadas em um nível de política podem substituir as configurações aplicadas em outro nível de política.</span><span class="sxs-lookup"><span data-stu-id="56ff1-107">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="56ff1-108">A precedência da política do Lync Server é: a política do usuário (maior influência) substitui uma política do site e uma política de site substitui uma política global (influência mínima).</span><span class="sxs-lookup"><span data-stu-id="56ff1-108">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="56ff1-109">Isso significa que, quanto mais perto a definição de política estiver do objeto que ela está afetando, maior será sua influência sobre o objeto.</span><span class="sxs-lookup"><span data-stu-id="56ff1-109">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="56ff1-110">Você pode configurar políticas para controlar o acesso do usuário federado, mesmo se você não tiver habilitado a Federação para sua organização.</span><span class="sxs-lookup"><span data-stu-id="56ff1-110">You can configure policies to control federated user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="56ff1-111">No entanto, as políticas que você configura são efetivadas apenas quando você tem a Federação habilitada para sua organização.</span><span class="sxs-lookup"><span data-stu-id="56ff1-111">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="56ff1-112">Para obter detalhes sobre como habilitar a Federação, consulte <A href="lync-server-2013-enable-or-disable-remote-user-access.md">habilitar ou desabilitar o acesso de usuário remoto no Lync Server 2013</A> na documentação de implantação ou documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="56ff1-112">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="56ff1-113">Além disso, se você especificar uma política de usuário para controlar o acesso do usuário federado, a política se aplicará somente aos usuários habilitados para o Lync Server 2013 e configurados para usar a política.</span><span class="sxs-lookup"><span data-stu-id="56ff1-113">Additionally, if you specify a user policy to control federated user access, the policy applies only to users that are enabled for Lync Server 2013 and configured to use the policy.</span></span>



</div>

<div>

## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="56ff1-114">Para configurar uma política para dar suporte ao acesso por usuários de domínios federados</span><span class="sxs-lookup"><span data-stu-id="56ff1-114">To configure a policy to support access by users of federated domains</span></span>

1.  <span data-ttu-id="56ff1-115">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="56ff1-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="56ff1-116">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="56ff1-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="56ff1-117">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="56ff1-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="56ff1-118">Na barra de navegação à esquerda, clique em **acesso ao usuário externo**e, em seguida, clique em **política de acesso externo**.</span><span class="sxs-lookup"><span data-stu-id="56ff1-118">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="56ff1-119">Na página **política de acesso externo** , siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="56ff1-119">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="56ff1-120">Para configurar a política global para dar suporte ao acesso de usuário federado, clique na política global, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="56ff1-120">To configure the global policy to support federated user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="56ff1-121">Para criar uma nova política de site, clique em **novo**e, em seguida, clique em **política do site**.</span><span class="sxs-lookup"><span data-stu-id="56ff1-121">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="56ff1-122">Em **selecionar um site**, clique no site apropriado na lista e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="56ff1-122">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="56ff1-123">Para criar uma nova política de usuário, clique em **novo**e, em seguida, clique em **política de usuário**.</span><span class="sxs-lookup"><span data-stu-id="56ff1-123">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="56ff1-124">Em **nova política de acesso externo**, crie um nome exclusivo no campo **nome** que indica o conteúdo da política do usuário (por exemplo, **EnableFederatedUsers** para uma política de usuário que permite comunicações para usuários do domínio federado).</span><span class="sxs-lookup"><span data-stu-id="56ff1-124">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableFederatedUsers** for a user policy that enables communications for federated domain users).</span></span>
    
      - <span data-ttu-id="56ff1-125">Para alterar uma política existente, clique na política apropriada listada na tabela, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="56ff1-125">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="56ff1-126">Adicionais Se você quiser adicionar ou editar uma descrição, especifique as informações da política em **Descrição**.</span><span class="sxs-lookup"><span data-stu-id="56ff1-126">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="56ff1-127">Siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="56ff1-127">Do one of the following:</span></span>
    
      - <span data-ttu-id="56ff1-128">Para habilitar o acesso de usuário federado para a política, marque a caixa de seleção **habilitar comunicações com usuários federados** .</span><span class="sxs-lookup"><span data-stu-id="56ff1-128">To enable federated user access for the policy, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="56ff1-129">Para desabilitar o acesso de usuário federado para a política, desmarque a caixa de seleção **habilitar comunicações com usuários federados** .</span><span class="sxs-lookup"><span data-stu-id="56ff1-129">To disable federated user access for the policy, clear the **Enable communications with federated users** check box.</span></span>

7.  <span data-ttu-id="56ff1-130">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="56ff1-130">Click **Commit**.</span></span>

<span data-ttu-id="56ff1-131">Para habilitar o acesso de usuário federado, você também deve habilitar o suporte para Federação em sua organização.</span><span class="sxs-lookup"><span data-stu-id="56ff1-131">To enable federated user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="56ff1-132">Para obter detalhes, consulte [habilitar ou desabilitar a conectividade de mensagens de chat públicas e de Federação no Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="56ff1-132">For details, see [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="56ff1-133">Se esta for uma política de usuário, você também deverá aplicar a política aos usuários que você deseja que possam colaborar com os usuários federados.</span><span class="sxs-lookup"><span data-stu-id="56ff1-133">If this is a user policy, you must also apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="56ff1-134">Para obter detalhes, consulte [atribuir uma política de acesso de usuário externo a um usuário habilitado do Lync no Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md).</span><span class="sxs-lookup"><span data-stu-id="56ff1-134">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md).</span></span>

</div>

<div>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="56ff1-135">Para configurar uma política existente usando o Windows PowerShell para dar suporte ao acesso por usuários de domínios federados</span><span class="sxs-lookup"><span data-stu-id="56ff1-135">To configure an existing policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="56ff1-136">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="56ff1-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="56ff1-137">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="56ff1-137">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="56ff1-138">Digite o seguinte no Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="56ff1-138">Type the following in the Lync Server Management Shell:</span></span>
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    <span data-ttu-id="56ff1-139">Um exemplo de comando que define a política global para acesso de usuário federado ao acesso de domínio federado habilitado, XMPP para acesso ao usuário remoto habilitado, acesso de usuário remoto para habilitado, acesso do provedor público como habilitado e conceder a capacidade de usar áudio e vídeo para provedores públicos que dão suporte a ele:</span><span class="sxs-lookup"><span data-stu-id="56ff1-139">An example command that will set the global policy for Federated user access to enabled, XMPP domain access to enabled, Remote user access to enabled, Public provider access to enabled, and grant the ability to use audio and video for public providers that support it:</span></span>
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="56ff1-140">O parâmetro "EnablePublicCloudAudioVideoAccess" não tem uma seleção correspondente no painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="56ff1-140">The parameter “EnablePublicCloudAudioVideoAccess” does not have a corresponding selection in the Lync Server Control Panel</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="56ff1-141">Para criar uma nova política usando o Windows PowerShell para dar suporte ao acesso por usuários de domínios federados</span><span class="sxs-lookup"><span data-stu-id="56ff1-141">To create a new policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="56ff1-142">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="56ff1-142">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="56ff1-143">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="56ff1-143">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="56ff1-144">Digite o seguinte no Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="56ff1-144">Type the following in the Lync Server Management Shell:</span></span>
    
        New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    <span data-ttu-id="56ff1-145">Um exemplo de como criar uma nova política de site:</span><span class="sxs-lookup"><span data-stu-id="56ff1-145">An example of creating a new site policy:</span></span>
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true

</div>

<div>

## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="56ff1-146">Para excluir ou redefinir uma política usando o Windows PowerShell para dar suporte ao acesso por usuários de domínios federados</span><span class="sxs-lookup"><span data-stu-id="56ff1-146">To delete or reset a policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="56ff1-147">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="56ff1-147">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="56ff1-148">Digite o seguinte no Shell de gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="56ff1-148">Type the following in the Lync Server Management Shell</span></span>
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy> 
    
    <span data-ttu-id="56ff1-149">Um exemplo de como redefinir a política global (a política global pode ter apenas sua configuração removida.</span><span class="sxs-lookup"><span data-stu-id="56ff1-149">An example of resetting the global policy (The global policy can only have its setting removed.</span></span> <span data-ttu-id="56ff1-150">A política não pode ser excluída):</span><span class="sxs-lookup"><span data-stu-id="56ff1-150">The policy cannot be deleted):</span></span>
    
        Remove-CsExternalAccessPolicy -Identity global 
    
    <span data-ttu-id="56ff1-151">Para remover uma política de site, digite:</span><span class="sxs-lookup"><span data-stu-id="56ff1-151">To remove a site policy, type:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity site:Redmond 
    
    <span data-ttu-id="56ff1-152">Exclui a política do site Redmond.</span><span class="sxs-lookup"><span data-stu-id="56ff1-152">Deletes the site policy Redmond.</span></span> <span data-ttu-id="56ff1-153">Para excluir uma política de usuário chamada UserEAPPolicy, digite:</span><span class="sxs-lookup"><span data-stu-id="56ff1-153">To delete a user policy named UserEAPPolicy, type:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity UserEAPPolicy

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="56ff1-154">Confira também</span><span class="sxs-lookup"><span data-stu-id="56ff1-154">See Also</span></span>


[<span data-ttu-id="56ff1-155">Habilitar ou desabilitar federação e conectividade de IM pública no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56ff1-155">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
[<span data-ttu-id="56ff1-156">Atribuir uma política de usuário externo a um usuário habilitado do Lync no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56ff1-156">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  


[<span data-ttu-id="56ff1-157">Gerenciar domínios SIP federados para sua organização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56ff1-157">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="56ff1-158">Gerenciar fornecedores SIP federados para sua organização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56ff1-158">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
[<span data-ttu-id="56ff1-159">Set-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="56ff1-159">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="56ff1-160">New-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="56ff1-160">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="56ff1-161">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="56ff1-161">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="56ff1-162">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="56ff1-162">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="56ff1-163">Grant CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="56ff1-163">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

