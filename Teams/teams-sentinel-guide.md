---
title: Azure Sentinel e Microsoft Teams
author: MicrosoftHeidi
ms.author: tracyp
manager: dansimp
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Conselhos e aprendizados de segurança para os ITAdmins sobre o uso do Sentinel para monitorar e buscar ameaças que possam surgir no Teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 310105abaa5a5c545bdb85963bb14796c630bf66
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121621"
---
# <a name="azure-sentinel-and-microsoft-teams"></a><span data-ttu-id="b637c-103">Azure Sentinel e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b637c-103">Azure Sentinel and Microsoft Teams</span></span>

<span data-ttu-id="b637c-104">O Teams desempenha um papel central na comunicação e no compartilhamento de dados no Microsoft 365 Cloud.</span><span class="sxs-lookup"><span data-stu-id="b637c-104">Teams serves a central role in both communication and data sharing in the Microsoft 365 Cloud.</span></span> <span data-ttu-id="b637c-105">Como o serviço do Teams aborda tantas tecnologias subjacentes na nuvem, ele pode se beneficiar das análises humanas e automatizadas, não apenas no que diz respeito à *busca em logs*, mas também no *monitoramento em tempo real das reuniões*.</span><span class="sxs-lookup"><span data-stu-id="b637c-105">Because the Teams service touches on so many underlying technologies in the Cloud, it can benefit from human and automated analysis not only when it comes to *hunting in logs*, but also in *real-time monitoring of meetings*.</span></span> <span data-ttu-id="b637c-106">O Azure Sentinel oferece aos administradores essas soluções.</span><span class="sxs-lookup"><span data-stu-id="b637c-106">Azure Sentinel offers admins these solutions.</span></span>

