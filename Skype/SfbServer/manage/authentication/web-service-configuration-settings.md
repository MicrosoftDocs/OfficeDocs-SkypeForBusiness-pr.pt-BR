---
title: Gerenciar configurações de serviço Web no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
description: 'Resumo: gerenciar configurações de serviço Web no Skype for Business Server.'
ms.openlocfilehash: b2a7f287c9386c89d132e03e96aa25e9472f7008
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297572"
---
# <a name="manage-web-service-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="c13de-103">Gerenciar configurações de serviço Web no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c13de-103">Manage Web Service configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="c13de-104">**Resumo:** Gerenciar configurações de serviço Web no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c13de-104">**Summary:** Manage Web Service configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="c13de-105">Você pode usar a página **serviço Web** para configurar os métodos de autenticação para acessar servidores Web e serviços Web relacionados ao Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c13de-105">You can use the **Web Service** page to configure the authentication methods for accessing Skype for Business Server related web servers and Web Services.</span></span>
  
<span data-ttu-id="c13de-106">Siga estas etapas para criar a nova política de Web Service.</span><span class="sxs-lookup"><span data-stu-id="c13de-106">Follow these steps to create a new Web Service policy.</span></span>
  
### <a name="to-create-new-web-service-configuration-settings"></a><span data-ttu-id="c13de-107">Para criar novas definições de configuração de serviço da Web</span><span class="sxs-lookup"><span data-stu-id="c13de-107">To create new web service configuration settings</span></span>

1.  <span data-ttu-id="c13de-108">Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Skype for Business Server .</span><span class="sxs-lookup"><span data-stu-id="c13de-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="c13de-109">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c13de-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="c13de-110">Na barra de navegação esquerda, clique em **Segurança** e em **Serviço da Web**.</span><span class="sxs-lookup"><span data-stu-id="c13de-110">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="c13de-111">Na página **Serviço da Web**, clique em **Novo** e faça um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="c13de-111">On the **Web Service** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="c13de-p101">Para configurar o Serviço da Web para um site, clique em **Configuração do site**. Em **Selecionar um site**, clique em um site no qual a política de Serviço da Web será aplicada e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c13de-p101">To configure the Web Service for a site, click **Site configuration**. In **Select a Site**, click the site to which the Web Service policy will be applied a site and click **OK**.</span></span>
    
   - <span data-ttu-id="c13de-p102">Para configurar o Serviço da Web para um pool, clique em **Configuração do pool**. Em **Selecionar um Serviço**, clique no serviço no qual a política de Serviço da Web será aplicada e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c13de-p102">To configure the Web Service for a pool, click **Pool configuration**. In **Select a Service**, click the service to which the Web Service policy will be applied and click **OK**.</span></span> 
    
5. <span data-ttu-id="c13de-116">Em **Nova configuração do Serviço da Web**, em **Autenticação integrada do Windows**, selecione **Negociar**, **Autenticação integrada do Windows** ou **Nenhum**.</span><span class="sxs-lookup"><span data-stu-id="c13de-116">In **New Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>
    
6. <span data-ttu-id="c13de-117">Selecione um ou mais dos seguintes dependendo das capacidades dos clientes e do suporte no seu ambiente:</span><span class="sxs-lookup"><span data-stu-id="c13de-117">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="c13de-118">**Habilitar autenticação de PIN** para permitir que os clientes sejam autenticados usando números PIN.</span><span class="sxs-lookup"><span data-stu-id="c13de-118">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
   - <span data-ttu-id="c13de-119">**Habilitar autenticação de certificado** para que os servidores no pool emitam certificados para os clientes.</span><span class="sxs-lookup"><span data-stu-id="c13de-119">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
   - <span data-ttu-id="c13de-120">**Habilitar download da cadeia de certificados** para que os servidores sejam apresentados com um download de certificado de autenticação da cadeia de certificados para aquele certificado.</span><span class="sxs-lookup"><span data-stu-id="c13de-120">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>
    
7. <span data-ttu-id="c13de-121">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="c13de-121">Click **Commit**.</span></span>
    
## <a name="modify-existing-web-service-configuration-settings"></a><span data-ttu-id="c13de-122">Modificar definições de configuração de Serviço da Web</span><span class="sxs-lookup"><span data-stu-id="c13de-122">Modify existing Web Service configuration settings</span></span>

<span data-ttu-id="c13de-123">Você pode usar a página **serviço Web** para configurar os métodos de autenticação para acessar servidores Web e serviços Web relacionados ao Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c13de-123">You can use the **Web Service** page to configure the authentication methods for accessing Skype for Business Server related web servers and Web Services.</span></span>
  
<span data-ttu-id="c13de-124">Execute estas etapas para modificar uma política de Serviço Web existente.</span><span class="sxs-lookup"><span data-stu-id="c13de-124">Follow these steps to modify an existing Web Service policy.</span></span>
  
### <a name="to-modify-existing-web-service-configuration-settings"></a><span data-ttu-id="c13de-125">Para modificar definições de configuração de Serviço da Web</span><span class="sxs-lookup"><span data-stu-id="c13de-125">To modify existing Web service configuration settings</span></span>

