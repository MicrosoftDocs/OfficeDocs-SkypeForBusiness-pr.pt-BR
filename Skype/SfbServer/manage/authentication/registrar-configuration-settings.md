---
title: Gerenciar definições de configuração de registrador no Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
description: 'Resumo: Gerencie definições de configuração de registrador para Skype para Business Server.'
ms.openlocfilehash: fdeca4389ffb64bd68cb3aee7ba6b28e979c5769
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901505"
---
# <a name="manage-registrar-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="a33a8-103">Gerenciar definições de configuração de registrador no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="a33a8-103">Manage Registrar configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="a33a8-104">**Resumo:** Gerencie definições de configuração de registrador para Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="a33a8-104">**Summary:** Manage Registrar configuration settings for Skype for Business Server.</span></span>
  
<span data-ttu-id="a33a8-p101">É possível usar o Registrador para configurar métodos de autenticação do servidor proxy. O protocolo de autenticação que você especificar determina que tipo de desafios os servidores no pool vão gerar para os clientes. Os protocolos disponíveis são:</span><span class="sxs-lookup"><span data-stu-id="a33a8-p101">You can use the Registrar to configure proxy server authentication methods. The authentication protocol you specify determines which type of challenges the servers in the pool issue to clients. The available protocols are:</span></span>
  
- <span data-ttu-id="a33a8-108">**Kerberos** Este é o mais forte esquema de autenticação baseada em senha disponível para os clientes, mas é normalmente disponível somente para clientes empresariais porque ele requer a conexão do cliente para um centro de distribuição de chaves (controlador de domínio Kerberos).</span><span class="sxs-lookup"><span data-stu-id="a33a8-108">**Kerberos** This is the strongest password-based authentication scheme available to clients, but it is normally available only to enterprise clients because it requires client connection to a Key Distribution Center (Kerberos domain controller).</span></span> <span data-ttu-id="a33a8-109">Essa configuração será apropriada se o servidor autenticar somente clientes empresariais.</span><span class="sxs-lookup"><span data-stu-id="a33a8-109">This setting is appropriate if the server authenticates only enterprise clients.</span></span>
    
- <span data-ttu-id="a33a8-110">**NTLM** Esta é a autenticação baseada em senha disponível para os clientes que usam um esquema de hash de desafio-resposta na senha.</span><span class="sxs-lookup"><span data-stu-id="a33a8-110">**NTLM** This is the password-based authentication available to clients that use a challenge-response hashing scheme on the password.</span></span> <span data-ttu-id="a33a8-111">Essa é a única forma de autenticação disponível para clientes sem conectividade com um Centro de distribuição de chaves (controlador de domínio Kerberos), como usuários remotos.</span><span class="sxs-lookup"><span data-stu-id="a33a8-111">This is the only form of authentication available to clients without connectivity to a Key Distribution Center (Kerberos domain controller), such as remote users.</span></span> <span data-ttu-id="a33a8-112">Se um servidor autenticar somente usuários remotos, escolha NTLM.</span><span class="sxs-lookup"><span data-stu-id="a33a8-112">If a server authenticates only remote users, you should choose NTLM.</span></span>
    
- <span data-ttu-id="a33a8-113">**Autenticação de certificado** Este é o novo método de autenticação quando o servidor precisa obter certificados de clientes do Lync Phone Edition, telefones de área comum, Skype para a empresa e o aplicativo da Windows Store do Lync.</span><span class="sxs-lookup"><span data-stu-id="a33a8-113">**Certificate authentication** This is the new authentication method when the server needs to obtain certificates from Lync Phone Edition clients, common area phones, Skype for Business and the Lync Windows Store app.</span></span> <span data-ttu-id="a33a8-114">Nos clientes do Lync Phone Edition, depois que um usuário entra no e é autenticado com êxito, fornecendo um número de identificação pessoal (PIN), Skype para Business Server e provisiona o URI do SIP para o telefone e provisiona um Skype para Business Server assinado certificado ou um certificado de usuário que identifica Joe (ex.: SN=joe@contoso.com) para o telefone.</span><span class="sxs-lookup"><span data-stu-id="a33a8-114">On Lync Phone Edition clients, after a user signs in and is successfully authenticated by providing a personal identification number (PIN), Skype for Business Server then provisions the SIP URI to the phone and provisions a Skype for Business Server signed certificate or a user certificate that identifies Joe (Ex: SN=joe@contoso.com ) to the phone.</span></span> <span data-ttu-id="a33a8-115">This certificate is used for authenticating with the Registrar and Web Services.</span><span class="sxs-lookup"><span data-stu-id="a33a8-115">This certificate is used for authenticating with the Registrar and Web Services.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a33a8-p105">Recomendamos a habilitação do Kerberos e NTLM quando um servidor suporta autenticação para clientes remotos e empresariais. O Servidor de Borda e os servidores internos se comunicam para assegurar que somente a autenticação NTLM seja oferecida aos clientes remotos. Se somente Kerberos for habilitado nesses servidores, não poderão autenticar usuários remotos. Se os usuários empresariais também autenticarem com base no servidor, o Kerberos será usado.</span><span class="sxs-lookup"><span data-stu-id="a33a8-p105">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients. The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients. If only Kerberos is enabled on these servers, they cannot authenticate remote users. If enterprise users also authenticate against the server, Kerberos is used.</span></span> 
  
