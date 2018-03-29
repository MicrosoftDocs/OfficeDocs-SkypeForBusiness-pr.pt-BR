---
title: Atualização do Gerenciador de estatísticas do Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/10/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: 'Resumo: Leia este tópico para saber como atualizar o Gerenciador de estatísticas Skype for Business Server 2015.'
ms.openlocfilehash: e5a9dd230f16313388cbb9a51e50910979e6c79c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server-2015"></a><span data-ttu-id="f4183-103">Atualização do Gerenciador de estatísticas do Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="f4183-103">Upgrade Statistics Manager for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f4183-104">**Resumo:** Leia este tópico para saber como atualizar o Gerenciador de estatísticas Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="f4183-104">**Summary:** Read this topic to learn how to upgrade Statistics Manager for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="f4183-105">Este tópico descreve como atualizar uma instalação existente do Gerenciador de estatísticas Skype for Business Server — uma ferramenta poderosa que permite que você visualize Skype para dados de integridade e desempenho do servidor de negócios em tempo real.</span><span class="sxs-lookup"><span data-stu-id="f4183-105">This topic describes how to upgrade an existing installation of Statistics Manager for Skype for Business Server—a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="f4183-106">Você pode sondar dados de desempenho em centenas de servidores por cada alguns segundos e exiba os resultados instantaneamente no site do Gerenciador de estatísticas.</span><span class="sxs-lookup"><span data-stu-id="f4183-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span> 
  
