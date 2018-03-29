---
title: Gerenciar configurações de Serviço da Web no Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
description: 'Resumo: Gerencie definições de configuração do serviço Web no Skype para Business Server 2015.'
ms.openlocfilehash: a0976728ecd09392408fb719861681e0465d7bed
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="manage-web-service-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="28d41-103">Gerenciar configurações de Serviço da Web no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="28d41-103">Manage Web Service configuration settings in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="28d41-104">**Resumo:** Gerencie definições de configuração do serviço Web no Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="28d41-104">**Summary:** Manage Web Service configuration settings in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="28d41-105">Você pode usar a página **Serviço Web** para configurar os métodos de autenticação para acessar o Skype para servidores de web Business Server 2015 relacionado e serviços Web.</span><span class="sxs-lookup"><span data-stu-id="28d41-105">You can use the **Web Service** page to configure the authentication methods for accessing Skype for Business Server 2015 related web servers and Web Services.</span></span>
  
<span data-ttu-id="28d41-106">Siga estas etapas para criar a nova política de Web Service.</span><span class="sxs-lookup"><span data-stu-id="28d41-106">Follow these steps to create a new Web Service policy.</span></span>
  
### <a name="to-create-new-web-service-configuration-settings"></a><span data-ttu-id="28d41-107">Para criar novas definições de configuração de serviço da Web</span><span class="sxs-lookup"><span data-stu-id="28d41-107">To create new web service configuration settings</span></span>

1.  <span data-ttu-id="28d41-108">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes), ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon no qualquer computador que esteja na rede em que você implantou Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="28d41-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2015.</span></span>
    
2. <span data-ttu-id="28d41-109">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="28d41-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="28d41-110">Na barra de navegação esquerda, clique em **Segurança** e em **Serviço da Web**.</span><span class="sxs-lookup"><span data-stu-id="28d41-110">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="28d41-111">Na página **Serviço da Web**, clique em **Novo** e faça um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="28d41-111">On the **Web Service** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="28d41-p101">Para configurar o Serviço da Web para um site, clique em **Configuração do site**. Em **Selecionar um site**, clique em um site no qual a política de Serviço da Web será aplicada e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="28d41-p101">To configure the Web Service for a site, click **Site configuration**. In **Select a Site**, click the site to which the Web Service policy will be applied a site and click **OK**.</span></span>
    
   - <span data-ttu-id="28d41-p102">Para configurar o Serviço da Web para um pool, clique em **Configuração do pool**. Em **Selecionar um Serviço**, clique no serviço no qual a política de Serviço da Web será aplicada e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="28d41-p102">To configure the Web Service for a pool, click **Pool configuration**. In **Select a Service**, click the service to which the Web Service policy will be applied and click **OK**.</span></span> 
    
5. <span data-ttu-id="28d41-116">Em **Nova configuração do Serviço da Web**, em **Autenticação integrada do Windows**, selecione **Negociar**, **Autenticação integrada do Windows** ou **Nenhum**.</span><span class="sxs-lookup"><span data-stu-id="28d41-116">In **New Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>
    
6. <span data-ttu-id="28d41-117">Selecione um ou mais dos seguintes dependendo das capacidades dos clientes e do suporte no seu ambiente:</span><span class="sxs-lookup"><span data-stu-id="28d41-117">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="28d41-118">**Habilitar autenticação de PIN** para permitir que os clientes sejam autenticados usando números PIN.</span><span class="sxs-lookup"><span data-stu-id="28d41-118">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
   - <span data-ttu-id="28d41-119">**Habilitar autenticação de certificado** para que os servidores no pool emitam certificados para os clientes.</span><span class="sxs-lookup"><span data-stu-id="28d41-119">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
   - <span data-ttu-id="28d41-120">**Habilitar download da cadeia de certificados** para que os servidores sejam apresentados com um download de certificado de autenticação da cadeia de certificados para aquele certificado.</span><span class="sxs-lookup"><span data-stu-id="28d41-120">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>
    
7. <span data-ttu-id="28d41-121">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="28d41-121">Click **Commit**.</span></span>
    
## <a name="modify-existing-web-service-configuration-settings"></a><span data-ttu-id="28d41-122">Modificar definições de configuração de Serviço da Web</span><span class="sxs-lookup"><span data-stu-id="28d41-122">Modify existing Web Service configuration settings</span></span>

<span data-ttu-id="28d41-123">Você pode usar a página **Serviço Web** para configurar os métodos de autenticação para acessar o Skype para servidores de web Business Server 2015 relacionado e serviços Web.</span><span class="sxs-lookup"><span data-stu-id="28d41-123">You can use the **Web Service** page to configure the authentication methods for accessing Skype for Business Server 2015 related web servers and Web Services.</span></span>
  
<span data-ttu-id="28d41-124">Execute estas etapas para modificar uma política de Serviço Web existente.</span><span class="sxs-lookup"><span data-stu-id="28d41-124">Follow these steps to modify an existing Web Service policy.</span></span>
  
### <a name="to-modify-existing-web-service-configuration-settings"></a><span data-ttu-id="28d41-125">Para modificar definições de configuração de Serviço da Web</span><span class="sxs-lookup"><span data-stu-id="28d41-125">To modify existing Web service configuration settings</span></span>

1.  <span data-ttu-id="28d41-126">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes), ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon no qualquer computador que esteja na rede em que você implantou Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="28d41-126">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2015.</span></span>
    
