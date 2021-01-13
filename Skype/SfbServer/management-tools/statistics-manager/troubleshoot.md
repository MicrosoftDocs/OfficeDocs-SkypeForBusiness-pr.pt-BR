---
title: Solução de problemas do Gerenciador de Estatísticas do Skype for Business Server
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
ms.assetid: 946189fa-521f-455c-9762-904e7e41b791
description: 'Resumo: Leia este tópico para solucionar problemas de implantação do Gerenciador de Estatísticas do Skype for Business Server.'
ms.openlocfilehash: ea3d6f66003841e893ebe2dcc5d3fe02d0da125b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821771"
---
# <a name="troubleshoot-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="e53a3-103">Solução de problemas do Gerenciador de Estatísticas do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e53a3-103">Troubleshoot Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="e53a3-104">**Resumo:** Leia este tópico para solucionar problemas de implantação do Gerenciador de Estatísticas do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e53a3-104">**Summary:** Read this topic to troubleshoot your deployment of Statistics Manager for Skype for Business Server.</span></span>
  
<span data-ttu-id="e53a3-105">Este tópico descreve como solucionar problemas de implantação do Gerenciador de Estatísticas descrevendo os eventos que você pode ver no log de eventos do aplicativo e as ações apropriadas que você pode tomar para corrigir o evento.</span><span class="sxs-lookup"><span data-stu-id="e53a3-105">This topic describes how to troubleshoot your Statistics Manager deployment by describing events you might see in the application event log, and appropriate actions you might take to rectify the event.</span></span> <span data-ttu-id="e53a3-106">Este tópico contém as seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="e53a3-106">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="e53a3-107">Eventos de agente</span><span class="sxs-lookup"><span data-stu-id="e53a3-107">Agent events</span></span>](troubleshoot.md#BKMK_Agent)
    
- [<span data-ttu-id="e53a3-108">Eventos de ouvinte</span><span class="sxs-lookup"><span data-stu-id="e53a3-108">Listener events</span></span>](troubleshoot.md#BKMK_Listener)
    
- [<span data-ttu-id="e53a3-109">Problemas do site</span><span class="sxs-lookup"><span data-stu-id="e53a3-109">Website issues</span></span>](troubleshoot.md#BKMK_Website)
    
## <a name="agent-events"></a><span data-ttu-id="e53a3-110">Eventos de agente</span><span class="sxs-lookup"><span data-stu-id="e53a3-110">Agent events</span></span>
<span data-ttu-id="e53a3-111"><a name="BKMK_Agent"> </a></span><span class="sxs-lookup"><span data-stu-id="e53a3-111"><a name="BKMK_Agent"> </a></span></span>

- <span data-ttu-id="e53a3-112">**1000** — Não é possível configurar o limitador de processador (Objeto de Trabalho) — Motivo desconhecido</span><span class="sxs-lookup"><span data-stu-id="e53a3-112">**1000** — Unable to setup processor limiter (Job Object) — Unknown reason</span></span>
    
- <span data-ttu-id="e53a3-113">**1001** — A limitação do processo não é permitida no processo (provavelmente já está dentro de um Objeto de Trabalho)</span><span class="sxs-lookup"><span data-stu-id="e53a3-113">**1001** — Process limiting isn't allowed on the process (probably already inside a Job Object)</span></span>
    
    <span data-ttu-id="e53a3-114">O Agente é executado dentro de um Objeto de Trabalho do Windows para limitar automaticamente seu espaço de memória.</span><span class="sxs-lookup"><span data-stu-id="e53a3-114">The Agent runs inside of a Windows Job Object to automatically limit its memory footprint.</span></span> <span data-ttu-id="e53a3-115">Se o agente não for iniciar e essas entradas de evento estão presentes no log de eventos, o Objeto de Trabalho não pode ser instanciado no servidor.</span><span class="sxs-lookup"><span data-stu-id="e53a3-115">If the agent will not start and these event entries are present in the event log, the Job Object is not able to be instantiated on the server.</span></span> <span data-ttu-id="e53a3-116">Para resolver esse problema, o limite de memória superior pode ser removido alterando um valor no arquivo de configuração:</span><span class="sxs-lookup"><span data-stu-id="e53a3-116">To work around this, the upper memory limit can be removed by changing a value in the config file:</span></span>
    
  ```console
  C:\Program Files\Skype for Business Server StatsMan Agent\PerfAgent.exe.config
  ```

    <span data-ttu-id="e53a3-117">Procure "MaxProcessMemoryMB" e altere o valor para "0", conforme mostrado:</span><span class="sxs-lookup"><span data-stu-id="e53a3-117">Search for "MaxProcessMemoryMB" and change the value to "0" as shown:</span></span>
    
  ```xml
  <setting name="MaxProcessMemoryMB" serializeAs="String"> <value>300</value> </setting>
  ```

    > [!NOTE]
    > <span data-ttu-id="e53a3-118">Se essa alteração for feita, o Agente geralmente ainda consumirá 100 MB de memória, no entanto, ele não será limitado a 300 MB como é o \< padrão.</span><span class="sxs-lookup"><span data-stu-id="e53a3-118">If this change is made, the Agent will generally still consume \< 100 MB of memory, however it will not be forcefully limited to 300 MB as is the default.</span></span> <span data-ttu-id="e53a3-119">Se essa alteração for feita, recomendamos monitorar de perto o uso da memória para garantir que o Agente não consuma uma grande quantidade de memória em seu computador host.</span><span class="sxs-lookup"><span data-stu-id="e53a3-119">If this change is made, we recommend closely monitoring memory usage to ensure the Agent does not consume a large amount of memory on its host machine.</span></span> 
  
- <span data-ttu-id="e53a3-120">**2000** — Falha de inicialização do cliente</span><span class="sxs-lookup"><span data-stu-id="e53a3-120">**2000** — Client initialization failure</span></span>
    
- <span data-ttu-id="e53a3-121">**2001**— Nenhuma conexão pode ser feita com o serviço em qualquer IP de origem</span><span class="sxs-lookup"><span data-stu-id="e53a3-121">**2001**— No connection could be made to the service on any source IP</span></span>
    
    <span data-ttu-id="e53a3-122">Se o Agente não puder se conectar ao computador Ouvinte, verifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e53a3-122">If the Agent cannot connect to the Listener computer, check the following:</span></span>
    
    1. <span data-ttu-id="e53a3-123">Certifique-se de que o serviço ouvinte está em execução no computador ouvinte.</span><span class="sxs-lookup"><span data-stu-id="e53a3-123">Ensure the Listener service is running on the Listener computer.</span></span> <span data-ttu-id="e53a3-124">Se não estiver, verifique se o Redis está em execução no servidor e reinicie o serviço ouvinte.</span><span class="sxs-lookup"><span data-stu-id="e53a3-124">If not, ensure Redis is running on that server and then restart the Listener service.</span></span>
        
        <span data-ttu-id="e53a3-125">Verifique o log de eventos do Gerenciador de Estatísticas no computador Ouvinte para garantir que não haja problemas com o serviço Ouvinte do Gerenciador de Estatísticas em si.</span><span class="sxs-lookup"><span data-stu-id="e53a3-125">Check the Statistics Manager event log on the Listener computer to ensure there are no issues with the Statistics Manager Listener service itself.</span></span>
        
    2. <span data-ttu-id="e53a3-126">Use uma ferramenta de conectividade, como telnet, para verificar a conectividade do computador do Agente com o Ouvinte na porta correta.</span><span class="sxs-lookup"><span data-stu-id="e53a3-126">Use a connectivity tool such as telnet to verify connectivity from the Agent computer to the Listener on the correct port.</span></span>
        
        <span data-ttu-id="e53a3-127">Caso não esteja, certifique-se de que a regra de firewall de entrada esteja habilitada no computador Ouvinte para o tipo de rede ao qual o computador Ouvinte está conectado (privado/público/domínio).</span><span class="sxs-lookup"><span data-stu-id="e53a3-127">If not, make sure the incoming firewall rule is enabled on the Listener computer for the network type that the Listener computer is connected to (private/public/domain).</span></span> <span data-ttu-id="e53a3-128">Se o computador Ouvinte não for ingressado em um domínio, a rede poderá ser listada como pública e, nesse caso, as regras de firewall instaladas com o Gerenciador de Estatísticas não serão aplicadas por padrão.</span><span class="sxs-lookup"><span data-stu-id="e53a3-128">If the Listener computer is not joined to a domain, the network may be listed as public and in that case the firewall rules installed with Statistics Manager will not apply by default.</span></span>
    
- <span data-ttu-id="e53a3-129">**4000** — Falha ao baixar informações do servidor do Ouvinte (motivo desconhecido)</span><span class="sxs-lookup"><span data-stu-id="e53a3-129">**4000** — Failure to download Server Info from Listener (unknown reason)</span></span>
    
  - <span data-ttu-id="e53a3-130">**4001** — Servidor não encontrado na topologia do ouvinte</span><span class="sxs-lookup"><span data-stu-id="e53a3-130">**4001** — Server Not Found in Listener Topology</span></span>
    
    <span data-ttu-id="e53a3-131">Esse erro ocorrerá se o servidor estiver se conectando com êxito ao Ouvinte, mas o servidor não foi adicionado à topologia no cache do Ouvinte.</span><span class="sxs-lookup"><span data-stu-id="e53a3-131">This error will occur if the server is successfully connecting to the Listener, but the server was not added to the topology in the Listener's cache.</span></span> <span data-ttu-id="e53a3-132">Opções de resolução:</span><span class="sxs-lookup"><span data-stu-id="e53a3-132">Resolution options:</span></span>
    
  - <span data-ttu-id="e53a3-133">Certifique-se de seguir as instruções para importar a topologia.</span><span class="sxs-lookup"><span data-stu-id="e53a3-133">Make sure you followed the instructions for importing the topology.</span></span> <span data-ttu-id="e53a3-134">Consulte [Importar a topologia.](deploy.md#BKMK_ImportTopology)</span><span class="sxs-lookup"><span data-stu-id="e53a3-134">See [Import the topology](deploy.md#BKMK_ImportTopology).</span></span> 
    
  - <span data-ttu-id="e53a3-135">Se o Agente estiver em um servidor que não está listado na topologia (por exemplo, os nós em um cluster SQL AlwaysOn), você precisará adicionar o Agente manualmente seguindo as instruções em Importar a [topologia.](deploy.md#BKMK_ImportTopology)</span><span class="sxs-lookup"><span data-stu-id="e53a3-135">If the Agent is on a server that is not listed in the topology (for example, the nodes in a SQL AlwaysOn cluster), you will need to add the Agent manually by following the instructions in [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
  - <span data-ttu-id="e53a3-136">**4002** — Senha de Ouvinte Inválida</span><span class="sxs-lookup"><span data-stu-id="e53a3-136">**4002** — Invalid Listener Password</span></span>
    
    <span data-ttu-id="e53a3-137">A senha criptografada que o agente está tentando usar não combina com a senha de serviço no Ouvinte em si.</span><span class="sxs-lookup"><span data-stu-id="e53a3-137">The encrypted password that the agent is attempting to use does not match the service password on the Listener itself.</span></span> <span data-ttu-id="e53a3-138">Desinstale o Agente e reinstale-o usando a senha de serviço correta.</span><span class="sxs-lookup"><span data-stu-id="e53a3-138">Uninstall the Agent and re-install it using the correct service password.</span></span>
    
  - <span data-ttu-id="e53a3-139">**4003** — Incompatibilidade de impressão digital do certificado</span><span class="sxs-lookup"><span data-stu-id="e53a3-139">**4003** — Certificate Thumbprint Mismatch</span></span>
    
    <span data-ttu-id="e53a3-140">A impressão digital do certificado dada ao Agente no momento da instalação não combina com a impressão digital no certificado que o Ouvinte está usando no momento e, portanto, a conexão será recusada.</span><span class="sxs-lookup"><span data-stu-id="e53a3-140">The certificate thumbprint given to the Agent at install time does not match the thumbprint on the certificate the Listener is currently using and therefore the connection will be refused.</span></span> <span data-ttu-id="e53a3-141">Desinstale o Agente e reinstale-o usando a impressão digital correta do certificado.</span><span class="sxs-lookup"><span data-stu-id="e53a3-141">Uninstall the Agent and re-install it using the correct certificate thumbprint.</span></span>
    
  - <span data-ttu-id="e53a3-142">**4004** — Resposta inválida ou HttpStatusCode</span><span class="sxs-lookup"><span data-stu-id="e53a3-142">**4004** — Invalid Response or HttpStatusCode</span></span>
    
    <span data-ttu-id="e53a3-143">O Ouvinte não está respondendo com um status esperado.</span><span class="sxs-lookup"><span data-stu-id="e53a3-143">The Listener is not responding with an expected status.</span></span> 
    
  - <span data-ttu-id="e53a3-144">Se a conexão for proxy, verifique a configuração do proxy.</span><span class="sxs-lookup"><span data-stu-id="e53a3-144">If the connection is proxied, check the proxy configuration.</span></span>
    
  - <span data-ttu-id="e53a3-145">Verifique o log statsMan do computador ouvinte em busca de problemas com sua configuração.</span><span class="sxs-lookup"><span data-stu-id="e53a3-145">Check the Listener computer's StatsMan log for issues with its configuration.</span></span>
    
  - <span data-ttu-id="e53a3-146">**4005** — Não foi preciso des serializar o XML</span><span class="sxs-lookup"><span data-stu-id="e53a3-146">**4005** — Couldn't de-serialize the XML</span></span>
    
    <span data-ttu-id="e53a3-147">As informações do servidor no servidor Ouvinte estão corrompidas ou pode haver uma incompatibilidade de versão entre o Agente e os computadores ouvintes.</span><span class="sxs-lookup"><span data-stu-id="e53a3-147">The server info on the Listener server is corrupt or there may be a version mismatch between the Agent and the Listener computers.</span></span> <span data-ttu-id="e53a3-148">Verifique se as versões corresponderam e verifique se há problemas no log de eventos do Ouvinte.</span><span class="sxs-lookup"><span data-stu-id="e53a3-148">Ensure the versions match and check the Listener event log for issues.</span></span>
    
## <a name="listener-events"></a><span data-ttu-id="e53a3-149">Eventos de ouvinte</span><span class="sxs-lookup"><span data-stu-id="e53a3-149">Listener events</span></span>
<span data-ttu-id="e53a3-150"><a name="BKMK_Listener"> </a></span><span class="sxs-lookup"><span data-stu-id="e53a3-150"><a name="BKMK_Listener"> </a></span></span>

- <span data-ttu-id="e53a3-151">**10000** — Falha de inicialização Motivo desconhecido (eles são irrecuperáveis e o serviço irá parar/falhar como resultado)</span><span class="sxs-lookup"><span data-stu-id="e53a3-151">**10000** — Startup failure Unknown reason (these are unrecoverable and the service will stop/crash as a result)</span></span>
    
  - <span data-ttu-id="e53a3-152">**10001** — Problema de configuração</span><span class="sxs-lookup"><span data-stu-id="e53a3-152">**10001** — Configuration problem</span></span>
    
    <span data-ttu-id="e53a3-153">Geralmente, isso ocorrerá quando o arquivo [listener_install_location]\PerfAgentListener.exe.config tiver sido modificado manualmente e não puder ser lido pelo aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e53a3-153">Generally this will occur when the [listener_install_location]\PerfAgentListener.exe.config file has been modified by hand and cannot be read by the application.</span></span>
    
  - <span data-ttu-id="e53a3-154">**10002** — Erro de inicialização do Ouvinte HTTP</span><span class="sxs-lookup"><span data-stu-id="e53a3-154">**10002** — HTTP Listener initialization error</span></span>
    
    <span data-ttu-id="e53a3-155">Esse evento geralmente será registrado quando a ACL da URL não tiver sido definida corretamente durante a instalação ou o Certificado SSL for inválido.</span><span class="sxs-lookup"><span data-stu-id="e53a3-155">This event will generally be logged when the URL ACL has not been set properly during installation or the SSL Cert is invalid.</span></span> <span data-ttu-id="e53a3-156">Verifique se o certificado em sua configuração é válido.</span><span class="sxs-lookup"><span data-stu-id="e53a3-156">Ensure the certificate in your configuration is valid.</span></span> <span data-ttu-id="e53a3-157">Se estiver, reinstale o Ouvinte de acordo com as instruções em [Implantar o Gerenciador de Estatísticas.](deploy.md#BKMK_Deploy)</span><span class="sxs-lookup"><span data-stu-id="e53a3-157">If it is, reinstall the Listener according to the instructions in [Deploy Statistics Manager](deploy.md#BKMK_Deploy).</span></span>
    
  - <span data-ttu-id="e53a3-158">**10003** — Falha do Redis</span><span class="sxs-lookup"><span data-stu-id="e53a3-158">**10003** — Redis failure</span></span>
    
  - <span data-ttu-id="e53a3-159">**10004** — Falha na infraestrutura de cache</span><span class="sxs-lookup"><span data-stu-id="e53a3-159">**10004** — Caching infrastructure failure</span></span>
    
  - <span data-ttu-id="e53a3-160">**10007** – Configurações (armazenadas em redis)</span><span class="sxs-lookup"><span data-stu-id="e53a3-160">**10007** — Settings (stored in redis)</span></span>
    
    <span data-ttu-id="e53a3-161">O Ouvinte não pôde contatar o Redis ou recuperar dados bem formados do cache e não pôde iniciar.</span><span class="sxs-lookup"><span data-stu-id="e53a3-161">The Listener could not contact Redis or retrieve well-formed data from the cache and could not start.</span></span> <span data-ttu-id="e53a3-162">Verifique se o serviço Redis foi iniciado e configurado corretamente no servidor.</span><span class="sxs-lookup"><span data-stu-id="e53a3-162">Ensure the Redis service is started and configured properly on the server.</span></span>
    
  - <span data-ttu-id="e53a3-163">**10005** — Recuperação/análise de informações do servidor</span><span class="sxs-lookup"><span data-stu-id="e53a3-163">**10005** — Server info retrieval/parsing</span></span>
    
    <span data-ttu-id="e53a3-164">As informações de topologia no cache redis são inválidas.</span><span class="sxs-lookup"><span data-stu-id="e53a3-164">The topology information in the Redis cache is invalid.</span></span> <span data-ttu-id="e53a3-165">Primeiro, tente reiniciar o Redis e o Ouvinte.</span><span class="sxs-lookup"><span data-stu-id="e53a3-165">First, attempt to restart Redis and the Listener.</span></span> <span data-ttu-id="e53a3-166">Se o erro persistir, consulte [Importar a topologia para](deploy.md#BKMK_ImportTopology) recriar os dados de topologia.</span><span class="sxs-lookup"><span data-stu-id="e53a3-166">If the error persists, see [Import the topology](deploy.md#BKMK_ImportTopology) to recreate the topology data.</span></span>
    
- <span data-ttu-id="e53a3-167">**10100** - Paralisação de PING do Redis</span><span class="sxs-lookup"><span data-stu-id="e53a3-167">**10100** — Redis PING outage</span></span>
    
  - <span data-ttu-id="e53a3-168">**10101** - Continuação da paralisação do PING do Redis (a cada 60 segundos)</span><span class="sxs-lookup"><span data-stu-id="e53a3-168">**10101** — Redis PING continued outage (every 60 seconds)</span></span>
    
  - <span data-ttu-id="e53a3-169">**30100** — Paralisação de PING do Redis restaurada</span><span class="sxs-lookup"><span data-stu-id="e53a3-169">**30100** — Redis PING outage restored</span></span>
    
    <span data-ttu-id="e53a3-170">Eles serão registrados quando o Ouvinte não puder se conectar ao Redis.</span><span class="sxs-lookup"><span data-stu-id="e53a3-170">These will be logged when the Listener cannot connect to Redis.</span></span> <span data-ttu-id="e53a3-171">Verifique se o Redis foi iniciado e se a conectividade de rede entre o Ouvinte e o Redis está disponível.</span><span class="sxs-lookup"><span data-stu-id="e53a3-171">Ensure Redis is started and network connectivity between the Listener and Redis is available.</span></span>
    
- <span data-ttu-id="e53a3-172">**10200** - Redis Write outage</span><span class="sxs-lookup"><span data-stu-id="e53a3-172">**10200** — Redis Write outage</span></span>
    
  - <span data-ttu-id="e53a3-173">**10201** — Continuação da indisistção de gravação do Redis (a cada 60 segundos)</span><span class="sxs-lookup"><span data-stu-id="e53a3-173">**10201** — Redis Write outage continued (every 60 seconds)</span></span>
    
  - <span data-ttu-id="e53a3-174">**30100** — Redis Write outage resolved</span><span class="sxs-lookup"><span data-stu-id="e53a3-174">**30100** — Redis Write outage resolved</span></span>
    
    <span data-ttu-id="e53a3-175">Eles serão registrados quando o Ouvinte não puder gravar no cache do Redis.</span><span class="sxs-lookup"><span data-stu-id="e53a3-175">These will be logged when the Listener cannot write to the Redis cache.</span></span> <span data-ttu-id="e53a3-176">Verifique se o Redis foi iniciado e se a conectividade de rede entre o Ouvinte e o Redis está disponível.</span><span class="sxs-lookup"><span data-stu-id="e53a3-176">Ensure Redis is started and network connectivity between the Listener and Redis is available.</span></span>
    
- <span data-ttu-id="e53a3-177">**30000** – Iniciado com êxito</span><span class="sxs-lookup"><span data-stu-id="e53a3-177">**30000** — Successfully started</span></span>
    
    <span data-ttu-id="e53a3-178">Registrado sempre que o Ouvinte é iniciado.</span><span class="sxs-lookup"><span data-stu-id="e53a3-178">Logged each time the Listener is started.</span></span>
    
- <span data-ttu-id="e53a3-179">**22000** – Inicialização bem-sucedida do Agente do Gerenciador de Estatísticas.</span><span class="sxs-lookup"><span data-stu-id="e53a3-179">**22000** — Initialization of Statistics Manager Agent succeeded.</span></span>
    
- <span data-ttu-id="e53a3-180">**23000** — Inicialização bem-sucedida do EventLogQueryManager (primeira vez ou após falha)</span><span class="sxs-lookup"><span data-stu-id="e53a3-180">**23000** — Initialization of EventLogQueryManager succeeded (first time or after failing)</span></span>
    
- <span data-ttu-id="e53a3-181">**24000** — Inicialização bem-sucedida de serverinfo (primeira vez ou após falha)</span><span class="sxs-lookup"><span data-stu-id="e53a3-181">**24000** — Initialization of serverinfo succeeded (first time or after failing)</span></span>
    
- <span data-ttu-id="e53a3-182">**25000** — O Ouvinte está novamente online após uma falha ao postar (ou primeira postagem bem-sucedida)</span><span class="sxs-lookup"><span data-stu-id="e53a3-182">**25000** — Listener is back online after failing to post (or first successful post)</span></span>
    
- <span data-ttu-id="e53a3-183">**5000** — Início do ouvinte offline para postar dados</span><span class="sxs-lookup"><span data-stu-id="e53a3-183">**5000** — Start of listener offline for posting data</span></span>
    
- <span data-ttu-id="e53a3-184">**5001** — O Ouvinte ainda está offline por um longo período</span><span class="sxs-lookup"><span data-stu-id="e53a3-184">**5001** — Listener is still offline for an extended period</span></span>
    
    <span data-ttu-id="e53a3-185">Esses eventos podem ser úteis para monitorar/alertar/limpar problemas.</span><span class="sxs-lookup"><span data-stu-id="e53a3-185">These events can be useful for monitoring/alerting/clearing issues.</span></span>
    
## <a name="website-issues"></a><span data-ttu-id="e53a3-186">Problemas do site</span><span class="sxs-lookup"><span data-stu-id="e53a3-186">Website issues</span></span>
<span data-ttu-id="e53a3-187"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="e53a3-187"><a name="BKMK_Website"> </a></span></span>

- <span data-ttu-id="e53a3-188">Prompts de logon repetitivos no Chrome – um bug que foi resolvido na versão 1.1.</span><span class="sxs-lookup"><span data-stu-id="e53a3-188">Repetitive login prompts in Chrome - this was a bug that has been resolved in version 1.1.</span></span> <span data-ttu-id="e53a3-189">Certifique-se de ter atualizado para a versão mais recente do Gerenciador de Estatísticas se estiver vendo prompts de logon repetidos no navegador Chrome.</span><span class="sxs-lookup"><span data-stu-id="e53a3-189">Be sure you have upgraded to the latest version of Statistics Manager if you are seeing repeated login prompts in the Chrome browser.</span></span> <span data-ttu-id="e53a3-190">Para verificar a versão do site que você está executando:</span><span class="sxs-lookup"><span data-stu-id="e53a3-190">To verify the version of the website you are running:</span></span>
    
  - <span data-ttu-id="e53a3-191">No Explorador de Arquivos, abra (diretório padrão)</span><span class="sxs-lookup"><span data-stu-id="e53a3-191">In File Explorer, open (default directory)</span></span>
    
  - <span data-ttu-id="e53a3-192">Clique com o botão direito do StatsManHubWebSite.dll e veja suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="e53a3-192">Right click on StatsManHubWebSite.dll and view its properties.</span></span>
    
  - <span data-ttu-id="e53a3-193">Se não for possível encontrar um computador na exibição Paisagem de KHI ou no de Detalhes do Contador, certifique-se de que ele seja membro de um Site e de um Pool.</span><span class="sxs-lookup"><span data-stu-id="e53a3-193">If a computer cannot be found in the KHI Landscape view or the Counter Details view, make sure it is a member of a Site and a Pool.</span></span> <span data-ttu-id="e53a3-194">Se não estiver, ele não aparecerá nesses exibições.</span><span class="sxs-lookup"><span data-stu-id="e53a3-194">If it is not, it will not appear in those views.</span></span> <span data-ttu-id="e53a3-195">Para obter informações sobre como definir um site e pool para um servidor na topologia, consulte [Importar a topologia.](deploy.md#BKMK_ImportTopology)</span><span class="sxs-lookup"><span data-stu-id="e53a3-195">For information about defining a site and pool for a server in the topology, see [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
  - <span data-ttu-id="e53a3-196">A versão do produto será mostrada nos detalhes de Descrição.</span><span class="sxs-lookup"><span data-stu-id="e53a3-196">The product version will be shown in the Description details.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="e53a3-197">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="e53a3-197">For more information</span></span>
<span data-ttu-id="e53a3-198"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="e53a3-198"><a name="BKMK_Website"> </a></span></span>

<span data-ttu-id="e53a3-199">Para obter mais informações, confira o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e53a3-199">For more information, see the following:</span></span>
  
- [<span data-ttu-id="e53a3-200">Planejar o Gerenciador de estatísticas do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e53a3-200">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="e53a3-201">Implantar o Gerenciador de estatísticas do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e53a3-201">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)
    
- [<span data-ttu-id="e53a3-202">Atualizar o Gerenciador de estatísticas do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e53a3-202">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)
