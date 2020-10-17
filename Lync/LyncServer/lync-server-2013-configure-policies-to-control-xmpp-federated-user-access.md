---
title: 'Lync Server 2013: configurar políticas para controlar o acesso de usuário federado do XMPP'
description: 'Lync Server 2013: configurar políticas para controlar o acesso de usuário federado do XMPP.'
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
ms.openlocfilehash: cdb2b7a3da6c00aa7725ecbb69856756f229ed97
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542777"
---
# <a name="configure-policies-to-control-xmpp-federated-user-access-in-lync-server-2013"></a><span data-ttu-id="143f4-103">Configurar políticas para controlar o acesso de usuário federado do XMPP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="143f4-103">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="143f4-104">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="143f4-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="143f4-105">Esta é uma documentação preliminar e está sujeita a alterações.</span><span class="sxs-lookup"><span data-stu-id="143f4-105">This is preliminary documentation and is subject to change.</span></span> <span data-ttu-id="143f4-106">Tópicos em branco são incluídos como espaços reservados.</span><span class="sxs-lookup"><span data-stu-id="143f4-106">Blank topics are included as placeholders.</span></span>

<span data-ttu-id="143f4-107">Ao configurar políticas para oferecer suporte a parceiros federados do protocolo XMPP, as políticas aplicam-se a usuários dos domínios XMPP federados, mas não a usuários de provedores de serviços de mensagens instantâneas (IM) do protocolo SIP (por exemplo, Windows Live), ou domínios SIP federados.</span><span class="sxs-lookup"><span data-stu-id="143f4-107">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains.</span></span> <span data-ttu-id="143f4-108">Configure um **Parceiro Federado XMPP** para cada domínio XMPP federado para os quais deseja permitir que seus usuários adicionem contatos e se comuniquem.</span><span class="sxs-lookup"><span data-stu-id="143f4-108">You configure an **XMPP Federated Partner** for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="143f4-109">Políticas de parceiros federados XMPP estão disponíveis somente em um único escopo, e embora não sejam definidas como políticas globais, agem como uma.</span><span class="sxs-lookup"><span data-stu-id="143f4-109">XMPP federated partners policies are only available in a single scope, though it is not defined as a global policy, acts as a global policy.</span></span> <span data-ttu-id="143f4-110">Para definir uma política global, de site ou de usuário para Parceiros Federados XMPP, configure o escopo da política primeiro criando e configurando a Política de Acesso Externo para o escopo necessário.</span><span class="sxs-lookup"><span data-stu-id="143f4-110">To define a global, site or user policy for XMPP Federation Partners, you configure the policy scope by first creating and configuring the External Access Policy for the scope you require.</span></span> <span data-ttu-id="143f4-111">Para obter detalhes sobre os tipos de políticas que você pode configurar para acesso externo e Federação, consulte [Managing Federation and external Access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="143f4-111">For details about the types of policies that you can configure for external access and federation, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) in the Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="143f4-112">Todas as políticas de <STRONG>Federação de Acesso Externo</STRONG> são aplicadas através de provisionamento em banda.</span><span class="sxs-lookup"><span data-stu-id="143f4-112">All <STRONG>Federation and External Access</STRONG> policies are applied through in-band provisioning.</span></span> <span data-ttu-id="143f4-113">As políticas que se aplicam ao usuário, pertencem a um site ou são globais no escopo são comunicadas ao cliente durante o login.</span><span class="sxs-lookup"><span data-stu-id="143f4-113">The policies that apply to the user, belong to a site, or are global in scope are communicated to the client during login.</span></span> <span data-ttu-id="143f4-114">Você pode configurar políticas para controlar o acesso de parceiros federados XMPP, mesmo se não tiver habilitado a federação XMPP para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="143f4-114">You can configure policies to control XMPP federated partner access, even if you have not enabled XMPP federation for your organization.</span></span> <span data-ttu-id="143f4-115">No entanto, as políticas configuradas produzem efeito somente quando você tem a federação de parceiros XMPP implantada, habilitada e configurada para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="143f4-115">However, the policies that you configure take effect only when you have XMPP partner federation deployed, enabled and configured for your organization.</span></span> <span data-ttu-id="143f4-116">Para obter detalhes sobre como implantar e configurar a Federação de parceiros do XMPP, consulte <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">Configuring SIP Federation, XMPP Federation and Public Instant Messaging in Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="143f4-116">For details about deploying and configuring XMPP partner federation, see <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</A> in the Deployment documentation.</span></span> <span data-ttu-id="143f4-117">Além disso, se você especificar uma política de usuário na política de acesso externo para controlar parceiros federados do XMPP, a política se aplicará somente aos usuários habilitados para o Lync Server 2013 e configurados para usar a política.</span><span class="sxs-lookup"><span data-stu-id="143f4-117">Additionally, if you specify a user policy in External Access Policy to control XMPP federated partners, the policy applies only to users that are enabled for Lync Server 2013 and configured to use the policy.</span></span>



