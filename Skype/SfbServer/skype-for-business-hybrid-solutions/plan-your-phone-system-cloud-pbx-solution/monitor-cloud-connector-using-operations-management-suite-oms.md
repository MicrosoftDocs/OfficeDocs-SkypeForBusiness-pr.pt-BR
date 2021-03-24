---
title: Monitor Cloud Connector utilizando Operations Management Suite (OMS).
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: Leia este tópico para saber como monitorar sua implantação do Cloud Connector versão 2.1 e posterior usando o Microsoft Operations Management Suite (OMS).
ms.openlocfilehash: 55685aae01bdcc3c7c979627dbba910bb33203fa
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098537"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a><span data-ttu-id="80ab6-103">Monitor Cloud Connector utilizando Operations Management Suite (OMS).</span><span class="sxs-lookup"><span data-stu-id="80ab6-103">Monitor Cloud Connector using Operations Management Suite (OMS)</span></span>

> [!Important]
> <span data-ttu-id="80ab6-104">O Cloud Connector Edition se aposentará em 31 de julho de 2021 junto com o Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="80ab6-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="80ab6-105">Depois que sua organização tiver atualizado para o Teams, saiba como conectar sua rede de telefonia local ao Teams usando [Roteamento Direto.](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="80ab6-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="80ab6-106">Leia este tópico para saber como monitorar sua implantação do Cloud Connector versão 2.1 e posterior usando o Microsoft Operations Management Suite (OMS).</span><span class="sxs-lookup"><span data-stu-id="80ab6-106">Read this topic to learn how to monitor your Cloud Connector version 2.1 and later deployment by using Microsoft Operations Management Suite (OMS).</span></span>

<span data-ttu-id="80ab6-107">Agora você pode monitorar sua implantação do Cloud Connector versão 2.1 e posterior usando o Operations Management Suite (OMS), uma solução de gerenciamento de TI na nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="80ab6-107">You can now monitor your Cloud Connector version 2.1 and later deployment by using Operations Management Suite (OMS), a Microsoft cloud IT management solution.</span></span> <span data-ttu-id="80ab6-108">O OMS Log Analytics permite monitorar e analisar a disponibilidade e o desempenho de recursos, incluindo máquinas físicas e virtuais.</span><span class="sxs-lookup"><span data-stu-id="80ab6-108">OMS Log Analytics enables you to monitor and analyze the availability and performance of resources including physical and virtual machines.</span></span> <span data-ttu-id="80ab6-109">Para obter mais informações sobre OMS e Análise de Log, consulte [O que é Operations Management Suite (OMS)?](/azure/operations-management-suite/operations-management-suite-overview)</span><span class="sxs-lookup"><span data-stu-id="80ab6-109">For more information about OMS and Log Analytics, see [What is Operations Management Suite (OMS)?](/azure/operations-management-suite/operations-management-suite-overview)</span></span>

<span data-ttu-id="80ab6-110">Este tópico contém as seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="80ab6-110">This topic contains the following sections:</span></span>

- <span data-ttu-id="80ab6-111">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="80ab6-111">Prerequisites</span></span>

- <span data-ttu-id="80ab6-112">Configurar o Cloud Connector para usar o OMS</span><span class="sxs-lookup"><span data-stu-id="80ab6-112">Configure Cloud Connector to use OMS</span></span>

- <span data-ttu-id="80ab6-113">Configurar OMS</span><span class="sxs-lookup"><span data-stu-id="80ab6-113">Configure OMS</span></span>

- <span data-ttu-id="80ab6-114">Analisar os alertas no repositório do Log Analytics</span><span class="sxs-lookup"><span data-stu-id="80ab6-114">Analyze the alerts in your Log Analytics repository</span></span>

- <span data-ttu-id="80ab6-115">Conjunto de monitoramento recomendado</span><span class="sxs-lookup"><span data-stu-id="80ab6-115">Recommended monitoring set</span></span>

## <a name="prerequisites"></a><span data-ttu-id="80ab6-116">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="80ab6-116">Prerequisites</span></span>

<span data-ttu-id="80ab6-117">Antes de usar o OMS para monitorar a implantação do Cloud Connector, você precisará do seguinte:</span><span class="sxs-lookup"><span data-stu-id="80ab6-117">Before you can use OMS to monitor your Cloud Connector deployment, you will need the following:</span></span>

- <span data-ttu-id="80ab6-118">**Uma conta do Azure e um espaço de trabalho OMS.**</span><span class="sxs-lookup"><span data-stu-id="80ab6-118">**An Azure account and an OMS workspace.**</span></span> <span data-ttu-id="80ab6-119">Se você ainda não tiver uma conta do Azure, precisará criar uma para usar o OMS Log Analytics.</span><span class="sxs-lookup"><span data-stu-id="80ab6-119">If you don't already have an Azure account, you will need to create one to use OMS Log Analytics.</span></span> <span data-ttu-id="80ab6-120">Para obter informações sobre como criar uma conta do Azure e configurar um espaço de trabalho OMS, consulte [Get started with a Log Analytics workspace](/azure/log-analytics/log-analytics-get-started).</span><span class="sxs-lookup"><span data-stu-id="80ab6-120">For information about how to create an Azure account and set up an OMS workspace, see [Get started with a Log Analytics workspace](/azure/log-analytics/log-analytics-get-started).</span></span>