> [!NOTE]
> <span data-ttu-id="b637c-107">Precisa de uma atualização no Azure Sentinel?</span><span class="sxs-lookup"><span data-stu-id="b637c-107">Need a refresher on Azure Sentinel?</span></span> <span data-ttu-id="b637c-108">[Este artigo](https://docs.microsoft.com/azure/sentinel/overview) é ideal para isso.</span><span class="sxs-lookup"><span data-stu-id="b637c-108">[This article](https://docs.microsoft.com/azure/sentinel/overview) is just the thing.</span></span>

## <a name="sentinel-and-microsoft-teams-activity-logs"></a><span data-ttu-id="b637c-109">Logs de atividades do Sentinel e do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b637c-109">Sentinel and Microsoft Teams Activity Logs</span></span>

<span data-ttu-id="b637c-110">Este artigo foca na coleta de logs de atividades do Teams no Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="b637c-110">This article focuses on collecting Teams activity logs in Azure Sentinel.</span></span> <span data-ttu-id="b637c-111">Além de permitir que os administradores coloquem o gerenciamento de segurança em um painel de vidro (incluindo dispositivos selecionados de terceiros, Proteção contra Ameaças da Microsoft e outras cargas de trabalho do Microsoft 365), as pastas de trabalho do Sentinel e as runbooks podem tornar o monitoramento de segurança sistemático.</span><span class="sxs-lookup"><span data-stu-id="b637c-111">Aside from allowing administrators to put security management under one pane of glass (including any selected 3rd party devices, Microsoft Threat Protection, and other Microsoft 365 Workloads), Sentinel workbooks, and runbooks can make security monitoring systematic.</span></span> <span data-ttu-id="b637c-112">Um primeiro passo importante nesse processo é coletar os logs necessários para análise.</span><span class="sxs-lookup"><span data-stu-id="b637c-112">A good first step in this process is collecting the needed logs for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="b637c-113">Mais de uma assinatura do Microsoft 365 pode ser apresentada na mesma instância do Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="b637c-113">More than one Microsoft 365 subscription can be surfaced in the same instance of Azure Sentinel.</span></span> <span data-ttu-id="b637c-114">Isso permitirá o [monitoramento em tempo real](https://docs.microsoft.com/azure/sentinel/livestream) e a busca por ameaças nos arquivos de logs históricos.</span><span class="sxs-lookup"><span data-stu-id="b637c-114">This will allow for [realtime monitoring](https://docs.microsoft.com/azure/sentinel/livestream) and hunting for threats in historical log file s.</span></span> <span data-ttu-id="b637c-115">Os administradores poderão buscar usando [consultas entre recursos](https://docs.microsoft.com/azure/azure-monitor/log-query/cross-workspace-query), que estão em um único grupo de recursos, entre grupos de recursos ou em outra assinatura.</span><span class="sxs-lookup"><span data-stu-id="b637c-115">Administrators will be able to hunt using [cross-resource queries](https://docs.microsoft.com/azure/azure-monitor/log-query/cross-workspace-query), that is within a single resource group, across resource groups, or in another subscription.</span></span>

## <a name="step-1-collect-teams-logs"></a><span data-ttu-id="b637c-116">Etapa 1: coletar registros do Teams</span><span class="sxs-lookup"><span data-stu-id="b637c-116">Step 1: Collect Teams logs</span></span>

<span data-ttu-id="b637c-117">Esta seção tem três partes:</span><span class="sxs-lookup"><span data-stu-id="b637c-117">This section has three parts:</span></span>

1. <span data-ttu-id="b637c-118">Habilitar logs de auditoria no **Microsoft 365** (M365).</span><span class="sxs-lookup"><span data-stu-id="b637c-118">Enabling Audit Logs in **Microsoft 365** (M365).</span></span>
2. <span data-ttu-id="b637c-119">Registrar um aplicativo no **Microsoft Azure** para permitir a autenticação e a autorização para a coleta de logs.</span><span class="sxs-lookup"><span data-stu-id="b637c-119">Registering an App in **Microsoft Azure** to permit authentication and authorization for log collection.</span></span>
3. <span data-ttu-id="b637c-120">Registrar a assinatura da API que permitirá a coleta de logs pela API do M365 pelo **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="b637c-120">Registering the API subscription that will allow log collection via M365 API via **PowerShell**.</span></span>

### <a name="enable-audit-logs-in-m365"></a><span data-ttu-id="b637c-121">Habilitar logs de auditoria no M365</span><span class="sxs-lookup"><span data-stu-id="b637c-121">Enable Audit logs in M365</span></span>

<span data-ttu-id="b637c-122">Como o Teams registra as atividades de logs no M365, os logs de auditoria não são coletados por padrão.</span><span class="sxs-lookup"><span data-stu-id="b637c-122">Because Teams logs activity through M365, audit logs aren't collected by default.</span></span> <span data-ttu-id="b637c-123">Ative esse recurso por meio [destas etapas](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%C2%A0).</span><span class="sxs-lookup"><span data-stu-id="b637c-123">Turn on this feature via [these steps](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%C2%A0).</span></span> <span data-ttu-id="b637c-124">Os dados do Teams são coletados na auditoria do M365 em *Audit.General*.</span><span class="sxs-lookup"><span data-stu-id="b637c-124">Teams data is collected in the M365 audit under *Audit.General*.</span></span>

### <a name="register-an-app-in-microsoft-azure-for-log-collection"></a><span data-ttu-id="b637c-125">Registrar um aplicativo no Microsoft Azure para a coleção de logs</span><span class="sxs-lookup"><span data-stu-id="b637c-125">Register an App in Microsoft Azure for log collection</span></span>

> [!TIP]
> <span data-ttu-id="b637c-126">Antes de começar, você precisará registrar a **ID do aplicativo/ID do cliente** e a **ID do locatário** para uso posterior.</span><span class="sxs-lookup"><span data-stu-id="b637c-126">Before you begin, you will need to record you **Application ID / Client ID**, and your **Tenant ID** for later use.</span></span> <span data-ttu-id="b637c-127">Certifique-se de capturá-los enquanto segue as etapas de registro do aplicativo a seguir.</span><span class="sxs-lookup"><span data-stu-id="b637c-127">Be sure to capture them as you walk through app registration steps below.</span></span> <span data-ttu-id="b637c-128">As duas IDs serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="b637c-128">You will see both IDs.</span></span>
>- <span data-ttu-id="b637c-129">Após a criação do aplicativo, clique em Registro do aplicativo na barra lateral de início rápido > Localize o nome de exibição do seu novo aplicativo > copie a ID do aplicativo (cliente).</span><span class="sxs-lookup"><span data-stu-id="b637c-129">After your app is created, click App Registration on the quick launch side-bar > Find your new app's display name > copy the Application (client) ID.</span></span>
>- <span data-ttu-id="b637c-130">Clique em Visão geral na barra lateral de início rápido, copie a ID do diretório (locatário).</span><span class="sxs-lookup"><span data-stu-id="b637c-130">Click Overview on the quick launch side-bar > copy the Directory (tenant) ID.</span></span>

<span data-ttu-id="b637c-131">Autentique e autorize um aplicativo do Azure AD (Azure Active Directory) para coletar dados de log da API.</span><span class="sxs-lookup"><span data-stu-id="b637c-131">Authenticate and authorize an Azure Active Directory (Azure AD) app to collect log data from the API.</span></span>

1. <span data-ttu-id="b637c-132">Navegue até a lâmina *Azure AD*, no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="b637c-132">Navigate to your *Azure AD* blade in the Azure portal.</span></span>
2. <span data-ttu-id="b637c-133">Clique em *Registros de aplicativos* na barra de início rápido.</span><span class="sxs-lookup"><span data-stu-id="b637c-133">Click on *App registrations* in the quick launch side-bar.</span></span>
3. <span data-ttu-id="b637c-134">Selecione *Novo registro*.</span><span class="sxs-lookup"><span data-stu-id="b637c-134">Select *New registration*.</span></span>
4. <span data-ttu-id="b637c-135">Nomeie o aplicativo de coleta de log do Teams e clique em *Registrar*.</span><span class="sxs-lookup"><span data-stu-id="b637c-135">Name your Teams log collecting app and click *Register*.</span></span>
5. <span data-ttu-id="b637c-136">Clique neste caminho: *Permissões da API* > *Adicionar uma permissão* > *APIs de gerenciamento do Office 365* > *Permissões de aplicativo*.</span><span class="sxs-lookup"><span data-stu-id="b637c-136">Click along this path: *API Permissions* > *Add a permission* > *Office 365 Management APIs* > *Application permissions*.</span></span>
6. <span data-ttu-id="b637c-137">Expanda Feed de atividades e marque *ActivityFeed.Read*.</span><span class="sxs-lookup"><span data-stu-id="b637c-137">Expand Activity Feed and check *ActivityFeed.Read*.</span></span>
7. <span data-ttu-id="b637c-138">Escolha a opção *Conceder consentimento de administração* aqui.</span><span class="sxs-lookup"><span data-stu-id="b637c-138">Choose *Grand admin consent* here.</span></span> <span data-ttu-id="b637c-139">Clique em Sim quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="b637c-139">Click Yes when prompted asking if you mean it.</span></span>
8. <span data-ttu-id="b637c-140">Clique em *Certificados e Segredos* na barra lateral> botão *Novo segredo do cliente*.</span><span class="sxs-lookup"><span data-stu-id="b637c-140">Click *Certificates and Secrets* in the side-bar> *New client secret* button.</span></span>
9. <span data-ttu-id="b637c-141">Na janela Novo segredo do cliente, digite uma descrição para o novo Segredo do Cliente, escolha “Nunca” para Expiração e clique em *Adicionar*.</span><span class="sxs-lookup"><span data-stu-id="b637c-141">On the New client secret window, enter a description for the new Client Secret, make sure you choose 'Never' for Expiration, and click *Add*.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b637c-142">É **essencial** copiar o novo segredo do cliente em uma entrada do gerenciador de senhas que passa pelo nome do aplicativo recém-criado.</span><span class="sxs-lookup"><span data-stu-id="b637c-142">It's **critical** to copy the new client secret into a password manager entry that goes under the name of the newly created app.</span></span> <span data-ttu-id="b637c-143">Não será possível voltar a examinar esse segredo após o fechamento da lâmina do Azure (*lâmina* sendo o termo do Azure para janela).</span><span class="sxs-lookup"><span data-stu-id="b637c-143">You won't be able to get back to look at this secret after the closing out of the Azure blade (*blade* being the Azure term for window).</span></span>

### <a name="register-the-api-with-powershell-to-collect-teams-logs"></a><span data-ttu-id="b637c-144">Registrar a API no PowerShell para coletar logs do Teams</span><span class="sxs-lookup"><span data-stu-id="b637c-144">Register the API with PowerShell to collect Teams logs</span></span>

<span data-ttu-id="b637c-145">A etapa final da instalação é coletar e registrar a assinatura da API para poder coletar os dados de log.</span><span class="sxs-lookup"><span data-stu-id="b637c-145">The final step in setup is to collect and register the API subscription so that you can collect your log data.</span></span> <span data-ttu-id="b637c-146">Isso é feito pelas chamadas do PowerShell REST para a API de atividade de gerenciamento do M365.</span><span class="sxs-lookup"><span data-stu-id="b637c-146">This is done via PowerShell REST calls to the M365 Management Activity API.</span></span>

<span data-ttu-id="b637c-147">Esteja pronto para fornecer a **ID do aplicativo (cliente)**, o novo **Segredo do cliente**, seu **domínio de URL para o M365** e os valores de **ID do diretório (locatário)** no cmdlet do PowerShell a seguir.</span><span class="sxs-lookup"><span data-stu-id="b637c-147">Be ready to supply **Application (client) ID**, the new **Client Secret**, your **URL domain for M365**, and **Directory (tenant) ID** values in the PowerShell cmdlet below.</span></span>

```PowerShell
$ClientID = "<Application (client) ID>"  
$ClientSecret = "<Client secret>"  
$loginURL = "https://login.microsoftonline.com/"  
$tenantdomain = "<domain>.onmicrosoft.com"  

$TenantGUID = "<Directory (tenant) ID>"  
$resource = "https://manage.office.com"  
$body = @{grant_type="client_credentials";resource=$resource;client_id=$ClientID;client_secret=$ClientSecret}
$oauth = Invoke-RestMethod -Method Post -Uri $loginURL/$tenantdomain/oauth2/token?api-version=1.0 -Body $body  
$headerParams = @{'Authorization'="$($oauth.token_type) $($oauth.access_token)"}
$publisher = New-Guid
Invoke-WebRequest -Method Post -Headers $headerParams -Uri "https://manage.office.com/api/v1.0/$tenantGuid/activity/feed/subscriptions/start?contentType=Audit.General&PublisherIdentifier=$Publisher"
```

## <a name="step-2-deploy-a-sentinel-playbook-to-ingest-the-teams-logs"></a><span data-ttu-id="b637c-148">Etapa 2: implantar um guia estratégico do Sentinel para incluir os logs do Teams</span><span class="sxs-lookup"><span data-stu-id="b637c-148">Step 2: Deploy a Sentinel Playbook to ingest the Teams logs</span></span>

<span data-ttu-id="b637c-149">Os guias estratégicos do Azure Sentinel (também chamados de aplicativos lógicos) permitirão que o Azure inclua os dados coletados do Teams.</span><span class="sxs-lookup"><span data-stu-id="b637c-149">Azure Sentinel Playbooks (also called Logic Apps) will allow Azure to ingest your collected Teams data.</span></span> <span data-ttu-id="b637c-150">O aplicativo lógico consulta o Office 365 para localizar os dados de auditoria que ele grava no espaço de trabalho do Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="b637c-150">The Logic App queries Office 365 to find the audit data it writes into the Azure Sentinel workspace.</span></span>

<span data-ttu-id="b637c-151">Use [este](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) modelo ARM para implantar o guia estratégico do Sentinel.</span><span class="sxs-lookup"><span data-stu-id="b637c-151">Use [this](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) ARM template to deploy your Sentinel Playbook.</span></span>

<span data-ttu-id="b637c-152">Coisas para lembrar:</span><span class="sxs-lookup"><span data-stu-id="b637c-152">Things to remember:</span></span>

1. <span data-ttu-id="b637c-153">Será necessário percorrer o modelo ARM e substituir determinados valores pelos apropriados ao seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="b637c-153">You will need to walk through the ARM template and replace certain of the values with values appropriate for your own environment.</span></span>
2. <span data-ttu-id="b637c-154">Será necessário reservar um tempo entre a inclusão de logs e a observação dos resultados no Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="b637c-154">You will need to allow time between the ingestion of logs and looking at the results in Azure Sentinel.</span></span>

   <span data-ttu-id="b637c-155">Aguarde de 5 a 10 minutos, entendendo que se não houver dados nos últimos 5 minutos, você receberá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="b637c-155">Wait for 5 to 10 minutes, understanding that if there is no data within the past 5 minutes you will see an error message.</span></span> <span data-ttu-id="b637c-156">Verifique os logs de auditoria e lembre-se de que, como as informações do Teams estão nos eventos Audit.General, que coletam mais que os logs do Teams, os resultados devem aparecer dentro de 5 a 10 minutos nos sistemas em uso.</span><span class="sxs-lookup"><span data-stu-id="b637c-156">Check Audit logs and keep in mind that because Teams information is in the Audit.General events, which collects more than Teams logs, results should appear within 5 to 10 minutes on systems that are in use.</span></span> <span data-ttu-id="b637c-157">Se estiver usando um ambiente de texto, certifique-se de usar o Teams para gerar o registro em log.</span><span class="sxs-lookup"><span data-stu-id="b637c-157">If using a text environment, be certain to use Teams in order to generate logging.</span></span>

![Gráfico que mostra as classes de aplicativos lógicos.](media/tracyp-teams-sentinel-logic-app.png#thumbnail)

 <p><details><summary> <span data-ttu-id="b637c-159">Explicação das ações no gráfico:</span><span class="sxs-lookup"><span data-stu-id="b637c-159">Explanation of actions in the graphic:</span></span> 
  </summary>

  <span data-ttu-id="b637c-160">• A recorrência é o Gatilho do Aplicativo Lógico que informa ao fluxo de trabalho que seja executado de hora em hora.</span><span class="sxs-lookup"><span data-stu-id="b637c-160">• Recurrence is the Logic App Trigger that tells the workflow to run every hour.</span></span>
  <p>
<span data-ttu-id="b637c-161">• A ação Hora Atual é muito básica e só tem a hora atual.</span><span class="sxs-lookup"><span data-stu-id="b637c-161">• The Current Time action is very basic and just gets the current time.</span></span>
  <p>
<span data-ttu-id="b637c-162">• A inicialização da Variável cria uma variável chamada NextPage e a define como 1.</span><span class="sxs-lookup"><span data-stu-id="b637c-162">• Initialize Variable creates a variable called NextPage and sets it to 1.</span></span> <span data-ttu-id="b637c-163">Isso será usado mais tarde para lidar com a paginação da API do O365.</span><span class="sxs-lookup"><span data-stu-id="b637c-163">This will be used later in order to handle pagination from the O365 API.</span></span>
  <p>
<span data-ttu-id="b637c-164">• A inicialização da Variável 2 cria uma variável vazia chamada Start Time.</span><span class="sxs-lookup"><span data-stu-id="b637c-164">• Initialize Variable 2 creates an empty variable called Start Time.</span></span>
  <p>
<span data-ttu-id="b637c-165">• Executar consulta e listar resultados é uma ação do Azure Monitor que consultará o espaço de trabalho quanto ao último log do O365 inserido no Aplicativo Lógico.</span><span class="sxs-lookup"><span data-stu-id="b637c-165">• Run Query and list results is an Azure Monitor action that will query the workspace for the last O365 log that was entered from the Logic App.</span></span>
  <p>
<span data-ttu-id="b637c-166">• A condição 4 é usada para verificar se a ação de executar consulta e listar resultados retornou dados.</span><span class="sxs-lookup"><span data-stu-id="b637c-166">• Condition 4 is used to check whether the Run Query and list results query returned any data.</span></span> <span data-ttu-id="b637c-167">Isso é feito para verificar se é a primeira vez que o aplicativo lógico foi usado.</span><span class="sxs-lookup"><span data-stu-id="b637c-167">This is done to check if this is the very first time the Logic App has been used.</span></span> <span data-ttu-id="b637c-168">Se nenhum dado for retornado, a variável StartTime será definida como Agora – 24 horas.</span><span class="sxs-lookup"><span data-stu-id="b637c-168">If no data is returned, StartTime variable is set to Now – 24 hours.</span></span> <span data-ttu-id="b637c-169">Se os dados forem retornados, a StartTime será definida como o último registro TimeGenerated.</span><span class="sxs-lookup"><span data-stu-id="b637c-169">If data is returned, StartTime is set to the last record TimeGenerated.</span></span> <span data-ttu-id="b637c-170">Isso é feito para que a consulta possa obter dados da última entrada até agora na pesquisa em relação à API do O365, ou nas últimas 24 horas se esta for a primeira execução.</span><span class="sxs-lookup"><span data-stu-id="b637c-170">This is done so that the query can get data from the last entry till now in the poll against the O365 API, or in the last 24 hours if this is the first run.</span></span>
  <p>
<span data-ttu-id="b637c-171">• A inicialização da Variável 3 cria uma variável chamada AvailableUri.</span><span class="sxs-lookup"><span data-stu-id="b637c-171">• Initialize Variable 3 creates a variable called AvailableUri.</span></span> <span data-ttu-id="b637c-172">Esta é uma cadeira de caracteres com a URL criada usando StartTime e CurrentTime como horário de início e de término, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="b637c-172">This is a string with the URL built using the StartTime and CurrentTime as start and end times, respectively.</span></span>
  <p>
<span data-ttu-id="b637c-173">• A condição Until é um loop que permite que o aplicativo lógico continue pesquisando a API para ver se há mais dados (paginação).</span><span class="sxs-lookup"><span data-stu-id="b637c-173">• The Until condition is a loop that allows the logic app to keep polling the API to see if there is more data (pagination).</span></span> <span data-ttu-id="b637c-174">O loop continuará enquanto a variável NextPage for 1.</span><span class="sxs-lookup"><span data-stu-id="b637c-174">As long as NextPage variable is 1 the loop will continue.</span></span> <span data-ttu-id="b637c-175">Posteriormente, essa variável será atualizada se não houver mais páginas pendentes de recuperação.</span><span class="sxs-lookup"><span data-stu-id="b637c-175">Later this variable will be updated if there are no more pages left to retrieve.</span></span>
  <p>
<span data-ttu-id="b637c-176">• Dentro do loop Until, a primeira etapa HTTP se conecta ao AvailableURI.</span><span class="sxs-lookup"><span data-stu-id="b637c-176">• Inside the Until loop, the first HTTP step Connects to the AvailableURI.</span></span> <span data-ttu-id="b637c-177">Esse URI retorna uma lista dos conteúdos disponíveis e os URIS de cada conteúdo.</span><span class="sxs-lookup"><span data-stu-id="b637c-177">This URI returns a list of available content and each contents URI.</span></span> <span data-ttu-id="b637c-178">Há mais informações sobre como isso funciona neste URL: https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.</span><span class="sxs-lookup"><span data-stu-id="b637c-178">There's more on how this works at this URL: https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.</span></span>
  <p>
<span data-ttu-id="b637c-179">• Em seguida, uma verificação será executada para garantir que os dados sejam retornados.</span><span class="sxs-lookup"><span data-stu-id="b637c-179">• Next a check is run to make sure data is returned.</span></span> <span data-ttu-id="b637c-180">A Condição verificará se o tamanho do corpo é 0.</span><span class="sxs-lookup"><span data-stu-id="b637c-180">The Condition checks if the length of the body is 0.</span></span> <span data-ttu-id="b637c-181">Nesse caso, não há dados para gravar no Análise de Logs.</span><span class="sxs-lookup"><span data-stu-id="b637c-181">If so there is no data to write to Log Analytics.</span></span> <span data-ttu-id="b637c-182">Se o valor for maior do que 0, há dados a processar.</span><span class="sxs-lookup"><span data-stu-id="b637c-182">If the value is greater than 0, there is data to process.</span></span>
  <p>
<span data-ttu-id="b637c-183">• Se dados forem detectados, será necessário reprocessá-los.</span><span class="sxs-lookup"><span data-stu-id="b637c-183">• If data is detected, it must next be processed.</span></span> <span data-ttu-id="b637c-184">Analisar o Parse define um esquema dos dados retornados.</span><span class="sxs-lookup"><span data-stu-id="b637c-184">Parse JSON defines a schema of the returned data.</span></span> <span data-ttu-id="b637c-185">Isso permite que aplicativos lógicos usem os dados analisados como conteúdo dinâmico nas etapas posteriores.</span><span class="sxs-lookup"><span data-stu-id="b637c-185">This allows logic apps to use the parsed data as Dynamic content in later steps.</span></span>
  <p>
<span data-ttu-id="b637c-186">• Como a lista retornada de dados disponíveis é uma Matriz, uma ação For Each é usada para percorrer a lista de conteúdo disponível.</span><span class="sxs-lookup"><span data-stu-id="b637c-186">• Since the returned list of available data is an Array, a For Each action is used to loop through the list of available content.</span></span>
  <p>
<span data-ttu-id="b637c-187">• Em seguida, deve-se capturar o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="b637c-187">• Next is grabbing the content.</span></span>  <span data-ttu-id="b637c-188">O HTTP é usado novamente para obter o contentUri (uma propriedade dinâmica criada a partir da Análise JSON), que é a URL dos dados a serem recuperados.</span><span class="sxs-lookup"><span data-stu-id="b637c-188">HTTP is used again to get the contentUri (a dynamic property created from Parse JSON), which is the URL of the data to retrieve.</span></span>
  <p>
<span data-ttu-id="b637c-189">• A Análise JSON também é usada para analisar os dados retornados.</span><span class="sxs-lookup"><span data-stu-id="b637c-189">• Parse JSON is also used to parse the returned data.</span></span> <span data-ttu-id="b637c-190">É possível encontrar alguns exemplos de conteúdo nesta URL: https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.</span><span class="sxs-lookup"><span data-stu-id="b637c-190">You can find some sample content at this URL: https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.</span></span>
  <p>
<span data-ttu-id="b637c-191">• Os dados retornados também são uma matriz.</span><span class="sxs-lookup"><span data-stu-id="b637c-191">• The data returned is also an array.</span></span> <span data-ttu-id="b637c-192">Um loop For Each também pode ser usado aqui.</span><span class="sxs-lookup"><span data-stu-id="b637c-192">A For Each loop can be used here as well.</span></span> <span data-ttu-id="b637c-193">Nesse loop, o fluxo de trabalho pega o item atual dos dados e usa a ação Send Data para gravar os dados na Análise de Logs.</span><span class="sxs-lookup"><span data-stu-id="b637c-193">In this loop, the workflow takes the current item of data and uses the Send Data action to write the data to Log Analytics.</span></span>
  <p>
<span data-ttu-id="b637c-194">• Como pode haver várias páginas de conteúdo disponível, uma condição verificará se o NextPageUri não é NULL.</span><span class="sxs-lookup"><span data-stu-id="b637c-194">• Since there may be multiple pages of available content, a condition checks if the NextPageUri is not NULL.</span></span> <span data-ttu-id="b637c-195">Se for NULL ou vazio, NextPage será definido como 0, o que encerrará o loop Until.</span><span class="sxs-lookup"><span data-stu-id="b637c-195">If it is NULL, or empty, NextPage is set to 0, which ends the Until loop.</span></span> <span data-ttu-id="b637c-196">Se contiver uma URL, a variável AvaibleUri será atualizada para essa URL.</span><span class="sxs-lookup"><span data-stu-id="b637c-196">If it contains a URL, the AvaibleUri variable is updated to that URL.</span></span> <span data-ttu-id="b637c-197">Dessa forma, a próxima execução do loop Until usará a próxima URL disponível, e não a URL inicial.</span><span class="sxs-lookup"><span data-stu-id="b637c-197">This way, the next run of the Until loop uses a next available URL, and not the starting URL.</span></span>

  </details>

> [!TIP]
> <span data-ttu-id="b637c-198">Você pode optar por usar uma *Função do Azure* para incluir esses logs. Em vez disso, se você fizer isso, as informações sobre como implantar estão [aqui](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20Data) ou [aqui](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20DataCSharp), dependendo de sua preferência.</span><span class="sxs-lookup"><span data-stu-id="b637c-198">You may choose to use an *Azure Function* to ingest those logs, instead, and if you do, the information on how to deploy is [here](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20Data), or [here](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20DataCSharp), depending on your preference.</span></span>

<span data-ttu-id="b637c-199">Com o conector (qualquer uma das opções acima selecionadas) em execução, você verá uma tabela personalizada chamada O365API_CL no espaço de trabalho do Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="b637c-199">With the connector (whichever of the options above you chose) running, you should see a custom table called O365API_CL in the Azure Sentinel workspace.</span></span> <span data-ttu-id="b637c-200">Isso armazenará os logs do Teams.</span><span class="sxs-lookup"><span data-stu-id="b637c-200">This will house your Teams logs.</span></span>

## <a name="step-3-use-sentinel-to-monitor-microsoft-teams"></a><span data-ttu-id="b637c-201">Etapa 3: usar o Sentinel para monitorar o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b637c-201">Step 3: Use Sentinel to monitor Microsoft Teams</span></span>

<span data-ttu-id="b637c-202">A identidade é um vetor de ataque importante a ser monitorado no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b637c-202">Identity is an important attack vector to monitor when it comes to Microsoft Teams.</span></span> <span data-ttu-id="b637c-203">Como o Azure AD (Azure Active Directory) é a base do diretório do Microsoft 365, incluindo o Teams, a coleta e a busca por ameaças nos logs do Azure AD em relação à autenticação serão úteis para capturar comportamentos suspeitos na identidade.</span><span class="sxs-lookup"><span data-stu-id="b637c-203">Because Azure Active Directory (Azure AD) is the underpinning of Microsoft 365's directory, including Teams, collecting and hunting for threats in Azure AD logs around authentication will be useful in capturing suspicious behaviour around identity.</span></span> <span data-ttu-id="b637c-204">Você pode usar o conector interno para extrair dados do Azure AD para o Azure Sentinel e usar essas consultas de [detecção](https://github.com/Azure/Azure-Sentinel/tree/master/Detections/SigninLogs) e [busca](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/SigninLogs) para procurar problemas.</span><span class="sxs-lookup"><span data-stu-id="b637c-204">You can use the built-in connector to pull Azure AD data into Azure Sentinel, and use these [detection](https://github.com/Azure/Azure-Sentinel/tree/master/Detections/SigninLogs) and [hunting](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/SigninLogs) queries to look for problems.</span></span>

<span data-ttu-id="b637c-205">Em relação a ataques específicos ao Microsoft Teams, ameaças a dados, por exemplo, o Azure Sentinel também tem meios para monitorar e localizá-los.</span><span class="sxs-lookup"><span data-stu-id="b637c-205">Regarding attacks specific to Microsoft Teams, threats to data, for example, Azure Sentinel also has means to monitor for them and hunt them down.</span></span>

### <a name="create-a-parser-for-your-data"></a><span data-ttu-id="b637c-206">Criar um analisador para seus dados</span><span class="sxs-lookup"><span data-stu-id="b637c-206">Create a parser for your data</span></span>

<span data-ttu-id="b637c-207">A primeira coisa a fazer para entender o grande conjunto de dados coletados é analisá-los.</span><span class="sxs-lookup"><span data-stu-id="b637c-207">The first thing to do in order to make sense of the large set of collected data is to give it meaning by parsing it.</span></span> <span data-ttu-id="b637c-208">Isso é feito com uma função KQL (Kusto Query Language) que facilita o uso dos dados.</span><span class="sxs-lookup"><span data-stu-id="b637c-208">This is done with a Kusto Query Language (KQL) Function that makes the data easier to use.</span></span>

> [!NOTE]
> <span data-ttu-id="b637c-209">As funções KQL são consultas salvas como um tipo de dados chamado de "função".</span><span class="sxs-lookup"><span data-stu-id="b637c-209">KQL functions are KQL queries saved as a data-type called 'function'.</span></span> <span data-ttu-id="b637c-210">As funções KQL têm um alias que pode ser inserido na caixa de consulta no Sentinel para executar a consulta novamente e de maneira mais rápida.</span><span class="sxs-lookup"><span data-stu-id="b637c-210">KQL functions have an alias that can be entered into the query box in Sentinel to quickly run the query again.</span></span> <span data-ttu-id="b637c-211">Para obter mais informações sobre as funções KQL e como criar uma função de analisador, leia [este artigo da Tech Community](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).</span><span class="sxs-lookup"><span data-stu-id="b637c-211">For more about KQL functions and how to build a parser function, read [this Tech Community article](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).</span></span>
 
 <span data-ttu-id="b637c-212">O analisador a seguir é um exemplo personalizável destinado a selecionar um subconjunto dos campos da API de Gerenciamento do Office 365 relevantes para o *Teams*.</span><span class="sxs-lookup"><span data-stu-id="b637c-212">The parser below is a customizable example aimed at selecting a subset of the Office 365 Management API fields relevant to *Teams*.</span></span> <span data-ttu-id="b637c-213">Há também um analisador sugerido no [GitHub](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt), mas o que está a seguir pode ser modificado para atender a diferentes necessidades e preferências.</span><span class="sxs-lookup"><span data-stu-id="b637c-213">There is also a suggested parser [GitHub](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt), but the parser below can be modified to fit different needs and preferences.</span></span>

```kusto
O365API_CL
| where Workload_s =~ "MicrosoftTeams"
| project TimeGenerated,
          Workload=Workload_s,
          Operation=Operation_s,
          TeamName=columnifexists('TeamName_s', ""),
          UserId=columnifexists('UserId_s', ""),
          AddOnName=columnifexists('AddOnName_s', AddOnGuid_g),
          Members=columnifexists('Members_s', ""),
          Settings=iif(Operation_s contains "Setting", pack("Name", columnifexists('Name_s', ""), "Old Value", columnifexists('OldValue_s', ""), "New Value", columnifexists('NewValue_s', "")),""),
          Details=pack("Id", columnifexists('Id_g', ""),  "OrganizationId", columnifexists('OrganizationId_g', ""), "UserType", columnifexists('UserType_d', ""), "UserKey", columnifexists('UserKey_g', ""), "TeamGuid", columnifexists('TeamGuid_s', "")) 
```
 <span data-ttu-id="b637c-214">Salve o analisador como uma função KQL, com um alias de TeamsData.</span><span class="sxs-lookup"><span data-stu-id="b637c-214">Save the parser as a KQL function, with an alias of TeamsData.</span></span> <span data-ttu-id="b637c-215">Ela será usada para as consultas a serem acompanhadas.</span><span class="sxs-lookup"><span data-stu-id="b637c-215">It will be used for the queries to follow.</span></span> <span data-ttu-id="b637c-216">É possível encontrar detalhes sobre a configuração e o uso de uma função KQL como analisador neste [artigo da Tech Community](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).</span><span class="sxs-lookup"><span data-stu-id="b637c-216">Details on configuring and using a KQL function as a parser can be found in this [Tech Community article](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).</span></span>

## <a name="helfpul-hunting-kql-queries"></a><span data-ttu-id="b637c-217">Consultas de grande ajuda de busca KQL</span><span class="sxs-lookup"><span data-stu-id="b637c-217">Helfpul hunting KQL queries</span></span>

<span data-ttu-id="b637c-218">Use essas consultas para se familiarizar com os dados e o ambiente do Teams.</span><span class="sxs-lookup"><span data-stu-id="b637c-218">Use these queries to familiarize yourself with your Teams data and Teams environment.</span></span> <span data-ttu-id="b637c-219">Saber como o ambiente deve parecer e se comportar é um primeiro passo importante para reconhecer atividades suspeitas.</span><span class="sxs-lookup"><span data-stu-id="b637c-219">Knowing how the environment should look and behave is a good first step in recognizing suspicious activity.</span></span> <span data-ttu-id="b637c-220">A partir daí, você pode se dedicar na busca por ameaças.</span><span class="sxs-lookup"><span data-stu-id="b637c-220">From there, you can branch out into threat hunting.</span></span>

#### <a name="federated-external-users-query"></a><span data-ttu-id="b637c-221">Consulta de usuários externos federados</span><span class="sxs-lookup"><span data-stu-id="b637c-221">Federated external users query</span></span>

<span data-ttu-id="b637c-222">Obtenha a lista de sites do Teams que têm usuários externos federados.</span><span class="sxs-lookup"><span data-stu-id="b637c-222">Get the list of Teams sites that have federated external users.</span></span> <span data-ttu-id="b637c-223">Esses usuários terão um sufixo de nome de domínio/UPN que *não* pertence à organização.</span><span class="sxs-lookup"><span data-stu-id="b637c-223">These users will have a domain name / UPN suffix that *isn't* owned by your organization.</span></span> <span data-ttu-id="b637c-224">Nesta consulta de exemplo, a organização é proprietária da contoso.com.</span><span class="sxs-lookup"><span data-stu-id="b637c-224">In this example query, the organization owns contoso.com.</span></span>

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| extend UPN = tostring(parse_json(Members)[0].Upn)
| where UPN !endswith "contoso.com"
| where parse_json(Members)[0].Role == 3
| project TeamName, Operation, UserId, Members, UPN
```

> [!TIP]
> <span data-ttu-id="b637c-225">Para saber mais sobre os tipos de acesso externo e de convidado no Teams, confira [este artigo](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations) ou a seção *Tipos de participantes* no [Guia de segurança do Teams](https://docs.microsoft.com/microsoftteams/teams-security-guide).</span><span class="sxs-lookup"><span data-stu-id="b637c-225">To learn more about External and Guest access types in Teams see [this article](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations), or the *Participant Types* section in the [Teams Security Guide](https://docs.microsoft.com/microsoftteams/teams-security-guide).</span></span>

#### <a name="who-recently-joined--whose-role-changed"></a><span data-ttu-id="b637c-226">Quem entrou recentemente/Quem mudou de função</span><span class="sxs-lookup"><span data-stu-id="b637c-226">Who recently joined / Whose role changed</span></span>

<span data-ttu-id="b637c-227">Consulte um usuário específico para verificar se ele foi adicionado a um canal do Teams nos últimos sete dias ou dentro de uma semana:</span><span class="sxs-lookup"><span data-stu-id="b637c-227">Query a specific user to check if they were added to a Teams channel in the last 7 days, or within a week:</span></span>

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where Members contains "UserName"
```

<span data-ttu-id="b637c-228">A função de um usuário foi alterada para uma equipe nos últimos sete dias:</span><span class="sxs-lookup"><span data-stu-id="b637c-228">Was a user's role changed for a Team in the last 7 days:</span></span>

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberRoleChanged"
| where Members contains "Role" and Members contains "1"
```

#### <a name="external-users-from-unknown-or-new-organizations"></a><span data-ttu-id="b637c-229">Usuários externos de organizações novas ou desconhecidas</span><span class="sxs-lookup"><span data-stu-id="b637c-229">External users from unknown or new organizations</span></span>

<span data-ttu-id="b637c-230">No Teams, é possível adicionar usuários externos ao ambiente ou canais.</span><span class="sxs-lookup"><span data-stu-id="b637c-230">In Teams, you can add external users to your environment or channels.</span></span> <span data-ttu-id="b637c-231">As organizações geralmente têm um número limitado de parcerias importantes e adicionam usuários entre esses parceiros.</span><span class="sxs-lookup"><span data-stu-id="b637c-231">Organizations often have a limited number of key partnerships and add users from among these partners.</span></span> <span data-ttu-id="b637c-232">Este KQL verifica os usuários externos adicionados às equipes provenientes de organizações que não foram vistas ou adicionadas antes.</span><span class="sxs-lookup"><span data-stu-id="b637c-232">This KQL looks at external users added to teams who come from organizations that haven't been seen or added before.</span></span>

```kusto
// If you have more than 14 days worth of Teams data change this value 
let data_date = 14d; 
// If you want to look at users further back than the last day change this value 
let lookback_data = 1d; 
let known_orgs = ( 
TeamsData  
| where TimeGenerated > ago(data_date) 
| where Operation =~ "MemberAdded" or Operation =~ "TeamsSessionStarted" 
// Extract the correct UPN and parse our external organization domain 
| extend UPN = iif(Operation == "MemberAdded", tostring(parse_json(Members)[0].UPN), UserId) 
| extend Organization = tostring(split(split(UPN, "_")[1], "#")[0]) 
| where isnotempty(Organization) 
| summarize by Organization); 
TeamsData  
| where TimeGenerated > ago(lookback_data) 
| where Operation =~ "MemberAdded" 
| extend UPN = tostring(parse_json(Members)[0].UPN) 
| extend Organization = tostring(split(split(UPN, "_")[1], "#")[0]) 
| where isnotempty(Organization) 
| where Organization !in (known_orgs) 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeGenerated, AccountCustomEntity = UPN 
```

#### <a name="external-users-who-were-added-and-then-removed"></a><span data-ttu-id="b637c-233">Usuários externos que foram adicionados e removidos</span><span class="sxs-lookup"><span data-stu-id="b637c-233">External users who were added and then removed</span></span>

<span data-ttu-id="b637c-234">Os invasores com algum nível de acesso existente podem adicionar uma nova conta externa às equipes para acessar e retirar dados.</span><span class="sxs-lookup"><span data-stu-id="b637c-234">Attackers with some level of existing access may add a new external account to Teams to access and exfiltrate data.</span></span> <span data-ttu-id="b637c-235">Eles também podem remover rapidamente esse usuário para ocultar o acesso realizado.</span><span class="sxs-lookup"><span data-stu-id="b637c-235">They may also quickly remove that user to hide that they made access.</span></span> <span data-ttu-id="b637c-236">Essa consulta procura por contas externas que são adicionadas às equipes e removidas rapidamente para ajudar a identificar comportamentos suspeitos.</span><span class="sxs-lookup"><span data-stu-id="b637c-236">This query hunts for external accounts that are added to Teams and swiftly removed to help identify suspicious behavior.</span></span>

```kusto
// If you want to look at user added further than 7 days ago adjust this value 
let time_ago = 7d; 
// If you want to change the timeframe of how quickly accounts need to be added and removed change this value 
let time_delta = 1h; 
TeamsData  
| where TimeGenerated > ago(time_ago) 
| where Operation =~ "MemberAdded" 
| extend UPN = tostring(parse_json(Members)[0].UPN) 
| project TimeAdded=TimeGenerated, Operation, UPN, UserWhoAdded = UserId, TeamName, TeamGuid = tostring(Details.TeamGuid) 
| join ( 
TeamsData  
| where TimeGenerated > ago(time_ago) 
| where Operation =~ "MemberRemoved" 
| extend UPN = tostring(parse_json(Members)[0].UPN) 
| project TimeDeleted=TimeGenerated, Operation, UPN, UserWhoDeleted = UserId, TeamName, TeamGuid = tostring(Details.TeamGuid)) on UPN, TeamGuid 
| where TimeDeleted < (TimeAdded + time_delta) 
| project TimeAdded, TimeDeleted, UPN, UserWhoAdded, UserWhoDeleted, TeamName, TeamGuid 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeAdded, AccountCustomEntity = UPN 
```

#### <a name="new-bot-or-application-added"></a><span data-ttu-id="b637c-237">Novo bot ou aplicativo adicionado</span><span class="sxs-lookup"><span data-stu-id="b637c-237">New bot or application added</span></span>

<span data-ttu-id="b637c-238">O Teams têm a capacidade de incluir aplicativos ou bots em uma equipe para estender o conjunto de recursos.</span><span class="sxs-lookup"><span data-stu-id="b637c-238">Teams has the ability to include apps or bots in a Team to extend the feature set.</span></span> <span data-ttu-id="b637c-239">Isso inclui aplicativos e bots personalizados.</span><span class="sxs-lookup"><span data-stu-id="b637c-239">This includes custom apps and bots.</span></span> <span data-ttu-id="b637c-240">Em alguns casos, um aplicativo ou bot poderia ser usado para estabelecer persistência no Teams sem precisar de uma conta de usuário, além de acessar arquivos e outros dados.</span><span class="sxs-lookup"><span data-stu-id="b637c-240">In some cases, an app or bot could be used to establish persistence in Teams without needing a user account, as well as access files and other data.</span></span> <span data-ttu-id="b637c-241">Esta consulta busca por novos aplicativos ou bots para o Teams.</span><span class="sxs-lookup"><span data-stu-id="b637c-241">This query hunts for apps or bots that are new to Teams.</span></span>

```kusto
// If you have more than 14 days worth of Teams data change this value 
let data_date = 14d; 
let historical_bots = ( 
TeamsData 
| where TimeGenerated > ago(data_date) 
| where isnotempty(AddOnName) 
| project AddOnName); 
TeamsData 
| where TimeGenerated > ago(1d) 
// Look for add-ins we have never seen before 
| where AddOnName in (historical_bots) 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeGenerated, AccountCustomEntity = UserId 
```

#### <a name="user-accounts-who-are-owners-of-large-numbers-of-teams"></a><span data-ttu-id="b637c-242">Contas de usuário proprietárias de um grande número de equipes</span><span class="sxs-lookup"><span data-stu-id="b637c-242">User accounts who are Owners of large numbers of Teams</span></span>

<span data-ttu-id="b637c-243">Os invasores que desejarem aumentar seus privilégios podem atribuir a si mesmos privilégios de proprietário de um grande número de equipes, quando, geralmente, os usuários criam e têm um pequeno número de equipes em torno de tópicos específicos.</span><span class="sxs-lookup"><span data-stu-id="b637c-243">Attackers looking to elevate their privileges may assign themselves Owner privileges of a large number of diverse Teams, when, usually, users create and own a small number of Teams around specific topics.</span></span> <span data-ttu-id="b637c-244">Esta consulta KQL procura por comportamentos suspeitos.</span><span class="sxs-lookup"><span data-stu-id="b637c-244">This KQL query looks for suspicious behaviour.</span></span>

```kusto
// Adjust this value to change how many teams a user is made owner of before detecting 
let max_owner_count = 3; 
// Change this value to adjust how larger timeframe the query is run over. 
let time_window = 1d; 
let high_owner_count = (TeamsData 
| where TimeGenerated > ago(time_window) 
| where Operation =~ "MemberRoleChanged" 
| extend Member = tostring(parse_json(Members)[0].UPN)  
| extend NewRole = toint(parse_json(Members)[0].Role)  
| where NewRole == 2 
| summarize dcount(TeamName) by Member 
| where dcount_TeamName > max_owner_count 
| project Member); 
TeamsData 
| where TimeGenerated > ago(time_window) 
| where Operation =~ "MemberRoleChanged" 
| extend Member = tostring(parse_json(Members)[0].UPN)  
| extend NewRole = toint(parse_json(Members)[0].Role)  
| where NewRole == 2 
| where Member in (high_owner_count) 
| extend TeamGuid = tostring(Details.TeamGuid) 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeGenerated, AccountCustomEntity = Member 
```

#### <a name="many-team-deletions-by-a-single-user"></a><span data-ttu-id="b637c-245">Várias exclusões da equipe por um único usuário</span><span class="sxs-lookup"><span data-stu-id="b637c-245">Many Team deletions by a single user</span></span>

<span data-ttu-id="b637c-246">Os invasores podem provocar interrupções, e comprometer projetos e dados ao excluir várias equipes.</span><span class="sxs-lookup"><span data-stu-id="b637c-246">Attackers can cause disruptions and jeopardize projects and data by deleting multiple teams.</span></span> <span data-ttu-id="b637c-247">Como as equipes geralmente são excluídas por proprietários individuais, uma exclusão central de várias equipes pode ser um sinal de problemas.</span><span class="sxs-lookup"><span data-stu-id="b637c-247">Because teams are generally deleted by individual Owners, a central deletion of many teams can be a sign of trouble.</span></span> <span data-ttu-id="b637c-248">Esse KQL procura por usuários únicos que excluem várias equipes.</span><span class="sxs-lookup"><span data-stu-id="b637c-248">This KQL looks for single users who delete multiple teams.</span></span>

```kusto
 // Adjust this value to change how many Teams should be deleted before including
 let max_delete = 3;
 // Adjust this value to change the timewindow the query runs over
 let time_window = 1d;
 let deleting_users = (
 TeamsData 
 | where TimeGenerated > ago(time_window)
 | where Operation =~ "TeamDeleted"
 | summarize count() by UserId
 | where count_ > max_delete
 | project UserId);
 TeamsData
 | where TimeGenerated > ago(time_window)
 | where Operation =~ "TeamDeleted"
 | where UserId in (deleting_users)
 | extend TeamGuid = tostring(Details.TeamGuid)
 | project-away AddOnName, Members, Settings
 // Uncomment the following line to map query entities is you plan to use this as a detection query
 //| extend timestamp = TimeGenerated, AccountCustomEntity = UserId
```

#### <a name="expanding-your-thread-hunting-opportunities"></a><span data-ttu-id="b637c-249">Expandir oportunidades de busca por thread</span><span class="sxs-lookup"><span data-stu-id="b637c-249">Expanding your thread hunting opportunities</span></span>

<span data-ttu-id="b637c-250">Você pode expandir suas buscas combinando consultas de recursos como o Azure AD (Azure Active Directory) ou outras cargas de trabalho do Office 365 com as consultas do Teams.</span><span class="sxs-lookup"><span data-stu-id="b637c-250">You can expand your hunting by combining queries from resources like Azure Active Directory (Azure AD), or other Office 365 workloads with your Teams queries.</span></span> <span data-ttu-id="b637c-251">Um exemplo é combinar a detecção de padrões suspeitos no Azure AD SigninLogs e usar essas informações ao procurar por proprietários de equipes.</span><span class="sxs-lookup"><span data-stu-id="b637c-251">One example is combining detection of suspicious patterns in Azure AD SigninLogs, and using that information while hunting for Team Owners.</span></span>

```kusto
let timeRange = 1d;
let lookBack = 7d;
let threshold_Failed = 5;
let threshold_FailedwithSingleIP = 20;
let threshold_IPAddressCount = 2;
let isGUID = "[0-9a-z]{8}-[0-9a-z]{4}-[0-9a-z]{4}-[0-9a-z]{4}-[0-9a-z]{12}";
let azPortalSignins = SigninLogs
| where TimeGenerated >= ago(timeRange)
// Azure Portal only and exclude non-failure Result Types
| where AppDisplayName has "Azure Portal" and ResultType !in ("0", "50125", "50140")
// Tagging identities not resolved to friendly names
| extend Unresolved = iff(Identity matches regex isGUID, true, false);
// Lookup up resolved identities from last 7 days
let identityLookup = SigninLogs
| where TimeGenerated >= ago(lookBack)
| where not(Identity matches regex isGUID)
| summarize by UserId, lu_UserDisplayName = UserDisplayName, lu_UserPrincipalName = UserPrincipalName;
// Join resolved names to unresolved list from portal signins
let unresolvedNames = azPortalSignins | where Unresolved == true | join kind= inner (
   identityLookup ) on UserId
| extend UserDisplayName = lu_UserDisplayName, UserPrincipalName = lu_UserPrincipalName
| project-away lu_UserDisplayName, lu_UserPrincipalName;
// Join Signins that had resolved names with list of unresolved that now have a resolved name
let u_azPortalSignins = azPortalSignins | where Unresolved == false | union unresolvedNames;
let failed_signins = (u_azPortalSignins
| extend Status = strcat(ResultType, ": ", ResultDescription), OS = tostring(DeviceDetail.operatingSystem), Browser = tostring(DeviceDetail.browser)
| extend FullLocation = strcat(Location,'|', LocationDetails.state, '|', LocationDetails.city)
| summarize TimeGenerated = makelist(TimeGenerated), Status = makelist(Status), IPAddresses = makelist(IPAddress), IPAddressCount = dcount(IPAddress), FailedLogonCount = count()
by UserPrincipalName, UserId, UserDisplayName, AppDisplayName, Browser, OS, FullLocation
| mvexpand TimeGenerated, IPAddresses, Status
| extend TimeGenerated = todatetime(tostring(TimeGenerated)), IPAddress = tostring(IPAddresses), Status = tostring(Status)
| project-away IPAddresses
| summarize StartTime = min(TimeGenerated), EndTime = max(TimeGenerated) by UserPrincipalName, UserId, UserDisplayName, Status, FailedLogonCount, IPAddress, IPAddressCount, AppDisplayName, Browser, OS, FullLocation
| where (IPAddressCount >= threshold_IPAddressCount and FailedLogonCount >= threshold_Failed) or FailedLogonCount >= threshold_FailedwithSingleIP
| project UserPrincipalName);
TeamsData
| where TimeGenerated > ago(time_window)
| where Operation =~ "MemberRoleChanged"
| extend Member = tostring(parse_json(Members)[0].UPN) 
| extend NewRole = toint(parse_json(Members)[0].Role) 
| where NewRole == 2
| where Member in (failed_signins)
| extend TeamGuid = tostring(Details.TeamGuid)
```

<span data-ttu-id="b637c-252">Além disso, você pode fazer as detecções específicas do SigninLogs para o Teams adicionando um filtro apenas para entradas com base no Teams usando:</span><span class="sxs-lookup"><span data-stu-id="b637c-252">Also, you can make the SigninLogs detections specific to Teams by adding a filter for only Teams-based sign-ins by using:</span></span>

```kusto
| where AppDisplayName startswith "Microsoft Teams"
```

<span data-ttu-id="b637c-253">Para ajudar a explicar melhor o uso do `where AppDisplayName starts with "Microsoft Teams"`, o KQL abaixo demonstra um logon bem-sucedido de um endereço IP com falha de um endereço IP diferente, mas com escopo definido apenas para as entradas do Teams:</span><span class="sxs-lookup"><span data-stu-id="b637c-253">To help explain using `where AppDisplayName starts with "Microsoft Teams"` further, the KQL below demonstrates a successful logon from one IP address with failure from a different IP address, but scoped only to Teams sign-ins:</span></span>

```kusto
let timeFrame = 1d;
let logonDiff = 10m;
SigninLogs 
  | where TimeGenerated >= ago(timeFrame) 
  | where ResultType == "0" 
  | where AppDisplayName startswith "Microsoft Teams"
  | project SuccessLogonTime = TimeGenerated, UserPrincipalName, SuccessIPAddress = IPAddress, AppDisplayName, SuccessIPBlock = strcat(split(IPAddress, ".")[0], ".", split(IPAddress, ".")[1])
  | join kind= inner (
      SigninLogs 
      | where TimeGenerated >= ago(timeFrame) 
      | where ResultType !in ("0", "50140") 
      | where ResultDescription !~ "Other"  
      | where AppDisplayName startswith "Microsoft Teams"
      | project FailedLogonTime = TimeGenerated, UserPrincipalName, FailedIPAddress = IPAddress, AppDisplayName, ResultType, ResultDescription
  ) on UserPrincipalName, AppDisplayName 
  | where SuccessLogonTime < FailedLogonTime and FailedLogonTime - SuccessLogonTime <= logonDiff and FailedIPAddress !startswith SuccessIPBlock
  | summarize FailedLogonTime = max(FailedLogonTime), SuccessLogonTime = max(SuccessLogonTime) by UserPrincipalName, SuccessIPAddress, AppDisplayName, FailedIPAddress, ResultType, ResultDescription 
  | extend timestamp = SuccessLogonTime, AccountCustomEntity = UserPrincipalName, IPCustomEntity = SuccessIPAddress
```

## <a name="important-information-and-updates"></a><span data-ttu-id="b637c-254">Atualizações e informações importantes</span><span class="sxs-lookup"><span data-stu-id="b637c-254">Important information and updates</span></span>

<span data-ttu-id="b637c-255">**Obrigado pela sua colaboração de conteúdo, Pete Bryan, Nicholas DiCola e Matthew Lowe.**</span><span class="sxs-lookup"><span data-stu-id="b637c-255">**Thank you for content collaboration, Pete Bryan, Nicholas DiCola, and Matthew Lowe.**</span></span> <span data-ttu-id="b637c-256">Pete Bryan e as pessoas com quem ele colabora continuarão desenvolvendo consultas de detecção e buscas por equipes, portanto, fique em contato com este repositório do [GitHub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) para obter atualizações.</span><span class="sxs-lookup"><span data-stu-id="b637c-256">Pete Bryan and the people he collaborates with will continue to develop detection and hunting queries for Teams, so keep in touch with this [GitHub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) repository for updates.</span></span>  <span data-ttu-id="b637c-257">Monitore as atualizações para o [analisador](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) e o [aplicativo lógico](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) usados neste artigo.</span><span class="sxs-lookup"><span data-stu-id="b637c-257">Monitor for updates to the [parser](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) and [logic app](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) used in this article.</span></span> <span data-ttu-id="b637c-258">Você também pode participar e contribuir com a [comunidade do Azure Sentinel](https://github.com/Azure/Azure-Sentinel/wiki).</span><span class="sxs-lookup"><span data-stu-id="b637c-258">You can also join and contribute to the [Azure Sentinel community](https://github.com/Azure/Azure-Sentinel/wiki).</span></span> <span data-ttu-id="b637c-259">Obrigado!</span><span class="sxs-lookup"><span data-stu-id="b637c-259">Thank you!</span></span> <span data-ttu-id="b637c-260">Boa busca.</span><span class="sxs-lookup"><span data-stu-id="b637c-260">Happy hunting.</span></span>

[<span data-ttu-id="b637c-261">Registrar seu aplicativo no Azure AD</span><span class="sxs-lookup"><span data-stu-id="b637c-261">Registering your application in Azure AD</span></span>](https://docs.microsoft.com/skype-sdk/ucwa/registeringyourapplicationinazuread%C2%A0%20%20%C2%A0)

[<span data-ttu-id="b637c-262">Ativar ou desativar a pesquisa de log de auditoria</span><span class="sxs-lookup"><span data-stu-id="b637c-262">Turn audit log search on or off</span></span>](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%C2%A0)

[<span data-ttu-id="b637c-263">O que é o Azure Sentinel?</span><span class="sxs-lookup"><span data-stu-id="b637c-263">What is Azure Sentinel</span></span>](https://docs.microsoft.com/azure/sentinel/overview)