</div>

<div>

## <a name="to-edit-a-global-policy-for-xmpp-federated-partners"></a><span data-ttu-id="143f4-118">Para editar uma política global para parceiros federados XMPP</span><span class="sxs-lookup"><span data-stu-id="143f4-118">To edit a global policy for XMPP federated partners</span></span>

1.  <span data-ttu-id="143f4-119">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="143f4-119">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="143f4-120">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="143f4-120">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="143f4-121">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="143f4-121">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="143f4-122">Na barra de navegação à esquerda, clique em **Acesso de Usuário Externo** e clique em **Política de Acesso Externo**.</span><span class="sxs-lookup"><span data-stu-id="143f4-122">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="143f4-123">Na página **Política de Acesso Externo**, faça o seguinte para a política global:</span><span class="sxs-lookup"><span data-stu-id="143f4-123">On the **External Access Policy** page, do the following for the global policy:</span></span>

5.  <span data-ttu-id="143f4-124">Clique na política global, clique em **Editar** e em Exibir detalhes.</span><span class="sxs-lookup"><span data-stu-id="143f4-124">Click the global policy, click **Edit**, and then click Show details.</span></span>

6.  <span data-ttu-id="143f4-125">Forneça uma descrição para a política global (opcional).</span><span class="sxs-lookup"><span data-stu-id="143f4-125">Provide a description for the Global policy (optional).</span></span>

7.  <span data-ttu-id="143f4-126">Selecione **Habilitar comunicações com usuários federados**.</span><span class="sxs-lookup"><span data-stu-id="143f4-126">Select **Enable communications with federated users**.</span></span>

8.  <span data-ttu-id="143f4-127">Selecione **Habilitar comunicações com usuários federados XMPP**.</span><span class="sxs-lookup"><span data-stu-id="143f4-127">Select **Enable communications with XMPP federated users**.</span></span>

9.  <span data-ttu-id="143f4-128">Clique em **Confirmar** para salvar suas alterações na política global.</span><span class="sxs-lookup"><span data-stu-id="143f4-128">Click **Commit** to save your changes to the Global policy.</span></span>

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners"></a><span data-ttu-id="143f4-129">Para criar uma política de site ou de usuário para parceiros federados XMPP</span><span class="sxs-lookup"><span data-stu-id="143f4-129">To create a site or user policy for XMPP federated partners</span></span>

1.  <span data-ttu-id="143f4-p105">Clique em **Novo** e em **Política de site** ou **Política de usuário**. Em **Selecionar um Site**, clique no site apropriado na lista e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="143f4-p105">Click **New**, and then click **Site policy** or **User policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>

2.  <span data-ttu-id="143f4-132">Forneça uma descrição para a política de site (opcional).</span><span class="sxs-lookup"><span data-stu-id="143f4-132">Provide a description for the Site policy (optional).</span></span>

3.  <span data-ttu-id="143f4-133">Na política de site ou de usuário, selecione **Habilitar comunicações com usuários federados**.</span><span class="sxs-lookup"><span data-stu-id="143f4-133">In the site or user policy, select **Enable communications with federated users**.</span></span>

4.  <span data-ttu-id="143f4-134">Selecione **Habilitar comunicações com usuários federados XMPP**.</span><span class="sxs-lookup"><span data-stu-id="143f4-134">Select **Enable communications with XMPP federated users**.</span></span>

5.  <span data-ttu-id="143f4-135">Clique em **Confirmar** para salvar suas alterações na política de site ou de usuário.</span><span class="sxs-lookup"><span data-stu-id="143f4-135">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners"></a><span data-ttu-id="143f4-136">Para editar uma política existente para parceiros federados XMPP</span><span class="sxs-lookup"><span data-stu-id="143f4-136">To edit an existing policy for XMPP federated partners</span></span>

1.  <span data-ttu-id="143f4-137">Para alterar uma política existente, selecione a política desejada na lista, clique em **Editar** e em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="143f4-137">To change an existing policy, select the appropriate policy in the list, click **Edit**, and then click **Show details**.</span></span>

