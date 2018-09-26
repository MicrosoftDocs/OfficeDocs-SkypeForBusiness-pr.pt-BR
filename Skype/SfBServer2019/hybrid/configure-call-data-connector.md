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
ms.openlocfilehash: 38e74e76e09d03036419f16807841a67fdf3433a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25030571"
---
# <a name="configure-call-data-connector"></a><span data-ttu-id="3355b-103">Configurar o conector de dados de chamada</span><span class="sxs-lookup"><span data-stu-id="3355b-103">Configure Call Data Connector</span></span>

[!INCLUDE [disclaimer](../disclaimer.md)]

<span data-ttu-id="3355b-104">Este artigo descreve como configurar o conector de dados chamada – um único conjunto de ferramentas que permite a exibição Skype para dados de qualidade de chamada do Business Server usando Skype para ferramentas de negócios Online chamada qualidade Dashboard (CQD) e análise de chamada (CA).</span><span class="sxs-lookup"><span data-stu-id="3355b-104">This article describes how to configure Call Data Connector--a single toolset that enables viewing Skype for Business Server Call Quality Data using Skype for Business Online Call Quality Dashboard (CQD) and Call Analytics (CA) tools.</span></span> 

> [!NOTE]
> <span data-ttu-id="3355b-105">Nesta versão de demonstração pública, painel de análise de chamadas somente está disponível.</span><span class="sxs-lookup"><span data-stu-id="3355b-105">At public preview release, only Call Analytics dashboard is available.</span></span>

<span data-ttu-id="3355b-106">Para obter mais informações sobre os benefícios de conector de dados de chamadas e pré-requisitos, como requisitos de função e configurar a conectividade híbrida, consulte [Planejar conector de dados da chamada](plan-call-data-connector.md).</span><span class="sxs-lookup"><span data-stu-id="3355b-106">For more information about Call Data Connector benefits and pre-requisites, such as role requirements and setting up hybrid connectivity, see [Plan Call Data Connector](plan-call-data-connector.md).</span></span>

## <a name="enable-monitoring"></a><span data-ttu-id="3355b-107">Habilitar o monitoramento</span><span class="sxs-lookup"><span data-stu-id="3355b-107">Enable Monitoring</span></span> 

<span data-ttu-id="3355b-108">Você deve configurar coleta de dados de qualidade da experiência (QoE); e gravação de dados de chamadas (CDR) Caso contrário, a análise de chamada e os painéis de qualidade de chamada não obtenham as informações a serem exibidas.</span><span class="sxs-lookup"><span data-stu-id="3355b-108">You must configure Call Data Recording (CDR) and Quality of Experience (QoE) data collection; otherwise, the Call Analytics and Call Quality Dashboards won’t get information to display.</span></span> <span data-ttu-id="3355b-109">Antes, você configurar conector de dados de chamada, siga as etapas fornecidas em [Deploy monitoramento no Skype para Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) para configurar o CDR e QoE.</span><span class="sxs-lookup"><span data-stu-id="3355b-109">Before you Configure Call Data Connector, follow the steps provided in [Deploy monitoring in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) to configure both CDR and QoE.</span></span>


## <a name="enable-call-data-connector"></a><span data-ttu-id="3355b-110">Habilitar o conector de dados de chamada</span><span class="sxs-lookup"><span data-stu-id="3355b-110">Enable Call Data Connector</span></span>

<span data-ttu-id="3355b-111">Para configurar e habilitar o conector de dados da chamada, você usará os cmdlets a seguir:</span><span class="sxs-lookup"><span data-stu-id="3355b-111">To configure and enable Call Data Connector, you will use the following cmdlets:</span></span>

