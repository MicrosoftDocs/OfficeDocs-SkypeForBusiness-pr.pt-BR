---
title: Notas de versão do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Release notes
ms:assetid: 9f9e864c-3365-4800-803c-5289bd8fd363
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205120(v=OCS.15)
ms:contentKeyID: 48184930
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f572c120d86c5f89fb82e23066a6262e957e5e2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201507"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="release-notes-for-lync-server-2013"></a><span data-ttu-id="7c2fb-102">Notas de versão do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c2fb-102">Release notes for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c2fb-103">_**Última modificação do tópico:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="7c2fb-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="7c2fb-104">Bem-vindo às notas de versão do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-104">Welcome to the Lync Server 2013 Release Notes.</span></span> <span data-ttu-id="7c2fb-105">Consulte este arquivo para obter informações sobre problemas conhecidos sobre o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-105">Refer to this file for information regarding known issues about Lync Server 2013.</span></span>

<div>

## <a name="about-this-document"></a><span data-ttu-id="7c2fb-106">Sobre este documento</span><span class="sxs-lookup"><span data-stu-id="7c2fb-106">About this document</span></span>

<span data-ttu-id="7c2fb-107">Este documento contém informações importantes que você deve saber antes de implantar e usar o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-107">This document contains important information that you should know before you deploy and use Lync Server 2013.</span></span> <span data-ttu-id="7c2fb-108">Para obter detalhes sobre o Lync Server 2013, consulte a documentação do [Microsoft Lync server 2013](microsoft-lync-server-2013.md) .</span><span class="sxs-lookup"><span data-stu-id="7c2fb-108">For details about Lync Server 2013, refer to the [Microsoft Lync Server 2013](microsoft-lync-server-2013.md) documentation.</span></span>

<span data-ttu-id="7c2fb-109">Este documento contém as seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="7c2fb-109">This document contains the following sections:</span></span>

  - <span data-ttu-id="7c2fb-110">Cliente do Lync 2013</span><span class="sxs-lookup"><span data-stu-id="7c2fb-110">Lync 2013 client</span></span>

  - <span data-ttu-id="7c2fb-111">Lync Server</span><span class="sxs-lookup"><span data-stu-id="7c2fb-111">Lync Server</span></span>

  - <span data-ttu-id="7c2fb-112">Instalação</span><span class="sxs-lookup"><span data-stu-id="7c2fb-112">Installation</span></span>

  - <span data-ttu-id="7c2fb-113">Movimentação</span><span class="sxs-lookup"><span data-stu-id="7c2fb-113">Mobility</span></span>

  - <span data-ttu-id="7c2fb-114">Conferências</span><span class="sxs-lookup"><span data-stu-id="7c2fb-114">Conferencing</span></span>

  - <span data-ttu-id="7c2fb-115">Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="7c2fb-115">Enterprise Voice</span></span>

  - <span data-ttu-id="7c2fb-116">Presença</span><span class="sxs-lookup"><span data-stu-id="7c2fb-116">Presence</span></span>

  - <span data-ttu-id="7c2fb-117">Aplicativo de Grupo de Resposta e Aplicativo Ponto de Espera de Chamadas</span><span class="sxs-lookup"><span data-stu-id="7c2fb-117">Response Group Application and Call Park Application</span></span>

  - <span data-ttu-id="7c2fb-118">Painel de controle do Lync Server, Construtor de topologias e Ferramenta de planejamento</span><span class="sxs-lookup"><span data-stu-id="7c2fb-118">Lync Server Control Panel, Topology Builder, and Planning Tool</span></span>

  - <span data-ttu-id="7c2fb-119">Localização</span><span class="sxs-lookup"><span data-stu-id="7c2fb-119">Localization</span></span>

  - <span data-ttu-id="7c2fb-120">Direitos autorais</span><span class="sxs-lookup"><span data-stu-id="7c2fb-120">Copyright</span></span>

</div>

<span id="LyncClient"></span>

<div>

## <a name="lync-2013-client"></a><span data-ttu-id="7c2fb-121">Cliente do Lync 2013</span><span class="sxs-lookup"><span data-stu-id="7c2fb-121">Lync 2013 client</span></span>

<div>

## <a name="transferring-a-file-in-an-instant-message-fails-if-the-file-is-open-in-another-application"></a><span data-ttu-id="7c2fb-122">A transferência de um arquivo em uma mensagem instantânea falha se o arquivo estiver aberto em outro aplicativo</span><span class="sxs-lookup"><span data-stu-id="7c2fb-122">Transferring a file in an instant message fails if the file is open in another application</span></span>

<span data-ttu-id="7c2fb-123">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-123">**Issue:**</span></span>

<span data-ttu-id="7c2fb-124">Se você tentar transferir um arquivo, como um documento do Word, incluindo-o em uma mensagem instantânea para outro usuário do Lync, a transferência parecerá bem-sucedida, mas pode falhar na transferência do arquivo.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-124">If you attempt to transfer a file, such as a Word document, by including it in an instant message to another Lync user, the transfer will appear to succeed but may actually fail to transfer the file.</span></span> <span data-ttu-id="7c2fb-125">Um ícone para o tipo de arquivo será exibido no cliente do Lync, mas o arquivo não poderá ser aberto pelo destinatário pretendido.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-125">An icon for the file type will be displayed in the Lync client, but the file cannot be opened by the intended receiver.</span></span> <span data-ttu-id="7c2fb-126">Nenhuma mensagem de erro é exibida para informá-lo que a transferência não foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-126">No error message is displayed to inform you that the transfer was not successfull.</span></span>

<span data-ttu-id="7c2fb-127">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-127">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-128">Para contornar esse problema, feche o arquivo aberto ou o aplicativo que o abriu antes de tentar transferir o arquivo em uma mensagem instantânea.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-128">To work around this issue, close the open file or application that has it open before attempting to transfer the file in an instant message.</span></span>

</div>

</div>

<span id="LyncServer"></span>

<div>

## <a name="lync-server"></a><span data-ttu-id="7c2fb-129">Lync Server</span><span class="sxs-lookup"><span data-stu-id="7c2fb-129">Lync Server</span></span>

<div>

## <a name="if-lync-server-storage-service-data-replication-fails-administrators-will-need-to-check-performance-counters-for-stale-storage-service-queue-items"></a><span data-ttu-id="7c2fb-130">Se a replicação de dados do serviço de armazenamento do Lync Server falhar, os administradores precisarão verificar os contadores de desempenho para itens de fila de serviço de armazenamento obsoleto</span><span class="sxs-lookup"><span data-stu-id="7c2fb-130">If Lync Server Storage Service data replication fails, administrators will need to check performance counters for stale Storage Service queue items</span></span>

<span data-ttu-id="7c2fb-131">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-131">**Issue:**</span></span>

<span data-ttu-id="7c2fb-132">O serviço de armazenamento do Lync Server usa o Windows Fabric para replicação.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-132">The Lync Server Storage Service uses Windows Fabric for replication.</span></span> <span data-ttu-id="7c2fb-133">Se os dados forem excluídos em um servidor front-end primário, mas a exclusão em um servidor front-end secundário falhar — por exemplo, se houver um desligamento ou erro inesperado no servidor de front-end, os dados podem ser deixados para trás e órfãos.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-133">If data is deleted on a primary Front End Server, but the deletion on a secondary Front End Server fails—for example, if there is an unexpected shutdown or error on the Front End Server—data can be left behind and "orphaned."</span></span> <span data-ttu-id="7c2fb-134">Os dados órfãos podem causar desempenho a degradar e perder espaço na unidade.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-134">The orphaned data can cause performance to degrade and waste drive space.</span></span>

<span data-ttu-id="7c2fb-135">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-135">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-136">Para contornar esse problema, se o espaço de\_LYSS\_de\_eventos\_de banco de 32058 usado (ID =\_\_)\_e\_o espaço de banco de usado como crítico (ID = 32059) forem gerados no log de eventos, os administradores devem verificar o contador de desempenho no servidor front **-** end em **ls: LYSS-Service**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-136">To work around this issue, if the events LYSS\_DB\_SPACE\_USED\_ERROR (Id=32058) and LYSS\_DB\_SPACE\_USED\_CRITICAL (Id=32059) are generated in the event log, administrators should check the performance counter on the Front End Server under **LS:LYSS - Storage Service API** with a name of **LYSS - Current number of Storage Service stale queue items**.</span></span> <span data-ttu-id="7c2fb-137">Se esse contador de desempenho tiver um valor alto — por exemplo, maior que 50000, o administrador deve executar a ferramenta CleanuUpStorageServiceData. exe no Lync Server 2013 Resource Kit, que excluirá todos os dados órfãos do pool.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-137">If this performance counter has a high value—for example, greater than 50,000—then the administrator should run the CleanuUpStorageServiceData.exe tool in the Lync Server 2013 Resource Kit, which will delete all orphaned data from the pool.</span></span> <span data-ttu-id="7c2fb-138">Para obter detalhes sobre a ferramenta, consulte a documentação do kit de recursos do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-138">For details about the tool, see the Lync Server 2013 Resource Kit documentation.</span></span>

</div>

<div>

## <a name="whenever-the-ip-address-configuration-is-changed-for-a-server-or-pool-lync-server-services-need-to-be-restarted"></a><span data-ttu-id="7c2fb-139">Sempre que a configuração de endereço IP for alterada para um servidor ou pool, os serviços do Lync Server precisarão ser reiniciados</span><span class="sxs-lookup"><span data-stu-id="7c2fb-139">Whenever the IP Address configuration is changed for a server or pool, Lync Server services need to be restarted</span></span>

<span data-ttu-id="7c2fb-140">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-140">**Issue:**</span></span>

<span data-ttu-id="7c2fb-141">Quando a configuração de endereço IP for alterada para uma implantação do Lync Server 2013, como a alteração do IPv4 para a pilha dual ou de uma pilha dual para IPv6, nem todos os componentes do servidor selecionarão a alteração da configuração até que os serviços sejam reiniciados.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-141">When the IP Address configuration is changed for a Lync Server 2013 deployment, such as changing from IPv4 to Dual Stack, or from Dual Stack to Ipv6, not all server components pick up the configuration change until the services are restarted.</span></span>

<span data-ttu-id="7c2fb-142">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-142">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-143">Para contornar esse problema, reinicie os serviços do Lync Server após alterar a configuração de endereço IP para a implantação.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-143">To work around this issue, restart Lync Server services after changing the IP Address configuration for the deployment.</span></span> <span data-ttu-id="7c2fb-144">Para fazer isso, execute os seguintes cmdlets no Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="7c2fb-144">To do so, run the following cmdlets in the Lync Server Management Shell:</span></span>

   ```PowerShell
    Stop-CsWindowsService -graceful
   ```

   ```PowerShell
    Start-CsWindowsService
   ```

</div>

<div>

## <a name="the-dial-in-conferencing-synthetic-transaction-cmdlet-is-no-longer-available-in-the-lync-server-2013-management-pack"></a><span data-ttu-id="7c2fb-145">O cmdlet de transação sintética de conferência discada não está mais disponível no pacote de gerenciamento do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c2fb-145">The dial-in conferencing synthetic transaction cmdlet is no longer available in the Lync Server 2013 Management Pack</span></span>

<span data-ttu-id="7c2fb-146">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-146">**Issue:**</span></span>

<span data-ttu-id="7c2fb-147">O cmdlet da transação sintética de conferência discada **Test-CsDialInConferencing** não está mais disponível no pacote de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-147">The dial-in conferencing synthetic transaction cmdlet **Test-CsDialInConferencing** is no longer available in the Lync Server 2013 Management Pack.</span></span>

<span data-ttu-id="7c2fb-148">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-148">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-149">O uso do cmdlet de transação sintética de conferência discada **Test-CsDialInConferencing** é suportado apenas internamente para uma empresa.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-149">Use of the Dial-In Conferencing Synthetic Transaction cmdlet **Test-CsDialInConferencing** is supported only internally to an enterprise.</span></span>

<span data-ttu-id="7c2fb-150">Os administradores podem continuar a usar o cmdlet no Shell de gerenciamento do Lync Server para fins de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-150">Administrators may continue to use the cmdlet in Lync Server Management Shell for troubleshooting purposes.</span></span> <span data-ttu-id="7c2fb-151">Se necessário, uma empresa também pode desenvolver um pacote de gerenciamento privado para executar o cmdlet internamente.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-151">If required, an enterprise can also develop a private management pack to run the cmdlet internally.</span></span>

</div>

<div>

## <a name="the-centralized-logging-service-stops-if-network-traffic-is-disrupted-when-log-files-are-being-copied-to-network-share"></a><span data-ttu-id="7c2fb-152">O serviço de registro em log centralizado interrompe se o tráfego de rede é interrompido quando os arquivos de log são copiados para o compartilhamento de rede</span><span class="sxs-lookup"><span data-stu-id="7c2fb-152">The Centralized Logging Service stops if network traffic is disrupted when log files are being copied to network share</span></span>

<span data-ttu-id="7c2fb-153">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-153">**Issue:**</span></span>

<span data-ttu-id="7c2fb-154">Quando o serviço de registro em log centralizado é configurado para usar um caminho de rede (o valor do parâmetro CacheFileNetworkFolder do cmdlet **Get-CsClsConfiguration** é um caminho UNC válido), os arquivos de log armazenados em cache são copiados para o compartilhamento de rede.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-154">When the Centralized Logging Service is configured to use a network path (the value of the CacheFileNetworkFolder parameter of the **Get-CsClsConfiguration** cmdlet is a valid UNC path), cached log files are copied to the network share.</span></span> <span data-ttu-id="7c2fb-155">Se houver uma interrupção no tráfego de rede enquanto os arquivos estão sendo copiados, ocorrerá uma exceção que causará a interrupção do serviço de registro em log centralizado.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-155">If there is a disruption in network traffic while the files are being copied, an exception will occur that will cause the centralized logging service to stop.</span></span>

<span data-ttu-id="7c2fb-156">O serviço é configurado para reiniciar automaticamente até três vezes, de modo que o serviço se recupere das três primeiras exceções.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-156">The service is configured to automatically restart up to three times, so the service will recover from the first three exceptions.</span></span>

<span data-ttu-id="7c2fb-157">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-157">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-158">Não há solução para esse problema.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-158">There is no workaround for this issue.</span></span> <span data-ttu-id="7c2fb-159">Para identificar o problema, monitore o log de eventos para o ID de evento 7031 no "Gerenciador de controle de serviço" que registra quando o serviço "agente de serviço de registro centralizado do Lync Server" foi finalizado inesperadamente.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-159">To identify the issue, monitor the event log for Event ID 7031 from the "Service Control Manager" that logs when the "Lync Server Centralized Logging Service Agent" service has terminated unexpectedly.</span></span> <span data-ttu-id="7c2fb-160">Se isso acontecer mais de três vezes, reinicie manualmente o serviço usando o cmdlet **Start-CsWindowService** .</span><span class="sxs-lookup"><span data-stu-id="7c2fb-160">If this happens more than three times, manually restart the service by using the **Start-CsWindowService** cmdlet.</span></span>

</div>

<div>

## <a name="storage-service-queue-items-need-to-be-imported-manually"></a><span data-ttu-id="7c2fb-161">Os itens da fila de serviço de armazenamento precisam ser importados manualmente</span><span class="sxs-lookup"><span data-stu-id="7c2fb-161">Storage Service Queue Items need to be imported manually</span></span>

<span data-ttu-id="7c2fb-162">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-162">**Issue:**</span></span>

<span data-ttu-id="7c2fb-163">O Lync Server 2013 armazena dados sobre conferência e mensagens instantâneas, como mensagens arquivadas e registro de detalhes de chamadas (CDR) em um banco de dados em cada servidor de front-end.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-163">Lync Server 2013 stores data about conferencing and instant messaging, such as archived messages and call detail recording (CDR), on a database on each Front End Server.</span></span> <span data-ttu-id="7c2fb-164">Os dados são armazenados no banco de dados enquanto estão sendo processados antes de serem entregues ao destino desejado.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-164">The data is stored in the database while it is being processed before being delivered to the intended destination.</span></span> <span data-ttu-id="7c2fb-165">Para melhorar o desempenho, o Lync Server 2013 exporta periodicamente os itens de fila do banco de dados local que não são processados por um período de tempo estendido e os salva no repositório de arquivos.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-165">To improve performance, Lync Server 2013 periodically exports the queue items from the local database that are not processed for an extended period of time, and saves them on the file store.</span></span> <span data-ttu-id="7c2fb-166">Se o repositório de arquivos não estiver disponível, os itens serão armazenados em cada servidor de front-end.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-166">If the file store is unavailable, the items are stored on each Front End Server.</span></span> <span data-ttu-id="7c2fb-167">A mesma operação ocorre para evitar a perda de dados durante o failover do pool.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-167">The same operation occurs to prevent data loss during pool failover.</span></span>

