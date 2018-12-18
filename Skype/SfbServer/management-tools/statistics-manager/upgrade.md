---
title: Atualizar o Gerenciador de estatísticas para Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: 'Resumo: Leia este tópico para saber como atualizar o Gerenciador de estatísticas Skype for Business Server.'
ms.openlocfilehash: e2118377fc782af6818d070bc0bd3f5ddacab99e
ms.sourcegitcommit: 8279beffec35fe8a75968245c6cb09f1d622370f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/18/2018
ms.locfileid: "27297892"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="d0688-103">Atualizar o Gerenciador de estatísticas para Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="d0688-103">Upgrade Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="d0688-104">**Resumo:** Leia este tópico para saber como atualizar o Gerenciador de estatísticas Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d0688-104">**Summary:** Read this topic to learn how to upgrade Statistics Manager for Skype for Business Server.</span></span>
  
<span data-ttu-id="d0688-105">Este tópico descreve como atualizar uma instalação existente do Gerenciador de estatísticas Skype for Business Server — uma ferramenta poderosa que permite que você visualize Skype para dados de integridade e desempenho do servidor de negócios em tempo real.</span><span class="sxs-lookup"><span data-stu-id="d0688-105">This topic describes how to upgrade an existing installation of Statistics Manager for Skype for Business Server—a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="d0688-106">Você pode sondar dados de desempenho em centenas de servidores por cada alguns segundos e exiba os resultados instantaneamente no site do Gerenciador de estatísticas.</span><span class="sxs-lookup"><span data-stu-id="d0688-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span> 
  
<span data-ttu-id="d0688-107">Para obter mais informações sobre o Gerenciador de estatísticas e os novos recursos na versão 2.0, consulte [Planejar para o Gerenciador de estatísticas de Skype para Business Server](plan.md) e o [Gerente estatísticas implantar Skype para Business Server](deploy.md).</span><span class="sxs-lookup"><span data-stu-id="d0688-107">For more information about Statistics Manager and the new features in Release 2.0, see [Plan for Statistics Manager for Skype for Business Server](plan.md) and [Deploy Statistics Manager for Skype for Business Server](deploy.md).</span></span>
  
<span data-ttu-id="d0688-108">Existem dois métodos para a atualização:</span><span class="sxs-lookup"><span data-stu-id="d0688-108">There are two methods for upgrading:</span></span>
  
- <span data-ttu-id="d0688-109">**Atualização automatizada.**</span><span class="sxs-lookup"><span data-stu-id="d0688-109">**Automated upgrade.**</span></span> <span data-ttu-id="d0688-110">Este método usa um script automatizado.</span><span class="sxs-lookup"><span data-stu-id="d0688-110">This method uses an automated script.</span></span> <span data-ttu-id="d0688-111">É o método mais fácil e deve ser aplicável a todos os cenários de atualização.</span><span class="sxs-lookup"><span data-stu-id="d0688-111">It is the easiest method and should be applicable to all upgrade scenarios.</span></span>
    
- <span data-ttu-id="d0688-112">**Atualização manual.**</span><span class="sxs-lookup"><span data-stu-id="d0688-112">**Manual upgrade.**</span></span> <span data-ttu-id="d0688-113">Este método é fornecido como um plano de backup no caso incomum que está falhando a atualização automatizada.</span><span class="sxs-lookup"><span data-stu-id="d0688-113">This method is provided as a backup plan in the unusual case that the automated upgrade fails.</span></span>
    
## <a name="prerequisites"></a><span data-ttu-id="d0688-114">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="d0688-114">Prerequisites</span></span>

<span data-ttu-id="d0688-115">Antes de atualizar, certifique-se de ter as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="d0688-115">Before you upgrade, be sure you have the following information:</span></span>
  
- <span data-ttu-id="d0688-116">Impressão digital do certificado do Ouvinte ativo</span><span class="sxs-lookup"><span data-stu-id="d0688-116">Active Listener Certificate Thumbprint</span></span>
    
- <span data-ttu-id="d0688-117">Senha de serviço do Ouvinte (inserida na instalação do Ouvinte e de cada Agente)</span><span class="sxs-lookup"><span data-stu-id="d0688-117">Listener Service Password (entered on install of the listener and every agent)</span></span>
    
- <span data-ttu-id="d0688-118">Configuração de Certificado SSL do site da Web</span><span class="sxs-lookup"><span data-stu-id="d0688-118">SSL Certificate configuration for the website</span></span>
    
## <a name="automated-upgrade"></a><span data-ttu-id="d0688-119">Atualização automatizada</span><span class="sxs-lookup"><span data-stu-id="d0688-119">Automated upgrade</span></span>

