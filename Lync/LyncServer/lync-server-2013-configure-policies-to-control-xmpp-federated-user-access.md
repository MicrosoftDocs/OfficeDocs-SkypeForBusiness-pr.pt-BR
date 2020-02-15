---
title: 'Lync Server 2013: configurar políticas para controlar o acesso de usuário federado do XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control XMPP federated user access
ms:assetid: 0fe0ff75-e52a-4e3e-923a-64f6412ac4e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552446(v=OCS.15)
ms:contentKeyID: 48679557
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ef7679270410df9c7a6ae6f1fa22858bf7a0b53
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035253"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-xmpp-federated-user-access-in-lync-server-2013"></a><span data-ttu-id="99c22-102">Configurar políticas para controlar o acesso de usuário federado do XMPP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99c22-102">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99c22-103">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="99c22-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="99c22-104">Esta é uma documentação preliminar e está sujeita a alterações.</span><span class="sxs-lookup"><span data-stu-id="99c22-104">This is preliminary documentation and is subject to change.</span></span> <span data-ttu-id="99c22-105">Tópicos em branco são incluídos como espaços reservados.</span><span class="sxs-lookup"><span data-stu-id="99c22-105">Blank topics are included as placeholders.</span></span>

<span data-ttu-id="99c22-106">Ao configurar políticas para oferecer suporte a parceiros federados do protocolo XMPP, as políticas aplicam-se a usuários dos domínios XMPP federados, mas não a usuários de provedores de serviços de mensagens instantâneas (IM) do protocolo SIP (por exemplo, Windows Live), ou domínios SIP federados.</span><span class="sxs-lookup"><span data-stu-id="99c22-106">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains.</span></span> <span data-ttu-id="99c22-107">Configure um **Parceiro Federado XMPP** para cada domínio XMPP federado para os quais deseja permitir que seus usuários adicionem contatos e se comuniquem.</span><span class="sxs-lookup"><span data-stu-id="99c22-107">You configure an **XMPP Federated Partner** for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="99c22-108">Políticas de parceiros federados XMPP estão disponíveis somente em um único escopo, e embora não sejam definidas como políticas globais, agem como uma.</span><span class="sxs-lookup"><span data-stu-id="99c22-108">XMPP federated partners policies are only available in a single scope, though it is not defined as a global policy, acts as a global policy.</span></span> <span data-ttu-id="99c22-109">Para definir uma política global, de site ou de usuário para Parceiros Federados XMPP, configure o escopo da política primeiro criando e configurando a Política de Acesso Externo para o escopo necessário.</span><span class="sxs-lookup"><span data-stu-id="99c22-109">To define a global, site or user policy for XMPP Federation Partners, you configure the policy scope by first creating and configuring the External Access Policy for the scope you require.</span></span> <span data-ttu-id="99c22-110">Para obter detalhes sobre os tipos de políticas que você pode configurar para acesso externo e Federação, consulte [Managing Federation and external Access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="99c22-110">For details about the types of policies that you can configure for external access and federation, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) in the Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="99c22-111">Todas as políticas de <STRONG>Federação de Acesso Externo</STRONG> são aplicadas através de provisionamento em banda.</span><span class="sxs-lookup"><span data-stu-id="99c22-111">All <STRONG>Federation and External Access</STRONG> policies are applied through in-band provisioning.</span></span> <span data-ttu-id="99c22-112">As políticas que se aplicam ao usuário, pertencem a um site ou são globais no escopo são comunicadas ao cliente durante o login.</span><span class="sxs-lookup"><span data-stu-id="99c22-112">The policies that apply to the user, belong to a site, or are global in scope are communicated to the client during login.</span></span> <span data-ttu-id="99c22-113">Você pode configurar políticas para controlar o acesso de parceiros federados XMPP, mesmo se não tiver habilitado a federação XMPP para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="99c22-113">You can configure policies to control XMPP federated partner access, even if you have not enabled XMPP federation for your organization.</span></span> <span data-ttu-id="99c22-114">No entanto, as políticas configuradas produzem efeito somente quando você tem a federação de parceiros XMPP implantada, habilitada e configurada para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="99c22-114">However, the policies that you configure take effect only when you have XMPP partner federation deployed, enabled and configured for your organization.</span></span> <span data-ttu-id="99c22-115">Para obter detalhes sobre como implantar e configurar a Federação de parceiros do XMPP, consulte <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">Configuring SIP Federation, XMPP Federation and Public Instant Messaging in Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="99c22-115">For details about deploying and configuring XMPP partner federation, see <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</A> in the Deployment documentation.</span></span> <span data-ttu-id="99c22-116">Além disso, se você especificar uma política de usuário na política de acesso externo para controlar parceiros federados do XMPP, a política se aplicará somente aos usuários habilitados para o Lync Server 2013 e configurados para usar a política.</span><span class="sxs-lookup"><span data-stu-id="99c22-116">Additionally, if you specify a user policy in External Access Policy to control XMPP federated partners, the policy applies only to users that are enabled for Lync Server 2013 and configured to use the policy.</span></span>