<span data-ttu-id="7c2fb-168">Durante a operação de exportação, o serviço de armazenamento do Lync Server registra cada estágio no log de eventos com IDs de evento de 32075 (operação de liberação completa iniciada), 32076 (a liberação completa é concluída), 32082 (liberação de nível de manutenção é iniciado), 32083 (liberação de nível de manutenção estiver concluído), 32089 (liberação ocorrida devido ao preenchimento do banco de dados).</span><span class="sxs-lookup"><span data-stu-id="7c2fb-168">During the export operation, the Lync Server Storage Service records every stage in the event log with event IDs of 32075 (full flush operation is started), 32076 (full flush is completed), 32082 (maintenance level flush is started), 32083 (maintenance level flush is completed), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="7c2fb-169">Esses dados não serão automaticamente importados de volta para o sistema para serem processados e entregues ao seu destino final (SQL Server ou Exchange Server).</span><span class="sxs-lookup"><span data-stu-id="7c2fb-169">This data will not automatically be imported back to the system to be processed and delivered to its final destination (SQL Server or Exchange Server).</span></span>

<span data-ttu-id="7c2fb-170">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-170">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-171">Para importar os dados para o sistema, os administradores precisarão usar a ferramenta ImportStorageServiceData no kit de recursos do Lync Server, que adicionará os dados de volta ao sistema para serem processados e entregues ao seu destino final.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-171">To import the data to the system, administrators will need to use the ImportStorageServiceData tool in the Lync Server Resource Kit, which will add the data back into the system to be processed and delivered to its final destination.</span></span>

</div>

<div>

## <a name="address-book-web-query-searches-will-fail-if-the-default-value-for-usenormalizationrules-is-changed-to-false"></a><span data-ttu-id="7c2fb-172">Pesquisas de consulta da Web do catálogo de endereços falharão se o valor padrão de UseNormalizationRules for alterado para false</span><span class="sxs-lookup"><span data-stu-id="7c2fb-172">Address Book Web Query searches will fail if the default value for UseNormalizationRules is changed to False</span></span>

<span data-ttu-id="7c2fb-173">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-173">**Issue:**</span></span>

<span data-ttu-id="7c2fb-174">Se o valor padrão de UseNormalizationRules for alterado para false, as pesquisas da consulta à Web do catálogo de endereços falharão.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-174">If the default value for UseNormalizationRules is changed to False, Address Book Web Query searches will fail.</span></span> <span data-ttu-id="7c2fb-175">Após a alteração do valor padrão, os usuários do cliente do Lync não poderão usar a consulta da Web do catálogo de endereços do Lync para pesquisar usuários.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-175">After the default value is changed, Lync Client users will not be able to use Lync Address Book web query to search for users.</span></span>

<span data-ttu-id="7c2fb-176">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-176">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-177">Se o valor padrão de UseNormalizationRules for definido como false para que os usuários possam usar números de telefone, conforme definido nos serviços de domínio do Active Directory sem o Lync Server 2013 aplicando regras de normalização, confira este problema fazendo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7c2fb-177">If the default value for UseNormalizationRules is set to False so that users can use phone numbers as defined in Active Directory Domain Services without Lync Server 2013 applying normalization rules, work around this issue by doing the following:</span></span>

1.  <span data-ttu-id="7c2fb-178">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-178">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="7c2fb-179">Siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="7c2fb-179">Do one of the following:</span></span>
    
      - <span data-ttu-id="7c2fb-180">Se sua implantação incluir apenas servidores do Lync Server 2013, execute o seguinte cmdlet no nível global para alterar os valores de UseNormalizationRules e IgnoreGenericRules para true:</span><span class="sxs-lookup"><span data-stu-id="7c2fb-180">If your deployment includes only Lync Server 2013 servers, run the following cmdlet at the global level to change the values for UseNormalizationRules and IgnoreGenericRules to True:</span></span>
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - <span data-ttu-id="7c2fb-181">Se sua implantação incluir uma combinação do Lync Server 2013 e do Lync Server 2010 ou do Office Communications Server 2007 R2, execute o seguinte cmdlet e atribua-o a cada pool do Lync Server 2013 na topologia:</span><span class="sxs-lookup"><span data-stu-id="7c2fb-181">If your deployment includes a combination of Lync Server 2013 and Lync Server 2010 or Office Communications Server 2007 R2, run the following cmdlet and assign it to each Lync Server 2013 pool in the topology:</span></span>
        
            new-csAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  <span data-ttu-id="7c2fb-182">Aguarde a replicação do CMS ocorrer em todos os pools.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-182">Wait for CMS replication to occur on all pools.</span></span>

4.  <span data-ttu-id="7c2fb-183">Modifique o arquivo de regras de normalização de telefone para a sua implantação para limpar o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-183">Modify the phone normalization rules file for your deployment to clear the content.</span></span> <span data-ttu-id="7c2fb-184">O arquivo está no compartilhamento de arquivos de cada pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-184">The file is on the file share of each Lync Server 2013 pool.</span></span> <span data-ttu-id="7c2fb-185">Se o arquivo não estiver presente, crie um arquivo\_vazio chamado "\_\_\_regras de normalização de número de telefone da empresa. txt".</span><span class="sxs-lookup"><span data-stu-id="7c2fb-185">If the file is not present, then create an empty file named "Company\_Phone\_Number\_Normalization\_Rules.txt."</span></span>

5.  <span data-ttu-id="7c2fb-186">Aguarde alguns minutos para que todos os pools de front-ends leiam os novos arquivos.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-186">Wait several minutes for all Front End pools to read the new files.</span></span>

6.  <span data-ttu-id="7c2fb-187">Execute o cmdlet a seguir em cada pool do Lync Server 2013 em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-187">Run the following cmdlet on each Lync Server 2013 pool in your deployment.</span></span>
    
        Update-csAddressBook

</div>

<div>

## <a name="address-book-server-error-event-21054-is-generated-once-daily-for-each-lync-2013-pool"></a><span data-ttu-id="7c2fb-188">O evento 21054 de erro do servidor do catálogo de endereços é gerado uma vez diariamente para cada pool do Lync 2013</span><span class="sxs-lookup"><span data-stu-id="7c2fb-188">Address Book Server error event 21054 is generated once daily for each Lync 2013 pool</span></span>

<span data-ttu-id="7c2fb-189">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-189">**Issue:**</span></span>

<span data-ttu-id="7c2fb-190">Lync Server 2013 o servidor do catálogo de endereços gerará evento de erro 21054 a cada dia ao realizar manutenção diária.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-190">Lync Server 2013 Address Book Server will generate error event 21054 once every day when performing daily maintenance.</span></span> <span data-ttu-id="7c2fb-191">O erro também é gerado toda vez que um administrador executa o cmdlet **Update-csAddressBook** , mesmo quando a atualização é bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-191">The error is also generated every time an administrator runs the **Update-csAddressBook** cmdlet, even when the update is successful.</span></span> <span data-ttu-id="7c2fb-192">No entanto, esse evento de erro pode ser ignorado com segurança quando a atualização for bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-192">However, this error event can safely be ignored when the update is successful.</span></span>

<span data-ttu-id="7c2fb-193">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-193">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-194">Quando você encontrar esse evento de erro, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="7c2fb-194">When you encounter this error event, run the following cmdlet:</span></span>

    Debug-csAddressBookReplication -Poolfqdn <Pool FQDN for which the event was generated>

<span data-ttu-id="7c2fb-195">Se o cmdlet relatar que não há objetos não indexados ou abandonados, o evento de erro 21054 pode ser ignorado com segurança.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-195">If the cmdlet reports that there are no unindexed or abandoned objects, the error event 21054 can be safely ignored.</span></span>

<span data-ttu-id="7c2fb-196">Além disso, o Key Health Indicator (KHI) "usuários do catálogo de endereços indexados corretamente" deve ser desativado no System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-196">Additionally, the Key Health Indicator (KHI) "Address Book Users Correctly Indexed" should be turned off in System Center Operations Manager.</span></span>

</div>

<div>

## <a name="requests-may-fail-when-ipv6-is-configured-on-an-edge-pool"></a><span data-ttu-id="7c2fb-197">As solicitações podem falhar quando o IPv6 é configurado em um pool de borda</span><span class="sxs-lookup"><span data-stu-id="7c2fb-197">Requests may fail when IPv6 is configured on an Edge pool</span></span>

<span data-ttu-id="7c2fb-198">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-198">**Issue:**</span></span>

<span data-ttu-id="7c2fb-199">Quando o IPv6 é configurado em um pool de borda, algumas solicitações ao pool de borda podem falhar.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-199">When IPv6 is configured on an Edge pool, some requests to the Edge pool may fail.</span></span>

<span data-ttu-id="7c2fb-200">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-200">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-201">Para contornar esse problema, não configure um pool de borda com IPv6.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-201">To work around this issue, do not configure an Edge pool with IPv6.</span></span>

</div>

<div>

## <a name="the-invoke-cspoolfailback-cmdlet-may-fail-during-pool-failback"></a><span data-ttu-id="7c2fb-202">O cmdlet Invoke-csPoolFailback pode falhar durante o failback do pool</span><span class="sxs-lookup"><span data-stu-id="7c2fb-202">The invoke-csPoolFailback cmdlet may fail during pool failback</span></span>

<span data-ttu-id="7c2fb-203">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-203">**Issue:**</span></span>

<span data-ttu-id="7c2fb-204">Ao tentar fazer o failback de um pool, o cmdlet **Invoke-csPoolFailback** pode falhar com o erro "falha ao concluir o processo de hidratação após repetidas tentativas".</span><span class="sxs-lookup"><span data-stu-id="7c2fb-204">When attempting to fail back a pool, the **invoke-csPoolFailback** cmdlet may fail with the error, "Failed to complete hydration process after repeated attempts."</span></span>

<span data-ttu-id="7c2fb-205">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-205">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-206">Para contornar esse problema, execute o cmdlet novamente e aguarde até que o cmdlet seja bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-206">To work around this issue, run the cmdlet again, and wait until the cmdlet succeeds.</span></span> <span data-ttu-id="7c2fb-207">Observe que o processo de failback pode levar vários minutos para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-207">Note that the failback process can take several minutes to complete.</span></span> <span data-ttu-id="7c2fb-208">Pode levar até 60 minutos para um pool com 20.000 usuários.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-208">It may take up to 60 minutes for a pool with 20,000 users.</span></span>

</div>

<div>

## <a name="data-loss-may-occur-when-you-add-a-front-end-server-to-an-already-established-pool--hybrid-skype-for-business-online"></a><span data-ttu-id="7c2fb-209">A perda de dados pode ocorrer quando você adiciona um servidor front-end a um pool já estabelecido – híbrido, Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="7c2fb-209">Data loss may occur when you add a Front End Server to an already established pool – Hybrid, Skype for Business Online</span></span>

<span data-ttu-id="7c2fb-210">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-210">**Issue:**</span></span>

<span data-ttu-id="7c2fb-211">Você pode encontrar esse problema em um ambiente em que um pool tenha mais de um servidor front-end, e você reinicia um dos servidores front-end ou adiciona um novo servidor front-end que não faz parte do pool.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-211">You may encounter this issue in an environment where a pool has more than one Front End Server, and you either restart one of the Front End Servers, or add a new Front End Server that was not previously part of the pool.</span></span>

<span data-ttu-id="7c2fb-212">Os usuários cujos dados estão sendo arquivados podem sofrer perda de dados até que uma distribuição estável do arquivamento de dados seja estabelecida para o pool.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-212">Users whose data is being archived may experience data loss until a stable distribution of data archiving is established for the pool.</span></span> <span data-ttu-id="7c2fb-213">Esse período de perda de dados em potencial é limitado a 15 minutos para conversas de pessoa a pessoa e 30 minutos para conferências.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-213">This period of potential data loss is limited to 15 minutes for person-to-person conversations, and 30 minutes for conferences.</span></span>

<span data-ttu-id="7c2fb-214">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-214">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-215">Ao executar a manutenção, em vez de iniciar servidores front-end no pool um, você deve fazer failover do pool para outro pool e, em seguida, executar tarefas de manutenção nos servidores.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-215">When you perform maintenance, instead of starting Front End Servers in the pool one by one, you should fail over the pool to another pool, and then perform maintenance tasks on the servers.</span></span> <span data-ttu-id="7c2fb-216">Você também pode tornar o serviço indisponível antes de realizar tarefas de manutenção e, em seguida, restaurar a disponibilidade quando a manutenção estiver concluída.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-216">You can also make the service unavailable before performing maintenance tasks, and then restore availability when maintenance is complete.</span></span>

</div>

<div>

## <a name="administrators-cannot-get-licensee-count-by-using-the-get-csclientaccesslicense-cmdlet"></a><span data-ttu-id="7c2fb-217">Os administradores não podem obter uma contagem de licenciados usando o cmdlet Get-CsClientAccessLicense</span><span class="sxs-lookup"><span data-stu-id="7c2fb-217">Administrators cannot get licensee count by using the Get-CsClientAccessLicense cmdlet</span></span>

<span data-ttu-id="7c2fb-218">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-218">**Issue:**</span></span>

<span data-ttu-id="7c2fb-219">Os administradores não podem obter o uso preciso da licença do cliente usando o cmdlet **Get-CsClientAccessLicense** .</span><span class="sxs-lookup"><span data-stu-id="7c2fb-219">Administrators cannot get accurate client license usage by using the **Get-CsClientAccessLicense** cmdlet.</span></span>

<span data-ttu-id="7c2fb-220">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-220">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-221">Para verificar o tipo de licença do servidor, você pode executar o cmdlet **Get-CsService** para recuperar os nomes de domínio totalmente qualificados (FDQNs) de todos os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-221">To check the server license type, you can run the **Get-CsService** cmdlet to retrieve the fully qualified domain names (FDQNs) of all databases.</span></span> <span data-ttu-id="7c2fb-222">Se o FQDN do servidor front-end for igual ao FQDN do banco de dados back-end, a licença será uma licença Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-222">If the FQDN of the Front End Server is the same as the FQDN of the back-end database, the license is a Standard edition license.</span></span> <span data-ttu-id="7c2fb-223">Caso contrário, a licença é uma licença Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-223">Otherwise, the license is an Enterprise edition license.</span></span>

</div>

<div>

## <a name="client-licensee-count-is-not-accurately-reported"></a><span data-ttu-id="7c2fb-224">A contagem do licenciado do cliente não é reportada com precisão</span><span class="sxs-lookup"><span data-stu-id="7c2fb-224">Client licensee count is not accurately reported</span></span>

<span data-ttu-id="7c2fb-225">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-225">**Issue:**</span></span>

<span data-ttu-id="7c2fb-226">Ao determinar as contagens de licença do cliente, você pode experimentar as seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="7c2fb-226">When determining client license counts, you may experience the following conditions:</span></span>

1.  <span data-ttu-id="7c2fb-227">**Contagem de licenças imprecisas para usuários móveis**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-227">**Inaccurate license count for mobile users**</span></span>
    
    <span data-ttu-id="7c2fb-228">A contagem de licenças é baseada no número de endereços IP exclusivos para usuários baseados em dispositivos.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-228">The license count is based on the number of unique IP addresses for device-based users.</span></span> <span data-ttu-id="7c2fb-229">A contagem de licenças será limitada das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="7c2fb-229">The license count will be limited in the following ways:</span></span>
    
      - <span data-ttu-id="7c2fb-230">As licenças serão descontadas se o endereço IP do usuário mudar durante sessões do Lync.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-230">Licenses will be overcounted if the IP address for the user changes during Lync sessions.</span></span> <span data-ttu-id="7c2fb-231">Isso pode ocorrer quando um usuário se conecta ao Lync Server de mais de um local com um cliente de desktop.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-231">This can occur when a user connects to Lync Server from more than one location with a desktop client.</span></span>
    
      - <span data-ttu-id="7c2fb-232">As licenças serão subcontadas se um usuário se conectar a um cliente móvel, porque o endereço IP do dispositivo não pode ser determinado.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-232">Licenses will be undercounted if a user connects with a mobile client, because the IP address for the device cannot be determined.</span></span>

