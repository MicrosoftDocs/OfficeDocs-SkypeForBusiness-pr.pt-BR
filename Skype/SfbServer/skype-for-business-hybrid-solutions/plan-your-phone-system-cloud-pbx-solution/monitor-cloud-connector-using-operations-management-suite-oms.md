---
title: Monitor Cloud Connector using Operations Management Suite (OMS).
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
description: Leia este tópico para aprender a monitorar a versão 2,1 do conector de nuvem e posterior usando o Microsoft Operations Management Suite (OMS).
ms.openlocfilehash: 1dcac3519624cef898622f915b08b24363453b84
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799621"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a><span data-ttu-id="b69f7-103">Monitor Cloud Connector using Operations Management Suite (OMS).</span><span class="sxs-lookup"><span data-stu-id="b69f7-103">Monitor Cloud Connector using Operations Management Suite (OMS)</span></span>

<span data-ttu-id="b69f7-104">Leia este tópico para aprender a monitorar a versão 2,1 do conector de nuvem e posterior usando o Microsoft Operations Management Suite (OMS).</span><span class="sxs-lookup"><span data-stu-id="b69f7-104">Read this topic to learn how to monitor your Cloud Connector version 2.1 and later deployment by using Microsoft Operations Management Suite (OMS).</span></span>

<span data-ttu-id="b69f7-105">Agora você pode monitorar a implantação do conector de nuvem versão 2,1 e posterior usando o Operations Management Suite (OMS), uma solução de gerenciamento de ti da nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b69f7-105">You can now monitor your Cloud Connector version 2.1 and later deployment by using Operations Management Suite (OMS), a Microsoft cloud IT management solution.</span></span> <span data-ttu-id="b69f7-106">A análise de logs do OMS permite que você monitore e analise a disponibilidade e o desempenho de recursos, incluindo máquinas físicas e virtuais.</span><span class="sxs-lookup"><span data-stu-id="b69f7-106">OMS Log Analytics enables you to monitor and analyze the availability and performance of resources including physical and virtual machines.</span></span> <span data-ttu-id="b69f7-107">Para obter mais informações sobre o OMS e a análise de logs, consulte [o que é o OMS (Operations Management Suite)?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview).</span><span class="sxs-lookup"><span data-stu-id="b69f7-107">For more information about OMS and Log Analytics, see [What is Operations Management Suite (OMS)?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview).</span></span>

<span data-ttu-id="b69f7-108">Este tópico inclui as seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="b69f7-108">This topic contains the following sections:</span></span>

- <span data-ttu-id="b69f7-109">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="b69f7-109">Prerequisites</span></span>

- <span data-ttu-id="b69f7-110">Configurar o conector de nuvem para usar o OMS</span><span class="sxs-lookup"><span data-stu-id="b69f7-110">Configure Cloud Connector to use OMS</span></span>

- <span data-ttu-id="b69f7-111">Configurar o OMS</span><span class="sxs-lookup"><span data-stu-id="b69f7-111">Configure OMS</span></span>

- <span data-ttu-id="b69f7-112">Analisar os alertas no repositório de análises de logs</span><span class="sxs-lookup"><span data-stu-id="b69f7-112">Analyze the alerts in your Log Analytics repository</span></span>

- <span data-ttu-id="b69f7-113">Conjunto de monitoramento recomendado</span><span class="sxs-lookup"><span data-stu-id="b69f7-113">Recommended monitoring set</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b69f7-114">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="b69f7-114">Prerequisites</span></span>

<span data-ttu-id="b69f7-115">Antes de usar o OMS para monitorar a implantação do conector de nuvem, será necessário o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b69f7-115">Before you can use OMS to monitor your Cloud Connector deployment, you will need the following:</span></span>

- <span data-ttu-id="b69f7-116">**Uma conta do Azure e um espaço de trabalho do OMS.**</span><span class="sxs-lookup"><span data-stu-id="b69f7-116">**An Azure account and an OMS workspace.**</span></span> <span data-ttu-id="b69f7-117">Se ainda não tiver uma conta do Azure, será necessário criar uma para usar a análise de logs do OMS.</span><span class="sxs-lookup"><span data-stu-id="b69f7-117">If you don't already have an Azure account, you will need to create one to use OMS Log Analytics.</span></span> <span data-ttu-id="b69f7-118">Para obter informações sobre como criar uma conta do Azure e configurar um espaço de trabalho do OMS, consulte [introdução a um espaço de trabalho de análise de logs](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).</span><span class="sxs-lookup"><span data-stu-id="b69f7-118">For information about how to create an Azure account and set up an OMS workspace, see [Get started with a Log Analytics workspace](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).</span></span>

- <span data-ttu-id="b69f7-119">**Cloud Connector versão 2,1 ou posterior**</span><span class="sxs-lookup"><span data-stu-id="b69f7-119">**Cloud Connector version 2.1 or later**</span></span>