</div>

<div>

## <a name="to-edit-a-global-policy-for-xmpp-federated-partners"></a><span data-ttu-id="99c22-117">Para editar uma política global para parceiros federados XMPP</span><span class="sxs-lookup"><span data-stu-id="99c22-117">To edit a global policy for XMPP federated partners</span></span>

1.  <span data-ttu-id="99c22-118">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="99c22-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="99c22-119">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="99c22-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="99c22-120">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="99c22-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="99c22-121">Na barra de navegação à esquerda, clique em **Acesso de Usuário Externo** e clique em **Política de Acesso Externo**.</span><span class="sxs-lookup"><span data-stu-id="99c22-121">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="99c22-122">Na página **Política de Acesso Externo**, faça o seguinte para a política global:</span><span class="sxs-lookup"><span data-stu-id="99c22-122">On the **External Access Policy** page, do the following for the global policy:</span></span>

5.  <span data-ttu-id="99c22-123">Clique na política global, clique em **Editar** e em Exibir detalhes.</span><span class="sxs-lookup"><span data-stu-id="99c22-123">Click the global policy, click **Edit**, and then click Show details.</span></span>

6.  <span data-ttu-id="99c22-124">Forneça uma descrição para a política global (opcional).</span><span class="sxs-lookup"><span data-stu-id="99c22-124">Provide a description for the Global policy (optional).</span></span>

7.  <span data-ttu-id="99c22-125">Selecione **Habilitar comunicações com usuários federados**.</span><span class="sxs-lookup"><span data-stu-id="99c22-125">Select **Enable communications with federated users**.</span></span>

8.  <span data-ttu-id="99c22-126">Selecione **Habilitar comunicações com usuários federados XMPP**.</span><span class="sxs-lookup"><span data-stu-id="99c22-126">Select **Enable communications with XMPP federated users**.</span></span>

9.  <span data-ttu-id="99c22-127">Clique em **Confirmar** para salvar suas alterações na política global.</span><span class="sxs-lookup"><span data-stu-id="99c22-127">Click **Commit** to save your changes to the Global policy.</span></span>

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners"></a><span data-ttu-id="99c22-128">Para criar uma política de site ou de usuário para parceiros federados XMPP</span><span class="sxs-lookup"><span data-stu-id="99c22-128">To create a site or user policy for XMPP federated partners</span></span>

1.  <span data-ttu-id="99c22-p105">Clique em **Novo** e em **Política de site** ou **Política de usuário**. Em **Selecionar um Site**, clique no site apropriado na lista e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="99c22-p105">Click **New**, and then click **Site policy** or **User policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>

2.  <span data-ttu-id="99c22-131">Forneça uma descrição para a política de site (opcional).</span><span class="sxs-lookup"><span data-stu-id="99c22-131">Provide a description for the Site policy (optional).</span></span>

3.  <span data-ttu-id="99c22-132">Na política de site ou de usuário, selecione **Habilitar comunicações com usuários federados**.</span><span class="sxs-lookup"><span data-stu-id="99c22-132">In the site or user policy, select **Enable communications with federated users**.</span></span>

4.  <span data-ttu-id="99c22-133">Selecione **Habilitar comunicações com usuários federados XMPP**.</span><span class="sxs-lookup"><span data-stu-id="99c22-133">Select **Enable communications with XMPP federated users**.</span></span>

5.  <span data-ttu-id="99c22-134">Clique em **Confirmar** para salvar suas alterações na política de site ou de usuário.</span><span class="sxs-lookup"><span data-stu-id="99c22-134">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners"></a><span data-ttu-id="99c22-135">Para editar uma política existente para parceiros federados XMPP</span><span class="sxs-lookup"><span data-stu-id="99c22-135">To edit an existing policy for XMPP federated partners</span></span>