2.  <span data-ttu-id="7c2fb-233">**As licenças são contadas duas vezes para chamadas PSTN (rede telefônica pública comutada) para o cliente Lync, chamadas do cliente Lync para linhas PSTN e chamadas do Lync encaminhadas para linhas PSTN**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-233">**Licenses are counted twice for public switched telephone network (PSTN) calls to Lync client, Lync client calls to PSTN lines, and Lync calls forwarded to PSTN lines**</span></span>
    
    <span data-ttu-id="7c2fb-234">Nos cenários a seguir, duas licenças adicionais serão contadas em vez de uma porque o número de telefone e o usuário do Lync são contados para determinar o número de licenças usadas.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-234">In the following scenarios, two additional licenses will be counted instead of one because both the phone number and the Lync user are counted to determine the number of licenses used.</span></span> <span data-ttu-id="7c2fb-235">Para obter dados de licenciamento precisos, remova manualmente as licenças geradas por um número de telefone.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-235">To obtain accurate licensing data, manually remove the licenses generated by a phone number.</span></span>
    
      - <span data-ttu-id="7c2fb-236">Uma chamada telefônica PSTN para o Lync</span><span class="sxs-lookup"><span data-stu-id="7c2fb-236">A PSTN phone call to Lync</span></span>
    
      - <span data-ttu-id="7c2fb-237">Uma chamada do Lync para uma linha PSTN</span><span class="sxs-lookup"><span data-stu-id="7c2fb-237">A Lync call to a PSTN line</span></span>
    
      - <span data-ttu-id="7c2fb-238">Uma chamada PSTN para o Lync e o Lync encaminha a chamada para uma linha PSTN.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-238">A PSTN call to Lync, and then Lync forwards the call to a PSTN line.</span></span> <span data-ttu-id="7c2fb-239">Uma das linhas PSTN será contada.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-239">One of the PSTN lines will be counted.</span></span>

3.  <span data-ttu-id="7c2fb-240">**Uma licença não será contada para um telefone do Lync conectado**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-240">**A license will not be counted for a logged-on Lync phone**</span></span>
    
    <span data-ttu-id="7c2fb-241">Quando um usuário usa um telefone certificado pelo Lync, se o telefone efetuar login e permanecer conectado, o que mantém seu status de logon, o telefone não será contado como usando uma licença se a consulta de licenças ocorrer após o logon do telefone.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-241">When a user uses a Lync-certified phone, if the phone logs in and stays connected, which retains its logon status, the phone will not be counted as using a license if the query for licenses occurs after the phone logged in.</span></span>

4.  <span data-ttu-id="7c2fb-242">**Licenças contadas para telefones PSTN que participam de conferências**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-242">**Licenses counted for PSTN phones joining conferences**</span></span>
    
    <span data-ttu-id="7c2fb-243">Quando um usuário ingressa em uma conferência com um telefone PSTN, uma licença será contada incorretamente para ingressar na conferência.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-243">When a user joins a conference with a PSTN phone, a license will inaccurately be counted for joining the conference.</span></span> <span data-ttu-id="7c2fb-244">No entanto, nenhuma licença é necessária para ingressar em uma conferência com um telefone PSTN.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-244">However, no license is needed to join a conference with a PSTN phone.</span></span>

<span data-ttu-id="7c2fb-245">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-245">**Workaround:**</span></span>

1.  <span data-ttu-id="7c2fb-246">**Contagem de licenças imprecisas para usuários móveis**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-246">**Inaccurate license count for mobile users**</span></span>
    
      - <span data-ttu-id="7c2fb-247">Você pode identificar manualmente os endereços IP que pertencem ao mesmo dispositivo e remover um deles na contagem de licenças.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-247">You can manually identify the IP addresses that belong to the same device and then remove one of them in the license count.</span></span>
    
      - <span data-ttu-id="7c2fb-248">Não há solução para esse problema com dispositivos móveis que se conectam ao cliente Lync.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-248">There is no workaround for this issue with mobile devices connecting with Lync client.</span></span>

2.  <span data-ttu-id="7c2fb-249">**As licenças são contadas duas vezes para chamadas PSTN para o cliente Lync, chamadas do cliente Lync para linhas PSTN e chamadas do Lync encaminhadas para linhas PSTN**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-249">**Licenses are counted twice for PSTN calls to Lync client, Lync client calls to PSTN lines, and Lync calls forwarded to PSTN lines**</span></span>
    
    <span data-ttu-id="7c2fb-250">Você precisará identificar manualmente o número de telefone PSTN e remover a contagem de licenças gerada para ele.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-250">You will need to manually identify the PSTN phone number and remove the license count generated for it.</span></span>

3.  <span data-ttu-id="7c2fb-251">**Uma licença não será contada para um telefone do Lync conectado**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-251">**A license will not be counted for a logged-in Lync phone**</span></span>
    
    <span data-ttu-id="7c2fb-252">Você pode configurar o telefone do Lync para fazer logoff e, em seguida, fazer logon novamente, em um intervalo regular, como a cada três meses.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-252">You can configure the Lync phone to log off, and then log on again, at a regular interval, such as every 3 months.</span></span>

4.  <span data-ttu-id="7c2fb-253">**Licenças contadas para telefones PSTN que participam de conferências**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-253">**Licenses counted for PSTN phones joining conferences**</span></span>
    
    <span data-ttu-id="7c2fb-254">Você pode identificar manualmente o número de telefone PSTN que é usado para ingressar na conferência e remover a licença gerada pelo número de telefone.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-254">You can manually identify the PSTN phone number that is used to join the conference and remove the license generated by the phone number.</span></span>

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-upgrading-to-silverlight-5"></a><span data-ttu-id="7c2fb-255">O painel de controle do Lync Server pára de funcionar em um ambiente VMware após a atualização para o Silverlight 5</span><span class="sxs-lookup"><span data-stu-id="7c2fb-255">The Lync Server Control Panel stops working in a VMware environment after upgrading to Silverlight 5</span></span>

<span data-ttu-id="7c2fb-256">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-256">**Issue:**</span></span>

<span data-ttu-id="7c2fb-257">Se você usar o painel de controle do Lync Server em um ambiente VMware, o painel de controle do Lync Server pode parar de funcionar após a atualização do Microsoft Silverlight para a versão 5.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-257">If you use the Lync Server Control Panel in a VMware environment, the Lync Server Control Panel may stop working after you upgrade Microsoft Silverlight to version 5.</span></span>

<span data-ttu-id="7c2fb-258">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-258">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-259">Para contornar esse problema, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="7c2fb-259">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="7c2fb-260">Desinstale o Silverlight 5 e instale o Silverlight [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156)4 de.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-260">Uninstall Silverlight 5, and install Silverlight 4 from [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156).</span></span>

  - <span data-ttu-id="7c2fb-261">Acessar o painel de controle do Lync Server em um computador que não é um computador virtual VMware.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-261">Access the Lync Server Control Panel from a computer that is not a VMware virtual computer.</span></span>
    
    <span data-ttu-id="7c2fb-262">Para fazer isso, você pode iniciar o painel de controle do Lync Server a partir do menu **Iniciar** do Windows no servidor, se as ferramentas de administração do Lync Server estiverem instaladas no computador.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-262">To do so, you can start the Lync Server Control Panel from the Windows **Start** menu on the server, if the Lync Server Administration tools are installed on the computer.</span></span>
    
    <span data-ttu-id="7c2fb-263">Você também pode acessar o painel de controle do Lync Server usando um navegador da Web.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-263">You can also access the Lync Server Control Panel by using a web browser.</span></span> <span data-ttu-id="7c2fb-264">A URL será\<semelhante ao FQDN\_\_\>do pool de front-https:///CSCP.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-264">The URL will be similar to https://\<frontend\_pool\_fqdn\>/cscp.</span></span>

</div>

<div>

## <a name="user-information-in-the-address-book-service-is-not-updated-after-the-distinguished-name-for-the-user-is-modified-in-active-directory"></a><span data-ttu-id="7c2fb-265">As informações do usuário no serviço de catálogo de endereços não são atualizadas depois que o nome distinto do usuário é modificado no Active Directory</span><span class="sxs-lookup"><span data-stu-id="7c2fb-265">User information in the Address Book Service is not updated after the distinguished name for the user is modified in Active Directory</span></span>

<span data-ttu-id="7c2fb-266">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-266">**Issue:**</span></span>

<span data-ttu-id="7c2fb-267">Se o nome diferenciado de um usuário (também conhecido como DN) for alterado nos serviços de domínio do Active Directory, as alterações adicionais não serão atualizadas no ABS (serviço de catálogo de endereços).</span><span class="sxs-lookup"><span data-stu-id="7c2fb-267">If a user’s distinguished name (also known as DN) is changed in Active Directory Domain Services, any additional changes will not be updated in the Address Book Service (ABS).</span></span> <span data-ttu-id="7c2fb-268">Isso não afeta a entrada ou a presença do usuário, mas impedirá a comunicação do usuário se o endereço SIP também for alterado, pois as pesquisas retornarão um endereço SIP desatualizado.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-268">This does not affect sign-in or presence for the user, but it will prevent communication for the user if the SIP address is also changed, because searches will return an outdated SIP address.</span></span>

<span data-ttu-id="7c2fb-269">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-269">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-270">Para contornar esse problema, não altere o DN de um usuário.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-270">To work around this issue, do not change a user’s DN.</span></span> <span data-ttu-id="7c2fb-271">Se você reverter o DN para o usuário para o valor anterior, as atualizações serão refletidas no serviço de catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-271">If you revert the DN for the user to the previous value, updates will be reflected in the Address Book Service.</span></span>

</div>

</div>

<span id="Installation"></span>

<div>

## <a name="installation"></a><span data-ttu-id="7c2fb-272">Instalação</span><span class="sxs-lookup"><span data-stu-id="7c2fb-272">Installation</span></span>

<div>

## <a name="using-non-ascii-characters-may-result-in-lync-server-failing-to-start"></a><span data-ttu-id="7c2fb-273">O uso de caracteres não ASCII pode resultar em falha na inicialização do Lync Server</span><span class="sxs-lookup"><span data-stu-id="7c2fb-273">Using non-ASCII characters may result in Lync server failing to start</span></span>

<span data-ttu-id="7c2fb-274">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-274">**Issue:**</span></span>

<span data-ttu-id="7c2fb-275">A instalação falhará se o nome da pasta de destino incluir caracteres não-ASCII (incluindo UNICODE, conjunto de caracteres de byte duplo (DBCS), UTF-8 e UTF-16).</span><span class="sxs-lookup"><span data-stu-id="7c2fb-275">Setup will fail if the destination folder name includes non-ASCII characters (including UNICODE, double-byte character set (DBCS), UTF-8, and UTF-16).</span></span> <span data-ttu-id="7c2fb-276">Além disso, a instalação pode ser bem-sucedida, mas o servidor não iniciará se os caracteres não-ASCII estiverem contidos em qualquer um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="7c2fb-276">In addition, Setup may succeed but the server will not start if non-ASCII characters are contained in any of the following:</span></span>

  - <span data-ttu-id="7c2fb-277">Nome do computador</span><span class="sxs-lookup"><span data-stu-id="7c2fb-277">Computer name</span></span>

  - <span data-ttu-id="7c2fb-278">Nome de domínio</span><span class="sxs-lookup"><span data-stu-id="7c2fb-278">Domain name</span></span>

  - <span data-ttu-id="7c2fb-279">Nome de usuário</span><span class="sxs-lookup"><span data-stu-id="7c2fb-279">User name</span></span>

  - <span data-ttu-id="7c2fb-280">URI do SIP do usuário</span><span class="sxs-lookup"><span data-stu-id="7c2fb-280">User SIP URI</span></span>

  - <span data-ttu-id="7c2fb-281">Nome da conta de serviço</span><span class="sxs-lookup"><span data-stu-id="7c2fb-281">Service account name</span></span>

<span data-ttu-id="7c2fb-282">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-282">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-283">Use apenas caracteres ASCII no nome da pasta de destino, nome do computador, nome do domínio, nome do usuário, URI do SIP do usuário e nomes da conta de serviço.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-283">Use only ASCII characters in the destination folder name, computer name, domain name, user name, user SIP URI, and service account names.</span></span>

</div>

<div>

## <a name="the-hotfix-for-heap-corruption-occurs-when-a-module-calls-the-insertentitybody-method-in-iis-75-must-be-installed-prior-to-installing-lync-server-2013"></a><span data-ttu-id="7c2fb-284">O hotfix para "a corrupção de pilha ocorre quando um módulo chama o método InsertEntityBody no IIS 7,5" deve ser instalado antes da instalação do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c2fb-284">The hotfix for "Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5" must be installed prior to installing Lync Server 2013</span></span>

<span data-ttu-id="7c2fb-285">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-285">**Issue:**</span></span>

<span data-ttu-id="7c2fb-286">O hotfix para "a corrupção de pilha ocorre quando um módulo chama o método InsertEntityBody no IIS 7,5[https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)" (), descrito no artigo da base de[https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603)dados de conhecimento da Microsoft 264886 (), deve ser instalado antes da instalação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-286">The hotfix for "Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5" ([https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)), described in Microsoft Knowledge Base article 264886 ([https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603)), must be installed prior to installing Lync Server 2013.</span></span>

<span data-ttu-id="7c2fb-287">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-287">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-288">Baixe e instale o hotfix do centro de download da Microsoft [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)em.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-288">Download and install the hotfix from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602).</span></span>

</div>

<div>

## <a name="lync-server-2013-fails-to-install-on-ita-windows-server-2012-os-rtm-version"></a><span data-ttu-id="7c2fb-289">Lync Server 2013 falha ao instalar no ITA Windows Server 2012 so versão RTM</span><span class="sxs-lookup"><span data-stu-id="7c2fb-289">Lync Server 2013 fails to install on ITA Windows Server 2012 OS RTM version</span></span>

<span data-ttu-id="7c2fb-290">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-290">**Issue:**</span></span>

<span data-ttu-id="7c2fb-291">A instalação do Lync Server 2013 falha no ITA do Windows Server 2012 devido à falha na instalação do Windows Fabric.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-291">Lync Server 2013 installation fails on ITA Windows Server 2012 due to Windows Fabric installation failing.</span></span>

<span data-ttu-id="7c2fb-292">A instalação do Windows Fabric falha porque os rastreamentos de malha são criados com o formato de hora de HH: MM: SS.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-292">Windows Fabric installation fails because fabric traces are created with the time format of HH:MM:SS.</span></span> <span data-ttu-id="7c2fb-293">No entanto, no Windows Server ITA, o formato de hora é HH. MM.SS.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-293">However, in ITA Windows Server, the time format is HH.MM.SS.</span></span>

<span data-ttu-id="7c2fb-294">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-294">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-295">Para contornar esse problema, atualize o registro do sistema antes de instalar o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-295">To work around this issue, update the system registry before installing Lync Server 2013.</span></span> <span data-ttu-id="7c2fb-296">A chave do registro que precisa ser atualizada é: HKEY\_Users\\. STimeFormat\\internacional\\do\\painel de controle padrão.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-296">The registry key that needs to be updated is: HKEY\_USERS\\.DEFAULT\\Control Panel\\International\\sTimeFormat.</span></span> <span data-ttu-id="7c2fb-297">Altere o valor de sTimeFormat para HH: mm: SS usando a interface de linha de comando do Windows PowerShell da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="7c2fb-297">Change the value of sTimeFormat to HH:mm:ss by using the Windows PowerShell command-line interface as follows:</span></span>

1.  <span data-ttu-id="7c2fb-298">Inicie o Windows PowerShell e execute os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="7c2fb-298">Start Windows PowerShell and run the following cmdlets:</span></span>
    
       ```PowerShell
        New-PSDrive -Name HKU -PSProvider Registry -Root HKEY_USERS
       ```
    
       ```PowerShell
        $a="HKU:\.Default\Control Panel\International"
       ```

2.  <span data-ttu-id="7c2fb-299">Para exibir o valor atual, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="7c2fb-299">To view the current value, run the following cmdlet:</span></span>
    
        Get-itemproperty $a -Name sTimeFormat
    
    <span data-ttu-id="7c2fb-300">Anote o valor atual de sTimeFormat para que ele possa ser restaurado após a conclusão da instalação.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-300">Make note of the current value for sTimeFormat so it can be restored after the installation is complete.</span></span>

3.  <span data-ttu-id="7c2fb-301">Para definir o novo valor, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="7c2fb-301">To set to new value, run the following cmdlet:</span></span>
    
        Set-ItemProperty $a -Name sTimeFormat -Value "HH:mm:ss"

