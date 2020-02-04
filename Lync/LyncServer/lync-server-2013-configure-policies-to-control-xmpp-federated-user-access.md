---
title: 'Lync Server 2013: Configurar políticas para controlar o acesso de usuário federado'
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
ms.openlocfilehash: cc79a915d0735f87c0852dff0ba4228b1e391fd8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730021"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-xmpp-federated-user-access-in-lync-server-2013"></a><span data-ttu-id="9bf5a-102">Configurar políticas para controlar o acesso de usuário federado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9bf5a-102">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9bf5a-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="9bf5a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="9bf5a-104">Esta documentação é preliminar e está sujeita a alterações.</span><span class="sxs-lookup"><span data-stu-id="9bf5a-104">This is preliminary documentation and is subject to change.</span></span> <span data-ttu-id="9bf5a-105">Os tópicos em branco são incluídos como espaços reservados.</span><span class="sxs-lookup"><span data-stu-id="9bf5a-105">Blank topics are included as placeholders.</span></span>

<span data-ttu-id="9bf5a-106">Quando você configura políticas para dar suporte a parceiros federados do protocolo de Unificação de mensagens e de protocolo de presença (XMPP), as políticas se aplicam a usuários de domínios federados XMPP, mas não aos usuários de provedores de serviços de mensagens instantâneas SIP (protocolo de iniciação de sessão) (por exemplo, Windows Live) ou domínios federados SIP.</span><span class="sxs-lookup"><span data-stu-id="9bf5a-106">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains.</span></span> <span data-ttu-id="9bf5a-107">Você configura um **parceiro federado do XMPP** para cada domínio federado XMPP que você deseja permitir que os usuários adicionem contatos e se comuniquem.</span><span class="sxs-lookup"><span data-stu-id="9bf5a-107">You configure an **XMPP Federated Partner** for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="9bf5a-108">As políticas de parceiros federados do XMPP só estão disponíveis em um único escopo, embora não seja definida como uma política global, atua como uma política global.</span><span class="sxs-lookup"><span data-stu-id="9bf5a-108">XMPP federated partners policies are only available in a single scope, though it is not defined as a global policy, acts as a global policy.</span></span> <span data-ttu-id="9bf5a-109">Para definir uma política global, de site ou de usuário para parceiros de Federação do XMPP, configure o escopo da política primeiro criando e configurando a política de acesso externo para o escopo que você precisa.</span><span class="sxs-lookup"><span data-stu-id="9bf5a-109">To define a global, site or user policy for XMPP Federation Partners, you configure the policy scope by first creating and configuring the External Access Policy for the scope you require.</span></span> <span data-ttu-id="9bf5a-110">Para obter detalhes sobre os tipos de políticas que você pode configurar para acesso externo e Federação, consulte [Gerenciando a Federação e acesso externo ao Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) na documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="9bf5a-110">For details about the types of policies that you can configure for external access and federation, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) in the Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9bf5a-111">Todas as políticas <STRONG>de acesso externo e agrupamento</STRONG> são aplicadas por meio do provisionamento em banda.</span><span class="sxs-lookup"><span data-stu-id="9bf5a-111">All <STRONG>Federation and External Access</STRONG> policies are applied through in-band provisioning.</span></span> <span data-ttu-id="9bf5a-112">As políticas que se aplicam ao usuário, pertencem a um site ou são globais em escopo são comunicadas ao cliente durante o logon.</span><span class="sxs-lookup"><span data-stu-id="9bf5a-112">The policies that apply to the user, belong to a site, or are global in scope are communicated to the client during login.</span></span> <span data-ttu-id="9bf5a-113">Você pode configurar políticas para controlar o acesso do parceiro federado do XMPP, mesmo se você não tiver habilitado a Federação do XMPP para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="9bf5a-113">You can configure policies to control XMPP federated partner access, even if you have not enabled XMPP federation for your organization.</span></span> <span data-ttu-id="9bf5a-114">No entanto, as políticas que você configura entram em vigor apenas quando você tem a Federação de parceiro do XMPP implantada, habilitada e configurada para sua organização.</span><span class="sxs-lookup"><span data-stu-id="9bf5a-114">However, the policies that you configure take effect only when you have XMPP partner federation deployed, enabled and configured for your organization.</span></span> <span data-ttu-id="9bf5a-115">Para obter detalhes sobre como implantar e configurar a Federação de parceiro do XMPP, consulte <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">Configurando Federação SIP, agrupamento XMPP e mensagens instantâneas públicas no Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="9bf5a-115">For details about deploying and configuring XMPP partner federation, see <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</A> in the Deployment documentation.</span></span> <span data-ttu-id="9bf5a-116">Além disso, se você especificar uma política de usuário na política de acesso externo para controlar os parceiros federados do XMPP, a política se aplicará somente aos usuários habilitados para o Lync Server 2013 e configurados para usar a política.</span><span class="sxs-lookup"><span data-stu-id="9bf5a-116">Additionally, if you specify a user policy in External Access Policy to control XMPP federated partners, the policy applies only to users that are enabled for Lync Server 2013 and configured to use the policy.</span></span>