<span data-ttu-id="f4183-107">Para obter mais informações sobre o Gerenciador de estatísticas e os novos recursos na versão 1.1, consulte [Planejar para o Gerenciador de estatísticas de Skype para Business Server 2015](plan.md) e o [Gerente estatísticas implantar Skype para Business Server 2015](deploy.md).</span><span class="sxs-lookup"><span data-stu-id="f4183-107">For more information about Statistics Manager and the new features in Release 1.1, see [Plan for Statistics Manager for Skype for Business Server 2015](plan.md) and [Deploy Statistics Manager for Skype for Business Server 2015](deploy.md).</span></span> <span data-ttu-id="f4183-108">Para obter informações sobre problemas conhecidos corrigidos na versão 1.1, veja [Problemas conhecidos corrigidos na versão 1.1](upgrade.md#BKMK_Fixed).</span><span class="sxs-lookup"><span data-stu-id="f4183-108">For information about known issues fixed in Release 1.1, see [Known issues fixed in release 1.1](upgrade.md#BKMK_Fixed).</span></span>
  
<span data-ttu-id="f4183-109">Existem dois métodos para a atualização:</span><span class="sxs-lookup"><span data-stu-id="f4183-109">There are two methods for upgrading:</span></span>
  
- <span data-ttu-id="f4183-110">**Atualização automatizada.**</span><span class="sxs-lookup"><span data-stu-id="f4183-110">**Automated upgrade.**</span></span> <span data-ttu-id="f4183-111">Este método usa um script automatizado.</span><span class="sxs-lookup"><span data-stu-id="f4183-111">This method uses an automated script.</span></span> <span data-ttu-id="f4183-112">É o método mais fácil e deve ser aplicável a todos os cenários de atualização.</span><span class="sxs-lookup"><span data-stu-id="f4183-112">It is the easiest method and should be applicable to all upgrade scenarios.</span></span>
    
- <span data-ttu-id="f4183-113">**Atualização manual.**</span><span class="sxs-lookup"><span data-stu-id="f4183-113">**Manual upgrade.**</span></span> <span data-ttu-id="f4183-114">Este método é fornecido como um plano de backup no caso incomum que está falhando a atualização automatizada.</span><span class="sxs-lookup"><span data-stu-id="f4183-114">This method is provided as a backup plan in the unusual case that the automated upgrade fails.</span></span>
    
## <a name="prerequisites"></a><span data-ttu-id="f4183-115">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="f4183-115">Prerequisites</span></span>

<span data-ttu-id="f4183-116">Antes de atualizar, certifique-se de ter as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="f4183-116">Before you upgrade, be sure you have the following information:</span></span>
  
- <span data-ttu-id="f4183-117">Impressão digital do certificado do Ouvinte ativo</span><span class="sxs-lookup"><span data-stu-id="f4183-117">Active Listener Certificate Thumbprint</span></span>
    
- <span data-ttu-id="f4183-118">Senha de serviço do Ouvinte (inserida na instalação do Ouvinte e de cada Agente)</span><span class="sxs-lookup"><span data-stu-id="f4183-118">Listener Service Password (entered on install of the listener and every agent)</span></span>
    
- <span data-ttu-id="f4183-119">Configuração de Certificado SSL do site da Web</span><span class="sxs-lookup"><span data-stu-id="f4183-119">SSL Certificate configuration for the website</span></span>
    
## <a name="automated-upgrade"></a><span data-ttu-id="f4183-120">Atualização automatizada</span><span class="sxs-lookup"><span data-stu-id="f4183-120">Automated upgrade</span></span>

<span data-ttu-id="f4183-121">O script reunirá suas informações de certificado e senha do ouvinte atuais, desinstalará a versão antiga do produto e, em seguida, instalará a nova versão.</span><span class="sxs-lookup"><span data-stu-id="f4183-121">The script will gather your current certificate information and listener password, uninstall the old version of the product, and then install the new version of the product.</span></span> <span data-ttu-id="f4183-122">A instância do Redis instalada no servidor não será alterada, portanto, todos os dados armazenados no cache serão retidos no processo de atualização.</span><span class="sxs-lookup"><span data-stu-id="f4183-122">The Redis instance installed on the server will not be touched, so any data stored in the cache will be retained through the upgrade process.</span></span>
  
1. <span data-ttu-id="f4183-123">Coloque os arquivos MSI da nova versão do agente, ouvinte e site juntamente com o script StatsMan.ps1 de atualização em uma única pasta no computador ouvinte.</span><span class="sxs-lookup"><span data-stu-id="f4183-123">Place the MSI files for the new version of the agent, listener and website along with the Update-StatsMan.ps1 script into a single folder on the Listener computer.</span></span>
    
2. <span data-ttu-id="f4183-124">Abra uma janela de administrador do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f4183-124">Open an administrative PowerShell window.</span></span> <span data-ttu-id="f4183-125">Atualize o componente do Ouvinte:</span><span class="sxs-lookup"><span data-stu-id="f4183-125">Upgrade the Listener component:</span></span>
    
  ```
  .\Update-StatsMan.ps1 -Service Listener
  ```

> [!NOTE]
> <span data-ttu-id="f4183-126">A senha do serviço Gerenciador de estatísticas será exibida em texto não criptografado na linha de comando conforme ele é passado para o instalador.</span><span class="sxs-lookup"><span data-stu-id="f4183-126">The Statistics Manager service password will be displayed in clear text on the command line as it is passed to the installer.</span></span> <span data-ttu-id="f4183-127">Proteja seu monitor conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="f4183-127">Be sure to shield your monitor as needed.</span></span> 
  
1. <span data-ttu-id="f4183-128">Na execução do script, você será solicitado a desinstalar a versão antiga do produto.</span><span class="sxs-lookup"><span data-stu-id="f4183-128">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="f4183-129">Responda Sim.</span><span class="sxs-lookup"><span data-stu-id="f4183-129">Answer Yes.</span></span>
    
2. <span data-ttu-id="f4183-130">Se o serviço Ouvinte estiver em operação, você será solicitado a fechar o aplicativo antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="f4183-130">If the Listener service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="f4183-131">Permitir que o aplicativo fechar (o ouvinte do Gerenciador de estatísticas serviço será interrompido).</span><span class="sxs-lookup"><span data-stu-id="f4183-131">Allow the application to close (the Statistics Manager Listener service will be stopped).</span></span>
    
3. <span data-ttu-id="f4183-132">Continue o processo de instalação.</span><span class="sxs-lookup"><span data-stu-id="f4183-132">Continue the install process.</span></span> <span data-ttu-id="f4183-133">Você notará que a senha de serviço e a impressão digital do certificado são pré-preenchidos.</span><span class="sxs-lookup"><span data-stu-id="f4183-133">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="f4183-134">Se não forem, adicione os valores salvos antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="f4183-134">If not, add the values you saved before continuing.</span></span>
    
3. <span data-ttu-id="f4183-135">Abra uma janela de administrador do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f4183-135">Open an administrative PowerShell window.</span></span> <span data-ttu-id="f4183-136">Atualize o componente do site:</span><span class="sxs-lookup"><span data-stu-id="f4183-136">Upgrade the Website component:</span></span>
    
  ```
  .\Update-StatsMan.ps1 -Service Website
  ```

1. <span data-ttu-id="f4183-137">Na execução do script, você será solicitado a desinstalar a versão antiga do produto.</span><span class="sxs-lookup"><span data-stu-id="f4183-137">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="f4183-138">Responda Sim.</span><span class="sxs-lookup"><span data-stu-id="f4183-138">Answer Yes.</span></span>
    
2. <span data-ttu-id="f4183-139">Se o serviço do Agente estiver em operação, você será solicitado a fechar o aplicativo antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="f4183-139">If the Agent service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="f4183-140">Permita que o aplicativo seja fechado (o serviço do Agente StatsMan será interrompido).</span><span class="sxs-lookup"><span data-stu-id="f4183-140">Allow the application to close (the StatsMan Agent service will be stopped).</span></span>
    
3. <span data-ttu-id="f4183-141">Continue o processo de instalação.</span><span class="sxs-lookup"><span data-stu-id="f4183-141">Continue the install process.</span></span> <span data-ttu-id="f4183-142">Você notará que a senha de serviço e a impressão digital do certificado são pré-preenchidos.</span><span class="sxs-lookup"><span data-stu-id="f4183-142">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="f4183-143">Se não forem, adicione os valores salvos antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="f4183-143">If not, add the values you saved before continuing.</span></span>
    
4. <span data-ttu-id="f4183-144">Abra uma janela de administrador do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f4183-144">Open an administrative PowerShell window.</span></span> <span data-ttu-id="f4183-145">Atualize o componente do Agente:</span><span class="sxs-lookup"><span data-stu-id="f4183-145">Upgrade the Agent component:</span></span>
    
  ```
  .\Update-StatsMan.ps1 -Service Agent
  ```

1. <span data-ttu-id="f4183-146">Na execução do script, você será solicitado a desinstalar a versão antiga do produto.</span><span class="sxs-lookup"><span data-stu-id="f4183-146">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="f4183-147">Responda Sim.</span><span class="sxs-lookup"><span data-stu-id="f4183-147">Answer Yes.</span></span>
    
2. <span data-ttu-id="f4183-148">Continue o processo de instalação.</span><span class="sxs-lookup"><span data-stu-id="f4183-148">Continue the install process.</span></span> <span data-ttu-id="f4183-149">Você notará que a porta do site é pré-preenchida.</span><span class="sxs-lookup"><span data-stu-id="f4183-149">You should notice that the website port is pre-populated.</span></span> <span data-ttu-id="f4183-150">Se não for, adicione o valor salvo antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="f4183-150">If not, add the value you saved before continuing.</span></span>
    
3. <span data-ttu-id="f4183-151">Verifique se o site está funcionando conforme esperado usando o navegador.</span><span class="sxs-lookup"><span data-stu-id="f4183-151">Verify the website is working as expected using the browser.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f4183-152">A atualização do Agente pode ser usada com o comutador -NoPrompt.</span><span class="sxs-lookup"><span data-stu-id="f4183-152">The Agent upgrade can be used with the -NoPrompt switch.</span></span> <span data-ttu-id="f4183-153">Isso permitirá que o processo de desinstalação/instalação seja executado silenciosamente, permitindo que ferramentas como PSExec sejam executadas remotamente durante a atualização em vários servidores.</span><span class="sxs-lookup"><span data-stu-id="f4183-153">This will allow the uninstall/install process to run silently, allowing tools such as PSExec to run the upgrade remotely on a large number of servers.</span></span> 
  
### <a name="manual-upgrade"></a><span data-ttu-id="f4183-154">Atualização manual</span><span class="sxs-lookup"><span data-stu-id="f4183-154">Manual upgrade</span></span>

<span data-ttu-id="f4183-155">Se, por algum motivo, a atualização automatizada falhar, é possível executar uma atualização manual da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="f4183-155">If for some reason, the automated upgrade fails, you can always perform a manual upgrade as follows:</span></span>
  
1. <span data-ttu-id="f4183-156">	No computador Ouvinte, desinstale o Ouvinte, o Site e o Agente (se instalados no servidor) através do painel de controle Programas e Recursos.  </span><span class="sxs-lookup"><span data-stu-id="f4183-156">On the Listener computer, uninstall the Listener, Website and the Agent (if it was installed on this server) via the Programs and Features control panel.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="f4183-157"> Mantenha o Redis instalado para que os dados no cache sejam mantidos durante o processo de atualização.</span><span class="sxs-lookup"><span data-stu-id="f4183-157">Keep Redis installed so that the data in the cache will then be maintained through the upgrade process.</span></span>
  
2. <span data-ttu-id="f4183-p119">	Instale as novas versões dos componentes, incluindo os valores salvos acima quando solicitados. Para obter mais informações sobre como instalar componentes, veja [Implantar o Gerenciador de Estatísticas](deploy.md#BKMK_Deploy)</span><span class="sxs-lookup"><span data-stu-id="f4183-p119">Install the new versions of the components, including the values you saved above when prompted for them. For more information about installing components, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy)</span></span>
    
## <a name="known-issues-fixed-in-release-11"></a><span data-ttu-id="f4183-160">Problemas conhecidos corrigidos na versão 1.1</span><span class="sxs-lookup"><span data-stu-id="f4183-160">Known issues fixed in release 1.1</span></span>
<span data-ttu-id="f4183-161"><a name="BKMK_Fixed"> </a></span><span class="sxs-lookup"><span data-stu-id="f4183-161"></span></span>

<span data-ttu-id="f4183-162">Os seguintes problemas conhecidos foram corrigidos na versão 1.1:</span><span class="sxs-lookup"><span data-stu-id="f4183-162">The following known issues have been fixed in release 1.1:</span></span>
  
- <span data-ttu-id="f4183-163">Interface do usuário/Server/Agent - diversas melhorias no desempenho e confiabilidade significativa</span><span class="sxs-lookup"><span data-stu-id="f4183-163">UI/Server/Agent - Numerous significant reliability and performance improvements</span></span>
    
- <span data-ttu-id="f4183-164">Interface do usuário - controle de filtro principal agora classificará corretamente com diferentes casos (foi gerando pessoas pensar determinados servidores não estavam no sistema quando fossem)</span><span class="sxs-lookup"><span data-stu-id="f4183-164">UI - Main filter control now sorts correctly with different cases (was leading people to think certain servers weren't in the system when they were)</span></span>
    
- <span data-ttu-id="f4183-165">Servidor - Os componentes de servidor agora serão instalados em servidores que não estiverem em inglês.</span><span class="sxs-lookup"><span data-stu-id="f4183-165">Server - Server components will now install on non-English servers.</span></span>
    
- <span data-ttu-id="f4183-166">Servidor/Agente - Em alguns casos, os componentes de agente e servidor não eram instalados, com erros .NET devido a uma versão específica do .NET 4.0.</span><span class="sxs-lookup"><span data-stu-id="f4183-166">Server/Agent - In some cases, agent and server components would not install with .NET errors due to a specific version of .NET 4.0.</span></span> <span data-ttu-id="f4183-167">Isso foi resolvido.</span><span class="sxs-lookup"><span data-stu-id="f4183-167">This has been resolved.</span></span>
    
- <span data-ttu-id="f4183-168">Agente - estendido adicionado para o agente de StatsMan do log de eventos.</span><span class="sxs-lookup"><span data-stu-id="f4183-168">Agent - Extended event logging added for the StatsMan Agent.</span></span> <span data-ttu-id="f4183-169">O agente não travará mais quando instalado em um servidor que não está na topologia, isso agora é registrado no log de eventos, junto com muitas outras possíveis condições de erro.</span><span class="sxs-lookup"><span data-stu-id="f4183-169">The agent will no longer crash when installed on a server not in the topology, this will now be logged in the event log, along with many other possible error conditions.</span></span>
    
- <span data-ttu-id="f4183-170">Interface do usuário - clientes Web usando o navegador Chrome veria vários prompts de logon quando usando um computador cliente não ingressou no mesmo grupo de trabalho ou domínio como o servidor Web do Gerenciador de estatísticas.</span><span class="sxs-lookup"><span data-stu-id="f4183-170">UI - Web clients using the Chrome browser would see multiple login prompts when using a client computer not joined to the same workgroup or domain as the Statistics Manager Web server.</span></span> <span data-ttu-id="f4183-171">Agora, apenas um único logon deve ser exigido por sessão.</span><span class="sxs-lookup"><span data-stu-id="f4183-171">Now only a single login should be required per session.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="f4183-172">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="f4183-172">For more information</span></span>
<span data-ttu-id="f4183-173"><a name="BKMK_Fixed"> </a></span><span class="sxs-lookup"><span data-stu-id="f4183-173"></span></span>

<span data-ttu-id="f4183-174">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="f4183-174">For more information, see the following:</span></span>
  
- [<span data-ttu-id="f4183-175">Planejar para o Gerenciador de estatísticas de Skype Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="f4183-175">Plan for Statistics Manager for Skype for Business Server 2015</span></span>](plan.md)
    
- [<span data-ttu-id="f4183-176">Implantar o Gerenciador de estatísticas para Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="f4183-176">Deploy Statistics Manager for Skype for Business Server 2015</span></span>](deploy.md)
    
- [<span data-ttu-id="f4183-177">Solucionar problemas de gerente de estatísticas para Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="f4183-177">Troubleshoot Statistics Manager for Skype for Business Server 2015</span></span>](troubleshoot.md)
    
- [<span data-ttu-id="f4183-178">Skype para o blog do Gerenciador de estatísticas do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="f4183-178">Skype for Business Server Statistics Manager blog</span></span>](https://blogs.technet.microsoft.com/skypestatsman/)
    

