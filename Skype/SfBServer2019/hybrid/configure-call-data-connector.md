---
title: Configurar o conector de dados de chamada
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Instruções para configurar o conector de dados da chamada, que permite a telemetria do Skype para negócios local para ser exibidos usando o Skype para as ferramentas de Business Online.
ms.openlocfilehash: 959bb182da91029fd43ebc3ccb99fb5a69d820b2
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/29/2018
ms.locfileid: "25838820"
---
# <a name="configure-call-data-connector"></a><span data-ttu-id="669f5-103">Configurar o conector de dados de chamada</span><span class="sxs-lookup"><span data-stu-id="669f5-103">Configure Call Data Connector</span></span>

<span data-ttu-id="669f5-104">Este artigo descreve como configurar o conector de dados chamada – um único conjunto de ferramentas que permite a exibição Skype para dados de qualidade de chamada do Business Server usando Skype para ferramentas de negócios Online chamada qualidade Dashboard (CQD) e análise de chamada (CA).</span><span class="sxs-lookup"><span data-stu-id="669f5-104">This article describes how to configure Call Data Connector--a single toolset that enables viewing Skype for Business Server Call Quality Data using Skype for Business Online Call Quality Dashboard (CQD) and Call Analytics (CA) tools.</span></span> 

> [!NOTE]
> <span data-ttu-id="669f5-105">Nesta versão de demonstração pública, painel de análise de chamadas somente está disponível.</span><span class="sxs-lookup"><span data-stu-id="669f5-105">At public preview release, only Call Analytics dashboard is available.</span></span>

<span data-ttu-id="669f5-106">Para obter mais informações sobre os benefícios de conector de dados de chamadas e pré-requisitos, como requisitos de função e configurar a conectividade híbrida, consulte [Planejar conector de dados da chamada](plan-call-data-connector.md).</span><span class="sxs-lookup"><span data-stu-id="669f5-106">For more information about Call Data Connector benefits and pre-requisites, such as role requirements and setting up hybrid connectivity, see [Plan Call Data Connector](plan-call-data-connector.md).</span></span>

## <a name="enable-monitoring"></a><span data-ttu-id="669f5-107">Habilitar o monitoramento</span><span class="sxs-lookup"><span data-stu-id="669f5-107">Enable Monitoring</span></span>
 
<span data-ttu-id="669f5-108">Você deve configurar o registro de dados de chamadas (CDR) e coleta de dados Quality of Experience (QoE) em seu front-end do pool de monitoramento, com LCSCdr e QoEMetrics bancos de dados locais; Caso contrário, a análise de chamada e os painéis de qualidade de chamada não obterá dados para trabalhar.</span><span class="sxs-lookup"><span data-stu-id="669f5-108">You must configure Call Data Recording (CDR) and Quality of Experience (QoE) data collection in your front end pool Monitoring,with local LCSCdr and QoEMetrics databases; otherwise, the Call Analytics and Call Quality Dashboards won’t get data to work with.</span></span> <span data-ttu-id="669f5-109">Antes, você configurar conector de dados de chamada, siga as etapas fornecidas em [Deploy monitoramento no Skype para Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) para configurar tanto CDR e QoE como monitoramento básico.</span><span class="sxs-lookup"><span data-stu-id="669f5-109">Before you Configure Call Data Connector, follow the steps provided in [Deploy monitoring in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) to configure both CDR and QoE as well as basic Monitoring.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="669f5-110">Conector de dados de chamada não funcionará se monitoramento não estiver habilitado no pool de front-end.</span><span class="sxs-lookup"><span data-stu-id="669f5-110">Call Data Connector will not function if Monitoring is not enabled on the front end pool.</span></span>

## <a name="enable-call-data-connector"></a><span data-ttu-id="669f5-111">Habilitar o conector de dados de chamada</span><span class="sxs-lookup"><span data-stu-id="669f5-111">Enable Call Data Connector</span></span>

<span data-ttu-id="669f5-112">Para configurar e habilitar o conector de dados da chamada, você usará os cmdlets a seguir:</span><span class="sxs-lookup"><span data-stu-id="669f5-112">To configure and enable Call Data Connector, you will use the following cmdlets:</span></span>