<span data-ttu-id="a33a8-120">Se você usará a clientes de aplicativo da Windows Store do Lync, você deverá habilitar a autenticação de certificado.</span><span class="sxs-lookup"><span data-stu-id="a33a8-120">If you will use Lync Windows Store app clients, you must enable certificate authentication.</span></span>
  
### <a name="to-create-new-registrar-configuration-settings"></a><span data-ttu-id="a33a8-121">Para criar novas configurações de Registrador</span><span class="sxs-lookup"><span data-stu-id="a33a8-121">To create new Registrar configuration settings</span></span>

1.  <span data-ttu-id="a33a8-122">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes), ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon no qualquer computador que esteja na rede em que você implantou Skype para Business Server .</span><span class="sxs-lookup"><span data-stu-id="a33a8-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="a33a8-123">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="a33a8-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="a33a8-124">Na barra de navegação esquerda, clique em **Segurança** e em **Registrador**.</span><span class="sxs-lookup"><span data-stu-id="a33a8-124">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="a33a8-125">Na página **Registrado**, clique em **Novo**</span><span class="sxs-lookup"><span data-stu-id="a33a8-125">On the **Registrar** page, click **New**</span></span>
    
5. <span data-ttu-id="a33a8-126">Em **Selecionar um Serviço**, clique no serviço ao qual o Registrador será aplicado e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a33a8-126">In **Select a Service**, click the service to which the Registrar is to be applied and then click **OK**.</span></span>
    
6. <span data-ttu-id="a33a8-127">Em **Nova Configuração do Registrador**, selecione uma ou mais das seguintes opções, dependendo dos recursos dos clientes e do suporte em seu ambiente:</span><span class="sxs-lookup"><span data-stu-id="a33a8-127">In **New Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="a33a8-128">**Habilitar autenticação Kerberos** para que os servidores no pool emitam desafios usando a autenticação Kerberos.</span><span class="sxs-lookup"><span data-stu-id="a33a8-128">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
   - <span data-ttu-id="a33a8-129">**Habilitar autenticação NTLM** para que os servidores no pool emitam desafios usando NTLM.</span><span class="sxs-lookup"><span data-stu-id="a33a8-129">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
   - <span data-ttu-id="a33a8-130">**Habilitar autenticação de certificado** para que os servidores no pool emitam certificados para os clientes.</span><span class="sxs-lookup"><span data-stu-id="a33a8-130">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
7. <span data-ttu-id="a33a8-131">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="a33a8-131">Click **Commit**.</span></span>
    
## <a name="modify-existing-registrar-configuration-settings"></a><span data-ttu-id="a33a8-132">Modificar as configurações existentes do Registrador</span><span class="sxs-lookup"><span data-stu-id="a33a8-132">Modify existing Registrar configuration settings</span></span>

<span data-ttu-id="a33a8-133">Você pode usar o Registrador para configurar protocolos de autenticação de servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="a33a8-133">You can use the Registrar to configure proxy server authentication protocols.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a33a8-p106">Recomendamos a habilitação do Kerberos e NTLM quando um servidor suporta autenticação para clientes remotos e empresariais. O Servidor de Borda e os servidores internos se comunicam para assegurar que somente a autenticação NTLM seja oferecida aos clientes remotos. Se somente Kerberos for habilitado nesses servidores, não poderão autenticar usuários remotos. Se os usuários empresariais também autenticarem com base no servidor, o Kerberos será usado.</span><span class="sxs-lookup"><span data-stu-id="a33a8-p106">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients. The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients. If only Kerberos is enabled on these servers, they cannot authenticate remote users. If enterprise users also authenticate against the server, Kerberos is used.</span></span> 
  
<span data-ttu-id="a33a8-138">Siga estas etapas para modificar um Registrador Avançado existente.</span><span class="sxs-lookup"><span data-stu-id="a33a8-138">Follow these steps to modify an existing Registrar.</span></span> 
  
### <a name="to-modify-existing-registrar-configuration-settings"></a><span data-ttu-id="a33a8-139">Para modificar as configurações existentes do Registrador</span><span class="sxs-lookup"><span data-stu-id="a33a8-139">To modify existing registrar configuration settings</span></span>