| <span data-ttu-id="3355b-112">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="3355b-112">Cmdlet</span></span>| <span data-ttu-id="3355b-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="3355b-113">Description</span></span>|
| :-----------------|---------------:|
| <span data-ttu-id="3355b-114">New-CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="3355b-114">New-CsCloudCallDataConnection</span></span> | <span data-ttu-id="3355b-115">Um cmdlet online que estabelece o coletor de dados online.</span><span class="sxs-lookup"><span data-stu-id="3355b-115">An online cmdlet that establishes an online data collector.</span></span>|
| <span data-ttu-id="3355b-116">Get-CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="3355b-116">Get-CsCloudCallDataConnection</span></span> | <span data-ttu-id="3355b-117">Um cmdlet online que recupera o coletor de dados de online existente.</span><span class="sxs-lookup"><span data-stu-id="3355b-117">An online cmdlet that retrieves an existing online data collector.</span></span>|  
| <span data-ttu-id="3355b-118">Get-CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="3355b-118">Get-CsCloudCallDataConnector</span></span> | <span data-ttu-id="3355b-119">Um cmdlet no local que recupera as informações de conexão criadas pelo cmdlet New-CsCloudCallDataConnection.</span><span class="sxs-lookup"><span data-stu-id="3355b-119">An on-premises cmdlet that retrieves the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |
| <span data-ttu-id="3355b-120">Set-CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="3355b-120">Set-CsCloudCallDataConnector</span></span> | <span data-ttu-id="3355b-121">Um cmdlet no local que salva uma cópia local das informações de conexão criadas pelo cmdlet New-CsCloudCallDataConnection.</span><span class="sxs-lookup"><span data-stu-id="3355b-121">An on-premises cmdlet that saves an on-premises copy of the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |  
| <span data-ttu-id="3355b-122">Set-CsCloudCallDataConnectorConfiguration</span><span class="sxs-lookup"><span data-stu-id="3355b-122">Set-CsCloudCallDataConnectorConfiguration</span></span> | <span data-ttu-id="3355b-123">Um cmdlet no local que permite ativar ou desativar o conector e personalizar o nível de escopo.</span><span class="sxs-lookup"><span data-stu-id="3355b-123">An on-premises cmdlet that allows you to enable or disable the connector and customize the scope level.</span></span>|

### <a name="configure-your-environment"></a><span data-ttu-id="3355b-124">Configurar seu ambiente</span><span class="sxs-lookup"><span data-stu-id="3355b-124">Configure your environment</span></span> 