<span data-ttu-id="d0688-120">O script reunirá suas informações de certificado e senha do ouvinte atuais, desinstalará a versão antiga do produto e, em seguida, instalará a nova versão.</span><span class="sxs-lookup"><span data-stu-id="d0688-120">The script will gather your current certificate information and listener password, uninstall the old version of the product, and then install the new version of the product.</span></span> <span data-ttu-id="d0688-121">A instância do Redis instalada no servidor não será alterada, portanto, todos os dados armazenados no cache serão retidos no processo de atualização.</span><span class="sxs-lookup"><span data-stu-id="d0688-121">The Redis instance installed on the server will not be touched, so any data stored in the cache will be retained through the upgrade process.</span></span>
  
1. <span data-ttu-id="d0688-122">Coloque os arquivos MSI da nova versão do agente, ouvinte e site juntamente com o script StatsMan.ps1 de atualização em uma única pasta no computador ouvinte.</span><span class="sxs-lookup"><span data-stu-id="d0688-122">Place the MSI files for the new version of the agent, listener and website along with the Update-StatsMan.ps1 script into a single folder on the Listener computer.</span></span>
    
2. <span data-ttu-id="d0688-123">Abra uma janela de administrador do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d0688-123">Open an administrative PowerShell window.</span></span> <span data-ttu-id="d0688-124">Atualize o componente do Ouvinte:</span><span class="sxs-lookup"><span data-stu-id="d0688-124">Upgrade the Listener component:</span></span>
    
   ```
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> <span data-ttu-id="d0688-125">A senha do serviço Gerenciador de estatísticas será exibida em texto não criptografado na linha de comando conforme ele é passado para o instalador.</span><span class="sxs-lookup"><span data-stu-id="d0688-125">The Statistics Manager service password will be displayed in clear text on the command line as it is passed to the installer.</span></span> <span data-ttu-id="d0688-126">Proteja seu monitor conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="d0688-126">Be sure to shield your monitor as needed.</span></span> 
  
1. <span data-ttu-id="d0688-127">Na execução do script, você será solicitado a desinstalar a versão antiga do produto.</span><span class="sxs-lookup"><span data-stu-id="d0688-127">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="d0688-128">Responda Sim.</span><span class="sxs-lookup"><span data-stu-id="d0688-128">Answer Yes.</span></span>
    
2. <span data-ttu-id="d0688-129">Se o serviço Ouvinte estiver em operação, você será solicitado a fechar o aplicativo antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="d0688-129">If the Listener service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="d0688-130">Permitir que o aplicativo fechar (o ouvinte do Gerenciador de estatísticas serviço será interrompido).</span><span class="sxs-lookup"><span data-stu-id="d0688-130">Allow the application to close (the Statistics Manager Listener service will be stopped).</span></span>
    
3. <span data-ttu-id="d0688-131">Continue o processo de instalação.</span><span class="sxs-lookup"><span data-stu-id="d0688-131">Continue the install process.</span></span> <span data-ttu-id="d0688-132">Você notará que a senha de serviço e a impressão digital do certificado são pré-preenchidos.</span><span class="sxs-lookup"><span data-stu-id="d0688-132">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="d0688-133">Se não forem, adicione os valores salvos antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="d0688-133">If not, add the values you saved before continuing.</span></span>
    
4. <span data-ttu-id="d0688-134">Abra uma janela de administrador do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d0688-134">Open an administrative PowerShell window.</span></span> <span data-ttu-id="d0688-135">Atualize o componente do site:</span><span class="sxs-lookup"><span data-stu-id="d0688-135">Upgrade the Website component:</span></span>
    
   ```
   .\Update-StatsMan.ps1 -Service Website
   ```

5. <span data-ttu-id="d0688-136">Na execução do script, você será solicitado a desinstalar a versão antiga do produto.</span><span class="sxs-lookup"><span data-stu-id="d0688-136">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="d0688-137">Responda Sim.</span><span class="sxs-lookup"><span data-stu-id="d0688-137">Answer Yes.</span></span>
    
6. <span data-ttu-id="d0688-138">Se o serviço do Agente estiver em operação, você será solicitado a fechar o aplicativo antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="d0688-138">If the Agent service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="d0688-139">Permita que o aplicativo seja fechado (o serviço do Agente StatsMan será interrompido).</span><span class="sxs-lookup"><span data-stu-id="d0688-139">Allow the application to close (the StatsMan Agent service will be stopped).</span></span>
    
7. <span data-ttu-id="d0688-140">Continue o processo de instalação.</span><span class="sxs-lookup"><span data-stu-id="d0688-140">Continue the install process.</span></span> <span data-ttu-id="d0688-141">Você notará que a senha de serviço e a impressão digital do certificado são pré-preenchidos.</span><span class="sxs-lookup"><span data-stu-id="d0688-141">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="d0688-142">Se não forem, adicione os valores salvos antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="d0688-142">If not, add the values you saved before continuing.</span></span>
    
8. <span data-ttu-id="d0688-143">Abra uma janela de administrador do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d0688-143">Open an administrative PowerShell window.</span></span> <span data-ttu-id="d0688-144">Atualize o componente do Agente:</span><span class="sxs-lookup"><span data-stu-id="d0688-144">Upgrade the Agent component:</span></span>
    
   ```
   .\Update-StatsMan.ps1 -Service Agent
   ```

9. <span data-ttu-id="d0688-145">Na execução do script, você será solicitado a desinstalar a versão antiga do produto.</span><span class="sxs-lookup"><span data-stu-id="d0688-145">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="d0688-146">Responda Sim.</span><span class="sxs-lookup"><span data-stu-id="d0688-146">Answer Yes.</span></span>
    
10. <span data-ttu-id="d0688-147">Continue o processo de instalação.</span><span class="sxs-lookup"><span data-stu-id="d0688-147">Continue the install process.</span></span> <span data-ttu-id="d0688-148">Você notará que a porta do site é pré-preenchida.</span><span class="sxs-lookup"><span data-stu-id="d0688-148">You should notice that the website port is pre-populated.</span></span> <span data-ttu-id="d0688-149">Se não for, adicione o valor salvo antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="d0688-149">If not, add the value you saved before continuing.</span></span>
    
11. <span data-ttu-id="d0688-150">Verifique se o site está funcionando conforme esperado usando o navegador.</span><span class="sxs-lookup"><span data-stu-id="d0688-150">Verify the website is working as expected using the browser.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d0688-151">A atualização do Agente pode ser usada com o comutador -NoPrompt.</span><span class="sxs-lookup"><span data-stu-id="d0688-151">The Agent upgrade can be used with the -NoPrompt switch.</span></span> <span data-ttu-id="d0688-152">Isso permitirá que o processo de desinstalação/instalação seja executado silenciosamente, permitindo que ferramentas como PSExec sejam executadas remotamente durante a atualização em vários servidores.</span><span class="sxs-lookup"><span data-stu-id="d0688-152">This will allow the uninstall/install process to run silently, allowing tools such as PSExec to run the upgrade remotely on a large number of servers.</span></span> 
  
### <a name="manual-upgrade"></a><span data-ttu-id="d0688-153">Atualização manual</span><span class="sxs-lookup"><span data-stu-id="d0688-153">Manual upgrade</span></span>

<span data-ttu-id="d0688-154">Se, por algum motivo, a atualização automatizada falhar, é possível executar uma atualização manual da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="d0688-154">If for some reason, the automated upgrade fails, you can always perform a manual upgrade as follows:</span></span>
  
1. <span data-ttu-id="d0688-155">	No computador Ouvinte, desinstale o Ouvinte, o Site e o Agente (se instalados no servidor) através do painel de controle Programas e Recursos.  </span><span class="sxs-lookup"><span data-stu-id="d0688-155">On the Listener computer, uninstall the Listener, Website and the Agent (if it was installed on this server) via the Programs and Features control panel.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="d0688-156"> Mantenha o Redis instalado para que os dados no cache sejam mantidos durante o processo de atualização.</span><span class="sxs-lookup"><span data-stu-id="d0688-156">Keep Redis installed so that the data in the cache will then be maintained through the upgrade process.</span></span>
  
2. <span data-ttu-id="d0688-p118">	Instale as novas versões dos componentes, incluindo os valores salvos acima quando solicitados. Para obter mais informações sobre como instalar componentes, veja [Implantar o Gerenciador de Estatísticas](deploy.md#BKMK_Deploy)</span><span class="sxs-lookup"><span data-stu-id="d0688-p118">Install the new versions of the components, including the values you saved above when prompted for them. For more information about installing components, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy)</span></span>

    
## <a name="for-more-information"></a><span data-ttu-id="d0688-159">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="d0688-159">For more information</span></span>
<span data-ttu-id="d0688-160"><a name="BKMK_Fixed"> </a></span><span class="sxs-lookup"><span data-stu-id="d0688-160"></span></span>

<span data-ttu-id="d0688-161">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="d0688-161">For more information, see the following:</span></span>
  
- [<span data-ttu-id="d0688-162">Planejar para o Gerenciador de estatísticas de Skype Business Server</span><span class="sxs-lookup"><span data-stu-id="d0688-162">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="d0688-163">Implantar o Gerenciador de estatísticas para Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="d0688-163">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)
    
- [<span data-ttu-id="d0688-164">Solucionar problemas de gerente de estatísticas para Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="d0688-164">Troubleshoot Statistics Manager for Skype for Business Server</span></span>](troubleshoot.md)
