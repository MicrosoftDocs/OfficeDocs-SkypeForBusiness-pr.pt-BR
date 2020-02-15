---
title: 'Lync Server 2013: configurar políticas para controlar o acesso de usuário federado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control federated user access
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c40b2a1fa071c7dd7f93e384418679ffcead38c0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035333"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-federated-user-access-in-lync-server-2013"></a><span data-ttu-id="88583-102">Configurar políticas para controlar o acesso de usuário federado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88583-102">Configure policies to control federated user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88583-103">_**Última modificação do tópico:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="88583-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="88583-104">Quando você configurar políticas para fornecer suporte às comunicações de parceiros federados, as políticas se aplicam aos usuários de domínios federados.</span><span class="sxs-lookup"><span data-stu-id="88583-104">When you configure policies to support communications with federated partners, the policies apply to users of federated domains.</span></span> <span data-ttu-id="88583-105">Você pode configurar uma ou mais políticas de acesso de usuário externo para controlar se os usuários de domínios federados podem colaborar com seus usuários do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="88583-105">You can configure one or more external user access policies to control whether users of federated domains can collaborate with your Lync Server 2013 users.</span></span> <span data-ttu-id="88583-106">Para controlar o acesso de usuários federados, você pode configurar políticas no nível global, de site e de usuário.</span><span class="sxs-lookup"><span data-stu-id="88583-106">To control federated user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="88583-107">As configurações de política do Lync Server aplicadas em um nível de política podem substituir as configurações que são aplicadas em outro nível de política.</span><span class="sxs-lookup"><span data-stu-id="88583-107">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="88583-108">A precedência de política do Lync Server é: a política de usuário (maior influência) substitui uma política de site e, em seguida, uma política de site substitui uma política global (menos influência).</span><span class="sxs-lookup"><span data-stu-id="88583-108">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="88583-109">Isso significa que quanto mais próxima a configuração de diretiva for o objeto que a política está afetando, maior será a influência sobre o objeto.</span><span class="sxs-lookup"><span data-stu-id="88583-109">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="88583-110">Você pode configurar políticas para controlar o acesso de usuário federado, mesmo se você não tiver habilitado a federação para sua organização.</span><span class="sxs-lookup"><span data-stu-id="88583-110">You can configure policies to control federated user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="88583-111">No entanto, as políticas que você configurar entram em vigor somente quando o federação é habilitada para sua organização.</span><span class="sxs-lookup"><span data-stu-id="88583-111">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="88583-112">Para obter detalhes sobre como habilitar a Federação, consulte <A href="lync-server-2013-enable-or-disable-remote-user-access.md">habilitar ou desabilitar o acesso de usuário remoto no Lync Server 2013</A> na documentação de implantação ou na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="88583-112">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="88583-113">Além disso, se você especificar uma política de usuário para controlar o acesso de usuário federado, a política será aplicada somente aos usuários habilitados para o Lync Server 2013 e configurados para usar a política.</span><span class="sxs-lookup"><span data-stu-id="88583-113">Additionally, if you specify a user policy to control federated user access, the policy applies only to users that are enabled for Lync Server 2013 and configured to use the policy.</span></span>



</div>

<div>

## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="88583-114">Para configurar uma política para suportar o acesso por usuários de domínios federados</span><span class="sxs-lookup"><span data-stu-id="88583-114">To configure a policy to support access by users of federated domains</span></span>

1.  <span data-ttu-id="88583-115">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="88583-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="88583-116">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="88583-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="88583-117">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="88583-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="88583-118">Na barra de navegação esquerda, clique em **Acesso do Usuário Externo** e em **Política de Acesso Externo**.</span><span class="sxs-lookup"><span data-stu-id="88583-118">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="88583-119">Na página **Política de Acesso Externo**, execute um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="88583-119">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="88583-120">Para configurar a política global para oferecer suporte ao acesso de usuário federado, clique na política global, clique em **Editar** e em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="88583-120">To configure the global policy to support federated user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="88583-p104">Para criar uma nova política de site, clique em **Nova** e em **Política de site**. Em **Selecionar um Site**, clique no site apropriado na lista e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="88583-p104">To create a new site policy, click **New**, and then click **Site policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="88583-p105">Para criar uma nova política de usuário, clique em **Nova** e em **Política de usuário**. Em **Nova Política de Acesso Externo**, crie um nome exclusivo no campo **Nome** que indica o a abrangência da política de usuário (por exemplo, **EnableFederatedUsers** para uma política de usuário que permite comunicações para usuários públicos).</span><span class="sxs-lookup"><span data-stu-id="88583-p105">To create a new user policy, click **New**, and then click **User policy**. In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableFederatedUsers** for a user policy that enables communications for federated domain users).</span></span>
    
      - <span data-ttu-id="88583-125">Para alterar uma política existente, clique na política adequada listada na tabela, clique em **Editar** e em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="88583-125">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="88583-126">(Opcional) Se você deseja adicionar ou editar uma descrição, especifique a informação da política em **Descrição**.</span><span class="sxs-lookup"><span data-stu-id="88583-126">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="88583-127">Siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="88583-127">Do one of the following:</span></span>
    
      - <span data-ttu-id="88583-128">Para habilitar o acesso de usuário federado na política, marque a caixa de seleção **Habilitar comunicações com usuários federados**.</span><span class="sxs-lookup"><span data-stu-id="88583-128">To enable federated user access for the policy, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="88583-129">Para desabilitar o acesso de usuário federado na política, desmarque a caixa de seleção **Habilitar comunicações com usuários federados**.</span><span class="sxs-lookup"><span data-stu-id="88583-129">To disable federated user access for the policy, clear the **Enable communications with federated users** check box.</span></span>

