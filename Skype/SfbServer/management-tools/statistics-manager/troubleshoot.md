---
title: Solucionar problemas de gerente de estatísticas para Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 946189fa-521f-455c-9762-904e7e41b791
description: 'Resumo: Leia este tópico para solucionar problemas de sua implantação do Gerenciador de estatísticas para Skype para Business Server.'
ms.openlocfilehash: 3a0bb2530e0b19685f28a747660e59b1fceec4e8
ms.sourcegitcommit: 8536a34cb13d40b30f84d95e6df10542ef85c36d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26292980"
---
# <a name="troubleshoot-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="7dfc8-103">Solucionar problemas de gerente de estatísticas para Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="7dfc8-103">Troubleshoot Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="7dfc8-104">**Resumo:** Leia este tópico para solucionar problemas de sua implantação do Gerenciador de estatísticas para Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="7dfc8-104">**Summary:** Read this topic to troubleshoot your deployment of Statistics Manager for Skype for Business Server.</span></span>
  
<span data-ttu-id="7dfc8-105">Este tópico descreve como solucionar problemas de sua implantação do Gerenciador de estatísticas descrevendo os eventos que talvez você veja no log de eventos do aplicativo e ações apropriadas, que você pode tomar para resolver o evento.</span><span class="sxs-lookup"><span data-stu-id="7dfc8-105">This topic describes how to troubleshoot your Statistics Manager deployment by describing events you might see in the application event log, and appropriate actions you might take to rectify the event.</span></span> <span data-ttu-id="7dfc8-106">Este tópico contém as seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="7dfc8-106">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="7dfc8-107">Eventos do Agente</span><span class="sxs-lookup"><span data-stu-id="7dfc8-107">Agent events</span></span>](troubleshoot.md#BKMK_Agent)
    
- [<span data-ttu-id="7dfc8-108">Eventos do Ouvinte</span><span class="sxs-lookup"><span data-stu-id="7dfc8-108">Listener events</span></span>](troubleshoot.md#BKMK_Listener)
    
- [<span data-ttu-id="7dfc8-109">Problemas de site da Web</span><span class="sxs-lookup"><span data-stu-id="7dfc8-109">Website issues</span></span>](troubleshoot.md#BKMK_Website)
    
## <a name="agent-events"></a><span data-ttu-id="7dfc8-110">Eventos do Agente</span><span class="sxs-lookup"><span data-stu-id="7dfc8-110">Agent events</span></span>
<span data-ttu-id="7dfc8-111"><a name="BKMK_Agent"> </a></span><span class="sxs-lookup"><span data-stu-id="7dfc8-111"></span></span>

- <span data-ttu-id="7dfc8-112">**1000** - Não é possível instalar o limitador do processador (Objeto de trabalho) - Motivo desconhecido</span><span class="sxs-lookup"><span data-stu-id="7dfc8-112">**1000** — Unable to setup processor limiter (Job Object) — Unknown reason</span></span>
    
- <span data-ttu-id="7dfc8-113">**1001** — limitando o processo não é permitida no processo (provavelmente já dentro de um objeto de trabalho)</span><span class="sxs-lookup"><span data-stu-id="7dfc8-113">**1001** — Process limiting isn't allowed on the process (probably already inside a Job Object)</span></span>
    
    <span data-ttu-id="7dfc8-114">O Agente é executado dentro de um Objeto de trabalho do Windows que limita automaticamente seu volume de memória.</span><span class="sxs-lookup"><span data-stu-id="7dfc8-114">The Agent runs inside of a Windows Job Object to automatically limit its memory footprint.</span></span> <span data-ttu-id="7dfc8-115">Se o agente não for iniciado e essas entradas de evento estiverem presentes no log de eventos, o Objeto de trabalho não consegue ser instanciado no servidor.</span><span class="sxs-lookup"><span data-stu-id="7dfc8-115">If the agent will not start and these event entries are present in the event log, the Job Object is not able to be instantiated on the server.</span></span> <span data-ttu-id="7dfc8-116">Para contornar o problema, o limite de memória superior pode ser removido com a alteração de um valor no arquivo de configurações:</span><span class="sxs-lookup"><span data-stu-id="7dfc8-116">To work around this, the upper memory limit can be removed by changing a value in the config file:</span></span>
    
  ```
  C:\Program Files\Skype for Business Server StatsMan Agent\PerfAgent.exe.config
  ```

    <span data-ttu-id="7dfc8-117">Procure "MaxProcessMemoryMB" e altere o valor para "0", conforme mostrado:</span><span class="sxs-lookup"><span data-stu-id="7dfc8-117">Search for "MaxProcessMemoryMB" and change the value to "0" as shown:</span></span>
    
  ```
  <setting name="MaxProcessMemoryMB" serializeAs="String"> <value>300</value> </setting>
  ```

    > [!NOTE]
    > <span data-ttu-id="7dfc8-118">Se essa alteração é feita, o agente geralmente ainda consumirá \< 100 MB de memória, porém não será forçada limitado a 300 MB conforme é o padrão.</span><span class="sxs-lookup"><span data-stu-id="7dfc8-118">If this change is made, the Agent will generally still consume \< 100 MB of memory, however it will not be forcefully limited to 300 MB as is the default.</span></span> <span data-ttu-id="7dfc8-119">Se essa alteração for feita, recomendamos monitorar de perto uso de memória para garantir que o Agente não consuma uma grande quantidade de memória na máquina do host.</span><span class="sxs-lookup"><span data-stu-id="7dfc8-119">If this change is made, we recommend closely monitoring memory usage to ensure the Agent does not consume a large amount of memory on its host machine.</span></span> 
  
- <span data-ttu-id="7dfc8-120">**2000** - Falha na inicialização do cliente</span><span class="sxs-lookup"><span data-stu-id="7dfc8-120">**2000** — Client initialization failure</span></span>
    
- <span data-ttu-id="7dfc8-121">**2001** - Não foi possível se conectar com o serviço em qualquer IP de origem</span><span class="sxs-lookup"><span data-stu-id="7dfc8-121">**2001**— No connection could be made to the service on any source IP</span></span>
    
    <span data-ttu-id="7dfc8-122">Se o Agente não puder se conectar ao computador Ouvinte, verifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7dfc8-122">If the Agent cannot connect to the Listener computer, check the following:</span></span>
    
1. <span data-ttu-id="7dfc8-123">Certifique-se de que o serviço Ouvinte está em execução no computador Ouvinte.</span><span class="sxs-lookup"><span data-stu-id="7dfc8-123">Ensure the Listener service is running on the Listener computer.</span></span> <span data-ttu-id="7dfc8-124">Se não estiver, certifique-se de que o Redis está sendo executado no servidor e reinicie o serviço Ouvinte.</span><span class="sxs-lookup"><span data-stu-id="7dfc8-124">If not, ensure Redis is running on that server and then restart the Listener service.</span></span>
    
    <span data-ttu-id="7dfc8-125">Verifique o log de eventos do Gerenciador de estatísticas no computador ouvinte para garantir que não existem problemas com o serviço de Gerenciador de estatísticas ouvinte em si.</span><span class="sxs-lookup"><span data-stu-id="7dfc8-125">Check the Statistics Manager event log on the Listener computer to ensure there are no issues with the Statistics Manager Listener service itself.</span></span>
    
2. <span data-ttu-id="7dfc8-126">Use uma ferramenta de conectividade, como telnet, para verificar a conectividade do computador do Agente ao do Ouvinte na porta correta.</span><span class="sxs-lookup"><span data-stu-id="7dfc8-126">Use a connectivity tool such as telnet to verify connectivity from the Agent computer to the Listener on the correct port.</span></span>
    
    <span data-ttu-id="7dfc8-127">Caso contrário, verifique se a regra de firewall de entrada está habilitada no computador Ouvinte para o tipo de rede ao qual esse computador está conectado (público/privado/domínio).</span><span class="sxs-lookup"><span data-stu-id="7dfc8-127">If not, make sure the incoming firewall rule is enabled on the Listener computer for the network type that the Listener computer is connected to (private/public/domain).</span></span> <span data-ttu-id="7dfc8-128">Se o computador de ouvinte não está vinculado a um domínio, a rede pode estar listada como pública e nesse caso, as regras de firewall instaladas com o Gerenciador de estatísticas não serão aplicadas por padrão.</span><span class="sxs-lookup"><span data-stu-id="7dfc8-128">If the Listener computer is not joined to a domain, the network may be listed as public and in that case the firewall rules installed with Statistics Manager will not apply by default.</span></span>
    
- <span data-ttu-id="7dfc8-129">**4000** - Falha para no download das Informações do servidor do Ouvinte (Motivo desconhecido)</span><span class="sxs-lookup"><span data-stu-id="7dfc8-129">**4000** — Failure to download Server Info from Listener (unknown reason)</span></span>
    
  - <span data-ttu-id="7dfc8-130">**4001** - Servidor não encontrado na topologia do Ouvinte</span><span class="sxs-lookup"><span data-stu-id="7dfc8-130">**4001** — Server Not Found in Listener Topology</span></span>
    
    <span data-ttu-id="7dfc8-131">Este erro ocorrerá se o servidor com êxito a conexão ao ouvinte, mas o servidor não foi adicionado à topologia no cache do ouvinte.</span><span class="sxs-lookup"><span data-stu-id="7dfc8-131">This error will occur if the server is successfully connecting to the Listener, but the server was not added to the topology in the Listener's cache.</span></span> <span data-ttu-id="7dfc8-132">Opções de solução:</span><span class="sxs-lookup"><span data-stu-id="7dfc8-132">Resolution options:</span></span>
    
  - <span data-ttu-id="7dfc8-p107">	Certifique-se de seguir as instruções para importar a topologia. Veja [Importar a topologia](deploy.md#BKMK_ImportTopology).  </span><span class="sxs-lookup"><span data-stu-id="7dfc8-p107">Make sure you followed the instructions for importing the topology. See [Import the topology](deploy.md#BKMK_ImportTopology).</span></span> 
    
  - <span data-ttu-id="7dfc8-135">Se o Agente estiver em um servidor que não está listado na topologia (por exemplo, os nós de um cluster SQL AlwaysOn), você precisará adicionar o Agente manualmente seguindo as instruções contidas em [Importar a topologia](deploy.md#BKMK_ImportTopology).</span><span class="sxs-lookup"><span data-stu-id="7dfc8-135">If the Agent is on a server that is not listed in the topology (for example, the nodes in a SQL AlwaysOn cluster), you will need to add the Agent manually by following the instructions in [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
  - <span data-ttu-id="7dfc8-136">**4002** - Senha do Ouvinte inválida</span><span class="sxs-lookup"><span data-stu-id="7dfc8-136">**4002** — Invalid Listener Password</span></span>
    
    <span data-ttu-id="7dfc8-137">A senha codificada que o agente esteja tentando usar não corresponde à senha de serviço no Ouvinte.</span><span class="sxs-lookup"><span data-stu-id="7dfc8-137">The encrypted password that the agent is attempting to use does not match the service password on the Listener itself.</span></span> <span data-ttu-id="7dfc8-138">Desinstale o Agente e volte a instalá-lo usando a senha de serviço correta.</span><span class="sxs-lookup"><span data-stu-id="7dfc8-138">Uninstall the Agent and re-install it using the correct service password.</span></span>
    
  - <span data-ttu-id="7dfc8-139">**4003** - Incompatibilidade de impressão digital do certificado</span><span class="sxs-lookup"><span data-stu-id="7dfc8-139">**4003** — Certificate Thumbprint Mismatch</span></span>
    
    <span data-ttu-id="7dfc8-140">A impressão digital do certificado dada ao Agente durante a instalação não corresponde à impressão digital no certificado que o Ouvinte está usando no momento e, portanto, a conexão será recusada.</span><span class="sxs-lookup"><span data-stu-id="7dfc8-140">The certificate thumbprint given to the Agent at install time does not match the thumbprint on the certificate the Listener is currently using and therefore the connection will be refused.</span></span> <span data-ttu-id="7dfc8-141">Desinstale o Agente e volte a instalá-lo usando a impressão digital do certificado correta.</span><span class="sxs-lookup"><span data-stu-id="7dfc8-141">Uninstall the Agent and re-install it using the correct certificate thumbprint.</span></span>
    
  - <span data-ttu-id="7dfc8-142">**4004** - Resposta inválida ou HttpStatusCode</span><span class="sxs-lookup"><span data-stu-id="7dfc8-142">**4004** — Invalid Response or HttpStatusCode</span></span>
    
    <span data-ttu-id="7dfc8-143">O Ouvinte não está respondendo com um status esperado.  </span><span class="sxs-lookup"><span data-stu-id="7dfc8-143">The Listener is not responding with an expected status.</span></span> 
    
  - <span data-ttu-id="7dfc8-144">Se a conexão for em proxy, marque a configuração de proxy.</span><span class="sxs-lookup"><span data-stu-id="7dfc8-144">If the connection is proxied, check the proxy configuration.</span></span>
    
  - <span data-ttu-id="7dfc8-145">Verifique se log de StatsMan do computador ouvinte para problemas com sua configuração.</span><span class="sxs-lookup"><span data-stu-id="7dfc8-145">Check the Listener computer's StatsMan log for issues with its configuration.</span></span>
    
  - <span data-ttu-id="7dfc8-146">**4005** - Não foi possível desserializar o XML</span><span class="sxs-lookup"><span data-stu-id="7dfc8-146">**4005** — Couldn't de-serialize the XML</span></span>
    
    <span data-ttu-id="7dfc8-147">As informações no servidor do Ouvinte estão corrompidas ou pode haver uma incompatibilidade de versões entre os computadores do Agente e do Ouvinte.</span><span class="sxs-lookup"><span data-stu-id="7dfc8-147">The server info on the Listener server is corrupt or there may be a version mismatch between the Agent and the Listener computers.</span></span> <span data-ttu-id="7dfc8-148">Certifique-se de que as versões são as mesmas e verifique o log de eventos do Ouvinte em busca de problemas.</span><span class="sxs-lookup"><span data-stu-id="7dfc8-148">Ensure the versions match and check the Listener event log for issues.</span></span>
    
## <a name="listener-events"></a><span data-ttu-id="7dfc8-149">Eventos do Ouvinte</span><span class="sxs-lookup"><span data-stu-id="7dfc8-149">Listener events</span></span>
<span data-ttu-id="7dfc8-150"><a name="BKMK_Listener"> </a></span><span class="sxs-lookup"><span data-stu-id="7dfc8-150"></span></span>

- <span data-ttu-id="7dfc8-151">**10000** - Falha na inicialização Motivo desconhecido (são irrecuperáveis, e o serviço será interrompido/falhará como resultado)</span><span class="sxs-lookup"><span data-stu-id="7dfc8-151">**10000** — Startup failure Unknown reason (these are unrecoverable and the service will stop/crash as a result)</span></span>
    
  - <span data-ttu-id="7dfc8-152">**10001** - Problema de configuração</span><span class="sxs-lookup"><span data-stu-id="7dfc8-152">**10001** — Configuration problem</span></span>
    
    <span data-ttu-id="7dfc8-153">Isso geralmente ocorre quando o arquivo [listener_install_location]\PerfAgentListener.exe.config foi modificado manualmente e não pode ser lido pelo aplicativo.</span><span class="sxs-lookup"><span data-stu-id="7dfc8-153">Generally this will occur when the [listener_install_location]\PerfAgentListener.exe.config file has been modified by hand and cannot be read by the application.</span></span>
    
  - <span data-ttu-id="7dfc8-154">**10002** - Erro de inicialização do Ouvinte do HTTP</span><span class="sxs-lookup"><span data-stu-id="7dfc8-154">**10002** — HTTP Listener initialization error</span></span>
    
    <span data-ttu-id="7dfc8-155">Esse evento geralmente será registrado quando a ACL da URL não tiver sido definida adequadamente durante a instalação ou o certificado SSL é inválido.</span><span class="sxs-lookup"><span data-stu-id="7dfc8-155">This event will generally be logged when the URL ACL has not been set properly during installation or the SSL Cert is invalid.</span></span> <span data-ttu-id="7dfc8-156">Verifique se o certificado em sua configuração é válido.</span><span class="sxs-lookup"><span data-stu-id="7dfc8-156">Ensure the certificate in your configuration is valid.</span></span> <span data-ttu-id="7dfc8-157">Se for, reinstale o Ouvinte seguindo as instruções contidas em [Implantar o Gerenciador de Estatísticas](deploy.md#BKMK_Deploy).</span><span class="sxs-lookup"><span data-stu-id="7dfc8-157">If it is, reinstall the Listener according to the instructions in [Deploy Statistics Manager](deploy.md#BKMK_Deploy).</span></span>
    
  - <span data-ttu-id="7dfc8-158">**10003** - Falha de Redis</span><span class="sxs-lookup"><span data-stu-id="7dfc8-158">**10003** — Redis failure</span></span>
    
  - <span data-ttu-id="7dfc8-159">**10004** - Falha na infraestrutura do cache</span><span class="sxs-lookup"><span data-stu-id="7dfc8-159">**10004** — Caching infrastructure failure</span></span>
    
  - <span data-ttu-id="7dfc8-160">**10007** - Configurações (armazenadas em Redis)</span><span class="sxs-lookup"><span data-stu-id="7dfc8-160">**10007** — Settings (stored in redis)</span></span>
    
    <span data-ttu-id="7dfc8-161">O Ouvinte não conseguiu contatar o Redis ou recuperar dados bem formados do cache, e não foi possível iniciar.</span><span class="sxs-lookup"><span data-stu-id="7dfc8-161">The Listener could not contact Redis or retrieve well-formed data from the cache and could not start.</span></span> <span data-ttu-id="7dfc8-162">Certifique-se de que o serviço Redis foi iniciado e configurado adequadamente no servidor.</span><span class="sxs-lookup"><span data-stu-id="7dfc8-162">Ensure the Redis service is started and configured properly on the server.</span></span>
    
  - <span data-ttu-id="7dfc8-163">**10005** - Recuperação/análise das informações do servidor</span><span class="sxs-lookup"><span data-stu-id="7dfc8-163">**10005** — Server info retrieval/parsing</span></span>
    
    <span data-ttu-id="7dfc8-164">As informações de topologia no cache Redis são inválidas.</span><span class="sxs-lookup"><span data-stu-id="7dfc8-164">The topology information in the Redis cache is invalid.</span></span> <span data-ttu-id="7dfc8-165">Primeiro, tente reiniciar Redis e o Ouvinte.</span><span class="sxs-lookup"><span data-stu-id="7dfc8-165">First, attempt to restart Redis and the Listener.</span></span> <span data-ttu-id="7dfc8-166">Se o erro persistir, veja [Importar a topologia](deploy.md#BKMK_ImportTopology) para recriar os dados da topologia.</span><span class="sxs-lookup"><span data-stu-id="7dfc8-166">If the error persists, see [Import the topology](deploy.md#BKMK_ImportTopology) to recreate the topology data.</span></span>
    
- <span data-ttu-id="7dfc8-167">**10100** - Interrupção de PING do Redis</span><span class="sxs-lookup"><span data-stu-id="7dfc8-167">**10100** — Redis PING outage</span></span>
    
  - <span data-ttu-id="7dfc8-168">**10101** - Interrupção continuada de PING do Redis (a cada 60 segundos)</span><span class="sxs-lookup"><span data-stu-id="7dfc8-168">**10101** — Redis PING continued outage (every 60 seconds)</span></span>
    
  - <span data-ttu-id="7dfc8-169">**30100** - Interrupção de PING do Redis restaurada</span><span class="sxs-lookup"><span data-stu-id="7dfc8-169">**30100** — Redis PING outage restored</span></span>
    
    <span data-ttu-id="7dfc8-170">Esses eventos serão registrados quando o Ouvinte não puder se conectar ao Redis.</span><span class="sxs-lookup"><span data-stu-id="7dfc8-170">These will be logged when the Listener cannot connect to Redis.</span></span> <span data-ttu-id="7dfc8-171">Verifique se o Redis foi iniciado e a conectividade de rede entre o Ouvinte e o Redis está disponível.</span><span class="sxs-lookup"><span data-stu-id="7dfc8-171">Ensure Redis is started and network connectivity between the Listener and Redis is available.</span></span>
    
- <span data-ttu-id="7dfc8-172">**10200** - Interrupção de gravação do Redis</span><span class="sxs-lookup"><span data-stu-id="7dfc8-172">**10200** — Redis Write outage</span></span>
    
  - <span data-ttu-id="7dfc8-173">**10201** - Interrupção continuada de gravação do Redis (a cada 60 segundos)</span><span class="sxs-lookup"><span data-stu-id="7dfc8-173">**10201** — Redis Write outage continued (every 60 seconds)</span></span>
    
  - <span data-ttu-id="7dfc8-174">**30100** - Interrupção de gravação do Redis resolvida</span><span class="sxs-lookup"><span data-stu-id="7dfc8-174">**30100** — Redis Write outage resolved</span></span>
    
    <span data-ttu-id="7dfc8-175">Esses eventos serão registrados quando o Ouvinte não puder gravar no cache do Redis.</span><span class="sxs-lookup"><span data-stu-id="7dfc8-175">These will be logged when the Listener cannot write to the Redis cache.</span></span> <span data-ttu-id="7dfc8-176">Verifique se o Redis foi iniciado e a conectividade de rede entre o Ouvinte e o Redis está disponível.</span><span class="sxs-lookup"><span data-stu-id="7dfc8-176">Ensure Redis is started and network connectivity between the Listener and Redis is available.</span></span>
    
- <span data-ttu-id="7dfc8-177">**30000** - Iniciado com êxito</span><span class="sxs-lookup"><span data-stu-id="7dfc8-177">**30000** — Successfully started</span></span>
    
    <span data-ttu-id="7dfc8-178">Registrado toda vez que o Ouvinte é iniciado.</span><span class="sxs-lookup"><span data-stu-id="7dfc8-178">Logged each time the Listener is started.</span></span>
    
- <span data-ttu-id="7dfc8-179">**22000** — inicialização do agente estatísticas Manager foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="7dfc8-179">**22000** — Initialization of Statistics Manager Agent succeeded.</span></span>
    
- <span data-ttu-id="7dfc8-180">**23000** - Inicialização bem-sucedida do EventLogQueryManager (primeira vez ou após uma falha)</span><span class="sxs-lookup"><span data-stu-id="7dfc8-180">**23000** — Initialization of EventLogQueryManager succeeded (first time or after failing)</span></span>
    
- <span data-ttu-id="7dfc8-181">**24000** - Inicialização bem-sucedida de serverinfo (primeira vez ou após uma falha)</span><span class="sxs-lookup"><span data-stu-id="7dfc8-181">**24000** — Initialization of serverinfo succeeded (first time or after failing)</span></span>
    
- <span data-ttu-id="7dfc8-182">**25000** - O Ouvinte está online novamente após uma falha ao postar (ou primeira postagem bem-sucedida)</span><span class="sxs-lookup"><span data-stu-id="7dfc8-182">**25000** — Listener is back online after failing to post (or first successful post)</span></span>
    
- <span data-ttu-id="7dfc8-183">**5000** - Início do ouvinte offline para postagem de dados</span><span class="sxs-lookup"><span data-stu-id="7dfc8-183">**5000** — Start of listener offline for posting data</span></span>
    
- <span data-ttu-id="7dfc8-184">**5001** - O Ouvinte continua offline durante um período extenso</span><span class="sxs-lookup"><span data-stu-id="7dfc8-184">**5001** — Listener is still offline for an extended period</span></span>
    
    <span data-ttu-id="7dfc8-185">Esses eventos podem ser úteis para monitorar/alertar sobre/resolver problemas.</span><span class="sxs-lookup"><span data-stu-id="7dfc8-185">These events can be useful for monitoring/alerting/clearing issues.</span></span>
    
## <a name="website-issues"></a><span data-ttu-id="7dfc8-186">Problemas de site da Web</span><span class="sxs-lookup"><span data-stu-id="7dfc8-186">Website issues</span></span>
<span data-ttu-id="7dfc8-187"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="7dfc8-187"></span></span>

- <span data-ttu-id="7dfc8-188">Os prompts de logon repetitiva no Chrome - este foi um bug que foi resolvido na versão 1.1.</span><span class="sxs-lookup"><span data-stu-id="7dfc8-188">Repetitive login prompts in Chrome - this was a bug that has been resolved in version 1.1.</span></span> <span data-ttu-id="7dfc8-189">Certifique-se de que você tiver atualizado para a versão mais recente do Gerenciador de estatísticas se você estiver vendo prompts de logon repetidas do navegador Google Chrome.</span><span class="sxs-lookup"><span data-stu-id="7dfc8-189">Be sure you have upgraded to the latest version of Statistics Manager if you are seeing repeated login prompts in the Chrome browser.</span></span> <span data-ttu-id="7dfc8-190">Para conferir a versão do site executada:</span><span class="sxs-lookup"><span data-stu-id="7dfc8-190">To verify the version of the website you are running:</span></span>
    
  - <span data-ttu-id="7dfc8-191">	No Explorador de Arquivos, abra (default directory)</span><span class="sxs-lookup"><span data-stu-id="7dfc8-191">In File Explorer, open (default directory)</span></span>
    
  - <span data-ttu-id="7dfc8-192">Clique com o botão direito do mouse em StatsManHubWebSite.dll e veja as propriedades.</span><span class="sxs-lookup"><span data-stu-id="7dfc8-192">Right click on StatsManHubWebSite.dll and view its properties.</span></span>
    
  - <span data-ttu-id="7dfc8-193">Caso um computador não possa ser encontrado no modo de exibição Paisagem do KHI ou no modo de exibição Detalhes do Contador, verifique se ele é membro de um Site e de um Pool.</span><span class="sxs-lookup"><span data-stu-id="7dfc8-193">If a computer cannot be found in the KHI Landscape view or the Counter Details view, make sure it is a member of a Site and a Pool.</span></span> <span data-ttu-id="7dfc8-194">Se não for, ele não aparecerá nesses modos de exibição.</span><span class="sxs-lookup"><span data-stu-id="7dfc8-194">If it is not, it will not appear in those views.</span></span> <span data-ttu-id="7dfc8-195">Para obter informações sobre como definir um site e um pool para um servidor na topologia, veja [Importar a topologia](deploy.md#BKMK_ImportTopology).</span><span class="sxs-lookup"><span data-stu-id="7dfc8-195">For information about defining a site and pool for a server in the topology, see [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
  - <span data-ttu-id="7dfc8-196">A versão do produto será mostrada nos detalhes de Descrição.</span><span class="sxs-lookup"><span data-stu-id="7dfc8-196">The product version will be shown in the Description details.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="7dfc8-197">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="7dfc8-197">For more information</span></span>
<span data-ttu-id="7dfc8-198"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="7dfc8-198"></span></span>

<span data-ttu-id="7dfc8-199">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="7dfc8-199">For more information, see the following:</span></span>
  
- [<span data-ttu-id="7dfc8-200">Planejar para o Gerenciador de estatísticas de Skype Business Server</span><span class="sxs-lookup"><span data-stu-id="7dfc8-200">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="7dfc8-201">Implantar o Gerenciador de estatísticas para Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="7dfc8-201">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)
    
- [<span data-ttu-id="7dfc8-202">Atualizar o Gerenciador de estatísticas para Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="7dfc8-202">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)
    
- [<span data-ttu-id="7dfc8-203">Blog sobre o Gerenciador de Estatísticas do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7dfc8-203">Skype for Business Server Statistics Manager blog</span></span>](https://blogs.technet.microsoft.com/dodeitte/2015/10/24/skype-for-business-server-real-time-statistics-manager)
    