1.  <span data-ttu-id="c13de-126">Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Skype for Business Server .</span><span class="sxs-lookup"><span data-stu-id="c13de-126">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="c13de-127">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c13de-127">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="c13de-128">Na barra de navegação esquerda, clique em **Segurança** e em **Serviço da Web**.</span><span class="sxs-lookup"><span data-stu-id="c13de-128">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="c13de-129">Na página **Serviço da Web**, clique em uma configuração, em **Editar** e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="c13de-129">On the **Web Service** page, click a configuration, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="c13de-130">Em **Editar Configuração do Serviço da Web**, em **Autenticação do Windows Integrada**, selecione **Negociar**, **NTLM** ou **Nenhum**.</span><span class="sxs-lookup"><span data-stu-id="c13de-130">In **Edit Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>
    
6. <span data-ttu-id="c13de-131">Selecione um ou mais dos seguintes dependendo das capacidades dos clientes e do suporte no seu ambiente:</span><span class="sxs-lookup"><span data-stu-id="c13de-131">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="c13de-132">**Habilitar autenticação de PIN** para permitir que os clientes sejam autenticados usando números PIN.</span><span class="sxs-lookup"><span data-stu-id="c13de-132">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
   - <span data-ttu-id="c13de-133">**Habilitar autenticação de certificado** para que os servidores no pool emitam certificados para os clientes.</span><span class="sxs-lookup"><span data-stu-id="c13de-133">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
   - <span data-ttu-id="c13de-134">**Habilitar download da cadeia de certificados** para que os servidores sejam apresentados com um download de certificado de autenticação da cadeia de certificados para aquele certificado.</span><span class="sxs-lookup"><span data-stu-id="c13de-134">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>
    
7. <span data-ttu-id="c13de-135">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="c13de-135">Click **Commit**.</span></span>
    
## <a name="delete-existing-web-service-configuration-settings"></a><span data-ttu-id="c13de-136">Excluir definições de configuração de Serviço da Web</span><span class="sxs-lookup"><span data-stu-id="c13de-136">Delete existing Web Service configuration settings</span></span>

<span data-ttu-id="c13de-137">Siga estas etapas para excluir definições de configuração do serviço da web.</span><span class="sxs-lookup"><span data-stu-id="c13de-137">Follow these steps to delete web service configuration settings.</span></span>
  
### <a name="to-delete-web-service-configuration-settings"></a><span data-ttu-id="c13de-138">Para excluir definições de configuração de serviço da Web</span><span class="sxs-lookup"><span data-stu-id="c13de-138">To delete web service configuration settings</span></span>

1.  <span data-ttu-id="c13de-139">Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Skype for Business Server .</span><span class="sxs-lookup"><span data-stu-id="c13de-139">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="c13de-140">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c13de-140">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="c13de-141">Na barra de navegação esquerda, clique em **Segurança** e em **Serviço da Web**.</span><span class="sxs-lookup"><span data-stu-id="c13de-141">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="c13de-142">Na página **Serviço da Web**, e no campo de pesquisa, digite todo ou parte do nome da política que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="c13de-142">On the **Web Service** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>
    
5. <span data-ttu-id="c13de-143">Na lista de políticas, clique na política que você deseja, clique em **Editar** e em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="c13de-143">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="c13de-144">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c13de-144">Click **OK**.</span></span>
    
## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c13de-145">Excluindo configurações de serviço Web usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c13de-145">Deleting Web Service Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c13de-146">Você pode excluir as configurações de serviço Web usando o Windows PowerShell e o cmdlet **Remove-CsWebServiceConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="c13de-146">You can delete web service configuration settings by using Windows PowerShell and the **Remove-CsWebServiceConfiguration** cmdlet.</span></span> <span data-ttu-id="c13de-147">Você pode executar esse cmdlet a partir do Shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c13de-147">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c13de-148">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo ["início rápido: Gerenciando o Microsoft Lync Server 2010 usando o PowerShell remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="c13de-148">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="c13de-149">O processo é o mesmo no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c13de-149">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a><span data-ttu-id="c13de-150">Para excluir um conjunto específico de definições de configuração do serviço da Web</span><span class="sxs-lookup"><span data-stu-id="c13de-150">To delete a specific collection of web service configuration settings</span></span>

- <span data-ttu-id="c13de-151">O seguinte comando remove as configurações de segurança do Serviço da Web aplicadas ao local Redmond:</span><span class="sxs-lookup"><span data-stu-id="c13de-151">The following command removes the Web Service security settings applied to the Redmond site:</span></span>
    
  ```
  Remove-CsWebServiceConfiguration -Identity "site:Redmond"
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="c13de-152">Para excluir todas as definições de configuração do serviço da Web aplicadas ao escopo local</span><span class="sxs-lookup"><span data-stu-id="c13de-152">To delete all of the web service configuration settings applied to the site scope</span></span>

<span data-ttu-id="c13de-153">O seguinte comando remove todas as configurações de segurança do Serviço da Web aplicadas ao escopo do serviço:</span><span class="sxs-lookup"><span data-stu-id="c13de-153">The following command removes all of the Web Service security settings applied to the service scope:</span></span>
    
  ```
  Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a><span data-ttu-id="c13de-154">Para excluir todas as definições de configuração do Serviço da Web que permitem a autenticação de certificado</span><span class="sxs-lookup"><span data-stu-id="c13de-154">To delete all of the web service configuration settings that allow certificate authentication</span></span>

<span data-ttu-id="c13de-155">O seguinte comando remove todas as configurações de segurança do Serviço da Web que permitem o uso de autenticação de certificados:</span><span class="sxs-lookup"><span data-stu-id="c13de-155">The following command removes all the Web Service security settings that allow the use of certificate authentication:</span></span>
    
  ```
  Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration
  ```

<span data-ttu-id="c13de-156">Para obter detalhes, consulte [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="c13de-156">For details, see [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps).</span></span>
  

