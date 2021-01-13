---
title: Atualizar o Gerenciador de Estatísticas do Skype for Business Server
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
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: 'Resumo: Leia este tópico para saber como atualizar o Gerenciador de Estatísticas do Skype for Business Server.'
ms.openlocfilehash: 6f2f0b885faad7bd650b3ff90650b64af98e9eee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821761"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="08f58-103">Atualizar o Gerenciador de Estatísticas do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="08f58-103">Upgrade Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="08f58-104">**Resumo:** Leia este tópico para saber como atualizar o Gerenciador de Estatísticas do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="08f58-104">**Summary:** Read this topic to learn how to upgrade Statistics Manager for Skype for Business Server.</span></span>
  
<span data-ttu-id="08f58-105">Este tópico descreve como atualizar uma instalação existente do Gerenciador de Estatísticas do Skype for Business Server— uma ferramenta poderosa que permite exibir dados de desempenho e de saúde do Skype for Business Server em tempo real.</span><span class="sxs-lookup"><span data-stu-id="08f58-105">This topic describes how to upgrade an existing installation of Statistics Manager for Skype for Business Server—a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="08f58-106">Você pode sondar dados de desempenho em centenas de servidores a cada poucos segundos e ver os resultados instantaneamente no site do Gerenciador de Estatísticas.</span><span class="sxs-lookup"><span data-stu-id="08f58-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span> 
  
<span data-ttu-id="08f58-107">Para obter mais informações sobre o Gerenciador de Estatísticas e os novos recursos na versão 2.0, consulte Plano para o Gerenciador de Estatísticas do [Skype for Business Server](plan.md) e Implantar o Gerenciador de Estatísticas do Skype for Business [Server.](deploy.md)</span><span class="sxs-lookup"><span data-stu-id="08f58-107">For more information about Statistics Manager and the new features in Release 2.0, see [Plan for Statistics Manager for Skype for Business Server](plan.md) and [Deploy Statistics Manager for Skype for Business Server](deploy.md).</span></span>
  
<span data-ttu-id="08f58-108">Há dois métodos para atualizar:</span><span class="sxs-lookup"><span data-stu-id="08f58-108">There are two methods for upgrading:</span></span>
  
- <span data-ttu-id="08f58-109">**Atualização automatizada.**</span><span class="sxs-lookup"><span data-stu-id="08f58-109">**Automated upgrade.**</span></span> <span data-ttu-id="08f58-110">Esse método usa um script automatizado.</span><span class="sxs-lookup"><span data-stu-id="08f58-110">This method uses an automated script.</span></span> <span data-ttu-id="08f58-111">É o método mais fácil e deve ser aplicável a todos os cenários de atualização.</span><span class="sxs-lookup"><span data-stu-id="08f58-111">It is the easiest method and should be applicable to all upgrade scenarios.</span></span>
    
- <span data-ttu-id="08f58-112">**Atualização manual.**</span><span class="sxs-lookup"><span data-stu-id="08f58-112">**Manual upgrade.**</span></span> <span data-ttu-id="08f58-113">Esse método é fornecido como um plano de backup no caso incomum de falha na atualização automatizada.</span><span class="sxs-lookup"><span data-stu-id="08f58-113">This method is provided as a backup plan in the unusual case that the automated upgrade fails.</span></span>
    
## <a name="prerequisites"></a><span data-ttu-id="08f58-114">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="08f58-114">Prerequisites</span></span>

<span data-ttu-id="08f58-115">Antes de atualizar, certifique-se de ter as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="08f58-115">Before you upgrade, be sure you have the following information:</span></span>
  
- <span data-ttu-id="08f58-116">Impressão digital do certificado do Ouvinte Ativo</span><span class="sxs-lookup"><span data-stu-id="08f58-116">Active Listener Certificate Thumbprint</span></span>
    
- <span data-ttu-id="08f58-117">Senha do Serviço de Escuta (inserida na instalação do ouvinte e de cada agente)</span><span class="sxs-lookup"><span data-stu-id="08f58-117">Listener Service Password (entered on install of the listener and every agent)</span></span>
    
- <span data-ttu-id="08f58-118">Configuração de Certificado SSL para o site</span><span class="sxs-lookup"><span data-stu-id="08f58-118">SSL Certificate configuration for the website</span></span>
    
## <a name="automated-upgrade"></a><span data-ttu-id="08f58-119">Atualização automatizada</span><span class="sxs-lookup"><span data-stu-id="08f58-119">Automated upgrade</span></span>

