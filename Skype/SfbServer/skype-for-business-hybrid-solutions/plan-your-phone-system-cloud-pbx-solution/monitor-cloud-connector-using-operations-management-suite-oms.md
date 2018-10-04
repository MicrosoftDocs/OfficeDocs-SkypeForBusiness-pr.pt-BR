---
title: Monitorar o conector de nuvem usando o pacote de gerenciamento de operações (OMS)
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: Leia este tópico para saber como monitorar sua versão do conector de nuvem 2.1 e a implantação posterior usando o pacote de gerenciamento de operações da Microsoft (OMS).
ms.openlocfilehash: 19946c0d7701d2fd31c1b41cae58e08cfdf4c52d
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372185"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a><span data-ttu-id="7e988-103">Monitorar o conector de nuvem usando o pacote de gerenciamento de operações (OMS)</span><span class="sxs-lookup"><span data-stu-id="7e988-103">Monitor Cloud Connector using Operations Management Suite (OMS)</span></span>

<span data-ttu-id="7e988-104">Leia este tópico para saber como monitorar sua versão do conector de nuvem 2.1 e a implantação posterior usando o pacote de gerenciamento de operações da Microsoft (OMS).</span><span class="sxs-lookup"><span data-stu-id="7e988-104">Read this topic to learn how to monitor your Cloud Connector version 2.1 and later deployment by using Microsoft Operations Management Suite (OMS).</span></span>

<span data-ttu-id="7e988-105">Agora você pode monitorar sua versão do conector de nuvem 2.1 e a implantação posterior usando o pacote de gerenciamento de operações (OMS), uma solução de gerenciamento de TI de nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7e988-105">You can now monitor your Cloud Connector version 2.1 and later deployment by using Operations Management Suite (OMS), a Microsoft cloud IT management solution.</span></span> <span data-ttu-id="7e988-106">Análise de Log OMS permite monitorar e analisar a disponibilidade e o desempenho dos recursos, incluindo físicos e máquinas virtuais.</span><span class="sxs-lookup"><span data-stu-id="7e988-106">OMS Log Analytics enables you to monitor and analyze the availability and performance of resources including physical and virtual machines.</span></span> <span data-ttu-id="7e988-107">Para obter mais informações sobre OMS e análise de Log, consulte [o que é o pacote de gerenciamento de operações (OMS)?](https://docs.microsoft.com/en-us/azure/operations-management-suite/operations-management-suite-overview).</span><span class="sxs-lookup"><span data-stu-id="7e988-107">For more information about OMS and Log Analytics, see [What is Operations Management Suite (OMS)?](https://docs.microsoft.com/en-us/azure/operations-management-suite/operations-management-suite-overview).</span></span>

<span data-ttu-id="7e988-108">Este tópico inclui as seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="7e988-108">This topic contains the following sections:</span></span>

- <span data-ttu-id="7e988-109">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="7e988-109">Prerequisites</span></span>

- <span data-ttu-id="7e988-110">Configure o conector de nuvem para usar o OMS</span><span class="sxs-lookup"><span data-stu-id="7e988-110">Configure Cloud Connector to use OMS</span></span>

- <span data-ttu-id="7e988-111">Configurar OMS</span><span class="sxs-lookup"><span data-stu-id="7e988-111">Configure OMS</span></span>

- <span data-ttu-id="7e988-112">Analisar os alertas no seu repositório de análise de Log</span><span class="sxs-lookup"><span data-stu-id="7e988-112">Analyze the alerts in your Log Analytics repository</span></span>

- <span data-ttu-id="7e988-113">Conjunto de monitoramento recomendado</span><span class="sxs-lookup"><span data-stu-id="7e988-113">Recommended monitoring set</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7e988-114">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="7e988-114">Prerequisites</span></span>

<span data-ttu-id="7e988-115">Antes de poder usar OMS para monitorar sua implantação do conector de nuvem, você precisará do seguinte:</span><span class="sxs-lookup"><span data-stu-id="7e988-115">Before you can use OMS to monitor your Cloud Connector deployment, you will need the following:</span></span>

- <span data-ttu-id="7e988-116">**Uma conta do Windows Azure e um espaço de trabalho do OMS.**</span><span class="sxs-lookup"><span data-stu-id="7e988-116">**An Azure account and an OMS workspace.**</span></span> <span data-ttu-id="7e988-117">Se você ainda não tiver uma conta do Windows Azure, você precisará criar um para usar a análise de Log OMS.</span><span class="sxs-lookup"><span data-stu-id="7e988-117">If you don't already have an Azure account, you will need to create one to use OMS Log Analytics.</span></span> <span data-ttu-id="7e988-118">Para obter informações sobre como criar uma conta do Windows Azure e configurar um espaço de trabalho do OMS, consulte [Introdução a um espaço de trabalho de análise de Log](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-get-started).</span><span class="sxs-lookup"><span data-stu-id="7e988-118">For information about how to create an Azure account and set up an OMS workspace, see [Get started with a Log Analytics workspace](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-get-started).</span></span>

- <span data-ttu-id="7e988-119">**Conector de nuvem versão 2.1 ou posterior**</span><span class="sxs-lookup"><span data-stu-id="7e988-119">**Cloud Connector version 2.1 or later**</span></span>

