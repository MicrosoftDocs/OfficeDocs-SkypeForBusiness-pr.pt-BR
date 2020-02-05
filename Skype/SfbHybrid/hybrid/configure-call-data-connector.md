---
title: Configurar o Call data Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Instruções para configurar o Call data Connector, que permite que a telemetria do Skype for Business local seja exibida usando as ferramentas do Skype for Business online.
ms.openlocfilehash: 0354f5a1fd1b4794af29d23e0a0fc1bf49dfebd2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726921"
---
# <a name="configure-call-data-connector"></a><span data-ttu-id="683ce-103">Configurar o Call data Connector</span><span class="sxs-lookup"><span data-stu-id="683ce-103">Configure Call Data Connector</span></span>

<span data-ttu-id="683ce-104">Este artigo descreve como configurar o Call data Connector – um único conjunto de ferramentas que permite exibir dados de qualidade de chamada do Skype for Business Server usando o painel de qualidade de chamada do Skype for Business online (CQD) e as ferramentas de análise de chamada (CA).</span><span class="sxs-lookup"><span data-stu-id="683ce-104">This article describes how to configure Call Data Connector--a single toolset that enables viewing Skype for Business Server Call Quality Data using Skype for Business Online Call Quality Dashboard (CQD) and Call Analytics (CA) tools.</span></span>

<span data-ttu-id="683ce-105">Para obter mais informações sobre os benefícios e pré-requisitos do Call data Connector, como requisitos de função e configuração da conectividade híbrida, consulte [Plan Call data Connector](plan-call-data-connector.md).</span><span class="sxs-lookup"><span data-stu-id="683ce-105">For more information about Call Data Connector benefits and pre-requisites, such as role requirements and setting up hybrid connectivity, see [Plan Call Data Connector](plan-call-data-connector.md).</span></span>

## <a name="enable-monitoring"></a><span data-ttu-id="683ce-106">Habilitar o monitoramento</span><span class="sxs-lookup"><span data-stu-id="683ce-106">Enable Monitoring</span></span>
 
<span data-ttu-id="683ce-107">Você deve configurar o registro de dados de chamada (CDR) e a coleta de dados de QoE (qualidade da experiência) em seu monitoramento do pool de front-ends, com bancos de dados locais do LCSCdr e do QoEMetrics; caso contrário, os painéis de análise de chamada e de qualidade de chamada não terão dados com os quais trabalhar.</span><span class="sxs-lookup"><span data-stu-id="683ce-107">You must configure Call Data Recording (CDR) and Quality of Experience (QoE) data collection in your front end pool Monitoring,with local LCSCdr and QoEMetrics databases; otherwise, the Call Analytics and Call Quality Dashboards won’t get data to work with.</span></span> <span data-ttu-id="683ce-108">Antes de configurar o Call data Connector, siga as etapas fornecidas em [Deploy Monitoring in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) para configurar CDR e QoE, bem como monitoramento básico.</span><span class="sxs-lookup"><span data-stu-id="683ce-108">Before you Configure Call Data Connector, follow the steps provided in [Deploy monitoring in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) to configure both CDR and QoE as well as basic Monitoring.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="683ce-109">Call data Connector não funcionará se o monitoramento não estiver habilitado no pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="683ce-109">Call Data Connector will not function if Monitoring is not enabled on the front end pool.</span></span>

## <a name="enable-call-data-connector"></a><span data-ttu-id="683ce-110">Habilitar conector de dados de chamada</span><span class="sxs-lookup"><span data-stu-id="683ce-110">Enable Call Data Connector</span></span>

<span data-ttu-id="683ce-111">Para configurar e habilitar o Call data Connector, você usará os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="683ce-111">To configure and enable Call Data Connector, you will use the following cmdlets:</span></span>

