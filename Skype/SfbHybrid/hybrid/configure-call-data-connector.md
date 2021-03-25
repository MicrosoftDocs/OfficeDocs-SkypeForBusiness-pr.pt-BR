---
title: Configurar o Conector de Dados de Chamada
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
description: Instruções para configurar o Conector de Dados de Chamadas, que permite que a telemetria do Skype for Business local seja exibida usando ferramentas do Skype for Business Online.
ms.openlocfilehash: f78d59d02964bd826fc705bc193cae3e21b293a5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118990"
---
# <a name="configure-call-data-connector"></a><span data-ttu-id="c0e66-103">Configurar o Conector de Dados de Chamada</span><span class="sxs-lookup"><span data-stu-id="c0e66-103">Configure Call Data Connector</span></span>

<span data-ttu-id="c0e66-104">Este artigo descreve como configurar o Conector de Dados de Chamada, um único conjunto de ferramentas que permite exibir dados de qualidade de chamadas do Skype for Business Server usando o CQD (Painel de Qualidade de Chamadas) do Skype for Business Online e as ferramentas de Análise de Chamadas (CA).</span><span class="sxs-lookup"><span data-stu-id="c0e66-104">This article describes how to configure Call Data Connector--a single toolset that enables viewing Skype for Business Server Call Quality Data using Skype for Business Online Call Quality Dashboard (CQD) and Call Analytics (CA) tools.</span></span>

<span data-ttu-id="c0e66-105">Para obter mais informações sobre os benefícios e pré-requisitos do Conector de Dados de [Chamada,](plan-call-data-connector.md)como requisitos de função e configuração da conectividade híbrida, consulte Plan Call Data Connector .</span><span class="sxs-lookup"><span data-stu-id="c0e66-105">For more information about Call Data Connector benefits and pre-requisites, such as role requirements and setting up hybrid connectivity, see [Plan Call Data Connector](plan-call-data-connector.md).</span></span>

## <a name="enable-monitoring"></a><span data-ttu-id="c0e66-106">Habilitar Monitoramento</span><span class="sxs-lookup"><span data-stu-id="c0e66-106">Enable Monitoring</span></span>
 
<span data-ttu-id="c0e66-107">Você deve configurar a cdr (gravação de dados de chamada) e a coleta de dados de Qualidade da Experiência (QoE) no monitoramento do pool front-end, com bancos de dados LCSCdr e QoEMetrics locais; caso contrário, os Painéis de Qualidade de Chamada e Análise de Chamada não obterão dados para trabalhar.</span><span class="sxs-lookup"><span data-stu-id="c0e66-107">You must configure Call Data Recording (CDR) and Quality of Experience (QoE) data collection in your front end pool Monitoring,with local LCSCdr and QoEMetrics databases; otherwise, the Call Analytics and Call Quality Dashboards won’t get data to work with.</span></span> <span data-ttu-id="c0e66-108">Antes de configurar o Conector de Dados de Chamada, siga as etapas fornecidas em Implantar monitoramento no [Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) para configurar CDR e QoE, bem como monitoramento básico.</span><span class="sxs-lookup"><span data-stu-id="c0e66-108">Before you Configure Call Data Connector, follow the steps provided in [Deploy monitoring in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) to configure both CDR and QoE as well as basic Monitoring.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c0e66-109">O Conector de Dados de Chamada não funcionará se o Monitoramento não estiver habilitado no pool front-end.</span><span class="sxs-lookup"><span data-stu-id="c0e66-109">Call Data Connector will not function if Monitoring is not enabled on the front end pool.</span></span>

## <a name="enable-call-data-connector"></a><span data-ttu-id="c0e66-110">Habilitar o Conector de Dados de Chamada</span><span class="sxs-lookup"><span data-stu-id="c0e66-110">Enable Call Data Connector</span></span>

