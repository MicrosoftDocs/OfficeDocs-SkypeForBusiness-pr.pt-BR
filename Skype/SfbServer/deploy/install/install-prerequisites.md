---
title: Instalar os pré-requisitos para o Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: 'Summary: Learn about the servers and server roles you must configure before you install Skype for Business Server 2015. Download a free trial of Skype for Business Server 2015 from the Microsoft Evaluation center at: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 6f84b4f0a95c45297ad809e6b04217e711c3dd5e
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
---
# <a name="install-prerequisites-for-skype-for-business-server-2015"></a><span data-ttu-id="a1381-104">Instalar os pré-requisitos para o Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a1381-104">Install prerequisites for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a1381-105">**Summary:** Learn about the servers and server roles you must configure before you install Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="a1381-105">**Summary:** Learn about the servers and server roles you must configure before you install Skype for Business Server 2015.</span></span> <span data-ttu-id="a1381-106">Download a free trial of Skype for Business Server 2015 from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="a1381-106">Download a free trial of Skype for Business Server 2015 from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="a1381-107">Os pré-requisitos de instalação consistem na configuração do Windows Server por meio da instalação das funções e dos recursos necessários em cada servidor da topologia.</span><span class="sxs-lookup"><span data-stu-id="a1381-107">Installing prerequisites consists of setting up Windows Server by installing the required roles and features on each of the servers in the topology.</span></span> <span data-ttu-id="a1381-108">Os requisitos são baseados na função que o servidor vai desempenhar na topologia.</span><span class="sxs-lookup"><span data-stu-id="a1381-108">The requirements are based on the role the server will fulfill in the topology.</span></span> <span data-ttu-id="a1381-109">Você pode executar os passos 1 a 5 em qualquer ordem.</span><span class="sxs-lookup"><span data-stu-id="a1381-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="a1381-110">No entanto, as etapas 6, 7 e 8 devem ser executadas nesta ordem, após concluir as etapas 1 a 5, conforme descrito no diagrama.</span><span class="sxs-lookup"><span data-stu-id="a1381-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="a1381-111">Os pré-requisitos de instalação é a etapa 1 de 8.</span><span class="sxs-lookup"><span data-stu-id="a1381-111">Installing prerequisites is step 1 of 8.</span></span>
  
