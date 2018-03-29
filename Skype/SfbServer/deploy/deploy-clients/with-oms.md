---
title: Implantar o gerenciamento do Skype Room Systems v2 com OMS
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/20/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: Este artigo discute como implantar o gerenciamento de sistemas de sala Skype v2 dispositivos de forma integrada e de ponta a ponta, usando o pacote de gerenciamento de operações do Microsoft.
ms.openlocfilehash: 0d0490d92a5513dad38a9ff6348a957204274878
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-systems-v2-management-with-oms"></a><span data-ttu-id="d923c-103">Implantar o gerenciamento do Skype Room Systems v2 com OMS</span><span class="sxs-lookup"><span data-stu-id="d923c-103">Deploy Skype Room Systems v2 management with OMS</span></span>
 
<span data-ttu-id="d923c-104">Este artigo discute como implantar o gerenciamento de sistemas de sala Skype v2 dispositivos de forma integrada e de ponta a ponta, usando o pacote de gerenciamento de operações do Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d923c-104">This article discusses how to deploy management of Skype Room Systems v2 devices in an integrated, end-to-end manner using Microsoft Operations Management Suite.</span></span> 
  
<span data-ttu-id="d923c-p101">Você pode configurar o Microsoft Operations Management Suite (OMS) para fornecer telemetria básica que ajudará você a gerenciar os dispositivos de sala de reunião do Skype. Com o passar do tempo, você pode comprar recursos de gerenciamento e dados adicionais para sua solução a fim de criar um modo de exibição mais detalhado do desempenho do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d923c-p101">You can configure Microsoft Operations Management Suite (OMS) to provide basic telemetry that will help you manage Skype meeting room devices. As your management solution matures, you can purchase additional data and management capabilities to create a more detailed view of device performance.</span></span>
  
<span data-ttu-id="d923c-107">Em um nível superior, é necessário executar as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="d923c-107">At a high level, you need to perform the following tasks:</span></span>
  
