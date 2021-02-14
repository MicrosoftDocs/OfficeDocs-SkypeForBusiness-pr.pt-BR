---
title: Implantar Gerenciador de Estatísticas do Skype for Business Server
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
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: 'Resumo: Leia este tópico para saber como implantar o Gerenciador de Estatísticas do Skype for Business Server.'
ms.openlocfilehash: 79e07c29a5df4a5da239687708a9bb52e995d191
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814811"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="645e7-103">Implantar Gerenciador de Estatísticas do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="645e7-103">Deploy Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="645e7-104">**Resumo:** Leia este tópico para saber como implantar o Gerenciador de Estatísticas do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="645e7-104">**Summary:** Read this topic to learn how to deploy Statistics Manager for Skype for Business Server.</span></span>
  
 <span data-ttu-id="645e7-105">O Gerenciador de Estatísticas do Skype for Business Server é uma poderosa ferramenta que permite exibir dados de desempenho e de saúde do Skype for Business Server em tempo real.</span><span class="sxs-lookup"><span data-stu-id="645e7-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="645e7-106">Você pode sondar dados de desempenho em centenas de servidores a cada poucos segundos e ver os resultados instantaneamente no site do Gerenciador de Estatísticas.</span><span class="sxs-lookup"><span data-stu-id="645e7-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>
  
