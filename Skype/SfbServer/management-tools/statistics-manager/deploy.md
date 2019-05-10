---
title: Implantar Gerenciador de Estatísticas do Skype for Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: 'Resumo: Leia este tópico para saber como implantar o Gerenciador de Estatísticas do Skype for Business Server.'
ms.openlocfilehash: c70bb596914142fb03e87ccd7e2f1df606aac31f
ms.sourcegitcommit: b2acf18ba6487154ebb4ee46938e96dc56cb2c9a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/09/2019
ms.locfileid: "33864901"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="8e21d-103">Implantar Gerenciador de Estatísticas do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8e21d-103">Deploy Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="8e21d-104">**Resumo:** Leia este tópico para saber como implantar o Gerenciador de Estatísticas do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8e21d-104">**Summary:** Read this topic to learn how to deploy Statistics Manager for Skype for Business Server.</span></span>
  
 <span data-ttu-id="8e21d-105">O Gerenciador de Estatísticas do Skype for Business Server é uma poderosa ferramenta que permite exibir o desempenho e a integridade do Skype for Business Server em tempo real.</span><span class="sxs-lookup"><span data-stu-id="8e21d-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="8e21d-106">É possível sondar dados de desempenho em centenas de servidores em intervalos de alguns segundos e ver os resultados instantaneamente no site do Gerenciador de Estatísticas.</span><span class="sxs-lookup"><span data-stu-id="8e21d-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>
  
