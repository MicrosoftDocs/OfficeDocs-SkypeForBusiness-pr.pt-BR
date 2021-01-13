---
title: Gerenciar definições de configuração do Serviço Web no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
description: 'Resumo: Gerenciar definições de configuração do Serviço Web no Skype for Business Server.'
ms.openlocfilehash: 68abe01614902d5e6f4c58040b30b6afbd475df8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806491"
---
# <a name="manage-web-service-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="f07cb-103">Gerenciar definições de configuração do Serviço Web no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f07cb-103">Manage Web Service configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="f07cb-104">**Resumo:** Gerenciar definições de configuração do Serviço Web no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f07cb-104">**Summary:** Manage Web Service configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="f07cb-105">Você pode usar a **página Serviço Web** para configurar os métodos de autenticação para acessar servidores Web e Serviços Web relacionados ao Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f07cb-105">You can use the **Web Service** page to configure the authentication methods for accessing Skype for Business Server related web servers and Web Services.</span></span>
  
<span data-ttu-id="f07cb-106">Siga estas etapas para criar uma nova política de Serviço Web.</span><span class="sxs-lookup"><span data-stu-id="f07cb-106">Follow these steps to create a new Web Service policy.</span></span>
  
### <a name="to-create-new-web-service-configuration-settings"></a><span data-ttu-id="f07cb-107">Para criar novas definições de configuração do serviço Web</span><span class="sxs-lookup"><span data-stu-id="f07cb-107">To create new web service configuration settings</span></span>

1.  <span data-ttu-id="f07cb-108">Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f07cb-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="f07cb-109">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f07cb-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="f07cb-110">Na barra de navegação esquerda, clique em **Segurança** e em **Serviço Web**.</span><span class="sxs-lookup"><span data-stu-id="f07cb-110">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="f07cb-111">Na página **Serviço web,** clique em **Novo** e, em seguida, faça um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="f07cb-111">On the **Web Service** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="f07cb-112">Para configurar o Serviço Web para um site, clique em **Configuração do site.**</span><span class="sxs-lookup"><span data-stu-id="f07cb-112">To configure the Web Service for a site, click **Site configuration**.</span></span> <span data-ttu-id="f07cb-113">Em **Selecionar um Site,** clique no site ao qual a política de Serviço Web será aplicada a um site e clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="f07cb-113">In **Select a Site**, click the site to which the Web Service policy will be applied a site and click **OK**.</span></span>
    
   - <span data-ttu-id="f07cb-114">Para configurar o Serviço Web para um pool, clique em **Configuração de pool.**</span><span class="sxs-lookup"><span data-stu-id="f07cb-114">To configure the Web Service for a pool, click **Pool configuration**.</span></span> <span data-ttu-id="f07cb-115">Em **Selecionar um Serviço,** clique no serviço ao qual a política de Serviço Web será aplicada e clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="f07cb-115">In **Select a Service**, click the service to which the Web Service policy will be applied and click **OK**.</span></span> 
    
5. <span data-ttu-id="f07cb-116">In **New Web Service Setting**, in Integrated Windows **authentication**, select **Negotiate**, Integrated **Windows authentication**, or **None**.</span><span class="sxs-lookup"><span data-stu-id="f07cb-116">In **New Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>
    
6. <span data-ttu-id="f07cb-117">Selecione uma ou mais das seguintes opções, dependendo dos recursos dos clientes do e suporte em seu ambiente:</span><span class="sxs-lookup"><span data-stu-id="f07cb-117">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="f07cb-118">**Habilitar Autenticação de PIN** para permitir que os clientes sejam autenticados usando números PIN.</span><span class="sxs-lookup"><span data-stu-id="f07cb-118">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
   - <span data-ttu-id="f07cb-119">**Habilitar autenticação de certificado** para que os servidores no pool emitam certificados aos clientes.</span><span class="sxs-lookup"><span data-stu-id="f07cb-119">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
   - <span data-ttu-id="f07cb-120">**Habilitar download da cadeia de certificados** para que os servidores com um certificado de autenticação baixem a cadeia de certificados para esse certificado.</span><span class="sxs-lookup"><span data-stu-id="f07cb-120">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>
    
7. <span data-ttu-id="f07cb-121">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="f07cb-121">Click **Commit**.</span></span>
    
## <a name="modify-existing-web-service-configuration-settings"></a><span data-ttu-id="f07cb-122">Modificar definições de configuração existentes do Serviço Web</span><span class="sxs-lookup"><span data-stu-id="f07cb-122">Modify existing Web Service configuration settings</span></span>

<span data-ttu-id="f07cb-123">Você pode usar a **página Serviço Web** para configurar os métodos de autenticação para acessar servidores Web e Serviços Web relacionados ao Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f07cb-123">You can use the **Web Service** page to configure the authentication methods for accessing Skype for Business Server related web servers and Web Services.</span></span>
  
<span data-ttu-id="f07cb-124">Execute estas etapas para modificar uma política de Serviço Web existente.</span><span class="sxs-lookup"><span data-stu-id="f07cb-124">Follow these steps to modify an existing Web Service policy.</span></span>
  
### <a name="to-modify-existing-web-service-configuration-settings"></a><span data-ttu-id="f07cb-125">Para modificar as definições de configuração existentes do serviço Web</span><span class="sxs-lookup"><span data-stu-id="f07cb-125">To modify existing Web service configuration settings</span></span>