<span data-ttu-id="3355b-125">Para configurar o ambiente para permitir o coletor de dados online, você deve primeiro faça logon no Skype para negócios Online PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="3355b-125">To configure your environment to enable an online data collector, you must first log in to Skype for Business Online PowerShell as an administrator.</span></span> <span data-ttu-id="3355b-126">Para obter mais informações, consulte [Gerenciar Skype para negócios Online com o Office 365 PowerShell](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="3355b-126">For more information, see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

<span data-ttu-id="3355b-127">Há dois métodos para fazer logon no Skype para negócios Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3355b-127">There are two methods for logging in to Skype for Business Online PowerShell:</span></span>

- <span data-ttu-id="3355b-128">Do Skype do shell de gerenciamento do Business Server 2019 (recomendado método)</span><span class="sxs-lookup"><span data-stu-id="3355b-128">From the Skype for Business Server 2019 management shell (recommended method)</span></span>
- <span data-ttu-id="3355b-129">A partir de outra sessão do PowerShell</span><span class="sxs-lookup"><span data-stu-id="3355b-129">From another PowerShell session</span></span>

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a><span data-ttu-id="3355b-130">Faça logon no Skype para negócios Online PowerShell do Skype do shell de gerenciamento do Business Server (recomendado método)</span><span class="sxs-lookup"><span data-stu-id="3355b-130">Log in to Skype for Business Online PowerShell from the Skype for Business Server management shell (recommended method)</span></span>

1. <span data-ttu-id="3355b-131">Se habilitar o conector pela primeira vez, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="3355b-131">If enabling the connector for the first time, run the following command:</span></span>

   ```
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. <span data-ttu-id="3355b-132">Se você receber um erro dizendo que a conexão já existe, isso significa que a conexão de dados chamada já existe para seu locatário.</span><span class="sxs-lookup"><span data-stu-id="3355b-132">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="3355b-133">Nesse caso, execute o comando:</span><span class="sxs-lookup"><span data-stu-id="3355b-133">In this case, run the command:</span></span> 

   ```
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a><span data-ttu-id="3355b-134">Faça logon no Skype para negócios Online PowerShell a partir de outra sessão PowerShell (método opcional)</span><span class="sxs-lookup"><span data-stu-id="3355b-134">Log in to Skype for Business Online PowerShell from another PowerShell session (optional method)</span></span>

1.  <span data-ttu-id="3355b-135">Se habilitar o conector pela primeira vez, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="3355b-135">If enabling the connector for the first time, run the following command:</span></span> 

    ``` 
    New-CsCloudCallDataConnection 
    ```

2.  <span data-ttu-id="3355b-136">Se você receber um erro dizendo que a conexão já existe, isso significa que a conexão de dados chamada já existe para seu locatário.</span><span class="sxs-lookup"><span data-stu-id="3355b-136">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="3355b-137">Nesse caso, execute o comando:</span><span class="sxs-lookup"><span data-stu-id="3355b-137">In this case, run the command:</span></span> 

    ```
    Get-CsCloudCallDataConnection  
    ```

<span data-ttu-id="3355b-138">A saída dos comandos acima contém um valor de token, você precisará configurar seu ambiente local da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="3355b-138">The output of the above commands contains a token value, which you will need when configuring your on-premises environment as follows:</span></span>

<span data-ttu-id="3355b-139">De dentro do Skype do shell de gerenciamento do Business Server, especifique o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="3355b-139">From within the Skype for Business Server management shell, specify the following command:</span></span>

```
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a><span data-ttu-id="3355b-140">Configurar o escopo</span><span class="sxs-lookup"><span data-stu-id="3355b-140">Configure the scope</span></span>

<span data-ttu-id="3355b-141">Você pode habilitar o conector de dados da chamada para um site específico ou para seu Skype inteira para implantação de servidor de negócios usando o cmdlet Set-CsCloudCallDataConnectorConfiguration do dentro do Skype do shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="3355b-141">You can enable Call Data Connector for a particular site or for your entire Skype for Business Server deployment by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="3355b-142">Por exemplo, o comando a seguir habilita a chamar o conector de dados no escopo global:</span><span class="sxs-lookup"><span data-stu-id="3355b-142">For example, the following command enables Call Data Connector at the global scope:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

<span data-ttu-id="3355b-143">Além das definições globais, as definições de configuração do conector de dados de chamada podem ser atribuídas ao escopo do site.</span><span class="sxs-lookup"><span data-stu-id="3355b-143">In addition to the global settings, Call Data Connector configuration settings can be assigned to the site scope.</span></span> <span data-ttu-id="3355b-144">Isso oferece flexibilidade de gerenciamento adicionais quando se trata de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="3355b-144">This provides additional management flexibility when it comes to monitoring.</span></span> <span data-ttu-id="3355b-145">Por exemplo, um administrador pode ativar o encaminhamento de chamadas de conector de dados para o site Redmond, mas desativar o encaminhamento de chamadas de conector de dados para o site de Dublin, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="3355b-145">For example, an administrator can enable Call Data Connector forwarding for the Redmond site but disable Call Data Connector forwarding for the Dublin site, as shown in the following example:</span></span>
  
```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

<span data-ttu-id="3355b-146">As configurações definidas no escopo do site têm precedência sobre as configurações definidas no escopo global.</span><span class="sxs-lookup"><span data-stu-id="3355b-146">Settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="3355b-147">Por exemplo, suponha que o encaminhamento de chamadas de conector de dados é habilitado no escopo global, mas desabilitado no escopo do site (para o site de Redmond).</span><span class="sxs-lookup"><span data-stu-id="3355b-147">For example, suppose Call Data Connector forwarding is enabled at the global scope, but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="3355b-148">Isso significa que chamar o registro de detalhes e informações de QoE não será encaminhada para os usuários no site de Redmond.</span><span class="sxs-lookup"><span data-stu-id="3355b-148">That means that call detail recording and QoE information will not be forwarded for users in the Redmond site.</span></span> <span data-ttu-id="3355b-149">No entanto, os usuários em outros sites (ou seja, usuários gerenciados pelas definições globais, em vez de configurações do site de Redmond) terão suas informações de QoE encaminhadas e o registro de detalhes da chamada.</span><span class="sxs-lookup"><span data-stu-id="3355b-149">However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording and QoE information forwarded.</span></span>

<span data-ttu-id="3355b-150">Valores para as configurações mais comumente usadas usados pelo conector de dados da chamada são mostrados na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="3355b-150">Values for the most commonly used settings used by Call Data Connector are shown in the following table:</span></span>  
|<span data-ttu-id="3355b-151">Propriedade</span><span class="sxs-lookup"><span data-stu-id="3355b-151">Property</span></span>|<span data-ttu-id="3355b-152">Descrição</span><span class="sxs-lookup"><span data-stu-id="3355b-152">Description</span></span>|<span data-ttu-id="3355b-153">Valor padrão</span><span class="sxs-lookup"><span data-stu-id="3355b-153">Default value</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3355b-154">EnableCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="3355b-154">EnableCallDataConnector</span></span>  <br/> |<span data-ttu-id="3355b-155">Indica se o conector de dados de chamadas está habilitado.</span><span class="sxs-lookup"><span data-stu-id="3355b-155">Indicates whether Call Data Connector is enabled.</span></span> <span data-ttu-id="3355b-156">Se for True, o monitoramento de registros será encaminhada para monitoramento online.</span><span class="sxs-lookup"><span data-stu-id="3355b-156">If True, monitoring records will be forwarded to online monitoring.</span></span>  <br/> |<span data-ttu-id="3355b-157">$False</span><span class="sxs-lookup"><span data-stu-id="3355b-157">$False</span></span>  <br/> |
| <span data-ttu-id="3355b-158">Identidade </span><span class="sxs-lookup"><span data-stu-id="3355b-158">Identity</span></span> | <span data-ttu-id="3355b-159">Determina o nível de escopo para o comando: global ou site.</span><span class="sxs-lookup"><span data-stu-id="3355b-159">Determines the scope level for the command: global or site.</span></span>   | <span data-ttu-id="3355b-160">global</span><span class="sxs-lookup"><span data-stu-id="3355b-160">global</span></span>  |

## <a name="disable-call-data-connector"></a><span data-ttu-id="3355b-161">Desabilitar o conector de dados de chamada</span><span class="sxs-lookup"><span data-stu-id="3355b-161">Disable Call Data Connector</span></span>

<span data-ttu-id="3355b-162">Desabilitar o conector de dados de chamada não desassociar o repositório de monitoramento do pool de Front-End, nem desinstalar ou caso contrário afetar o banco de dados de monitoramento de back-end.</span><span class="sxs-lookup"><span data-stu-id="3355b-162">Disabling Call Data Connector does not disassociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="3355b-163">Quando você desabilita o conector de dados da chamada, pare Skype para Business Server de carregar dados de chamada para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="3355b-163">When you disable Call Data Connector, you stop Skype for Business Server from uploading call data to the cloud.</span></span> 

<span data-ttu-id="3355b-164">Desabilitar o conector de dados de chamada usando o cmdlet Set-CsCloudCallDataConnectorConfiguration do dentro do Skype do shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="3355b-164">You disable Call Data Connector by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="3355b-165">Por exemplo, o comando a seguir desabilita o conector de dados chamada no escopo global, definindo a propriedade EnableCallDataConnector como $False:</span><span class="sxs-lookup"><span data-stu-id="3355b-165">For example, the following command disables Call Data Connector at the global scope by setting the EnableCallDataConnector property to $False:</span></span>
  
```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

<span data-ttu-id="3355b-166">Se você deseja continuar com o carregamento de dados de chamada para a nuvem, defina a propriedade de EnableCallDataConnector voltar ao $True, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="3355b-166">If you want to resume uploading call data to the cloud, set the EnableCallDataConnector property back to $True, as shown in the following example:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a><span data-ttu-id="3355b-167">Modo de exibição de dados por meio do painel online no local</span><span class="sxs-lookup"><span data-stu-id="3355b-167">View on-premises data through the online dashboard</span></span>

 <span data-ttu-id="3355b-168">Depois de chamar o conector de dados estiver habilitado, você pode exibir os dados de chamada local no painel de análise de chamadas, conforme descrito na [Análise de uso de chamadas para solucionar problemas de baixa qualidade](https://docs.microsoft.com/en-us/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span><span class="sxs-lookup"><span data-stu-id="3355b-168">After Call Data Connector is enabled, you can view your on-premises call data on the Call Analytics dashboard as described in  [Use Call Analytics to troubleshoot poor quality](https://docs.microsoft.com/en-us/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span></span>


## <a name="for-more-information"></a><span data-ttu-id="3355b-169">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="3355b-169">For more information</span></span>

<span data-ttu-id="3355b-170">Para obter mais informações sobre os cmdlets, você pode usar o comando Get-Help do Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="3355b-170">For more information on the cmdlets, you can use the Get-Help command from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="3355b-171">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3355b-171">For example:</span></span>
  
<span data-ttu-id="3355b-172">Get-Help Get-CsCloudCallDataConnector | mais</span><span class="sxs-lookup"><span data-stu-id="3355b-172">Get-Help Get-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="3355b-173">Get-Help Set-CsCloudCallDataConnector | mais</span><span class="sxs-lookup"><span data-stu-id="3355b-173">Get-Help Set-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="3355b-174">Get-Help Set-CsCloudCallDataConnectorConfiguration | mais</span><span class="sxs-lookup"><span data-stu-id="3355b-174">Get-Help Set-CsCloudCallDataConnectorConfiguration | more</span></span>