1.  <span data-ttu-id="a33a8-140">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes), ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon no qualquer computador que esteja na rede em que você implantou Skype para Business Server .</span><span class="sxs-lookup"><span data-stu-id="a33a8-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="a33a8-141">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="a33a8-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="a33a8-142">Na barra de navegação esquerda, clique em **Segurança** e em **Registrador**.</span><span class="sxs-lookup"><span data-stu-id="a33a8-142">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="a33a8-143">Na página **Registrador Avançado**, clique em um serviço, em **Editar** e em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="a33a8-143">On the **Registrar** page, click a service, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="a33a8-144">Em **Editar Configuração do Registrador Avançado**, selecione um ou mais dos itens a seguir, dependendo dos recursos dos clientes e do suporte em seu ambiente:</span><span class="sxs-lookup"><span data-stu-id="a33a8-144">In **Edit Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="a33a8-145">**Habilitar autenticação Kerberos** para que os servidores no pool emitam desafios usando a autenticação Kerberos.</span><span class="sxs-lookup"><span data-stu-id="a33a8-145">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
   - <span data-ttu-id="a33a8-146">**Habilitar autenticação NTLM** para que os servidores no pool emitam desafios usando NTLM.</span><span class="sxs-lookup"><span data-stu-id="a33a8-146">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
   - <span data-ttu-id="a33a8-147">**Habilitar autenticação de certificado** para que os servidores no pool emitam certificados para os clientes.</span><span class="sxs-lookup"><span data-stu-id="a33a8-147">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
6. <span data-ttu-id="a33a8-148">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="a33a8-148">Click **Commit**.</span></span>
    
### <a name="to-delete-registrar-configuration-settings"></a><span data-ttu-id="a33a8-149">Para excluir as definições de configuração do Registrador</span><span class="sxs-lookup"><span data-stu-id="a33a8-149">To delete Registrar configuration settings</span></span>

1. <span data-ttu-id="a33a8-150">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes), ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon no qualquer computador que esteja na rede em que você implantou Skype para Business Server .</span><span class="sxs-lookup"><span data-stu-id="a33a8-150">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="a33a8-151">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="a33a8-151">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="a33a8-152">Na barra de navegação esquerda, clique em **Segurança** e em **Registrador**.</span><span class="sxs-lookup"><span data-stu-id="a33a8-152">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="a33a8-153">Na página **Registrador Avançado** e no campo de pesquisa, digite todo ou parte do nome do Registrador Avançado que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="a33a8-153">On the **Registrar** page, and in the search field, type all or part of the name of the Registrar you want to delete.</span></span>
    
5. <span data-ttu-id="a33a8-154">Na lista, clique no Registrador Avançado desejado, clique em **Editar** e em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="a33a8-154">In the list, click the Registrar that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="a33a8-155">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a33a8-155">Click **OK**.</span></span>
    
## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a33a8-156">Removendo definições de configuração de registrador usando Cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a33a8-156">Removing Registrar Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a33a8-157">Você pode excluir as definições de configuração do registrador usando o Windows PowerShell e o cmdlet **Remove-CsProxyConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="a33a8-157">You can delete the Registrar configuration settings by using Windows PowerShell and the **Remove-CsProxyConfiguration** cmdlet.</span></span> <span data-ttu-id="a33a8-158">Você pode executar esse cmdlet a partir do Skype do Shell de gerenciamento do servidor de negócios ou uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a33a8-158">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a33a8-159">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype para Business Server, consulte o artigo do blog ["rápida iniciar: Gerenciando Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="a33a8-159">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="a33a8-160">O processo é o mesmo em Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="a33a8-160">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specific-set-of-registrar-security-settings"></a><span data-ttu-id="a33a8-161">Para remover um conjunto específico de configurações de segurança do Registrador</span><span class="sxs-lookup"><span data-stu-id="a33a8-161">To remove a specific set of Registrar security settings</span></span>

- <span data-ttu-id="a33a8-162">O seguinte comando remove as configurações de segurança do Registrador aplicadas ao servidor de borda atl-edge-011.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="a33a8-162">The following command removes the Registrar security settings applied to the edge Server atl-edge-011.litwareinc.com:</span></span>
    
  ```
  Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a><span data-ttu-id="a33a8-163">Para remover todas as configurações de segurança do Registrador aplicadas ao escopo do site</span><span class="sxs-lookup"><span data-stu-id="a33a8-163">To remove all of the Registrar security settings applied to the site scope</span></span>

- <span data-ttu-id="a33a8-164">O seguinte comando remove todas as configurações de segurança do Registrador aplicadas ao serviço registrador:</span><span class="sxs-lookup"><span data-stu-id="a33a8-164">The following command removes all the Registrar security settings applied to the Registrar service:</span></span>
    
  ```
  Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a><span data-ttu-id="a33a8-165">Para remover todas as configurações de segurança do Registrador que permitem a autenticação de NTLM</span><span class="sxs-lookup"><span data-stu-id="a33a8-165">To remove all of the Registrar security settings that allow NTLM authentication</span></span>

- <span data-ttu-id="a33a8-166">O seguinte comando exclui todas as configurações de segurança do Registrador que permite o uso de NTLM para autenticação do cliente:</span><span class="sxs-lookup"><span data-stu-id="a33a8-166">The following command deletes all the Registrar security settings that allow the use of NTLM for client authentication:</span></span>
    
  ```
  Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration
  ```

<span data-ttu-id="a33a8-167">Para obter detalhes, consulte [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="a33a8-167">For details, see [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps).</span></span>
  