4.  <span data-ttu-id="7c2fb-302">Após a instalação bem-sucedida do Lync Server 2013, restaure o valor original do sTimeFormat executando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="7c2fb-302">After Lync Server 2013 has been successfully installed, restore the original value for the sTimeFormat by running the following cmdlet:</span></span>
    
        - <span data-ttu-id="7c2fb-303">Set-ItemProperty $a-Name sTimeFormat-Value "<valor observado na etapa 3.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-303">Set-ItemProperty $a -Name sTimeFormat -Value "<Value noted down in Step 3.</span></span> <span data-ttu-id="7c2fb-304">> acima "</span><span class="sxs-lookup"><span data-stu-id="7c2fb-304">above>"</span></span>

</div>

</div>

<span id="Mobility"></span>

<div>

## <a name="mobility"></a><span data-ttu-id="7c2fb-305">Movimentação</span><span class="sxs-lookup"><span data-stu-id="7c2fb-305">Mobility</span></span>

<div>

## <a name="issues-for-mobile-clients-during-the-server-failover-process"></a><span data-ttu-id="7c2fb-306">Problemas para clientes móveis durante o processo de failover do servidor</span><span class="sxs-lookup"><span data-stu-id="7c2fb-306">Issues for mobile clients during the server failover process</span></span>

<span data-ttu-id="7c2fb-307">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-307">**Issue:**</span></span>

<span data-ttu-id="7c2fb-308">Quando um Lync Server falha e o processo de failover é iniciado, os seguintes problemas podem afetar os usuários do cliente móvel:</span><span class="sxs-lookup"><span data-stu-id="7c2fb-308">When a Lync Server fails and the failover process begins, the following issues may affect mobile client users:</span></span>

  - <span data-ttu-id="7c2fb-309">Nenhuma chamada ou sinal de entrada do Lync para até 10 minutos após o início do failover.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-309">No incoming Lync call or signal for up to 10 minutes after failover begins.</span></span>

  - <span data-ttu-id="7c2fb-310">Não é possível aceitar solicitações de chat de entrada</span><span class="sxs-lookup"><span data-stu-id="7c2fb-310">Cannot accept incoming Chat requests</span></span>

  - <span data-ttu-id="7c2fb-311">Não é possível ingressar em reuniões se o servidor com falha for o servidor local do usuário</span><span class="sxs-lookup"><span data-stu-id="7c2fb-311">Cannot join meetings if the failed server is the home server for the user</span></span>

<span data-ttu-id="7c2fb-312">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-312">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-313">Não há solução para esse problema.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-313">There is no workaround for this issue.</span></span> <span data-ttu-id="7c2fb-314">A funcionalidade normal será restaurada após a conclusão do processo de failover.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-314">Normal functionality will be restored once the failover process is complete.</span></span>

</div>

<div>

## <a name="if-a-mobile-user-declines-an-incoming-call-from-another-lync-endpoint-the-call-is-displayed-as-a-missed-conversion-on-lync-mobile-clients"></a><span data-ttu-id="7c2fb-315">Se um usuário móvel recusar uma chamada de entrada de outro ponto de extremidade do Lync, a chamada será exibida como uma conversão perdida nos clientes móveis do Lync</span><span class="sxs-lookup"><span data-stu-id="7c2fb-315">If a mobile user declines an incoming call from another Lync endpoint, the call is displayed as a missed conversion on Lync Mobile clients</span></span>

<span data-ttu-id="7c2fb-316">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-316">**Issue:**</span></span>

<span data-ttu-id="7c2fb-317">Se um usuário móvel recusar uma chamada de entrada e a chamada tiver originado de outro ponto de extremidade do Lync, a chamada será exibida como uma conversa perdida no cliente móvel do Lync, em vez de uma chamada na lista de chamadas de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-317">If a mobile user declines an incoming call, and the call originated from another Lync endpoint, the call is displayed as a missed conversation in the Lync Mobile client instead of a call in the device call list.</span></span>

<span data-ttu-id="7c2fb-318">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-318">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-319">Não há solução para esse problema.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-319">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="the-mobile-client-may-not-display-a-federated-contacts-display-name-when-searching-for-contacts"></a><span data-ttu-id="7c2fb-320">O cliente móvel pode não exibir o nome de exibição de um contato federado ao pesquisar contatos</span><span class="sxs-lookup"><span data-stu-id="7c2fb-320">The mobile client may not display a federated contact’s display name when searching for contacts</span></span>

<span data-ttu-id="7c2fb-321">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-321">**Issue:**</span></span>

<span data-ttu-id="7c2fb-322">O nome para exibição de contatos federados pode não ser exibido em alguns cenários, como a pesquisa de um contato federado na lista de contatos.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-322">The display name for federated contacts may not be displayed in some scenarios, such as when searching for a federated contact in the contact list.</span></span> <span data-ttu-id="7c2fb-323">Isso pode ocorrer quando não há nenhuma assinatura de presença ativa para o contato do cliente móvel do Lync.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-323">This can occur when the there is no active presence subscription for the contact from the Lync mobile client.</span></span>

<span data-ttu-id="7c2fb-324">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-324">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-325">Não há solução para esse problema.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-325">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="in-the-mobile-client-invitee-and-timestamp-information-are-missing-from-a-missed-conversation-that-is-an-invitation-to-a-conference"></a><span data-ttu-id="7c2fb-326">No cliente móvel, as informações de convidado e carimbo de data/hora estão ausentes de uma conversa perdida que é um convite para uma conferência</span><span class="sxs-lookup"><span data-stu-id="7c2fb-326">In the mobile client, invitee and timestamp information are missing from a missed conversation that is an invitation to a conference</span></span>

<span data-ttu-id="7c2fb-327">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-327">**Issue:**</span></span>

<span data-ttu-id="7c2fb-328">No cliente móvel, quando uma conversa perdida é um convite para uma conferência, as informações do convidado e do carimbo de data/hora estão ausentes da mensagem de conversa perdida.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-328">In the mobile client, when a missed conversation is an invitation to a conference, the invitee and timestamp information is missing from the missed conversation message.</span></span>

<span data-ttu-id="7c2fb-329">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-329">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-330">Não há solução para esse problema.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-330">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="mobile-client-users-making-calls-using-voip-are-not-be-able-to-leave-voice-mail-for-users-whose-voice-mail-is-configured-in-exchange-2010-or-earlier-versions"></a><span data-ttu-id="7c2fb-331">Os usuários móveis de clientes que fazem chamadas usando VoIP não podem deixar a caixa postal para os usuários cujas mensagens de voz estão configuradas no Exchange 2010 ou versões anteriores</span><span class="sxs-lookup"><span data-stu-id="7c2fb-331">Mobile client users making calls using VoIP are not be able to leave voice mail for users whose voice mail is configured in Exchange 2010 or earlier versions</span></span>

<span data-ttu-id="7c2fb-332">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-332">**Issue:**</span></span>

<span data-ttu-id="7c2fb-333">Se um usuário de cliente móvel estiver usando VoIP para fazer chamadas, o usuário não poderá deixar mensagens de caixa postal para usuários configurados para usar a caixa postal no Microsoft Exchange Server 2007 ou no Microsoft Exchange Server 2010.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-333">If a mobile client user is using VoIP to place calls, the user will not be able to leave voice mail messages for users configured to use voice mail in Microsoft Exchange Server 2007 or Microsoft Exchange Server 2010.</span></span>

<span data-ttu-id="7c2fb-334">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-334">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-335">Para contornar esse problema, use o Exchange 2010 com SP1 ou versão posterior do Microsoft Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-335">To work around this issue, use Exchange 2010 with SP1 or later version of Microsoft Exchange Server.</span></span>

</div>

<div>

## <a name="when-using-block-with-url-for-client-version-configuration-on-mobile-clients-an-incorrect-error-message-may-be-displayed"></a><span data-ttu-id="7c2fb-336">Ao usar bloquear com URL para configuração de versão de cliente em clientes móveis, uma mensagem de erro incorreta pode ser exibida</span><span class="sxs-lookup"><span data-stu-id="7c2fb-336">When using Block with URL for Client Version Configuration on mobile clients, an incorrect error message may be displayed</span></span>

<span data-ttu-id="7c2fb-337">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-337">**Issue:**</span></span>

<span data-ttu-id="7c2fb-338">Ao usar **Bloquear com URL** para configuração de versão de cliente em clientes móveis, uma mensagem de erro incorreta pode ser exibida quando a versão do cliente não é suportada.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-338">When using **Block with URL** for Client Version Configuration on mobile clients, an incorrect error message may be displayed when the client version is not supported.</span></span>

<span data-ttu-id="7c2fb-339">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-339">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-340">Para contornar esse problema, configure a configuração de versão do cliente para usar **Bloquear** em vez de **Bloquear com URL**.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-340">To work around this issue, configure Client Version Configuration to use **Block** instead of **Block with URL**.</span></span>

</div>

</div>

<span id="Conferencing"></span>

<div>

## <a name="conferencing"></a><span data-ttu-id="7c2fb-341">Conferências</span><span class="sxs-lookup"><span data-stu-id="7c2fb-341">Conferencing</span></span>

<div>

## <a name="antivirus-software-running-on-lync-server-2013front-end-servers-can-cause-application-domain-recycling-which-temporarily-interrupts-service-for-lync-web-app-2013-lync-mobile-2010-and-lync-mobile-2013-clients"></a><span data-ttu-id="7c2fb-342">O software antivírus executado nos servidores front-end do Lync Server 2013 pode causar a reciclagem do domínio do aplicativo, que interrompe temporariamente o serviço para os clientes do Lync Web App 2013, Lync Mobile 2010 e Lync Mobile 2013</span><span class="sxs-lookup"><span data-stu-id="7c2fb-342">Antivirus software running on Lync Server 2013 Front End Servers can cause Application Domain recycling, which temporarily interrupts service for Lync Web App 2013, Lync Mobile 2010, and Lync Mobile 2013 clients</span></span>

<span data-ttu-id="7c2fb-343">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-343">**Issue:**</span></span>

<span data-ttu-id="7c2fb-344">O software antivírus pode acionar reinicializações de domínio de aplicativo, o que pode resultar em aplicativos de cliente de API da Web do Lync Mobility Service 2013 e UC (comunicações unificadas) (Lync Web App 2013, Lync Mobile 2010 e Lync Mobile 2013) para perder o estado.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-344">Antivirus software can trigger application domain restarts, which can result in Lync Mobility Service 2013 and unified communications (UC) Web API client applications (Lync Web App 2013, Lync Mobile 2010, and Lync Mobile 2013) to lose their state.</span></span>

<span data-ttu-id="7c2fb-345">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-345">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-346">Para contornar esse problema, exclua as pastas que contêm os componentes Web e o .NET Framework da verificação antivírus.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-346">To work around this issue, exclude the folders containing Web components and .NET framework from antivirus scanning.</span></span> <span data-ttu-id="7c2fb-347">Para obter detalhes, consulte o artigo 312592 da base de dados de conhecimento da Microsoft, "PRB: reinicializações aleatórias do aplicativo com o erro" o [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592)aplicativo está reiniciando "no ASP.net" em.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-347">For details, see Microsoft Knowledge Base article 312592, "PRB: Random application restarts with 'Application is restarting' error in ASP.NET," at [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592).</span></span>

<span data-ttu-id="7c2fb-348">As pastas a seguir devem ser excluídas:</span><span class="sxs-lookup"><span data-stu-id="7c2fb-348">The following folders should be excluded:</span></span>

  - <span data-ttu-id="7c2fb-349">% ProgramFiles\\% Microsoft Lync Server\\2013 Web\\Components MCX\\ext</span><span class="sxs-lookup"><span data-stu-id="7c2fb-349">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Mcx\\Ext</span></span>

  - <span data-ttu-id="7c2fb-350">% ProgramFiles\\% Microsoft Lync Server\\2013 Web\\Components MCX\\int</span><span class="sxs-lookup"><span data-stu-id="7c2fb-350">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Mcx\\Int</span></span>

  - <span data-ttu-id="7c2fb-351">% ProgramFiles\\% Microsoft Lync Server\\2013 Web\\Components Ucwa\\int</span><span class="sxs-lookup"><span data-stu-id="7c2fb-351">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Ucwa\\Int</span></span>

  - <span data-ttu-id="7c2fb-352">% ProgramFiles\\% Microsoft Lync Server\\2013 Web\\Components Ucwa\\ext</span><span class="sxs-lookup"><span data-stu-id="7c2fb-352">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Ucwa\\Ext</span></span>

  - <span data-ttu-id="7c2fb-353">% WINDIR%\\Microsoft.NET\\Framework64\\v 4.0.30319\\config</span><span class="sxs-lookup"><span data-stu-id="7c2fb-353">%Windir%\\Microsoft.NET\\Framework64\\v4.0.30319\\Config</span></span>

</div>

<div>

## <a name="activex-controls-or-native-xmlhttp-support-must-be-enabled-in-windows-internet-explorer-to-successfully-join-conferences"></a><span data-ttu-id="7c2fb-354">Os controles ActiveX ou o suporte a XMLHTTP nativo devem estar habilitados no Windows Internet Explorer para ingressar em conferências com êxito</span><span class="sxs-lookup"><span data-stu-id="7c2fb-354">ActiveX Controls or native XMLHTTP support must be enabled in Windows Internet Explorer to successfully join conferences</span></span>

<span data-ttu-id="7c2fb-355">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-355">**Issue:**</span></span>

<span data-ttu-id="7c2fb-356">Se um usuário desabilitou os controles ActiveX e o suporte a XMLHTTP nativo nas configurações de navegador da Internet do Windows Internet Explorer, o usuário não poderá participar de uma reunião se o Internet Explorer estiver selecionado como navegador padrão.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-356">If a user has disabled both ActiveX Controls and native XMLHTTP support in Windows Internet Explorer Internet browser settings, the user will not be able to join a meeting if Internet Explorer is selected as the default browser.</span></span>

<span data-ttu-id="7c2fb-357">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-357">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-358">Habilite controles ActiveX ou "suporte ao XMLHTTP nativo" no Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-358">Enable either ActiveX Controls or "native XMLHTTP support" in Internet Explorer.</span></span>

</div>

<div>

## <a name="lync-server-web-conferencing-service-cannot-recover-from-critical-mode"></a><span data-ttu-id="7c2fb-359">O serviço de conferência da Web do Lync Server não pode se recuperar do modo crítico</span><span class="sxs-lookup"><span data-stu-id="7c2fb-359">Lync Server Web Conferencing service cannot recover from critical mode</span></span>

<span data-ttu-id="7c2fb-360">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-360">**Issue:**</span></span>

<span data-ttu-id="7c2fb-361">Se o modo crítico for habilitado para arquivamento, em caso de falhas no sistema, o modo crítico será iniciado e as conferências não funcionarão mais para os participantes.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-361">If critical mode is turned for archiving, in case of system failures, critical mode will start and the conferences will no longer work for the participants.</span></span> <span data-ttu-id="7c2fb-362">Depois que o administrador corrige as falhas do sistema (como correção de um problema de banco de dados), o serviço de audioconferência não recupera automaticamente e o administrador deve reiniciar manualmente o serviço de conferência para que a conferência continue.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-362">After the administrator fixes the system failures (such as fixing a database issue), the data conferencing service doesn't automatically recover, and the administrator must manually restart the conferencing service for conferencing to resume.</span></span>

<span data-ttu-id="7c2fb-363">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-363">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-364">Um administrador precisa reiniciar manualmente o serviço de conferência após a correção da falha do sistema.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-364">An administrator needs to manually restart the conferencing service after the system failure is fixed.</span></span>

</div>

<div>

## <a name="web-conferencing-service-ignores-the-http-proxy-for-external-office-web-app-servers"></a><span data-ttu-id="7c2fb-365">O serviço de Webconferência ignora o proxy HTTP para servidores do Office Web App externos</span><span class="sxs-lookup"><span data-stu-id="7c2fb-365">Web Conferencing service ignores the HTTP proxy for external Office Web App Servers</span></span>

<span data-ttu-id="7c2fb-366">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-366">**Issue:**</span></span>