| <span data-ttu-id="683ce-112">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="683ce-112">Cmdlet</span></span>| <span data-ttu-id="683ce-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="683ce-113">Description</span></span>|
| :-----------------|---------------:|
| <span data-ttu-id="683ce-114">New-CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="683ce-114">New-CsCloudCallDataConnection</span></span> | <span data-ttu-id="683ce-115">Um cmdlet online que estabelece um coletor de dados online.</span><span class="sxs-lookup"><span data-stu-id="683ce-115">An online cmdlet that establishes an online data collector.</span></span>|
| <span data-ttu-id="683ce-116">Get-CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="683ce-116">Get-CsCloudCallDataConnection</span></span> | <span data-ttu-id="683ce-117">Um cmdlet online que recupera um coletor de dados online existente.</span><span class="sxs-lookup"><span data-stu-id="683ce-117">An online cmdlet that retrieves an existing online data collector.</span></span>|  
| <span data-ttu-id="683ce-118">Get-CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="683ce-118">Get-CsCloudCallDataConnector</span></span> | <span data-ttu-id="683ce-119">Um cmdlet local que recupera as informações de conexão criadas pelo cmdlet New-CsCloudCallDataConnection.</span><span class="sxs-lookup"><span data-stu-id="683ce-119">An on-premises cmdlet that retrieves the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |
| <span data-ttu-id="683ce-120">Set-CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="683ce-120">Set-CsCloudCallDataConnector</span></span> | <span data-ttu-id="683ce-121">Um cmdlet local que salva uma cópia local das informações de conexão criadas pelo cmdlet New-CsCloudCallDataConnection.</span><span class="sxs-lookup"><span data-stu-id="683ce-121">An on-premises cmdlet that saves an on-premises copy of the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |  
| <span data-ttu-id="683ce-122">Set-CsCloudCallDataConnectorConfiguration</span><span class="sxs-lookup"><span data-stu-id="683ce-122">Set-CsCloudCallDataConnectorConfiguration</span></span> | <span data-ttu-id="683ce-123">Um cmdlet local que permite habilitar ou desabilitar o conector e personalizar o nível de escopo.</span><span class="sxs-lookup"><span data-stu-id="683ce-123">An on-premises cmdlet that allows you to enable or disable the connector and customize the scope level.</span></span>|

> [!NOTE]
> <span data-ttu-id="683ce-124">Para apagar sua configuração e começar novamente, use o cmdlet Remove-csclouddatconnectorconfiguration.</span><span class="sxs-lookup"><span data-stu-id="683ce-124">To erase your configuration and start over, please use the Remove-csclouddatconnectorconfiguration cmdlet.</span></span>

### <a name="configure-your-environment"></a><span data-ttu-id="683ce-125">Configurar seu ambiente</span><span class="sxs-lookup"><span data-stu-id="683ce-125">Configure your environment</span></span> 

