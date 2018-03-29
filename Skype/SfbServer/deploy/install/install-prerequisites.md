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
description: 'Resumo: Saiba mais sobre os servidores e funções de servidor, que você deve configurar antes de instalar Skype para Business Server 2015. Baixe uma versão de avaliação gratuita do Skype para negócios 2015 de servidor do centro da Evaluation da Microsoft em: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 350f64a2808e51866cd5720cb1955259ff773c81
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="install-prerequisites-for-skype-for-business-server-2015"></a><span data-ttu-id="829f1-104">Instalar os pré-requisitos para o Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="829f1-104">Install prerequisites for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="829f1-105">**Resumo:** Saiba mais sobre os servidores e funções de servidor, que você deve configurar antes de instalar Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="829f1-105">**Summary:** Learn about the servers and server roles you must configure before you install Skype for Business Server 2015.</span></span> <span data-ttu-id="829f1-106">Baixe uma versão de avaliação gratuita do Skype para negócios 2015 de servidor do [Centro de avaliação do Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="829f1-106">Download a free trial of Skype for Business Server 2015 from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="829f1-107">Os pré-requisitos de instalação consistem na configuração do Windows Server por meio da instalação das funções e dos recursos necessários em cada servidor da topologia.</span><span class="sxs-lookup"><span data-stu-id="829f1-107">Installing prerequisites consists of setting up Windows Server by installing the required roles and features on each of the servers in the topology.</span></span> <span data-ttu-id="829f1-108">Os requisitos são baseados na função que o servidor vai desempenhar na topologia.</span><span class="sxs-lookup"><span data-stu-id="829f1-108">The requirements are based on the role the server will fulfill in the topology.</span></span> <span data-ttu-id="829f1-109">Você pode executar os passos 1 a 5 em qualquer ordem.</span><span class="sxs-lookup"><span data-stu-id="829f1-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="829f1-110">No entanto, as etapas 6, 7 e 8 devem ser executadas nesta ordem, após concluir as etapas 1 a 5, conforme descrito no diagrama.</span><span class="sxs-lookup"><span data-stu-id="829f1-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="829f1-111">Os pré-requisitos de instalação é a etapa 1 de 8.</span><span class="sxs-lookup"><span data-stu-id="829f1-111">Installing prerequisites is step 1 of 8.</span></span>
  
![Diagrama de visão geral - instalar pré-requisitos.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a><span data-ttu-id="829f1-113">Instalação do Windows Server</span><span class="sxs-lookup"><span data-stu-id="829f1-113">Setup Windows Server</span></span>

<span data-ttu-id="829f1-114">Skype para Business Server 2015 requer o sistema operacional Windows Server e um número de pré-requisitos antes que ele possa ser instalado.</span><span class="sxs-lookup"><span data-stu-id="829f1-114">Skype for Business Server 2015 requires the Windows Server operating system and a number of prerequisites before it can be installed.</span></span> <span data-ttu-id="829f1-115">Para obter detalhes sobre como planejar os pré-requisitos, consulte [requisitos de servidor para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="829f1-115">For details on planning for prerequisites, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span> 
  
> [!TIP]
> <span data-ttu-id="829f1-p105">Esse procedimento usa o Windows Server 2012 R2. Se você estiver usando uma versão diferente do Windows Server, o procedimento pode ser um pouco diferente.</span><span class="sxs-lookup"><span data-stu-id="829f1-p105">This procedure uses Windows Server 2012 R2. If you are using a different version of Windows Server, the procedure might be slightly different.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="829f1-118">Antes de começar, certifique-se de que o Windows Server seja atualizada usando o Windows Update.</span><span class="sxs-lookup"><span data-stu-id="829f1-118">Before you begin, make sure that Windows Server is up-to-date by using Windows Update.</span></span> 
  
![Windows Server atualizado.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
<span data-ttu-id="829f1-120">Assista as etapas do vídeo para **os pré-requisitos de instalação**:</span><span class="sxs-lookup"><span data-stu-id="829f1-120">Watch the video steps for **install prerequisites**:</span></span>
  
![Seu navegador não oferece suporte a vídeo. Instale o Microsoft Silverlight, o Adobe Flash Player ou o Internet Explorer 9.](../../media/MSN_Video_Widget.gif)
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a><span data-ttu-id="829f1-123">Instale as funções e os recursos necessários para os servidores front-end</span><span class="sxs-lookup"><span data-stu-id="829f1-123">Install required roles and features for front-end servers</span></span>

1. <span data-ttu-id="829f1-124">Abra o Server Manager e clique em **Adicionar funções e recurso**.</span><span class="sxs-lookup"><span data-stu-id="829f1-124">Open Server Manager, and click **Add roles and features**.</span></span>
    
2. <span data-ttu-id="829f1-125">Leia a página **Antes de Começar** para se familiarizar com a instalação de funções e recursos no Windows Server, e depois clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="829f1-125">Read the **Before You Begin** page to familiarize yourself with installing roles and features in Windows Server, and then click **Next**.</span></span>
    
3. <span data-ttu-id="829f1-126">Selecione **Instalação baseada em função ou baseada em recurso**, e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="829f1-126">Select **Role-based or feature-based installation**, and click **Next**.</span></span>
    
4. <span data-ttu-id="829f1-127">Selecione o servidor no qual você será instalando Skype para Business Server 2015 e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="829f1-127">Select the server on which you will be installing Skype for Business Server 2015, and click **Next**.</span></span>
    
5. <span data-ttu-id="829f1-128">Selecione a função **Servidor Web (IIS)**, e quando a janela de recursos obrigatórios aparecer, clique em **Adicionar recursos**, e depois clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="829f1-128">Select the **Web Server (IIS)** role, and when the required features window pops up, click **Add Features**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="829f1-129">Verifique se os recursos de software listados no [Software que deve ser instalado antes de um Skype para implantação Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#Software) estão no servidor que executará o Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="829f1-129">Make sure the software features listed in [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#Software) are on the server that will run Skype for Business Server 2015.</span></span> <span data-ttu-id="829f1-130">Aqui está uma lista resumida:</span><span class="sxs-lookup"><span data-stu-id="829f1-130">Here's an abbreviated list:</span></span>
    
   - <span data-ttu-id="829f1-131">Recursos do .NET framework</span><span class="sxs-lookup"><span data-stu-id="829f1-131">.NET Framework Features</span></span>
    
   - <span data-ttu-id="829f1-132">Recursos do WCF</span><span class="sxs-lookup"><span data-stu-id="829f1-132">WCF Services</span></span>
    
   - <span data-ttu-id="829f1-133">Ativação HTTP</span><span class="sxs-lookup"><span data-stu-id="829f1-133">HTTP Activation</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="829f1-p108">A Ativação HTTP requer recursos adicionais. Clique em **Adicionar recursos** para ver a caixa de diálogo que aparecerá quando você selecionar Ativação HTTP.</span><span class="sxs-lookup"><span data-stu-id="829f1-p108">HTTP Activation requires additional features. Click **Add Features** to the warning dialog box that pops up when you select HTTP Activation.</span></span>
  
   - <span data-ttu-id="829f1-136">Media Foundation (necessário para servidores Front-End e servidores Standard Edition usadas para conferências).</span><span class="sxs-lookup"><span data-stu-id="829f1-136">Media Foundation (required by Front End Servers and Standard Edition servers used for conferencing.)</span></span>
    
   - <span data-ttu-id="829f1-137">AD DS and AD LDS ToolsFerramentas de Administração de Servidor Remoto</span><span class="sxs-lookup"><span data-stu-id="829f1-137">Remote Server Administration Tools</span></span>
    
   - <span data-ttu-id="829f1-138">Ferramentas de Administração de Funções</span><span class="sxs-lookup"><span data-stu-id="829f1-138">Role Administration Tools</span></span>
    
   - <span data-ttu-id="829f1-139">AD DS</span><span class="sxs-lookup"><span data-stu-id="829f1-139">AD DS</span></span> 
    
   - <span data-ttu-id="829f1-140">O AD LDS</span><span class="sxs-lookup"><span data-stu-id="829f1-140">AD LDS</span></span>
    
   - <span data-ttu-id="829f1-141">Windows Identity Foundation 3.5</span><span class="sxs-lookup"><span data-stu-id="829f1-141">Windows Identity Foundation 3.5</span></span>
    
7. <span data-ttu-id="829f1-142">Clique em **Avançar** para continuar no assistente.</span><span class="sxs-lookup"><span data-stu-id="829f1-142">Click **Next** to continue through the wizard.</span></span>
    
8. <span data-ttu-id="829f1-143">Leia as observações sobre a **Função Servidor Web (IIS)**, e depois clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="829f1-143">Read through the notes about the **Web Server Role (IIS)**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="829f1-144">Selecione os seguintes **serviços de função Servidor Web (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="829f1-144">Select the following **Web Server (IIS) role services**.</span></span>
    
   - <span data-ttu-id="829f1-145">Recursos HTTP Comuns</span><span class="sxs-lookup"><span data-stu-id="829f1-145">Common HTTP Features</span></span>
    
   - <span data-ttu-id="829f1-146">Documento padrão</span><span class="sxs-lookup"><span data-stu-id="829f1-146">Default Document</span></span>
    
   - <span data-ttu-id="829f1-147">Pesquisa de diretório</span><span class="sxs-lookup"><span data-stu-id="829f1-147">Directory Browsing</span></span>
    
   - <span data-ttu-id="829f1-148">Erros HTTP</span><span class="sxs-lookup"><span data-stu-id="829f1-148">HTTP Errors</span></span>
    
   - <span data-ttu-id="829f1-149">Conteúdo estático</span><span class="sxs-lookup"><span data-stu-id="829f1-149">Static Content</span></span>
    
   - <span data-ttu-id="829f1-150">Integridade e Diagnósticos</span><span class="sxs-lookup"><span data-stu-id="829f1-150">Health and Diagnostics</span></span>
    
   - <span data-ttu-id="829f1-151">Log HTTP</span><span class="sxs-lookup"><span data-stu-id="829f1-151">HTTP Logging</span></span>
    
   - <span data-ttu-id="829f1-152">Ferramentas de log</span><span class="sxs-lookup"><span data-stu-id="829f1-152">Logging Tools</span></span>
    
   - <span data-ttu-id="829f1-153">Rastreamento</span><span class="sxs-lookup"><span data-stu-id="829f1-153">Tracing</span></span>
    
   - <span data-ttu-id="829f1-154">Desempenho</span><span class="sxs-lookup"><span data-stu-id="829f1-154">Performance</span></span>
    
   - <span data-ttu-id="829f1-155">Compressão de conteúdo estático</span><span class="sxs-lookup"><span data-stu-id="829f1-155">Static Content Compression</span></span>
    
   - <span data-ttu-id="829f1-156">Compactação de conteúdo dinâmico</span><span class="sxs-lookup"><span data-stu-id="829f1-156">Dynamic Content Compression</span></span>
    
   - <span data-ttu-id="829f1-157">Segurança</span><span class="sxs-lookup"><span data-stu-id="829f1-157">Security</span></span>
    
   - <span data-ttu-id="829f1-158">Requisição de filtro</span><span class="sxs-lookup"><span data-stu-id="829f1-158">Request Filtering</span></span>
    
   - <span data-ttu-id="829f1-159">Autenticação de mapeamento de certificado de cliente</span><span class="sxs-lookup"><span data-stu-id="829f1-159">Client Certificate Mapping Authentication</span></span>
    
   - <span data-ttu-id="829f1-160">Autenticação do Windows</span><span class="sxs-lookup"><span data-stu-id="829f1-160">Windows Authentication</span></span>
    
   - <span data-ttu-id="829f1-161">Desenvolvimento do aplicativo</span><span class="sxs-lookup"><span data-stu-id="829f1-161">Application Development</span></span>
    
   - <span data-ttu-id="829f1-162">Extensibilidade .NET 3.5</span><span class="sxs-lookup"><span data-stu-id="829f1-162">.NET Extensibility 3.5</span></span>
    
   - <span data-ttu-id="829f1-163">Extensibilidade .NET 4.5</span><span class="sxs-lookup"><span data-stu-id="829f1-163">.NET Extensibility 4.5</span></span>
    
   - <span data-ttu-id="829f1-164">ASP.NET 3.5</span><span class="sxs-lookup"><span data-stu-id="829f1-164">ASP.NET 3.5</span></span>
    
   - <span data-ttu-id="829f1-165">ASP.NET 4.5</span><span class="sxs-lookup"><span data-stu-id="829f1-165">ASP.NET 4.5</span></span>
    
   - <span data-ttu-id="829f1-166">Extensões ISAPI</span><span class="sxs-lookup"><span data-stu-id="829f1-166">ISAPI Extensions</span></span>
    
   - <span data-ttu-id="829f1-167">Filtros ISAPI</span><span class="sxs-lookup"><span data-stu-id="829f1-167">ISAPI Filters</span></span>
    
   - <span data-ttu-id="829f1-168">Ferramentas de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="829f1-168">Management Tools</span></span>
    
   - <span data-ttu-id="829f1-169">Console de gerenciamento IIS</span><span class="sxs-lookup"><span data-stu-id="829f1-169">IIS Management Console</span></span>
    
   - <span data-ttu-id="829f1-170">Ferramentas e scripts de gerenciamento IIS</span><span class="sxs-lookup"><span data-stu-id="829f1-170">IIS Management Scripts and Tools</span></span>
    
10. <span data-ttu-id="829f1-171">Clique em **Avançar** para continuar no assistente.</span><span class="sxs-lookup"><span data-stu-id="829f1-171">Click **Next** to continue through the wizard.</span></span>
    
11. <span data-ttu-id="829f1-172">Examine as seleções de instalação para certificar-se de que todos os requisitos foram selecionados e clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="829f1-172">Review the installation selections to make sure all requirements are selected, and then click **Install**.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="829f1-173">O Windows Server 2012 R2 não instala todos os arquivo de origem para os recursos necessários por padrão.</span><span class="sxs-lookup"><span data-stu-id="829f1-173">Windows Server 2012 R2 does not install all of the source files for the required features by default.</span></span> <span data-ttu-id="829f1-174">Se o servidor não estiver conectado à Internet, você terá que inserir a mídia do Windows Server 2012 R2 e selecionar **Especificar um caminho de origem alternativo** para instalar os recursos necessários.</span><span class="sxs-lookup"><span data-stu-id="829f1-174">If the server is not connected to the Internet, you will need to insert the Windows Server 2012 R2 media and select **Specify an alternate source path** in order to install the required features.</span></span> <span data-ttu-id="829f1-175">Os arquivos de origem estão localizados no diretório sources\sxs.</span><span class="sxs-lookup"><span data-stu-id="829f1-175">The source files are located in the sources\sxs directory.</span></span> <span data-ttu-id="829f1-176">Por exemplo, se a mídia do Windows Server 2012 R2 estiver na unidade D, você teria que definir o caminho como `d:\sources\sxs`.</span><span class="sxs-lookup"><span data-stu-id="829f1-176">For example, if the Windows Server 2012 R2 media is in drive D, you would set the path to `d:\sources\sxs`.</span></span> <span data-ttu-id="829f1-177">> É importante que você tenha as atualizações mais recentes do Windows Update.</span><span class="sxs-lookup"><span data-stu-id="829f1-177">> It is important that you have the latest updates from Windows Update.</span></span> <span data-ttu-id="829f1-178">Se você não estiver conectado à Internet, terá que instalar manualmente todas as atualizações importantes, bem como quaisquer pré-requisitos para as atualizações necessárias.</span><span class="sxs-lookup"><span data-stu-id="829f1-178">If you are not connected to the Internet, you will need to manually install all relevant updates as well as any prerequisites to the required updates.</span></span> 
  
12. <span data-ttu-id="829f1-179">Quando a caixa de diálogo indicar que a instalação foi concluída, você terá que reiniciar o servidor para concluir o processo.</span><span class="sxs-lookup"><span data-stu-id="829f1-179">When the dialog box indicates that the installation has completed, you will need to reboot the server to complete the process.</span></span>
    
13. <span data-ttu-id="829f1-180">Execute o **Windows Update** novamente para verificar se há alguma atualização para as funções e os serviços que foram instalados.</span><span class="sxs-lookup"><span data-stu-id="829f1-180">Run **Windows Update** again to check if there are any updates to the roles and services that were installed.</span></span>
    
14. <span data-ttu-id="829f1-181">Se você for usar Skype para painel de controle do Business Server neste servidor você também deve instalar o Silverlight.</span><span class="sxs-lookup"><span data-stu-id="829f1-181">If you will be using Skype for Business Server Control Panel on this server then you must also install Silverlight.</span></span> <span data-ttu-id="829f1-182">Para instalar o Silverlight, consulte [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span><span class="sxs-lookup"><span data-stu-id="829f1-182">To install Silverlight, see [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span></span>
    
<span data-ttu-id="829f1-183">Os pré-requisitos podem ser instalados executando o seguinte comando PowerShell.</span><span class="sxs-lookup"><span data-stu-id="829f1-183">The prerequisites can be installed by running the following PowerShell command.</span></span> <span data-ttu-id="829f1-184">Observe que o comando procura arquivos de origem em uma ordem específica.</span><span class="sxs-lookup"><span data-stu-id="829f1-184">Note that the command looks for source files in a specific order.</span></span> <span data-ttu-id="829f1-185">Se você estiver online, o comando acessa o Windows Update.</span><span class="sxs-lookup"><span data-stu-id="829f1-185">If you are online, the command accesses Windows Update.</span></span> <span data-ttu-id="829f1-186">No entanto, se você estiver offline, terá que verificar se os arquivos de origem estão disponíveis para o comando.</span><span class="sxs-lookup"><span data-stu-id="829f1-186">However, if you are offline, you need to make sure the source files are available to the command.</span></span> <span data-ttu-id="829f1-187">Para obter mais informações sobre como usar o PowerShell para instalar as funções e recursos, consulte [instalar ou desinstalar funções, serviços de função ou recursos](https://technet.microsoft.com/en-us/library/hh831809.aspx) e [Install-WindowsFeature](https://technet.microsoft.com/en-us/library/jj205467.aspx).</span><span class="sxs-lookup"><span data-stu-id="829f1-187">For more information about using PowerShell to install roles and features, see [Install or Uninstall Roles, Role Services, or Features](https://technet.microsoft.com/en-us/library/hh831809.aspx) and [Install-WindowsFeature](https://technet.microsoft.com/en-us/library/jj205467.aspx).</span></span> <span data-ttu-id="829f1-188">Não se esqueça de executar o Windows Update novamente após instalar os pré-requisitos, mesmo se você usar o comando PowerShell.</span><span class="sxs-lookup"><span data-stu-id="829f1-188">Don't forget to run Windows Update again after you install prerequisites, even if you use the PowerShell command.</span></span>
```
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS
```

> [!IMPORTANT]
> <span data-ttu-id="829f1-189">Os pré-requisitos para servidores executando funções diferentes da de servidor front-end, como a função de Diretor, Chat Persistente ou Borda, terão seus próprios pré-requisitos.</span><span class="sxs-lookup"><span data-stu-id="829f1-189">The prerequisites for servers performing roles other than front-end server, such as the role of Director, Persistent Chat, or Edge, have their own prerequisites.</span></span> <span data-ttu-id="829f1-190">Para obter detalhes sobre os pré-requisitos exatos exigidos por cada tipo de servidor, consulte [requisitos de servidor para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="829f1-190">For details on the exact prerequisites required by each server type, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span> 
  