2. <span data-ttu-id="28d41-127">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="28d41-127">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="28d41-128">Na barra de navegação esquerda, clique em **Segurança** e em **Serviço da Web**.</span><span class="sxs-lookup"><span data-stu-id="28d41-128">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="28d41-129">Na página **Serviço da Web**, clique em uma configuração, em **Editar** e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="28d41-129">On the **Web Service** page, click a configuration, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="28d41-130">Em **Editar Configuração do Serviço da Web**, em **Autenticação do Windows Integrada**, selecione **Negociar**, **NTLM** ou **Nenhum**.</span><span class="sxs-lookup"><span data-stu-id="28d41-130">In **Edit Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>
    
6. <span data-ttu-id="28d41-131">Selecione um ou mais dos seguintes dependendo das capacidades dos clientes e do suporte no seu ambiente:</span><span class="sxs-lookup"><span data-stu-id="28d41-131">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="28d41-132">**Habilitar autenticação de PIN** para permitir que os clientes sejam autenticados usando números PIN.</span><span class="sxs-lookup"><span data-stu-id="28d41-132">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
   - <span data-ttu-id="28d41-133">**Habilitar autenticação de certificado** para que os servidores no pool emitam certificados para os clientes.</span><span class="sxs-lookup"><span data-stu-id="28d41-133">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
   - <span data-ttu-id="28d41-134">**Habilitar download da cadeia de certificados** para que os servidores sejam apresentados com um download de certificado de autenticação da cadeia de certificados para aquele certificado.</span><span class="sxs-lookup"><span data-stu-id="28d41-134">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>
    
7. <span data-ttu-id="28d41-135">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="28d41-135">Click **Commit**.</span></span>
    
## <a name="delete-existing-web-service-configuration-settings"></a><span data-ttu-id="28d41-136">Excluir definições de configuração de Serviço da Web</span><span class="sxs-lookup"><span data-stu-id="28d41-136">Delete existing Web Service configuration settings</span></span>

<span data-ttu-id="28d41-137">Siga estas etapas para excluir definições de configuração do serviço da web.</span><span class="sxs-lookup"><span data-stu-id="28d41-137">Follow these steps to delete web service configuration settings.</span></span>
  
### <a name="to-delete-web-service-configuration-settings"></a><span data-ttu-id="28d41-138">Para excluir definições de configuração de serviço da Web</span><span class="sxs-lookup"><span data-stu-id="28d41-138">To delete web service configuration settings</span></span>

1.  <span data-ttu-id="28d41-139">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes), ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon no qualquer computador que esteja na rede em que você implantou Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="28d41-139">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2015.</span></span>
    
2. <span data-ttu-id="28d41-140">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="28d41-140">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="28d41-141">Na barra de navegação esquerda, clique em **Segurança** e em **Serviço da Web**.</span><span class="sxs-lookup"><span data-stu-id="28d41-141">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="28d41-142">Na página **Serviço da Web**, e no campo de pesquisa, digite todo ou parte do nome da política que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="28d41-142">On the **Web Service** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>
    
5. <span data-ttu-id="28d41-143">Na lista de políticas, clique na política que você deseja, clique em **Editar** e em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="28d41-143">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="28d41-144">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="28d41-144">Click **OK**.</span></span>
    
## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="28d41-145">A exclusão de definições de configuração do serviço Web usando Cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="28d41-145">Deleting Web Service Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="28d41-146">Você pode excluir as definições de configuração do serviço web usando o Windows PowerShell e o cmdlet **Remove-CsWebServiceConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="28d41-146">You can delete web service configuration settings by using Windows PowerShell and the **Remove-CsWebServiceConfiguration** cmdlet.</span></span> <span data-ttu-id="28d41-147">Você pode executar esse cmdlet a partir do Skype do Shell de gerenciamento do servidor de negócios ou uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28d41-147">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="28d41-148">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype para Business Server, consulte o artigo do blog ["rápida iniciar: Gerenciando Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="28d41-148">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="28d41-149">O processo é o mesmo em Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="28d41-149">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a><span data-ttu-id="28d41-150">Para excluir um conjunto específico de definições de configuração do serviço da Web</span><span class="sxs-lookup"><span data-stu-id="28d41-150">To delete a specific collection of web service configuration settings</span></span>

- <span data-ttu-id="28d41-151">O seguinte comando remove as configurações de segurança do Serviço da Web aplicadas ao local Redmond:</span><span class="sxs-lookup"><span data-stu-id="28d41-151">The following command removes the Web Service security settings applied to the Redmond site:</span></span>
    
  ```
  Remove-CsWebServiceConfiguration -Identity "site:Redmond"
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="28d41-152">Para excluir todas as definições de configuração do serviço da Web aplicadas ao escopo local</span><span class="sxs-lookup"><span data-stu-id="28d41-152">To delete all of the web service configuration settings applied to the site scope</span></span>

<span data-ttu-id="28d41-153">O seguinte comando remove todas as configurações de segurança do Serviço da Web aplicadas ao escopo do serviço:</span><span class="sxs-lookup"><span data-stu-id="28d41-153">The following command removes all of the Web Service security settings applied to the service scope:</span></span>
    
  ```
  Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a><span data-ttu-id="28d41-154">Para excluir todas as definições de configuração do Serviço da Web que permitem a autenticação de certificado</span><span class="sxs-lookup"><span data-stu-id="28d41-154">To delete all of the web service configuration settings that allow certificate authentication</span></span>

<span data-ttu-id="28d41-155">O seguinte comando remove todas as configurações de segurança do Serviço da Web que permitem o uso de autenticação de certificados:</span><span class="sxs-lookup"><span data-stu-id="28d41-155">The following command removes all the Web Service security settings that allow the use of certificate authentication:</span></span>
    
  ```
  Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration
  ```

<span data-ttu-id="28d41-156">Para obter detalhes, consulte [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="28d41-156">For details, see [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps).</span></span>
  