- <span data-ttu-id="7e988-120">**Nova pesquisa de log de análise de log** é necessária para monitoramento de conector de nuvem.</span><span class="sxs-lookup"><span data-stu-id="7e988-120">**Log Analytics new log search** is required for Cloud Connector monitoring.</span></span> <span data-ttu-id="7e988-121">Para obter mais informações, consulte [atualizar seu espaço de trabalho de análise de Log do Windows Azure para a nova pesquisa de log](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-log-search-upgrade).</span><span class="sxs-lookup"><span data-stu-id="7e988-121">For more information, see [Upgrade your Azure Log Analytics workspace to new log search](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-log-search-upgrade).</span></span>

## <a name="configure-cloud-connector-to-use-oms"></a><span data-ttu-id="7e988-122">Configure o conector de nuvem para usar o OMS</span><span class="sxs-lookup"><span data-stu-id="7e988-122">Configure Cloud Connector to use OMS</span></span>

<span data-ttu-id="7e988-123">Você precisará configurar seu ambiente do local do conector de nuvem para usar o OMS.</span><span class="sxs-lookup"><span data-stu-id="7e988-123">You'll need to configure your Cloud Connector on-premises environment to use OMS.</span></span> <span data-ttu-id="7e988-124">Para fazer isso, você precisará sua ID de espaço de trabalho do OMS e a chave, que pode ser encontrado usando o portal OMS da seguinte maneira: configurações--\>fontes conectado –\> servidores Windows:</span><span class="sxs-lookup"><span data-stu-id="7e988-124">To do this, you will need your OMS workspace ID and key, which you can find by using the OMS portal as follows: Settings --\>Connected Sources --\> Windows Servers:</span></span>