2.  <span data-ttu-id="143f4-138">Altere ou atualize a descrição da política (opcional).</span><span class="sxs-lookup"><span data-stu-id="143f4-138">Change or update the description for the policy (optional).</span></span>

3.  <span data-ttu-id="143f4-139">Marque ou desmarque a opção **Habilitar comunicações com usuários federados**.</span><span class="sxs-lookup"><span data-stu-id="143f4-139">Select or unselect **Enable communications with federated users**.</span></span>

4.  <span data-ttu-id="143f4-140">Marque ou desmarque a opção **Habilitar comunicações com usuários federados XMPP**.</span><span class="sxs-lookup"><span data-stu-id="143f4-140">Select or unselect **Enable communications with XMPP federated users**.</span></span>

5.  <span data-ttu-id="143f4-141">Clique em **Confirmar** para salvar suas alterações na política.</span><span class="sxs-lookup"><span data-stu-id="143f4-141">Click **Commit** to save your changes to the policy.</span></span>

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a><span data-ttu-id="143f4-142">Para editar uma política existente para parceiros federados XMPP usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="143f4-142">To edit an existing policy for XMPP federated partners by using Windows PowerShell</span></span>

1.  <span data-ttu-id="143f4-143">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="143f4-143">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="143f4-144">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="143f4-144">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="143f4-145">Digite o seguinte no Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="143f4-145">Type the following in the Lync Server Management Shell:</span></span>
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    <span data-ttu-id="143f4-146">Um comando de exemplo que definirá a política global para acesso de usuário federado como true (Enabled) e o acesso de domínio XMPP como true (Enabled):</span><span class="sxs-lookup"><span data-stu-id="143f4-146">An example command that will set the global policy for Federated user access to True (enabled) and XMPP domain access to True (enabled):</span></span>
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners-using-windows-powershell"></a><span data-ttu-id="143f4-147">Para criar uma política de site ou de usuário para parceiros federados XMPP usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="143f4-147">To create a site or user policy for XMPP federated partners using Windows PowerShell</span></span>

1.  <span data-ttu-id="143f4-148">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="143f4-148">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="143f4-149">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="143f4-149">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="143f4-150">Digite o seguinte no Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="143f4-150">Type the following in the Lync Server Management Shell:</span></span>
    
        New-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    <span data-ttu-id="143f4-151">Um comando de exemplo que definirá uma política de site para o site Redmond para o acesso de usuários federados como habilitado e acesso ao domínio XMPP como habilitado:</span><span class="sxs-lookup"><span data-stu-id="143f4-151">An example command that will set a site policy for the Redmond site for Federated user access to enabled and XMPP domain access to enabled:</span></span>
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-delete-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a><span data-ttu-id="143f4-152">Para excluir uma política existente para parceiros federados XMPP usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="143f4-152">To delete an existing policy for XMPP federated partners by using Windows PowerShell</span></span>

1.  <span data-ttu-id="143f4-153">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="143f4-153">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="143f4-154">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="143f4-154">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="143f4-155">Digite o seguinte no Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="143f4-155">Type the following in the Lync Server Management Shell:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>
    
    <span data-ttu-id="143f4-156">Um comando de exemplo que excluirá uma política de usuário:</span><span class="sxs-lookup"><span data-stu-id="143f4-156">An example command that will delete a user policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity EAPUserPolicySetXMPP

4.  <span data-ttu-id="143f4-157">Um comando de exemplo que redefinirá a política global para a configuração padrão:</span><span class="sxs-lookup"><span data-stu-id="143f4-157">An example command that will reset the global policy to defaults:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity global

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="143f4-158">Confira também</span><span class="sxs-lookup"><span data-stu-id="143f4-158">See Also</span></span>


[<span data-ttu-id="143f4-159">Atribuir uma política de acesso de usuário externo a um usuário habilitado do Lync no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="143f4-159">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  
[<span data-ttu-id="143f4-160">Habilitar ou desabilitar Federação e conectividade de IM pública no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="143f4-160">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  


[<span data-ttu-id="143f4-161">Gerenciar parceiros federados do XMPP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="143f4-161">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[<span data-ttu-id="143f4-162">Set-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="143f4-162">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="143f4-163">New-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="143f4-163">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="143f4-164">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="143f4-164">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="143f4-165">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="143f4-165">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="143f4-166">Grant-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="143f4-166">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