7.  <span data-ttu-id="88583-130">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="88583-130">Click **Commit**.</span></span>

<span data-ttu-id="88583-131">Para habilitar o acesso do usuário federado, você também deve habilitar o suporte para federação em sua organização.</span><span class="sxs-lookup"><span data-stu-id="88583-131">To enable federated user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="88583-132">Para obter detalhes, consulte [habilitar ou desabilitar Federação e conectividade de im pública no Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="88583-132">For details, see [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="88583-133">Se essa for uma política de usuário, você também deverá aplicar a política aos usuários que também devem ser capazes de colaborar com usuários federados.</span><span class="sxs-lookup"><span data-stu-id="88583-133">If this is a user policy, you must also apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="88583-134">Para obter detalhes, consulte [atribuir uma política de acesso de usuário externo a um usuário habilitado do Lync no Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md).</span><span class="sxs-lookup"><span data-stu-id="88583-134">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md).</span></span>

</div>

<div>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="88583-135">Para configurar uma política existente usando o Windows PowerShell para dar suporte ao acesso por usuários de domínios federados</span><span class="sxs-lookup"><span data-stu-id="88583-135">To configure an existing policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="88583-136">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="88583-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="88583-137">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="88583-137">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="88583-138">Digite o seguinte no Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="88583-138">Type the following in the Lync Server Management Shell:</span></span>
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    <span data-ttu-id="88583-139">Um exemplo de comando que definirá a política global para habilitar o acesso de usuários federados, acesso ao domínio XMPP, acesso de usuário remoto, acesso de provedor público e conceder a capacidade de utilizar áudio e vídeo para provedores públicos que os suportem:</span><span class="sxs-lookup"><span data-stu-id="88583-139">An example command that will set the global policy for Federated user access to enabled, XMPP domain access to enabled, Remote user access to enabled, Public provider access to enabled, and grant the ability to use audio and video for public providers that support it:</span></span>
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="88583-140">O parâmetro "EnablePublicCloudAudioVideoAccess" não tem uma seleção correspondente no painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="88583-140">The parameter “EnablePublicCloudAudioVideoAccess” does not have a corresponding selection in the Lync Server Control Panel</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="88583-141">Para criar uma nova política usando o Windows PowerShell para dar suporte ao acesso por usuários de domínios federados</span><span class="sxs-lookup"><span data-stu-id="88583-141">To create a new policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="88583-142">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="88583-142">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="88583-143">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="88583-143">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="88583-144">Digite o seguinte no Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="88583-144">Type the following in the Lync Server Management Shell:</span></span>
    
        New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    <span data-ttu-id="88583-145">Um exemplo de criação de uma nova política de site:</span><span class="sxs-lookup"><span data-stu-id="88583-145">An example of creating a new site policy:</span></span>
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true

</div>

<div>

## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="88583-146">Para excluir ou redefinir uma política usando o Windows PowerShell para dar suporte ao acesso por usuários de domínios federados</span><span class="sxs-lookup"><span data-stu-id="88583-146">To delete or reset a policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="88583-147">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="88583-147">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="88583-148">Digite o seguinte no Shell de gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="88583-148">Type the following in the Lync Server Management Shell</span></span>
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy> 
    
    <span data-ttu-id="88583-p108">Um exemplo de redefinição de política global (A política global somente pode ter sua configuração removida. A política não pode ser excluída):</span><span class="sxs-lookup"><span data-stu-id="88583-p108">An example of resetting the global policy (The global policy can only have its setting removed. The policy cannot be deleted):</span></span>
    
        Remove-CsExternalAccessPolicy -Identity global 
    
    <span data-ttu-id="88583-151">Para remover uma política de site, digite:</span><span class="sxs-lookup"><span data-stu-id="88583-151">To remove a site policy, type:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity site:Redmond 
    
    <span data-ttu-id="88583-152">Exclua a política de site de Redmond.</span><span class="sxs-lookup"><span data-stu-id="88583-152">Deletes the site policy Redmond.</span></span> <span data-ttu-id="88583-153">Para excluir uma política de usuário chamada UserEAPPolicy, digite:</span><span class="sxs-lookup"><span data-stu-id="88583-153">To delete a user policy named UserEAPPolicy, type:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity UserEAPPolicy

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="88583-154">Confira também</span><span class="sxs-lookup"><span data-stu-id="88583-154">See Also</span></span>


[<span data-ttu-id="88583-155">Habilitar ou desabilitar Federação e conectividade de IM pública no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88583-155">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
[<span data-ttu-id="88583-156">Atribuir uma política de acesso de usuário externo a um usuário habilitado do Lync no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88583-156">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  


[<span data-ttu-id="88583-157">Gerenciar domínios federados SIP para sua organização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88583-157">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="88583-158">Gerenciar provedores federados SIP para sua organização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88583-158">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
[<span data-ttu-id="88583-159">Set-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="88583-159">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="88583-160">New-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="88583-160">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="88583-161">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="88583-161">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="88583-162">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="88583-162">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="88583-163">Grant-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="88583-163">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