![Captura de tela do Cloud Connector OMS](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

<span data-ttu-id="7e988-126">Como configurar o conector de nuvem para usar o OMS depende do seu cenário:</span><span class="sxs-lookup"><span data-stu-id="7e988-126">How you configure Cloud Connector to use OMS depends on your scenario:</span></span>

- <span data-ttu-id="7e988-127">**Se você estiver instalando um novo dispositivo de conector de nuvem ou você deseja implantar um aparelho de novamente**, siga estas etapas antes de executar Install-CcAppliance:</span><span class="sxs-lookup"><span data-stu-id="7e988-127">**If you are installing a new Cloud Connector appliance or you want to re-deploy an appliance**, follow these steps before you run Install-CcAppliance:</span></span>

1. <span data-ttu-id="7e988-128">No arquivo CloudConnector.ini seção [comuns], defina o parâmetro OMSEnabled como True.</span><span class="sxs-lookup"><span data-stu-id="7e988-128">In the CloudConnector.ini file [Common] section, set the OMSEnabled parameter to True.</span></span>

    <span data-ttu-id="7e988-129">Sempre que o conector de nuvem é implantado ou atualizado, ele tentará instalar o agente OMS automaticamente nas VMs.</span><span class="sxs-lookup"><span data-stu-id="7e988-129">Each time Cloud Connector is deployed or upgraded, it will try to install the OMS agent automatically onto the VMs.</span></span> <span data-ttu-id="7e988-130">Habilite esse recurso para que o agente OMS pode sobreviver a atualização automática do conector de nuvem.</span><span class="sxs-lookup"><span data-stu-id="7e988-130">Enable this feature so the OMS agent can survive the Cloud Connector automatic update.</span></span>

2. <span data-ttu-id="7e988-131">Para configurar o OMS ID e a chave, execute Set-CcCredential - AccountType OMSWorkspace.</span><span class="sxs-lookup"><span data-stu-id="7e988-131">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

- <span data-ttu-id="7e988-132">**Se você estiver instalando um operador OMS em um aparelho de conector de nuvem existente**, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="7e988-132">**If you are installing an OMS agent onto an existing Cloud Connector appliance**, follow these steps:</span></span>

1. <span data-ttu-id="7e988-133">No arquivo CloudConnector.ini seção [comuns], defina OMSEnabled = true.</span><span class="sxs-lookup"><span data-stu-id="7e988-133">In the CloudConnector.ini file [Common] section, set OMSEnabled=true.</span></span> 

2. <span data-ttu-id="7e988-134">Execute Import-CcConfiguration.</span><span class="sxs-lookup"><span data-stu-id="7e988-134">Run Import-CcConfiguration.</span></span> 

3. <span data-ttu-id="7e988-135">Execute Install-CcOMSAgent.</span><span class="sxs-lookup"><span data-stu-id="7e988-135">Run Install-CcOMSAgent.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="7e988-136">Se a credencial de OMSWorkspace nunca tiver sido definida, você será solicitado da credencial ao se executar install-CcOMSAgent.</span><span class="sxs-lookup"><span data-stu-id="7e988-136">If the OMSWorkspace credential has never been set, you are prompted for the credential when you run install-CcOMSAgent.</span></span> 

- <span data-ttu-id="7e988-137">**Se você deseja atualizar a ID de espaço de trabalho do OMS ou a chave em um aparelho de conector de nuvem que já tenha instalado um operador OMS:**</span><span class="sxs-lookup"><span data-stu-id="7e988-137">**If you want to update the OMS workspace ID or key in a Cloud Connector appliance that has already installed an OMS agent:**</span></span>

1. <span data-ttu-id="7e988-138">Para configurar o OMS ID e a chave, execute Set-CcCredential - AccountType OMSWorkspace.</span><span class="sxs-lookup"><span data-stu-id="7e988-138">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

2. <span data-ttu-id="7e988-139">Para aplicar as atualizações, execute o Install-CcOMSAgent.</span><span class="sxs-lookup"><span data-stu-id="7e988-139">To apply the updates, run Install-CcOMSAgent.</span></span> 

- <span data-ttu-id="7e988-140">**Para todos os cenários, verifique se os operadores estão conectados da seguinte maneira:**</span><span class="sxs-lookup"><span data-stu-id="7e988-140">**For all scenarios, verify that the agents are connected as follows:**</span></span>

    <span data-ttu-id="7e988-141">No portal do OMS, vá para configurações -\> fontes conectado -\> servidores do Windows.</span><span class="sxs-lookup"><span data-stu-id="7e988-141">In the OMS portal, go to Settings -\> Connected Sources -\> Windows Servers.</span></span> <span data-ttu-id="7e988-142">Você verá uma lista de máquinas conectadas.</span><span class="sxs-lookup"><span data-stu-id="7e988-142">You will see a list of connected machines.</span></span> 

## <a name="configure-oms"></a><span data-ttu-id="7e988-143">Configurar OMS</span><span class="sxs-lookup"><span data-stu-id="7e988-143">Configure OMS</span></span>

<span data-ttu-id="7e988-144">Em seguida, você precisará especificar sua configuração de OMS usando o portal do OMS.</span><span class="sxs-lookup"><span data-stu-id="7e988-144">Next, you will need to specify your OMS configuration by using the OMS portal.</span></span> <span data-ttu-id="7e988-145">Especificamente, você precisará:</span><span class="sxs-lookup"><span data-stu-id="7e988-145">Specifically, you will need to:</span></span>

- <span data-ttu-id="7e988-146">Especifique as informações sobre logs de eventos e contadores de desempenho.</span><span class="sxs-lookup"><span data-stu-id="7e988-146">Specify information about event logs and performance counters.</span></span>

- <span data-ttu-id="7e988-147">Crie alertas.</span><span class="sxs-lookup"><span data-stu-id="7e988-147">Create alerts.</span></span> 

### <a name="specify-information-about-event-logs-and-performance-counters"></a><span data-ttu-id="7e988-148">Especifique as informações sobre logs de eventos e contadores de desempenho</span><span class="sxs-lookup"><span data-stu-id="7e988-148">Specify information about event logs and performance counters</span></span>

<span data-ttu-id="7e988-149">No portal do OMS, você deve especificar informações sobre os logs de eventos e contadores de desempenho da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="7e988-149">In the OMS portal, you must specify information about the event logs and performance counters as follows:</span></span>

1. <span data-ttu-id="7e988-150">Vá para configurações -\>dados -\>logs de eventos do Windows e adicione os logs de eventos para:</span><span class="sxs-lookup"><span data-stu-id="7e988-150">Go to Settings-\>Data-\>Windows Event logs, and add event logs for:</span></span> 

   - <span data-ttu-id="7e988-151">Servidor Lync</span><span class="sxs-lookup"><span data-stu-id="7e988-151">Lync Server</span></span>

   - <span data-ttu-id="7e988-152">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="7e988-152">Application</span></span>

     > [!NOTE]
     > <span data-ttu-id="7e988-153">Você deve inserir manualmente o Lync Server na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="7e988-153">You must manually enter Lync Server in the text box.</span></span> <span data-ttu-id="7e988-154">Ela não é exibida como uma opção na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="7e988-154">It does not appear as an option in the drop-down list.</span></span> 

     <span data-ttu-id="7e988-155">Para obter mais informações, consulte [fontes de dados de log de eventos do Windows na análise de Log](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-windows-events)</span><span class="sxs-lookup"><span data-stu-id="7e988-155">For more information, see [Windows event log data sources in Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-windows-events)</span></span>

2. <span data-ttu-id="7e988-156">Vá para configurações -\>dados -\> contadores de desempenho do Windows, e adicionar contadores de desempenho para:</span><span class="sxs-lookup"><span data-stu-id="7e988-156">Go to Settings-\>Data-\> Windows Performance Counters, and add performance counters for:</span></span> 

   - <span data-ttu-id="7e988-157">**Contadores de nível do sistema operacional**.</span><span class="sxs-lookup"><span data-stu-id="7e988-157">**OS level counters**.</span></span> <span data-ttu-id="7e988-158">Você pode adicionar contadores de nível do sistema operacional, como o uso do processador, o uso da memória, o uso da rede, ou você pode usar as soluções existentes, como desempenho e capacidade, Monitor de desempenho de rede sem adicionar contadores explicitamente.</span><span class="sxs-lookup"><span data-stu-id="7e988-158">You can add OS level counters, such as processor usage, memory usage, network usage, or you can use existing solutions such as Capacity and Performance, Network Performance Monitor without adding counters explicitly.</span></span> <span data-ttu-id="7e988-159">Independentemente de como você decide monitorá-los, a Microsoft recomenda que você monitore esses contadores do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="7e988-159">No matter how you decide to monitor them, Microsoft recommends that you monitor these OS counters.</span></span>

   - <span data-ttu-id="7e988-160">**Skype para contadores de negócios**.</span><span class="sxs-lookup"><span data-stu-id="7e988-160">**Skype for Business counters**.</span></span> <span data-ttu-id="7e988-161">Existem diversos contadores fornecidos pelo Skype para negócios.</span><span class="sxs-lookup"><span data-stu-id="7e988-161">There are numerous counters provided by Skype for Business.</span></span> <span data-ttu-id="7e988-162">Você pode encontrar esses contadores fazendo logon em qualquer servidor de mediação e abrindo o Monitor de desempenho.</span><span class="sxs-lookup"><span data-stu-id="7e988-162">You can find these counters by logging on to any Mediation Server and opening the Performance Monitor.</span></span> <span data-ttu-id="7e988-163">Esses contadores começam com "LS:".</span><span class="sxs-lookup"><span data-stu-id="7e988-163">These counters start with "LS:".</span></span> <span data-ttu-id="7e988-164">A Microsoft recomenda que você inicie com os seguintes contadores de capacidade no mínimo e adicionar outras pessoas de interesse:</span><span class="sxs-lookup"><span data-stu-id="7e988-164">Microsoft recommends that you start with the following capacity counters at a minimum, and add others that are of interest:</span></span>

     <span data-ttu-id="7e988-165">Total de chamadas ativas:</span><span class="sxs-lookup"><span data-stu-id="7e988-165">Total active calls:</span></span>

   - <span data-ttu-id="7e988-166">LS:MediationServer - entrada Calls(_Total)\- atual</span><span class="sxs-lookup"><span data-stu-id="7e988-166">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

   - <span data-ttu-id="7e988-167">LS:MediationServer - saída Calls(_Total)\- atual</span><span class="sxs-lookup"><span data-stu-id="7e988-167">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

     <span data-ttu-id="7e988-168">Chamadas de desvio de mídia ativa total:</span><span class="sxs-lookup"><span data-stu-id="7e988-168">Total active media bypass calls:</span></span>

   - <span data-ttu-id="7e988-169">LS:MediationServer - entrada Calls(_Total)\- chamadas de desvio de mídia ativa</span><span class="sxs-lookup"><span data-stu-id="7e988-169">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span> 

   - <span data-ttu-id="7e988-170">LS:MediationServer - saída Calls(_Total)\- chamadas de desvio de mídia ativa</span><span class="sxs-lookup"><span data-stu-id="7e988-170">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span> 

     > [!NOTE]
     > <span data-ttu-id="7e988-171">Você deve inserir manualmente os contadores de desempenho na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="7e988-171">You must manually enter the performance counters in the text box.</span></span> <span data-ttu-id="7e988-172">Eles não aparecem como opções na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="7e988-172">They do not appear as options in the drop-down list.</span></span> 

     <span data-ttu-id="7e988-173">Para obter mais informações, consulte [Windows e Linux fontes de dados de desempenho na análise de Log](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-performance-counters)</span><span class="sxs-lookup"><span data-stu-id="7e988-173">For more information, see [Windows and Linux performance data sources in Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-performance-counters)</span></span>

### <a name="create-alerts"></a><span data-ttu-id="7e988-174">Criar alertas</span><span class="sxs-lookup"><span data-stu-id="7e988-174">Create alerts</span></span>

<span data-ttu-id="7e988-175">Existem dois tipos de alertas no OMS: número de alertas de resultados e os alertas de medida métrico.</span><span class="sxs-lookup"><span data-stu-id="7e988-175">There are two types of alerts in OMS: Number of results alerts and Metric measurement alerts.</span></span> <span data-ttu-id="7e988-176">Para obter mais informações sobre como criar alertas, consulte [Trabalhando com as regras de alerta na análise de Log](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-alerts-creating).</span><span class="sxs-lookup"><span data-stu-id="7e988-176">For more information about creating alerts, see [Working with alert rules in Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-alerts-creating).</span></span>

<span data-ttu-id="7e988-177">Ao criar alertas, você deve considerar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7e988-177">You should consider the following when creating alerts:</span></span>

- <span data-ttu-id="7e988-178">Verifique se que o alerta é um alerta de número de resultados, que é a seleção padrão.</span><span class="sxs-lookup"><span data-stu-id="7e988-178">Make sure the alert is a Number-of-results alert, which is the default selection.</span></span> 

- <span data-ttu-id="7e988-179">As consultas de demonstração exigem que o "Número de resultados" é definido como "maior que 0".</span><span class="sxs-lookup"><span data-stu-id="7e988-179">The demo queries require that "Number of results" is set to "Greater than 0".</span></span> 

- <span data-ttu-id="7e988-180">É recomendável que você defina janela de tempo e frequência de alerta para 5 minutos.</span><span class="sxs-lookup"><span data-stu-id="7e988-180">It is recommended that you set both Time window and Alert frequency to 5 minutes.</span></span> 

- <span data-ttu-id="7e988-181">É recomendável que você não ative "Suprimir alertas" para alertas de demonstração.</span><span class="sxs-lookup"><span data-stu-id="7e988-181">It is recommended that you do not enable "Suppress alerts" for demo alerts.</span></span> 

- <span data-ttu-id="7e988-182">Para cenários típicos de alerta, a Microsoft recomenda a criação de um par de alertas: alerta de um erro e a redefinição de um alerta.</span><span class="sxs-lookup"><span data-stu-id="7e988-182">For typical alert scenarios, Microsoft recommends creating a pair of alerts: one error alert and one reset alert.</span></span> <span data-ttu-id="7e988-183">O alerta de erro, selecione o nível de severidade crítico; o alerta de redefinição, selecione o nível de severidade informativa.</span><span class="sxs-lookup"><span data-stu-id="7e988-183">For the error alert, select severity level Critical; for the reset alert, select severity level Informational .</span></span>

<span data-ttu-id="7e988-184">As seções a seguir descrevem como criar alertas de amostra.</span><span class="sxs-lookup"><span data-stu-id="7e988-184">The following sections describe how to create sample alerts.</span></span>

 <span data-ttu-id="7e988-185">**Criar um par de alerta: "RTCMEDSRV não está em execução em servidores de mediação" e "RTCMEDSRV está em execução em servidores de mediação"**</span><span class="sxs-lookup"><span data-stu-id="7e988-185">**Create an alert pair: "RTCMEDSRV is NOT running in Mediation Servers" and "RTCMEDSRV is back in running in Mediation Servers"**</span></span>

<span data-ttu-id="7e988-186">Para criar esse par de alerta:</span><span class="sxs-lookup"><span data-stu-id="7e988-186">To create this alert pair:</span></span>

- <span data-ttu-id="7e988-187">A consulta para o alerta de erro é:</span><span class="sxs-lookup"><span data-stu-id="7e988-187">The query for the error alert is:</span></span>

  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    <span data-ttu-id="7e988-188">A consulta usa o filtro de computador *em que o computador contém "MediationServer"* .</span><span class="sxs-lookup"><span data-stu-id="7e988-188">The query uses the computer filter  *where Computer contains "MediationServer"*  .</span></span> <span data-ttu-id="7e988-189">O filtro seleciona apenas o computador cujo nome contém a cadeia de caracteres "MediationServer".</span><span class="sxs-lookup"><span data-stu-id="7e988-189">The filter selects only the computer whose name contains the string "MediationServer".</span></span>

     <span data-ttu-id="7e988-190">Você faria substitua o filtro filtro seu próprio computador ou simplesmente removê-lo.</span><span class="sxs-lookup"><span data-stu-id="7e988-190">You would replace the filter with your own computer filter or simply remove it.</span></span> <span data-ttu-id="7e988-191">Você pode criar filtros de cadeia de caracteres complexos sem expressões regulares.</span><span class="sxs-lookup"><span data-stu-id="7e988-191">You can create complex string filters without regular expressions.</span></span> <span data-ttu-id="7e988-192">Para obter mais informações, consulte [operadores de cadeia de caracteres](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span><span class="sxs-lookup"><span data-stu-id="7e988-192">For more information, see [String operators](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span></span> <span data-ttu-id="7e988-193">Você também pode optar por usar expressões regulares.</span><span class="sxs-lookup"><span data-stu-id="7e988-193">You can also choose to use regular expressions.</span></span> <span data-ttu-id="7e988-194">Além disso, você pode criar um grupo de computadores salvar uma consulta de pesquisa e usando esse grupo como seu filtro do computador em sua consulta de alerta.</span><span class="sxs-lookup"><span data-stu-id="7e988-194">Moreover, you can create a computer group by saving a search query and using that group as your computer filter in your alert query.</span></span> <span data-ttu-id="7e988-195">Para obter mais informações, consulte [grupos de computadores na análise de Log pesquisas de log](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-computer-groups).</span><span class="sxs-lookup"><span data-stu-id="7e988-195">For more information, see [Computer groups in Log Analytics log searches](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-computer-groups).</span></span>

    <span data-ttu-id="7e988-196">Para cada computador, a consulta de erro será Obtenha o último log de eventos para o início do serviço RTCMEDSRV e parada de serviço.</span><span class="sxs-lookup"><span data-stu-id="7e988-196">For each computer, the error query will get the last event log for both the RTCMEDSRV service start and service stop.</span></span> <span data-ttu-id="7e988-197">Ele retornará um logon se o último evento é o evento de parada do serviço; ele não retornará nada se o último evento é o evento de inicialização do serviço.</span><span class="sxs-lookup"><span data-stu-id="7e988-197">It will return one log if the last event is the service stop event; it will return nothing if the last event is the service start event.</span></span> <span data-ttu-id="7e988-198">Em resumo, a consulta retornará uma lista de servidores cuja RTCMEDSRV for interrompido na janela de tempo.</span><span class="sxs-lookup"><span data-stu-id="7e988-198">In short, the query would return a list of servers whose RTCMEDSRV is stopped in the time window.</span></span> 

- <span data-ttu-id="7e988-199">A consulta para o alerta de redefinição é:</span><span class="sxs-lookup"><span data-stu-id="7e988-199">The query for the reset alert is:</span></span>

  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    <span data-ttu-id="7e988-200">A consulta reset faz exatamente a oposto coisa da consulta de erro.</span><span class="sxs-lookup"><span data-stu-id="7e988-200">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="7e988-201">Para cada computador, ele retornará um se o último evento for o serviço iniciado evento; ele não retornará nada se o último evento é o evento de parada do serviço.</span><span class="sxs-lookup"><span data-stu-id="7e988-201">For each computer, it will return one if the last event is the service start event; it will return nothing if the last event is the service stop event.</span></span>

  <span data-ttu-id="7e988-202">**Criar um par de alerta: "demais várias chamadas simultâneas em servidores de mediação" e "chamadas simultâneas reverterá para carga normal"**</span><span class="sxs-lookup"><span data-stu-id="7e988-202">**Create an alert pair: " Too many concurrent calls in Mediation Servers" and "Concurrent calls fall back to normal load"**</span></span>

<span data-ttu-id="7e988-203">Para criar esse alerta:</span><span class="sxs-lookup"><span data-stu-id="7e988-203">To create this alert:</span></span>

- <span data-ttu-id="7e988-204">A consulta para o alerta de erro é:</span><span class="sxs-lookup"><span data-stu-id="7e988-204">The query for the error alert is:</span></span>

  ```
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    <span data-ttu-id="7e988-205">Para cada computador, a consulta obterá os contadores de últimos de chamada de entrada e chamadas de saída e soma esses dois valores.</span><span class="sxs-lookup"><span data-stu-id="7e988-205">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="7e988-206">Ele retornará um log se o valor de soma exceder 500; ele não retornará nada se isso não acontecer.</span><span class="sxs-lookup"><span data-stu-id="7e988-206">It will return one log if the sum value exceeds 500; it will return nothing if it doesn't.</span></span> <span data-ttu-id="7e988-207">Em resumo, a consulta retornará uma lista de servidores cujas chamadas simultâneas são muitos na janela de tempo.</span><span class="sxs-lookup"><span data-stu-id="7e988-207">In short, the query would return a list of servers whose concurrent calls are too many in the time window.</span></span>

- <span data-ttu-id="7e988-208">A consulta para o alerta de redefinição é:</span><span class="sxs-lookup"><span data-stu-id="7e988-208">The query for the reset alert is:</span></span>

  ```
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    <span data-ttu-id="7e988-209">A consulta reset faz exatamente a oposto coisa da consulta de erro.</span><span class="sxs-lookup"><span data-stu-id="7e988-209">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="7e988-210">Para cada computador, a consulta obterá os contadores de últimos de chamada de entrada e chamadas de saída e soma esses dois valores.</span><span class="sxs-lookup"><span data-stu-id="7e988-210">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="7e988-211">Ele retornará um log se o valor de soma for menor do que 500; ele retornará nothing caso contrário.</span><span class="sxs-lookup"><span data-stu-id="7e988-211">It will return one log if the sum value is less than 500; it will return nothing otherwise.</span></span>

  <span data-ttu-id="7e988-212">**Criar um alerta: "uso da CPU \> 90 ou RTCMEDIARELAY interrompido em servidores" alerta**</span><span class="sxs-lookup"><span data-stu-id="7e988-212">**Create an alert: "CPU usage \> 90 or RTCMEDIARELAY stopped in Servers" alert**</span></span>

<span data-ttu-id="7e988-213">Para criar esse alerta, a consulta é:</span><span class="sxs-lookup"><span data-stu-id="7e988-213">To create this alert, the query is:</span></span>

```
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

<span data-ttu-id="7e988-214">A consulta receberá todos os contadores de uso do processador e evento de parada do serviço de todos os computadores e o retorno de um log se o uso do processador exceder 90% ou serviço nunca foi interrompido.</span><span class="sxs-lookup"><span data-stu-id="7e988-214">The query will get all processor usage counter and service stop event from all computers and return one log if either processor usage exceeds 90% or service is ever stopped.</span></span> 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a><span data-ttu-id="7e988-215">Analisar os alertas no seu repositório de análise de Log</span><span class="sxs-lookup"><span data-stu-id="7e988-215">Analyze the alerts in your Log Analytics repository</span></span>

<span data-ttu-id="7e988-216">Para analisar os alertas no seu repositório, use a solução de gerenciamento de alerta.</span><span class="sxs-lookup"><span data-stu-id="7e988-216">To analyze the alerts in your repository, use the Alert Management solution.</span></span> <span data-ttu-id="7e988-217">Para obter mais informações, consulte [solução de gerenciamento de alerta no pacote de gerenciamento de operações (OMS)](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-solution-alert-management)</span><span class="sxs-lookup"><span data-stu-id="7e988-217">For more information, see [Alert Management solution in Operations Management Suite (OMS)](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-solution-alert-management)</span></span>

## <a name="recommended-minimal-monitoring-set"></a><span data-ttu-id="7e988-218">Conjunto de monitoramento mínimo recomendado</span><span class="sxs-lookup"><span data-stu-id="7e988-218">Recommended minimal monitoring set</span></span>

<span data-ttu-id="7e988-219">Para identificar problemas com os logs de eventos e contadores de desempenho:</span><span class="sxs-lookup"><span data-stu-id="7e988-219">To identify issues with event logs and performance counters:</span></span> 

- <span data-ttu-id="7e988-220">**Logs de eventos.**</span><span class="sxs-lookup"><span data-stu-id="7e988-220">**Event logs.**</span></span> <span data-ttu-id="7e988-221">Para qualquer problema, deve haver um par de eventos, com um conjunto de eventos para indicar que algo está errado, enquanto a outra indica que tudo bem.</span><span class="sxs-lookup"><span data-stu-id="7e988-221">For any issue, there should be an events pair, with one set of events to indicate something is wrong, while the other indicates that everything is well.</span></span> <span data-ttu-id="7e988-222">Para qualquer período de tempo determinado, ele é o último evento gravado que indicará se algo é anormal para esse período de tempo.</span><span class="sxs-lookup"><span data-stu-id="7e988-222">For any given time period, it is the last event recorded that will indicate whether something is amiss for that time period.</span></span>

- <span data-ttu-id="7e988-223">**Contadores de desempenho.**</span><span class="sxs-lookup"><span data-stu-id="7e988-223">**Performance Counters.**</span></span> <span data-ttu-id="7e988-224">Deve haver um limite para os contadores monitorados.</span><span class="sxs-lookup"><span data-stu-id="7e988-224">There should be a threshold for the monitored counters.</span></span>

<span data-ttu-id="7e988-225">A tabela a seguir lista os serviços que a Microsoft recomenda monitoring, listando as identificações de evento parar e iniciar:</span><span class="sxs-lookup"><span data-stu-id="7e988-225">The following table lists the services that Microsoft recommends monitoring by listing the stop and start event IDs:</span></span>

|<span data-ttu-id="7e988-226">Nome do serviço</span><span class="sxs-lookup"><span data-stu-id="7e988-226">Service Name</span></span>  <br/> |<span data-ttu-id="7e988-227">Função de servidor de destino</span><span class="sxs-lookup"><span data-stu-id="7e988-227">Target Server Role</span></span>  <br/> |<span data-ttu-id="7e988-228">Parar a ID do evento</span><span class="sxs-lookup"><span data-stu-id="7e988-228">Stop Event ID</span></span>  <br/> |<span data-ttu-id="7e988-229">ID do evento de iniciar</span><span class="sxs-lookup"><span data-stu-id="7e988-229">Start Event ID</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7e988-230">RTCMEDSRV</span><span class="sxs-lookup"><span data-stu-id="7e988-230">RTCMEDSRV</span></span>  <br/> |<span data-ttu-id="7e988-231">Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="7e988-231">Mediation Server</span></span>  <br/> |<span data-ttu-id="7e988-232">25003</span><span class="sxs-lookup"><span data-stu-id="7e988-232">25003</span></span>  <br/> |<span data-ttu-id="7e988-233">25002</span><span class="sxs-lookup"><span data-stu-id="7e988-233">25002</span></span>  <br/> |
|<span data-ttu-id="7e988-234">RTCSRV</span><span class="sxs-lookup"><span data-stu-id="7e988-234">RTCSRV</span></span>  <br/> |<span data-ttu-id="7e988-235">Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="7e988-235">Edge Server</span></span>  <br/> |<span data-ttu-id="7e988-236">12289</span><span class="sxs-lookup"><span data-stu-id="7e988-236">12289</span></span>  <br/> |<span data-ttu-id="7e988-237">12288</span><span class="sxs-lookup"><span data-stu-id="7e988-237">12288</span></span>  <br/> |
|<span data-ttu-id="7e988-238">RTCMRAUTH</span><span class="sxs-lookup"><span data-stu-id="7e988-238">RTCMRAUTH</span></span>  <br/> |<span data-ttu-id="7e988-239">Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="7e988-239">Edge Server</span></span>  <br/> |<span data-ttu-id="7e988-240">19003</span><span class="sxs-lookup"><span data-stu-id="7e988-240">19003</span></span>  <br/> |<span data-ttu-id="7e988-241">19002</span><span class="sxs-lookup"><span data-stu-id="7e988-241">19002</span></span>  <br/> |
|<span data-ttu-id="7e988-242">RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="7e988-242">RTCMEDIARELAY</span></span>  <br/> |<span data-ttu-id="7e988-243">Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="7e988-243">Edge Server</span></span>  <br/> |<span data-ttu-id="7e988-244">22003</span><span class="sxs-lookup"><span data-stu-id="7e988-244">22003</span></span>  <br/> |<span data-ttu-id="7e988-245">22002</span><span class="sxs-lookup"><span data-stu-id="7e988-245">22002</span></span>  <br/> |

<span data-ttu-id="7e988-246">A tabela a seguir lista os problemas de rede que a Microsoft recomenda monitoramento:</span><span class="sxs-lookup"><span data-stu-id="7e988-246">The following table lists the network issues that Microsoft recommends monitoring:</span></span>


| <span data-ttu-id="7e988-247">Nome do monitor</span><span class="sxs-lookup"><span data-stu-id="7e988-247">Monitor Name</span></span>  <br/>                                        | <span data-ttu-id="7e988-248">Função de servidor de destino</span><span class="sxs-lookup"><span data-stu-id="7e988-248">Target Server Role</span></span>  <br/> | <span data-ttu-id="7e988-249">Expressão de ID do evento de sucesso</span><span class="sxs-lookup"><span data-stu-id="7e988-249">Success Event ID expression</span></span>  <br/> | <span data-ttu-id="7e988-250">Expressão de ID do evento de erro</span><span class="sxs-lookup"><span data-stu-id="7e988-250">Error Event ID expression</span></span>  <br/> | <span data-ttu-id="7e988-251">Exemplo de falha</span><span class="sxs-lookup"><span data-stu-id="7e988-251">Failure example</span></span>  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| <span data-ttu-id="7e988-252">Servidor de mediação falha de conectividade de gateway</span><span class="sxs-lookup"><span data-stu-id="7e988-252">Mediation Server to gateway connectivity failure</span></span>  <br/>    | <span data-ttu-id="7e988-253">Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="7e988-253">Mediation Server</span></span>  <br/>   | <span data-ttu-id="7e988-254">25062</span><span class="sxs-lookup"><span data-stu-id="7e988-254">25062</span></span>                              |                                  | <span data-ttu-id="7e988-255">25002</span><span class="sxs-lookup"><span data-stu-id="7e988-255">25002</span></span>  <br/>           |
| <span data-ttu-id="7e988-256">Falha na conclusão de chamada do servidor de mediação para gateway</span><span class="sxs-lookup"><span data-stu-id="7e988-256">Mediation Server to gateway call completion failure</span></span>  <br/> | <span data-ttu-id="7e988-257">Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="7e988-257">Mediation Server</span></span>  <br/>   | <span data-ttu-id="7e988-258">25064</span><span class="sxs-lookup"><span data-stu-id="7e988-258">25064</span></span>                              |                                  | <span data-ttu-id="7e988-259">25002</span><span class="sxs-lookup"><span data-stu-id="7e988-259">25002</span></span>  <br/>           |
| <span data-ttu-id="7e988-260">Problemas críticos de rede</span><span class="sxs-lookup"><span data-stu-id="7e988-260">Critical network problems</span></span>  <br/>                           | <span data-ttu-id="7e988-261">Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="7e988-261">Edge Server</span></span>  <br/>        | <span data-ttu-id="7e988-262">14353</span><span class="sxs-lookup"><span data-stu-id="7e988-262">14353</span></span>                              |                                  | <span data-ttu-id="7e988-263">12288</span><span class="sxs-lookup"><span data-stu-id="7e988-263">12288</span></span>  <br/>           |

<span data-ttu-id="7e988-264">O exemplo a seguir lista os contadores de capacidade de chamada que devem ser monitorados.</span><span class="sxs-lookup"><span data-stu-id="7e988-264">The following lists the call capacity counters that should be monitored.</span></span> <span data-ttu-id="7e988-265">Esses números devem ser menor do que 500 para o standard edition de conector de nuvem; menor que 50 Edition mínima do conector de nuvem.</span><span class="sxs-lookup"><span data-stu-id="7e988-265">These numbers should be less that 500 for Cloud Connector standard edition; less than 50 for Cloud Connector minimum edition.</span></span>

- <span data-ttu-id="7e988-266">LS:MediationServer - entrada Calls(_Total)\- atual</span><span class="sxs-lookup"><span data-stu-id="7e988-266">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="7e988-267">LS:MediationServer - saída Calls(_Total)\- atual</span><span class="sxs-lookup"><span data-stu-id="7e988-267">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="7e988-268">LS:MediationServer - entrada Calls(_Total)\- chamadas de desvio de mídia ativa</span><span class="sxs-lookup"><span data-stu-id="7e988-268">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span>

- <span data-ttu-id="7e988-269">LS:MediationServer - saída Calls(_Total)\- chamadas de desvio de mídia ativa</span><span class="sxs-lookup"><span data-stu-id="7e988-269">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span>

## <a name="see-also"></a><span data-ttu-id="7e988-270">Consulte também</span><span class="sxs-lookup"><span data-stu-id="7e988-270">See also</span></span>

<span data-ttu-id="7e988-271">Para obter mais informações sobre como trabalhar com OMS, consulte o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7e988-271">For more information about working with OMS, see the following:</span></span>

- [<span data-ttu-id="7e988-272">Localizar dados usando as pesquisas de log na análise de Log</span><span class="sxs-lookup"><span data-stu-id="7e988-272">Find data using log searches in Log Analytics</span></span>](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-log-searches)

- [<span data-ttu-id="7e988-273">Referência de linguagem de análise de Log do Windows Azure</span><span class="sxs-lookup"><span data-stu-id="7e988-273">Azure Log Analytics Language Reference</span></span>](https://docs.loganalytics.io/docs/Language-Reference)

- [<span data-ttu-id="7e988-274">Compreensão dos alertas na análise de Log</span><span class="sxs-lookup"><span data-stu-id="7e988-274">Understanding alerts in Log Analytics</span></span>](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-alerts)

- [<span data-ttu-id="7e988-275">Conectar computadores Windows para o serviço de Log de análise no Windows Azure</span><span class="sxs-lookup"><span data-stu-id="7e988-275">Connect Windows computers to the Log Analytics service in Azure</span></span>](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-windows-agents)