- <span data-ttu-id="b69f7-120">**Análise de log a pesquisa de novo log** é necessária para o monitoramento do conector de nuvem.</span><span class="sxs-lookup"><span data-stu-id="b69f7-120">**Log Analytics new log search** is required for Cloud Connector monitoring.</span></span> <span data-ttu-id="b69f7-121">Para obter mais informações, consulte [atualizar o espaço de trabalho do Microsoft Azure log Analytics para a nova pesquisa de log](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade).</span><span class="sxs-lookup"><span data-stu-id="b69f7-121">For more information, see [Upgrade your Azure Log Analytics workspace to new log search](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade).</span></span>

## <a name="configure-cloud-connector-to-use-oms"></a><span data-ttu-id="b69f7-122">Configurar o conector de nuvem para usar o OMS</span><span class="sxs-lookup"><span data-stu-id="b69f7-122">Configure Cloud Connector to use OMS</span></span>

<span data-ttu-id="b69f7-123">Você precisará configurar seu ambiente local do conector de nuvem para usar o OMS.</span><span class="sxs-lookup"><span data-stu-id="b69f7-123">You'll need to configure your Cloud Connector on-premises environment to use OMS.</span></span> <span data-ttu-id="b69f7-124">Para fazer isso, você precisará da ID e da chave do espaço de trabalho do OMS, que pode ser encontrado usando o portal do OMS da\>seguinte maneira: configurações\> -fontes conectadas – Windows Servers:</span><span class="sxs-lookup"><span data-stu-id="b69f7-124">To do this, you will need your OMS workspace ID and key, which you can find by using the OMS portal as follows: Settings --\>Connected Sources --\> Windows Servers:</span></span>