<span data-ttu-id="c0e66-111">Para configurar e habilitar o Conector de Dados de Chamada, você usará os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="c0e66-111">To configure and enable Call Data Connector, you will use the following cmdlets:</span></span>

| <span data-ttu-id="c0e66-112">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="c0e66-112">Cmdlet</span></span>| <span data-ttu-id="c0e66-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="c0e66-113">Description</span></span>|
| :-----------------|---------------:|
| <span data-ttu-id="c0e66-114">New-CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="c0e66-114">New-CsCloudCallDataConnection</span></span> | <span data-ttu-id="c0e66-115">Um cmdlet online que estabelece um coletor de dados online.</span><span class="sxs-lookup"><span data-stu-id="c0e66-115">An online cmdlet that establishes an online data collector.</span></span>|
| <span data-ttu-id="c0e66-116">Get-CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="c0e66-116">Get-CsCloudCallDataConnection</span></span> | <span data-ttu-id="c0e66-117">Um cmdlet online que recupera um coletor de dados online existente.</span><span class="sxs-lookup"><span data-stu-id="c0e66-117">An online cmdlet that retrieves an existing online data collector.</span></span>|  
| <span data-ttu-id="c0e66-118">Get-CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="c0e66-118">Get-CsCloudCallDataConnector</span></span> | <span data-ttu-id="c0e66-119">Um cmdlet local que recupera as informações de conexão criadas pelo cmdlet New-CsCloudCallDataConnection local.</span><span class="sxs-lookup"><span data-stu-id="c0e66-119">An on-premises cmdlet that retrieves the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |
| <span data-ttu-id="c0e66-120">Set-CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="c0e66-120">Set-CsCloudCallDataConnector</span></span> | <span data-ttu-id="c0e66-121">Um cmdlet local que salva uma cópia local das informações de conexão criadas pelo cmdlet New-CsCloudCallDataConnection local.</span><span class="sxs-lookup"><span data-stu-id="c0e66-121">An on-premises cmdlet that saves an on-premises copy of the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |  
| <span data-ttu-id="c0e66-122">Set-CsCloudCallDataConnectorConfiguration</span><span class="sxs-lookup"><span data-stu-id="c0e66-122">Set-CsCloudCallDataConnectorConfiguration</span></span> | <span data-ttu-id="c0e66-123">Um cmdlet local que permite habilitar ou desabilitar o conector e personalizar o nível de escopo.</span><span class="sxs-lookup"><span data-stu-id="c0e66-123">An on-premises cmdlet that allows you to enable or disable the connector and customize the scope level.</span></span>|

> [!NOTE]
> <span data-ttu-id="c0e66-124">Para apagar sua configuração e recomeçar, use o cmdlet Remove-csclouddatconnectorconfiguration.</span><span class="sxs-lookup"><span data-stu-id="c0e66-124">To erase your configuration and start over, please use the Remove-csclouddatconnectorconfiguration cmdlet.</span></span>

### <a name="configure-your-environment"></a><span data-ttu-id="c0e66-125">Configurar seu ambiente</span><span class="sxs-lookup"><span data-stu-id="c0e66-125">Configure your environment</span></span> 