<span data-ttu-id="7c2fb-367">Se você tiver implantado um servidor do Office Web Apps externo para o serviço de Webconferência (ou seja, um servidor que não esteja na rede corporativa interna) na Internet, na rede de perímetro e o serviço de Webconferência exigir um proxy HTTP para se conectar a isso, o A descoberta do servidor do Office Web Apps falhará.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-367">If you have deployed an Office Web Apps Server external to the Web Conferencing service (that is, a server that is not in the internal corporate network) in the Internet, perimeter network, and the Web Conferencing service requires an HTTP proxy to connect to this, the Office Web Apps Server discovery will fail.</span></span> <span data-ttu-id="7c2fb-368">O serviço de Webconferência ignora a configuração de proxy HTTP, conforme definido no construtor de topologias para a instalação do servidor do Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-368">The Web Conferencing service ignores the HTTP proxy setting, as defined in Topology Builder for Office Web Apps Server setup.</span></span> <span data-ttu-id="7c2fb-369">Como resultado, o cliente do Lync não poderá fazer o compartilhamento do Microsoft PowerPoint 2010 com outros participantes na conferência.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-369">As a result, the Lync client will not be able to do Microsoft PowerPoint 2010 sharing with other participants in the conference.</span></span> <span data-ttu-id="7c2fb-370">Se você estiver instalando o Lync Server local e também configurar o servidor do Office Web Apps no local na rede interna, não será necessária uma configuração de proxy.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-370">If you are installing Lync Server on-premises and also configure Office Web Apps Server on-premises in the internal network, a proxy configuration is not required.</span></span>

<span data-ttu-id="7c2fb-371">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-371">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-372">A única solução alternativa é não ter uma configuração de implantação que exija o uso do proxy HTTP para se comunicar com um servidor externo do Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-372">The only workaround is to not have a deployment configuration that requires the use of HTTP proxy to communicate with an external Office Web Apps Server.</span></span>

</div>

<div>

## <a name="adding-video-to-an-audio-conferencing-provider-conference-is-not-supported"></a><span data-ttu-id="7c2fb-373">A adição de vídeo a uma conferência de provedor de audioconferência não é suportada</span><span class="sxs-lookup"><span data-stu-id="7c2fb-373">Adding video to an audio conferencing provider conference is not supported</span></span>

<span data-ttu-id="7c2fb-374">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-374">**Issue:**</span></span>

<span data-ttu-id="7c2fb-375">A adição de um vídeo não é suportada se o usuário fizer parte de uma conferência de provedor de audioconferência para áudio.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-375">Adding a video is not supported if the user is joined to an audio conferencing provider conference for audio.</span></span>

<span data-ttu-id="7c2fb-376">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-376">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-377">Não há solução para esse problema.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-377">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="topologies-with-ipv6-enabled-force-the-lync-web-app-silverlight-plug-in-auto-update-to-ensure-screen-sharing-functionality-can-work-from-lync-web-app"></a><span data-ttu-id="7c2fb-378">Topologias com IPv6 habilitado forçar a atualização automática do plug-in do Lync Web App Silverlight para garantir que a funcionalidade de compartilhamento de tela possa funcionar no Lync Web App</span><span class="sxs-lookup"><span data-stu-id="7c2fb-378">Topologies with IPv6 enabled force the Lync Web App Silverlight plug-in auto-update to ensure screen sharing functionality can work from Lync Web App</span></span>

<span data-ttu-id="7c2fb-379">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-379">**Issue:**</span></span>

<span data-ttu-id="7c2fb-380">Quando uma topologia é configurada com IPv6 habilitado, os usuários não podem compartilhar sua tela do cliente do Lync Web App se uma versão anterior do plug-in de compartilhamento de tela já estiver instalada.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-380">When a topology is configured with IPv6 enabled, users cannot share their screen from the Lync Web App client if an earlier version of the screen-sharing plug-in is already installed.</span></span>

<span data-ttu-id="7c2fb-381">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-381">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-382">Para forçar uma atualização para a versão mais recente do plug-in de compartilhamento de tela ao ingressar na reunião via Lync Web App, modifique o valor de **MinSupportedBuildVersion** de "4.0.7457.0" para "4.0.7577.380" em ambos os arquivos a seguir:</span><span class="sxs-lookup"><span data-stu-id="7c2fb-382">To force an update to the most recent version of the screen-sharing plug-in when joining meeting via Lync Web App, modify the value of **MinSupportedBuildVersion** from "4.0.7457.0" to "4.0.7577.380" in both of the following files:</span></span>

  - <span data-ttu-id="7c2fb-383">% ProgramFiles\\% Microsoft Lync Server\\15 Web\\Components REACH\\plug\\-ins do cliente\\\\int ReachAppShPluginProperties. xml</span><span class="sxs-lookup"><span data-stu-id="7c2fb-383">%ProgramFiles%\\Microsoft Lync Server 15\\Web Components\\Reach\\Int\\Client\\Plugins\\ReachAppShPluginProperties.xml</span></span>

  - <span data-ttu-id="7c2fb-384">% ProgramFiles\\% Microsoft Lync Server\\15 Web\\Components\\atingem\\plug-ins do\\cliente\\ReachAppShPluginProperties. xml</span><span class="sxs-lookup"><span data-stu-id="7c2fb-384">%ProgramFiles%\\Microsoft Lync Server 15\\Web Components\\Reach\\Ext\\Client\\Plugins\\ReachAppShPluginProperties.xml</span></span>

</div>

</div>

<span id="EnterpriseVoice"></span>

<div>

## <a name="enterprise-voice"></a><span data-ttu-id="7c2fb-385">Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="7c2fb-385">Enterprise Voice</span></span>

<div>

## <a name="in-some-cases-a-lync-client-running-on-a-computer-configured-to-use-ipv4-and-ipv6-dual-stack-might-not-support-capabilities-that-rely-in-the-ip-subnet-of-the-computer-such-as-e911-media-bypass-call-admission-control-and-location-based-routing"></a><span data-ttu-id="7c2fb-386">Em alguns casos, um cliente do Lync executando em um computador configurado para usar a pilha Dual IPv4 e IPv6 pode não oferecer suporte a recursos que dependem da sub-rede IP do computador, como E911, bypass de mídia, controle de admissão de chamadas e roteamento baseado em local</span><span class="sxs-lookup"><span data-stu-id="7c2fb-386">In some cases, a Lync client running on a computer configured to use IPv4 and IPv6 dual stack might not support capabilities that rely in the IP subnet of the computer such as E911, Media Bypass, Call Admission Control and Location Based Routing</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="7c2fb-387">As informações contidas nesta seção pertencem às atualizações cumulativas do Lync Server 2013:2013 de fevereiro.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-387">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="7c2fb-388">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-388">**Issue:**</span></span>

<span data-ttu-id="7c2fb-389">Quando um cliente Lync está sendo executado em um computador que está habilitado para a pilha Dual IPv4 e IPv6 e com base na resolução DNS do servidor proxy, o cliente pode usar o endereço IPv6 do computador para entrar.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-389">When a Lync client is running on a computer that is enabled for IPv4 and IPv6 dual stack and based on the DNS resolution of the proxy server, the client may use the IPv6 address of the computer to sign in.</span></span> <span data-ttu-id="7c2fb-390">Depois disso, o cliente do Lync suportará apenas os recursos suportados para IPv6, que excluirá E911, bypass de mídia, controle de admissão de chamada e roteamento baseado em local.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-390">After doing so, the Lync Client will support only the capabilities supported for IPv6, which excludes E911, Media Bypass, Call Admission Control and Location Based Routing.</span></span>

<span data-ttu-id="7c2fb-391">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-391">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-392">Para contornar esse problema, desative o suporte a IPv6 no computador cliente.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-392">To work around this issue, disable IPv6 support on the client computer.</span></span>

</div>

<div>

## <a name="if-enterprise-voice-is-not-configured-for-a-user-the-user-will-need-to-use-e164-format-to-dial-out-from-a-conference"></a><span data-ttu-id="7c2fb-393">Se o Enterprise Voice não estiver configurado para um usuário, o usuário deverá usar o formato e164 para discar de uma conferência</span><span class="sxs-lookup"><span data-stu-id="7c2fb-393">If Enterprise Voice is not configured for a user, the user will need to use E164 format to dial out from a conference</span></span>

<span data-ttu-id="7c2fb-394">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-394">**Issue:**</span></span>

<span data-ttu-id="7c2fb-395">Se o Enterprise Voice não estiver configurado para um usuário, esse usuário precisará usar o formato e164 para discar com êxito de uma conferência.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-395">If Enterprise Voice is not configured for a user, that user will need to use the E164 format to successfully dial out from a conference.</span></span> <span data-ttu-id="7c2fb-396">Se o formato e164 não for usado, o usuário não poderá discar da conferência.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-396">If the E164 format is not used, the user will not be able to dial out from the conference.</span></span>

<span data-ttu-id="7c2fb-397">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-397">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-398">Para contornar esse problema, os usuários que não estão habilitados para o Enterprise Voice devem discar de uma conferência usando números no formato e164.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-398">To work around this issue, users who are not enabled for Enterprise Voice should dial out from a conference by using numbers in the E164 format.</span></span>

</div>

</div>

<span id="Presence"></span>

<div>

## <a name="presence"></a><span data-ttu-id="7c2fb-399">Presença</span><span class="sxs-lookup"><span data-stu-id="7c2fb-399">Presence</span></span>

<div>

## <a name="if-a-user-has-selected-block-all-invites-and-communications-while-the-unified-contact-store-is-turned-on-for-the-user-presence-status-is-not-rejected-when-it-should-be"></a><span data-ttu-id="7c2fb-400">Se um usuário selecionar "bloquear todos os convites e comunicações" enquanto o repositório de contato unificado estiver ativado para o usuário, o status de presença não será rejeitado quando deveria</span><span class="sxs-lookup"><span data-stu-id="7c2fb-400">If a user has selected "Block all invites and communications" while the unified contact store is turned on for the user, Presence status is not rejected when it should be</span></span>

<span data-ttu-id="7c2fb-401">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-401">**Issue:**</span></span>

<span data-ttu-id="7c2fb-402">Se um usuário selecionar "bloquear todos os convites e comunicações" enquanto o repositório de contato unificado estiver ativado para o usuário, o status de presença não será rejeitado quando deveria.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-402">If a user has selected "Block all invites and communications" while the unified contact store is turned on for the user, Presence status is not rejected when it should be.</span></span>

<span data-ttu-id="7c2fb-403">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-403">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-404">Para contornar esse problema, você pode desativar o repositório unificado de contatos para o usuário.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-404">To work around this issue, you can turn off the unified contact store for the user.</span></span> <span data-ttu-id="7c2fb-405">Para fazer isso, execute os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="7c2fb-405">To do so, run the following cmdlets:</span></span>

    Set-CsUserServicesPolicy -Identity "<user display name>" -UcsAllowed $False

<span data-ttu-id="7c2fb-406">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="7c2fb-406">For example:</span></span>

    Set-CsUserServicesPolicy -Identity "Ken Myer" -UcsAllowed $False

</div>

<div>

## <a name="office-communications-server-2007-r2-users-homed-on-premises-are-not-able-to-see-the-presence-status-of-skype-for-business-online-users-in-hybrid-deployments---hybrid"></a><span data-ttu-id="7c2fb-407">Os usuários do Office Communications Server 2007 R2 hospedados no local não podem ver o status de presença de usuários do Skype for Business online em implantações híbridas-híbrido</span><span class="sxs-lookup"><span data-stu-id="7c2fb-407">Office Communications Server 2007 R2 users homed on-premises are not able to see the Presence status of Skype for Business Online users in hybrid deployments - Hybrid</span></span>

<span data-ttu-id="7c2fb-408">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-408">**Issue:**</span></span>

<span data-ttu-id="7c2fb-409">O problema pode ocorrer em uma implantação híbrida quando você está usando um diretor do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-409">The issue may occur in a hybrid deployment when you are using a Lync Server 2013 Director.</span></span>

<span data-ttu-id="7c2fb-410">O status de presença para usuários hospedados no Skype for Business Online é exibido como presença desconhecida para usuários locais.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-410">Presence status for users homed to Skype for Business Online is displayed as Presence Unknown for on-premises users.</span></span> <span data-ttu-id="7c2fb-411">Além disso, os usuários hospedados no Skype for Business online não podem ver o status de presença dos usuários locais do Office Communications Server R2.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-411">Also, users homed to Skype for Business Online are not able to see presence status for Office Communications Server R2 on-premises users.</span></span>

<span data-ttu-id="7c2fb-412">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-412">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-413">Para resolver esse problema parcialmente, altere o servidor local (msRTCSIP-presencehomeserver) dos usuários do Skype for Business online para apontar para um pool local do Lync Server 2013 em vez do diretor do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-413">To partially work around this issue, change the Home Server (msrtcsip-presencehomeserver) of the Skype for Business Online users to point to a Lync Server 2013 on-premises pool instead of the Lync Server 2013 Director.</span></span> <span data-ttu-id="7c2fb-414">Você pode modificar essa configuração no servidor front-end local.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-414">You can modify this setting on the on-premises Front End Server.</span></span>

<span data-ttu-id="7c2fb-415">Essa solução alternativa exibirá corretamente o status de presença de usuários hospedados no Office Communications Server 2007 R2 para os usuários do Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-415">This workaround will correctly display the Presence status of users homed to Office Communications Server 2007 R2 to Skype for Business Online users.</span></span>

</div>

</div>

<span id="ResponseGroup"></span>

<div>

## <a name="response-group-application-call-park-application-and-group-call-pickup"></a><span data-ttu-id="7c2fb-416">Aplicativo de grupo de resposta, aplicativo de estacionamento de chamada e recebimento de chamada em grupo</span><span class="sxs-lookup"><span data-stu-id="7c2fb-416">Response Group application, Call Park application, and Group Call Pickup</span></span>

<div>

## <a name="a-caller-might-hear-one-second-of-music-on-hold-during-the-establishment-of-a-call-with-the-retrieving-party"></a><span data-ttu-id="7c2fb-417">Um chamador pode ouvir um segundo de música em espera durante o estabelecimento de uma chamada com a parte de recuperação</span><span class="sxs-lookup"><span data-stu-id="7c2fb-417">A caller might hear one second of music-on-hold during the establishment of a call with the retrieving party</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="7c2fb-418">As informações contidas nesta seção pertencem às atualizações cumulativas do Lync Server 2013:2013 de fevereiro.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-418">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="7c2fb-419">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-419">**Issue:**</span></span>

<span data-ttu-id="7c2fb-420">Quando uma chamada é recuperada por recebimento de chamada em grupo, o chamador pode ouvir um segundo de música em espera durante o estabelecimento da chamada com o participante do recuperador.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-420">When a call is retrieved via Group Call Pickup, the caller might hear one second of music-on-hold during the establishment of the call with the retriever party.</span></span>

<span data-ttu-id="7c2fb-421">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-421">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-422">Não há solução para esse problema.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-422">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="a-response-group-agent-can-sign-in-and-sign-out-through-a-lync-server-2010-agent-console-to-lync-server-2010-formal-agent-groups-only"></a><span data-ttu-id="7c2fb-423">Um agente de grupo de resposta pode entrar e sair por meio de um console de agente do Lync Server 2010 para grupos de agente formal do Lync Server 2010 apenas</span><span class="sxs-lookup"><span data-stu-id="7c2fb-423">A Response Group agent can sign in and sign out through a Lync Server 2010 Agent Console to Lync Server 2010 formal Agent Groups only</span></span>

<span data-ttu-id="7c2fb-424">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-424">**Issue:**</span></span>

<span data-ttu-id="7c2fb-425">Um agente de grupo de resposta do Lync Server 2013 pode entrar e sair por meio de um console de agente do Lync Server 2010 para os grupos de agente formal do Lync Server 2010 apenas.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-425">A Lync Server 2013 Response Group agent can sign in and sign out through a Lync Server 2010 Agent Console to Lync Server 2010 formal Agent Groups only.</span></span> <span data-ttu-id="7c2fb-426">No console de agente do Lync Server 2010, os usuários podem ver apenas o grupo de resposta do Lync Server 2010 ao qual eles pertencem.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-426">In the Lync Server 2010 Agent Console, users can see only the Lync Server 2010 Response Group that they belong to.</span></span> <span data-ttu-id="7c2fb-427">Eles não podem ver qualquer um dos grupos de resposta do Lync Server 2013 aos quais eles pertencem.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-427">They cannot see any of the Lync Server 2013 Response Groups that they belong to.</span></span>

<span data-ttu-id="7c2fb-428">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-428">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-429">Se o agente de grupo de resposta for um usuário do Lync Server 2013 e parte de um grupo de agente formal do Lync Server 2013, o usuário deverá acessar o console de agente do Lync Server 2013 diretamente por meio de um link da Web em um navegador para entrar e sair de grupos de agentes do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-429">If the Response Group agent is a Lync Server 2013 user, and part of a Lync Server 2013 formal Agent Group, the user must access the Lync Server 2013 Agent Console directly via a web link in a browser to sign in to and sign out from Lync Server 2013 Agent Groups.</span></span>

