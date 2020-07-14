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
# <a name="azure-sentinel-and-microsoft-teams"></a>Azure Sentinel e Microsoft Teams

O Teams desempenha um papel central na comunicação e no compartilhamento de dados no Microsoft 365 Cloud. Como o serviço do Teams aborda tantas tecnologias subjacentes na nuvem, ele pode se beneficiar das análises humanas e automatizadas, não apenas no que diz respeito à *busca em logs*, mas também no *monitoramento em tempo real das reuniões*. O Azure Sentinel oferece aos administradores essas soluções.

> [!NOTE]
> Precisa de uma atualização no Azure Sentinel? [Este artigo](https://docs.microsoft.com/azure/sentinel/overview) é ideal para isso.

## <a name="sentinel-and-microsoft-teams-activity-logs"></a>Logs de atividades do Sentinel e do Microsoft Teams

Este artigo foca na coleta de logs de atividades do Teams no Azure Sentinel. Além de permitir que os administradores coloquem o gerenciamento de segurança em um painel de vidro (incluindo dispositivos selecionados de terceiros, Proteção contra Ameaças da Microsoft e outras cargas de trabalho do Microsoft 365), as pastas de trabalho do Sentinel e as runbooks podem tornar o monitoramento de segurança sistemático. Um primeiro passo importante nesse processo é coletar os logs necessários para análise.

> [!NOTE]
> Mais de uma assinatura do Microsoft 365 pode ser apresentada na mesma instância do Azure Sentinel. Isso permitirá o [monitoramento em tempo real](https://docs.microsoft.com/azure/sentinel/livestream) e a busca por ameaças nos arquivos de logs históricos. Os administradores poderão buscar usando [consultas entre recursos](https://docs.microsoft.com/azure/azure-monitor/log-query/cross-workspace-query), que estão em um único grupo de recursos, entre grupos de recursos ou em outra assinatura.

## <a name="step-1-collect-teams-logs"></a>Etapa 1: coletar registros do Teams

Esta seção tem três partes:

1. Habilitar logs de auditoria no **Microsoft 365** (M365).
2. Registrar um aplicativo no **Microsoft Azure** para permitir a autenticação e a autorização para a coleta de logs.
3. Registrar a assinatura da API que permitirá a coleta de logs pela API do M365 pelo **PowerShell**.

### <a name="enable-audit-logs-in-m365"></a>Habilitar logs de auditoria no M365

Como o Teams registra as atividades de logs no M365, os logs de auditoria não são coletados por padrão. Ative esse recurso por meio [destas etapas](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%C2%A0). Os dados do Teams são coletados na auditoria do M365 em *Audit.General*.

### <a name="register-an-app-in-microsoft-azure-for-log-collection"></a>Registrar um aplicativo no Microsoft Azure para a coleção de logs

> [!TIP]
> Antes de começar, você precisará registrar a **ID do aplicativo/ID do cliente** e a **ID do locatário** para uso posterior. Certifique-se de capturá-los enquanto segue as etapas de registro do aplicativo a seguir. As duas IDs serão exibidas.
>- Após a criação do aplicativo, clique em Registro do aplicativo na barra lateral de início rápido > Localize o nome de exibição do seu novo aplicativo > copie a ID do aplicativo (cliente).
>- Clique em Visão geral na barra lateral de início rápido, copie a ID do diretório (locatário).

Autentique e autorize um aplicativo do Azure AD (Azure Active Directory) para coletar dados de log da API.

1. Navegue até a lâmina *Azure AD*, no portal do Azure.
2. Clique em *Registros de aplicativos* na barra de início rápido.
3. Selecione *Novo registro*.
4. Nomeie o aplicativo de coleta de log do Teams e clique em *Registrar*.
5. Clique neste caminho: *Permissões da API* > *Adicionar uma permissão* > *APIs de gerenciamento do Office 365* > *Permissões de aplicativo*.
6. Expanda Feed de atividades e marque *ActivityFeed.Read*.
7. Escolha a opção *Conceder consentimento de administração* aqui. Clique em Sim quando solicitado.
8. Clique em *Certificados e Segredos* na barra lateral> botão *Novo segredo do cliente*.
9. Na janela Novo segredo do cliente, digite uma descrição para o novo Segredo do Cliente, escolha “Nunca” para Expiração e clique em *Adicionar*.

> [!IMPORTANT]
> É **essencial** copiar o novo segredo do cliente em uma entrada do gerenciador de senhas que passa pelo nome do aplicativo recém-criado. Não será possível voltar a examinar esse segredo após o fechamento da lâmina do Azure (*lâmina* sendo o termo do Azure para janela).

### <a name="register-the-api-with-powershell-to-collect-teams-logs"></a>Registrar a API no PowerShell para coletar logs do Teams

A etapa final da instalação é coletar e registrar a assinatura da API para poder coletar os dados de log. Isso é feito pelas chamadas do PowerShell REST para a API de atividade de gerenciamento do M365.

Esteja pronto para fornecer a **ID do aplicativo (cliente)**, o novo **Segredo do cliente**, seu **domínio de URL para o M365** e os valores de **ID do diretório (locatário)** no cmdlet do PowerShell a seguir.

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

## <a name="step-2-deploy-a-sentinel-playbook-to-ingest-the-teams-logs"></a>Etapa 2: implantar um guia estratégico do Sentinel para incluir os logs do Teams

Os guias estratégicos do Azure Sentinel (também chamados de aplicativos lógicos) permitirão que o Azure inclua os dados coletados do Teams. O aplicativo lógico consulta o Office 365 para localizar os dados de auditoria que ele grava no espaço de trabalho do Azure Sentinel.

Use [este](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) modelo ARM para implantar o guia estratégico do Sentinel.

Coisas para lembrar:

1. Será necessário percorrer o modelo ARM e substituir determinados valores pelos apropriados ao seu ambiente.
2. Será necessário reservar um tempo entre a inclusão de logs e a observação dos resultados no Azure Sentinel.

   Aguarde de 5 a 10 minutos, entendendo que se não houver dados nos últimos 5 minutos, você receberá uma mensagem de erro. Verifique os logs de auditoria e lembre-se de que, como as informações do Teams estão nos eventos Audit.General, que coletam mais que os logs do Teams, os resultados devem aparecer dentro de 5 a 10 minutos nos sistemas em uso. Se estiver usando um ambiente de texto, certifique-se de usar o Teams para gerar o registro em log.

![Gráfico que mostra as classes de aplicativos lógicos.](media/tracyp-teams-sentinel-logic-app.png#thumbnail)

 <p><details><summary> Explicação das ações no gráfico: 
  </summary>

  • A recorrência é o Gatilho do Aplicativo Lógico que informa ao fluxo de trabalho que seja executado de hora em hora.
  <p>
• A ação Hora Atual é muito básica e só tem a hora atual.
  <p>
• A inicialização da Variável cria uma variável chamada NextPage e a define como 1. Isso será usado mais tarde para lidar com a paginação da API do O365.
  <p>
• A inicialização da Variável 2 cria uma variável vazia chamada Start Time.
  <p>
• Executar consulta e listar resultados é uma ação do Azure Monitor que consultará o espaço de trabalho quanto ao último log do O365 inserido no Aplicativo Lógico.
  <p>
• A condição 4 é usada para verificar se a ação de executar consulta e listar resultados retornou dados. Isso é feito para verificar se é a primeira vez que o aplicativo lógico foi usado. Se nenhum dado for retornado, a variável StartTime será definida como Agora – 24 horas. Se os dados forem retornados, a StartTime será definida como o último registro TimeGenerated. Isso é feito para que a consulta possa obter dados da última entrada até agora na pesquisa em relação à API do O365, ou nas últimas 24 horas se esta for a primeira execução.
  <p>
• A inicialização da Variável 3 cria uma variável chamada AvailableUri. Esta é uma cadeira de caracteres com a URL criada usando StartTime e CurrentTime como horário de início e de término, respectivamente.
  <p>
• A condição Until é um loop que permite que o aplicativo lógico continue pesquisando a API para ver se há mais dados (paginação). O loop continuará enquanto a variável NextPage for 1. Posteriormente, essa variável será atualizada se não houver mais páginas pendentes de recuperação.
  <p>
• Dentro do loop Until, a primeira etapa HTTP se conecta ao AvailableURI. Esse URI retorna uma lista dos conteúdos disponíveis e os URIS de cada conteúdo. Há mais informações sobre como isso funciona neste URL: https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.
  <p>
• Em seguida, uma verificação será executada para garantir que os dados sejam retornados. A Condição verificará se o tamanho do corpo é 0. Nesse caso, não há dados para gravar no Análise de Logs. Se o valor for maior do que 0, há dados a processar.
  <p>
• Se dados forem detectados, será necessário reprocessá-los. Analisar o Parse define um esquema dos dados retornados. Isso permite que aplicativos lógicos usem os dados analisados como conteúdo dinâmico nas etapas posteriores.
  <p>
• Como a lista retornada de dados disponíveis é uma Matriz, uma ação For Each é usada para percorrer a lista de conteúdo disponível.
  <p>
• Em seguida, deve-se capturar o conteúdo.  O HTTP é usado novamente para obter o contentUri (uma propriedade dinâmica criada a partir da Análise JSON), que é a URL dos dados a serem recuperados.
  <p>
• A Análise JSON também é usada para analisar os dados retornados. É possível encontrar alguns exemplos de conteúdo nesta URL: https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.
  <p>
• Os dados retornados também são uma matriz. Um loop For Each também pode ser usado aqui. Nesse loop, o fluxo de trabalho pega o item atual dos dados e usa a ação Send Data para gravar os dados na Análise de Logs.
  <p>
• Como pode haver várias páginas de conteúdo disponível, uma condição verificará se o NextPageUri não é NULL. Se for NULL ou vazio, NextPage será definido como 0, o que encerrará o loop Until. Se contiver uma URL, a variável AvaibleUri será atualizada para essa URL. Dessa forma, a próxima execução do loop Until usará a próxima URL disponível, e não a URL inicial.

  </details>

> [!TIP]
> Você pode optar por usar uma *Função do Azure* para incluir esses logs. Em vez disso, se você fizer isso, as informações sobre como implantar estão [aqui](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20Data) ou [aqui](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20DataCSharp), dependendo de sua preferência.

Com o conector (qualquer uma das opções acima selecionadas) em execução, você verá uma tabela personalizada chamada O365API_CL no espaço de trabalho do Azure Sentinel. Isso armazenará os logs do Teams.

## <a name="step-3-use-sentinel-to-monitor-microsoft-teams"></a>Etapa 3: usar o Sentinel para monitorar o Microsoft Teams

A identidade é um vetor de ataque importante a ser monitorado no Microsoft Teams. Como o Azure AD (Azure Active Directory) é a base do diretório do Microsoft 365, incluindo o Teams, a coleta e a busca por ameaças nos logs do Azure AD em relação à autenticação serão úteis para capturar comportamentos suspeitos na identidade. Você pode usar o conector interno para extrair dados do Azure AD para o Azure Sentinel e usar essas consultas de [detecção](https://github.com/Azure/Azure-Sentinel/tree/master/Detections/SigninLogs) e [busca](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/SigninLogs) para procurar problemas.

Em relação a ataques específicos ao Microsoft Teams, ameaças a dados, por exemplo, o Azure Sentinel também tem meios para monitorar e localizá-los.

### <a name="create-a-parser-for-your-data"></a>Criar um analisador para seus dados

A primeira coisa a fazer para entender o grande conjunto de dados coletados é analisá-los. Isso é feito com uma função KQL (Kusto Query Language) que facilita o uso dos dados.

> [!NOTE]
> As funções KQL são consultas salvas como um tipo de dados chamado de "função". As funções KQL têm um alias que pode ser inserido na caixa de consulta no Sentinel para executar a consulta novamente e de maneira mais rápida. Para obter mais informações sobre as funções KQL e como criar uma função de analisador, leia [este artigo da Tech Community](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).
 
 O analisador a seguir é um exemplo personalizável destinado a selecionar um subconjunto dos campos da API de Gerenciamento do Office 365 relevantes para o *Teams*. Há também um analisador sugerido no [GitHub](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt), mas o que está a seguir pode ser modificado para atender a diferentes necessidades e preferências.

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
 Salve o analisador como uma função KQL, com um alias de TeamsData. Ela será usada para as consultas a serem acompanhadas. É possível encontrar detalhes sobre a configuração e o uso de uma função KQL como analisador neste [artigo da Tech Community](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).

## <a name="helfpul-hunting-kql-queries"></a>Consultas de grande ajuda de busca KQL

Use essas consultas para se familiarizar com os dados e o ambiente do Teams. Saber como o ambiente deve parecer e se comportar é um primeiro passo importante para reconhecer atividades suspeitas. A partir daí, você pode se dedicar na busca por ameaças.

#### <a name="federated-external-users-query"></a>Consulta de usuários externos federados

Obtenha a lista de sites do Teams que têm usuários externos federados. Esses usuários terão um sufixo de nome de domínio/UPN que *não* pertence à organização. Nesta consulta de exemplo, a organização é proprietária da contoso.com.

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
> Para saber mais sobre os tipos de acesso externo e de convidado no Teams, confira [este artigo](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations) ou a seção *Tipos de participantes* no [Guia de segurança do Teams](https://docs.microsoft.com/microsoftteams/teams-security-guide).

#### <a name="who-recently-joined--whose-role-changed"></a>Quem entrou recentemente/Quem mudou de função

Consulte um usuário específico para verificar se ele foi adicionado a um canal do Teams nos últimos sete dias ou dentro de uma semana:

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where Members contains "UserName"
```

A função de um usuário foi alterada para uma equipe nos últimos sete dias:

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberRoleChanged"
| where Members contains "Role" and Members contains "1"
```

#### <a name="external-users-from-unknown-or-new-organizations"></a>Usuários externos de organizações novas ou desconhecidas

No Teams, é possível adicionar usuários externos ao ambiente ou canais. As organizações geralmente têm um número limitado de parcerias importantes e adicionam usuários entre esses parceiros. Este KQL verifica os usuários externos adicionados às equipes provenientes de organizações que não foram vistas ou adicionadas antes.

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

#### <a name="external-users-who-were-added-and-then-removed"></a>Usuários externos que foram adicionados e removidos

Os invasores com algum nível de acesso existente podem adicionar uma nova conta externa às equipes para acessar e retirar dados. Eles também podem remover rapidamente esse usuário para ocultar o acesso realizado. Essa consulta procura por contas externas que são adicionadas às equipes e removidas rapidamente para ajudar a identificar comportamentos suspeitos.

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

#### <a name="new-bot-or-application-added"></a>Novo bot ou aplicativo adicionado

O Teams têm a capacidade de incluir aplicativos ou bots em uma equipe para estender o conjunto de recursos. Isso inclui aplicativos e bots personalizados. Em alguns casos, um aplicativo ou bot poderia ser usado para estabelecer persistência no Teams sem precisar de uma conta de usuário, além de acessar arquivos e outros dados. Esta consulta busca por novos aplicativos ou bots para o Teams.

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

#### <a name="user-accounts-who-are-owners-of-large-numbers-of-teams"></a>Contas de usuário proprietárias de um grande número de equipes

Os invasores que desejarem aumentar seus privilégios podem atribuir a si mesmos privilégios de proprietário de um grande número de equipes, quando, geralmente, os usuários criam e têm um pequeno número de equipes em torno de tópicos específicos. Esta consulta KQL procura por comportamentos suspeitos.

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

#### <a name="many-team-deletions-by-a-single-user"></a>Várias exclusões da equipe por um único usuário

Os invasores podem provocar interrupções, e comprometer projetos e dados ao excluir várias equipes. Como as equipes geralmente são excluídas por proprietários individuais, uma exclusão central de várias equipes pode ser um sinal de problemas. Esse KQL procura por usuários únicos que excluem várias equipes.

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

#### <a name="expanding-your-thread-hunting-opportunities"></a>Expandir oportunidades de busca por thread

Você pode expandir suas buscas combinando consultas de recursos como o Azure AD (Azure Active Directory) ou outras cargas de trabalho do Office 365 com as consultas do Teams. Um exemplo é combinar a detecção de padrões suspeitos no Azure AD SigninLogs e usar essas informações ao procurar por proprietários de equipes.

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

Além disso, você pode fazer as detecções específicas do SigninLogs para o Teams adicionando um filtro apenas para entradas com base no Teams usando:

```kusto
| where AppDisplayName startswith "Microsoft Teams"
```

Para ajudar a explicar melhor o uso do `where AppDisplayName starts with "Microsoft Teams"`, o KQL abaixo demonstra um logon bem-sucedido de um endereço IP com falha de um endereço IP diferente, mas com escopo definido apenas para as entradas do Teams:

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

## <a name="important-information-and-updates"></a>Atualizações e informações importantes

**Obrigado pela sua colaboração de conteúdo, Pete Bryan, Nicholas DiCola e Matthew Lowe.** Pete Bryan e as pessoas com quem ele colabora continuarão desenvolvendo consultas de detecção e buscas por equipes, portanto, fique em contato com este repositório do [GitHub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) para obter atualizações.  Monitore as atualizações para o [analisador](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) e o [aplicativo lógico](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) usados neste artigo. Você também pode participar e contribuir com a [comunidade do Azure Sentinel](https://github.com/Azure/Azure-Sentinel/wiki). Obrigado! Boa busca.

[Registrar seu aplicativo no Azure AD](https://docs.microsoft.com/skype-sdk/ucwa/registeringyourapplicationinazuread%C2%A0%20%20%C2%A0)

[Ativar ou desativar a pesquisa de log de auditoria](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%C2%A0)

[O que é o Azure Sentinel?](https://docs.microsoft.com/azure/sentinel/overview)