</div>

<div>

## <a name="to-edit-a-global-policy-for-xmpp-federated-partners"></a><span data-ttu-id="9bf5a-117">Para editar uma política global para parceiros federados XMPP</span><span class="sxs-lookup"><span data-stu-id="9bf5a-117">To edit a global policy for XMPP federated partners</span></span>

1.  <span data-ttu-id="9bf5a-118">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="9bf5a-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9bf5a-119">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9bf5a-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9bf5a-120">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9bf5a-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9bf5a-121">Na barra de navegação à esquerda, clique em **acesso ao usuário externo**e, em seguida, clique em **política de acesso externo**.</span><span class="sxs-lookup"><span data-stu-id="9bf5a-121">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="9bf5a-122">Na página **política de acesso externo** , faça o seguinte para a política global:</span><span class="sxs-lookup"><span data-stu-id="9bf5a-122">On the **External Access Policy** page, do the following for the global policy:</span></span>

5.  <span data-ttu-id="9bf5a-123">Clique na política global, clique em **Editar**e, em seguida, clique em mostrar detalhes.</span><span class="sxs-lookup"><span data-stu-id="9bf5a-123">Click the global policy, click **Edit**, and then click Show details.</span></span>

6.  <span data-ttu-id="9bf5a-124">Forneça uma descrição para a política global (opcional).</span><span class="sxs-lookup"><span data-stu-id="9bf5a-124">Provide a description for the Global policy (optional).</span></span>

7.  <span data-ttu-id="9bf5a-125">Selecione **habilitar comunicações com usuários federados**.</span><span class="sxs-lookup"><span data-stu-id="9bf5a-125">Select **Enable communications with federated users**.</span></span>

8.  <span data-ttu-id="9bf5a-126">Selecione **habilitar comunicações com usuários federados do XMPP**.</span><span class="sxs-lookup"><span data-stu-id="9bf5a-126">Select **Enable communications with XMPP federated users**.</span></span>

9.  <span data-ttu-id="9bf5a-127">Clique em **confirmar** para salvar as alterações na política global.</span><span class="sxs-lookup"><span data-stu-id="9bf5a-127">Click **Commit** to save your changes to the Global policy.</span></span>

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners"></a><span data-ttu-id="9bf5a-128">Para criar uma política de site ou de usuário para parceiros federados XMPP</span><span class="sxs-lookup"><span data-stu-id="9bf5a-128">To create a site or user policy for XMPP federated partners</span></span>

1.  <span data-ttu-id="9bf5a-129">Clique em **novo**e, em seguida, clique em política do **site** ou **política do usuário**.</span><span class="sxs-lookup"><span data-stu-id="9bf5a-129">Click **New**, and then click **Site policy** or **User policy**.</span></span> <span data-ttu-id="9bf5a-130">Em **selecionar um site**, clique no site apropriado na lista e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9bf5a-130">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>

2.  <span data-ttu-id="9bf5a-131">Forneça uma descrição para a política de site (opcional).</span><span class="sxs-lookup"><span data-stu-id="9bf5a-131">Provide a description for the Site policy (optional).</span></span>

3.  <span data-ttu-id="9bf5a-132">Na política do site ou do usuário, selecione **habilitar comunicações com usuários federados**.</span><span class="sxs-lookup"><span data-stu-id="9bf5a-132">In the site or user policy, select **Enable communications with federated users**.</span></span>

4.  <span data-ttu-id="9bf5a-133">Selecione **habilitar comunicações com usuários federados do XMPP**.</span><span class="sxs-lookup"><span data-stu-id="9bf5a-133">Select **Enable communications with XMPP federated users**.</span></span>

5.  <span data-ttu-id="9bf5a-134">Clique em **confirmar** para salvar as alterações no site ou na política de usuário.</span><span class="sxs-lookup"><span data-stu-id="9bf5a-134">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners"></a><span data-ttu-id="9bf5a-135">Para editar uma política existente para parceiros federados XMPP</span><span class="sxs-lookup"><span data-stu-id="9bf5a-135">To edit an existing policy for XMPP federated partners</span></span>

1.  <span data-ttu-id="9bf5a-136">Para alterar uma política existente, selecione a política apropriada na lista, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="9bf5a-136">To change an existing policy, select the appropriate policy in the list, click **Edit**, and then click **Show details**.</span></span>