<span data-ttu-id="683ce-126">Para configurar seu ambiente para habilitar um coletor de dados online, primeiro você deve fazer logon no Skype for Business online PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="683ce-126">To configure your environment to enable an online data collector, you must first log in to Skype for Business Online PowerShell as an administrator.</span></span> <span data-ttu-id="683ce-127">Para obter mais informações, consulte [Manage Skype for Business online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="683ce-127">For more information, see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

<span data-ttu-id="683ce-128">Há dois métodos para fazer logon no Skype for Business online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="683ce-128">There are two methods for logging in to Skype for Business Online PowerShell:</span></span>

- <span data-ttu-id="683ce-129">No Shell de gerenciamento do Skype for Business Server 2019 (método recomendado)</span><span class="sxs-lookup"><span data-stu-id="683ce-129">From the Skype for Business Server 2019 management shell (recommended method)</span></span>
- <span data-ttu-id="683ce-130">De outra sessão do PowerShell</span><span class="sxs-lookup"><span data-stu-id="683ce-130">From another PowerShell session</span></span>

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a><span data-ttu-id="683ce-131">Faça logon no Skype for Business online PowerShell do Shell de gerenciamento do Skype for Business Server (método recomendado)</span><span class="sxs-lookup"><span data-stu-id="683ce-131">Log in to Skype for Business Online PowerShell from the Skype for Business Server management shell (recommended method)</span></span>

1. <span data-ttu-id="683ce-132">Se habilitar o conector pela primeira vez, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="683ce-132">If enabling the connector for the first time, run the following command:</span></span>

   ```PowerShell
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. <span data-ttu-id="683ce-133">Se você receber um erro de que a conexão já existe, isso significa que a conexão de dados de chamada já existe para o locatário.</span><span class="sxs-lookup"><span data-stu-id="683ce-133">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="683ce-134">Nesse caso, execute o comando:</span><span class="sxs-lookup"><span data-stu-id="683ce-134">In this case, run the command:</span></span> 

   ```PowerShell
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a><span data-ttu-id="683ce-135">Faça logon no Skype for Business online PowerShell a partir de outra sessão do PowerShell (método opcional)</span><span class="sxs-lookup"><span data-stu-id="683ce-135">Log in to Skype for Business Online PowerShell from another PowerShell session (optional method)</span></span>

1.  <span data-ttu-id="683ce-136">Se habilitar o conector pela primeira vez, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="683ce-136">If enabling the connector for the first time, run the following command:</span></span> 

    ```PowerShell 
    New-CsCloudCallDataConnection 
    ```

2.  <span data-ttu-id="683ce-137">Se você receber um erro de que a conexão já existe, isso significa que a conexão de dados de chamada já existe para o locatário.</span><span class="sxs-lookup"><span data-stu-id="683ce-137">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="683ce-138">Nesse caso, execute o comando:</span><span class="sxs-lookup"><span data-stu-id="683ce-138">In this case, run the command:</span></span> 

    ```PowerShell
    Get-CsCloudCallDataConnection  
    ```

<span data-ttu-id="683ce-139">A saída dos comandos acima contém um valor de token, que você precisará ao configurar seu ambiente local da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="683ce-139">The output of the above commands contains a token value, which you will need when configuring your on-premises environment as follows:</span></span>

<span data-ttu-id="683ce-140">No Shell de gerenciamento do Skype for Business Server, especifique o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="683ce-140">From within the Skype for Business Server management shell, specify the following command:</span></span>

```PowerShell
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a><span data-ttu-id="683ce-141">Configurar o escopo</span><span class="sxs-lookup"><span data-stu-id="683ce-141">Configure the scope</span></span>

<span data-ttu-id="683ce-142">Você pode habilitar o Call data Connector para um determinado site ou para toda a sua implantação do Skype for Business Server usando o cmdlet Set-CsCloudCallDataConnectorConfiguration de dentro do Shell de gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="683ce-142">You can enable Call Data Connector for a particular site or for your entire Skype for Business Server deployment by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="683ce-143">Por exemplo, o seguinte comando habilita o Call data Connector no escopo global:</span><span class="sxs-lookup"><span data-stu-id="683ce-143">For example, the following command enables Call Data Connector at the global scope:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

<span data-ttu-id="683ce-144">Além das configurações globais, as definições de configuração do conector de dados de chamadas podem ser atribuídas ao escopo do site.</span><span class="sxs-lookup"><span data-stu-id="683ce-144">In addition to the global settings, Call Data Connector configuration settings can be assigned to the site scope.</span></span> <span data-ttu-id="683ce-145">Isso oferece flexibilidade de gerenciamento adicional quando se trata de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="683ce-145">This provides additional management flexibility when it comes to monitoring.</span></span> <span data-ttu-id="683ce-146">Por exemplo, um administrador pode habilitar o encaminhamento do conector de dados de chamada para o site de Redmond, mas desabilitar o encaminhamento do conector de dados de chamadas para o site Dublin, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="683ce-146">For example, an administrator can enable Call Data Connector forwarding for the Redmond site but disable Call Data Connector forwarding for the Dublin site, as shown in the following example:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

<span data-ttu-id="683ce-147">As configurações definidas no escopo do site têm precedência sobre as configurações definidas no escopo global.</span><span class="sxs-lookup"><span data-stu-id="683ce-147">Settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="683ce-148">Por exemplo, suponha que o encaminhamento do Call data Connector está habilitado no escopo global, mas desabilitado no escopo do site (para o site de Redmond).</span><span class="sxs-lookup"><span data-stu-id="683ce-148">For example, suppose Call Data Connector forwarding is enabled at the global scope, but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="683ce-149">Isso significa que a gravação de detalhes da chamada e as informações de QoE não serão encaminhadas para os usuários no site de Redmond.</span><span class="sxs-lookup"><span data-stu-id="683ce-149">That means that call detail recording and QoE information will not be forwarded for users in the Redmond site.</span></span> <span data-ttu-id="683ce-150">No entanto, os usuários em outros sites (ou seja, os usuários gerenciados pelas configurações globais em vez das configurações de site de Redmond) terão suas informações de registro de detalhes de chamadas e de QoE encaminhadas.</span><span class="sxs-lookup"><span data-stu-id="683ce-150">However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording and QoE information forwarded.</span></span>

<span data-ttu-id="683ce-151">Os valores das configurações usadas com mais frequência usadas pelo Call data Connector são mostrados na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="683ce-151">Values for the most commonly used settings used by Call Data Connector are shown in the following table:</span></span>  

|<span data-ttu-id="683ce-152">Propriedade</span><span class="sxs-lookup"><span data-stu-id="683ce-152">Property</span></span>|<span data-ttu-id="683ce-153">Descrição</span><span class="sxs-lookup"><span data-stu-id="683ce-153">Description</span></span>|<span data-ttu-id="683ce-154">Valor padrão</span><span class="sxs-lookup"><span data-stu-id="683ce-154">Default value</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="683ce-155">EnableCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="683ce-155">EnableCallDataConnector</span></span>  <br/> |<span data-ttu-id="683ce-156">Indica se o conector de dados de chamada está habilitado.</span><span class="sxs-lookup"><span data-stu-id="683ce-156">Indicates whether Call Data Connector is enabled.</span></span> <span data-ttu-id="683ce-157">Se true, os registros de monitoramento serão encaminhados para o monitoramento online.</span><span class="sxs-lookup"><span data-stu-id="683ce-157">If True, monitoring records will be forwarded to online monitoring.</span></span>  <br/> |<span data-ttu-id="683ce-158">$False</span><span class="sxs-lookup"><span data-stu-id="683ce-158">$False</span></span>  <br/> |
| <span data-ttu-id="683ce-159">Identidade</span><span class="sxs-lookup"><span data-stu-id="683ce-159">Identity</span></span> | <span data-ttu-id="683ce-160">Determina o nível de escopo para o comando: global ou site.</span><span class="sxs-lookup"><span data-stu-id="683ce-160">Determines the scope level for the command: global or site.</span></span>   | <span data-ttu-id="683ce-161">global</span><span class="sxs-lookup"><span data-stu-id="683ce-161">global</span></span>  |

## <a name="disable-call-data-connector"></a><span data-ttu-id="683ce-162">Desabilitar o conector de dados de chamadas</span><span class="sxs-lookup"><span data-stu-id="683ce-162">Disable Call Data Connector</span></span>

<span data-ttu-id="683ce-163">Desabilitar o Call data Connector não desassocia o repositório de monitoramento do pool de front-ends, nem desinstala ou afeta o banco de dados de monitoramento de backend.</span><span class="sxs-lookup"><span data-stu-id="683ce-163">Disabling Call Data Connector does not disassociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="683ce-164">Ao desabilitar o Call data Connector, você interrompe o Skype for Business Server de carregar dados de chamadas para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="683ce-164">When you disable Call Data Connector, you stop Skype for Business Server from uploading call data to the cloud.</span></span> 

<span data-ttu-id="683ce-165">Você desabilita o Call data Connector usando o cmdlet Set-CsCloudCallDataConnectorConfiguration de dentro do Shell de gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="683ce-165">You disable Call Data Connector by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="683ce-166">Por exemplo, o comando a seguir desabilita o conector de dados de chamada no escopo global, definindo a propriedade EnableCallDataConnector como $False:</span><span class="sxs-lookup"><span data-stu-id="683ce-166">For example, the following command disables Call Data Connector at the global scope by setting the EnableCallDataConnector property to $False:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

<span data-ttu-id="683ce-167">Se você quiser continuar carregando dados de chamada para a nuvem, defina a propriedade EnableCallDataConnector de volta para $True, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="683ce-167">If you want to resume uploading call data to the cloud, set the EnableCallDataConnector property back to $True, as shown in the following example:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a><span data-ttu-id="683ce-168">Exibir dados locais por meio do painel online</span><span class="sxs-lookup"><span data-stu-id="683ce-168">View on-premises data through the online dashboard</span></span>

 <span data-ttu-id="683ce-169">Após a habilitação do conector de dados de chamada, você pode exibir os dados de chamada local no painel do Analytics ou no painel de qualidade de chamada, conforme descrito em [usar o Call Analytics para solucionar problemas de qualidade ruim](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) e [ativar e usar o painel de qualidade da chamada para o Microsoft Teams e o Skype for Business online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard).</span><span class="sxs-lookup"><span data-stu-id="683ce-169">After Call Data Connector is enabled, you can view your on-premises call data on the Call Analytics dashboard or Call Quality Dashboard as described in  [Use Call Analytics to troubleshoot poor quality](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) and [Turn on and use Call Quality Dashboard for Microsoft Teams and Skype for Business Online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="683ce-170">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="683ce-170">For more information</span></span>

<span data-ttu-id="683ce-171">Para obter mais informações sobre os cmdlets, você pode usar o comando Get-Help do Shell de gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="683ce-171">For more information on the cmdlets, you can use the Get-Help command from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="683ce-172">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="683ce-172">For example:</span></span>

<span data-ttu-id="683ce-173">Get-Help Get-CsCloudCallDataConnector | adicionais</span><span class="sxs-lookup"><span data-stu-id="683ce-173">Get-Help Get-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="683ce-174">Get-Help Set-CsCloudCallDataConnector | adicionais</span><span class="sxs-lookup"><span data-stu-id="683ce-174">Get-Help Set-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="683ce-175">Get-Help Set-CsCloudCallDataConnectorConfiguration | adicionais</span><span class="sxs-lookup"><span data-stu-id="683ce-175">Get-Help Set-CsCloudCallDataConnectorConfiguration | more</span></span>
