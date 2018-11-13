---
title: Implantar o Gerenciador de Estatísticas para o Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/9/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: 'Resumo: Leia este tópico para saber como implantar o Gerenciador de estatísticas para Skype para Business Server 2015.'
ms.openlocfilehash: 75a8af0794431a0f74233ad0c6a422b3827c7656
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295179"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server-2015"></a><span data-ttu-id="88689-103">Deploy Statistics Manager for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="88689-103">Deploy Statistics Manager for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="88689-104">**Resumo:** Leia este tópico para saber como implantar o Gerenciador de estatísticas para Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="88689-104">**Summary:** Read this topic to learn how to deploy Statistics Manager for Skype for Business Server 2015.</span></span>
  
 <span data-ttu-id="88689-105">Gerenciador de estatísticas para Skype para Business Server é uma ferramenta poderosa que permite que você visualize Skype para dados de integridade e desempenho do servidor de negócios em tempo real.</span><span class="sxs-lookup"><span data-stu-id="88689-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="88689-106">Você pode sondar dados de desempenho em centenas de servidores por cada alguns segundos e exiba os resultados instantaneamente no site do Gerenciador de estatísticas.</span><span class="sxs-lookup"><span data-stu-id="88689-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>
  
<span data-ttu-id="88689-107">Antes de tentar instalar o Gerenciador de estatísticas, certifique-se de que você está familiarizado com os requisitos de hardware, software e rede.</span><span class="sxs-lookup"><span data-stu-id="88689-107">Before you attempt to install Statistics Manager, be sure you are familiar with the software, networking, and hardware requirements.</span></span> <span data-ttu-id="88689-108">Para obter mais informações, consulte [Planejar para o Gerenciador de estatísticas de Skype para Business Server 2015](plan.md).</span><span class="sxs-lookup"><span data-stu-id="88689-108">For more information, see [Plan for Statistics Manager for Skype for Business Server 2015](plan.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="88689-109">Se você estiver atualizando de uma versão anterior do Gerenciador de estatísticas, consulte [Atualizar o Gerenciador de estatísticas para Skype para Business Server 2015](upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="88689-109">If you are upgrading from a previous version of Statistics Manager, see [Upgrade Statistics Manager for Skype for Business Server 2015](upgrade.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="88689-110">O site do Gerenciador de Estatísticas foi testado e funciona corretamente no Internet Explorer 11+, Edge 20.10240+ e Chrome 46+ (versão evergreen atual).</span><span class="sxs-lookup"><span data-stu-id="88689-110">The Statistics Manager Website has been tested and works correctly on Internet Explorer 11+, Edge 20.10240+ , and Chrome 46+ (current evergreen version).</span></span> 
  
<span data-ttu-id="88689-111">Você pode encontrar o Gerenciador de estatísticas disponível para download em [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload).</span><span class="sxs-lookup"><span data-stu-id="88689-111">You can find the Statistics Manager downloadable at [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload).</span></span> 
  
<span data-ttu-id="88689-112">Este tópico inclui as seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="88689-112">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="88689-113">Implantar o Gerenciador de Estatísticas</span><span class="sxs-lookup"><span data-stu-id="88689-113">Deploy Statistics Manager</span></span>](deploy.md#BKMK_Deploy)
    
- [<span data-ttu-id="88689-114">Solução de problemas de implantação</span><span class="sxs-lookup"><span data-stu-id="88689-114">Troubleshoot your deployment</span></span>](deploy.md#BKMK_Troubleshoot)
    
- [<span data-ttu-id="88689-115">Criar um certificado autoassinado</span><span class="sxs-lookup"><span data-stu-id="88689-115">Create a self-signed certificate</span></span>](deploy.md#BKMK_SelfCert)
    
## <a name="deploy-statistics-manager"></a><span data-ttu-id="88689-116">Implantar o Gerenciador de Estatísticas</span><span class="sxs-lookup"><span data-stu-id="88689-116">Deploy Statistics Manager</span></span>
<span data-ttu-id="88689-117"><a name="BKMK_Deploy"> </a></span><span class="sxs-lookup"><span data-stu-id="88689-117"></span></span>

<span data-ttu-id="88689-118">Para implantar o Gerenciador de estatísticas, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="88689-118">To deploy Statistics Manager, follow these steps:</span></span>
  
1. <span data-ttu-id="88689-119">Prepare o computador host Ouvinte instalando o sistema de cache na memória Redis e verificando se você instalou os certificados adequados.</span><span class="sxs-lookup"><span data-stu-id="88689-119">Prepare the Listener host machine by installing the Redis in-memory caching system, and by ensuring that you have installed the appropriate certificates.</span></span>
    
2. <span data-ttu-id="88689-120">Instale o serviço de escuta no computador host. </span><span class="sxs-lookup"><span data-stu-id="88689-120">Install the Listener service on the host machine.</span></span> 
    
3. <span data-ttu-id="88689-121">Instale o site no computador host.</span><span class="sxs-lookup"><span data-stu-id="88689-121">Install the Website on the host machine.</span></span>
    
4. <span data-ttu-id="88689-122">Instale um agente em cada Skype para máquina Business Server que devem ser monitoradas.</span><span class="sxs-lookup"><span data-stu-id="88689-122">Install an Agent on each Skype for Business Server machine you wish to monitor.</span></span>
    
5. <span data-ttu-id="88689-123">Importe a topologia para os servidores que estiver monitorando.</span><span class="sxs-lookup"><span data-stu-id="88689-123">Import the topology for the servers you are monitoring.</span></span>
    
> [!NOTE]
> <span data-ttu-id="88689-124">O Redis, o serviço de escuta e o site deverão estar todos instalados no mesmo computador host.</span><span class="sxs-lookup"><span data-stu-id="88689-124">Redis, the Listener service, and the Website must all be installed on the same host machine.</span></span> <span data-ttu-id="88689-125">Certifique-se de que a máquina host não tem Skype para Business Server instalado.</span><span class="sxs-lookup"><span data-stu-id="88689-125">Be sure the host machine does not have Skype for Business Server installed.</span></span> 
  
### <a name="prepare-the-listener-host-machine"></a><span data-ttu-id="88689-126">Preparar o computador host Ouvinte</span><span class="sxs-lookup"><span data-stu-id="88689-126">Prepare the Listener host machine</span></span>

<span data-ttu-id="88689-127">Para preparar a máquina host, você precisará instalar o sistema de cache de na memória relacionada e verifique se é um certificado válido na máquina.</span><span class="sxs-lookup"><span data-stu-id="88689-127">To prepare the host machine, you will need to install the Redis in-memory caching system, and ensure that a valid certificate is on the machine.</span></span> <span data-ttu-id="88689-128">A Microsoft recomenda que você instale a compilação estável mais recente do 3.0 relacionada.</span><span class="sxs-lookup"><span data-stu-id="88689-128">Microsoft recommends that you install the latest stable build of Redis 3.0.</span></span> <span data-ttu-id="88689-129">Gerenciador de estatísticas versão 1.1 foi testada com relacionada 3.0.501 e relacionada 2.8.2400.</span><span class="sxs-lookup"><span data-stu-id="88689-129">Statistics Manager version 1.1 was tested with Redis 3.0.501 and Redis 2.8.2400.</span></span> 
  
1. <span data-ttu-id="88689-130">Baixe o relacionada nos seguinte site: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis).</span><span class="sxs-lookup"><span data-stu-id="88689-130">Download Redis from the following site: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis).</span></span> 
    
    <span data-ttu-id="88689-131">Instaladores não assinados podem ser baixados do[https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)</span><span class="sxs-lookup"><span data-stu-id="88689-131">Unsigned installers can be downloaded from [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)</span></span>
    
    <span data-ttu-id="88689-132">Se necessário, binários assinados estão disponíveis por meio de gerenciadores de pacotes populares: [Nuget](https://www.nuget.org/packages/Redis-64/) e [Choclatey](https://chocolatey.org/packages/redis-64).</span><span class="sxs-lookup"><span data-stu-id="88689-132">If required, signed binaries are available through popular package managers: [Nuget](https://www.nuget.org/packages/Redis-64/) and [Choclatey](https://chocolatey.org/packages/redis-64).</span></span>
    
   - <span data-ttu-id="88689-133">Execute o msi fornecido e siga as instruções.</span><span class="sxs-lookup"><span data-stu-id="88689-133">Run the provided msi and follow the prompts.</span></span>
    
   - <span data-ttu-id="88689-134">Não marque a caixa para adicionar uma regra de firewall.</span><span class="sxs-lookup"><span data-stu-id="88689-134">Do not check the box to add a firewall rule.</span></span>
    
2. <span data-ttu-id="88689-135">O serviço de escuta requer um certificado.</span><span class="sxs-lookup"><span data-stu-id="88689-135">The Listener service requires a certificate.</span></span> <span data-ttu-id="88689-136">Microsoft recomenda que você tenha um certificado assinado por uma autoridade de certificação confiável.</span><span class="sxs-lookup"><span data-stu-id="88689-136">Microsoft strongly recommends that you have a certificate signed by a trusted certificate authority.</span></span> 
    
    <span data-ttu-id="88689-137">Se quiser usar um certificado autoassinado (para fins de teste em um laboratório, por exemplo), veja [Criar um certificado autoassinado](deploy.md#BKMK_SelfCert).</span><span class="sxs-lookup"><span data-stu-id="88689-137">If you want to use a self-signed certificate--for testing purposes in a lab, for example--see [Create a self-signed certificate](deploy.md#BKMK_SelfCert).</span></span>
    
    <span data-ttu-id="88689-p106">Observe que o Agente utiliza a verificação de impressão digital do certificado (em vez de verificação de cadeia). Ele não fará a validação completa do certificado, pois é possível usar certificados autoassinados.</span><span class="sxs-lookup"><span data-stu-id="88689-p106">Note that the Agent uses certificate thumbprint verification (instead of chain verification). It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>
    
### <a name="install-the-listener-service"></a><span data-ttu-id="88689-140">Instalar o serviço de escuta</span><span class="sxs-lookup"><span data-stu-id="88689-140">Install the Listener service</span></span>

<span data-ttu-id="88689-141">Instale o serviço de ouvinte na máquina host executando o StatsManPerfAgentListener.msi e especificando o seguinte:</span><span class="sxs-lookup"><span data-stu-id="88689-141">Install the Listener service on the host machine by running the StatsManPerfAgentListener.msi and specifying the following:</span></span>
  
1. <span data-ttu-id="88689-142">Leia o Contrato de Licença e, se estiver de acordo, selecione \*\*Aceito os termos do Contrato de Licença \*\* e clique em **Avançar**. </span><span class="sxs-lookup"><span data-stu-id="88689-142">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="88689-143">Na próxima página, especifique as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="88689-143">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="88689-144">**Senha do Serviço:** esta é a senha que os Agentes remotos usarão para se autenticarem no serviço de escuta.</span><span class="sxs-lookup"><span data-stu-id="88689-144">**Service Password:** This is the password the remote Agents will use to authenticate to the Listener service.</span></span>
    
   - <span data-ttu-id="88689-145">**Porta de serviço:** Esse é o número de porta HTTPS que o ouvinte usará para se comunicar com os agentes.</span><span class="sxs-lookup"><span data-stu-id="88689-145">**Service Port:** This is the HTTPS port number that the Listener will use to communicate with the Agents.</span></span> <span data-ttu-id="88689-146">Durante a instalação, essa porta poderão através do firewall local, será criada uma ACL de URL e um certificado SSL será vinculado a essa porta.</span><span class="sxs-lookup"><span data-stu-id="88689-146">During installation, this port will be allowed through the local firewall, a URL ACL will be created, and an SSL cert will be bound to this port.</span></span> <span data-ttu-id="88689-147">O padrão é 8443.</span><span class="sxs-lookup"><span data-stu-id="88689-147">The default is 8443.</span></span>
    
   - <span data-ttu-id="88689-148">**Impressão digital do certificado:** Esta é a impressão digital do certificado que o ouvinte usará para criptografar o protocolo HTTPS.</span><span class="sxs-lookup"><span data-stu-id="88689-148">**Certificate Thumbprint:** This is the certificate thumbprint the Listener will use to encrypt the HTTPS protocol.</span></span> <span data-ttu-id="88689-149">Serviço de rede deve ter acesso de leitura para a chave privada.</span><span class="sxs-lookup"><span data-stu-id="88689-149">Network Service must have read access to the private key.</span></span>
    
     <span data-ttu-id="88689-150">Clique no botão **Selecionar...** para escolher a impressão digital.</span><span class="sxs-lookup"><span data-stu-id="88689-150">Click the **Select...** button to choose the thumbprint.</span></span>
    
     <span data-ttu-id="88689-151">Você pode encontrar a impressão digital do Certificado usando o Gerenciador de Certificados ou o seguinte comando do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="88689-151">You can find the Certificate thumbprint by using Certificate Manager or by using the following PowerShell command:</span></span>
    
   ```
   Get-ChildItem -path cert:\LocalMachine\My
   ```

   - <span data-ttu-id="88689-152">**Instalar Dir:** Esse é o diretório no qual os binários serão instalados.</span><span class="sxs-lookup"><span data-stu-id="88689-152">**Install Dir:** This is the directory on which the binaries will be installed.</span></span> <span data-ttu-id="88689-153">Você pode alterá-lo do padrão usando o botão **Browse...** .</span><span class="sxs-lookup"><span data-stu-id="88689-153">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="88689-154">**AppData Dir:** Esse é o diretório onde a pasta de Logs e outros dados serão armazenados.</span><span class="sxs-lookup"><span data-stu-id="88689-154">**AppData Dir:** This is the directory where the Logs folder and other data will be stored.</span></span> <span data-ttu-id="88689-155">Você pode alterá-lo do padrão.</span><span class="sxs-lookup"><span data-stu-id="88689-155">You may change it from the default.</span></span> <span data-ttu-id="88689-156">Ela não será excluída em Desinstalar.</span><span class="sxs-lookup"><span data-stu-id="88689-156">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="88689-157">Clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="88689-157">Click **Install**.</span></span>
    
<span data-ttu-id="88689-158">Para validar a instalação, execute as etapas a seguir:</span><span class="sxs-lookup"><span data-stu-id="88689-158">To validate the installation, perform the following steps:</span></span>
  
1. <span data-ttu-id="88689-159">Abra um navegador e navegue atéhttps://localhost:\<service-port\>/healthcheck/</span><span class="sxs-lookup"><span data-stu-id="88689-159">Open a browser and navigate to https://localhost:\<service-port\>/healthcheck/</span></span>
    
    <span data-ttu-id="88689-160">Por padrão, a porta de serviço é 8443 (a menos que você tenha especificado outra porta).</span><span class="sxs-lookup"><span data-stu-id="88689-160">By default, the service port is 8443 (unless you specified another port).</span></span>
    
2. <span data-ttu-id="88689-161">Para garantir que o Ouvinte tenha sido instalado corretamente, procure o seguinte:</span><span class="sxs-lookup"><span data-stu-id="88689-161">To ensure the Listener has installed properly, look for the following:</span></span>
    
   - <span data-ttu-id="88689-162">Se a página de verificação de integridade aparecer, a instalação do Ouvinte foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="88689-162">If the healthcheck page shows up, the Listener installation was successful.</span></span>
    
   - <span data-ttu-id="88689-163">Se o valor de KnownServersCount for 1 ou maior, a conexão com o Redis foi estabelecida.</span><span class="sxs-lookup"><span data-stu-id="88689-163">If the KnownServersCount is 1 or higher, then the connection to Redis is established.</span></span>
    
   - <span data-ttu-id="88689-164">Após aguardar alguns minutos e depois que pelo menos um Agente tiver sido instalado, verifique se o contador ValuesWritten está aumentando.</span><span class="sxs-lookup"><span data-stu-id="88689-164">After waiting a few minutes, and after at least one Agent has been installed, check to see that the ValuesWritten counter is incrementing.</span></span>
    
### <a name="install-the-website"></a><span data-ttu-id="88689-165">Instalar o site</span><span class="sxs-lookup"><span data-stu-id="88689-165">Install the Website</span></span>

<span data-ttu-id="88689-166">Instale o site na máquina host executando o StatsManWebSite.msi e especificando o seguinte:</span><span class="sxs-lookup"><span data-stu-id="88689-166">Install the Website on the host machine by running the StatsManWebSite.msi and specifying the following:</span></span>
  
1. <span data-ttu-id="88689-167">Leia o Contrato de Licença e, se estiver de acordo, selecione \*\*Aceito os termos do Contrato de Licença \*\* e clique em **Avançar**. </span><span class="sxs-lookup"><span data-stu-id="88689-167">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="88689-168">Na próxima página, especifique as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="88689-168">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="88689-169">**Porta de serviço:** Esse é o número de porta que o site escutará.</span><span class="sxs-lookup"><span data-stu-id="88689-169">**Service Port:** This is the port number the web site will listen on.</span></span> <span data-ttu-id="88689-170">Você pode alterar posteriormente usando o Gerenciador do IIS vinculando.</span><span class="sxs-lookup"><span data-stu-id="88689-170">You can change it later by using IIS manager binding.</span></span> <span data-ttu-id="88689-171">Durante a instalação, essa porta poderão através do firewall local.</span><span class="sxs-lookup"><span data-stu-id="88689-171">During installation, this port will be allowed through the local firewall.</span></span>
    
   - <span data-ttu-id="88689-172">**Instalar Dir:** Esse é o diretório onde os binários serão instalados.</span><span class="sxs-lookup"><span data-stu-id="88689-172">**Install Dir:** This is the directory where the binaries will be installed.</span></span> <span data-ttu-id="88689-173">Você pode alterá-lo do padrão usando o botão **Browse...** .</span><span class="sxs-lookup"><span data-stu-id="88689-173">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="88689-174">**AppData Dir:** Esse é o diretório onde a pasta de Logs e outros dados serão armazenados.</span><span class="sxs-lookup"><span data-stu-id="88689-174">**AppData Dir:** This is the directory where the Logs folder and other data will be stored.</span></span> <span data-ttu-id="88689-175">Você pode alterá-lo do padrão.</span><span class="sxs-lookup"><span data-stu-id="88689-175">You may change it from the default.</span></span> <span data-ttu-id="88689-176">Ela não será excluída em Desinstalar.</span><span class="sxs-lookup"><span data-stu-id="88689-176">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="88689-177">Clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="88689-177">Click **Install**.</span></span>
    
<span data-ttu-id="88689-178">Para exibir o site da Web, abra um navegador e navegue até: http://localhost, webport\>/.</span><span class="sxs-lookup"><span data-stu-id="88689-178">To view the Website, open a browser, and navigate to: http://localhost,webport\>/.</span></span>
  
<span data-ttu-id="88689-179">Para exibir somente informações de integridade, abra um navegador e navegue até: http://localhost:\<webport\>/healthcheck/.</span><span class="sxs-lookup"><span data-stu-id="88689-179">To view health information only, open a browser, and navigate to: http://localhost:\<webport\>/healthcheck/.</span></span>
  
<span data-ttu-id="88689-180">Por padrão, o número da porta da Web é 8080.</span><span class="sxs-lookup"><span data-stu-id="88689-180">By default, the web port number is 8080.</span></span> <span data-ttu-id="88689-181">Você pode alterar a associação de porta do site usando o gerenciador do IIS.</span><span class="sxs-lookup"><span data-stu-id="88689-181">You can change the port binding of the website by using IIS manager.</span></span>
  
<span data-ttu-id="88689-182">O instalador da Web adiciona um grupo de segurança local, chamado StatsManWebSiteUsers.</span><span class="sxs-lookup"><span data-stu-id="88689-182">The web installer adds a local security group, called StatsManWebSiteUsers.</span></span> <span data-ttu-id="88689-183">Você pode adicionar contas a esse grupo de segurança para conceder acesso ao site.</span><span class="sxs-lookup"><span data-stu-id="88689-183">You can add accounts to this security group to grant access to the Website.</span></span> 
  
### <a name="install-the-agents"></a><span data-ttu-id="88689-184">Instalar os Agentes</span><span class="sxs-lookup"><span data-stu-id="88689-184">Install the Agents</span></span>

<span data-ttu-id="88689-185">Instale um agente em cada Skype para servidor de negócios que você deseja monitorar executando o StatsManPerfAgent.msi e especificando o seguinte:</span><span class="sxs-lookup"><span data-stu-id="88689-185">Install an Agent on each Skype for Business Server that you wish to monitor by running the StatsManPerfAgent.msi and specifying the following:</span></span>
  
1. <span data-ttu-id="88689-186">Leia o Contrato de Licença e, se estiver de acordo, selecione \*\*Aceito os termos do Contrato de Licença \*\* e clique em **Avançar**. </span><span class="sxs-lookup"><span data-stu-id="88689-186">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="88689-187">Na próxima página, especifique as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="88689-187">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="88689-188">**Senha do Serviço:** esta é a senha que o agente remoto usará para se autenticar no serviço de escuta.</span><span class="sxs-lookup"><span data-stu-id="88689-188">**Service Password:** This is the password the remote agent will use to authenticate to the Listener service.</span></span>
    
   - <span data-ttu-id="88689-189">**URI do serviço:** Esse é o URI de onde o ouvinte reside.</span><span class="sxs-lookup"><span data-stu-id="88689-189">**Service URI:** This is the URI where the Listener resides.</span></span> <span data-ttu-id="88689-190">Ela deve usar o https://name:port formato.</span><span class="sxs-lookup"><span data-stu-id="88689-190">It should use the https://name:port format.</span></span>
    
     <span data-ttu-id="88689-191">Você pode usar um nome NetBIOS ou um FQDN.</span><span class="sxs-lookup"><span data-stu-id="88689-191">You can use a NETBIOS name or a FQDN.</span></span> <span data-ttu-id="88689-192">Você pode usar o nome que também é especificado como o **assunto** ou **Nomes alternativos do assunto** do certificado no serviço do ouvinte, mas isso não é um requisito.</span><span class="sxs-lookup"><span data-stu-id="88689-192">You can use the name that is also specified as the **Subject** or **Subject Alternative Names** of the certificate on the Listener service, but this is not a requirement.</span></span>
    
   - <span data-ttu-id="88689-193">**Pessoal Thumbprint:** Esta é a impressão digital do certificado SSL que do ouvinte está usando.</span><span class="sxs-lookup"><span data-stu-id="88689-193">**Service Thumbprint:** This is the thumbprint of the SSL certificate the Listener is using.</span></span> <span data-ttu-id="88689-194">O agente usará essa impressão digital para autenticar para o ouvinte.</span><span class="sxs-lookup"><span data-stu-id="88689-194">The Agent will use this thumbprint to authenticate to the Listener.</span></span> <span data-ttu-id="88689-195">(Não farão completos de validação do certificado porque é possível usar certificados autoassinados.)</span><span class="sxs-lookup"><span data-stu-id="88689-195">(It will not do full certificate validation because it is possible to use self-signed certificates.)</span></span>
    
   - <span data-ttu-id="88689-196">**Instalar Dir:** Esse é o diretório no qual os binários serão instalados.</span><span class="sxs-lookup"><span data-stu-id="88689-196">**Install Dir:** This is the directory on which the binaries will be installed.</span></span> <span data-ttu-id="88689-197">Você pode alterá-lo do padrão usando o botão **Browse...** .</span><span class="sxs-lookup"><span data-stu-id="88689-197">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="88689-198">**AppData Dir:** Esse é o diretório onde a pasta de Logs e o arquivo Password criptografadas serão armazenados.</span><span class="sxs-lookup"><span data-stu-id="88689-198">**AppData Dir:** This is the directory where the Logs folder and the encrypted password.txt file will be stored.</span></span> <span data-ttu-id="88689-199">Você pode Agradeço alterá-lo do padrão.</span><span class="sxs-lookup"><span data-stu-id="88689-199">You may thanks change it from the default.</span></span> <span data-ttu-id="88689-200">Ela não será excluída em Desinstalar.</span><span class="sxs-lookup"><span data-stu-id="88689-200">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="88689-201">Clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="88689-201">Click **Install**.</span></span>
    
<span data-ttu-id="88689-p121">Se você estiver instalando um Agente em muitos computadores, convém fazer isso no modo autônomo. Por exemplo:  </span><span class="sxs-lookup"><span data-stu-id="88689-p121">If you are installing an Agent on numerous machines, you will probably want to do this in unattended mode. For example:</span></span> 
  
```
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_  STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a><span data-ttu-id="88689-204">Importar a topologia</span><span class="sxs-lookup"><span data-stu-id="88689-204">Import the topology</span></span>
<span data-ttu-id="88689-205"><a name="BKMK_ImportTopology"> </a></span><span class="sxs-lookup"><span data-stu-id="88689-205"></span></span>

<span data-ttu-id="88689-206">Depois de estatísticas Manager é instalado e em execução, você precisa importar o Skype para a topologia de servidor de negócios assim que o Gerenciador de estatísticas sabe o Site, Pool e a função de cada servidor.</span><span class="sxs-lookup"><span data-stu-id="88689-206">After Statistics Manager is installed and running, you need to import the Skype for Business Server topology so that Statistics Manager knows the Site, Pool, and Role of each server.</span></span> <span data-ttu-id="88689-207">Para importar sua Skype para topologia de servidores corporativos, você usará o cmdlet [Get-CsPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) para recuperar informações sobre cada pool em uso na sua organização e importar essas informações para o Manager de estatísticas.</span><span class="sxs-lookup"><span data-stu-id="88689-207">To import your Skype for Business Server topology, you will use the [Get-CsPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) cmdlet to retrieve information about each pool in use in your organization, then import this information into Statistics Manager.</span></span>
  
<span data-ttu-id="88689-208">Para importar o Skype para topologia de servidores corporativos, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="88689-208">To import the Skype for Business Server topology, follow these steps:</span></span>
  
1. <span data-ttu-id="88689-209">Em um host que possui o Skype para cmdlets do PowerShell do servidor de negócios:</span><span class="sxs-lookup"><span data-stu-id="88689-209">On a host that has the Skype for Business Server PowerShell cmdlets:</span></span>
    
    <span data-ttu-id="88689-210">a.</span><span class="sxs-lookup"><span data-stu-id="88689-210">a.</span></span> <span data-ttu-id="88689-211">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="88689-211">Run the following command:</span></span> 
    
   ```
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```
    <span data-ttu-id="88689-212">b.</span><span class="sxs-lookup"><span data-stu-id="88689-212">b.</span></span> <span data-ttu-id="88689-213">Copie o arquivo de "mypoolinfo.xml" para o servidor que executa o ouvinte.</span><span class="sxs-lookup"><span data-stu-id="88689-213">Copy the "mypoolinfo.xml" file to the server that runs the Listener.</span></span>
    
2. <span data-ttu-id="88689-214">No host que executa o Ouvinte:</span><span class="sxs-lookup"><span data-stu-id="88689-214">On the host that runs the Listener:</span></span>
    
   <span data-ttu-id="88689-215">a.</span><span class="sxs-lookup"><span data-stu-id="88689-215">a.</span></span> <span data-ttu-id="88689-216">Execute o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="88689-216">Run PowerShell.</span></span>
    
   <span data-ttu-id="88689-217">b.</span><span class="sxs-lookup"><span data-stu-id="88689-217">b.</span></span> <span data-ttu-id="88689-218">Navegue até o diretório no qual o Ouvinte está instalado.</span><span class="sxs-lookup"><span data-stu-id="88689-218">Navigate to the directory on which the Listener is installed.</span></span> <span data-ttu-id="88689-219">O padrão é:</span><span class="sxs-lookup"><span data-stu-id="88689-219">The default is:</span></span> 
    
   ```
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

3. <span data-ttu-id="88689-220">Para confirmar quais servidores estão sendo adicionados e atualizados, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="88689-220">To confirm which servers are being added and updated, run the following command:</span></span>
    
   ```
    .\Update-StatsManServerInfo.ps1 -CsPoolFile  <path to mypoolinfo.xml>
   ```

<span data-ttu-id="88689-221">O seguinte comando permite ver todas as opções:</span><span class="sxs-lookup"><span data-stu-id="88689-221">The following command enables you to view all options:</span></span>
  
```
Get-Help .\Update-StatsManServerInfo.ps1 -Detailed 
```

<span data-ttu-id="88689-222">Para ver as informações do servidor que estão sendo importadas atualmente, execute o seguinte script: </span><span class="sxs-lookup"><span data-stu-id="88689-222">To see your your currently imported server information, run the following script:</span></span> 
  
```
.\Get-StatsManServerInfo.ps1
```

<span data-ttu-id="88689-223">Por exemplo-- se você gostaria de monitorar os servidores que não estão na sua Skype para topologia de servidores de negócios – um servidor Exchange, você poderá fazer uma importação de servidor único no host que executa o ouvinte.</span><span class="sxs-lookup"><span data-stu-id="88689-223">If you would like to monitor servers that are not in your Skype for Business Server topology--an Exchange Server, for example--you can do a single-server import on the host that runs the Listener.</span></span> <span data-ttu-id="88689-224">Para fazer uma importação de um único servidor, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="88689-224">To do a single-server import, follow these steps:</span></span>
  
1. <span data-ttu-id="88689-225">Navegue até o diretório no qual o Ouvinte está instalado.</span><span class="sxs-lookup"><span data-stu-id="88689-225">Navigate to the directory on which the Listener is installed.</span></span> <span data-ttu-id="88689-226">O padrão é:</span><span class="sxs-lookup"><span data-stu-id="88689-226">The default is:</span></span> 
    
   ```
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

2. <span data-ttu-id="88689-227">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="88689-227">Run the following command:</span></span>
    
   ```
    .\Update-StatsManServerInfo.ps1 -HostName <hostname> -SiteName <name of site> -PoolName <poolName> -Roles <role1>[,<role2>,<roleN>]
   ```

## <a name="troubleshoot-your-deployment"></a><span data-ttu-id="88689-228">Solução de problemas de implantação</span><span class="sxs-lookup"><span data-stu-id="88689-228">Troubleshoot your deployment</span></span>
<span data-ttu-id="88689-229"><a name="BKMK_Troubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="88689-229"></span></span>

<span data-ttu-id="88689-230">Se ocorrer falha na inicialização de um Agente, verifique o seguinte: </span><span class="sxs-lookup"><span data-stu-id="88689-230">If an Agent fails to start, check for the following:</span></span> 
  
- <span data-ttu-id="88689-231">É o agente registrado no Gerenciador de estatísticas?</span><span class="sxs-lookup"><span data-stu-id="88689-231">Is the agent registered in Statistics Manager?</span></span>
    
1. <span data-ttu-id="88689-p129">	Certifique-se de seguir as instruções para importar a topologia. Veja [Importar a topologia](deploy.md#BKMK_ImportTopology).  </span><span class="sxs-lookup"><span data-stu-id="88689-p129">Make sure you followed the instructions for importing the topology. See [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
2. <span data-ttu-id="88689-234">Se o Agente estiver em um servidor que não está listado na topologia (por exemplo, os nós de um cluster SQL AlwaysOn), você precisará adicionar o Agente manualmente seguindo as instruções contidas em [Importar a topologia](deploy.md#BKMK_ImportTopology).</span><span class="sxs-lookup"><span data-stu-id="88689-234">If the Agent is on a server that is not listed in the topology (for example, the nodes in a SQL AlwaysOn cluster), you will need to add the Agent manually by following the instructions in [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
- <span data-ttu-id="88689-235">O Agente pode contatar o Ouvinte?</span><span class="sxs-lookup"><span data-stu-id="88689-235">Can the Agent contact the Listener?</span></span>
    
1. <span data-ttu-id="88689-236">Verifique se o serviço de escuta está em execução.  </span><span class="sxs-lookup"><span data-stu-id="88689-236">Make sure the Listener service is running.</span></span> 
    
    <span data-ttu-id="88689-237">Se não estiver, verifique se o Redis está em execução e, em seguida, tente reiniciar o Ouvinte.</span><span class="sxs-lookup"><span data-stu-id="88689-237">If it is not running, make sure Redis is running, and then try to restart the Listener.</span></span>
    
2. <span data-ttu-id="88689-238">Verifique se a porta está aberta para o serviço de escuta e que o computador agente pode se comunicar com a porta.</span><span class="sxs-lookup"><span data-stu-id="88689-238">Make sure the port is open to the Listener service, and that the Agent computer can communicate with the port.</span></span>
    
- <span data-ttu-id="88689-239">Para garantir que o Gerenciador de estatísticas é coleta de dados, você pode verificar o arquivo CSV da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="88689-239">To ensure that Statistics Manager is collecting data, you can check the CSV file as follows.</span></span> 
    
    <span data-ttu-id="88689-240">O seguinte comando recupera os nomes de armazenamento do contador:  </span><span class="sxs-lookup"><span data-stu-id="88689-240">The following command retrieves the counter storage names:</span></span> 
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    <span data-ttu-id="88689-241">O próximo comando recupera os valores dos contadores especificados: </span><span class="sxs-lookup"><span data-stu-id="88689-241">The next command retrieves the values for the specified counters:</span></span> 
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

<span data-ttu-id="88689-242">Para obter informações sobre todos os eventos que talvez você veja no log de eventos de aplicativo, consulte [Solucionar problemas de Gerenciador de estatísticas para Skype para Business Server 2015](troubleshoot.md).</span><span class="sxs-lookup"><span data-stu-id="88689-242">For information about all the events you might see in the application event log, see [Troubleshoot Statistics Manager for Skype for Business Server 2015](troubleshoot.md).</span></span>
  
## <a name="create-a-self-signed-certificate"></a><span data-ttu-id="88689-243">Criar um certificado autoassinado</span><span class="sxs-lookup"><span data-stu-id="88689-243">Create a self-signed certificate</span></span>
<span data-ttu-id="88689-244"><a name="BKMK_SelfCert"> </a></span><span class="sxs-lookup"><span data-stu-id="88689-244"></span></span>

<span data-ttu-id="88689-245">A Microsoft recomenda que você use um certificado assinado por uma autoridade de certificação confiável.</span><span class="sxs-lookup"><span data-stu-id="88689-245">Microsoft strongly recommends that you use a certificate signed by a trusted certificate authority.</span></span> <span data-ttu-id="88689-246">No entanto, se quiser usar um certificado autoassinado para fins de teste, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="88689-246">However, if you want to use a self-signed certificate for testing purposes, do the following:</span></span> 
  
1. <span data-ttu-id="88689-247">Conectado como Administrador em um console do PowerShell, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="88689-247">From a PowerShell console while logged on as Administrator, type the following:</span></span>
    
   ```
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. <span data-ttu-id="88689-248">Tipo `certlm.msc`.</span><span class="sxs-lookup"><span data-stu-id="88689-248">Type  `certlm.msc`.</span></span> <span data-ttu-id="88689-249">Isso abrirá o Gerenciador de Certificados do computador local.</span><span class="sxs-lookup"><span data-stu-id="88689-249">This will open the Certificate Manager for the local machine.</span></span>
    
3. <span data-ttu-id="88689-250">Navegue até o **pessoal**e abra **certificados**.</span><span class="sxs-lookup"><span data-stu-id="88689-250">Navigate to **Personal**, and then open **Certificates**.</span></span>
    
4. <span data-ttu-id="88689-251">Clique com o botão direito em **StatsManListener -\>todas as tarefas -\>gerenciar chaves particulares …**</span><span class="sxs-lookup"><span data-stu-id="88689-251">Right click on **StatsManListener-\>All Tasks-\>Manage Private Keys…**</span></span>
    
5. <span data-ttu-id="88689-252">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="88689-252">Click **Add**.</span></span>
    
6. <span data-ttu-id="88689-253">Na caixa **Digite os nomes de objeto a serem selecionados**, digite o seguinte: Serviço de Rede.</span><span class="sxs-lookup"><span data-stu-id="88689-253">In the **Enter the object names to select** box, type the following: Network Service</span></span>
    
7. <span data-ttu-id="88689-254">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="88689-254">Click **OK**.</span></span>
    
8. <span data-ttu-id="88689-p132">Em **Controle Total**, desmarque a caixa de seleção **Permitir**. (Apenas o acesso de leitura é necessário.)</span><span class="sxs-lookup"><span data-stu-id="88689-p132">Under **Full Control**, un-check the **Allow** check box. (Only Read access is necessary.)</span></span>
    
9. <span data-ttu-id="88689-257">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="88689-257">Click **OK**.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="88689-258">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="88689-258">For more information</span></span>
<span data-ttu-id="88689-259"><a name="BKMK_SelfCert"> </a></span><span class="sxs-lookup"><span data-stu-id="88689-259"></span></span>

<span data-ttu-id="88689-260">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="88689-260">For more information, see the following:</span></span>
  
- [<span data-ttu-id="88689-261">Plan for Statistics Manager for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="88689-261">Plan for Statistics Manager for Skype for Business Server 2015</span></span>](plan.md)
    
- [<span data-ttu-id="88689-262">Upgrade Statistics Manager for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="88689-262">Upgrade Statistics Manager for Skype for Business Server 2015</span></span>](upgrade.md)
    
- [<span data-ttu-id="88689-263">Troubleshoot Statistics Manager for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="88689-263">Troubleshoot Statistics Manager for Skype for Business Server 2015</span></span>](troubleshoot.md)
    
- [<span data-ttu-id="88689-264">Blog sobre o Gerenciador de Estatísticas do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="88689-264">Skype for Business Server Statistics Manager blog</span></span>](https://blogs.technet.microsoft.com/skypestatsman/)
    