<span data-ttu-id="08f58-120">O script coletará as informações atuais do certificado e a senha do ouvinte, desinstalará a versão antiga do produto e instalará a nova versão do produto.</span><span class="sxs-lookup"><span data-stu-id="08f58-120">The script will gather your current certificate information and listener password, uninstall the old version of the product, and then install the new version of the product.</span></span> <span data-ttu-id="08f58-121">A instância redis instalada no servidor não será tocada, portanto, todos os dados armazenados no cache serão mantidos durante o processo de atualização.</span><span class="sxs-lookup"><span data-stu-id="08f58-121">The Redis instance installed on the server will not be touched, so any data stored in the cache will be retained through the upgrade process.</span></span>
  
1. <span data-ttu-id="08f58-122">Coloque os arquivos MSI para a nova versão do agente, ouvinte e site juntamente com o script Update-StatsMan.ps1 em uma única pasta no computador ouvinte.</span><span class="sxs-lookup"><span data-stu-id="08f58-122">Place the MSI files for the new version of the agent, listener and website along with the Update-StatsMan.ps1 script into a single folder on the Listener computer.</span></span>
    
2. <span data-ttu-id="08f58-123">Abra uma janela administrativa do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="08f58-123">Open an administrative PowerShell window.</span></span> <span data-ttu-id="08f58-124">Atualize o componente Ouvinte:</span><span class="sxs-lookup"><span data-stu-id="08f58-124">Upgrade the Listener component:</span></span>
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> <span data-ttu-id="08f58-125">A senha de serviço do Gerenciador de Estatísticas será exibida em texto não limpo na linha de comando à medida que ela for passada para o instalador.</span><span class="sxs-lookup"><span data-stu-id="08f58-125">The Statistics Manager service password will be displayed in clear text on the command line as it is passed to the installer.</span></span> <span data-ttu-id="08f58-126">Certifique-se de proteger seu monitor conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="08f58-126">Be sure to shield your monitor as needed.</span></span> 
  
1. <span data-ttu-id="08f58-127">Ao executar o script, você deverá ser solicitado a desinstalar a versão antiga do produto.</span><span class="sxs-lookup"><span data-stu-id="08f58-127">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="08f58-128">Responda Sim.</span><span class="sxs-lookup"><span data-stu-id="08f58-128">Answer Yes.</span></span>
    
2. <span data-ttu-id="08f58-129">Se o serviço ouvinte estiver em execução, você será solicitado a fechar o aplicativo antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="08f58-129">If the Listener service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="08f58-130">Permitir que o aplicativo seja fechado (o serviço ouvinte do Gerenciador de Estatísticas será interrompido).</span><span class="sxs-lookup"><span data-stu-id="08f58-130">Allow the application to close (the Statistics Manager Listener service will be stopped).</span></span>
    
3. <span data-ttu-id="08f58-131">Continue o processo de instalação.</span><span class="sxs-lookup"><span data-stu-id="08f58-131">Continue the install process.</span></span> <span data-ttu-id="08f58-132">Você deve observar que a senha de serviço e a impressão digital do certificado estão pré-preenchidas.</span><span class="sxs-lookup"><span data-stu-id="08f58-132">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="08f58-133">Caso não, adicione os valores salvos antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="08f58-133">If not, add the values you saved before continuing.</span></span>
    
4. <span data-ttu-id="08f58-134">Abra uma janela administrativa do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="08f58-134">Open an administrative PowerShell window.</span></span> <span data-ttu-id="08f58-135">Atualize o componente site:</span><span class="sxs-lookup"><span data-stu-id="08f58-135">Upgrade the Website component:</span></span>
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Website
   ```

5. <span data-ttu-id="08f58-136">Ao executar o script, você deverá ser solicitado a desinstalar a versão antiga do produto.</span><span class="sxs-lookup"><span data-stu-id="08f58-136">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="08f58-137">Responda Sim.</span><span class="sxs-lookup"><span data-stu-id="08f58-137">Answer Yes.</span></span>
    
6. <span data-ttu-id="08f58-138">Se o serviço do Agente estiver em execução, você será solicitado a fechar o aplicativo antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="08f58-138">If the Agent service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="08f58-139">Permitir que o aplicativo seja fechado (o serviço agente StatsMan será interrompido).</span><span class="sxs-lookup"><span data-stu-id="08f58-139">Allow the application to close (the StatsMan Agent service will be stopped).</span></span>
    
7. <span data-ttu-id="08f58-140">Continue o processo de instalação.</span><span class="sxs-lookup"><span data-stu-id="08f58-140">Continue the install process.</span></span> <span data-ttu-id="08f58-141">Você deve observar que a senha de serviço e a impressão digital do certificado estão pré-preenchidas.</span><span class="sxs-lookup"><span data-stu-id="08f58-141">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="08f58-142">Caso não, adicione os valores salvos antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="08f58-142">If not, add the values you saved before continuing.</span></span>
    
8. <span data-ttu-id="08f58-143">Abra uma janela administrativa do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="08f58-143">Open an administrative PowerShell window.</span></span> <span data-ttu-id="08f58-144">Atualize o componente do Agente:</span><span class="sxs-lookup"><span data-stu-id="08f58-144">Upgrade the Agent component:</span></span>
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Agent
   ```