1.  <span data-ttu-id="99c22-136">Para alterar uma política existente, selecione a política desejada na lista, clique em **Editar** e em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="99c22-136">To change an existing policy, select the appropriate policy in the list, click **Edit**, and then click **Show details**.</span></span>

2.  <span data-ttu-id="99c22-137">Altere ou atualize a descrição da política (opcional).</span><span class="sxs-lookup"><span data-stu-id="99c22-137">Change or update the description for the policy (optional).</span></span>

3.  <span data-ttu-id="99c22-138">Marque ou desmarque a opção **Habilitar comunicações com usuários federados**.</span><span class="sxs-lookup"><span data-stu-id="99c22-138">Select or unselect **Enable communications with federated users**.</span></span>

4.  <span data-ttu-id="99c22-139">Marque ou desmarque a opção **Habilitar comunicações com usuários federados XMPP**.</span><span class="sxs-lookup"><span data-stu-id="99c22-139">Select or unselect **Enable communications with XMPP federated users**.</span></span>

5.  <span data-ttu-id="99c22-140">Clique em **Confirmar** para salvar suas alterações na política.</span><span class="sxs-lookup"><span data-stu-id="99c22-140">Click **Commit** to save your changes to the policy.</span></span>

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a><span data-ttu-id="99c22-141">Para editar uma política existente para parceiros federados XMPP usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="99c22-141">To edit an existing policy for XMPP federated partners by using Windows PowerShell</span></span>

1.  <span data-ttu-id="99c22-142">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="99c22-142">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="99c22-143">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="99c22-143">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="99c22-144">Digite o seguinte no Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="99c22-144">Type the following in the Lync Server Management Shell:</span></span>
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    <span data-ttu-id="99c22-145">Um comando de exemplo que definirá a política global para acesso de usuário federado como true (Enabled) e o acesso de domínio XMPP como true (Enabled):</span><span class="sxs-lookup"><span data-stu-id="99c22-145">An example command that will set the global policy for Federated user access to True (enabled) and XMPP domain access to True (enabled):</span></span>
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners-using-windows-powershell"></a><span data-ttu-id="99c22-146">Para criar uma política de site ou de usuário para parceiros federados XMPP usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="99c22-146">To create a site or user policy for XMPP federated partners using Windows PowerShell</span></span>

1.  <span data-ttu-id="99c22-147">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="99c22-147">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="99c22-148">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="99c22-148">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="99c22-149">Digite o seguinte no Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="99c22-149">Type the following in the Lync Server Management Shell:</span></span>
    
        New-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    <span data-ttu-id="99c22-150">Um comando de exemplo que definirá uma política de site para o site Redmond para o acesso de usuários federados como habilitado e acesso ao domínio XMPP como habilitado:</span><span class="sxs-lookup"><span data-stu-id="99c22-150">An example command that will set a site policy for the Redmond site for Federated user access to enabled and XMPP domain access to enabled:</span></span>
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-delete-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a><span data-ttu-id="99c22-151">Para excluir uma política existente para parceiros federados XMPP usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="99c22-151">To delete an existing policy for XMPP federated partners by using Windows PowerShell</span></span>

1.  <span data-ttu-id="99c22-152">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="99c22-152">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="99c22-153">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="99c22-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="99c22-154">Digite o seguinte no Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="99c22-154">Type the following in the Lync Server Management Shell:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>
    
    <span data-ttu-id="99c22-155">Um comando de exemplo que excluirá uma política de usuário:</span><span class="sxs-lookup"><span data-stu-id="99c22-155">An example command that will delete a user policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity EAPUserPolicySetXMPP

4.  <span data-ttu-id="99c22-156">Um comando de exemplo que redefinirá a política global para a configuração padrão:</span><span class="sxs-lookup"><span data-stu-id="99c22-156">An example command that will reset the global policy to defaults:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity global

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="99c22-157">Confira também</span><span class="sxs-lookup"><span data-stu-id="99c22-157">See Also</span></span>


[<span data-ttu-id="99c22-158">Atribuir uma política de acesso de usuário externo a um usuário habilitado do Lync no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99c22-158">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  
[<span data-ttu-id="99c22-159">Habilitar ou desabilitar Federação e conectividade de IM pública no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99c22-159">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  


[<span data-ttu-id="99c22-160">Gerenciar parceiros federados do XMPP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99c22-160">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[<span data-ttu-id="99c22-161">Set-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="99c22-161">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="99c22-162">New-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="99c22-162">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="99c22-163">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="99c22-163">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="99c22-164">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="99c22-164">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="99c22-165">Grant-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="99c22-165">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