</div>

<div>

## <a name="a-lync-server-2010response-group-agent-cannot-place-calls-on-behalf-of-a-lync-server-2013response-group"></a><span data-ttu-id="7c2fb-430">Um agente de grupo de resposta do Lync Server 2010 não pode fazer chamadas em nome de um grupo de resposta do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c2fb-430">A Lync Server 2010 Response Group agent cannot place calls on behalf of a Lync Server 2013 Response Group</span></span>

<span data-ttu-id="7c2fb-431">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-431">**Issue:**</span></span>

<span data-ttu-id="7c2fb-432">Um usuário do Lync Server 2010 que é um agente de um grupo de resposta do Lync Server 2013 não é capaz de fazer uma chamada em nome do grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-432">A Lync Server 2010 user who is an Agent of a Lync Server 2013 Response Group is not able to place a call on behalf of the Response Group.</span></span> <span data-ttu-id="7c2fb-433">O grupo de resposta do Lync Server 2013 não estará disponível no cliente do Lync para fazer uma chamada.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-433">The Lync Server 2013 Response Group will not be available in the Lync Client to place a call.</span></span>

<span data-ttu-id="7c2fb-434">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-434">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-435">Para contornar esse problema, você deve mover o usuário do Lync Server 2010 para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-435">To work around this issue, you must move the Lync Server 2010 user to Lync Server 2013.</span></span>

</div>

<div>

## <a name="removing-a-response-group-from-lync-server-2010-after-it-has-been-migrated-to-lync-server-2013-will-prevent-the-response-group-from-accepting-any-incoming-calls"></a><span data-ttu-id="7c2fb-436">Remover um grupo de resposta do Lync Server 2010 após a migração para o Lync Server 2013 impedirá que o grupo de resposta aceite qualquer chamada de entrada</span><span class="sxs-lookup"><span data-stu-id="7c2fb-436">Removing a Response Group from Lync Server 2010 after it has been migrated to Lync Server 2013 will prevent the Response Group from accepting any incoming calls</span></span>

<span data-ttu-id="7c2fb-437">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-437">**Issue:**</span></span>

<span data-ttu-id="7c2fb-438">Se um grupo de resposta que foi migrado do Lync Server 2010 para o Lync Server 2013 for removido do Lync Server 2010 através do painel de controle do Lync Server ou do Shell de gerenciamento do Lync Server, o grupo de resposta no Lync Server 2013 deixará de receber todas as chamadas de entrada.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-438">If a Response Group that has been migrated from Lync Server 2010 to Lync Server 2013 is removed from Lync Server 2010 through the Lync Server Control Panel or the Lync Server Management Shell, the Response Group in Lync Server 2013 will stop receiving any incoming calls.</span></span>

<span data-ttu-id="7c2fb-439">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-439">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-440">Para contornar esse problema, não remova nenhum grupo de resposta do Lync Server 2010 que tenha sido migrado do Lync Server 2010 para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-440">To work around this issue, do not remove any Response Groups from Lync Server 2010 that have been migrated from Lync Server 2010 to Lync Server 2013.</span></span>

<span data-ttu-id="7c2fb-441">Se o grupo de resposta já tiver sido removido, você deverá reimplantá-lo no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-441">If the Response Group has already been removed, you should redeploy it in Lync Server 2013.</span></span>

</div>

<div>

## <a name="when-a-new-managed-workflow-is-set-to-inactive-when-created-deployment-of-the-workflow-will-fail"></a><span data-ttu-id="7c2fb-442">Quando um novo fluxo de trabalho gerenciado é definido como inativo quando criado, a implantação do fluxo de trabalho falhará</span><span class="sxs-lookup"><span data-stu-id="7c2fb-442">When a new managed workflow is set to inactive when created, deployment of the workflow will fail</span></span>

<span data-ttu-id="7c2fb-443">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-443">**Issue:**</span></span>

<span data-ttu-id="7c2fb-444">Quando um novo fluxo de trabalho gerenciado é definido como inativo quando criado, a implantação do fluxo de trabalho falhará.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-444">When a new managed workflow is set to inactive when created, deployment of the workflow will fail.</span></span> <span data-ttu-id="7c2fb-445">Esse problema é encontrado quando o fluxo de trabalho é definido como inativo quando criado, mas não afeta um fluxo de trabalho que é editado para configurá-lo como inativo após ter sido implantado.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-445">This issue is encountered when the workflow is set to inactive when created, but does not affect a workflow that is edited to set it to inactive after is has been deployed.</span></span>

<span data-ttu-id="7c2fb-446">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-446">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-447">Ao criar e implantar um fluxo de trabalho, defina o fluxo de trabalho como ativo e implante-o.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-447">When creating and deploying a workflow, set the workflow as active and then deploy it.</span></span> <span data-ttu-id="7c2fb-448">Depois que o fluxo de trabalho é implantado com êxito, o fluxo de trabalho pode ser editado e definido como inativo.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-448">After the workflow is successfully deployed, the workflow can be edited and set to inactive.</span></span>

</div>

<div>

## <a name="removing-a-response-group-from-the-owner-pool-will-prevent-the-response-group-of-the-backup-pool-from-accepting-any-incoming-calls-during-failover-if-the-response-group-has-been-imported-to-the-backup-pool"></a><span data-ttu-id="7c2fb-449">Remover um grupo de resposta do pool proprietário impedirá que o grupo de resposta do pool de backup aceite quaisquer chamadas de entrada durante o failover se o grupo de resposta tiver sido importado para o pool de backup</span><span class="sxs-lookup"><span data-stu-id="7c2fb-449">Removing a Response Group from the Owner pool will prevent the Response Group of the Backup pool from accepting any incoming calls during failover if the Response Group has been imported to the Backup pool</span></span>

<span data-ttu-id="7c2fb-450">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-450">**Issue:**</span></span>

<span data-ttu-id="7c2fb-451">Se um grupo de resposta pertencente ao pool primário tiver sido importado para o pool de backup sem substituir o proprietário e o grupo de resposta for removido do pool de proprietário, o grupo de resposta no pool de backup não aceitará chamadas de entrada durante o failover.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-451">If a Response Group that is owned by the primary pool has been imported to the backup pool without overwriting the owner, and the Response Group is removed from the owner pool, the Response Group in the Backup pool will not accept any incoming calls during failover.</span></span>

<span data-ttu-id="7c2fb-452">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-452">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-453">Será necessário reimplantar o grupo de resposta no pool primário.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-453">You will need to redeploy the Response Group in the Primary pool.</span></span> <span data-ttu-id="7c2fb-454">Você precisará exportar a configuração do grupo de resposta do pool primário e importá-la para o pool de backup novamente.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-454">You will then need to export the Response Group configuration from the Primary pool and import it to the Backup pool again.</span></span>

<span data-ttu-id="7c2fb-455">Você também pode recriar o grupo de resposta no pool de backup.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-455">You can also recreate the Response Group in the Backup pool.</span></span> <span data-ttu-id="7c2fb-456">Nesse caso, o pool de backup será o pool de proprietários do grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-456">In this case, the Backup pool will be the owner pool of the Response Group.</span></span>

</div>

<div>

## <a name="a-parked-call-cant-be-retrieved-from-the-call-park-application-if-the-retrieve-request-is-done-on-behalf-of-a-response-group"></a><span data-ttu-id="7c2fb-457">Uma chamada estacionada não pode ser recuperada do aplicativo de estacionamento de chamada se a solicitação de recuperação for feita em nome de um grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="7c2fb-457">A parked call can't be retrieved from the Call Park application if the retrieve request is done on behalf of a Response Group</span></span>

<span data-ttu-id="7c2fb-458">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-458">**Issue:**</span></span>

<span data-ttu-id="7c2fb-459">Quando as seguintes condições forem verdadeiras, uma solicitação de recuperação de uma chamada estacionada falhará:</span><span class="sxs-lookup"><span data-stu-id="7c2fb-459">When the following conditions are true, a retrieve request for a parked call will fail:</span></span>

  - <span data-ttu-id="7c2fb-460">Um agente é parte de um grupo de resposta anônimo</span><span class="sxs-lookup"><span data-stu-id="7c2fb-460">An agent is part of an anonymous Response Group</span></span>

  - <span data-ttu-id="7c2fb-461">O agente tenta recuperar uma chamada estacionada do aplicativo de estacionamento de chamada através do grupo de resposta anônima</span><span class="sxs-lookup"><span data-stu-id="7c2fb-461">The agent attempts to retrieve a parked call from the Call Park application through the anonymous Response Group</span></span>

  - <span data-ttu-id="7c2fb-462">O agente tenta recuperar a chamada discando o número de órbita através da opção chamar em nome de ou através da mesma opção no cliente do atendedor do Lync</span><span class="sxs-lookup"><span data-stu-id="7c2fb-462">The agent attempts to retrieve the call by dialing the orbit number through the Call On Behalf option or through the same option in the Lync attendant client</span></span>

<span data-ttu-id="7c2fb-463">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-463">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-464">Não há soluções alternativas para esse problema.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-464">There are no workarounds for this issue.</span></span> <span data-ttu-id="7c2fb-465">A chamada estacionada deve ser recuperada sem fazer isso em nome de um grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-465">The parked call should be retrieved without doing so on behalf of a Response Group.</span></span>

</div>

</div>

<span id="TopoBuilder"></span>

<div>

## <a name="lync-server-control-panel-topology-builder-and-planning-tool"></a><span data-ttu-id="7c2fb-466">Painel de controle do Lync Server, Construtor de topologias e Ferramenta de planejamento</span><span class="sxs-lookup"><span data-stu-id="7c2fb-466">Lync Server Control Panel, Topology Builder, and Planning Tool</span></span>

<div>

## <a name="planning-tool-limitations"></a><span data-ttu-id="7c2fb-467">Limitações da ferramenta de planejamento</span><span class="sxs-lookup"><span data-stu-id="7c2fb-467">Planning Tool Limitations</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="7c2fb-468">As informações contidas nesta seção pertencem às atualizações cumulativas do Lync Server 2013:2013 de fevereiro.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-468">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="7c2fb-469">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-469">**Issue:**</span></span>

<span data-ttu-id="7c2fb-470">A ferramenta de planejamento tem as seguintes limitações ao planejar sua implantação:</span><span class="sxs-lookup"><span data-stu-id="7c2fb-470">The Planning Tool has the following limitations when planning for your deployment:</span></span>

  - <span data-ttu-id="7c2fb-471">Há suporte para o máximo de 10 sites centrais</span><span class="sxs-lookup"><span data-stu-id="7c2fb-471">There is a maximum of 10 central sites supported</span></span>

  - <span data-ttu-id="7c2fb-472">Cada site central pode ter no máximo 14 sites de filial</span><span class="sxs-lookup"><span data-stu-id="7c2fb-472">Each central site can have a maximum of 14 branch sites</span></span>

  - <span data-ttu-id="7c2fb-473">Cada site central pode ter no máximo 240.000 usuários</span><span class="sxs-lookup"><span data-stu-id="7c2fb-473">Each central site can have a maximum of 240,000 users</span></span>

<span data-ttu-id="7c2fb-474">Além disso, a ferramenta de planejamento não inclui valores para o seguinte ao calcular a topologia recomendada:</span><span class="sxs-lookup"><span data-stu-id="7c2fb-474">In addition, the Planning Tool does not include values for the following when calculating the recommended topology:</span></span>

  - <span data-ttu-id="7c2fb-475">O número de usuários hospedados online</span><span class="sxs-lookup"><span data-stu-id="7c2fb-475">The number of users that are homed online</span></span>

  - <span data-ttu-id="7c2fb-476">A porcentagem de usuários habilitados para Federação do XMPP</span><span class="sxs-lookup"><span data-stu-id="7c2fb-476">The percentage of users that are enabled for XMPP federation</span></span>

  - <span data-ttu-id="7c2fb-477">Porcentagem de usuários que estão usando o Lync Web App</span><span class="sxs-lookup"><span data-stu-id="7c2fb-477">Percentage of users that are using Lync Web App</span></span>

<span data-ttu-id="7c2fb-478">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-478">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-479">Não há solução para esses problemas.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-479">There is no workaround for these issues.</span></span> <span data-ttu-id="7c2fb-480">Para obter mais informações sobre a ferramenta de planejamento, consulte [projetando a topologia do Lync Server 2013 usando a ferramenta de planejamento](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md).</span><span class="sxs-lookup"><span data-stu-id="7c2fb-480">For more information about the Planning Tool, see [Designing the topology for Lync Server 2013 by using the Planning Tool](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md).</span></span>

</div>

<div>

## <a name="planning-tool-may-not-use-previously-defined-ip-addresses-for-the-edge-network-when-updating-options"></a><span data-ttu-id="7c2fb-481">A ferramenta de planejamento pode não usar endereços IP previamente definidos para a rede de borda ao atualizar opções</span><span class="sxs-lookup"><span data-stu-id="7c2fb-481">Planning Tool may not use previously defined IP addresses for the Edge network when updating options</span></span>

<span data-ttu-id="7c2fb-482">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-482">**Issue:**</span></span>

<span data-ttu-id="7c2fb-483">Depois de concluir o design usando a ferramenta de planejamento, se você fizer alterações nas opções de rede de borda, poderão ser adicionados endereços IP adicionais ao design em vez de atualizar os endereços IP existentes.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-483">After you complete your design using the Planning Tool, if you make changes to the Edge Network options, additional IP addresses may be added to the design instead of updating the existing IP addresses.</span></span> <span data-ttu-id="7c2fb-484">Isso pode ocorrer quando você estiver exibindo os detalhes do diagrama de rede de borda, selecione **clique aqui para atualizar suas opções**e, em seguida, na caixa de diálogo opções de configuração, selecione rede de borda selecionar **desejo usar os mesmos endereços IP e FQDNs, mas diferentes portas para os serviços de borda no meu servidor de borda**.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-484">This can occur when you are viewing the details of the Edge Network Diagram, select **Click here to update your options**, and then, on the Configuration Options dialog, you select Edge Network select **I want to use the same FQDNs and IP addresses, but different ports for the edge services on my Edge Server**.</span></span> <span data-ttu-id="7c2fb-485">A aplicação de qualquer alteração pode resultar na adição de novos endereços IP e servidores de borda ao design.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-485">Applying any changes may result in new IP addresses and Edge servers being added to the design.</span></span>

<span data-ttu-id="7c2fb-486">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-486">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-487">No momento, não há solução para esse problema.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-487">There is no workaround for this issue at this time.</span></span>

</div>

<div>

## <a name="in-lync-server-control-panel-move-all-users-to-pool-may-not-work-as-expected"></a><span data-ttu-id="7c2fb-488">No painel de controle do Lync Server, "mover todos os usuários para o pool" pode não funcionar como esperado</span><span class="sxs-lookup"><span data-stu-id="7c2fb-488">In Lync Server Control Panel, "Move all users to pool" may not work as expected</span></span>

<span data-ttu-id="7c2fb-489">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-489">**Issue:**</span></span>

<span data-ttu-id="7c2fb-490">Ao usar o painel de controle do Lync Server para mover todos os usuários de um pool para outro em um ambiente complexo do Active Directory, como um com vários controladores de domínio e domínios pai/filho, uma mensagem de erro pode ser retornada que diz, "o usuário especificado não é um usuário herdado, use o cmdlet Move-CsUser."</span><span class="sxs-lookup"><span data-stu-id="7c2fb-490">When using the Lync Server Control Panel to move all users from one pool to another pool in a complex Active Directory environment, such as one with multiple Domain Controllers and parent/child domains, an error message may be returned that states, “Specified user is not a legacy user, use Move-CsUser cmdlet instead.”</span></span> <span data-ttu-id="7c2fb-491">Isso é um resultado de tempos de replicação mais longos em ambientes complexos do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-491">This is a result of longer replication times in complex Active Directory environments.</span></span>