<span data-ttu-id="645e7-107">Antes de tentar instalar o Gerenciador de Estatísticas, certifique-se de estar familiarizado com os requisitos de software, rede e hardware.</span><span class="sxs-lookup"><span data-stu-id="645e7-107">Before you attempt to install Statistics Manager, be sure you are familiar with the software, networking, and hardware requirements.</span></span> <span data-ttu-id="645e7-108">Para obter mais informações, [consulte Plan for Statistics Manager for Skype for Business Server](plan.md).</span><span class="sxs-lookup"><span data-stu-id="645e7-108">For more information, see [Plan for Statistics Manager for Skype for Business Server](plan.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="645e7-109">Se você estiver atualizando de uma versão anterior do Gerenciador de Estatísticas, consulte Atualizar o Gerenciador de Estatísticas [do Skype for Business Server.](upgrade.md)</span><span class="sxs-lookup"><span data-stu-id="645e7-109">If you are upgrading from a previous version of Statistics Manager, see [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="645e7-110">O site do Gerenciador de Estatísticas foi testado e funciona corretamente no Internet Explorer 11+, no Edge 20.10240+ e no Chrome 46+ (versão atual).</span><span class="sxs-lookup"><span data-stu-id="645e7-110">The Statistics Manager Website has been tested and works correctly on Internet Explorer 11+, Edge 20.10240+ , and Chrome 46+ (current evergreen version).</span></span> 
  
<span data-ttu-id="645e7-111">Você pode encontrar o Gerenciador de Estatísticas para download em [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload) .</span><span class="sxs-lookup"><span data-stu-id="645e7-111">You can find the Statistics Manager downloadable at [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload).</span></span> 
  
<span data-ttu-id="645e7-112">Este tópico contém as seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="645e7-112">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="645e7-113">Implantar o Gerenciador de Estatísticas</span><span class="sxs-lookup"><span data-stu-id="645e7-113">Deploy Statistics Manager</span></span>](deploy.md#BKMK_Deploy)
    
- [<span data-ttu-id="645e7-114">Solucionar problemas de sua implantação</span><span class="sxs-lookup"><span data-stu-id="645e7-114">Troubleshoot your deployment</span></span>](deploy.md#BKMK_Troubleshoot)
    
- [<span data-ttu-id="645e7-115">Criar um certificado auto-assinado</span><span class="sxs-lookup"><span data-stu-id="645e7-115">Create a self-signed certificate</span></span>](deploy.md#BKMK_SelfCert)
    
## <a name="deploy-statistics-manager"></a><span data-ttu-id="645e7-116">Implantar o Gerenciador de Estatísticas</span><span class="sxs-lookup"><span data-stu-id="645e7-116">Deploy Statistics Manager</span></span>
<span data-ttu-id="645e7-117"><a name="BKMK_Deploy"> </a></span><span class="sxs-lookup"><span data-stu-id="645e7-117"><a name="BKMK_Deploy"> </a></span></span>

<span data-ttu-id="645e7-118">Para implantar o Gerenciador de Estatísticas, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="645e7-118">To deploy Statistics Manager, follow these steps:</span></span>
  
1. <span data-ttu-id="645e7-119">Prepare o computador host do Ouvinte instalando o sistema de cache na memória redis e garantindo que você instalou os certificados apropriados.</span><span class="sxs-lookup"><span data-stu-id="645e7-119">Prepare the Listener host machine by installing the Redis in-memory caching system, and by ensuring that you have installed the appropriate certificates.</span></span>
    
2. <span data-ttu-id="645e7-120">Instale o serviço ouvinte no computador host.</span><span class="sxs-lookup"><span data-stu-id="645e7-120">Install the Listener service on the host machine.</span></span> 
    
3. <span data-ttu-id="645e7-121">Instale o site no computador host.</span><span class="sxs-lookup"><span data-stu-id="645e7-121">Install the Website on the host machine.</span></span>
    
4. <span data-ttu-id="645e7-122">Instale um Agente em cada máquina do Skype for Business Server que você deseja monitorar.</span><span class="sxs-lookup"><span data-stu-id="645e7-122">Install an Agent on each Skype for Business Server machine you wish to monitor.</span></span>
    
5. <span data-ttu-id="645e7-123">Importe a topologia para os servidores que você está monitorando.</span><span class="sxs-lookup"><span data-stu-id="645e7-123">Import the topology for the servers you are monitoring.</span></span>
    
> [!NOTE]
> <span data-ttu-id="645e7-124">O Redis, o serviço ouvinte e o site devem estar todos instalados no mesmo computador host.</span><span class="sxs-lookup"><span data-stu-id="645e7-124">Redis, the Listener service, and the Website must all be installed on the same host machine.</span></span> <span data-ttu-id="645e7-125">Certifique-se de que o computador host não tenha o Skype for Business Server instalado.</span><span class="sxs-lookup"><span data-stu-id="645e7-125">Be sure the host machine does not have Skype for Business Server installed.</span></span> 
  
### <a name="prepare-the-listener-host-machine"></a><span data-ttu-id="645e7-126">Preparar o computador host do Ouvinte</span><span class="sxs-lookup"><span data-stu-id="645e7-126">Prepare the Listener host machine</span></span>

<span data-ttu-id="645e7-127">Para preparar o computador host, você precisará instalar o sistema de cache na memória redis e garantir que um certificado válido está no computador.</span><span class="sxs-lookup"><span data-stu-id="645e7-127">To prepare the host machine, you will need to install the Redis in-memory caching system, and ensure that a valid certificate is on the machine.</span></span> <span data-ttu-id="645e7-128">A Microsoft recomenda que você instale a versão estável mais recente do Redis 3.0.</span><span class="sxs-lookup"><span data-stu-id="645e7-128">Microsoft recommends that you install the latest stable build of Redis 3.0.</span></span> <span data-ttu-id="645e7-129">A versão 2.0 do Gerenciador de Estatísticas foi testada com o Redis 3.2.100.</span><span class="sxs-lookup"><span data-stu-id="645e7-129">Statistics Manager version 2.0 was tested with Redis 3.2.100.</span></span> 
  
1. <span data-ttu-id="645e7-130">Baixe o Redis do seguinte site: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis) .</span><span class="sxs-lookup"><span data-stu-id="645e7-130">Download Redis from the following site: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis).</span></span> 
    
    <span data-ttu-id="645e7-131">Instaladores não assinados podem ser baixados de [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)</span><span class="sxs-lookup"><span data-stu-id="645e7-131">Unsigned installers can be downloaded from [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)</span></span>
    
    <span data-ttu-id="645e7-132">Se necessário, binários assinados estão disponíveis por meio de gerenciadores de pacote populares: [Nuget](https://www.nuget.org/packages/Redis-64/) e [Choclatey](https://chocolatey.org/packages/redis-64).</span><span class="sxs-lookup"><span data-stu-id="645e7-132">If required, signed binaries are available through popular package managers: [Nuget](https://www.nuget.org/packages/Redis-64/) and [Choclatey](https://chocolatey.org/packages/redis-64).</span></span>
    
   - <span data-ttu-id="645e7-133">Execute o msi fornecido e siga os prompts.</span><span class="sxs-lookup"><span data-stu-id="645e7-133">Run the provided msi and follow the prompts.</span></span>
    
   - <span data-ttu-id="645e7-134">Não marque a caixa para adicionar uma regra de firewall.</span><span class="sxs-lookup"><span data-stu-id="645e7-134">Do not check the box to add a firewall rule.</span></span>
    
2. <span data-ttu-id="645e7-135">O serviço ouvinte requer um certificado.</span><span class="sxs-lookup"><span data-stu-id="645e7-135">The Listener service requires a certificate.</span></span> <span data-ttu-id="645e7-136">A Microsoft recomenda que você tenha um certificado assinado por uma autoridade de certificação confiável.</span><span class="sxs-lookup"><span data-stu-id="645e7-136">Microsoft strongly recommends that you have a certificate signed by a trusted certificate authority.</span></span> 
    
    <span data-ttu-id="645e7-137">Se você quiser usar um certificado auto-assinado para fins de teste em um laboratório, por exemplo-- consulte Criar um [certificado auto-assinado.](deploy.md#BKMK_SelfCert)</span><span class="sxs-lookup"><span data-stu-id="645e7-137">If you want to use a self-signed certificate--for testing purposes in a lab, for example--see [Create a self-signed certificate](deploy.md#BKMK_SelfCert).</span></span>
    
    <span data-ttu-id="645e7-138">Observe que o Agente usa a verificação de impressão digital do certificado (em vez de verificação em cadeia).</span><span class="sxs-lookup"><span data-stu-id="645e7-138">Note that the Agent uses certificate thumbprint verification (instead of chain verification).</span></span> <span data-ttu-id="645e7-139">Ele não fará a validação completa do certificado porque é possível usar certificados auto-assinados.</span><span class="sxs-lookup"><span data-stu-id="645e7-139">It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>
    
### <a name="install-the-listener-service"></a><span data-ttu-id="645e7-140">Instalar o serviço ouvinte</span><span class="sxs-lookup"><span data-stu-id="645e7-140">Install the Listener service</span></span>

<span data-ttu-id="645e7-141">Instale o serviço ouvinte no computador host executando o StatsManPerfAgentListener.msi e especificando o seguinte:</span><span class="sxs-lookup"><span data-stu-id="645e7-141">Install the Listener service on the host machine by running the StatsManPerfAgentListener.msi and specifying the following:</span></span>
  
1. <span data-ttu-id="645e7-142">Revise o Contrato de Licença e, se você concordar, selecione **I accept the terms in the license agreement** e clique em **Next**.</span><span class="sxs-lookup"><span data-stu-id="645e7-142">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="645e7-143">Na próxima página, especifique as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="645e7-143">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="645e7-144">**Senha de Serviço:** Esta é a senha que os Agentes remotos usarão para se autenticar no serviço ouvinte.</span><span class="sxs-lookup"><span data-stu-id="645e7-144">**Service Password:** This is the password the remote Agents will use to authenticate to the Listener service.</span></span>
    
   - <span data-ttu-id="645e7-145">**Porta de Serviço:** Esse é o número da porta HTTPS que o Ouvinte usará para se comunicar com os Agentes.</span><span class="sxs-lookup"><span data-stu-id="645e7-145">**Service Port:** This is the HTTPS port number that the Listener will use to communicate with the Agents.</span></span> <span data-ttu-id="645e7-146">Durante a instalação, essa porta será permitida através do firewall local, uma ACL de URL será criada e um certificado SSL será vinculado a essa porta.</span><span class="sxs-lookup"><span data-stu-id="645e7-146">During installation, this port will be allowed through the local firewall, a URL ACL will be created, and an SSL cert will be bound to this port.</span></span> <span data-ttu-id="645e7-147">O padrão é 8443.</span><span class="sxs-lookup"><span data-stu-id="645e7-147">The default is 8443.</span></span>
    
   - <span data-ttu-id="645e7-148">**Impressão digital do certificado:** Esta é a impressão digital do certificado que o Ouvinte usará para criptografar o protocolo HTTPS.</span><span class="sxs-lookup"><span data-stu-id="645e7-148">**Certificate Thumbprint:** This is the certificate thumbprint the Listener will use to encrypt the HTTPS protocol.</span></span> <span data-ttu-id="645e7-149">O Serviço de Rede deve ter acesso de leitura à chave privada.</span><span class="sxs-lookup"><span data-stu-id="645e7-149">Network Service must have read access to the private key.</span></span>
    
     <span data-ttu-id="645e7-150">Clique no **botão Selecionar...** para escolher a impressão digital.</span><span class="sxs-lookup"><span data-stu-id="645e7-150">Click the **Select...** button to choose the thumbprint.</span></span>
    
     <span data-ttu-id="645e7-151">Você pode encontrar a impressão digital do certificado usando o Gerenciador de Certificados ou usando o seguinte comando do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="645e7-151">You can find the Certificate thumbprint by using Certificate Manager or by using the following PowerShell command:</span></span>
    
       ```PowerShell
       Get-ChildItem -path cert:\LocalMachine\My
       ```

   - <span data-ttu-id="645e7-152">**Install Dir:** Este é o diretório no qual os binários serão instalados.</span><span class="sxs-lookup"><span data-stu-id="645e7-152">**Install Dir:** This is the directory on which the binaries will be installed.</span></span> <span data-ttu-id="645e7-153">Você pode alterá-lo do padrão usando o **botão Procurar...**</span><span class="sxs-lookup"><span data-stu-id="645e7-153">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="645e7-154">**AppData Dir:** Esse é o diretório onde a pasta Logs e outros dados serão armazenados.</span><span class="sxs-lookup"><span data-stu-id="645e7-154">**AppData Dir:** This is the directory where the Logs folder and other data will be stored.</span></span> <span data-ttu-id="645e7-155">Você pode alterá-lo do padrão.</span><span class="sxs-lookup"><span data-stu-id="645e7-155">You may change it from the default.</span></span> <span data-ttu-id="645e7-156">Ele não será excluído na desinstalação.</span><span class="sxs-lookup"><span data-stu-id="645e7-156">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="645e7-157">Clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="645e7-157">Click **Install**.</span></span>
    
<span data-ttu-id="645e7-158">Para validar a instalação, execute as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="645e7-158">To validate the installation, perform the following steps:</span></span>
  
1. <span data-ttu-id="645e7-159">Abra um navegador e navegue até https://localhost: \<service-port\> /healthcheck/</span><span class="sxs-lookup"><span data-stu-id="645e7-159">Open a browser and navigate to https://localhost:\<service-port\>/healthcheck/</span></span>
    
    <span data-ttu-id="645e7-160">Por padrão, a porta de serviço é 8443 (a menos que você tenha especificado outra porta).</span><span class="sxs-lookup"><span data-stu-id="645e7-160">By default, the service port is 8443 (unless you specified another port).</span></span>
    
2. <span data-ttu-id="645e7-161">Para garantir que o Ouvinte tenha sido instalado corretamente, procure o seguinte:</span><span class="sxs-lookup"><span data-stu-id="645e7-161">To ensure the Listener has installed properly, look for the following:</span></span>
    
   - <span data-ttu-id="645e7-162">Se a página de verificação de saúde aparecer, a instalação do Ouvinte foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="645e7-162">If the healthcheck page shows up, the Listener installation was successful.</span></span>
    
   - <span data-ttu-id="645e7-163">Se KnownServerCount for 1 ou superior, a conexão com o Redis será estabelecida.</span><span class="sxs-lookup"><span data-stu-id="645e7-163">If the KnownServerCount is 1 or higher,  the connection to Redis is established.</span></span>
    
   - <span data-ttu-id="645e7-164">Depois de aguardar alguns minutos e após a instalação de pelo menos um Agente, verifique se o contador ValuesWritten está incrementando.</span><span class="sxs-lookup"><span data-stu-id="645e7-164">After waiting a few minutes, and after at least one Agent has been installed, check to see that the ValuesWritten counter is incrementing.</span></span>
    
### <a name="install-the-website"></a><span data-ttu-id="645e7-165">Instalar o site</span><span class="sxs-lookup"><span data-stu-id="645e7-165">Install the Website</span></span>

<span data-ttu-id="645e7-166">Instale o site no computador host executando o StatsManWebSite.msi (incluído no [Skype for Business Server, Real-Time Statistics Manager (64 bits)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)) e especificando o seguinte:</span><span class="sxs-lookup"><span data-stu-id="645e7-166">Install the Website on the host machine by running the StatsManWebSite.msi (included with [Skype for Business Server, Real-Time Statistics Manager (64-bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)) and specifying the following:</span></span>
  
1. <span data-ttu-id="645e7-167">Revise o Contrato de Licença e, se você concordar, selecione **I accept the terms in the license agreement** e clique em **Next**.</span><span class="sxs-lookup"><span data-stu-id="645e7-167">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="645e7-168">Na próxima página, especifique as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="645e7-168">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="645e7-169">**Porta de Serviço:** Esse é o número da porta que o site escutará.</span><span class="sxs-lookup"><span data-stu-id="645e7-169">**Service Port:** This is the port number the web site will listen on.</span></span> <span data-ttu-id="645e7-170">Você pode alterá-lo posteriormente usando a associação do gerenciador do IIS.</span><span class="sxs-lookup"><span data-stu-id="645e7-170">You can change it later by using IIS manager binding.</span></span> <span data-ttu-id="645e7-171">Durante a instalação, essa porta será permitida através do firewall local.</span><span class="sxs-lookup"><span data-stu-id="645e7-171">During installation, this port will be allowed through the local firewall.</span></span>
    
   - <span data-ttu-id="645e7-172">**Install Dir:** Este é o diretório onde os binários serão instalados.</span><span class="sxs-lookup"><span data-stu-id="645e7-172">**Install Dir:** This is the directory where the binaries will be installed.</span></span> <span data-ttu-id="645e7-173">Você pode alterá-lo do padrão usando o **botão Procurar...**</span><span class="sxs-lookup"><span data-stu-id="645e7-173">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="645e7-174">**AppData Dir:** Esse é o diretório onde a pasta Logs e outros dados serão armazenados.</span><span class="sxs-lookup"><span data-stu-id="645e7-174">**AppData Dir:** This is the directory where the Logs folder and other data will be stored.</span></span> <span data-ttu-id="645e7-175">Você pode alterá-lo do padrão.</span><span class="sxs-lookup"><span data-stu-id="645e7-175">You may change it from the default.</span></span> <span data-ttu-id="645e7-176">Ele não será excluído na desinstalação.</span><span class="sxs-lookup"><span data-stu-id="645e7-176">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="645e7-177">Clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="645e7-177">Click **Install**.</span></span>
    
<span data-ttu-id="645e7-178">Para exibir o site, abra um navegador e navegue até: http://localhost ,webport \> /.</span><span class="sxs-lookup"><span data-stu-id="645e7-178">To view the Website, open a browser, and navigate to: http://localhost,webport\>/.</span></span>
  
<span data-ttu-id="645e7-179">Para exibir apenas informações de saúde, abra um navegador e navegue até: http://localhost: \<webport\> /healthcheck/.</span><span class="sxs-lookup"><span data-stu-id="645e7-179">To view health information only, open a browser, and navigate to: http://localhost:\<webport\>/healthcheck/.</span></span>
  
<span data-ttu-id="645e7-180">Por padrão, o número da porta da Web é 8080.</span><span class="sxs-lookup"><span data-stu-id="645e7-180">By default, the web port number is 8080.</span></span> <span data-ttu-id="645e7-181">Você pode alterar a associação de porta do site usando o gerenciador do IIS.</span><span class="sxs-lookup"><span data-stu-id="645e7-181">You can change the port binding of the website by using IIS manager.</span></span>
  
<span data-ttu-id="645e7-182">O instalador da Web adiciona um grupo de segurança local, chamado StatsManWebSiteUsers.</span><span class="sxs-lookup"><span data-stu-id="645e7-182">The web installer adds a local security group, called StatsManWebSiteUsers.</span></span> <span data-ttu-id="645e7-183">Você pode adicionar contas a esse grupo de segurança para conceder acesso ao site.</span><span class="sxs-lookup"><span data-stu-id="645e7-183">You can add accounts to this security group to grant access to the Website.</span></span> 
  
### <a name="install-the-agents"></a><span data-ttu-id="645e7-184">Instalar os Agentes</span><span class="sxs-lookup"><span data-stu-id="645e7-184">Install the Agents</span></span>

<span data-ttu-id="645e7-185">Instale um Agente em cada Skype for Business Server que você deseja monitorar executando o StatsManPerfAgent.msi e especificando o seguinte:</span><span class="sxs-lookup"><span data-stu-id="645e7-185">Install an Agent on each Skype for Business Server that you wish to monitor by running the StatsManPerfAgent.msi and specifying the following:</span></span>
  
1. <span data-ttu-id="645e7-186">Revise o Contrato de Licença e, se você concordar, selecione **I accept the terms in the license agreement** e clique em **Next**.</span><span class="sxs-lookup"><span data-stu-id="645e7-186">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="645e7-187">Na próxima página, especifique as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="645e7-187">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="645e7-188">**Senha de Serviço:** Esta é a senha que o agente remoto usará para se autenticar no serviço ouvinte.</span><span class="sxs-lookup"><span data-stu-id="645e7-188">**Service Password:** This is the password the remote agent will use to authenticate to the Listener service.</span></span>
    
   - <span data-ttu-id="645e7-189">**URI do serviço:** Esse é o URI em que o Ouvinte reside.</span><span class="sxs-lookup"><span data-stu-id="645e7-189">**Service URI:** This is the URI where the Listener resides.</span></span> <span data-ttu-id="645e7-190">Ele deve usar o https://name:port formato.</span><span class="sxs-lookup"><span data-stu-id="645e7-190">It should use the https://name:port format.</span></span>
    
     <span data-ttu-id="645e7-191">Você pode usar um nome NETBIOS ou um FQDN.</span><span class="sxs-lookup"><span data-stu-id="645e7-191">You can use a NETBIOS name or a FQDN.</span></span> <span data-ttu-id="645e7-192">Você pode usar o nome que  também  é especificado como Assunto ou Nomes Alternativos de Assunto do certificado no serviço ouvinte, mas isso não é um requisito.</span><span class="sxs-lookup"><span data-stu-id="645e7-192">You can use the name that is also specified as the **Subject** or **Subject Alternative Names** of the certificate on the Listener service, but this is not a requirement.</span></span>
    
   - <span data-ttu-id="645e7-193">**Impressão digital do serviço:** Esta é a impressão digital do certificado SSL que o Ouvinte está usando.</span><span class="sxs-lookup"><span data-stu-id="645e7-193">**Service Thumbprint:** This is the thumbprint of the SSL certificate the Listener is using.</span></span> <span data-ttu-id="645e7-194">O Agente usará essa impressão digital para autenticar o Ouvinte.</span><span class="sxs-lookup"><span data-stu-id="645e7-194">The Agent will use this thumbprint to authenticate to the Listener.</span></span> <span data-ttu-id="645e7-195">(Ele não fará a validação completa do certificado porque é possível usar certificados auto-assinados.)</span><span class="sxs-lookup"><span data-stu-id="645e7-195">(It will not do full certificate validation because it is possible to use self-signed certificates.)</span></span>
    
   - <span data-ttu-id="645e7-196">**Install Dir:** Este é o diretório no qual os binários serão instalados.</span><span class="sxs-lookup"><span data-stu-id="645e7-196">**Install Dir:** This is the directory on which the binaries will be installed.</span></span> <span data-ttu-id="645e7-197">Você pode alterá-lo do padrão usando o **botão Procurar...**</span><span class="sxs-lookup"><span data-stu-id="645e7-197">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="645e7-198">**AppData Dir:** Esse é o diretório onde a pasta Logs e o arquivo password.txt criptografado serão armazenados.</span><span class="sxs-lookup"><span data-stu-id="645e7-198">**AppData Dir:** This is the directory where the Logs folder and the encrypted password.txt file will be stored.</span></span> <span data-ttu-id="645e7-199">Você pode alterá-la do padrão.</span><span class="sxs-lookup"><span data-stu-id="645e7-199">You may thanks change it from the default.</span></span> <span data-ttu-id="645e7-200">Ele não será excluído na desinstalação.</span><span class="sxs-lookup"><span data-stu-id="645e7-200">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="645e7-201">Clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="645e7-201">Click **Install**.</span></span>
    
<span data-ttu-id="645e7-202">Se você estiver instalando um Agente em vários máquinas, provavelmente vai querer fazer isso no modo autônomo.</span><span class="sxs-lookup"><span data-stu-id="645e7-202">If you are installing an Agent on numerous machines, you will probably want to do this in unattended mode.</span></span> <span data-ttu-id="645e7-203">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="645e7-203">For example:</span></span> 
  
```console
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_  STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a><span data-ttu-id="645e7-204">Importar a topologia</span><span class="sxs-lookup"><span data-stu-id="645e7-204">Import the topology</span></span>
<span data-ttu-id="645e7-205"><a name="BKMK_ImportTopology"> </a></span><span class="sxs-lookup"><span data-stu-id="645e7-205"><a name="BKMK_ImportTopology"> </a></span></span>

<span data-ttu-id="645e7-206">Depois que o Gerenciador de Estatísticas estiver instalado e em execução, você precisará importar a topologia do Skype for Business Server para que o Gerenciador de Estatísticas conheça o Site, o Pool e a Função de cada servidor.</span><span class="sxs-lookup"><span data-stu-id="645e7-206">After Statistics Manager is installed and running, you need to import the Skype for Business Server topology so that Statistics Manager knows the Site, Pool, and Role of each server.</span></span> <span data-ttu-id="645e7-207">Para importar sua topologia do Skype for Business Server, você usará o cmdlet [Get-CsPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) para recuperar informações sobre cada pool em uso na organização e, em seguida, importar essas informações para o Gerenciador de Estatísticas.</span><span class="sxs-lookup"><span data-stu-id="645e7-207">To import your Skype for Business Server topology, you will use the [Get-CsPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) cmdlet to retrieve information about each pool in use in your organization, then import this information into Statistics Manager.</span></span>
  
<span data-ttu-id="645e7-208">Para importar a topologia do Skype for Business Server, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="645e7-208">To import the Skype for Business Server topology, follow these steps:</span></span>
  
1. <span data-ttu-id="645e7-209">Em um host que tem os cmdlets do PowerShell do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="645e7-209">On a host that has the Skype for Business Server PowerShell cmdlets:</span></span>
    
    <span data-ttu-id="645e7-210">a.</span><span class="sxs-lookup"><span data-stu-id="645e7-210">a.</span></span> <span data-ttu-id="645e7-211">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="645e7-211">Run the following command:</span></span> 
    
   ```PowerShell
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```
    <span data-ttu-id="645e7-212">b.</span><span class="sxs-lookup"><span data-stu-id="645e7-212">b.</span></span> <span data-ttu-id="645e7-213">Copie o arquivo "mypoolinfo.xml" para o servidor que executa o Ouvinte.</span><span class="sxs-lookup"><span data-stu-id="645e7-213">Copy the "mypoolinfo.xml" file to the server that runs the Listener.</span></span>
    
2. <span data-ttu-id="645e7-214">No host que executa o Ouvinte:</span><span class="sxs-lookup"><span data-stu-id="645e7-214">On the host that runs the Listener:</span></span>
    
   <span data-ttu-id="645e7-215">a.</span><span class="sxs-lookup"><span data-stu-id="645e7-215">a.</span></span> <span data-ttu-id="645e7-216">Execute o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="645e7-216">Run PowerShell.</span></span>
    
   <span data-ttu-id="645e7-217">b.</span><span class="sxs-lookup"><span data-stu-id="645e7-217">b.</span></span> <span data-ttu-id="645e7-218">Navegue até o diretório no qual o Ouvinte está instalado.</span><span class="sxs-lookup"><span data-stu-id="645e7-218">Navigate to the directory on which the Listener is installed.</span></span> <span data-ttu-id="645e7-219">O padrão é:</span><span class="sxs-lookup"><span data-stu-id="645e7-219">The default is:</span></span> 
    
   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

3. <span data-ttu-id="645e7-220">Para confirmar quais servidores estão sendo adicionados e atualizados, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="645e7-220">To confirm which servers are being added and updated, run the following command:</span></span>
    
   ```console
    .\Update-StatsManServerInfo.ps1 -CsPoolFile  <path to mypoolinfo.xml>
   ```

<span data-ttu-id="645e7-221">O comando a seguir permite que você veja todas as opções:</span><span class="sxs-lookup"><span data-stu-id="645e7-221">The following command enables you to view all options:</span></span>
  
```powershell
Get-Help .\Update-StatsManServerInfo.ps1 -Detailed 
```

<span data-ttu-id="645e7-222">Para ver suas informações de servidor importadas no momento, execute o seguinte script:</span><span class="sxs-lookup"><span data-stu-id="645e7-222">To see your currently imported server information, run the following script:</span></span> 
  
```powershell
.\Get-StatsManServerInfo.ps1
```

<span data-ttu-id="645e7-223">Se você quiser monitorar servidores que não estão em sua topologia do Skype for Business Server , um Exchange Server, por exemplo-- você pode fazer uma importação de servidor único no host que executa o Ouvinte.</span><span class="sxs-lookup"><span data-stu-id="645e7-223">If you would like to monitor servers that are not in your Skype for Business Server topology--an Exchange Server, for example--you can do a single-server import on the host that runs the Listener.</span></span> <span data-ttu-id="645e7-224">Para fazer uma importação de um único servidor, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="645e7-224">To do a single-server import, follow these steps:</span></span>
  
1. <span data-ttu-id="645e7-225">Navegue até o diretório no qual o Ouvinte está instalado.</span><span class="sxs-lookup"><span data-stu-id="645e7-225">Navigate to the directory on which the Listener is installed.</span></span> <span data-ttu-id="645e7-226">O padrão é:</span><span class="sxs-lookup"><span data-stu-id="645e7-226">The default is:</span></span> 
    
   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

2. <span data-ttu-id="645e7-227">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="645e7-227">Run the following command:</span></span>
    
   ```powershell
    .\Update-StatsManServerInfo.ps1 -HostName <hostname> -SiteName <name of site> -PoolName <poolName> -Roles <role1>[,<role2>,<roleN>]
   ```

## <a name="troubleshoot-your-deployment"></a><span data-ttu-id="645e7-228">Solucionar problemas de sua implantação</span><span class="sxs-lookup"><span data-stu-id="645e7-228">Troubleshoot your deployment</span></span>
<span data-ttu-id="645e7-229"><a name="BKMK_Troubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="645e7-229"><a name="BKMK_Troubleshoot"> </a></span></span>

<span data-ttu-id="645e7-230">Se um Agente falhar ao iniciar, verifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="645e7-230">If an Agent fails to start, check for the following:</span></span> 
  
- <span data-ttu-id="645e7-231">O agente está registrado no Gerenciador de Estatísticas?</span><span class="sxs-lookup"><span data-stu-id="645e7-231">Is the agent registered in Statistics Manager?</span></span>
    
    1. <span data-ttu-id="645e7-232">Certifique-se de seguir as instruções para importar a topologia.</span><span class="sxs-lookup"><span data-stu-id="645e7-232">Make sure you followed the instructions for importing the topology.</span></span> <span data-ttu-id="645e7-233">Consulte [Importar a topologia.](deploy.md#BKMK_ImportTopology)</span><span class="sxs-lookup"><span data-stu-id="645e7-233">See [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
        
    2. <span data-ttu-id="645e7-234">Se o Agente estiver em um servidor que não está listado na topologia (por exemplo, os nós em um cluster SQL AlwaysOn), você precisará adicionar o Agente manualmente seguindo as instruções em Importar a [topologia.](deploy.md#BKMK_ImportTopology)</span><span class="sxs-lookup"><span data-stu-id="645e7-234">If the Agent is on a server that is not listed in the topology (for example, the nodes in a SQL AlwaysOn cluster), you will need to add the Agent manually by following the instructions in [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
- <span data-ttu-id="645e7-235">O Agente pode contatar o Ouvinte?</span><span class="sxs-lookup"><span data-stu-id="645e7-235">Can the Agent contact the Listener?</span></span>
    
    1. <span data-ttu-id="645e7-236">Certifique-se de que o serviço ouvinte está em execução.</span><span class="sxs-lookup"><span data-stu-id="645e7-236">Make sure the Listener service is running.</span></span> 
        
        <span data-ttu-id="645e7-237">Se não estiver em execução, certifique-se de que o Redis está em execução e tente reiniciar o Ouvinte.</span><span class="sxs-lookup"><span data-stu-id="645e7-237">If it is not running, make sure Redis is running, and then try to restart the Listener.</span></span>
        
    2. <span data-ttu-id="645e7-238">Certifique-se de que a porta está aberta para o serviço ouvinte e se o computador do Agente pode se comunicar com a porta.</span><span class="sxs-lookup"><span data-stu-id="645e7-238">Make sure the port is open to the Listener service, and that the Agent computer can communicate with the port.</span></span>
    
- <span data-ttu-id="645e7-239">Para garantir que o Gerenciador de Estatísticas está coletando dados, você pode verificar o arquivo CSV da seguinte forma.</span><span class="sxs-lookup"><span data-stu-id="645e7-239">To ensure that Statistics Manager is collecting data, you can check the CSV file as follows.</span></span> 
    
    <span data-ttu-id="645e7-240">O comando a seguir recupera os nomes de armazenamento de contador:</span><span class="sxs-lookup"><span data-stu-id="645e7-240">The following command retrieves the counter storage names:</span></span> 
    
  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    <span data-ttu-id="645e7-241">O próximo comando recupera os valores dos contadores especificados:</span><span class="sxs-lookup"><span data-stu-id="645e7-241">The next command retrieves the values for the specified counters:</span></span> 
    
  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

<span data-ttu-id="645e7-242">Para obter informações sobre todos os eventos que você pode ver no log de eventos do aplicativo, consulte [Troubleshoot Statistics Manager for Skype for Business Server](troubleshoot.md).</span><span class="sxs-lookup"><span data-stu-id="645e7-242">For information about all the events you might see in the application event log, see [Troubleshoot Statistics Manager for Skype for Business Server](troubleshoot.md).</span></span>
  
## <a name="create-a-self-signed-certificate"></a><span data-ttu-id="645e7-243">Criar um certificado auto-assinado</span><span class="sxs-lookup"><span data-stu-id="645e7-243">Create a self-signed certificate</span></span>
<span data-ttu-id="645e7-244"><a name="BKMK_SelfCert"> </a></span><span class="sxs-lookup"><span data-stu-id="645e7-244"><a name="BKMK_SelfCert"> </a></span></span>

<span data-ttu-id="645e7-245">A Microsoft recomenda que você use um certificado assinado por uma autoridade de certificação confiável.</span><span class="sxs-lookup"><span data-stu-id="645e7-245">Microsoft strongly recommends that you use a certificate signed by a trusted certificate authority.</span></span> <span data-ttu-id="645e7-246">No entanto, se você quiser usar um certificado auto-assinado para fins de teste, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="645e7-246">However, if you want to use a self-signed certificate for testing purposes, do the following:</span></span> 
  
1. <span data-ttu-id="645e7-247">Em um console do PowerShell enquanto estiver conectado como Administrador, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="645e7-247">From a PowerShell console while logged on as Administrator, type the following:</span></span>
    
   ```powershell
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. <span data-ttu-id="645e7-248">Tipo  `certlm.msc` .</span><span class="sxs-lookup"><span data-stu-id="645e7-248">Type  `certlm.msc`.</span></span> <span data-ttu-id="645e7-249">Isso abrirá o Gerenciador de Certificados para o computador local.</span><span class="sxs-lookup"><span data-stu-id="645e7-249">This will open the Certificate Manager for the local machine.</span></span>
    
3. <span data-ttu-id="645e7-250">Navegue **até Pessoal** e abra **Certificados.**</span><span class="sxs-lookup"><span data-stu-id="645e7-250">Navigate to **Personal**, and then open **Certificates**.</span></span>
    
4. <span data-ttu-id="645e7-251">Clique com o botão direito do mouse em **StatsManListener - \> Todas as Tarefas - Gerenciar Chaves \> Privadas...**</span><span class="sxs-lookup"><span data-stu-id="645e7-251">Right click on **StatsManListener-\>All Tasks-\>Manage Private Keys…**</span></span>
    
5. <span data-ttu-id="645e7-252">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="645e7-252">Click **Add**.</span></span>
    
6. <span data-ttu-id="645e7-253">Na caixa **Digite os nomes de objeto a ser selecionado,** digite o seguinte: Serviço de Rede</span><span class="sxs-lookup"><span data-stu-id="645e7-253">In the **Enter the object names to select** box, type the following: Network Service</span></span>
    
7. <span data-ttu-id="645e7-254">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="645e7-254">Click **OK**.</span></span>
    
8. <span data-ttu-id="645e7-255">Em **Controle Total,** des marque a **caixa de** seleção Permitir.</span><span class="sxs-lookup"><span data-stu-id="645e7-255">Under **Full Control**, un-check the **Allow** check box.</span></span> <span data-ttu-id="645e7-256">(Somente o acesso de leitura é necessário.)</span><span class="sxs-lookup"><span data-stu-id="645e7-256">(Only Read access is necessary.)</span></span>
    
9. <span data-ttu-id="645e7-257">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="645e7-257">Click **OK**.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="645e7-258">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="645e7-258">For more information</span></span>
<span data-ttu-id="645e7-259"><a name="BKMK_SelfCert"> </a></span><span class="sxs-lookup"><span data-stu-id="645e7-259"><a name="BKMK_SelfCert"> </a></span></span>

<span data-ttu-id="645e7-260">Para obter mais informações, confira o seguinte:</span><span class="sxs-lookup"><span data-stu-id="645e7-260">For more information, see the following:</span></span>
  
- [<span data-ttu-id="645e7-261">Planejar o Gerenciador de estatísticas do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="645e7-261">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="645e7-262">Atualizar o Gerenciador de estatísticas do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="645e7-262">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)
    
- <span data-ttu-id="645e7-263">[Solução de problemas do Gerenciador de Estatísticas do Skype for Business Server](troubleshoot.md) ß</span><span class="sxs-lookup"><span data-stu-id="645e7-263">[Troubleshoot Statistics Manager for Skype for Business Server](troubleshoot.md) ß</span></span>