9. <span data-ttu-id="08f58-145">Ao executar o script, você deverá ser solicitado a desinstalar a versão antiga do produto.</span><span class="sxs-lookup"><span data-stu-id="08f58-145">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="08f58-146">Responda Sim.</span><span class="sxs-lookup"><span data-stu-id="08f58-146">Answer Yes.</span></span>
    
10. <span data-ttu-id="08f58-147">Continue o processo de instalação.</span><span class="sxs-lookup"><span data-stu-id="08f58-147">Continue the install process.</span></span> <span data-ttu-id="08f58-148">Você deve observar que a porta do site é pré-preenchida.</span><span class="sxs-lookup"><span data-stu-id="08f58-148">You should notice that the website port is pre-populated.</span></span> <span data-ttu-id="08f58-149">Caso não, adicione o valor salvo antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="08f58-149">If not, add the value you saved before continuing.</span></span>
    
11. <span data-ttu-id="08f58-150">Verifique se o site está funcionando conforme o esperado usando o navegador.</span><span class="sxs-lookup"><span data-stu-id="08f58-150">Verify the website is working as expected using the browser.</span></span>
    
> [!NOTE]
> <span data-ttu-id="08f58-151">A atualização do Agente pode ser usada com a opção -NoPrompt.</span><span class="sxs-lookup"><span data-stu-id="08f58-151">The Agent upgrade can be used with the -NoPrompt switch.</span></span> <span data-ttu-id="08f58-152">Isso permitirá que o processo de desinstalação/instalação seja executado silenciosamente, permitindo que ferramentas como PSExec executem a atualização remotamente em um grande número de servidores.</span><span class="sxs-lookup"><span data-stu-id="08f58-152">This will allow the uninstall/install process to run silently, allowing tools such as PSExec to run the upgrade remotely on a large number of servers.</span></span> 
  
### <a name="manual-upgrade"></a><span data-ttu-id="08f58-153">Atualização manual</span><span class="sxs-lookup"><span data-stu-id="08f58-153">Manual upgrade</span></span>

<span data-ttu-id="08f58-154">Se, por algum motivo, a atualização automatizada falhar, você sempre poderá executar uma atualização manual da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="08f58-154">If for some reason, the automated upgrade fails, you can always perform a manual upgrade as follows:</span></span>
  
1. <span data-ttu-id="08f58-155">No computador ouvinte, desinstale o Ouvinte, o Site e o Agente (se ele foi instalado neste servidor) por meio do painel de controle Programas e Recursos.</span><span class="sxs-lookup"><span data-stu-id="08f58-155">On the Listener computer, uninstall the Listener, Website and the Agent (if it was installed on this server) via the Programs and Features control panel.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="08f58-156">Mantenha o Redis instalado para que os dados no cache sejam mantidos durante o processo de atualização.</span><span class="sxs-lookup"><span data-stu-id="08f58-156">Keep Redis installed so that the data in the cache will then be maintained through the upgrade process.</span></span>
  
2. <span data-ttu-id="08f58-157">Instale as novas versões dos componentes, incluindo os valores salvos acima quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="08f58-157">Install the new versions of the components, including the values you saved above when prompted for them.</span></span> <span data-ttu-id="08f58-158">Para obter mais informações sobre como instalar componentes, [consulte Implantar o Gerenciador de Estatísticas](deploy.md#BKMK_Deploy)</span><span class="sxs-lookup"><span data-stu-id="08f58-158">For more information about installing components, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy)</span></span>

    
## <a name="for-more-information"></a><span data-ttu-id="08f58-159">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="08f58-159">For more information</span></span>
<span data-ttu-id="08f58-160"><a name="BKMK_Fixed"> </a></span><span class="sxs-lookup"><span data-stu-id="08f58-160"><a name="BKMK_Fixed"> </a></span></span>

<span data-ttu-id="08f58-161">Para obter mais informações, confira o seguinte:</span><span class="sxs-lookup"><span data-stu-id="08f58-161">For more information, see the following:</span></span>
  
- [<span data-ttu-id="08f58-162">Planejar o Gerenciador de estatísticas do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="08f58-162">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="08f58-163">Implantar o Gerenciador de estatísticas do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="08f58-163">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)
    
- [<span data-ttu-id="08f58-164">Solução de problemas do Gerenciador de estatísticas do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="08f58-164">Troubleshoot Statistics Manager for Skype for Business Server</span></span>](troubleshoot.md)