2.  <span data-ttu-id="9bf5a-137">Altere ou atualize a descrição da política (opcional).</span><span class="sxs-lookup"><span data-stu-id="9bf5a-137">Change or update the description for the policy (optional).</span></span>

3.  <span data-ttu-id="9bf5a-138">Marque ou desmarque **habilitar comunicações com usuários federados**.</span><span class="sxs-lookup"><span data-stu-id="9bf5a-138">Select or unselect **Enable communications with federated users**.</span></span>

4.  <span data-ttu-id="9bf5a-139">Marque ou desmarque **habilitar comunicações com usuários federados do XMPP**.</span><span class="sxs-lookup"><span data-stu-id="9bf5a-139">Select or unselect **Enable communications with XMPP federated users**.</span></span>

5.  <span data-ttu-id="9bf5a-140">Clique em **confirmar** para salvar as alterações na política.</span><span class="sxs-lookup"><span data-stu-id="9bf5a-140">Click **Commit** to save your changes to the policy.</span></span>

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a><span data-ttu-id="9bf5a-141">Para editar uma política existente para parceiros federados do XMPP usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9bf5a-141">To edit an existing policy for XMPP federated partners by using Windows PowerShell</span></span>

1.  <span data-ttu-id="9bf5a-142">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="9bf5a-142">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9bf5a-143">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="9bf5a-143">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="9bf5a-144">Digite o seguinte no Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="9bf5a-144">Type the following in the Lync Server Management Shell:</span></span>
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    <span data-ttu-id="9bf5a-145">Um exemplo de comando que define a política global para acesso de usuário federado a true (Enabled) e o acesso de domínio XMPP para true (Enabled):</span><span class="sxs-lookup"><span data-stu-id="9bf5a-145">An example command that will set the global policy for Federated user access to True (enabled) and XMPP domain access to True (enabled):</span></span>
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners-using-windows-powershell"></a><span data-ttu-id="9bf5a-146">Para criar uma política de site ou de usuário para parceiros federados do XMPP usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9bf5a-146">To create a site or user policy for XMPP federated partners using Windows PowerShell</span></span>

1.  <span data-ttu-id="9bf5a-147">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="9bf5a-147">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9bf5a-148">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="9bf5a-148">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="9bf5a-149">Digite o seguinte no Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="9bf5a-149">Type the following in the Lync Server Management Shell:</span></span>
    
        New-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    <span data-ttu-id="9bf5a-150">Um exemplo de comando que definirá uma política de site para o site Redmond para acesso de usuário federado ao acesso de domínio habilitado e XMPP como habilitado:</span><span class="sxs-lookup"><span data-stu-id="9bf5a-150">An example command that will set a site policy for the Redmond site for Federated user access to enabled and XMPP domain access to enabled:</span></span>
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-delete-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a><span data-ttu-id="9bf5a-151">Para excluir uma política existente para parceiros federados do XMPP usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9bf5a-151">To delete an existing policy for XMPP federated partners by using Windows PowerShell</span></span>

1.  <span data-ttu-id="9bf5a-152">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="9bf5a-152">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9bf5a-153">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="9bf5a-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="9bf5a-154">Digite o seguinte no Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="9bf5a-154">Type the following in the Lync Server Management Shell:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>
    
    <span data-ttu-id="9bf5a-155">Um exemplo de comando que excluirá uma política de usuário:</span><span class="sxs-lookup"><span data-stu-id="9bf5a-155">An example command that will delete a user policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity EAPUserPolicySetXMPP

4.  <span data-ttu-id="9bf5a-156">Um exemplo de comando que irá redefinir a política global para padrões:</span><span class="sxs-lookup"><span data-stu-id="9bf5a-156">An example command that will reset the global policy to defaults:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity global

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9bf5a-157">Confira também</span><span class="sxs-lookup"><span data-stu-id="9bf5a-157">See Also</span></span>


[<span data-ttu-id="9bf5a-158">Atribuir uma política de usuário externo a um usuário habilitado do Lync no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9bf5a-158">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  
[<span data-ttu-id="9bf5a-159">Habilitar ou desabilitar federação e conectividade de IM pública no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9bf5a-159">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  


[<span data-ttu-id="9bf5a-160">Gerenciar parceiros XMPP federados no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9bf5a-160">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[<span data-ttu-id="9bf5a-161">Set-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="9bf5a-161">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="9bf5a-162">New-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="9bf5a-162">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="9bf5a-163">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="9bf5a-163">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="9bf5a-164">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="9bf5a-164">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="9bf5a-165">Grant CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="9bf5a-165">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