| <span data-ttu-id="669f5-113">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="669f5-113">Cmdlet</span></span>| <span data-ttu-id="669f5-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="669f5-114">Description</span></span>|
| :-----------------|---------------:|
| <span data-ttu-id="669f5-115">New-CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="669f5-115">New-CsCloudCallDataConnection</span></span> | <span data-ttu-id="669f5-116">Um cmdlet online que estabelece o coletor de dados online.</span><span class="sxs-lookup"><span data-stu-id="669f5-116">An online cmdlet that establishes an online data collector.</span></span>|
| <span data-ttu-id="669f5-117">Get-CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="669f5-117">Get-CsCloudCallDataConnection</span></span> | <span data-ttu-id="669f5-118">Um cmdlet online que recupera o coletor de dados de online existente.</span><span class="sxs-lookup"><span data-stu-id="669f5-118">An online cmdlet that retrieves an existing online data collector.</span></span>|  
| <span data-ttu-id="669f5-119">Get-CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="669f5-119">Get-CsCloudCallDataConnector</span></span> | <span data-ttu-id="669f5-120">Um cmdlet no local que recupera as informações de conexão criadas pelo cmdlet New-CsCloudCallDataConnection.</span><span class="sxs-lookup"><span data-stu-id="669f5-120">An on-premises cmdlet that retrieves the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |
| <span data-ttu-id="669f5-121">Set-CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="669f5-121">Set-CsCloudCallDataConnector</span></span> | <span data-ttu-id="669f5-122">Um cmdlet no local que salva uma cópia local das informações de conexão criadas pelo cmdlet New-CsCloudCallDataConnection.</span><span class="sxs-lookup"><span data-stu-id="669f5-122">An on-premises cmdlet that saves an on-premises copy of the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |  
| <span data-ttu-id="669f5-123">Set-CsCloudCallDataConnectorConfiguration</span><span class="sxs-lookup"><span data-stu-id="669f5-123">Set-CsCloudCallDataConnectorConfiguration</span></span> | <span data-ttu-id="669f5-124">Um cmdlet no local que permite ativar ou desativar o conector e personalizar o nível de escopo.</span><span class="sxs-lookup"><span data-stu-id="669f5-124">An on-premises cmdlet that allows you to enable or disable the connector and customize the scope level.</span></span>|

### <a name="configure-your-environment"></a><span data-ttu-id="669f5-125">Configurar seu ambiente</span><span class="sxs-lookup"><span data-stu-id="669f5-125">Configure your environment</span></span> 