![Captura de tela para OMS do conector da nuvem](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

<span data-ttu-id="b69f7-126">A maneira como você configura o conector de nuvem para usar o OMS depende do seu cenário:</span><span class="sxs-lookup"><span data-stu-id="b69f7-126">How you configure Cloud Connector to use OMS depends on your scenario:</span></span>

- <span data-ttu-id="b69f7-127">**Se você estiver instalando um novo dispositivo de conector de nuvem ou se quiser reimplantar um dispositivo**, siga estas etapas antes de executar o Install-CcAppliance:</span><span class="sxs-lookup"><span data-stu-id="b69f7-127">**If you are installing a new Cloud Connector appliance or you want to re-deploy an appliance**, follow these steps before you run Install-CcAppliance:</span></span>

1. <span data-ttu-id="b69f7-128">Na seção arquivo CloudConnector. ini [Common], defina o parâmetro OMSEnabled como true.</span><span class="sxs-lookup"><span data-stu-id="b69f7-128">In the CloudConnector.ini file [Common] section, set the OMSEnabled parameter to True.</span></span>

    <span data-ttu-id="b69f7-129">Toda vez que o conector da nuvem é implantado ou atualizado, ele tenta instalar o agente do OMS automaticamente nas VMs.</span><span class="sxs-lookup"><span data-stu-id="b69f7-129">Each time Cloud Connector is deployed or upgraded, it will try to install the OMS agent automatically onto the VMs.</span></span> <span data-ttu-id="b69f7-130">Habilite esse recurso para que o agente do OMS possa sobreviver à atualização automática do conector de nuvem.</span><span class="sxs-lookup"><span data-stu-id="b69f7-130">Enable this feature so the OMS agent can survive the Cloud Connector automatic update.</span></span>

2. <span data-ttu-id="b69f7-131">Para configurar a chave e a ID do OMS, execute Set-CcCredential-AccountType OMSWorkspace.</span><span class="sxs-lookup"><span data-stu-id="b69f7-131">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

- <span data-ttu-id="b69f7-132">**Se você estiver instalando um agente do OMS em um dispositivo de conexão de nuvem existente**, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="b69f7-132">**If you are installing an OMS agent onto an existing Cloud Connector appliance**, follow these steps:</span></span>

1. <span data-ttu-id="b69f7-133">Na seção arquivo CloudConnector. ini [Common], defina OMSEnabled = true.</span><span class="sxs-lookup"><span data-stu-id="b69f7-133">In the CloudConnector.ini file [Common] section, set OMSEnabled=true.</span></span> 

2. <span data-ttu-id="b69f7-134">Execute Import-CcConfiguration.</span><span class="sxs-lookup"><span data-stu-id="b69f7-134">Run Import-CcConfiguration.</span></span> 

3. <span data-ttu-id="b69f7-135">Execute install-CcOMSAgent.</span><span class="sxs-lookup"><span data-stu-id="b69f7-135">Run Install-CcOMSAgent.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="b69f7-136">Se a credencial OMSWorkspace nunca tiver sido definida, você será solicitado a fornecer uma credencial quando executar instalar-CcOMSAgent.</span><span class="sxs-lookup"><span data-stu-id="b69f7-136">If the OMSWorkspace credential has never been set, you are prompted for the credential when you run install-CcOMSAgent.</span></span> 

- <span data-ttu-id="b69f7-137">**Se você deseja atualizar a chave ou ID do espaço de trabalho do OMS em um aparelho de conector de nuvem que já instalou um agente do OMS:**</span><span class="sxs-lookup"><span data-stu-id="b69f7-137">**If you want to update the OMS workspace ID or key in a Cloud Connector appliance that has already installed an OMS agent:**</span></span>

1. <span data-ttu-id="b69f7-138">Para configurar a chave e a ID do OMS, execute Set-CcCredential-AccountType OMSWorkspace.</span><span class="sxs-lookup"><span data-stu-id="b69f7-138">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

2. <span data-ttu-id="b69f7-139">Para aplicar as atualizações, execute install-CcOMSAgent.</span><span class="sxs-lookup"><span data-stu-id="b69f7-139">To apply the updates, run Install-CcOMSAgent.</span></span> 

- <span data-ttu-id="b69f7-140">**Para todos os cenários, verifique se os agentes estão conectados da seguinte maneira:**</span><span class="sxs-lookup"><span data-stu-id="b69f7-140">**For all scenarios, verify that the agents are connected as follows:**</span></span>

    <span data-ttu-id="b69f7-141">No portal do OMS, vá para configurações-\> fontes conectadas\> – Windows Servers.</span><span class="sxs-lookup"><span data-stu-id="b69f7-141">In the OMS portal, go to Settings -\> Connected Sources -\> Windows Servers.</span></span> <span data-ttu-id="b69f7-142">Você verá uma lista de máquinas conectadas.</span><span class="sxs-lookup"><span data-stu-id="b69f7-142">You will see a list of connected machines.</span></span> 

## <a name="configure-oms"></a><span data-ttu-id="b69f7-143">Configurar o OMS</span><span class="sxs-lookup"><span data-stu-id="b69f7-143">Configure OMS</span></span>

<span data-ttu-id="b69f7-144">Em seguida, você precisará especificar a configuração do OMS usando o portal do OMS.</span><span class="sxs-lookup"><span data-stu-id="b69f7-144">Next, you will need to specify your OMS configuration by using the OMS portal.</span></span> <span data-ttu-id="b69f7-145">Especificamente, será necessário:</span><span class="sxs-lookup"><span data-stu-id="b69f7-145">Specifically, you will need to:</span></span>

- <span data-ttu-id="b69f7-146">Especifique informações sobre logs de eventos e contadores de desempenho.</span><span class="sxs-lookup"><span data-stu-id="b69f7-146">Specify information about event logs and performance counters.</span></span>

- <span data-ttu-id="b69f7-147">Criar alertas.</span><span class="sxs-lookup"><span data-stu-id="b69f7-147">Create alerts.</span></span> 

### <a name="specify-information-about-event-logs-and-performance-counters"></a><span data-ttu-id="b69f7-148">Especificar informações sobre logs de eventos e contadores de desempenho</span><span class="sxs-lookup"><span data-stu-id="b69f7-148">Specify information about event logs and performance counters</span></span>

<span data-ttu-id="b69f7-149">No portal do OMS, você deve especificar informações sobre os logs de eventos e os contadores de desempenho da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="b69f7-149">In the OMS portal, you must specify information about the event logs and performance counters as follows:</span></span>

1. <span data-ttu-id="b69f7-150">Vá para configurações-\>dados –\>logs de eventos do Windows e adicione logs de eventos para:</span><span class="sxs-lookup"><span data-stu-id="b69f7-150">Go to Settings-\>Data-\>Windows Event logs, and add event logs for:</span></span> 

   - <span data-ttu-id="b69f7-151">Servidor Lync</span><span class="sxs-lookup"><span data-stu-id="b69f7-151">Lync Server</span></span>

   - <span data-ttu-id="b69f7-152">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="b69f7-152">Application</span></span>

     > [!NOTE]
     > <span data-ttu-id="b69f7-153">Você deve inserir manualmente o Lync Server na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="b69f7-153">You must manually enter Lync Server in the text box.</span></span> <span data-ttu-id="b69f7-154">Ele não aparece como uma opção na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="b69f7-154">It does not appear as an option in the drop-down list.</span></span> 

     <span data-ttu-id="b69f7-155">Para obter mais informações, consulte [fontes de dados de log de eventos do Windows em análises de logs](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)</span><span class="sxs-lookup"><span data-stu-id="b69f7-155">For more information, see [Windows event log data sources in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)</span></span>

2. <span data-ttu-id="b69f7-156">Vá para configurações-\>dados-\> contadores de desempenho do Windows e adicionar contadores de desempenho para:</span><span class="sxs-lookup"><span data-stu-id="b69f7-156">Go to Settings-\>Data-\> Windows Performance Counters, and add performance counters for:</span></span> 

   - <span data-ttu-id="b69f7-157">**Contadores de nível do sistema operacional**.</span><span class="sxs-lookup"><span data-stu-id="b69f7-157">**OS level counters**.</span></span> <span data-ttu-id="b69f7-158">Você pode adicionar contadores de nível do sistema operacional, como uso do processador, uso da memória, uso da rede ou usar soluções existentes, como capacidade e desempenho, monitor de desempenho de rede sem adicionar contadores explicitamente.</span><span class="sxs-lookup"><span data-stu-id="b69f7-158">You can add OS level counters, such as processor usage, memory usage, network usage, or you can use existing solutions such as Capacity and Performance, Network Performance Monitor without adding counters explicitly.</span></span> <span data-ttu-id="b69f7-159">Não importa como você decida monitorá-los, a Microsoft recomenda que você monitore esses contadores do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="b69f7-159">No matter how you decide to monitor them, Microsoft recommends that you monitor these OS counters.</span></span>

   - <span data-ttu-id="b69f7-160">**Contadores do Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="b69f7-160">**Skype for Business counters**.</span></span> <span data-ttu-id="b69f7-161">Há vários contadores fornecidos pelo Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="b69f7-161">There are numerous counters provided by Skype for Business.</span></span> <span data-ttu-id="b69f7-162">Você pode encontrar esses contadores fazendo logon em qualquer servidor de mediação e abrindo o monitor de desempenho.</span><span class="sxs-lookup"><span data-stu-id="b69f7-162">You can find these counters by logging on to any Mediation Server and opening the Performance Monitor.</span></span> <span data-ttu-id="b69f7-163">Estes contadores começam com "LS:".</span><span class="sxs-lookup"><span data-stu-id="b69f7-163">These counters start with "LS:".</span></span> <span data-ttu-id="b69f7-164">A Microsoft recomenda que você comece com os seguintes contadores de capacidade no mínimo e adicione outros que sejam de interesse:</span><span class="sxs-lookup"><span data-stu-id="b69f7-164">Microsoft recommends that you start with the following capacity counters at a minimum, and add others that are of interest:</span></span>

     <span data-ttu-id="b69f7-165">Total de chamadas ativas:</span><span class="sxs-lookup"><span data-stu-id="b69f7-165">Total active calls:</span></span>

   - <span data-ttu-id="b69f7-166">LS: MediationServer-chamadas de entrada (_Total)\- atuais</span><span class="sxs-lookup"><span data-stu-id="b69f7-166">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

   - <span data-ttu-id="b69f7-167">LS: MediationServer-chamadas de saída (_Total\- ) atuais</span><span class="sxs-lookup"><span data-stu-id="b69f7-167">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

     <span data-ttu-id="b69f7-168">Total de chamadas bypass de mídia ativas:</span><span class="sxs-lookup"><span data-stu-id="b69f7-168">Total active media bypass calls:</span></span>

   - <span data-ttu-id="b69f7-169">LS: MediationServer-chamadas de chamadas de entrada do\- active media (_Total)</span><span class="sxs-lookup"><span data-stu-id="b69f7-169">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span> 

   - <span data-ttu-id="b69f7-170">LS: MediationServer (_Total)\- chamadas de bypass de mídia ativas</span><span class="sxs-lookup"><span data-stu-id="b69f7-170">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span> 

     > [!NOTE]
     > <span data-ttu-id="b69f7-171">Você deve inserir manualmente os contadores de desempenho na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="b69f7-171">You must manually enter the performance counters in the text box.</span></span> <span data-ttu-id="b69f7-172">Elas não aparecem como opções na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="b69f7-172">They do not appear as options in the drop-down list.</span></span> 

     <span data-ttu-id="b69f7-173">Para obter mais informações, consulte [fontes de dados de desempenho do Windows e Linux em análises de logs](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)</span><span class="sxs-lookup"><span data-stu-id="b69f7-173">For more information, see [Windows and Linux performance data sources in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)</span></span>

### <a name="create-alerts"></a><span data-ttu-id="b69f7-174">Criar alertas</span><span class="sxs-lookup"><span data-stu-id="b69f7-174">Create alerts</span></span>

<span data-ttu-id="b69f7-175">Há dois tipos de alertas no OMS: número de alertas de resultados e alertas de medição métrica.</span><span class="sxs-lookup"><span data-stu-id="b69f7-175">There are two types of alerts in OMS: Number of results alerts and Metric measurement alerts.</span></span> <span data-ttu-id="b69f7-176">Para obter mais informações sobre a criação de alertas, consulte [trabalhando com regras de alerta na análise de logs](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).</span><span class="sxs-lookup"><span data-stu-id="b69f7-176">For more information about creating alerts, see [Working with alert rules in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).</span></span>

<span data-ttu-id="b69f7-177">Você deve considerar o seguinte ao criar alertas:</span><span class="sxs-lookup"><span data-stu-id="b69f7-177">You should consider the following when creating alerts:</span></span>

- <span data-ttu-id="b69f7-178">Verifique se o alerta é um alerta de número de resultados, que é a seleção padrão.</span><span class="sxs-lookup"><span data-stu-id="b69f7-178">Make sure the alert is a Number-of-results alert, which is the default selection.</span></span> 

- <span data-ttu-id="b69f7-179">As consultas de demonstração exigem que "número de resultados" seja definido como "maior que 0".</span><span class="sxs-lookup"><span data-stu-id="b69f7-179">The demo queries require that "Number of results" is set to "Greater than 0".</span></span> 

- <span data-ttu-id="b69f7-180">É recomendável que você defina a frequência da janela de tempo e do alerta como 5 minutos.</span><span class="sxs-lookup"><span data-stu-id="b69f7-180">It is recommended that you set both Time window and Alert frequency to 5 minutes.</span></span> 

- <span data-ttu-id="b69f7-181">É recomendável que você não habilite "suprimir alertas" para alertas de demonstração.</span><span class="sxs-lookup"><span data-stu-id="b69f7-181">It is recommended that you do not enable "Suppress alerts" for demo alerts.</span></span> 

- <span data-ttu-id="b69f7-182">Para cenários de alerta típicos, a Microsoft recomenda a criação de um par de alertas: um alerta de erro e um alerta de redefinição.</span><span class="sxs-lookup"><span data-stu-id="b69f7-182">For typical alert scenarios, Microsoft recommends creating a pair of alerts: one error alert and one reset alert.</span></span> <span data-ttu-id="b69f7-183">Para o alerta de erro, selecione nível de gravidade crítico; para o alerta de redefinição, selecione nível de gravidade informativo.</span><span class="sxs-lookup"><span data-stu-id="b69f7-183">For the error alert, select severity level Critical; for the reset alert, select severity level Informational .</span></span>

<span data-ttu-id="b69f7-184">As seções a seguir descrevem como criar alertas de exemplo.</span><span class="sxs-lookup"><span data-stu-id="b69f7-184">The following sections describe how to create sample alerts.</span></span>

 <span data-ttu-id="b69f7-185">**Criar um par de alertas: "RTCMEDSRV não está em execução nos servidores de mediação" e "RTCMEDSRV está em execução nos servidores de mediação"**</span><span class="sxs-lookup"><span data-stu-id="b69f7-185">**Create an alert pair: "RTCMEDSRV is NOT running in Mediation Servers" and "RTCMEDSRV is back in running in Mediation Servers"**</span></span>

<span data-ttu-id="b69f7-186">Para criar este par de alertas:</span><span class="sxs-lookup"><span data-stu-id="b69f7-186">To create this alert pair:</span></span>

- <span data-ttu-id="b69f7-187">A consulta do alerta de erro é:</span><span class="sxs-lookup"><span data-stu-id="b69f7-187">The query for the error alert is:</span></span>

  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    <span data-ttu-id="b69f7-188">A consulta usa o filtro do computador *onde o computador contém "MediationServer"* .</span><span class="sxs-lookup"><span data-stu-id="b69f7-188">The query uses the computer filter  *where Computer contains "MediationServer"*  .</span></span> <span data-ttu-id="b69f7-189">O filtro seleciona apenas o computador cujo nome contém a cadeia de caracteres "MediationServer".</span><span class="sxs-lookup"><span data-stu-id="b69f7-189">The filter selects only the computer whose name contains the string "MediationServer".</span></span>

     <span data-ttu-id="b69f7-190">Você substituiria o filtro pelo seu próprio filtro de computador ou simplesmente o removerá.</span><span class="sxs-lookup"><span data-stu-id="b69f7-190">You would replace the filter with your own computer filter or simply remove it.</span></span> <span data-ttu-id="b69f7-191">Você pode criar filtros de cadeia de caracteres complexas sem expressões regulares.</span><span class="sxs-lookup"><span data-stu-id="b69f7-191">You can create complex string filters without regular expressions.</span></span> <span data-ttu-id="b69f7-192">Para obter mais informações, consulte [operadores de cadeia de caracteres](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span><span class="sxs-lookup"><span data-stu-id="b69f7-192">For more information, see [String operators](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span></span> <span data-ttu-id="b69f7-193">Você também pode optar por usar expressões regulares.</span><span class="sxs-lookup"><span data-stu-id="b69f7-193">You can also choose to use regular expressions.</span></span> <span data-ttu-id="b69f7-194">Além disso, você pode criar um grupo de computador salvando uma consulta de pesquisa e usando esse grupo como filtro do computador na sua consulta de alerta.</span><span class="sxs-lookup"><span data-stu-id="b69f7-194">Moreover, you can create a computer group by saving a search query and using that group as your computer filter in your alert query.</span></span> <span data-ttu-id="b69f7-195">Para obter mais informações, consulte [grupos de computadores nas pesquisas de log de análise de logs](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups).</span><span class="sxs-lookup"><span data-stu-id="b69f7-195">For more information, see [Computer groups in Log Analytics log searches](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups).</span></span>

    <span data-ttu-id="b69f7-196">Para cada computador, a consulta de erro obterá o último log de eventos para o início do serviço RTCMEDSRV e o término do serviço.</span><span class="sxs-lookup"><span data-stu-id="b69f7-196">For each computer, the error query will get the last event log for both the RTCMEDSRV service start and service stop.</span></span> <span data-ttu-id="b69f7-197">Será retornado um log se o último evento for o evento de parada do serviço; será retornado nada se o último evento for o evento de início do serviço.</span><span class="sxs-lookup"><span data-stu-id="b69f7-197">It will return one log if the last event is the service stop event; it will return nothing if the last event is the service start event.</span></span> <span data-ttu-id="b69f7-198">Em resumo, a consulta retornaria uma lista de servidores cujo RTCMEDSRV está parado na janela de tempo.</span><span class="sxs-lookup"><span data-stu-id="b69f7-198">In short, the query would return a list of servers whose RTCMEDSRV is stopped in the time window.</span></span> 

- <span data-ttu-id="b69f7-199">A consulta para o alerta de redefinição é:</span><span class="sxs-lookup"><span data-stu-id="b69f7-199">The query for the reset alert is:</span></span>

  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    <span data-ttu-id="b69f7-200">A consulta redefinir faz exatamente a coisa oposta da consulta de erro.</span><span class="sxs-lookup"><span data-stu-id="b69f7-200">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="b69f7-201">Para cada computador, ele retornará um se o último evento for o evento de início do serviço; Ele não retornará nada se o último evento for o evento Stop do serviço.</span><span class="sxs-lookup"><span data-stu-id="b69f7-201">For each computer, it will return one if the last event is the service start event; it will return nothing if the last event is the service stop event.</span></span>

  <span data-ttu-id="b69f7-202">**Criar um par de alertas: "muitas chamadas simultâneas nos servidores de mediação" e "chamadas simultâneas retornam à carga normal"**</span><span class="sxs-lookup"><span data-stu-id="b69f7-202">**Create an alert pair: " Too many concurrent calls in Mediation Servers" and "Concurrent calls fall back to normal load"**</span></span>

<span data-ttu-id="b69f7-203">Para criar este alerta:</span><span class="sxs-lookup"><span data-stu-id="b69f7-203">To create this alert:</span></span>

- <span data-ttu-id="b69f7-204">A consulta do alerta de erro é:</span><span class="sxs-lookup"><span data-stu-id="b69f7-204">The query for the error alert is:</span></span>

  ```
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    <span data-ttu-id="b69f7-205">Para cada computador, a consulta obterá os últimos contadores de chamadas de entrada e de saída e somará esses dois valores.</span><span class="sxs-lookup"><span data-stu-id="b69f7-205">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="b69f7-206">Será retornado um log se o valor da soma exceder 500; Ele não retornará nada se isso não acontecer.</span><span class="sxs-lookup"><span data-stu-id="b69f7-206">It will return one log if the sum value exceeds 500; it will return nothing if it doesn't.</span></span> <span data-ttu-id="b69f7-207">Em resumo, a consulta retornaria uma lista de servidores cujas chamadas simultâneas são muito diferentes na janela de tempo.</span><span class="sxs-lookup"><span data-stu-id="b69f7-207">In short, the query would return a list of servers whose concurrent calls are too many in the time window.</span></span>

- <span data-ttu-id="b69f7-208">A consulta para o alerta de redefinição é:</span><span class="sxs-lookup"><span data-stu-id="b69f7-208">The query for the reset alert is:</span></span>

  ```
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    <span data-ttu-id="b69f7-209">A consulta redefinir faz exatamente a coisa oposta da consulta de erro.</span><span class="sxs-lookup"><span data-stu-id="b69f7-209">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="b69f7-210">Para cada computador, a consulta obterá os últimos contadores de chamadas de entrada e de saída e somará esses dois valores.</span><span class="sxs-lookup"><span data-stu-id="b69f7-210">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="b69f7-211">Ele retornará um log se o valor soma for menor que 500; Isso não retornará nada do contrário.</span><span class="sxs-lookup"><span data-stu-id="b69f7-211">It will return one log if the sum value is less than 500; it will return nothing otherwise.</span></span>

  <span data-ttu-id="b69f7-212">**Criar um alerta: alerta "uso \> da CPU 90 ou RTCMEDIARELAY interrompido nos servidores"**</span><span class="sxs-lookup"><span data-stu-id="b69f7-212">**Create an alert: "CPU usage \> 90 or RTCMEDIARELAY stopped in Servers" alert**</span></span>

<span data-ttu-id="b69f7-213">Para criar esse alerta, a consulta é:</span><span class="sxs-lookup"><span data-stu-id="b69f7-213">To create this alert, the query is:</span></span>

```
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

<span data-ttu-id="b69f7-214">A consulta receberá todo o contador de uso do processador e evento de parada do serviço de todos os computadores e retornará um log se o uso do processador exceder 90% ou serviço for interrompido.</span><span class="sxs-lookup"><span data-stu-id="b69f7-214">The query will get all processor usage counter and service stop event from all computers and return one log if either processor usage exceeds 90% or service is ever stopped.</span></span> 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a><span data-ttu-id="b69f7-215">Analisar os alertas no repositório de análises de logs</span><span class="sxs-lookup"><span data-stu-id="b69f7-215">Analyze the alerts in your Log Analytics repository</span></span>

<span data-ttu-id="b69f7-216">Para analisar os alertas no repositório, use a solução de gerenciamento de alertas.</span><span class="sxs-lookup"><span data-stu-id="b69f7-216">To analyze the alerts in your repository, use the Alert Management solution.</span></span> <span data-ttu-id="b69f7-217">Para obter mais informações, consulte [solução de gerenciamento de alertas no OMS (Operations Management Suite)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)</span><span class="sxs-lookup"><span data-stu-id="b69f7-217">For more information, see [Alert Management solution in Operations Management Suite (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)</span></span>

## <a name="recommended-minimal-monitoring-set"></a><span data-ttu-id="b69f7-218">Conjunto de monitoramento mínimo recomendado</span><span class="sxs-lookup"><span data-stu-id="b69f7-218">Recommended minimal monitoring set</span></span>

<span data-ttu-id="b69f7-219">Para identificar problemas com os logs de eventos e os contadores de desempenho:</span><span class="sxs-lookup"><span data-stu-id="b69f7-219">To identify issues with event logs and performance counters:</span></span> 

- <span data-ttu-id="b69f7-220">**Logs de eventos.**</span><span class="sxs-lookup"><span data-stu-id="b69f7-220">**Event logs.**</span></span> <span data-ttu-id="b69f7-221">Em caso de problemas, deve haver um par de eventos, com um conjunto de eventos para indicar que algo está errado, enquanto o outro indica que tudo está bem.</span><span class="sxs-lookup"><span data-stu-id="b69f7-221">For any issue, there should be an events pair, with one set of events to indicate something is wrong, while the other indicates that everything is well.</span></span> <span data-ttu-id="b69f7-222">Para qualquer período de tempo específico, é o último evento registrado que indicará se algo está inadequado para esse período de tempo.</span><span class="sxs-lookup"><span data-stu-id="b69f7-222">For any given time period, it is the last event recorded that will indicate whether something is amiss for that time period.</span></span>

- <span data-ttu-id="b69f7-223">**Contadores de desempenho.**</span><span class="sxs-lookup"><span data-stu-id="b69f7-223">**Performance Counters.**</span></span> <span data-ttu-id="b69f7-224">Deve haver um limiar para os contadores monitorados.</span><span class="sxs-lookup"><span data-stu-id="b69f7-224">There should be a threshold for the monitored counters.</span></span>

<span data-ttu-id="b69f7-225">A tabela a seguir lista os serviços que a Microsoft recomenda monitorar ao listar as IDs de evento stop e start:</span><span class="sxs-lookup"><span data-stu-id="b69f7-225">The following table lists the services that Microsoft recommends monitoring by listing the stop and start event IDs:</span></span>

|<span data-ttu-id="b69f7-226">Nome do serviço</span><span class="sxs-lookup"><span data-stu-id="b69f7-226">Service Name</span></span>  <br/> |<span data-ttu-id="b69f7-227">Função de servidor de destino</span><span class="sxs-lookup"><span data-stu-id="b69f7-227">Target Server Role</span></span>  <br/> |<span data-ttu-id="b69f7-228">Parar ID do evento</span><span class="sxs-lookup"><span data-stu-id="b69f7-228">Stop Event ID</span></span>  <br/> |<span data-ttu-id="b69f7-229">Iniciar ID do evento</span><span class="sxs-lookup"><span data-stu-id="b69f7-229">Start Event ID</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b69f7-230">RTCMEDSRV</span><span class="sxs-lookup"><span data-stu-id="b69f7-230">RTCMEDSRV</span></span>  <br/> |<span data-ttu-id="b69f7-231">Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="b69f7-231">Mediation Server</span></span>  <br/> |<span data-ttu-id="b69f7-232">25003</span><span class="sxs-lookup"><span data-stu-id="b69f7-232">25003</span></span>  <br/> |<span data-ttu-id="b69f7-233">25002</span><span class="sxs-lookup"><span data-stu-id="b69f7-233">25002</span></span>  <br/> |
|<span data-ttu-id="b69f7-234">RTCSRV</span><span class="sxs-lookup"><span data-stu-id="b69f7-234">RTCSRV</span></span>  <br/> |<span data-ttu-id="b69f7-235">Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="b69f7-235">Edge Server</span></span>  <br/> |<span data-ttu-id="b69f7-236">12289</span><span class="sxs-lookup"><span data-stu-id="b69f7-236">12289</span></span>  <br/> |<span data-ttu-id="b69f7-237">12288</span><span class="sxs-lookup"><span data-stu-id="b69f7-237">12288</span></span>  <br/> |
|<span data-ttu-id="b69f7-238">RTCMRAUTH</span><span class="sxs-lookup"><span data-stu-id="b69f7-238">RTCMRAUTH</span></span>  <br/> |<span data-ttu-id="b69f7-239">Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="b69f7-239">Edge Server</span></span>  <br/> |<span data-ttu-id="b69f7-240">19003</span><span class="sxs-lookup"><span data-stu-id="b69f7-240">19003</span></span>  <br/> |<span data-ttu-id="b69f7-241">19002</span><span class="sxs-lookup"><span data-stu-id="b69f7-241">19002</span></span>  <br/> |
|<span data-ttu-id="b69f7-242">RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="b69f7-242">RTCMEDIARELAY</span></span>  <br/> |<span data-ttu-id="b69f7-243">Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="b69f7-243">Edge Server</span></span>  <br/> |<span data-ttu-id="b69f7-244">22003</span><span class="sxs-lookup"><span data-stu-id="b69f7-244">22003</span></span>  <br/> |<span data-ttu-id="b69f7-245">22002</span><span class="sxs-lookup"><span data-stu-id="b69f7-245">22002</span></span>  <br/> |

<span data-ttu-id="b69f7-246">A tabela a seguir lista os problemas de rede que a Microsoft recomenda monitorar:</span><span class="sxs-lookup"><span data-stu-id="b69f7-246">The following table lists the network issues that Microsoft recommends monitoring:</span></span>


| <span data-ttu-id="b69f7-247">Nome do monitor</span><span class="sxs-lookup"><span data-stu-id="b69f7-247">Monitor Name</span></span>  <br/>                                        | <span data-ttu-id="b69f7-248">Função de servidor de destino</span><span class="sxs-lookup"><span data-stu-id="b69f7-248">Target Server Role</span></span>  <br/> | <span data-ttu-id="b69f7-249">Expressão de ID do evento de sucesso</span><span class="sxs-lookup"><span data-stu-id="b69f7-249">Success Event ID expression</span></span>  <br/> | <span data-ttu-id="b69f7-250">Expressão de ID de evento de erro</span><span class="sxs-lookup"><span data-stu-id="b69f7-250">Error Event ID expression</span></span>  <br/> | <span data-ttu-id="b69f7-251">Exemplo de falha</span><span class="sxs-lookup"><span data-stu-id="b69f7-251">Failure example</span></span>  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| <span data-ttu-id="b69f7-252">Falha no servidor de mediação para conectividade de gateway</span><span class="sxs-lookup"><span data-stu-id="b69f7-252">Mediation Server to gateway connectivity failure</span></span>  <br/>    | <span data-ttu-id="b69f7-253">Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="b69f7-253">Mediation Server</span></span>  <br/>   | <span data-ttu-id="b69f7-254">25062</span><span class="sxs-lookup"><span data-stu-id="b69f7-254">25062</span></span>                              |                                  | <span data-ttu-id="b69f7-255">25002</span><span class="sxs-lookup"><span data-stu-id="b69f7-255">25002</span></span>  <br/>           |
| <span data-ttu-id="b69f7-256">Falha na conclusão da chamada do servidor de mediação para gateway</span><span class="sxs-lookup"><span data-stu-id="b69f7-256">Mediation Server to gateway call completion failure</span></span>  <br/> | <span data-ttu-id="b69f7-257">Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="b69f7-257">Mediation Server</span></span>  <br/>   | <span data-ttu-id="b69f7-258">25064</span><span class="sxs-lookup"><span data-stu-id="b69f7-258">25064</span></span>                              |                                  | <span data-ttu-id="b69f7-259">25002</span><span class="sxs-lookup"><span data-stu-id="b69f7-259">25002</span></span>  <br/>           |
| <span data-ttu-id="b69f7-260">Problemas críticos na rede</span><span class="sxs-lookup"><span data-stu-id="b69f7-260">Critical network problems</span></span>  <br/>                           | <span data-ttu-id="b69f7-261">Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="b69f7-261">Edge Server</span></span>  <br/>        | <span data-ttu-id="b69f7-262">14353</span><span class="sxs-lookup"><span data-stu-id="b69f7-262">14353</span></span>                              |                                  | <span data-ttu-id="b69f7-263">12288</span><span class="sxs-lookup"><span data-stu-id="b69f7-263">12288</span></span>  <br/>           |

<span data-ttu-id="b69f7-264">O seguinte lista os contadores de capacidade de chamada que devem ser monitorados.</span><span class="sxs-lookup"><span data-stu-id="b69f7-264">The following lists the call capacity counters that should be monitored.</span></span> <span data-ttu-id="b69f7-265">Esses números devem ser inferiores ao 500 para a edição padrão do conector de nuvem; menor que 50 para a edição mínima do conector de nuvem.</span><span class="sxs-lookup"><span data-stu-id="b69f7-265">These numbers should be less that 500 for Cloud Connector standard edition; less than 50 for Cloud Connector minimum edition.</span></span>

- <span data-ttu-id="b69f7-266">LS: MediationServer-chamadas de entrada (_Total)\- atuais</span><span class="sxs-lookup"><span data-stu-id="b69f7-266">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="b69f7-267">LS: MediationServer-chamadas de saída (_Total\- ) atuais</span><span class="sxs-lookup"><span data-stu-id="b69f7-267">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="b69f7-268">LS: MediationServer-chamadas de chamadas de entrada do\- active media (_Total)</span><span class="sxs-lookup"><span data-stu-id="b69f7-268">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span>

- <span data-ttu-id="b69f7-269">LS: MediationServer (_Total)\- chamadas de bypass de mídia ativas</span><span class="sxs-lookup"><span data-stu-id="b69f7-269">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span>

## <a name="see-also"></a><span data-ttu-id="b69f7-270">Confira também</span><span class="sxs-lookup"><span data-stu-id="b69f7-270">See also</span></span>

<span data-ttu-id="b69f7-271">Para obter mais informações sobre como trabalhar com o OMS, consulte o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b69f7-271">For more information about working with OMS, see the following:</span></span>

- [<span data-ttu-id="b69f7-272">Localizar dados usando pesquisas de log na análise de logs</span><span class="sxs-lookup"><span data-stu-id="b69f7-272">Find data using log searches in Log Analytics</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-searches)

- [<span data-ttu-id="b69f7-273">Referência da linguagem do Azure log Analytics</span><span class="sxs-lookup"><span data-stu-id="b69f7-273">Azure Log Analytics Language Reference</span></span>](https://docs.loganalytics.io/docs/Language-Reference)

- [<span data-ttu-id="b69f7-274">Noções básicas sobre alertas em análises de logs</span><span class="sxs-lookup"><span data-stu-id="b69f7-274">Understanding alerts in Log Analytics</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts)

- [<span data-ttu-id="b69f7-275">Conectar computadores Windows ao serviço analítico de logs no Azure</span><span class="sxs-lookup"><span data-stu-id="b69f7-275">Connect Windows computers to the Log Analytics service in Azure</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)