1. [<span data-ttu-id="d923c-108">Configurar os dispositivos para o Gerenciamento do OMS </span><span class="sxs-lookup"><span data-stu-id="d923c-108">Configure devices for OMS Management </span></span>](with-oms.md#config_devices)
    
2. [<span data-ttu-id="d923c-109">Mapear os campos personalizados</span><span class="sxs-lookup"><span data-stu-id="d923c-109">Map custom fields</span></span>](with-oms.md#Custom_fields)
    
3. [<span data-ttu-id="d923c-110">Definir os modos de exibição do SRS v2 no OMS</span><span class="sxs-lookup"><span data-stu-id="d923c-110">Define the SRS v2 views in OMS</span></span>](with-oms.md#Views)
    
## <a name="find-and-record-device-locations-capabilities-and-configurations"></a><span data-ttu-id="d923c-111">Localizar e registrar os locais, os recursos e as configurações do dispositivo</span><span class="sxs-lookup"><span data-stu-id="d923c-111">Find and record device locations, capabilities, and configurations</span></span>
<span data-ttu-id="d923c-112"><a name="find_devices"> </a></span><span class="sxs-lookup"><span data-stu-id="d923c-112"></span></span>

<span data-ttu-id="d923c-p102">A primeira etapa é criar um banco de dados detalhado de todos os equipamentos do sistema, os detalhes de seus recursos e da configuração, bem como sua localização. No caso de organizações de pequeno e médio portes, uma planilha pode ser adequada para esta tarefa. Se você trabalhar em uma organização de grande porte, deverá considerar ferramentas de gerenciamento de ativos e serviços de terceiros. O importante é você registrar a localização e todos os detalhes relevantes de cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d923c-p102">The first step is to create a detailed database of all of the equipment in the system, the details of its capabilities and configuration, and its location. A spreadsheet may be adequate for this task in small to medium organizations. If you work at a larger organization, you may need to consider asset management tools and third-party services. What is important is that you record the location and all the relevant details of every device.</span></span>
  
<span data-ttu-id="d923c-117">Depois de concluir o trabalho, você pode usar essas informações para enviar técnicos e gerenciar patches e atualizações de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d923c-117">Once that work is done, you can use this information to dispatch technicians and manage device patches and upgrades.</span></span>
  
## <a name="configure-devices-for-oms-management"></a><span data-ttu-id="d923c-118">Configurar os dispositivos para o Gerenciamento do OMS </span><span class="sxs-lookup"><span data-stu-id="d923c-118">Configure devices for OMS Management</span></span>
<span data-ttu-id="d923c-119"><a name="config_devices"> </a></span><span class="sxs-lookup"><span data-stu-id="d923c-119"></span></span>

<span data-ttu-id="d923c-120">Para cada dispositivo SRS, siga as instruções encontradas em [computadores com Windows se conectar ao serviço de Log de análise no Windows Azure](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-windows-agents).</span><span class="sxs-lookup"><span data-stu-id="d923c-120">For each SRS device, follow the instructions found in [Connect Windows computers to the Log Analytics service in Azure](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-windows-agents).</span></span>
  
## <a name="configure-oms-to-collect-device-event-logs"></a><span data-ttu-id="d923c-121">Configurar o OMS para obter logs de eventos do dispositivo</span><span class="sxs-lookup"><span data-stu-id="d923c-121">Configure OMS to collect device event logs</span></span>
<span data-ttu-id="d923c-122"><a name="config_devices"> </a></span><span class="sxs-lookup"><span data-stu-id="d923c-122"></span></span>

<span data-ttu-id="d923c-123">Você precisará configurar especificamente OMS para coletar logs de eventos de dispositivos SRS usando as etapas em [fontes de dados de log de eventos do Windows na análise de Log](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-windows-events).</span><span class="sxs-lookup"><span data-stu-id="d923c-123">You will need to specifically configure OMS to collect event logs from SRS devices using the steps at [Windows event log data sources in Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-windows-events).</span></span> <span data-ttu-id="d923c-124">O log de eventos SRS para selecionar é "Skype sistema de sala" e você deve verificar as caixas de opção para todos os tipos: erro, aviso e informações.</span><span class="sxs-lookup"><span data-stu-id="d923c-124">The SRS event log to select is "Skype Room System" and you should check the option boxes for all types: Error, Warning and Information.</span></span>
  
## <a name="map-custom-fields"></a><span data-ttu-id="d923c-125">Mapear os campos personalizados</span><span class="sxs-lookup"><span data-stu-id="d923c-125">Map custom fields</span></span>
<span data-ttu-id="d923c-126"><a name="Custom_fields"> </a></span><span class="sxs-lookup"><span data-stu-id="d923c-126"></span></span>

<span data-ttu-id="d923c-127">Antes que os blocos criados nas [exibições de definir o v2 SRS no OMS](with-oms.md#Views) podem ser usados, você precisará criar campos personalizados para sua exibição.</span><span class="sxs-lookup"><span data-stu-id="d923c-127">Before the tiles created in the [Define the SRS v2 views in OMS](with-oms.md#Views) can be used, you'll need to create custom fields for your view.</span></span> <span data-ttu-id="d923c-128">consulte [campos personalizados na análise de Log](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-custom-fields) para obter detalhes sobre como criar campos personalizados.</span><span class="sxs-lookup"><span data-stu-id="d923c-128">see [Custom fields in Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-custom-fields) for details on creating custom fields.</span></span>
  
<span data-ttu-id="d923c-129">Use os mapeamentos mostrados abaixo, OMS adicionará automaticamente o _CF ao definir o novo campo.</span><span class="sxs-lookup"><span data-stu-id="d923c-129">Use the mappings shown below, OMS will automatically add the _CF when defining the new field.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="d923c-130">Lembre-se de que os campos JSON e OMS diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="d923c-130">Remember that all JSON and OMS fields are case sensitive.</span></span> 
  
<span data-ttu-id="d923c-131">**Mapeamento de campos personalizados**</span><span class="sxs-lookup"><span data-stu-id="d923c-131">**Custom fields mapping**</span></span>

|<span data-ttu-id="d923c-132">**Campo JSON**</span><span class="sxs-lookup"><span data-stu-id="d923c-132">**JSON field**</span></span>|<span data-ttu-id="d923c-133">**Campo personalizado de OMS**</span><span class="sxs-lookup"><span data-stu-id="d923c-133">**OMS custom field**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d923c-134">Descrição</span><span class="sxs-lookup"><span data-stu-id="d923c-134">Description</span></span>  <br/> |<span data-ttu-id="d923c-135">SRSEventDescription_CF</span><span class="sxs-lookup"><span data-stu-id="d923c-135">SRSEventDescription_CF</span></span>  <br/> |
|<span data-ttu-id="d923c-136">ResourceState</span><span class="sxs-lookup"><span data-stu-id="d923c-136">ResourceState</span></span>  <br/> |<span data-ttu-id="d923c-137">SRSResourceState_CF</span><span class="sxs-lookup"><span data-stu-id="d923c-137">SRSResourceState_CF</span></span>  <br/> |
|<span data-ttu-id="d923c-138">Nomedaoperação</span><span class="sxs-lookup"><span data-stu-id="d923c-138">OperationName</span></span>  <br/> |<span data-ttu-id="d923c-139">SRSOperationName_CF</span><span class="sxs-lookup"><span data-stu-id="d923c-139">SRSOperationName_CF</span></span>  <br/> |
|<span data-ttu-id="d923c-140">OperationResult</span><span class="sxs-lookup"><span data-stu-id="d923c-140">OperationResult</span></span>  <br/> |<span data-ttu-id="d923c-141">SRSOperationResult_CF</span><span class="sxs-lookup"><span data-stu-id="d923c-141">SRSOperationResult_CF</span></span>  <br/> |
|<span data-ttu-id="d923c-142">Sistema operacional</span><span class="sxs-lookup"><span data-stu-id="d923c-142">OS</span></span>  <br/> |<span data-ttu-id="d923c-143">SRSOSVersion_CF</span><span class="sxs-lookup"><span data-stu-id="d923c-143">SRSOSVersion_CF</span></span>  <br/> |
|<span data-ttu-id="d923c-144">Versão do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="d923c-144">OSVersion</span></span>  <br/> |<span data-ttu-id="d923c-145">SRSOSLongVersion_CF</span><span class="sxs-lookup"><span data-stu-id="d923c-145">SRSOSLongVersion_CF</span></span>  <br/> |
|<span data-ttu-id="d923c-146">Alias</span><span class="sxs-lookup"><span data-stu-id="d923c-146">Alias</span></span>  <br/> |<span data-ttu-id="d923c-147">SRSAlias_CF</span><span class="sxs-lookup"><span data-stu-id="d923c-147">SRSAlias_CF</span></span>  <br/> |
|<span data-ttu-id="d923c-148">DisplayName</span><span class="sxs-lookup"><span data-stu-id="d923c-148">DisplayName</span></span>  <br/> |<span data-ttu-id="d923c-149">SRSDisplayName_CF</span><span class="sxs-lookup"><span data-stu-id="d923c-149">SRSDisplayName_CF</span></span>  <br/> |
|<span data-ttu-id="d923c-150">AppVersion</span><span class="sxs-lookup"><span data-stu-id="d923c-150">AppVersion</span></span>  <br/> |<span data-ttu-id="d923c-151">SRSAppVersion_CF</span><span class="sxs-lookup"><span data-stu-id="d923c-151">SRSAppVersion_CF</span></span>  <br/> |
|<span data-ttu-id="d923c-152">IPv4Address</span><span class="sxs-lookup"><span data-stu-id="d923c-152">IPv4Address</span></span>  <br/> |<span data-ttu-id="d923c-153">SRSIPv4Address_CF</span><span class="sxs-lookup"><span data-stu-id="d923c-153">SRSIPv4Address_CF</span></span>  <br/> |
|<span data-ttu-id="d923c-154">IPv6Address</span><span class="sxs-lookup"><span data-stu-id="d923c-154">IPv6Address</span></span>  <br/> |<span data-ttu-id="d923c-155">SRSIPv6Address_CF</span><span class="sxs-lookup"><span data-stu-id="d923c-155">SRSIPv6Address_CF</span></span>  <br/> |
   
## <a name="define-the-srs-v2-views-in-oms"></a><span data-ttu-id="d923c-156">Definir os modos de exibição do SRS v2 no OMS</span><span class="sxs-lookup"><span data-stu-id="d923c-156">Define the SRS v2 views in OMS</span></span>
<span data-ttu-id="d923c-157"><a name="Views"> </a></span><span class="sxs-lookup"><span data-stu-id="d923c-157"></span></span>

<span data-ttu-id="d923c-158">Depois que os dados forem coletados e os campos personalizados forem mapeados, você poderá usar o Designer de exibição do OMS para desenvolver um painel contendo blocos para monitorar os eventos SRS v2.</span><span class="sxs-lookup"><span data-stu-id="d923c-158">Once data is collected and custom fields are mapped, you can use OMS View Designer to develop a Dashboard containing Tiles to monitor SRS v2 events.</span></span> <span data-ttu-id="d923c-159">Use o Designer de modo de exibição para criar os seguintes blocos, consulte [Use o Designer de modo de exibição para criar exibições personalizadas na análise de Log](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-view-designer) , conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="d923c-159">Use View Designer to create the following tiles, refer to [Use View Designer to create custom views in Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-view-designer) as necessary.</span></span>
  
### <a name="create-a-tile-that-shows-healthy-devices"></a><span data-ttu-id="d923c-160">Criar um bloco que mostre os dispositivos íntegros</span><span class="sxs-lookup"><span data-stu-id="d923c-160">Create a tile that shows healthy devices</span></span>

1. <span data-ttu-id="d923c-161">Definir o caso:</span><span class="sxs-lookup"><span data-stu-id="d923c-161">Define the case:</span></span> 
    
    <span data-ttu-id="d923c-162">Este bloco exibe todos os dispositivos de integridade que enviaram uma mensagem de pulsação nos últimos 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="d923c-162">This tile displays all devices that have sent a heartbeat message in the last 10 minutes.</span></span>
    
2. <span data-ttu-id="d923c-163">Atribuir bloco de grupo </span><span class="sxs-lookup"><span data-stu-id="d923c-163">Assign Group Title</span></span> 
    
   ```
   SRS v2
   ```

3. <span data-ttu-id="d923c-164">Marcar a caixa de novo grupo</span><span class="sxs-lookup"><span data-stu-id="d923c-164">Check the new group box</span></span>
    
4. <span data-ttu-id="d923c-165">Adicionar texto de legenda de bloco</span><span class="sxs-lookup"><span data-stu-id="d923c-165">Add the Tile legend text</span></span>
    
   ```
   All healthy devices (Heartbeat sent in last 10 minutes)
   ```

5. <span data-ttu-id="d923c-166">Inserir a consulta de bloco</span><span class="sxs-lookup"><span data-stu-id="d923c-166">Enter the tile query</span></span>
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" TimeGenerated >NOW-10MINUTES|measure count() by SRSDisplayName_CF 
   ```

6. <span data-ttu-id="d923c-167">Inserir a consulta de lista</span><span class="sxs-lookup"><span data-stu-id="d923c-167">Enter the list query</span></span>
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |measure max(TimeGenerated) as LastHB by SRSDisplayName_CF |Where LastHB>NOW-10MINUTES
   ```

7. <span data-ttu-id="d923c-168">Definir o nome dos títulos da coluna</span><span class="sxs-lookup"><span data-stu-id="d923c-168">Define column titles name</span></span>
    
   ```
   Display Name
   ```

8. <span data-ttu-id="d923c-169">Definir o valor dos títulos da coluna</span><span class="sxs-lookup"><span data-stu-id="d923c-169">Define Column titles value</span></span>
    
   ```
   Last HB
   ```

9. <span data-ttu-id="d923c-170">Inserir a consulta de navegação</span><span class="sxs-lookup"><span data-stu-id="d923c-170">Enter Navigation query</span></span>
    
   ```
   {selected item} EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat"|Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="create-the-tile-that-shows-devices-with-connectivity-issues"></a><span data-ttu-id="d923c-171">Criar o bloco que mostra os dispositivos com problemas de conectividade</span><span class="sxs-lookup"><span data-stu-id="d923c-171">Create the tile that shows devices with connectivity issues</span></span>

1. <span data-ttu-id="d923c-172">Definir o caso:</span><span class="sxs-lookup"><span data-stu-id="d923c-172">Define the case:</span></span> 
    
    <span data-ttu-id="d923c-p106">Este bloco exibe todos os dispositivos que não enviaram uma mensagem de pulsação nos últimos 10 minutos. Esses dispositivos podem estar com problemas de conectividade com a rede, com o Exchange ou com o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="d923c-p106">This tile displays all devices that have not sent a heartbeat message in the last 10 minutes. These devices may be experiencing issues with network connectivity, Exchange connectivity, or Skype for Business connectivity.</span></span>
    
2. <span data-ttu-id="d923c-175">Atribuir bloco de grupo </span><span class="sxs-lookup"><span data-stu-id="d923c-175">Assign Group Title</span></span> 
    
   ```
   SRS v2
   ```

3. <span data-ttu-id="d923c-176">Não marcar caixa de novo grupo.</span><span class="sxs-lookup"><span data-stu-id="d923c-176">Do not check the new group box.</span></span> <span data-ttu-id="d923c-177">Você já fez isso ao criar o bloco 1 e não precisa fazer isso novamente.</span><span class="sxs-lookup"><span data-stu-id="d923c-177">You already did this when creating tile 1, and don't need to do it again.</span></span>
    
4. <span data-ttu-id="d923c-178">Adicionar texto de legenda de bloco</span><span class="sxs-lookup"><span data-stu-id="d923c-178">Add the Tile legend text</span></span>
    
   ```
   Devices no longer sending Heartbeat messages
   ```

5. <span data-ttu-id="d923c-179">Inserir a consulta de bloco</span><span class="sxs-lookup"><span data-stu-id="d923c-179">Enter the tile query</span></span>
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |measure max(TimeGenerated) as LastHB by Computer|Where LastHB<NOW-10MINUTES
   ```

6. <span data-ttu-id="d923c-180">Inserir a consulta de lista</span><span class="sxs-lookup"><span data-stu-id="d923c-180">Enter the list query</span></span>
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |measure max(TimeGenerated) as LastHB by Computer|Where LastHB<NOW-10MINUTES
   ```

7. <span data-ttu-id="d923c-181">Definir o nome dos títulos da coluna</span><span class="sxs-lookup"><span data-stu-id="d923c-181">Define column titles name</span></span>
    
   ```
   Device Name
   ```

8. <span data-ttu-id="d923c-182">Definir o valor dos títulos da coluna</span><span class="sxs-lookup"><span data-stu-id="d923c-182">Define Column titles Value</span></span> 
    
   ```
   Last HB
   ```

9. <span data-ttu-id="d923c-183">Inserir a consulta de navegação</span><span class="sxs-lookup"><span data-stu-id="d923c-183">Enter Navigation query</span></span>
    
   ```
   {selected item} EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="list-devices-with-a-hardware-error"></a><span data-ttu-id="d923c-184">Listar dispositivos com erro de hardware </span><span class="sxs-lookup"><span data-stu-id="d923c-184">List devices with a hardware error</span></span>

1. <span data-ttu-id="d923c-185">Definir o caso:</span><span class="sxs-lookup"><span data-stu-id="d923c-185">Define the case:</span></span> 
    
   <span data-ttu-id="d923c-186">Este elemento exibe todos os dispositivos que enviaram uma mensagem indicando uma problemas de componente de hardware de um ou mais nos últimos 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="d923c-186">This tile displays all devices that sent a message indicating a one or more hardware component issues in the last 10 minutes.</span></span> 
    
2. <span data-ttu-id="d923c-187">Atribuir bloco de grupo </span><span class="sxs-lookup"><span data-stu-id="d923c-187">Assign Group Title</span></span> 
    
   ```
   SRS v2
   ```

3. <span data-ttu-id="d923c-188">Não marcar caixa de novo grupo.</span><span class="sxs-lookup"><span data-stu-id="d923c-188">Do not check the new group box.</span></span> <span data-ttu-id="d923c-189">Você já fez isso ao criar o bloco 1 e não precisa fazer isso novamente.</span><span class="sxs-lookup"><span data-stu-id="d923c-189">You already did this when creating tile 1, and don't need to do it again.</span></span>
    
4. <span data-ttu-id="d923c-190">Legenda do bloco: </span><span class="sxs-lookup"><span data-stu-id="d923c-190">Tile legend:</span></span> 
    
   ```
   Devices with a Hardware Error
   ```

5. <span data-ttu-id="d923c-191">Consulta de bloco</span><span class="sxs-lookup"><span data-stu-id="d923c-191">Tile Query</span></span>
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:3001 TimeGenerated>NOW-10MINUTES|measure count() by SRSDisplayName_CF
   ```

6. <span data-ttu-id="d923c-192">Consulta de lista:</span><span class="sxs-lookup"><span data-stu-id="d923c-192">List query:</span></span>
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:3001 TimeGenerated>NOW-10MINUTES|measure max(TimeGenerated) by SRSDisplayName_CF
   ```

7. <span data-ttu-id="d923c-193">Nome dos títulos da coluna: </span><span class="sxs-lookup"><span data-stu-id="d923c-193">Column titles Name:</span></span> 
    
   ```
   Display Name
   ```

8. <span data-ttu-id="d923c-194">Valor dos títulos da coluna: </span><span class="sxs-lookup"><span data-stu-id="d923c-194">Column titles Value:</span></span> 
    
   ```
   Last Error
   ```

9. <span data-ttu-id="d923c-195">Consulta de navegação: </span><span class="sxs-lookup"><span data-stu-id="d923c-195">Navigation query:</span></span> 
    
   ```
   {selected item}  EventLevelName:Error EventID:3001|Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="list-devices-with-an-app-error"></a><span data-ttu-id="d923c-196">Listar dispositivos com erro de aplicativo </span><span class="sxs-lookup"><span data-stu-id="d923c-196">List devices with an App error</span></span>

1. <span data-ttu-id="d923c-197">Definir o caso:</span><span class="sxs-lookup"><span data-stu-id="d923c-197">Define the case:</span></span> 
    
   <span data-ttu-id="d923c-198">Este bloco exibe todos os dispositivos de SRS que reportaram um ou mais erros de componente de aplicativo nos últimos 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="d923c-198">This tile displays all SRS devices that report 1 or more app component errors within the last 10 minutes</span></span>
    
2. <span data-ttu-id="d923c-199">Atribuir bloco de grupo </span><span class="sxs-lookup"><span data-stu-id="d923c-199">Assign Group Title</span></span> 
    
   ```
   SRS v2
   ```

3. <span data-ttu-id="d923c-200">Não marcar caixa de novo grupo.</span><span class="sxs-lookup"><span data-stu-id="d923c-200">Do not check the new group box.</span></span> <span data-ttu-id="d923c-201">Você já fez isso ao criar o bloco 1 e não precisa fazer isso novamente.</span><span class="sxs-lookup"><span data-stu-id="d923c-201">You already did this when creating tile 1, and don't need to do it again.</span></span>
    
4. <span data-ttu-id="d923c-202">Legenda do bloco: </span><span class="sxs-lookup"><span data-stu-id="d923c-202">Tile legend:</span></span> 
   ``` 
    Device with App Errors (in prior 10 minutes)
   ``` 
5. <span data-ttu-id="d923c-203">Consulta de bloco: </span><span class="sxs-lookup"><span data-stu-id="d923c-203">Tile Query:</span></span> 
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:2001 TimeGenerated>NOW-10MINUTES|measure count() by Computer
   ```

6. <span data-ttu-id="d923c-204">Consulta de lista: </span><span class="sxs-lookup"><span data-stu-id="d923c-204">List query:</span></span> 
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:2001 TimeGenerated>NOW-10MINUTES|measure max(TimeGenerated) by Computer
   ```

7. <span data-ttu-id="d923c-205">Nome dos títulos da coluna: </span><span class="sxs-lookup"><span data-stu-id="d923c-205">Column titles Name:</span></span> 
    
   ```
   Device Name
   ```

8. <span data-ttu-id="d923c-206">Valor dos títulos da coluna: </span><span class="sxs-lookup"><span data-stu-id="d923c-206">Column titles Value:</span></span> 
    
   ```
   Last Error
   ```

9. <span data-ttu-id="d923c-207">Consulta de navegação:</span><span class="sxs-lookup"><span data-stu-id="d923c-207">Navigation query:</span></span>
    
   ```
   {selected item} EventLevelName:Error|Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="list-devices-requiring-a-restart"></a><span data-ttu-id="d923c-208">Listar dispositivos que exigem reinicialização</span><span class="sxs-lookup"><span data-stu-id="d923c-208">List devices requiring a restart</span></span>

1. <span data-ttu-id="d923c-209">Definir o caso:</span><span class="sxs-lookup"><span data-stu-id="d923c-209">Define the case:</span></span> 
    
   <span data-ttu-id="d923c-210">Este bloco exibe todos os dispositivos de SRS que foram reinicializados nas últimas 24 horas e a quantidade de reinicializações</span><span class="sxs-lookup"><span data-stu-id="d923c-210">This tile displays all SRS devices that have been restarted in the past 24 hours and number of restarts</span></span>
    
2. <span data-ttu-id="d923c-211">Atribuir bloco de grupo </span><span class="sxs-lookup"><span data-stu-id="d923c-211">Assign Group Title</span></span> 
    
  ```
  SRS v2
  ```

3. <span data-ttu-id="d923c-212">Não marcar caixa de novo grupo.</span><span class="sxs-lookup"><span data-stu-id="d923c-212">Do not check the new group box.</span></span> <span data-ttu-id="d923c-213">Você já fez isso ao criar o bloco 1 e não precisa fazer isso novamente.</span><span class="sxs-lookup"><span data-stu-id="d923c-213">You already did this when creating tile 1, and don't need to do it again.</span></span>
    
4. <span data-ttu-id="d923c-214">Legenda do bloco: </span><span class="sxs-lookup"><span data-stu-id="d923c-214">Tile legend:</span></span> 
    
   ```
   Devices with App restarted (past 24 hours)
   ```

5. <span data-ttu-id="d923c-215">Consulta de bloco: </span><span class="sxs-lookup"><span data-stu-id="d923c-215">Tile Query:</span></span> 
    
   ```
   Type:Event EventLog:"Skype Room System" EventID:4000 TimeGenerated>NOW-24HOURS|measure count() by Computer
   ```

6. <span data-ttu-id="d923c-216">Consulta de lista: </span><span class="sxs-lookup"><span data-stu-id="d923c-216">List query:</span></span> 
    
   ```
   Type:Event EventLog:"Skype Room System" EventID:4000 TimeGenerated>NOW-24HOURS|measure count(EventID) by SRSDisplayName_CF
   ```

7. <span data-ttu-id="d923c-217">Nome dos títulos da coluna: </span><span class="sxs-lookup"><span data-stu-id="d923c-217">Column titles Name:</span></span> 
    
   ```
   Display Name
   ```

8. <span data-ttu-id="d923c-218">Valor dos títulos da coluna: </span><span class="sxs-lookup"><span data-stu-id="d923c-218">Column titles Value:</span></span> 
    
   ```
   Number of restarts
   ```

9. <span data-ttu-id="d923c-219">Consulta de navegação: </span><span class="sxs-lookup"><span data-stu-id="d923c-219">Navigation query:</span></span> 
    
   ```
   {selected item} EventID:4000 TimeGenerated >NOW-24HOURS|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

<span data-ttu-id="d923c-p111">Isso conclui a criação do modo de exibição. Os alertas atualmente disponíveis são todos refletidos em um ou mais desses blocos.</span><span class="sxs-lookup"><span data-stu-id="d923c-p111">That completes view creation. The alerts currently available are all reflected in one or more of these tiles.</span></span>
## <a name="see-also"></a><span data-ttu-id="d923c-222">Ver também</span><span class="sxs-lookup"><span data-stu-id="d923c-222">See also</span></span>
<span data-ttu-id="d923c-223"><a name="Views"> </a></span><span class="sxs-lookup"><span data-stu-id="d923c-223"></span></span>

#### 

[<span data-ttu-id="d923c-224">Planejar o gerenciamento de v2 Skype sala sistemas com OMS</span><span class="sxs-lookup"><span data-stu-id="d923c-224">Plan Skype Room Systems v2 management with OMS</span></span>](../../plan-your-deployment/clients-and-devices/oms-management.md)
  
[<span data-ttu-id="d923c-225">Gerencia dispositivos de v2 de sistemas de sala Skype com OMS</span><span class="sxs-lookup"><span data-stu-id="d923c-225">Manage Skype Room Systems v2 devices with OMS</span></span>](../../manage/skype-room-systems-v2/oms.md)