<span data-ttu-id="7c2fb-492">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-492">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-493">Para contornar esse problema, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="7c2fb-493">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="7c2fb-494">Use filtros no painel de controle do Lync Server para pesquisar usuários herdados, selecione-os e use o **comando mover usuários selecionados para o pool** em vez de **mover todos os usuários para o pool**.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-494">Use filters in the Lync Server Control Panel to search for legacy users, select those users, and then use the **Move selected users to pool command** instead of **Move all users to pool**.</span></span>

  - <span data-ttu-id="7c2fb-495">Use o Shell de gerenciamento do Lync Server para mover usuários herdados em lotes usando cmdlets do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-495">Use the Lync Server Management Shell to move legacy users in batches by using Lync Server cmdlets.</span></span>

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-the-microsoft-silverlight-browser-plug-in-is-updated-to-version-5"></a><span data-ttu-id="7c2fb-496">O painel de controle do Lync Server pára de funcionar em um ambiente VMware depois que o plug-in do navegador Microsoft Silverlight é atualizado para a versão 5</span><span class="sxs-lookup"><span data-stu-id="7c2fb-496">The Lync Server Control Panel stops working in a VMware environment after the Microsoft Silverlight browser plug-in is updated to version 5</span></span>

<span data-ttu-id="7c2fb-497">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-497">**Issue:**</span></span>

<span data-ttu-id="7c2fb-498">Se você usar o painel de controle do Lync Server em um ambiente VMware, o painel de controle do Lync Server pode parar de funcionar após a atualização do Silverlight para a versão 5.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-498">If you use the Lync Server Control Panel in a VMware environment, the Lync Server Control Panel may stop working after you upgrade Silverlight to version 5.</span></span>

<span data-ttu-id="7c2fb-499">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-499">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-500">Para contornar esse problema, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="7c2fb-500">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="7c2fb-501">Desinstale o Silverlight 5 e, em seguida, [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0)instale o Silverlight 4 a partir do.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-501">Uninstall Silverlight 5, and then install Silverlight 4 from [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0).</span></span>

  - <span data-ttu-id="7c2fb-502">Abra o painel de controle do Lync Server em um computador que não é um computador virtual VMware.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-502">Open the Lync Server Control Panel from a computer that is not a VMware virtual computer.</span></span>
    
    <span data-ttu-id="7c2fb-503">Para abrir o painel de controle do Lync Server em um computador remoto, instale as ferramentas de administração do Lync Server no computador e, em seguida, inicie o painel de controle do Lync Server no menu **Iniciar** do Windows.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-503">To open the Lync Server Control Panel from a remote computer, install Lync Server Administration tools on the computer, and then start the Lync Server Control Panel from the Windows **Start** menu.</span></span>
    
    <span data-ttu-id="7c2fb-504">Você também pode abrir o painel de controle do Lync Server inserindo a URL em um navegador da Web.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-504">You can also open the Lync Server Control Panel by entering the URL in a web browser.</span></span> <span data-ttu-id="7c2fb-505">A URL será\<semelhante ao FQDN\_\_\>do pool de front-https:///CSCP.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-505">The URL will be similar to https://\<frontend\_pool\_fqdn\>/cscp.</span></span>

</div>

<div>

## <a name="an-administrator-cannot-run-the-uninstall-csmirrordb-cmdlet-after-removing-the-mirroring-database-in-topology-builder"></a><span data-ttu-id="7c2fb-506">Um administrador não pode executar o cmdlet Uninstall-csMirrorDB após remover o banco de dados de espelhamento no construtor de topologias</span><span class="sxs-lookup"><span data-stu-id="7c2fb-506">An administrator cannot run the Uninstall-csMirrorDB cmdlet after removing the mirroring database in Topology Builder</span></span>

<span data-ttu-id="7c2fb-507">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-507">**Issue:**</span></span>

<span data-ttu-id="7c2fb-508">Quando um administrador desativa um banco de dados de espelhamento no construtor de topologias e, em seguida, exclui o banco de dados de espelhamento no construtor de topologia, uma mensagem é exibida na lista de tarefas pendentes para que o administrador execute o cmdlet **Uninstall-csMirrorDatabase** para remover o espelhamento do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-508">When an administrator disables a mirroring database in Topology Builder, and then deletes the mirroring database in Topology Builder, a message is displayed in the To do list for the administrator to run the **Uninstall-csMirrorDatabase** cmdlet to remove mirroring from SQL Server.</span></span> <span data-ttu-id="7c2fb-509">Quando o administrador tenta executar o cmdlet, ele falha.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-509">When the administrator attempts to run the cmdlet, it fails.</span></span>

<span data-ttu-id="7c2fb-510">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-510">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-511">Para remover o espelhamento de SQL de um pool no construtor de topologia, você deve primeiro usar um cmdlet para remover o espelho no SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-511">To remove SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server.</span></span> <span data-ttu-id="7c2fb-512">Em seguida, você poderá usar o Construtor de Topologias para remover o espelho da topologia.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-512">You can then use Topology Builder to remove the mirror from the topology.</span></span> <span data-ttu-id="7c2fb-513">Para remover o espelho no SQL Server, use o cmdlet a seguir:</span><span class="sxs-lookup"><span data-stu-id="7c2fb-513">To remove the mirror in SQL Server, use the following cmdlet:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

<span data-ttu-id="7c2fb-514">Por exemplo, para remover o espelhamento e descartar os bancos de dados dos bancos de dados do usuário, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7c2fb-514">For example, to remove mirroring and drop the databases for the user databases, type the following:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

<span data-ttu-id="7c2fb-515">O parâmetro *DropExistingDatabasesOnMirror* faz com que os bancos de dados afetados sejam excluídos do espelho.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-515">The *DropExistingDatabasesOnMirror* parameter causes the affected databases to be deleted from the mirror.</span></span> <span data-ttu-id="7c2fb-516">Em seguida, para remover o espelho da topologia, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7c2fb-516">Then, to remove the mirror from the topology, do the following:</span></span>

1.  <span data-ttu-id="7c2fb-517">No Construtor de Topologias, clique com o botão direito do mouse no pool e em **Editar Propriedades**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-517">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="7c2fb-518">Desmarque **habilitar espelhamento do repositório SQL** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-518">Clear **Enable SQL Store Mirroring** and click **OK**.</span></span>

3.  <span data-ttu-id="7c2fb-519">Publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-519">Publish the topology.</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="7c2fb-520">Sempre que fizer uma alteração em uma relação de espelhamento de banco de dados de back-end, você deverá reiniciar todos os servidores front-end no pool.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-520">Whenever you make a change to a back-end database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span>



</div>

</div>

<div>

## <a name="validation-errors-are-returned-in-topology-builder-when-an-administrator-attempts-to-remove-a-deployment-with-a-front-end-pool-that-has-an-associated-witness-store"></a><span data-ttu-id="7c2fb-521">Erros de validação são retornados no construtor de topologia quando um administrador tenta remover uma implantação com um pool de front-ends que tem um repositório testemunha associado</span><span class="sxs-lookup"><span data-stu-id="7c2fb-521">Validation errors are returned in Topology Builder when an administrator attempts to remove a deployment with a Front End pool that has an associated witness store</span></span>

<span data-ttu-id="7c2fb-522">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-522">**Issue:**</span></span>

<span data-ttu-id="7c2fb-523">Se um administrador tentar usar o comando **remover implantação** no construtor de topologias para remover uma implantação que inclui um pool de front-ends com um repositório testemunha associado, um erro de validação será exibido no construtor de topologias e a ação não prosseguirá.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-523">If an administrator attempts to use the **Remove Deployment** command in Topology Builder to remove a deployment that includes a Front End pool with an associated witness store, a validation error is displayed in Topology Builder and the action will not proceed.</span></span>

<span data-ttu-id="7c2fb-524">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-524">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-525">Para contornar esse problema, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="7c2fb-525">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="7c2fb-526">Remova o repositório testemunha antes de tentar remover a implantação.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-526">Remove the witness store before attempting to remove the deployment.</span></span>

  - <span data-ttu-id="7c2fb-527">Adicione um repositório testemunha para o pool de front-ends e remova-o.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-527">Add a witness store for the Front End pool and then remove it.</span></span>

</div>

<div>

## <a name="persistent-chat-server-deployment-information-is-inconsistent-between-the-planning-tool-and-topology-builder"></a><span data-ttu-id="7c2fb-528">As informações de implantação do servidor de chat persistente são inconsistentes entre a ferramenta de planejamento e o construtor de topologia</span><span class="sxs-lookup"><span data-stu-id="7c2fb-528">Persistent Chat Server deployment information is inconsistent between the Planning Tool and Topology Builder</span></span>

<span data-ttu-id="7c2fb-529">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-529">**Issue:**</span></span>

<span data-ttu-id="7c2fb-530">Quando o Lync Server 2013, a ferramenta de planejamento gera o diagrama de topologia de site para uma implantação de servidor de chat persistente com a recuperação de desastre habilitada, o diagrama de topologia de site inclui vários sites (físicos), com servidores de chat persistentes atribuídos igualmente em cada no.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-530">When the Lync Server 2013, Planning Tool outputs the site topology diagram for a Persistent Chat Server deployment with disaster recovery enabled, the site topology diagram includes multiple (physical) sites, with evenly assigned Persistent Chat Servers at each site.</span></span> <span data-ttu-id="7c2fb-531">No construtor de topologias, todos os servidores de chat persistentes são representados como pertencentes a um único site (lógico) e estão listados no mesmo nó do pool de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-531">In Topology Builder, all Persistent Chat Servers are represented as belonging to a single (logical) site, and are listed under the same Persistent Chat Server pool node.</span></span>

<span data-ttu-id="7c2fb-532">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-532">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-533">No momento, não temos uma solução alternativa para esse problema.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-533">Currently, we do not have a workaround for this issue.</span></span> <span data-ttu-id="7c2fb-534">O usuário deve analisar a saída da ferramenta de planejamento para a implantação do servidor de chat persistente e modificar o plano para atender às suas necessidades específicas.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-534">The user should analyze the output of the Planning Tool for the Persistent Chat Server deployment, and modify the plan to meet their specific needs.</span></span>

</div>

</div>

<span id="Localization"></span>

<div>

## <a name="localization"></a><span data-ttu-id="7c2fb-535">Localização</span><span class="sxs-lookup"><span data-stu-id="7c2fb-535">Localization</span></span>

<div>

## <a name="monitoring"></a><span data-ttu-id="7c2fb-536">Monitoramento</span><span class="sxs-lookup"><span data-stu-id="7c2fb-536">Monitoring</span></span>

<div>

## <a name="the-deploy-monitoring-reports-wizard-displays-incorrect-characters-under-certain-circumstances-when-using-the-east-asian-version-of-lync-server"></a><span data-ttu-id="7c2fb-537">O assistente implantar relatórios de monitoramento exibe caracteres incorretos sob determinadas circunstâncias ao usar a versão do leste asiático do Lync Server</span><span class="sxs-lookup"><span data-stu-id="7c2fb-537">The Deploy Monitoring Reports wizard displays incorrect characters under certain circumstances when using the East Asian version of Lync Server</span></span>

<span data-ttu-id="7c2fb-538">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-538">**Issue:**</span></span>

<span data-ttu-id="7c2fb-539">Ao usar uma versão do leste asiático do Lync Server 2013 — por exemplo, chinês (simplificado), chinês (tradicional), japonês ou coreano — em um sistema operacional que tenha a localidade do sistema não definida para um idioma do leste asiático, o assistente implantar relatórios de monitoramento será exibe pontos de interrogação ou outros caracteres em vez de mensagens localizadas.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-539">When using an East Asian version of Lync Server 2013—for example, Chinese (Simplified), Chinese (Traditional), Japanese, or Korean—on an operating system that has the system locale not set to an East Asian language, the Deploy Monitoring Reports wizard will display question marks or other characters instead of localized messages.</span></span>

<span data-ttu-id="7c2fb-540">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-540">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-541">Para corrigir esse problema, defina a localidade do sistema operacional e do Lync Server 2013 para o mesmo idioma, que exibirá todas as mensagens corretamente.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-541">To correct this issue, set the locale for the operating system and Lync Server 2013 to the same language, which will display all messages correctly.</span></span>

</div>

</div>

<div>

## <a name="lync-server-control-panel"></a><span data-ttu-id="7c2fb-542">Painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="7c2fb-542">Lync Server Control Panel</span></span>

<div>

## <a name="in-certain-cases-the-first-item-in-the-top-navigation-bar-on-a-page-of-lync-server-control-panel-disappears-when-the-last-item-in-the-top-navigation-bar-is-clicked"></a><span data-ttu-id="7c2fb-543">Em determinados casos, o primeiro item da barra de navegação superior em uma página do painel de controle do Lync Server desaparece quando o último item na barra de navegação superior é clicado</span><span class="sxs-lookup"><span data-stu-id="7c2fb-543">In certain cases, the first item in the top navigation bar on a page of Lync Server Control Panel disappears when the last item in the top navigation bar is clicked</span></span>

<span data-ttu-id="7c2fb-544">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-544">**Issue:**</span></span>

<span data-ttu-id="7c2fb-545">Há três casos conhecidos em que clicar no último item na barra de navegação superior em uma página do painel de controle do Lync Server fará com que o primeiro item na barra de navegação superior desapareça:</span><span class="sxs-lookup"><span data-stu-id="7c2fb-545">There are three known cases where clicking the last item in the top navigation bar on a page of the Lync Server Control Panel will cause the first item in the top navigation bar to disappear:</span></span>

  - <span data-ttu-id="7c2fb-546">Na versão francesa, na página "Féderation et accès externe", o item "Stratégie d'accès externo" desaparecerá quando "Partenaires fédérés XMPP" for clicado.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-546">In the French of version, on the page "Féderation et accès externe," the item "Stratégie d'accès externe" will disappear when "Partenaires fédérés XMPP" is clicked.</span></span>

  - <span data-ttu-id="7c2fb-547">Na versão em alemão, na página "clientes", o item "Clientversionskonfiguration" desaparecerá quando "Pushbenachrichtigungskonfiguration" for clicado.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-547">In the German version, on the "Clients" page, the item "Clientversionskonfiguration" disappears when "Pushbenachrichtigungskonfiguration" is clicked.</span></span>

  - <span data-ttu-id="7c2fb-548">Na versão em Russo, na página "Конфигурация сети", o item "Глобально" desaparecerá quando "Маршрут региона" for clicado.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-548">In the Russian version, on "Конфигурация сети" page, the item "Глобально" disappears when "Маршрут региона" is clicked.</span></span>

<span data-ttu-id="7c2fb-549">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-549">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-550">Para contornar esse problema, atualize a página do painel de controle do Lync Server no navegador.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-550">To work around this issue, refresh the page of the Lync Server Control Panel in your browser.</span></span> <span data-ttu-id="7c2fb-551">A página será carregada no navegador com todos os itens na barra de navegação superior exibida.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-551">The page will load in the browser with all of the items in the top navigation bar displayed.</span></span>

</div>

</div>

<div>

## <a name="address-book"></a><span data-ttu-id="7c2fb-552">Catálogo de endereços</span><span class="sxs-lookup"><span data-stu-id="7c2fb-552">Address Book</span></span>

<div>

## <a name="indexing-in-the-address-book-does-not-work-as-expected-in-some-languages"></a><span data-ttu-id="7c2fb-553">A indexação no catálogo de endereços não funciona como esperado em alguns idiomas</span><span class="sxs-lookup"><span data-stu-id="7c2fb-553">Indexing in the Address Book does not work as expected in some languages</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="7c2fb-554">As informações contidas nesta seção pertencem às atualizações cumulativas do Lync Server 2013:2013 de fevereiro.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-554">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="7c2fb-555">Se as propriedades de um usuário contiverem um campo indexado e esse campo contiver apenas caracteres que não podem ser indexados, o usuário não será exibido nas pesquisas realizadas no catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-555">If a user’s properties contain an indexed field, and that field contains only characters that cannot be indexed, then the user will not appear in searches performed in the Address Book.</span></span>