![Diagrama de visão geral - instalar pré-requisitos.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a><span data-ttu-id="a1381-113">Instalação do Windows Server</span><span class="sxs-lookup"><span data-stu-id="a1381-113">Setup Windows Server</span></span>

<span data-ttu-id="a1381-114">Skype for Business Server 2015 requires the Windows Server operating system and a number of prerequisites before it can be installed.</span><span class="sxs-lookup"><span data-stu-id="a1381-114">Skype for Business Server 2015 requires the Windows Server operating system and a number of prerequisites before it can be installed.</span></span> <span data-ttu-id="a1381-115">For details on planning for prerequisites, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1381-115">For details on planning for prerequisites, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span> 
  
> [!TIP]
> <span data-ttu-id="a1381-p105">Esse procedimento usa o Windows Server 2012 R2. Se você estiver usando uma versão diferente do Windows Server, o procedimento pode ser um pouco diferente.</span><span class="sxs-lookup"><span data-stu-id="a1381-p105">This procedure uses Windows Server 2012 R2. If you are using a different version of Windows Server, the procedure might be slightly different.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="a1381-118">Before you begin, make sure that Windows Server is up-to-date by using Windows Update.</span><span class="sxs-lookup"><span data-stu-id="a1381-118">Before you begin, make sure that Windows Server is up-to-date by using Windows Update.</span></span> 
  
![Windows Server atualizado.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
<span data-ttu-id="a1381-120">Assista as etapas do vídeo para **os pré-requisitos de instalação**:</span><span class="sxs-lookup"><span data-stu-id="a1381-120">Watch the video steps for **install prerequisites**:</span></span>
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a><span data-ttu-id="a1381-121">Instale as funções e os recursos necessários para os servidores front-end</span><span class="sxs-lookup"><span data-stu-id="a1381-121">Install required roles and features for front-end servers</span></span>

1. <span data-ttu-id="a1381-122">Abra o Server Manager e clique em **Adicionar funções e recurso**.</span><span class="sxs-lookup"><span data-stu-id="a1381-122">Open Server Manager, and click **Add roles and features**.</span></span>
    
2. <span data-ttu-id="a1381-123">Leia a página **Antes de Começar** para se familiarizar com a instalação de funções e recursos no Windows Server, e depois clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a1381-123">Read the **Before You Begin** page to familiarize yourself with installing roles and features in Windows Server, and then click **Next**.</span></span>
    
3. <span data-ttu-id="a1381-124">Selecione **Instalação baseada em função ou baseada em recurso**, e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a1381-124">Select **Role-based or feature-based installation**, and click **Next**.</span></span>
    
4. <span data-ttu-id="a1381-125">Select the server on which you will be installing Skype for Business Server 2015, and click **Next**.</span><span class="sxs-lookup"><span data-stu-id="a1381-125">Select the server on which you will be installing Skype for Business Server 2015, and click **Next**.</span></span>
    
5. <span data-ttu-id="a1381-126">Selecione a função **Servidor Web (IIS)**, e quando a janela de recursos obrigatórios aparecer, clique em **Adicionar recursos**, e depois clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a1381-126">Select the **Web Server (IIS)** role, and when the required features window pops up, click **Add Features**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="a1381-127">Make sure the software features listed in [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#Software) are on the server that will run Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="a1381-127">Make sure the software features listed in [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#Software) are on the server that will run Skype for Business Server 2015.</span></span> <span data-ttu-id="a1381-128">Here's an abbreviated list:</span><span class="sxs-lookup"><span data-stu-id="a1381-128">Here's an abbreviated list:</span></span>
    
   - <span data-ttu-id="a1381-129">.NET Framework Features</span><span class="sxs-lookup"><span data-stu-id="a1381-129">.NET Framework Features</span></span>
    
   - <span data-ttu-id="a1381-130">Recursos do WCF</span><span class="sxs-lookup"><span data-stu-id="a1381-130">WCF Services</span></span>
    
   - <span data-ttu-id="a1381-131">Ativação HTTP</span><span class="sxs-lookup"><span data-stu-id="a1381-131">HTTP Activation</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a1381-p107">A Ativação HTTP requer recursos adicionais. Clique em **Adicionar recursos** para ver a caixa de diálogo que aparecerá quando você selecionar Ativação HTTP.</span><span class="sxs-lookup"><span data-stu-id="a1381-p107">HTTP Activation requires additional features. Click **Add Features** to the warning dialog box that pops up when you select HTTP Activation.</span></span>
  
   - <span data-ttu-id="a1381-134">Media Foundation (required by Front End Servers and Standard Edition servers used for conferencing.)</span><span class="sxs-lookup"><span data-stu-id="a1381-134">Media Foundation (required by Front End Servers and Standard Edition servers used for conferencing.)</span></span>
    
   - <span data-ttu-id="a1381-135">AD DS and AD LDS ToolsFerramentas de Administração de Servidor Remoto</span><span class="sxs-lookup"><span data-stu-id="a1381-135">Remote Server Administration Tools</span></span>
    
   - <span data-ttu-id="a1381-136">Ferramentas de Administração de Funções</span><span class="sxs-lookup"><span data-stu-id="a1381-136">Role Administration Tools</span></span>
    
   - <span data-ttu-id="a1381-137">AD DS</span><span class="sxs-lookup"><span data-stu-id="a1381-137">AD DS</span></span> 
    
   - <span data-ttu-id="a1381-138">AD LDS</span><span class="sxs-lookup"><span data-stu-id="a1381-138">AD LDS</span></span>
    
   - <span data-ttu-id="a1381-139">Windows Identity Foundation 3.5</span><span class="sxs-lookup"><span data-stu-id="a1381-139">Windows Identity Foundation 3.5</span></span>
    
7. <span data-ttu-id="a1381-140">Clique em **Avançar** para continuar no assistente.</span><span class="sxs-lookup"><span data-stu-id="a1381-140">Click **Next** to continue through the wizard.</span></span>
    
8. <span data-ttu-id="a1381-141">Leia as observações sobre a **Função Servidor Web (IIS)**, e depois clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a1381-141">Read through the notes about the **Web Server Role (IIS)**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="a1381-142">Selecione os seguintes **serviços de função Servidor Web (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="a1381-142">Select the following **Web Server (IIS) role services**.</span></span>
    
   - <span data-ttu-id="a1381-143">Recursos HTTP Comuns</span><span class="sxs-lookup"><span data-stu-id="a1381-143">Common HTTP Features</span></span>
    
   - <span data-ttu-id="a1381-144">Documento padrão</span><span class="sxs-lookup"><span data-stu-id="a1381-144">Default Document</span></span>
    
   - <span data-ttu-id="a1381-145">Pesquisa de diretório</span><span class="sxs-lookup"><span data-stu-id="a1381-145">Directory Browsing</span></span>
    
   - <span data-ttu-id="a1381-146">Erros HTTP</span><span class="sxs-lookup"><span data-stu-id="a1381-146">HTTP Errors</span></span>
    
   - <span data-ttu-id="a1381-147">Conteúdo estático</span><span class="sxs-lookup"><span data-stu-id="a1381-147">Static Content</span></span>
    
   - <span data-ttu-id="a1381-148">Integridade e Diagnósticos</span><span class="sxs-lookup"><span data-stu-id="a1381-148">Health and Diagnostics</span></span>
    
   - <span data-ttu-id="a1381-149">Log HTTP</span><span class="sxs-lookup"><span data-stu-id="a1381-149">HTTP Logging</span></span>
    
   - <span data-ttu-id="a1381-150">Ferramentas de log</span><span class="sxs-lookup"><span data-stu-id="a1381-150">Logging Tools</span></span>
    
   - <span data-ttu-id="a1381-151">Rastreamento</span><span class="sxs-lookup"><span data-stu-id="a1381-151">Tracing</span></span>
    
   - <span data-ttu-id="a1381-152">Desempenho</span><span class="sxs-lookup"><span data-stu-id="a1381-152">Performance</span></span>
    
   - <span data-ttu-id="a1381-153">Compressão de conteúdo estático</span><span class="sxs-lookup"><span data-stu-id="a1381-153">Static Content Compression</span></span>
    
   - <span data-ttu-id="a1381-154">Compactação de conteúdo dinâmico</span><span class="sxs-lookup"><span data-stu-id="a1381-154">Dynamic Content Compression</span></span>
    
   - <span data-ttu-id="a1381-155">Segurança</span><span class="sxs-lookup"><span data-stu-id="a1381-155">Security</span></span>
    
   - <span data-ttu-id="a1381-156">Requisição de filtro</span><span class="sxs-lookup"><span data-stu-id="a1381-156">Request Filtering</span></span>
    
   - <span data-ttu-id="a1381-157">Autenticação de mapeamento de certificado de cliente</span><span class="sxs-lookup"><span data-stu-id="a1381-157">Client Certificate Mapping Authentication</span></span>
    
   - <span data-ttu-id="a1381-158">Autenticação do Windows</span><span class="sxs-lookup"><span data-stu-id="a1381-158">Windows Authentication</span></span>
    
   - <span data-ttu-id="a1381-159">Desenvolvimento do aplicativo</span><span class="sxs-lookup"><span data-stu-id="a1381-159">Application Development</span></span>
    
   - <span data-ttu-id="a1381-160">Extensibilidade .NET 3.5</span><span class="sxs-lookup"><span data-stu-id="a1381-160">.NET Extensibility 3.5</span></span>
    
   - <span data-ttu-id="a1381-161">Extensibilidade .NET 4.5</span><span class="sxs-lookup"><span data-stu-id="a1381-161">.NET Extensibility 4.5</span></span>
    
   - <span data-ttu-id="a1381-162">ASP.NET 3.5</span><span class="sxs-lookup"><span data-stu-id="a1381-162">ASP.NET 3.5</span></span>
    
   - <span data-ttu-id="a1381-163">ASP.NET 4.5</span><span class="sxs-lookup"><span data-stu-id="a1381-163">ASP.NET 4.5</span></span>
    
   - <span data-ttu-id="a1381-164">Extensões ISAPI</span><span class="sxs-lookup"><span data-stu-id="a1381-164">ISAPI Extensions</span></span>
    
   - <span data-ttu-id="a1381-165">Filtros ISAPI</span><span class="sxs-lookup"><span data-stu-id="a1381-165">ISAPI Filters</span></span>
    
   - <span data-ttu-id="a1381-166">Ferramentas de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="a1381-166">Management Tools</span></span>
    
   - <span data-ttu-id="a1381-167">Console de gerenciamento IIS</span><span class="sxs-lookup"><span data-stu-id="a1381-167">IIS Management Console</span></span>
    
   - <span data-ttu-id="a1381-168">Ferramentas e scripts de gerenciamento IIS</span><span class="sxs-lookup"><span data-stu-id="a1381-168">IIS Management Scripts and Tools</span></span>
    
10. <span data-ttu-id="a1381-169">Clique em **Avançar** para continuar no assistente.</span><span class="sxs-lookup"><span data-stu-id="a1381-169">Click **Next** to continue through the wizard.</span></span>
    
11. <span data-ttu-id="a1381-170">Examine as seleções de instalação para certificar-se de que todos os requisitos foram selecionados e clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="a1381-170">Review the installation selections to make sure all requirements are selected, and then click **Install**.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="a1381-171">O Windows Server 2012 R2 não instala todos os arquivo de origem para os recursos necessários por padrão.</span><span class="sxs-lookup"><span data-stu-id="a1381-171">Windows Server 2012 R2 does not install all of the source files for the required features by default.</span></span> <span data-ttu-id="a1381-172">Se o servidor não estiver conectado à Internet, você terá que inserir a mídia do Windows Server 2012 R2 e selecionar **Especificar um caminho de origem alternativo** para instalar os recursos necessários.</span><span class="sxs-lookup"><span data-stu-id="a1381-172">If the server is not connected to the Internet, you will need to insert the Windows Server 2012 R2 media and select **Specify an alternate source path** in order to install the required features.</span></span> <span data-ttu-id="a1381-173">Os arquivos de origem estão localizados no diretório sources\sxs.</span><span class="sxs-lookup"><span data-stu-id="a1381-173">The source files are located in the sources\sxs directory.</span></span> <span data-ttu-id="a1381-174">Por exemplo, se a mídia do Windows Server 2012 R2 estiver na unidade D, você teria que definir o caminho como `d:\sources\sxs`.</span><span class="sxs-lookup"><span data-stu-id="a1381-174">For example, if the Windows Server 2012 R2 media is in drive D, you would set the path to `d:\sources\sxs`.</span></span> <span data-ttu-id="a1381-175">> It is important that you have the latest updates from Windows Update.</span><span class="sxs-lookup"><span data-stu-id="a1381-175">> It is important that you have the latest updates from Windows Update.</span></span> <span data-ttu-id="a1381-176">Se você não estiver conectado à Internet, terá que instalar manualmente todas as atualizações importantes, bem como quaisquer pré-requisitos para as atualizações necessárias.</span><span class="sxs-lookup"><span data-stu-id="a1381-176">If you are not connected to the Internet, you will need to manually install all relevant updates as well as any prerequisites to the required updates.</span></span> 
  
12. <span data-ttu-id="a1381-177">Quando a caixa de diálogo indicar que a instalação foi concluída, você terá que reiniciar o servidor para concluir o processo.</span><span class="sxs-lookup"><span data-stu-id="a1381-177">When the dialog box indicates that the installation has completed, you will need to reboot the server to complete the process.</span></span>
    
13. <span data-ttu-id="a1381-178">Execute o **Windows Update** novamente para verificar se há alguma atualização para as funções e os serviços que foram instalados.</span><span class="sxs-lookup"><span data-stu-id="a1381-178">Run **Windows Update** again to check if there are any updates to the roles and services that were installed.</span></span>
    
14. <span data-ttu-id="a1381-179">If you will be using Skype for Business Server Control Panel on this server then you must also install Silverlight.</span><span class="sxs-lookup"><span data-stu-id="a1381-179">If you will be using Skype for Business Server Control Panel on this server then you must also install Silverlight.</span></span> <span data-ttu-id="a1381-180">To install Silverlight, see [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span><span class="sxs-lookup"><span data-stu-id="a1381-180">To install Silverlight, see [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span></span>
    
<span data-ttu-id="a1381-181">Os pré-requisitos podem ser instalados executando o seguinte comando PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a1381-181">The prerequisites can be installed by running the following PowerShell command.</span></span> <span data-ttu-id="a1381-182">Observe que o comando procura arquivos de origem em uma ordem específica.</span><span class="sxs-lookup"><span data-stu-id="a1381-182">Note that the command looks for source files in a specific order.</span></span> <span data-ttu-id="a1381-183">Se você estiver online, o comando acessa o Windows Update.</span><span class="sxs-lookup"><span data-stu-id="a1381-183">If you are online, the command accesses Windows Update.</span></span> <span data-ttu-id="a1381-184">No entanto, se você estiver offline, terá que verificar se os arquivos de origem estão disponíveis para o comando.</span><span class="sxs-lookup"><span data-stu-id="a1381-184">However, if you are offline, you need to make sure the source files are available to the command.</span></span> <span data-ttu-id="a1381-185">For more information about using PowerShell to install roles and features, see [Install or Uninstall Roles, Role Services, or Features](https://technet.microsoft.com/en-us/library/hh831809.aspx) and [Install-WindowsFeature](https://technet.microsoft.com/en-us/library/jj205467.aspx).</span><span class="sxs-lookup"><span data-stu-id="a1381-185">For more information about using PowerShell to install roles and features, see [Install or Uninstall Roles, Role Services, or Features](https://technet.microsoft.com/en-us/library/hh831809.aspx) and [Install-WindowsFeature](https://technet.microsoft.com/en-us/library/jj205467.aspx).</span></span> <span data-ttu-id="a1381-186">Não se esqueça de executar o Windows Update novamente após instalar os pré-requisitos, mesmo se você usar o comando PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a1381-186">Don't forget to run Windows Update again after you install prerequisites, even if you use the PowerShell command.</span></span>
```
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS
```

> [!IMPORTANT]
> <span data-ttu-id="a1381-187">Os pré-requisitos para servidores executando funções diferentes da de servidor front-end, como a função de Diretor, Chat Persistente ou Borda, terão seus próprios pré-requisitos.</span><span class="sxs-lookup"><span data-stu-id="a1381-187">The prerequisites for servers performing roles other than front-end server, such as the role of Director, Persistent Chat, or Edge, have their own prerequisites.</span></span> <span data-ttu-id="a1381-188">For details on the exact prerequisites required by each server type, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1381-188">For details on the exact prerequisites required by each server type, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span> 
  