1.  <span data-ttu-id="f07cb-126">Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f07cb-126">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="f07cb-127">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f07cb-127">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="f07cb-128">Na barra de navegação esquerda, clique em **Segurança** e em **Serviço Web**.</span><span class="sxs-lookup"><span data-stu-id="f07cb-128">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="f07cb-129">Na página **Serviço Web**, clique em uma configuração, em **Editar** e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="f07cb-129">On the **Web Service** page, click a configuration, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="f07cb-130">Em **Editar Configuração do Serviço Web**, em **Autenticação do Windows Integrada**, selecione **Negociar**, **NTLM** ou **Nenhum**.</span><span class="sxs-lookup"><span data-stu-id="f07cb-130">In **Edit Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>
    
6. <span data-ttu-id="f07cb-131">Selecione uma ou mais das seguintes opções, dependendo dos recursos dos clientes do e suporte em seu ambiente:</span><span class="sxs-lookup"><span data-stu-id="f07cb-131">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="f07cb-132">**Habilitar Autenticação de PIN** para permitir que os clientes sejam autenticados usando números PIN.</span><span class="sxs-lookup"><span data-stu-id="f07cb-132">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
   - <span data-ttu-id="f07cb-133">**Habilitar autenticação de certificado** para que os servidores no pool emitam certificados aos clientes.</span><span class="sxs-lookup"><span data-stu-id="f07cb-133">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
   - <span data-ttu-id="f07cb-134">**Habilitar download da cadeia de certificados** para que os servidores com um certificado de autenticação baixem a cadeia de certificados para esse certificado.</span><span class="sxs-lookup"><span data-stu-id="f07cb-134">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>
    
7. <span data-ttu-id="f07cb-135">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="f07cb-135">Click **Commit**.</span></span>
    
## <a name="delete-existing-web-service-configuration-settings"></a><span data-ttu-id="f07cb-136">Excluir definições de configuração existentes do Serviço Web</span><span class="sxs-lookup"><span data-stu-id="f07cb-136">Delete existing Web Service configuration settings</span></span>

<span data-ttu-id="f07cb-137">Siga estas etapas para excluir as definições de configuração do serviço Web.</span><span class="sxs-lookup"><span data-stu-id="f07cb-137">Follow these steps to delete web service configuration settings.</span></span>
  
### <a name="to-delete-web-service-configuration-settings"></a><span data-ttu-id="f07cb-138">Para excluir definições de configuração do serviço Web</span><span class="sxs-lookup"><span data-stu-id="f07cb-138">To delete web service configuration settings</span></span>

1.  <span data-ttu-id="f07cb-139">Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f07cb-139">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="f07cb-140">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f07cb-140">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="f07cb-141">Na barra de navegação esquerda, clique em **Segurança** e em **Serviço Web**.</span><span class="sxs-lookup"><span data-stu-id="f07cb-141">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="f07cb-142">Na página **Serviço Web**, e no campo de pesquisa, digite todo ou parte do nome da política que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="f07cb-142">On the **Web Service** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>
    
5. <span data-ttu-id="f07cb-143">Na lista de políticas, clique na política que você deseja, clique em **Editar** e em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="f07cb-143">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="f07cb-144">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f07cb-144">Click **OK**.</span></span>
    
## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f07cb-145">Excluindo definições de configuração do serviço Web usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f07cb-145">Deleting Web Service Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f07cb-146">Você pode excluir as definições de configuração do serviço Web usando o Windows PowerShell e o cmdlet **Remove-CsWebServiceConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="f07cb-146">You can delete web service configuration settings by using Windows PowerShell and the **Remove-CsWebServiceConfiguration** cmdlet.</span></span> <span data-ttu-id="f07cb-147">Você pode executar este cmdlet usando o Shell de gerenciamento do Skype for Business Server ou uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f07cb-147">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f07cb-148">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo do blog ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="f07cb-148">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="f07cb-149">O processo é o mesmo no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f07cb-149">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a><span data-ttu-id="f07cb-150">Para excluir um conjunto específico de definições de configuração do serviço da Web</span><span class="sxs-lookup"><span data-stu-id="f07cb-150">To delete a specific collection of web service configuration settings</span></span>

- <span data-ttu-id="f07cb-151">O seguinte comando remove as configurações de segurança do Serviço da Web aplicadas ao local Redmond:</span><span class="sxs-lookup"><span data-stu-id="f07cb-151">The following command removes the Web Service security settings applied to the Redmond site:</span></span>
    
  ```PowerShell
  Remove-CsWebServiceConfiguration -Identity "site:Redmond"
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="f07cb-152">Para excluir todas as definições de configuração do serviço Web aplicadas ao escopo do site</span><span class="sxs-lookup"><span data-stu-id="f07cb-152">To delete all of the web service configuration settings applied to the site scope</span></span>

<span data-ttu-id="f07cb-153">O seguinte comando remove todas as configurações de segurança do Serviço da Web aplicadas ao escopo do serviço:</span><span class="sxs-lookup"><span data-stu-id="f07cb-153">The following command removes all of the Web Service security settings applied to the service scope:</span></span>
    
  ```PowerShell
  Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a><span data-ttu-id="f07cb-154">Para excluir todas as definições de configuração do serviço Web que permitem a autenticação de certificado</span><span class="sxs-lookup"><span data-stu-id="f07cb-154">To delete all of the web service configuration settings that allow certificate authentication</span></span>

<span data-ttu-id="f07cb-155">O seguinte comando remove todas as configurações de segurança do Serviço da Web que permitem o uso de autenticação de certificados:</span><span class="sxs-lookup"><span data-stu-id="f07cb-155">The following command removes all the Web Service security settings that allow the use of certificate authentication:</span></span>
    
  ```PowerShell
  Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration
  ```

<span data-ttu-id="f07cb-156">Para obter detalhes, [consulte Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f07cb-156">For details, see [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps).</span></span>
  