<span data-ttu-id="8e21d-107">Antes de tentar instalar o Gerenciador de Estatísticas, certifique-se que você está familiarizado com os requisitos de software, rede e hardware.</span><span class="sxs-lookup"><span data-stu-id="8e21d-107">Before you attempt to install Statistics Manager, be sure you are familiar with the software, networking, and hardware requirements.</span></span> <span data-ttu-id="8e21d-108">Para mais informações, confira [Plano para Gerenciador de Estatísticas do Skype for Business Server](plan.md).</span><span class="sxs-lookup"><span data-stu-id="8e21d-108">For more information, see [Plan for Statistics Manager for Skype for Business Server](plan.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="8e21d-109">Se você estiver atualizando de uma versão anterior do Gerenciador de Estatísticas, confira [Atualizar o Gerenciador de Estatísticas do Skype for Business Server](upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="8e21d-109">If you are upgrading from a previous version of Statistics Manager, see [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="8e21d-110">O site do Gerenciador de Estatísticas foi testado e funciona corretamente no Internet Explorer 11+, Microsoft Edge 20.10240+ e Chrome 46+ (versão evergreen atual).</span><span class="sxs-lookup"><span data-stu-id="8e21d-110">The Statistics Manager Website has been tested and works correctly on Internet Explorer 11+, Edge 20.10240+ , and Chrome 46+ (current evergreen version).</span></span> 
  
<span data-ttu-id="8e21d-111">Você pode encontrar o Gerenciador de Estatísticas disponível para download na [ https://aka.ms/StatsManDownload ](https://aka.ms/StatsManDownload).</span><span class="sxs-lookup"><span data-stu-id="8e21d-111">You can find the Statistics Manager downloadable at [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload).</span></span> 
  
<span data-ttu-id="8e21d-112">Este tópico inclui as seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="8e21d-112">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="8e21d-113">Implantar o Gerenciador de Estatísticas</span><span class="sxs-lookup"><span data-stu-id="8e21d-113">Deploy Statistics Manager</span></span>](deploy.md#BKMK_Deploy)
    
- [<span data-ttu-id="8e21d-114">Solução de problemas de implantação</span><span class="sxs-lookup"><span data-stu-id="8e21d-114">Troubleshoot your deployment</span></span>](deploy.md#BKMK_Troubleshoot)
    
- [<span data-ttu-id="8e21d-115">Criar um certificado autoassinado</span><span class="sxs-lookup"><span data-stu-id="8e21d-115">Create a self-signed certificate</span></span>](deploy.md#BKMK_SelfCert)
    
## <a name="deploy-statistics-manager"></a><span data-ttu-id="8e21d-116">Implantar o Gerenciador de Estatísticas</span><span class="sxs-lookup"><span data-stu-id="8e21d-116">Deploy Statistics Manager</span></span>
<span data-ttu-id="8e21d-117"><a name="BKMK_Deploy"> </a></span><span class="sxs-lookup"><span data-stu-id="8e21d-117"><a name="BKMK_Deploy"> </a></span></span>

<span data-ttu-id="8e21d-118">Para implantar o Gerenciador de Estatísticas, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="8e21d-118">To deploy Statistics Manager, follow these steps:</span></span>
  
1. <span data-ttu-id="8e21d-119">Prepare o computador host Ouvinte instalando o sistema de cache na memória Redis e verificando se você instalou os certificados adequados.</span><span class="sxs-lookup"><span data-stu-id="8e21d-119">Prepare the Listener host machine by installing the Redis in-memory caching system, and by ensuring that you have installed the appropriate certificates.</span></span>
    
2. <span data-ttu-id="8e21d-120">Instale o serviço de escuta no computador host.</span><span class="sxs-lookup"><span data-stu-id="8e21d-120">Install the Listener service on the host machine.</span></span> 
    
3. <span data-ttu-id="8e21d-121">Instale o site no computador host.</span><span class="sxs-lookup"><span data-stu-id="8e21d-121">Install the Website on the host machine.</span></span>
    
4. <span data-ttu-id="8e21d-122">Instale um Agente em cada computador com Skype for Business Server que desejar monitorar.</span><span class="sxs-lookup"><span data-stu-id="8e21d-122">Install an Agent on each Skype for Business Server machine you wish to monitor.</span></span>
    
5. <span data-ttu-id="8e21d-123">Importe a topologia para os servidores que estiver monitorando.</span><span class="sxs-lookup"><span data-stu-id="8e21d-123">Import the topology for the servers you are monitoring.</span></span>
    
> [!NOTE]
> <span data-ttu-id="8e21d-124">O Redis, o serviço de escuta e o site deverão estar todos instalados no mesmo computador host.</span><span class="sxs-lookup"><span data-stu-id="8e21d-124">Redis, the Listener service, and the Website must all be installed on the same host machine.</span></span> <span data-ttu-id="8e21d-125">Certifique-se que o computador host não tem o Skype for Business Server instalado.</span><span class="sxs-lookup"><span data-stu-id="8e21d-125">Be sure the host machine does not have Skype for Business Server installed.</span></span> 
  
### <a name="prepare-the-listener-host-machine"></a><span data-ttu-id="8e21d-126">Preparar o computador host Ouvinte</span><span class="sxs-lookup"><span data-stu-id="8e21d-126">Prepare the Listener host machine</span></span>

<span data-ttu-id="8e21d-127">Para preparar o computador host, será necessário instalar o sistema de cache na memória Redis e verificar se há um certificado válido no computador.</span><span class="sxs-lookup"><span data-stu-id="8e21d-127">To prepare the host machine, you will need to install the Redis in-memory caching system, and ensure that a valid certificate is on the machine.</span></span> <span data-ttu-id="8e21d-128">A Microsoft recomenda que você instale o build estável mais recente do Redis 3.0.</span><span class="sxs-lookup"><span data-stu-id="8e21d-128">Microsoft recommends that you install the latest stable build of Redis 3.0.</span></span> <span data-ttu-id="8e21d-129">A versão 2.0 do Gerenciador de Estatísticas foi testada com o Redis 3.2.100.</span><span class="sxs-lookup"><span data-stu-id="8e21d-129">Statistics Manager version 2.0 was tested with Redis 3.2.100.</span></span> 
  
1. <span data-ttu-id="8e21d-130">Baixe o Redis do seguinte site: [ https://github.com/MSOpenTech/redis ](https://github.com/MSOpenTech/redis).</span><span class="sxs-lookup"><span data-stu-id="8e21d-130">Download Redis from the following site: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis).</span></span> 
    
    <span data-ttu-id="8e21d-131">Instaladores não assinados podem ser baixados do [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)</span><span class="sxs-lookup"><span data-stu-id="8e21d-131">Unsigned installers can be downloaded from [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)</span></span>
    
    <span data-ttu-id="8e21d-132">Se necessário, os binários assinados estão disponíveis por meio de gerenciadores de pacotes populares: [Nuget](https://www.nuget.org/packages/Redis-64/) e [Choclatey](https://chocolatey.org/packages/redis-64).</span><span class="sxs-lookup"><span data-stu-id="8e21d-132">If required, signed binaries are available through popular package managers: [Nuget](https://www.nuget.org/packages/Redis-64/) and [Choclatey](https://chocolatey.org/packages/redis-64).</span></span>
    
   - <span data-ttu-id="8e21d-133">Execute o msi fornecido e siga as instruções.</span><span class="sxs-lookup"><span data-stu-id="8e21d-133">Run the provided msi and follow the prompts.</span></span>
    
   - <span data-ttu-id="8e21d-134">Não marque a caixa para adicionar uma regra de firewall.</span><span class="sxs-lookup"><span data-stu-id="8e21d-134">Do not check the box to add a firewall rule.</span></span>
    
2. <span data-ttu-id="8e21d-135">O serviço de escuta requer um certificado.</span><span class="sxs-lookup"><span data-stu-id="8e21d-135">The Listener service requires a certificate.</span></span> <span data-ttu-id="8e21d-136">A Microsoft recomenda que você tenha um certificado assinado por uma autoridade de certificação confiável.</span><span class="sxs-lookup"><span data-stu-id="8e21d-136">Microsoft strongly recommends that you have a certificate signed by a trusted certificate authority.</span></span> 
    
    <span data-ttu-id="8e21d-137">Se quiser usar um certificado autoassinado (para fins de teste em um laboratório, por exemplo), veja [Criar um certificado autoassinado](deploy.md#BKMK_SelfCert).</span><span class="sxs-lookup"><span data-stu-id="8e21d-137">If you want to use a self-signed certificate--for testing purposes in a lab, for example--see [Create a self-signed certificate](deploy.md#BKMK_SelfCert).</span></span>
    
    <span data-ttu-id="8e21d-p106">Observe que o Agente utiliza a verificação de impressão digital do certificado (em vez de verificação de cadeia). Ele não fará a validação completa do certificado, pois é possível usar certificados autoassinados.</span><span class="sxs-lookup"><span data-stu-id="8e21d-p106">Note that the Agent uses certificate thumbprint verification (instead of chain verification). It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>
    
### <a name="install-the-listener-service"></a><span data-ttu-id="8e21d-140">Instalar o serviço de escuta</span><span class="sxs-lookup"><span data-stu-id="8e21d-140">Install the Listener service</span></span>

<span data-ttu-id="8e21d-141">Instale o serviço de escuta no computador host executando o StatsManPerfAgentListener.msi e especificando o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8e21d-141">Install the Listener service on the host machine by running the StatsManPerfAgentListener.msi and specifying the following:</span></span>
  
1. <span data-ttu-id="8e21d-142">Leia o Contrato de Licença e, se estiver de acordo, selecione \*\*Aceito os termos do Contrato de Licença \*\* e clique em **Avançar**. </span><span class="sxs-lookup"><span data-stu-id="8e21d-142">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="8e21d-143">Na próxima página, especifique as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="8e21d-143">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="8e21d-144">**Senha do Serviço:** esta é a senha que os Agentes remotos usarão para se autenticarem no serviço de escuta.</span><span class="sxs-lookup"><span data-stu-id="8e21d-144">**Service Password:** This is the password the remote Agents will use to authenticate to the Listener service.</span></span>
    
   - <span data-ttu-id="8e21d-145">**Porta do Serviço:** Este é o número de porta HTTPS que o Ouvinte usará para se comunicar com os Agentes.</span><span class="sxs-lookup"><span data-stu-id="8e21d-145">**Service Port:** This is the HTTPS port number that the Listener will use to communicate with the Agents.</span></span> <span data-ttu-id="8e21d-146">Durante a instalação, essa porta será permitida através do firewall local, uma ACL de URL será criada e um certificado SSL será associado a essa porta.</span><span class="sxs-lookup"><span data-stu-id="8e21d-146">During installation, this port will be allowed through the local firewall, a URL ACL will be created, and an SSL cert will be bound to this port.</span></span> <span data-ttu-id="8e21d-147">O padrão é 8443.</span><span class="sxs-lookup"><span data-stu-id="8e21d-147">The default is 8443.</span></span>
    
   - <span data-ttu-id="8e21d-148">**Impressão Digital do Certificado:** Essa é a impressão digital de certificado que o Ouvinte usará para criptografar o protocolo HTTPS.</span><span class="sxs-lookup"><span data-stu-id="8e21d-148">**Certificate Thumbprint:** This is the certificate thumbprint the Listener will use to encrypt the HTTPS protocol.</span></span> <span data-ttu-id="8e21d-149">O Serviço de Rede deve ter acesso de leitura à chave privada.</span><span class="sxs-lookup"><span data-stu-id="8e21d-149">Network Service must have read access to the private key.</span></span>
    
     <span data-ttu-id="8e21d-150">Clique no botão **Selecionar...** para escolher a impressão digital.</span><span class="sxs-lookup"><span data-stu-id="8e21d-150">Click the **Select...** button to choose the thumbprint.</span></span>
    
     <span data-ttu-id="8e21d-151">Você pode encontrar a impressão digital do Certificado usando o Gerenciador de Certificados ou o seguinte comando do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8e21d-151">You can find the Certificate thumbprint by using Certificate Manager or by using the following PowerShell command:</span></span>
    
   ```
   Get-ChildItem -path cert:\LocalMachine\My
   ```

   - <span data-ttu-id="8e21d-152">**Install Dir:** Esse é o diretório no qual os binários serão instalados.</span><span class="sxs-lookup"><span data-stu-id="8e21d-152">**Install Dir:** This is the directory on which the binaries will be installed.</span></span> <span data-ttu-id="8e21d-153">Você pode alterá-lo do padrão usando o botão \*\*Procurar... \*\*.</span><span class="sxs-lookup"><span data-stu-id="8e21d-153">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="8e21d-154">**AppData Dir:** Esse é o diretório onde a pasta Logs e outros dados serão armazenados.</span><span class="sxs-lookup"><span data-stu-id="8e21d-154">**AppData Dir:** This is the directory where the Logs folder and other data will be stored.</span></span> <span data-ttu-id="8e21d-155">Você pode alterá-lo do padrão.</span><span class="sxs-lookup"><span data-stu-id="8e21d-155">You may change it from the default.</span></span> <span data-ttu-id="8e21d-156">Ele não será excluído na desinstalação.</span><span class="sxs-lookup"><span data-stu-id="8e21d-156">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="8e21d-157">Clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="8e21d-157">Click **Install**.</span></span>
    
<span data-ttu-id="8e21d-158">Para validar a instalação, execute as etapas a seguir:</span><span class="sxs-lookup"><span data-stu-id="8e21d-158">To validate the installation, perform the following steps:</span></span>
  
1. <span data-ttu-id="8e21d-159">Abra um navegador e navegue até https://localhost:\<service-port\>/healthcheck/</span><span class="sxs-lookup"><span data-stu-id="8e21d-159">Open a browser and navigate to https://localhost:\<service-port\>/healthcheck/</span></span>
    
    <span data-ttu-id="8e21d-160">Por padrão, a porta de serviço é 8443 (a menos que você tenha especificado outra porta).</span><span class="sxs-lookup"><span data-stu-id="8e21d-160">By default, the service port is 8443 (unless you specified another port).</span></span>
    
2. <span data-ttu-id="8e21d-161">Para garantir que o Ouvinte tenha sido instalado corretamente, procure o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8e21d-161">To ensure the Listener has installed properly, look for the following:</span></span>
    
   - <span data-ttu-id="8e21d-162">Se a página de verificação de integridade aparecer, a instalação do Ouvinte foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="8e21d-162">If the healthcheck page shows up, the Listener installation was successful.</span></span>
    
   - <span data-ttu-id="8e21d-163">Se o KnownServerCount for 1 ou superior, a conexão para relacionada é estabelecida.</span><span class="sxs-lookup"><span data-stu-id="8e21d-163">If the KnownServerCount is 1 or higher,  the connection to Redis is established.</span></span>
    
   - <span data-ttu-id="8e21d-164">Após aguardar alguns minutos e depois que pelo menos um Agente tiver sido instalado, verifique se o contador ValuesWritten está aumentando.</span><span class="sxs-lookup"><span data-stu-id="8e21d-164">After waiting a few minutes, and after at least one Agent has been installed, check to see that the ValuesWritten counter is incrementing.</span></span>
    
### <a name="install-the-website"></a><span data-ttu-id="8e21d-165">Instalar o site</span><span class="sxs-lookup"><span data-stu-id="8e21d-165">Install the Website</span></span>

<span data-ttu-id="8e21d-166">Instalar o site no computador host executando o StatsManWebSite.msi (incluindo o[Skype for Business Server, o Gerenciador de Estatísticas em tempo real (64 bits)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)) e especificar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8e21d-166">Install the Website on the host machine by running the StatsManWebSite.msi (included with [Skype for Business Server, Real-Time Statistics Manager (64-bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)) and specifying the following:</span></span>
  
1. <span data-ttu-id="8e21d-167">Leia o Contrato de Licença e, se estiver de acordo, selecione \*\*Aceito os termos do Contrato de Licença \*\* e clique em **Avançar**. </span><span class="sxs-lookup"><span data-stu-id="8e21d-167">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="8e21d-168">Na próxima página, especifique as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="8e21d-168">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="8e21d-169">**Porta do Serviço:** Esse é o número de porta que o site da web escutará.</span><span class="sxs-lookup"><span data-stu-id="8e21d-169">**Service Port:** This is the port number the web site will listen on.</span></span> <span data-ttu-id="8e21d-170">Você pode alterá-lo posteriormente usando a associação do gerenciador do IIS.</span><span class="sxs-lookup"><span data-stu-id="8e21d-170">You can change it later by using IIS manager binding.</span></span> <span data-ttu-id="8e21d-171">Durante a instalação, essa porta será permitida através do firewall local.</span><span class="sxs-lookup"><span data-stu-id="8e21d-171">During installation, this port will be allowed through the local firewall.</span></span>
    
   - <span data-ttu-id="8e21d-172">**Instalação Dir:** Esse é o diretório onde os binários serão instalados.</span><span class="sxs-lookup"><span data-stu-id="8e21d-172">**Install Dir:** This is the directory where the binaries will be installed.</span></span> <span data-ttu-id="8e21d-173">Você pode alterá-lo do padrão usando o botão \*\*Procurar... \*\*.</span><span class="sxs-lookup"><span data-stu-id="8e21d-173">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="8e21d-174">**AppData Dir:** Esse é o diretório onde a pasta Logs e outros dados serão armazenados.</span><span class="sxs-lookup"><span data-stu-id="8e21d-174">**AppData Dir:** This is the directory where the Logs folder and other data will be stored.</span></span> <span data-ttu-id="8e21d-175">Você pode alterá-lo do padrão.</span><span class="sxs-lookup"><span data-stu-id="8e21d-175">You may change it from the default.</span></span> <span data-ttu-id="8e21d-176">Ele não será excluído na desinstalação.</span><span class="sxs-lookup"><span data-stu-id="8e21d-176">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="8e21d-177">Clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="8e21d-177">Click **Install**.</span></span>
    
<span data-ttu-id="8e21d-178">Para exibir o site, abra um navegador e navegue até: http://localhost, webport\>/.</span><span class="sxs-lookup"><span data-stu-id="8e21d-178">To view the Website, open a browser, and navigate to: http://localhost,webport\>/.</span></span>
  
<span data-ttu-id="8e21d-179">Para exibir apenas informações de integridade, abra um navegador e vá até: http://localhost:\<webport\>/healthcheck/.</span><span class="sxs-lookup"><span data-stu-id="8e21d-179">To view health information only, open a browser, and navigate to: http://localhost:\<webport\>/healthcheck/.</span></span>
  
<span data-ttu-id="8e21d-180">Por padrão, o número da porta da Web é 8080.</span><span class="sxs-lookup"><span data-stu-id="8e21d-180">By default, the web port number is 8080.</span></span> <span data-ttu-id="8e21d-181">Você pode alterar a associação de porta do site usando o gerenciador do IIS.</span><span class="sxs-lookup"><span data-stu-id="8e21d-181">You can change the port binding of the website by using IIS manager.</span></span>
  
<span data-ttu-id="8e21d-182">O instalador da Web adiciona um grupo de segurança local, chamado StatsManWebSiteUsers.</span><span class="sxs-lookup"><span data-stu-id="8e21d-182">The web installer adds a local security group, called StatsManWebSiteUsers.</span></span> <span data-ttu-id="8e21d-183">Você pode adicionar contas a esse grupo de segurança para conceder acesso ao site.</span><span class="sxs-lookup"><span data-stu-id="8e21d-183">You can add accounts to this security group to grant access to the Website.</span></span> 
  
### <a name="install-the-agents"></a><span data-ttu-id="8e21d-184">Instalar os Agentes</span><span class="sxs-lookup"><span data-stu-id="8e21d-184">Install the Agents</span></span>

<span data-ttu-id="8e21d-185">Instale um Agente em cada Skype for Business Server que deseja monitorar executando o arquivo StatsManPerfAgent.msi e especificando o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8e21d-185">Install an Agent on each Skype for Business Server that you wish to monitor by running the StatsManPerfAgent.msi and specifying the following:</span></span>
  
1. <span data-ttu-id="8e21d-186">Leia o Contrato de Licença e, se estiver de acordo, selecione \*\*Aceito os termos do Contrato de Licença \*\* e clique em **Avançar**. </span><span class="sxs-lookup"><span data-stu-id="8e21d-186">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="8e21d-187">Na próxima página, especifique as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="8e21d-187">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="8e21d-188">**Senha do Serviço:** esta é a senha que o agente remoto usará para se autenticar no serviço de escuta.</span><span class="sxs-lookup"><span data-stu-id="8e21d-188">**Service Password:** This is the password the remote agent will use to authenticate to the Listener service.</span></span>
    
   - <span data-ttu-id="8e21d-189">**Serviço URI:** Esse é o URI onde o Ouvinte reside.</span><span class="sxs-lookup"><span data-stu-id="8e21d-189">**Service URI:** This is the URI where the Listener resides.</span></span> <span data-ttu-id="8e21d-190">Deve-se usar o https://name:port formatar.</span><span class="sxs-lookup"><span data-stu-id="8e21d-190">It should use the https://name:port format.</span></span>
    
     <span data-ttu-id="8e21d-191">Você pode usar um nome NetBIOS ou um FQDN.</span><span class="sxs-lookup"><span data-stu-id="8e21d-191">You can use a NETBIOS name or a FQDN.</span></span> <span data-ttu-id="8e21d-192">Você pode usar o nome especificado como também os **Assunto** ou **Nomes de Assuntos Alternativos** do certificado em serviço de escuta, mas isso não é um requisito.</span><span class="sxs-lookup"><span data-stu-id="8e21d-192">You can use the name that is also specified as the **Subject** or **Subject Alternative Names** of the certificate on the Listener service, but this is not a requirement.</span></span>
    
   - <span data-ttu-id="8e21d-193">**Serviço de Impressão Digital:** Essa é a impressão digital do certificado SSL que o Ouvinte está usando.</span><span class="sxs-lookup"><span data-stu-id="8e21d-193">**Service Thumbprint:** This is the thumbprint of the SSL certificate the Listener is using.</span></span> <span data-ttu-id="8e21d-194">O Agente usará essa impressão digital para se autenticar com o Ouvinte.</span><span class="sxs-lookup"><span data-stu-id="8e21d-194">The Agent will use this thumbprint to authenticate to the Listener.</span></span> <span data-ttu-id="8e21d-195">(Ele não fará a validação completa do certificado, pois é possível usar certificados autoassinados.)</span><span class="sxs-lookup"><span data-stu-id="8e21d-195">(It will not do full certificate validation because it is possible to use self-signed certificates.)</span></span>
    
   - <span data-ttu-id="8e21d-196">**Install Dir:** Esse é o diretório no qual os binários serão instalados.</span><span class="sxs-lookup"><span data-stu-id="8e21d-196">**Install Dir:** This is the directory on which the binaries will be installed.</span></span> <span data-ttu-id="8e21d-197">Você pode alterá-lo do padrão usando o botão \*\*Procurar... \*\*.</span><span class="sxs-lookup"><span data-stu-id="8e21d-197">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="8e21d-198">**AppData Dir:** Esse é o diretório onde a pasta Logs e o arquivo password.txt criptografado serão armazenados.</span><span class="sxs-lookup"><span data-stu-id="8e21d-198">**AppData Dir:** This is the directory where the Logs folder and the encrypted password.txt file will be stored.</span></span> <span data-ttu-id="8e21d-199">Você pode alterar o diretório do padrão.</span><span class="sxs-lookup"><span data-stu-id="8e21d-199">You may thanks change it from the default.</span></span> <span data-ttu-id="8e21d-200">Ele não será excluído na desinstalação.</span><span class="sxs-lookup"><span data-stu-id="8e21d-200">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="8e21d-201">Clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="8e21d-201">Click **Install**.</span></span>
    
<span data-ttu-id="8e21d-p121">Se você estiver instalando um Agente em muitos computadores, convém fazer isso no modo autônomo. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="8e21d-p121">If you are installing an Agent on numerous machines, you will probably want to do this in unattended mode. For example:</span></span> 
  
```
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_  STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a><span data-ttu-id="8e21d-204">Importar a topologia</span><span class="sxs-lookup"><span data-stu-id="8e21d-204">Import the topology</span></span>
<span data-ttu-id="8e21d-205"><a name="BKMK_ImportTopology"> </a></span><span class="sxs-lookup"><span data-stu-id="8e21d-205"><a name="BKMK_ImportTopology"> </a></span></span>

<span data-ttu-id="8e21d-206">Depois que o StatisticsManager for instalado e executado, você precisará importar a topologia do Skype for Business Server para que o Gerenciador de Estatísticas saiba o Site, o Pool e a Função de cada servidor.</span><span class="sxs-lookup"><span data-stu-id="8e21d-206">After Statistics Manager is installed and running, you need to import the Skype for Business Server topology so that Statistics Manager knows the Site, Pool, and Role of each server.</span></span> <span data-ttu-id="8e21d-207">Para importar a topologia do Skype for Business Server, você usará o [Get-CsPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) cmdlet para recuperar informações sobre cada grupo em uso na sua organização. Em seguida, importe essas informações para o Gerenciador de Estatísticas.</span><span class="sxs-lookup"><span data-stu-id="8e21d-207">To import your Skype for Business Server topology, you will use the [Get-CsPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) cmdlet to retrieve information about each pool in use in your organization, then import this information into Statistics Manager.</span></span>
  
<span data-ttu-id="8e21d-208">Para importar a topologia do Skype for Business Server, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="8e21d-208">To import the Skype for Business Server topology, follow these steps:</span></span>
  
1. <span data-ttu-id="8e21d-209">Em um host que tem o Skype for Business Server PowerShell cmdlets:</span><span class="sxs-lookup"><span data-stu-id="8e21d-209">On a host that has the Skype for Business Server PowerShell cmdlets:</span></span>
    
    <span data-ttu-id="8e21d-210">a.</span><span class="sxs-lookup"><span data-stu-id="8e21d-210">a.</span></span> <span data-ttu-id="8e21d-211">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="8e21d-211">Run the following command:</span></span> 
    
   ```
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```
    <span data-ttu-id="8e21d-212">b.</span><span class="sxs-lookup"><span data-stu-id="8e21d-212">b.</span></span> <span data-ttu-id="8e21d-213">Copie o arquivo “mypoolinfo.xml” no servidor que executa o Ouvinte.</span><span class="sxs-lookup"><span data-stu-id="8e21d-213">Copy the "mypoolinfo.xml" file to the server that runs the Listener.</span></span>
    
2. <span data-ttu-id="8e21d-214">No host que executa o Ouvinte:</span><span class="sxs-lookup"><span data-stu-id="8e21d-214">On the host that runs the Listener:</span></span>
    
   <span data-ttu-id="8e21d-215">a.</span><span class="sxs-lookup"><span data-stu-id="8e21d-215">a.</span></span> <span data-ttu-id="8e21d-216">Execute o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8e21d-216">Run PowerShell.</span></span>
    
   <span data-ttu-id="8e21d-217">b.</span><span class="sxs-lookup"><span data-stu-id="8e21d-217">b.</span></span> <span data-ttu-id="8e21d-218">Navegue até o diretório no qual o Ouvinte está instalado.</span><span class="sxs-lookup"><span data-stu-id="8e21d-218">Navigate to the directory on which the Listener is installed.</span></span> <span data-ttu-id="8e21d-219">O padrão é:</span><span class="sxs-lookup"><span data-stu-id="8e21d-219">The default is:</span></span> 
    
   ```
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

3. <span data-ttu-id="8e21d-220">Para confirmar quais servidores estão sendo adicionados e atualizados, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="8e21d-220">To confirm which servers are being added and updated, run the following command:</span></span>
    
   ```
    .\Update-StatsManServerInfo.ps1 -CsPoolFile  <path to mypoolinfo.xml>
   ```

<span data-ttu-id="8e21d-221">O seguinte comando permite ver todas as opções:</span><span class="sxs-lookup"><span data-stu-id="8e21d-221">The following command enables you to view all options:</span></span>
  
```
Get-Help .\Update-StatsManServerInfo.ps1 -Detailed 
```

<span data-ttu-id="8e21d-222">Para ver as informações que estão sendo importadas atualmente no seu servidor, execute o seguinte script:</span><span class="sxs-lookup"><span data-stu-id="8e21d-222">To see your currently imported server information, run the following script:</span></span> 
  
```
.\Get-StatsManServerInfo.ps1
```

<span data-ttu-id="8e21d-223">Se quiser monitorar servidores que não estão em sua topologia do Skype for Business Server--um Exchange Server, por exemplo--você pode fazer uma importação de um único servidor no host que executa o Ouvinte.</span><span class="sxs-lookup"><span data-stu-id="8e21d-223">If you would like to monitor servers that are not in your Skype for Business Server topology--an Exchange Server, for example--you can do a single-server import on the host that runs the Listener.</span></span> <span data-ttu-id="8e21d-224">Para fazer uma importação de um único servidor, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="8e21d-224">To do a single-server import, follow these steps:</span></span>
  
1. <span data-ttu-id="8e21d-225">Navegue até o diretório no qual o Ouvinte está instalado.</span><span class="sxs-lookup"><span data-stu-id="8e21d-225">Navigate to the directory on which the Listener is installed.</span></span> <span data-ttu-id="8e21d-226">O padrão é:</span><span class="sxs-lookup"><span data-stu-id="8e21d-226">The default is:</span></span> 
    
   ```
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

2. <span data-ttu-id="8e21d-227">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="8e21d-227">Run the following command:</span></span>
    
   ```
    .\Update-StatsManServerInfo.ps1 -HostName <hostname> -SiteName <name of site> -PoolName <poolName> -Roles <role1>[,<role2>,<roleN>]
   ```

## <a name="troubleshoot-your-deployment"></a><span data-ttu-id="8e21d-228">Solução de problemas de implantação</span><span class="sxs-lookup"><span data-stu-id="8e21d-228">Troubleshoot your deployment</span></span>
<span data-ttu-id="8e21d-229"><a name="BKMK_Troubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="8e21d-229"><a name="BKMK_Troubleshoot"> </a></span></span>

<span data-ttu-id="8e21d-230">Se ocorrer falha na inicialização de um Agente, verifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8e21d-230">If an Agent fails to start, check for the following:</span></span> 
  
- <span data-ttu-id="8e21d-231">O agente está registrado no Gerenciador de Estatísticas?</span><span class="sxs-lookup"><span data-stu-id="8e21d-231">Is the agent registered in Statistics Manager?</span></span>
    
1. <span data-ttu-id="8e21d-p129">	Certifique-se de seguir as instruções para importar a topologia. Veja [Importar a topologia](deploy.md#BKMK_ImportTopology).  </span><span class="sxs-lookup"><span data-stu-id="8e21d-p129">Make sure you followed the instructions for importing the topology. See [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
2. <span data-ttu-id="8e21d-234">Se o Agente estiver em um servidor que não está listado na topologia (por exemplo, os nós de um cluster SQL AlwaysOn), você precisará adicionar o Agente manualmente seguindo as instruções contidas em [Importar a topologia](deploy.md#BKMK_ImportTopology).</span><span class="sxs-lookup"><span data-stu-id="8e21d-234">If the Agent is on a server that is not listed in the topology (for example, the nodes in a SQL AlwaysOn cluster), you will need to add the Agent manually by following the instructions in [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
- <span data-ttu-id="8e21d-235">O Agente pode contatar o Ouvinte?</span><span class="sxs-lookup"><span data-stu-id="8e21d-235">Can the Agent contact the Listener?</span></span>
    
1. <span data-ttu-id="8e21d-236">Verifique se o serviço de escuta está em execução.</span><span class="sxs-lookup"><span data-stu-id="8e21d-236">Make sure the Listener service is running.</span></span> 
    
    <span data-ttu-id="8e21d-237">Se não estiver, verifique se o Redis está em execução e, em seguida, tente reiniciar o Ouvinte.</span><span class="sxs-lookup"><span data-stu-id="8e21d-237">If it is not running, make sure Redis is running, and then try to restart the Listener.</span></span>
    
2. <span data-ttu-id="8e21d-238">Verifique se a porta está aberta para o serviço de escuta, e se o computador do Agente consegue se comunicar com a porta.</span><span class="sxs-lookup"><span data-stu-id="8e21d-238">Make sure the port is open to the Listener service, and that the Agent computer can communicate with the port.</span></span>
    
- <span data-ttu-id="8e21d-239">Para garantir que o Gerenciador de Estatísticas esteja coletando dados, você pode verificar o arquivo CSV da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="8e21d-239">To ensure that Statistics Manager is collecting data, you can check the CSV file as follows.</span></span> 
    
    <span data-ttu-id="8e21d-240">O seguinte comando recupera os nomes de armazenamento do contador:</span><span class="sxs-lookup"><span data-stu-id="8e21d-240">The following command retrieves the counter storage names:</span></span> 
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    <span data-ttu-id="8e21d-241">O próximo comando recupera os valores dos contadores especificados:</span><span class="sxs-lookup"><span data-stu-id="8e21d-241">The next command retrieves the values for the specified counters:</span></span> 
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

<span data-ttu-id="8e21d-242">Para obter informações sobre todos os eventos que você talvez veja no log de eventos do aplicativo, consulte [Solução de Problemas do Gerenciador de Estatísticas do Skype for Business Server](troubleshoot.md).</span><span class="sxs-lookup"><span data-stu-id="8e21d-242">For information about all the events you might see in the application event log, see [Troubleshoot Statistics Manager for Skype for Business Server](troubleshoot.md).</span></span>
  
## <a name="create-a-self-signed-certificate"></a><span data-ttu-id="8e21d-243">Criar um certificado autoassinado</span><span class="sxs-lookup"><span data-stu-id="8e21d-243">Create a self-signed certificate</span></span>
<span data-ttu-id="8e21d-244"><a name="BKMK_SelfCert"> </a></span><span class="sxs-lookup"><span data-stu-id="8e21d-244"><a name="BKMK_SelfCert"> </a></span></span>

<span data-ttu-id="8e21d-245">A Microsoft recomenda que você use um certificado assinado por uma autoridade de certificação confiável.</span><span class="sxs-lookup"><span data-stu-id="8e21d-245">Microsoft strongly recommends that you use a certificate signed by a trusted certificate authority.</span></span> <span data-ttu-id="8e21d-246">No entanto, se quiser usar um certificado autoassinado para fins de teste, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8e21d-246">However, if you want to use a self-signed certificate for testing purposes, do the following:</span></span> 
  
1. <span data-ttu-id="8e21d-247">Conectado como Administrador em um console do PowerShell, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8e21d-247">From a PowerShell console while logged on as Administrator, type the following:</span></span>
    
   ```
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. <span data-ttu-id="8e21d-248">Tipo `certlm.msc`.</span><span class="sxs-lookup"><span data-stu-id="8e21d-248">Type  `certlm.msc`.</span></span> <span data-ttu-id="8e21d-249">Isso abrirá o Gerenciador de Certificados do computador local.</span><span class="sxs-lookup"><span data-stu-id="8e21d-249">This will open the Certificate Manager for the local machine.</span></span>
    
3. <span data-ttu-id="8e21d-250">Navegue até **Pessoal**e abra **Certificados**.</span><span class="sxs-lookup"><span data-stu-id="8e21d-250">Navigate to **Personal**, and then open **Certificates**.</span></span>
    
4. <span data-ttu-id="8e21d-251">Clique com botão direito do mouse em **StatsManListener –\>Todas as Tarefas-\>Gerenciar Chaves Privadas...**</span><span class="sxs-lookup"><span data-stu-id="8e21d-251">Right click on **StatsManListener-\>All Tasks-\>Manage Private Keys…**</span></span>
    
5. <span data-ttu-id="8e21d-252">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="8e21d-252">Click **Add**.</span></span>
    
6. <span data-ttu-id="8e21d-253">Na caixa **Digite os nomes de objeto a serem selecionados**, digite o seguinte: Serviço de Rede.</span><span class="sxs-lookup"><span data-stu-id="8e21d-253">In the **Enter the object names to select** box, type the following: Network Service</span></span>
    
7. <span data-ttu-id="8e21d-254">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="8e21d-254">Click **OK**.</span></span>
    
8. <span data-ttu-id="8e21d-p132">Em **Controle Total**, desmarque a caixa de seleção **Permitir**. (Apenas o acesso de leitura é necessário.)</span><span class="sxs-lookup"><span data-stu-id="8e21d-p132">Under **Full Control**, un-check the **Allow** check box. (Only Read access is necessary.)</span></span>
    
9. <span data-ttu-id="8e21d-257">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="8e21d-257">Click **OK**.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="8e21d-258">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="8e21d-258">For more information</span></span>
<span data-ttu-id="8e21d-259"><a name="BKMK_SelfCert"> </a></span><span class="sxs-lookup"><span data-stu-id="8e21d-259"><a name="BKMK_SelfCert"> </a></span></span>

<span data-ttu-id="8e21d-260">Para obter mais informações, consulte o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8e21d-260">For more information, see the following:</span></span>
  
- [<span data-ttu-id="8e21d-261">Planejar o Gerenciador de Estatísticas do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8e21d-261">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="8e21d-262">Atualizar o Gerenciador de Estatísticas do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8e21d-262">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)
    
- <span data-ttu-id="8e21d-263">[Solução de Problemas do Gerenciador de Estatísticas do Skype for Business Server](troubleshoot.md) ß</span><span class="sxs-lookup"><span data-stu-id="8e21d-263">[Troubleshoot Statistics Manager for Skype for Business Server](troubleshoot.md) ß</span></span>