<span data-ttu-id="c0e66-126">Para configurar seu ambiente para habilitar um coletor de dados online, você deve primeiro fazer logoff no PowerShell do Skype for Business Online como administrador.</span><span class="sxs-lookup"><span data-stu-id="c0e66-126">To configure your environment to enable an online data collector, you must first log in to Skype for Business Online PowerShell as an administrator.</span></span> <span data-ttu-id="c0e66-127">Para obter mais informações, consulte [Manage Skype for Business Online with Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="c0e66-127">For more information, see [Manage Skype for Business Online with Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

<span data-ttu-id="c0e66-128">Há dois métodos para entrar no PowerShell do Skype for Business Online:</span><span class="sxs-lookup"><span data-stu-id="c0e66-128">There are two methods for logging in to Skype for Business Online PowerShell:</span></span>

- <span data-ttu-id="c0e66-129">No shell de gerenciamento do Skype for Business Server 2019 (método recomendado)</span><span class="sxs-lookup"><span data-stu-id="c0e66-129">From the Skype for Business Server 2019 management shell (recommended method)</span></span>
- <span data-ttu-id="c0e66-130">De outra sessão do PowerShell</span><span class="sxs-lookup"><span data-stu-id="c0e66-130">From another PowerShell session</span></span>

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a><span data-ttu-id="c0e66-131">Faça logoff no PowerShell do Skype for Business Online no shell de gerenciamento do Skype for Business Server (método recomendado)</span><span class="sxs-lookup"><span data-stu-id="c0e66-131">Log in to Skype for Business Online PowerShell from the Skype for Business Server management shell (recommended method)</span></span>

1. <span data-ttu-id="c0e66-132">Se habilenciar o conector pela primeira vez, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="c0e66-132">If enabling the connector for the first time, run the following command:</span></span>

   ```PowerShell
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. <span data-ttu-id="c0e66-133">Se você receber um erro de que a conexão já existe, isso significa que a conexão de dados de chamada já existe para seu locatário.</span><span class="sxs-lookup"><span data-stu-id="c0e66-133">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="c0e66-134">Nesse caso, execute o comando:</span><span class="sxs-lookup"><span data-stu-id="c0e66-134">In this case, run the command:</span></span> 

   ```PowerShell
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a><span data-ttu-id="c0e66-135">Faça logon no PowerShell do Skype for Business Online de outra sessão do PowerShell (método opcional)</span><span class="sxs-lookup"><span data-stu-id="c0e66-135">Log in to Skype for Business Online PowerShell from another PowerShell session (optional method)</span></span>

1.  <span data-ttu-id="c0e66-136">Se habilenciar o conector pela primeira vez, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="c0e66-136">If enabling the connector for the first time, run the following command:</span></span> 

    ```PowerShell 
    New-CsCloudCallDataConnection 
    ```

2.  <span data-ttu-id="c0e66-137">Se você receber um erro de que a conexão já existe, isso significa que a conexão de dados de chamada já existe para seu locatário.</span><span class="sxs-lookup"><span data-stu-id="c0e66-137">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="c0e66-138">Nesse caso, execute o comando:</span><span class="sxs-lookup"><span data-stu-id="c0e66-138">In this case, run the command:</span></span> 

    ```PowerShell
    Get-CsCloudCallDataConnection  
    ```

<span data-ttu-id="c0e66-139">A saída dos comandos acima contém um valor de token, que você precisará ao configurar seu ambiente local da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="c0e66-139">The output of the above commands contains a token value, which you will need when configuring your on-premises environment as follows:</span></span>

<span data-ttu-id="c0e66-140">No shell de gerenciamento do Skype for Business Server, especifique o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="c0e66-140">From within the Skype for Business Server management shell, specify the following command:</span></span>

```PowerShell
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a><span data-ttu-id="c0e66-141">Configurar o escopo</span><span class="sxs-lookup"><span data-stu-id="c0e66-141">Configure the scope</span></span>

<span data-ttu-id="c0e66-142">Você pode habilitar o Conector de Dados de Chamada para um site específico ou para toda a implantação do Skype for Business Server usando o cmdlet Set-CsCloudCallDataConnectorConfiguration de dentro do shell de gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c0e66-142">You can enable Call Data Connector for a particular site or for your entire Skype for Business Server deployment by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="c0e66-143">Por exemplo, o comando a seguir habilita o Conector de Dados de Chamada no escopo global:</span><span class="sxs-lookup"><span data-stu-id="c0e66-143">For example, the following command enables Call Data Connector at the global scope:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

<span data-ttu-id="c0e66-144">Além das configurações globais, as configurações do Conector de Dados de Chamada podem ser atribuídas ao escopo do site.</span><span class="sxs-lookup"><span data-stu-id="c0e66-144">In addition to the global settings, Call Data Connector configuration settings can be assigned to the site scope.</span></span> <span data-ttu-id="c0e66-145">Isso fornece flexibilidade de gerenciamento adicional quando se trata de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="c0e66-145">This provides additional management flexibility when it comes to monitoring.</span></span> <span data-ttu-id="c0e66-146">Por exemplo, um administrador pode habilitar o encaminhamento do Conector de Dados de Chamada para o site redmond, mas desabilitar o encaminhamento do Conector de Dados de Chamada para o site dublin, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="c0e66-146">For example, an administrator can enable Call Data Connector forwarding for the Redmond site but disable Call Data Connector forwarding for the Dublin site, as shown in the following example:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

<span data-ttu-id="c0e66-147">As configurações definidas no escopo do site têm precedência sobre as configurações definidas no escopo global.</span><span class="sxs-lookup"><span data-stu-id="c0e66-147">Settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="c0e66-148">Por exemplo, suponha que o encaminhamento do Conector de Dados de Chamada está habilitado no escopo global, mas desabilitado no escopo do site (para o site redmond).</span><span class="sxs-lookup"><span data-stu-id="c0e66-148">For example, suppose Call Data Connector forwarding is enabled at the global scope, but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="c0e66-149">Isso significa que o registro de detalhes da chamada e as informações de QoE não serão encaminhadas para os usuários no site redmond.</span><span class="sxs-lookup"><span data-stu-id="c0e66-149">That means that call detail recording and QoE information will not be forwarded for users in the Redmond site.</span></span> <span data-ttu-id="c0e66-150">No entanto, os usuários em outros sites (ou seja, usuários gerenciados pelas configurações globais em vez das configurações de site redmond) terão suas informações de detalhes de chamada e informações de QoE encaminhadas.</span><span class="sxs-lookup"><span data-stu-id="c0e66-150">However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording and QoE information forwarded.</span></span>

<span data-ttu-id="c0e66-151">Os valores das configurações mais usadas pelo Conector de Dados de Chamada são mostrados na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="c0e66-151">Values for the most commonly used settings used by Call Data Connector are shown in the following table:</span></span>  

|<span data-ttu-id="c0e66-152">Propriedade</span><span class="sxs-lookup"><span data-stu-id="c0e66-152">Property</span></span>|<span data-ttu-id="c0e66-153">Descrição</span><span class="sxs-lookup"><span data-stu-id="c0e66-153">Description</span></span>|<span data-ttu-id="c0e66-154">Valor padrão</span><span class="sxs-lookup"><span data-stu-id="c0e66-154">Default value</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c0e66-155">EnableCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="c0e66-155">EnableCallDataConnector</span></span>  <br/> |<span data-ttu-id="c0e66-156">Indica se o Conector de Dados de Chamada está habilitado.</span><span class="sxs-lookup"><span data-stu-id="c0e66-156">Indicates whether Call Data Connector is enabled.</span></span> <span data-ttu-id="c0e66-157">Se True, os registros de monitoramento serão encaminhados para monitoramento online.</span><span class="sxs-lookup"><span data-stu-id="c0e66-157">If True, monitoring records will be forwarded to online monitoring.</span></span>  <br/> |<span data-ttu-id="c0e66-158">$False</span><span class="sxs-lookup"><span data-stu-id="c0e66-158">$False</span></span>  <br/> |
| <span data-ttu-id="c0e66-159">Identidade</span><span class="sxs-lookup"><span data-stu-id="c0e66-159">Identity</span></span> | <span data-ttu-id="c0e66-160">Determina o nível de escopo do comando: global ou site.</span><span class="sxs-lookup"><span data-stu-id="c0e66-160">Determines the scope level for the command: global or site.</span></span>   | <span data-ttu-id="c0e66-161">global</span><span class="sxs-lookup"><span data-stu-id="c0e66-161">global</span></span>  |

## <a name="disable-call-data-connector"></a><span data-ttu-id="c0e66-162">Desabilitar o Conector de Dados de Chamada</span><span class="sxs-lookup"><span data-stu-id="c0e66-162">Disable Call Data Connector</span></span>

<span data-ttu-id="c0e66-163">Desabilitar o Conector de Dados de Chamada não desassocia o armazenamento de monitoramento do pool de Front-End, nem desinstala ou afeta o banco de dados de monitoramento de back-end.</span><span class="sxs-lookup"><span data-stu-id="c0e66-163">Disabling Call Data Connector does not disassociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="c0e66-164">Ao desabilitar o Conector de Dados de Chamadas, você impede que o Skype for Business Server carregue dados de chamadas na nuvem.</span><span class="sxs-lookup"><span data-stu-id="c0e66-164">When you disable Call Data Connector, you stop Skype for Business Server from uploading call data to the cloud.</span></span> 

<span data-ttu-id="c0e66-165">Desabilite o Conector de Dados de Chamada usando o cmdlet Set-CsCloudCallDataConnectorConfiguration de dentro do shell de gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c0e66-165">You disable Call Data Connector by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="c0e66-166">Por exemplo, o comando a seguir desabilita o Conector de Dados de Chamada no escopo global definindo a propriedade EnableCallDataConnector como $False:</span><span class="sxs-lookup"><span data-stu-id="c0e66-166">For example, the following command disables Call Data Connector at the global scope by setting the EnableCallDataConnector property to $False:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

<span data-ttu-id="c0e66-167">Se você quiser continuar carregando dados de chamada para a nuvem, desmarcar a propriedade EnableCallDataConnector de volta para $True, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="c0e66-167">If you want to resume uploading call data to the cloud, set the EnableCallDataConnector property back to $True, as shown in the following example:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a><span data-ttu-id="c0e66-168">Exibir dados locais por meio do painel online</span><span class="sxs-lookup"><span data-stu-id="c0e66-168">View on-premises data through the online dashboard</span></span>

 <span data-ttu-id="c0e66-169">Depois que o Conector de Dados de Chamada for habilitado, você poderá exibir seus dados de chamadas locais no painel do Análise de Chamadas ou no Painel de Qualidade de Chamadas, conforme descrito em [Use Call Analytics](/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) para solucionar problemas de baixa qualidade e Ativar e usar o Painel de Qualidade de Chamadas para o Microsoft Teams e o Skype for Business [Online.](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard)</span><span class="sxs-lookup"><span data-stu-id="c0e66-169">After Call Data Connector is enabled, you can view your on-premises call data on the Call Analytics dashboard or Call Quality Dashboard as described in  [Use Call Analytics to troubleshoot poor quality](/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) and [Turn on and use Call Quality Dashboard for Microsoft Teams and Skype for Business Online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="c0e66-170">Para saber mais</span><span class="sxs-lookup"><span data-stu-id="c0e66-170">For more information</span></span>

<span data-ttu-id="c0e66-171">Para obter mais informações sobre os cmdlets, você pode usar o comando Get-Help do Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c0e66-171">For more information on the cmdlets, you can use the Get-Help command from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="c0e66-172">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c0e66-172">For example:</span></span>

<span data-ttu-id="c0e66-173">Get-Help Get-CsCloudCallDataConnector | mais</span><span class="sxs-lookup"><span data-stu-id="c0e66-173">Get-Help Get-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="c0e66-174">Get-Help Set-CsCloudCallDataConnector | mais</span><span class="sxs-lookup"><span data-stu-id="c0e66-174">Get-Help Set-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="c0e66-175">Get-Help Set-CsCloudCallDataConnectorConfiguration | mais</span><span class="sxs-lookup"><span data-stu-id="c0e66-175">Get-Help Set-CsCloudCallDataConnectorConfiguration | more</span></span>