<span data-ttu-id="669f5-126">Para configurar o ambiente para permitir o coletor de dados online, você deve primeiro faça logon no Skype para negócios Online PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="669f5-126">To configure your environment to enable an online data collector, you must first log in to Skype for Business Online PowerShell as an administrator.</span></span> <span data-ttu-id="669f5-127">Para obter mais informações, consulte [Gerenciar Skype para negócios Online com o Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="669f5-127">For more information, see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

<span data-ttu-id="669f5-128">Há dois métodos para fazer logon no Skype para negócios Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="669f5-128">There are two methods for logging in to Skype for Business Online PowerShell:</span></span>

- <span data-ttu-id="669f5-129">Do Skype do shell de gerenciamento do Business Server 2019 (recomendado método)</span><span class="sxs-lookup"><span data-stu-id="669f5-129">From the Skype for Business Server 2019 management shell (recommended method)</span></span>
- <span data-ttu-id="669f5-130">A partir de outra sessão do PowerShell</span><span class="sxs-lookup"><span data-stu-id="669f5-130">From another PowerShell session</span></span>

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a><span data-ttu-id="669f5-131">Faça logon no Skype para negócios Online PowerShell do Skype do shell de gerenciamento do Business Server (recomendado método)</span><span class="sxs-lookup"><span data-stu-id="669f5-131">Log in to Skype for Business Online PowerShell from the Skype for Business Server management shell (recommended method)</span></span>

1. <span data-ttu-id="669f5-132">Se habilitar o conector pela primeira vez, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="669f5-132">If enabling the connector for the first time, run the following command:</span></span>

   ```
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. <span data-ttu-id="669f5-133">Se você receber um erro dizendo que a conexão já existe, isso significa que a conexão de dados chamada já existe para seu locatário.</span><span class="sxs-lookup"><span data-stu-id="669f5-133">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="669f5-134">Nesse caso, execute o comando:</span><span class="sxs-lookup"><span data-stu-id="669f5-134">In this case, run the command:</span></span> 

   ```
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a><span data-ttu-id="669f5-135">Faça logon no Skype para negócios Online PowerShell a partir de outra sessão PowerShell (método opcional)</span><span class="sxs-lookup"><span data-stu-id="669f5-135">Log in to Skype for Business Online PowerShell from another PowerShell session (optional method)</span></span>

1.  <span data-ttu-id="669f5-136">Se habilitar o conector pela primeira vez, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="669f5-136">If enabling the connector for the first time, run the following command:</span></span> 

    ``` 
    New-CsCloudCallDataConnection 
    ```

2.  <span data-ttu-id="669f5-137">Se você receber um erro dizendo que a conexão já existe, isso significa que a conexão de dados chamada já existe para seu locatário.</span><span class="sxs-lookup"><span data-stu-id="669f5-137">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="669f5-138">Nesse caso, execute o comando:</span><span class="sxs-lookup"><span data-stu-id="669f5-138">In this case, run the command:</span></span> 

    ```
    Get-CsCloudCallDataConnection  
    ```

<span data-ttu-id="669f5-139">A saída dos comandos acima contém um valor de token, você precisará configurar seu ambiente local da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="669f5-139">The output of the above commands contains a token value, which you will need when configuring your on-premises environment as follows:</span></span>

<span data-ttu-id="669f5-140">De dentro do Skype do shell de gerenciamento do Business Server, especifique o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="669f5-140">From within the Skype for Business Server management shell, specify the following command:</span></span>

```
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a><span data-ttu-id="669f5-141">Configurar o escopo</span><span class="sxs-lookup"><span data-stu-id="669f5-141">Configure the scope</span></span>

<span data-ttu-id="669f5-142">Você pode habilitar o conector de dados da chamada para um site específico ou para seu Skype inteira para implantação de servidor de negócios usando o cmdlet Set-CsCloudCallDataConnectorConfiguration do dentro do Skype do shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="669f5-142">You can enable Call Data Connector for a particular site or for your entire Skype for Business Server deployment by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="669f5-143">Por exemplo, o comando a seguir habilita a chamar o conector de dados no escopo global:</span><span class="sxs-lookup"><span data-stu-id="669f5-143">For example, the following command enables Call Data Connector at the global scope:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

<span data-ttu-id="669f5-144">Além das definições globais, as definições de configuração do conector de dados de chamada podem ser atribuídas ao escopo do site.</span><span class="sxs-lookup"><span data-stu-id="669f5-144">In addition to the global settings, Call Data Connector configuration settings can be assigned to the site scope.</span></span> <span data-ttu-id="669f5-145">Isso oferece flexibilidade de gerenciamento adicionais quando se trata de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="669f5-145">This provides additional management flexibility when it comes to monitoring.</span></span> <span data-ttu-id="669f5-146">Por exemplo, um administrador pode ativar o encaminhamento de chamadas de conector de dados para o site Redmond, mas desativar o encaminhamento de chamadas de conector de dados para o site de Dublin, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="669f5-146">For example, an administrator can enable Call Data Connector forwarding for the Redmond site but disable Call Data Connector forwarding for the Dublin site, as shown in the following example:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

<span data-ttu-id="669f5-147">As configurações definidas no escopo do site têm precedência sobre as configurações definidas no escopo global.</span><span class="sxs-lookup"><span data-stu-id="669f5-147">Settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="669f5-148">Por exemplo, suponha que o encaminhamento de chamadas de conector de dados é habilitado no escopo global, mas desabilitado no escopo do site (para o site de Redmond).</span><span class="sxs-lookup"><span data-stu-id="669f5-148">For example, suppose Call Data Connector forwarding is enabled at the global scope, but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="669f5-149">Isso significa que chamar o registro de detalhes e informações de QoE não será encaminhada para os usuários no site de Redmond.</span><span class="sxs-lookup"><span data-stu-id="669f5-149">That means that call detail recording and QoE information will not be forwarded for users in the Redmond site.</span></span> <span data-ttu-id="669f5-150">No entanto, os usuários em outros sites (ou seja, usuários gerenciados pelas definições globais, em vez de configurações do site de Redmond) terão suas informações de QoE encaminhadas e o registro de detalhes da chamada.</span><span class="sxs-lookup"><span data-stu-id="669f5-150">However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording and QoE information forwarded.</span></span>

<span data-ttu-id="669f5-151">Valores para as configurações mais comumente usadas usados pelo conector de dados da chamada são mostrados na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="669f5-151">Values for the most commonly used settings used by Call Data Connector are shown in the following table:</span></span>  

|<span data-ttu-id="669f5-152">Propriedade</span><span class="sxs-lookup"><span data-stu-id="669f5-152">Property</span></span>|<span data-ttu-id="669f5-153">Descrição</span><span class="sxs-lookup"><span data-stu-id="669f5-153">Description</span></span>|<span data-ttu-id="669f5-154">Valor padrão</span><span class="sxs-lookup"><span data-stu-id="669f5-154">Default value</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="669f5-155">EnableCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="669f5-155">EnableCallDataConnector</span></span>  <br/> |<span data-ttu-id="669f5-156">Indica se o conector de dados de chamadas está habilitado.</span><span class="sxs-lookup"><span data-stu-id="669f5-156">Indicates whether Call Data Connector is enabled.</span></span> <span data-ttu-id="669f5-157">Se for True, o monitoramento de registros será encaminhada para monitoramento online.</span><span class="sxs-lookup"><span data-stu-id="669f5-157">If True, monitoring records will be forwarded to online monitoring.</span></span>  <br/> |<span data-ttu-id="669f5-158">$False</span><span class="sxs-lookup"><span data-stu-id="669f5-158">$False</span></span>  <br/> |
| <span data-ttu-id="669f5-159">Identidade </span><span class="sxs-lookup"><span data-stu-id="669f5-159">Identity</span></span> | <span data-ttu-id="669f5-160">Determina o nível de escopo para o comando: global ou site.</span><span class="sxs-lookup"><span data-stu-id="669f5-160">Determines the scope level for the command: global or site.</span></span>   | <span data-ttu-id="669f5-161">global</span><span class="sxs-lookup"><span data-stu-id="669f5-161">global</span></span>  |

## <a name="disable-call-data-connector"></a><span data-ttu-id="669f5-162">Desabilitar o conector de dados de chamada</span><span class="sxs-lookup"><span data-stu-id="669f5-162">Disable Call Data Connector</span></span>

<span data-ttu-id="669f5-163">Desabilitar o conector de dados de chamada não desassociar o repositório de monitoramento do pool de Front-End, nem desinstalar ou caso contrário afetar o banco de dados de monitoramento de back-end.</span><span class="sxs-lookup"><span data-stu-id="669f5-163">Disabling Call Data Connector does not disassociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="669f5-164">Quando você desabilita o conector de dados da chamada, pare Skype para Business Server de carregar dados de chamada para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="669f5-164">When you disable Call Data Connector, you stop Skype for Business Server from uploading call data to the cloud.</span></span> 

<span data-ttu-id="669f5-165">Desabilitar o conector de dados de chamada usando o cmdlet Set-CsCloudCallDataConnectorConfiguration do dentro do Skype do shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="669f5-165">You disable Call Data Connector by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="669f5-166">Por exemplo, o comando a seguir desabilita o conector de dados chamada no escopo global, definindo a propriedade EnableCallDataConnector como $False:</span><span class="sxs-lookup"><span data-stu-id="669f5-166">For example, the following command disables Call Data Connector at the global scope by setting the EnableCallDataConnector property to $False:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

<span data-ttu-id="669f5-167">Se você deseja continuar com o carregamento de dados de chamada para a nuvem, defina a propriedade de EnableCallDataConnector voltar ao $True, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="669f5-167">If you want to resume uploading call data to the cloud, set the EnableCallDataConnector property back to $True, as shown in the following example:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a><span data-ttu-id="669f5-168">Modo de exibição de dados por meio do painel online no local</span><span class="sxs-lookup"><span data-stu-id="669f5-168">View on-premises data through the online dashboard</span></span>

 <span data-ttu-id="669f5-169">Depois de chamar o conector de dados estiver habilitado, você pode exibir os dados de chamada local no painel de análise de chamadas, conforme descrito na [Análise de uso de chamadas para solucionar problemas de baixa qualidade](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span><span class="sxs-lookup"><span data-stu-id="669f5-169">After Call Data Connector is enabled, you can view your on-premises call data on the Call Analytics dashboard as described in  [Use Call Analytics to troubleshoot poor quality](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span></span>


## <a name="for-more-information"></a><span data-ttu-id="669f5-170">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="669f5-170">For more information</span></span>

<span data-ttu-id="669f5-171">Para obter mais informações sobre os cmdlets, você pode usar o comando Get-Help do Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="669f5-171">For more information on the cmdlets, you can use the Get-Help command from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="669f5-172">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="669f5-172">For example:</span></span>

<span data-ttu-id="669f5-173">Get-Help Get-CsCloudCallDataConnector | mais</span><span class="sxs-lookup"><span data-stu-id="669f5-173">Get-Help Get-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="669f5-174">Get-Help Set-CsCloudCallDataConnector | mais</span><span class="sxs-lookup"><span data-stu-id="669f5-174">Get-Help Set-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="669f5-175">Get-Help Set-CsCloudCallDataConnectorConfiguration | mais</span><span class="sxs-lookup"><span data-stu-id="669f5-175">Get-Help Set-CsCloudCallDataConnectorConfiguration | more</span></span>