- <span data-ttu-id="80ab6-121">**Cloud Connector versão 2.1 ou posterior**</span><span class="sxs-lookup"><span data-stu-id="80ab6-121">**Cloud Connector version 2.1 or later**</span></span>

- <span data-ttu-id="80ab6-122">**A nova pesquisa de log do Log Analytics** é necessária para monitoramento do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="80ab6-122">**Log Analytics new log search** is required for Cloud Connector monitoring.</span></span> <span data-ttu-id="80ab6-123">Para obter mais informações, [consulte Upgrade your Azure Log Analytics workspace to new log search](/azure/log-analytics/log-analytics-log-search-upgrade).</span><span class="sxs-lookup"><span data-stu-id="80ab6-123">For more information, see [Upgrade your Azure Log Analytics workspace to new log search](/azure/log-analytics/log-analytics-log-search-upgrade).</span></span>

## <a name="configure-cloud-connector-to-use-oms"></a><span data-ttu-id="80ab6-124">Configurar o Cloud Connector para usar o OMS</span><span class="sxs-lookup"><span data-stu-id="80ab6-124">Configure Cloud Connector to use OMS</span></span>

<span data-ttu-id="80ab6-125">Você precisará configurar seu ambiente local do Cloud Connector para usar o OMS.</span><span class="sxs-lookup"><span data-stu-id="80ab6-125">You'll need to configure your Cloud Connector on-premises environment to use OMS.</span></span> <span data-ttu-id="80ab6-126">Para fazer isso, você precisará da ID e da chave do espaço de trabalho OMS, que você pode encontrar usando o portal OMS da seguinte forma: Configurações - Fontes Conectadas - Servidores \> \> Windows:</span><span class="sxs-lookup"><span data-stu-id="80ab6-126">To do this, you will need your OMS workspace ID and key, which you can find by using the OMS portal as follows: Settings --\>Connected Sources --\> Windows Servers:</span></span>