<span data-ttu-id="7c2fb-556">Os seguintes caracteres e localidades não podem ser indexados:</span><span class="sxs-lookup"><span data-stu-id="7c2fb-556">The following characters and locales cannot be indexed:</span></span>

  - <span data-ttu-id="7c2fb-557">Caracteres cirílico, grego e armênio em maiúsculas e minúsculas</span><span class="sxs-lookup"><span data-stu-id="7c2fb-557">Upper-case Cyrillic, Greek, and Armenian characters</span></span>

  - <span data-ttu-id="7c2fb-558">Caracteres acentuados em maiúsculas</span><span class="sxs-lookup"><span data-stu-id="7c2fb-558">Upper-case accented characters</span></span>

  - <span data-ttu-id="7c2fb-559">Tailandês</span><span class="sxs-lookup"><span data-stu-id="7c2fb-559">Thai</span></span>

  - <span data-ttu-id="7c2fb-560">Lao</span><span class="sxs-lookup"><span data-stu-id="7c2fb-560">Lao</span></span>

  - <span data-ttu-id="7c2fb-561">Myanmar</span><span class="sxs-lookup"><span data-stu-id="7c2fb-561">Myanmar</span></span>

  - <span data-ttu-id="7c2fb-562">Devanágari</span><span class="sxs-lookup"><span data-stu-id="7c2fb-562">Devanagari</span></span>

  - <span data-ttu-id="7c2fb-563">Etiópico</span><span class="sxs-lookup"><span data-stu-id="7c2fb-563">Ethiopic</span></span>

  - <span data-ttu-id="7c2fb-564">Tibetano</span><span class="sxs-lookup"><span data-stu-id="7c2fb-564">Tibetan</span></span>

  - <span data-ttu-id="7c2fb-565">Bengali</span><span class="sxs-lookup"><span data-stu-id="7c2fb-565">Bengali</span></span>

  - <span data-ttu-id="7c2fb-566">Gujarati</span><span class="sxs-lookup"><span data-stu-id="7c2fb-566">Gujarati</span></span>

  - <span data-ttu-id="7c2fb-567">Telugu</span><span class="sxs-lookup"><span data-stu-id="7c2fb-567">Telugu</span></span>

  - <span data-ttu-id="7c2fb-568">Todos os outros scripts índicos</span><span class="sxs-lookup"><span data-stu-id="7c2fb-568">All other Indic scripts</span></span>

</div>

</div>

<div>

## <a name="lync-web-app-web-scheduler-and-web-components"></a><span data-ttu-id="7c2fb-569">Lync Web App, Agendador da Web e componentes da Web</span><span class="sxs-lookup"><span data-stu-id="7c2fb-569">Lync Web App, Web Scheduler, and Web components</span></span>

<div>

## <a name="language-fallback-for-certain-languages-in-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-might-not-work-as-expected"></a><span data-ttu-id="7c2fb-570">O fallback de idioma para determinados idiomas do Lync Web Scheduler, discar, inicializador de ingresso, gerenciamento de salas de chat persistente e OCTab pode não funcionar conforme o esperado</span><span class="sxs-lookup"><span data-stu-id="7c2fb-570">Language fallback for certain languages in Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab might not work as expected</span></span>

<span data-ttu-id="7c2fb-571">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-571">**Issue:**</span></span>

<span data-ttu-id="7c2fb-572">Ao selecionar uma localidade neutra em um navegador da Web (no Internet Explorer, por exemplo, o nome do idioma sem mais especificação, como \["\]norueguês no") em vez de uma localidade especificando o idioma, o script e a localidade (como "norueguês \[, BOKMÅL (\]Noruega) NB-não") pode levar a um comportamento de exibição inesperado para determinados idiomas no navegador do Lync Web, no iniciador de ingresso, no gerenciamento da sala de chat persistente</span><span class="sxs-lookup"><span data-stu-id="7c2fb-572">When selecting a neutral locale in a web browser (in Internet Explorer, for example, the language name without further specification, like "Norwegian \[no\]") instead of a locale specifying language, script and locale (such as "Norwegian, Bokmål (Norway) \[nb-NO\]") might lead to unexpected display behavior for certain languages in Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab.</span></span> <span data-ttu-id="7c2fb-573">Por exemplo, os usuários podem ver a página em inglês quando um dos seguintes idiomas é selecionado:</span><span class="sxs-lookup"><span data-stu-id="7c2fb-573">For example, users might see the English page when one of the following languages is selected:</span></span>

  - <span data-ttu-id="7c2fb-574">Norueguês</span><span class="sxs-lookup"><span data-stu-id="7c2fb-574">Norwegian</span></span>

  - <span data-ttu-id="7c2fb-575">Português</span><span class="sxs-lookup"><span data-stu-id="7c2fb-575">Portuguese</span></span>

  - <span data-ttu-id="7c2fb-576">Sérvio</span><span class="sxs-lookup"><span data-stu-id="7c2fb-576">Serbian</span></span>

<span data-ttu-id="7c2fb-577">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-577">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-578">Se você quiser selecionar um idioma com uma localidade neutra, sempre certifique-se de que você também adicionou o idioma com uma localidade específica (com código de script e/ou país) como um idioma adicional na lista de preferência de idioma do seu navegador.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-578">If you want to select a language with a neutral locale, always make sure that you also add the language with a specific locale (with script and/or country code) as an additional language in your browser's language preference list.</span></span>

</div>

<div>

## <a name="there-is-limited-support-for-azeri-and-uzbek-locales-when-using-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-in-some-web-browsers"></a><span data-ttu-id="7c2fb-579">Há suporte limitado para localidades azeri e uzbeque ao usar o Agendador do Lync, discagem, inicializador de ingresso, gerenciamento de salas de chat persistente e OCTab em alguns navegadores da Web</span><span class="sxs-lookup"><span data-stu-id="7c2fb-579">There is limited support for Azeri and Uzbek locales when using Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab in some web browsers</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="7c2fb-580">As informações contidas nesta seção pertencem às atualizações cumulativas do Lync Server 2013:2013 de fevereiro.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-580">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="7c2fb-581">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-581">**Issue:**</span></span>

<span data-ttu-id="7c2fb-582">Quando você usa o Internet Explorer 8 ou o Internet Explorer 9 e define o idioma do navegador como Azeri (latino) ou uzbeque (latino), as páginas de discagem e inicializador de ingresso serão exibidas em inglês ou no conjunto de idiomas preferencial no navegador.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-582">When you use Internet Explorer 8 or Internet Explorer 9, and set the browser language to Azeri (Latin) or Uzbek (Latin), the Dial-in and Join Launcher pages will be displayed in English or the preferred language set in the browser.</span></span>

<span data-ttu-id="7c2fb-583">Quando você usa o Firefox ou navegadores Chrome e define o idioma do navegador como Azeri (latino) ou uzbeque (latino), o Lync Web App, Lync Web Scheduler e RGS OCTab serão mostrados em inglês ou no conjunto de idiomas preferencial para o navegador.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-583">When you use Firefox or Chrome browsers, and you set the browser language to Azeri (Latin) or Uzbek (Latin), the Lync Web App, Lync Web Scheduler, and RGS OCTab will be shown in English or the preferred language set for the browser.</span></span>

<span data-ttu-id="7c2fb-584">A localidade uzbeque (latino) não é suportada no navegador Safari.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-584">The Uzbek (Latin) locale is not supported in the Safari browser.</span></span>

<span data-ttu-id="7c2fb-585">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-585">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-586">Não há solução alternativa para esses problemas.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-586">There is not workaround for these issues.</span></span>

</div>

</div>

<div>

## <a name="the-drop-down-arrow-is-missing-for-join-meeting-from-list-in-the-romanian-version-of-lync-web-app"></a><span data-ttu-id="7c2fb-587">A seta suspensa está ausente para a lista "participar da reunião de" na versão romeno do Lync Web App</span><span class="sxs-lookup"><span data-stu-id="7c2fb-587">The drop-down arrow is missing for "Join meeting from" list in the Romanian version of Lync Web App</span></span>

<span data-ttu-id="7c2fb-588">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-588">**Issue:**</span></span>

<span data-ttu-id="7c2fb-589">Quando um usuário que está usando a versão romeno do Lync Web App executa as etapas a seguir, a seta suspensa não é exibida para **participar da reunião** na lista suspensa:</span><span class="sxs-lookup"><span data-stu-id="7c2fb-589">When a user who is using the Romanian version of Lync Web App performs the following steps, the drop-down arrow is not displayed for **Join meeting** in drop-down list:</span></span>

1.  <span data-ttu-id="7c2fb-590">Selecione **lembrar-me neste computador** na guia **geral** .</span><span class="sxs-lookup"><span data-stu-id="7c2fb-590">Select **Remember me on this computer** on the **General** tab.</span></span>

2.  <span data-ttu-id="7c2fb-591">Selecione a guia **telefone** .</span><span class="sxs-lookup"><span data-stu-id="7c2fb-591">Select the **Phone** tab.</span></span>

3.  <span data-ttu-id="7c2fb-592">Clique na lista suspensa para **participar da reunião**.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-592">Click the drop-down list for **Join meeting from**.</span></span>
    
    <span data-ttu-id="7c2fb-593">Os usuários não verão uma seta que indica que há mais opções do que o **Lync Web App**padrão, que inclui: **não ingressar em áudio** (no romeno, "nu se asociaža la") e **novo número**"(no romeno," Număr Nou ").</span><span class="sxs-lookup"><span data-stu-id="7c2fb-593">Users will not see an arrow that indicates that there are more options than the default **Lync Web App**, which include: **Don't join audio** (in Romanian, "Nu se asociaža la componenta audio") and **New number**" (in Romanian, "Număr nou").</span></span>

<span data-ttu-id="7c2fb-594">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-594">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-595">Embora a seta dessa lista suspensa não seja exibida, os usuários ainda podem selecionar as configurações adicionais na lista clicando no valor padrão.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-595">Even though the arrow for this drop-down list is not displayed, users can still select the additional settings in the list by clicking on the default value.</span></span>

</div>

<div>

## <a name="when-using-the-turkish-version-of-lync-web-scheduler-a-meeting-cannot-be-saved-when-using-the-people-i-choose-option-under-who-is-a-presenter"></a><span data-ttu-id="7c2fb-596">Ao usar a versão em Turco do Agendador do Lync Web, não é possível salvar uma reunião ao usar a opção "pessoas que eu escolher" em "quem é um apresentador"</span><span class="sxs-lookup"><span data-stu-id="7c2fb-596">When using the Turkish version of Lync Web Scheduler, a meeting cannot be saved when using the "People I choose" option under "Who is a presenter"</span></span>

<span data-ttu-id="7c2fb-597">**Execute**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-597">**Issue:**</span></span>

<span data-ttu-id="7c2fb-598">Ao criar ou editar uma reunião na versão em Turco do programa de programação do Lync Web, a opção "pessoas que eu escolher" em "quem é um apresentador" não é suportada.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-598">When creating or editing a meeting in the Turkish version of the Lync Web Scheduler, the option "People I choose" under "Who is a presenter" is not supported.</span></span> <span data-ttu-id="7c2fb-599">Quando essa opção é selecionada, a reunião não pode ser salva.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-599">When this option is selected, the meeting can't be saved.</span></span> <span data-ttu-id="7c2fb-600">Em vez disso, uma mensagem de erro é exibida, indicando que uma ou mais pessoas não podem ser feitas apresentadores.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-600">Instead, an error message appears, indicating that one or more people cannot be made presenters.</span></span>

<span data-ttu-id="7c2fb-601">**Solução alternativa**</span><span class="sxs-lookup"><span data-stu-id="7c2fb-601">**Workaround:**</span></span>

<span data-ttu-id="7c2fb-602">Para contornar esse problema, os usuários podem usar a opção padrão "pessoas da minha empresa" ou qualquer outra opção, como "somente organizador" ou "todos incluindo pessoas fora da minha empresa".</span><span class="sxs-lookup"><span data-stu-id="7c2fb-602">To work around this issue, users can use the default option of "People from my company," or any other choice, such as "Only Organizer" or "Everyone including people outside of my company."</span></span> <span data-ttu-id="7c2fb-603">O organizador pode rebaixar ou promover pessoas para suas funções corretas posteriormente, depois de ingressar na reunião.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-603">The organizer can demote or promote people to their correct roles later, after they have joined the meeting.</span></span>

<span data-ttu-id="7c2fb-604">Como alternativa, os usuários que entendem outro idioma podem alterar a seleção de idioma no navegador para um dos outros idiomas com suporte do 43 e tentar usar a opção "pessoas que eu escolher".</span><span class="sxs-lookup"><span data-stu-id="7c2fb-604">Alternatively, users who understand another language can change the language selection in their browser to one of the other 43 supported languages and attempt to use the “People I choose” option.</span></span>

</div>

</div>

<span id="Copyright"></span>

<div>

## <a name="copyright"></a><span data-ttu-id="7c2fb-605">Direitos autorais</span><span class="sxs-lookup"><span data-stu-id="7c2fb-605">Copyright</span></span>

<span data-ttu-id="7c2fb-606">Este documento oferece suporte a uma versão preliminar de um produto de software que pode ser alterado substancialmente antes do lançamento comercial final, e é a informação confidencial e proprietária da Microsoft Corporation.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-606">This document supports a preliminary release of a software product that may be changed substantially prior to final commercial release, and is the confidential and proprietary information of Microsoft Corporation.</span></span> <span data-ttu-id="7c2fb-607">Ela é divulgada de acordo com um contrato de não divulgação entre o destinatário e a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-607">It is disclosed pursuant to a non-disclosure agreement between the recipient and Microsoft.</span></span> <span data-ttu-id="7c2fb-608">Este documento é fornecido apenas para fins informativos, e a Microsoft não oferece garantias, expressas ou implícitas, neste documento.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-608">This document is provided for informational purposes only and Microsoft makes no warranties, either express or implied, in this document.</span></span> <span data-ttu-id="7c2fb-609">As informações neste documento, incluindo URLs e outras referências de sites da Internet, estão sujeitas a alterações sem aviso prévio.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-609">Information in this document, including URL and other Internet website references, is subject to change without notice.</span></span> <span data-ttu-id="7c2fb-610">Todo o risco do uso ou dos resultados do uso deste documento permanece com o usuário.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-610">The entire risk of the use or the results from the use of this document remains with the user.</span></span> <span data-ttu-id="7c2fb-611">Salvo indicação em contrário, as empresas, organizações, produtos, nomes de domínio, endereços de email, logotipos, pessoas, lugares e eventos descritos nos exemplos aqui mencionados são fictícios.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-611">Unless otherwise noted, the companies, organizations, products, domain names, email addresses, logos, people, places, and events depicted in examples herein are fictitious.</span></span> <span data-ttu-id="7c2fb-612">Nenhuma associação com qualquer empresa, organização, produto, nome de domínio, endereço de email, logotipo, pessoa, lugar ou evento real é intencional ou deve ser inferida.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-612">No association with any real company, organization, product, domain name, email address, logo, person, place, or event is intended or should be inferred.</span></span> <span data-ttu-id="7c2fb-613">A conformidade com as leis de copyright aplicáveis é de responsabilidade do usuário.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-613">Complying with all applicable copyright laws is the responsibility of the user.</span></span> <span data-ttu-id="7c2fb-614">Sem limitar os direitos de copyright, nenhuma parte deste documento pode ser reproduzida, armazenada ou inserida em um sistema de recuperação, nem transmitida em qualquer forma ou por qualquer meio (eletrônico, mecânico, fotocópia, gravação ou outros) ou por qualquer propósito, sem permissão expressa por escrito da Corporation.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-614">Without limiting the rights under copyright, no part of this document may be reproduced, stored in or introduced into a retrieval system, or transmitted in any form or by any means (electronic, mechanical, photocopying, recording, or otherwise), or for any purpose, without the express written permission of Microsoft Corporation.</span></span>

<span data-ttu-id="7c2fb-p162">A Microsoft pode ter patentes, aplicações de patentes, marcas registradas, copyrights ou direitos de propriedade intelectual que são objetos de discussão neste documento. Exceto conforme expressamente fornecido em qualquer contrato de licença por escrito, o fornecimento deste documento não lhe concede nenhuma licença a essas patentes, marcas registradas, copyrights ou outra propriedade intelectual.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-p162">Microsoft may have patents, patent applications, trademarks, copyrights, or other intellectual property rights covering subject matter in this document. Except as expressly provided in any written license agreement from Microsoft, the furnishing of this document does not give you any license to these patents, trademarks, copyrights, or other intellectual property.</span></span>

<span data-ttu-id="7c2fb-617">© 2012 Microsoft Corporation.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-617">© 2012 Microsoft Corporation.</span></span> <span data-ttu-id="7c2fb-618">Todos os direitos reservados.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-618">All rights reserved.</span></span>

<span data-ttu-id="7c2fb-619">Microsoft, Windows, Windows Live, Active Directory, Internet Explorer, MSN, Outlook e SQL Server são marcas registradas ou comerciais da Microsoft Corporation nos Estados Unidos e/ou em outros países/regiões.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-619">Microsoft, Windows, Windows Live, Active Directory, Internet Explorer, MSN, Outlook, and SQL Server are either registered trademarks or trademarks of Microsoft Corporation in the United States and/or other countries/regions.</span></span>

<span data-ttu-id="7c2fb-620">Todas as outras marcas comerciais são propriedade dos respectivos donos.</span><span class="sxs-lookup"><span data-stu-id="7c2fb-620">All other trademarks are property of their respective owners.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