![Captura de tela para OMS do Cloud Connector](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

<span data-ttu-id="80ab6-128">A forma como você configura o Cloud Connector para usar o OMS depende do cenário:</span><span class="sxs-lookup"><span data-stu-id="80ab6-128">How you configure Cloud Connector to use OMS depends on your scenario:</span></span>

- <span data-ttu-id="80ab6-129">**Se você estiver instalando um** novo dispositivo do Cloud Connector ou quiser implantar um dispositivo de novo, siga estas etapas antes de executar Install-CcAppliance:</span><span class="sxs-lookup"><span data-stu-id="80ab6-129">**If you are installing a new Cloud Connector appliance or you want to re-deploy an appliance**, follow these steps before you run Install-CcAppliance:</span></span>

    1. <span data-ttu-id="80ab6-130">Na seção CloudConnector.ini arquivo [Common], de definir o parâmetro OMSEnabled como True.</span><span class="sxs-lookup"><span data-stu-id="80ab6-130">In the CloudConnector.ini file [Common] section, set the OMSEnabled parameter to True.</span></span>

        <span data-ttu-id="80ab6-131">Sempre que o Cloud Connector for implantado ou atualizado, ele tentará instalar o agente OMS automaticamente nas VMs.</span><span class="sxs-lookup"><span data-stu-id="80ab6-131">Each time Cloud Connector is deployed or upgraded, it will try to install the OMS agent automatically onto the VMs.</span></span> <span data-ttu-id="80ab6-132">Habilita esse recurso para que o agente OMS possa sobreviver à atualização automática do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="80ab6-132">Enable this feature so the OMS agent can survive the Cloud Connector automatic update.</span></span>

    2. <span data-ttu-id="80ab6-133">Para configurar a ID e a chave do OMS, execute Set-CcCredential -AccountType OMSWorkspace.</span><span class="sxs-lookup"><span data-stu-id="80ab6-133">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

- <span data-ttu-id="80ab6-134">**Se você estiver instalando um agente OMS em um dispositivo do Cloud Connector** existente, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="80ab6-134">**If you are installing an OMS agent onto an existing Cloud Connector appliance**, follow these steps:</span></span>

    1. <span data-ttu-id="80ab6-135">Na seção CloudConnector.ini arquivo [Common], de definir OMSEnabled=true.</span><span class="sxs-lookup"><span data-stu-id="80ab6-135">In the CloudConnector.ini file [Common] section, set OMSEnabled=true.</span></span> 

    2. <span data-ttu-id="80ab6-136">Execute Import-CcConfiguration.</span><span class="sxs-lookup"><span data-stu-id="80ab6-136">Run Import-CcConfiguration.</span></span> 

    3. <span data-ttu-id="80ab6-137">Execute Install-CcOMSAgent.</span><span class="sxs-lookup"><span data-stu-id="80ab6-137">Run Install-CcOMSAgent.</span></span> 

        > [!NOTE]
        > <span data-ttu-id="80ab6-138">Se a credencial OMSWorkspace nunca tiver sido definida, você será solicitado a solicitar a credencial ao executar install-CcOMSAgent.</span><span class="sxs-lookup"><span data-stu-id="80ab6-138">If the OMSWorkspace credential has never been set, you are prompted for the credential when you run install-CcOMSAgent.</span></span> 

- <span data-ttu-id="80ab6-139">**Se você quiser atualizar a ID ou a chave do espaço de trabalho OMS em um dispositivo do Cloud Connector que já instalou um agente OMS:**</span><span class="sxs-lookup"><span data-stu-id="80ab6-139">**If you want to update the OMS workspace ID or key in a Cloud Connector appliance that has already installed an OMS agent:**</span></span>

    1. <span data-ttu-id="80ab6-140">Para configurar a ID e a chave do OMS, execute Set-CcCredential -AccountType OMSWorkspace.</span><span class="sxs-lookup"><span data-stu-id="80ab6-140">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

    2. <span data-ttu-id="80ab6-141">Para aplicar as atualizações, execute Install-CcOMSAgent.</span><span class="sxs-lookup"><span data-stu-id="80ab6-141">To apply the updates, run Install-CcOMSAgent.</span></span> 

- <span data-ttu-id="80ab6-142">**Para todos os cenários, verifique se os agentes estão conectados da seguinte forma:**</span><span class="sxs-lookup"><span data-stu-id="80ab6-142">**For all scenarios, verify that the agents are connected as follows:**</span></span>

    <span data-ttu-id="80ab6-143">No portal OMS, acesse Configurações - \> Fontes Conectadas - \> Servidores Windows.</span><span class="sxs-lookup"><span data-stu-id="80ab6-143">In the OMS portal, go to Settings -\> Connected Sources -\> Windows Servers.</span></span> <span data-ttu-id="80ab6-144">Você verá uma lista de máquinas conectadas.</span><span class="sxs-lookup"><span data-stu-id="80ab6-144">You will see a list of connected machines.</span></span> 

## <a name="configure-oms"></a><span data-ttu-id="80ab6-145">Configurar OMS</span><span class="sxs-lookup"><span data-stu-id="80ab6-145">Configure OMS</span></span>

<span data-ttu-id="80ab6-146">Em seguida, você precisará especificar sua configuração OMS usando o portal OMS.</span><span class="sxs-lookup"><span data-stu-id="80ab6-146">Next, you will need to specify your OMS configuration by using the OMS portal.</span></span> <span data-ttu-id="80ab6-147">Especificamente, você precisará:</span><span class="sxs-lookup"><span data-stu-id="80ab6-147">Specifically, you will need to:</span></span>

- <span data-ttu-id="80ab6-148">Especifique informações sobre logs de eventos e contadores de desempenho.</span><span class="sxs-lookup"><span data-stu-id="80ab6-148">Specify information about event logs and performance counters.</span></span>

- <span data-ttu-id="80ab6-149">Criar alertas.</span><span class="sxs-lookup"><span data-stu-id="80ab6-149">Create alerts.</span></span> 

### <a name="specify-information-about-event-logs-and-performance-counters"></a><span data-ttu-id="80ab6-150">Especificar informações sobre logs de eventos e contadores de desempenho</span><span class="sxs-lookup"><span data-stu-id="80ab6-150">Specify information about event logs and performance counters</span></span>

<span data-ttu-id="80ab6-151">No portal OMS, você deve especificar informações sobre os logs de eventos e os contadores de desempenho da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="80ab6-151">In the OMS portal, you must specify information about the event logs and performance counters as follows:</span></span>

1. <span data-ttu-id="80ab6-152">Vá para Configurações- Dados- Logs de \> eventos do Windows e adicione logs de eventos \> para:</span><span class="sxs-lookup"><span data-stu-id="80ab6-152">Go to Settings-\>Data-\>Windows Event logs, and add event logs for:</span></span> 

   - <span data-ttu-id="80ab6-153">Lync Server</span><span class="sxs-lookup"><span data-stu-id="80ab6-153">Lync Server</span></span>

   - <span data-ttu-id="80ab6-154">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="80ab6-154">Application</span></span>

     > [!NOTE]
     > <span data-ttu-id="80ab6-155">Você deve inserir manualmente o Lync Server na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="80ab6-155">You must manually enter Lync Server in the text box.</span></span> <span data-ttu-id="80ab6-156">Ele não aparece como uma opção na listada.</span><span class="sxs-lookup"><span data-stu-id="80ab6-156">It does not appear as an option in the drop-down list.</span></span> 

     <span data-ttu-id="80ab6-157">Para obter mais informações, consulte Fontes [de dados do log de eventos do Windows no Log Analytics](/azure/log-analytics/log-analytics-data-sources-windows-events)</span><span class="sxs-lookup"><span data-stu-id="80ab6-157">For more information, see [Windows event log data sources in Log Analytics](/azure/log-analytics/log-analytics-data-sources-windows-events)</span></span>

2. <span data-ttu-id="80ab6-158">Vá para Configurações- Dados- Contadores de Desempenho do \> \> Windows e adicione contadores de desempenho para:</span><span class="sxs-lookup"><span data-stu-id="80ab6-158">Go to Settings-\>Data-\> Windows Performance Counters, and add performance counters for:</span></span> 

   - <span data-ttu-id="80ab6-159">**Contadores de nível do sistema operacional**.</span><span class="sxs-lookup"><span data-stu-id="80ab6-159">**OS level counters**.</span></span> <span data-ttu-id="80ab6-160">Você pode adicionar contadores de nível de sistema operacional, como uso do processador, uso de memória, uso de rede ou pode usar soluções existentes, como Capacidade e Desempenho, Monitor de Desempenho de Rede sem adicionar contadores explicitamente.</span><span class="sxs-lookup"><span data-stu-id="80ab6-160">You can add OS level counters, such as processor usage, memory usage, network usage, or you can use existing solutions such as Capacity and Performance, Network Performance Monitor without adding counters explicitly.</span></span> <span data-ttu-id="80ab6-161">Não importa como você decida monitorá-los, a Microsoft recomenda que você monitore esses contadores do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="80ab6-161">No matter how you decide to monitor them, Microsoft recommends that you monitor these OS counters.</span></span>

   - <span data-ttu-id="80ab6-162">**Contadores do Skype for Business.**</span><span class="sxs-lookup"><span data-stu-id="80ab6-162">**Skype for Business counters**.</span></span> <span data-ttu-id="80ab6-163">Há vários contadores fornecidos pelo Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="80ab6-163">There are numerous counters provided by Skype for Business.</span></span> <span data-ttu-id="80ab6-164">Você pode encontrar esses contadores fazendo logo em qualquer Servidor de Mediação e abrindo o Monitor de Desempenho.</span><span class="sxs-lookup"><span data-stu-id="80ab6-164">You can find these counters by logging on to any Mediation Server and opening the Performance Monitor.</span></span> <span data-ttu-id="80ab6-165">Esses contadores começam com "LS:".</span><span class="sxs-lookup"><span data-stu-id="80ab6-165">These counters start with "LS:".</span></span> <span data-ttu-id="80ab6-166">A Microsoft recomenda que você comece com os seguintes contadores de capacidade no mínimo e adicione outros que são de interesse:</span><span class="sxs-lookup"><span data-stu-id="80ab6-166">Microsoft recommends that you start with the following capacity counters at a minimum, and add others that are of interest:</span></span>

     <span data-ttu-id="80ab6-167">Total de chamadas ativas:</span><span class="sxs-lookup"><span data-stu-id="80ab6-167">Total active calls:</span></span>

       - <span data-ttu-id="80ab6-168">LS:MediationServer - Chamadas de entrada(_Total) \- Atual</span><span class="sxs-lookup"><span data-stu-id="80ab6-168">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

       - <span data-ttu-id="80ab6-169">LS:MediationServer - Chamadas de saída(_Total) \- Atual</span><span class="sxs-lookup"><span data-stu-id="80ab6-169">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

     <span data-ttu-id="80ab6-170">Total de chamadas de bypass de mídia ativa:</span><span class="sxs-lookup"><span data-stu-id="80ab6-170">Total active media bypass calls:</span></span>

       - <span data-ttu-id="80ab6-171">LS:MediationServer - Chamadas de entrada(_Total) Chamadas de bypass de \- mídia ativas</span><span class="sxs-lookup"><span data-stu-id="80ab6-171">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span> 

       - <span data-ttu-id="80ab6-172">LS:MediationServer - Chamadas de saída(_Total) Chamadas de bypass de \- mídia ativas</span><span class="sxs-lookup"><span data-stu-id="80ab6-172">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span> 

     > [!NOTE]
     > <span data-ttu-id="80ab6-173">Você deve inserir manualmente os contadores de desempenho na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="80ab6-173">You must manually enter the performance counters in the text box.</span></span> <span data-ttu-id="80ab6-174">Eles não aparecem como opções na lista lista listada.</span><span class="sxs-lookup"><span data-stu-id="80ab6-174">They do not appear as options in the drop-down list.</span></span> 

     <span data-ttu-id="80ab6-175">Para obter mais informações, consulte [Fontes de dados de desempenho do Windows e linux no Log Analytics](/azure/log-analytics/log-analytics-data-sources-performance-counters)</span><span class="sxs-lookup"><span data-stu-id="80ab6-175">For more information, see [Windows and Linux performance data sources in Log Analytics](/azure/log-analytics/log-analytics-data-sources-performance-counters)</span></span>

### <a name="create-alerts"></a><span data-ttu-id="80ab6-176">Criar alertas</span><span class="sxs-lookup"><span data-stu-id="80ab6-176">Create alerts</span></span>

<span data-ttu-id="80ab6-177">Há dois tipos de alertas no OMS: número de alertas de resultados e alertas de medida métrica.</span><span class="sxs-lookup"><span data-stu-id="80ab6-177">There are two types of alerts in OMS: Number of results alerts and Metric measurement alerts.</span></span> <span data-ttu-id="80ab6-178">Para obter mais informações sobre como criar alertas, consulte [Working with alert rules in Log Analytics](/azure/log-analytics/log-analytics-alerts-creating).</span><span class="sxs-lookup"><span data-stu-id="80ab6-178">For more information about creating alerts, see [Working with alert rules in Log Analytics](/azure/log-analytics/log-analytics-alerts-creating).</span></span>

<span data-ttu-id="80ab6-179">Você deve considerar o seguinte ao criar alertas:</span><span class="sxs-lookup"><span data-stu-id="80ab6-179">You should consider the following when creating alerts:</span></span>

- <span data-ttu-id="80ab6-180">Certifique-se de que o alerta seja um alerta número de resultados, que é a seleção padrão.</span><span class="sxs-lookup"><span data-stu-id="80ab6-180">Make sure the alert is a Number-of-results alert, which is the default selection.</span></span> 

- <span data-ttu-id="80ab6-181">As consultas de demonstração exigem que "Número de resultados" seja definido como "Maior que 0".</span><span class="sxs-lookup"><span data-stu-id="80ab6-181">The demo queries require that "Number of results" is set to "Greater than 0".</span></span> 

- <span data-ttu-id="80ab6-182">É recomendável definir a janela Hora e a frequência de alerta como 5 minutos.</span><span class="sxs-lookup"><span data-stu-id="80ab6-182">It is recommended that you set both Time window and Alert frequency to 5 minutes.</span></span> 

- <span data-ttu-id="80ab6-183">É recomendável que você não habilita "Suprimir alertas" para alertas de demonstração.</span><span class="sxs-lookup"><span data-stu-id="80ab6-183">It is recommended that you do not enable "Suppress alerts" for demo alerts.</span></span> 

- <span data-ttu-id="80ab6-184">Para cenários de alerta típicos, a Microsoft recomenda a criação de um par de alertas: um alerta de erro e um alerta de redefinição.</span><span class="sxs-lookup"><span data-stu-id="80ab6-184">For typical alert scenarios, Microsoft recommends creating a pair of alerts: one error alert and one reset alert.</span></span> <span data-ttu-id="80ab6-185">Para o alerta de erro, selecione nível de gravidade Crítico; para o alerta de redefinição, selecione nível de gravidade Informacional .</span><span class="sxs-lookup"><span data-stu-id="80ab6-185">For the error alert, select severity level Critical; for the reset alert, select severity level Informational .</span></span>

<span data-ttu-id="80ab6-186">As seções a seguir descrevem como criar alertas de exemplo.</span><span class="sxs-lookup"><span data-stu-id="80ab6-186">The following sections describe how to create sample alerts.</span></span>

 <span data-ttu-id="80ab6-187">**Crie um par de alertas: "RTCMEDSRV NÃO está sendo executado em Servidores de Mediação" e "RTCMEDSRV está de volta em execução em Servidores de Mediação"**</span><span class="sxs-lookup"><span data-stu-id="80ab6-187">**Create an alert pair: "RTCMEDSRV is NOT running in Mediation Servers" and "RTCMEDSRV is back in running in Mediation Servers"**</span></span>

<span data-ttu-id="80ab6-188">Para criar esse par de alertas:</span><span class="sxs-lookup"><span data-stu-id="80ab6-188">To create this alert pair:</span></span>

- <span data-ttu-id="80ab6-189">A consulta para o alerta de erro é:</span><span class="sxs-lookup"><span data-stu-id="80ab6-189">The query for the error alert is:</span></span>

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    <span data-ttu-id="80ab6-190">A consulta usa o filtro do computador  *onde Computer contém "MediationServer"*  .</span><span class="sxs-lookup"><span data-stu-id="80ab6-190">The query uses the computer filter  *where Computer contains "MediationServer"*  .</span></span> <span data-ttu-id="80ab6-191">O filtro seleciona apenas o computador cujo nome contém a cadeia de caracteres "MediationServer".</span><span class="sxs-lookup"><span data-stu-id="80ab6-191">The filter selects only the computer whose name contains the string "MediationServer".</span></span>

     <span data-ttu-id="80ab6-192">Você substituiria o filtro por seu próprio filtro de computador ou simplesmente o removeria.</span><span class="sxs-lookup"><span data-stu-id="80ab6-192">You would replace the filter with your own computer filter or simply remove it.</span></span> <span data-ttu-id="80ab6-193">Você pode criar filtros de cadeia de caracteres complexos sem expressões regulares.</span><span class="sxs-lookup"><span data-stu-id="80ab6-193">You can create complex string filters without regular expressions.</span></span> <span data-ttu-id="80ab6-194">Para obter mais informações, consulte [Operadores de cadeia de caracteres](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span><span class="sxs-lookup"><span data-stu-id="80ab6-194">For more information, see [String operators](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span></span> <span data-ttu-id="80ab6-195">Você também pode optar por usar expressões regulares.</span><span class="sxs-lookup"><span data-stu-id="80ab6-195">You can also choose to use regular expressions.</span></span> <span data-ttu-id="80ab6-196">Além disso, você pode criar um grupo de computadores salvando uma consulta de pesquisa e usando esse grupo como filtro de computador na consulta de alerta.</span><span class="sxs-lookup"><span data-stu-id="80ab6-196">Moreover, you can create a computer group by saving a search query and using that group as your computer filter in your alert query.</span></span> <span data-ttu-id="80ab6-197">Para obter mais informações, consulte [Grupos de computadores em Pesquisas de log do Log Analytics.](/azure/log-analytics/log-analytics-computer-groups)</span><span class="sxs-lookup"><span data-stu-id="80ab6-197">For more information, see [Computer groups in Log Analytics log searches](/azure/log-analytics/log-analytics-computer-groups).</span></span>

    <span data-ttu-id="80ab6-198">Para cada computador, a consulta de erro obterá o último log de eventos para o início do serviço RTCMEDSRV e a parada de serviço.</span><span class="sxs-lookup"><span data-stu-id="80ab6-198">For each computer, the error query will get the last event log for both the RTCMEDSRV service start and service stop.</span></span> <span data-ttu-id="80ab6-199">Ele retornará um log se o último evento for o evento de parada de serviço; ele não retornará nada se o último evento for o evento de início do serviço.</span><span class="sxs-lookup"><span data-stu-id="80ab6-199">It will return one log if the last event is the service stop event; it will return nothing if the last event is the service start event.</span></span> <span data-ttu-id="80ab6-200">Em resumo, a consulta retornaria uma lista de servidores cujo RTCMEDSRV é interrompido na janela de tempo.</span><span class="sxs-lookup"><span data-stu-id="80ab6-200">In short, the query would return a list of servers whose RTCMEDSRV is stopped in the time window.</span></span> 

- <span data-ttu-id="80ab6-201">A consulta para o alerta de redefinição é:</span><span class="sxs-lookup"><span data-stu-id="80ab6-201">The query for the reset alert is:</span></span>

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    <span data-ttu-id="80ab6-202">A consulta de redefinição faz exatamente o oposto da consulta de erro.</span><span class="sxs-lookup"><span data-stu-id="80ab6-202">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="80ab6-203">Para cada computador, ele retornará um se o último evento for o evento de início do serviço; ele não retornará nada se o último evento for o evento de parada de serviço.</span><span class="sxs-lookup"><span data-stu-id="80ab6-203">For each computer, it will return one if the last event is the service start event; it will return nothing if the last event is the service stop event.</span></span>

<span data-ttu-id="80ab6-204">**Crie um par de alertas: " Muitas chamadas simultâneas em Servidores de Mediação" e "Chamadas simultâneas voltam à carga normal"**</span><span class="sxs-lookup"><span data-stu-id="80ab6-204">**Create an alert pair: " Too many concurrent calls in Mediation Servers" and "Concurrent calls fall back to normal load"**</span></span>

<span data-ttu-id="80ab6-205">Para criar esse alerta:</span><span class="sxs-lookup"><span data-stu-id="80ab6-205">To create this alert:</span></span>

- <span data-ttu-id="80ab6-206">A consulta para o alerta de erro é:</span><span class="sxs-lookup"><span data-stu-id="80ab6-206">The query for the error alert is:</span></span>

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    <span data-ttu-id="80ab6-207">Para cada computador, a consulta receberá os últimos contadores para chamada de entrada e chamada de saída e soma esses dois valores.</span><span class="sxs-lookup"><span data-stu-id="80ab6-207">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="80ab6-208">Ele retornará um log se o valor da soma exceder 500; ele não retornará nada se não retornar.</span><span class="sxs-lookup"><span data-stu-id="80ab6-208">It will return one log if the sum value exceeds 500; it will return nothing if it doesn't.</span></span> <span data-ttu-id="80ab6-209">Em resumo, a consulta retornaria uma lista de servidores cujas chamadas simultâneas são muitas na janela de tempo.</span><span class="sxs-lookup"><span data-stu-id="80ab6-209">In short, the query would return a list of servers whose concurrent calls are too many in the time window.</span></span>

- <span data-ttu-id="80ab6-210">A consulta para o alerta de redefinição é:</span><span class="sxs-lookup"><span data-stu-id="80ab6-210">The query for the reset alert is:</span></span>

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    <span data-ttu-id="80ab6-211">A consulta de redefinição faz exatamente o oposto da consulta de erro.</span><span class="sxs-lookup"><span data-stu-id="80ab6-211">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="80ab6-212">Para cada computador, a consulta receberá os últimos contadores para chamada de entrada e chamada de saída e soma esses dois valores.</span><span class="sxs-lookup"><span data-stu-id="80ab6-212">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="80ab6-213">Ele retornará um log se o valor da soma for menor que 500; ele não retornará nada caso contrário.</span><span class="sxs-lookup"><span data-stu-id="80ab6-213">It will return one log if the sum value is less than 500; it will return nothing otherwise.</span></span>

<span data-ttu-id="80ab6-214">**Criar um alerta: alerta "Uso da CPU \> 90 ou RTCMEDIARELAY interrompido em Servidores"**</span><span class="sxs-lookup"><span data-stu-id="80ab6-214">**Create an alert: "CPU usage \> 90 or RTCMEDIARELAY stopped in Servers" alert**</span></span>

<span data-ttu-id="80ab6-215">Para criar esse alerta, a consulta é:</span><span class="sxs-lookup"><span data-stu-id="80ab6-215">To create this alert, the query is:</span></span>

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

<span data-ttu-id="80ab6-216">A consulta obterá todo o contador de uso do processador e o evento de parada de serviço de todos os computadores e retornará um log se o uso do processador exceder 90% ou se o serviço for interrompido.</span><span class="sxs-lookup"><span data-stu-id="80ab6-216">The query will get all processor usage counter and service stop event from all computers and return one log if either processor usage exceeds 90% or service is ever stopped.</span></span> 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a><span data-ttu-id="80ab6-217">Analisar os alertas no repositório do Log Analytics</span><span class="sxs-lookup"><span data-stu-id="80ab6-217">Analyze the alerts in your Log Analytics repository</span></span>

<span data-ttu-id="80ab6-218">Para analisar os alertas em seu repositório, use a solução gerenciamento de alertas.</span><span class="sxs-lookup"><span data-stu-id="80ab6-218">To analyze the alerts in your repository, use the Alert Management solution.</span></span> <span data-ttu-id="80ab6-219">Para obter mais informações, consulte [Solução de Gerenciamento de Alertas no Operations Management Suite (OMS)](/azure/log-analytics/log-analytics-solution-alert-management)</span><span class="sxs-lookup"><span data-stu-id="80ab6-219">For more information, see [Alert Management solution in Operations Management Suite (OMS)](/azure/log-analytics/log-analytics-solution-alert-management)</span></span>

## <a name="recommended-minimal-monitoring-set"></a><span data-ttu-id="80ab6-220">Conjunto de monitoramento mínimo recomendado</span><span class="sxs-lookup"><span data-stu-id="80ab6-220">Recommended minimal monitoring set</span></span>

<span data-ttu-id="80ab6-221">Para identificar problemas com logs de eventos e contadores de desempenho:</span><span class="sxs-lookup"><span data-stu-id="80ab6-221">To identify issues with event logs and performance counters:</span></span> 

- <span data-ttu-id="80ab6-222">**Logs de eventos.**</span><span class="sxs-lookup"><span data-stu-id="80ab6-222">**Event logs.**</span></span> <span data-ttu-id="80ab6-223">Para qualquer problema, deve haver um par de eventos, com um conjunto de eventos para indicar que algo está errado, enquanto o outro indica que tudo está bem.</span><span class="sxs-lookup"><span data-stu-id="80ab6-223">For any issue, there should be an events pair, with one set of events to indicate something is wrong, while the other indicates that everything is well.</span></span> <span data-ttu-id="80ab6-224">Para qualquer determinado período de tempo, é o último evento registrado que indicará se algo está errado para esse período.</span><span class="sxs-lookup"><span data-stu-id="80ab6-224">For any given time period, it is the last event recorded that will indicate whether something is amiss for that time period.</span></span>

- <span data-ttu-id="80ab6-225">**Contadores de desempenho.**</span><span class="sxs-lookup"><span data-stu-id="80ab6-225">**Performance Counters.**</span></span> <span data-ttu-id="80ab6-226">Deve haver um limite para os contadores monitorados.</span><span class="sxs-lookup"><span data-stu-id="80ab6-226">There should be a threshold for the monitored counters.</span></span>

<span data-ttu-id="80ab6-227">A tabela a seguir lista os serviços que a Microsoft recomenda monitoramento listando as IDs do evento stop and start:</span><span class="sxs-lookup"><span data-stu-id="80ab6-227">The following table lists the services that Microsoft recommends monitoring by listing the stop and start event IDs:</span></span>

|<span data-ttu-id="80ab6-228">Nome do Serviço</span><span class="sxs-lookup"><span data-stu-id="80ab6-228">Service Name</span></span>  <br/> |<span data-ttu-id="80ab6-229">Função de servidor de destino</span><span class="sxs-lookup"><span data-stu-id="80ab6-229">Target Server Role</span></span>  <br/> |<span data-ttu-id="80ab6-230">ID do evento Stop</span><span class="sxs-lookup"><span data-stu-id="80ab6-230">Stop Event ID</span></span>  <br/> |<span data-ttu-id="80ab6-231">ID do evento Start</span><span class="sxs-lookup"><span data-stu-id="80ab6-231">Start Event ID</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="80ab6-232">RTCMEDSRV</span><span class="sxs-lookup"><span data-stu-id="80ab6-232">RTCMEDSRV</span></span>  <br/> |<span data-ttu-id="80ab6-233">Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="80ab6-233">Mediation Server</span></span>  <br/> |<span data-ttu-id="80ab6-234">25003</span><span class="sxs-lookup"><span data-stu-id="80ab6-234">25003</span></span>  <br/> |<span data-ttu-id="80ab6-235">25002</span><span class="sxs-lookup"><span data-stu-id="80ab6-235">25002</span></span>  <br/> |
|<span data-ttu-id="80ab6-236">RTCSRV</span><span class="sxs-lookup"><span data-stu-id="80ab6-236">RTCSRV</span></span>  <br/> |<span data-ttu-id="80ab6-237">Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="80ab6-237">Edge Server</span></span>  <br/> |<span data-ttu-id="80ab6-238">12289</span><span class="sxs-lookup"><span data-stu-id="80ab6-238">12289</span></span>  <br/> |<span data-ttu-id="80ab6-239">12288</span><span class="sxs-lookup"><span data-stu-id="80ab6-239">12288</span></span>  <br/> |
|<span data-ttu-id="80ab6-240">RTCMRAUTH</span><span class="sxs-lookup"><span data-stu-id="80ab6-240">RTCMRAUTH</span></span>  <br/> |<span data-ttu-id="80ab6-241">Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="80ab6-241">Edge Server</span></span>  <br/> |<span data-ttu-id="80ab6-242">19003</span><span class="sxs-lookup"><span data-stu-id="80ab6-242">19003</span></span>  <br/> |<span data-ttu-id="80ab6-243">19002</span><span class="sxs-lookup"><span data-stu-id="80ab6-243">19002</span></span>  <br/> |
|<span data-ttu-id="80ab6-244">RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="80ab6-244">RTCMEDIARELAY</span></span>  <br/> |<span data-ttu-id="80ab6-245">Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="80ab6-245">Edge Server</span></span>  <br/> |<span data-ttu-id="80ab6-246">22003</span><span class="sxs-lookup"><span data-stu-id="80ab6-246">22003</span></span>  <br/> |<span data-ttu-id="80ab6-247">22002</span><span class="sxs-lookup"><span data-stu-id="80ab6-247">22002</span></span>  <br/> |

<span data-ttu-id="80ab6-248">A tabela a seguir lista os problemas de rede que a Microsoft recomenda monitoramento:</span><span class="sxs-lookup"><span data-stu-id="80ab6-248">The following table lists the network issues that Microsoft recommends monitoring:</span></span>


| <span data-ttu-id="80ab6-249">Nome do Monitor</span><span class="sxs-lookup"><span data-stu-id="80ab6-249">Monitor Name</span></span>  <br/>                                        | <span data-ttu-id="80ab6-250">Função de servidor de destino</span><span class="sxs-lookup"><span data-stu-id="80ab6-250">Target Server Role</span></span>  <br/> | <span data-ttu-id="80ab6-251">Expressão de ID do Evento de Sucesso</span><span class="sxs-lookup"><span data-stu-id="80ab6-251">Success Event ID expression</span></span>  <br/> | <span data-ttu-id="80ab6-252">Expressão de ID do Evento de Erro</span><span class="sxs-lookup"><span data-stu-id="80ab6-252">Error Event ID expression</span></span>  <br/> | <span data-ttu-id="80ab6-253">Exemplo de falha</span><span class="sxs-lookup"><span data-stu-id="80ab6-253">Failure example</span></span>  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| <span data-ttu-id="80ab6-254">Falha de conectividade do Servidor de Mediação para gateway</span><span class="sxs-lookup"><span data-stu-id="80ab6-254">Mediation Server to gateway connectivity failure</span></span>  <br/>    | <span data-ttu-id="80ab6-255">Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="80ab6-255">Mediation Server</span></span>  <br/>   | <span data-ttu-id="80ab6-256">25062</span><span class="sxs-lookup"><span data-stu-id="80ab6-256">25062</span></span>                              |                                  | <span data-ttu-id="80ab6-257">25002</span><span class="sxs-lookup"><span data-stu-id="80ab6-257">25002</span></span>  <br/>           |
| <span data-ttu-id="80ab6-258">Falha de conclusão de chamada do Servidor de Mediação para gateway</span><span class="sxs-lookup"><span data-stu-id="80ab6-258">Mediation Server to gateway call completion failure</span></span>  <br/> | <span data-ttu-id="80ab6-259">Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="80ab6-259">Mediation Server</span></span>  <br/>   | <span data-ttu-id="80ab6-260">25064</span><span class="sxs-lookup"><span data-stu-id="80ab6-260">25064</span></span>                              |                                  | <span data-ttu-id="80ab6-261">25002</span><span class="sxs-lookup"><span data-stu-id="80ab6-261">25002</span></span>  <br/>           |
| <span data-ttu-id="80ab6-262">Problemas críticos de rede</span><span class="sxs-lookup"><span data-stu-id="80ab6-262">Critical network problems</span></span>  <br/>                           | <span data-ttu-id="80ab6-263">Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="80ab6-263">Edge Server</span></span>  <br/>        | <span data-ttu-id="80ab6-264">14353</span><span class="sxs-lookup"><span data-stu-id="80ab6-264">14353</span></span>                              |                                  | <span data-ttu-id="80ab6-265">12288</span><span class="sxs-lookup"><span data-stu-id="80ab6-265">12288</span></span>  <br/>           |

<span data-ttu-id="80ab6-266">O seguinte lista os contadores de capacidade de chamada que devem ser monitorados.</span><span class="sxs-lookup"><span data-stu-id="80ab6-266">The following lists the call capacity counters that should be monitored.</span></span> <span data-ttu-id="80ab6-267">Esses números devem ter menos de 500 para a edição padrão do Cloud Connector; menos de 50 para a edição mínima do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="80ab6-267">These numbers should be less that 500 for Cloud Connector standard edition; less than 50 for Cloud Connector minimum edition.</span></span>

- <span data-ttu-id="80ab6-268">LS:MediationServer - Chamadas de entrada(_Total) \- Atual</span><span class="sxs-lookup"><span data-stu-id="80ab6-268">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="80ab6-269">LS:MediationServer - Chamadas de saída(_Total) \- Atual</span><span class="sxs-lookup"><span data-stu-id="80ab6-269">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="80ab6-270">LS:MediationServer - Chamadas de entrada(_Total) Chamadas de bypass de \- mídia ativas</span><span class="sxs-lookup"><span data-stu-id="80ab6-270">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span>

- <span data-ttu-id="80ab6-271">LS:MediationServer - Chamadas de saída(_Total) Chamadas de bypass de \- mídia ativas</span><span class="sxs-lookup"><span data-stu-id="80ab6-271">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span>

## <a name="see-also"></a><span data-ttu-id="80ab6-272">Confira também</span><span class="sxs-lookup"><span data-stu-id="80ab6-272">See also</span></span>

<span data-ttu-id="80ab6-273">Para obter mais informações sobre como trabalhar com OMS, consulte o seguinte:</span><span class="sxs-lookup"><span data-stu-id="80ab6-273">For more information about working with OMS, see the following:</span></span>

- [<span data-ttu-id="80ab6-274">Encontrar dados usando pesquisas de log no Log Analytics</span><span class="sxs-lookup"><span data-stu-id="80ab6-274">Find data using log searches in Log Analytics</span></span>](/azure/log-analytics/log-analytics-log-searches)

- [<span data-ttu-id="80ab6-275">Referência de idioma do Azure Log Analytics</span><span class="sxs-lookup"><span data-stu-id="80ab6-275">Azure Log Analytics Language Reference</span></span>](https://docs.loganalytics.io/docs/Language-Reference)

- [<span data-ttu-id="80ab6-276">Noções básicas sobre alertas no Log Analytics</span><span class="sxs-lookup"><span data-stu-id="80ab6-276">Understanding alerts in Log Analytics</span></span>](/azure/log-analytics/log-analytics-alerts)

- [<span data-ttu-id="80ab6-277">Conectar computadores Windows ao serviço de Análise de Log no Azure</span><span class="sxs-lookup"><span data-stu-id="80ab6-277">Connect Windows computers to the Log Analytics service in Azure</span></span>](/azure/log-analytics/log-analytics-windows-agents)