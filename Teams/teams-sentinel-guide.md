---
title: Azure Sentinel e Microsoft Teams
author: MicrosoftHeidi
ms.author: tracyp
manager: dansimp
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Conselhos e aprendizados de segurança para administradores de TI sobre o uso do Sentinel para monitorar e buscar ameaças que possam surgir no Teams.
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
ms.openlocfilehash: c3b2c37f7f3731b34abb5337bf954250e0c3564d
ms.sourcegitcommit: 046b020cee8af00a1d0e5f5866f847d42e8ad9a5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51712763"
---
# <a name="azure-sentinel-and-microsoft-teams"></a><span data-ttu-id="2050d-103">Azure Sentinel e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2050d-103">Azure Sentinel and Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2050d-104">O Azure Sentinel agora tem um conector integrado.</span><span class="sxs-lookup"><span data-stu-id="2050d-104">Azure Sentinel now has an integrated connector.</span></span> <span data-ttu-id="2050d-105">Para obter mais informações, confira [Conectar logs do Office 365 ao Azure Sentinel](/azure/sentinel/connect-office-365).</span><span class="sxs-lookup"><span data-stu-id="2050d-105">For more information, see [Connect Office 365 Logs to Azure Sentinel](/azure/sentinel/connect-office-365).</span></span> <span data-ttu-id="2050d-106">Esta é a rota recomendada para coletar esses logs e substitui os métodos de coleta descritos abaixo.</span><span class="sxs-lookup"><span data-stu-id="2050d-106">This is the recommended route for collecting these logs and supersedes the collection methods described below.</span></span>

<span data-ttu-id="2050d-107">O Teams desempenha um papel central na comunicação e no compartilhamento de dados no Microsoft 365 Cloud.</span><span class="sxs-lookup"><span data-stu-id="2050d-107">Teams serves a central role in communication and data-sharing in the Microsoft 365 Cloud.</span></span> <span data-ttu-id="2050d-108">Como o Teams tangencia tantas tecnologias na nuvem, ele pode se beneficiar de análises humanas e automatizadas.</span><span class="sxs-lookup"><span data-stu-id="2050d-108">Since Teams touches on so many technologies in the Cloud, it can benefit from human and automated analysis.</span></span> <span data-ttu-id="2050d-109">Isso se aplica a *registro em logs* e *monitoramento em tempo real de reuniões*.</span><span class="sxs-lookup"><span data-stu-id="2050d-109">This applies to both *hunting in logs*, and *real-time monitoring of meetings*.</span></span> <span data-ttu-id="2050d-110">O Azure Sentinel oferece aos administradores essas soluções.</span><span class="sxs-lookup"><span data-stu-id="2050d-110">Azure Sentinel offers admins these solutions.</span></span>

> [!NOTE]
> <span data-ttu-id="2050d-111">Precisa de uma atualização no Azure Sentinel?</span><span class="sxs-lookup"><span data-stu-id="2050d-111">Need a refresher on Azure Sentinel?</span></span> <span data-ttu-id="2050d-112">[Este artigo](/azure/sentinel/overview) é ideal para isso.</span><span class="sxs-lookup"><span data-stu-id="2050d-112">[This article](/azure/sentinel/overview) is just the thing.</span></span>

## <a name="sentinel-and-microsoft-teams-activity-logs"></a><span data-ttu-id="2050d-113">Logs de atividades do Sentinel e do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2050d-113">Sentinel and Microsoft Teams Activity Logs</span></span>

<span data-ttu-id="2050d-114">Este artigo foca na coleta de logs de atividades do Teams no Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="2050d-114">This article focuses on collecting Teams activity logs in Azure Sentinel.</span></span>

<span data-ttu-id="2050d-115">Ele permite que os administradores façam o gerenciamento de segurança em um só local.</span><span class="sxs-lookup"><span data-stu-id="2050d-115">Sentinel lets administrators do security management in one location.</span></span> <span data-ttu-id="2050d-116">Isso inclui o gerenciamento de:</span><span class="sxs-lookup"><span data-stu-id="2050d-116">This includes managing:</span></span>

- <span data-ttu-id="2050d-117">Dispositivos de terceiros</span><span class="sxs-lookup"><span data-stu-id="2050d-117">Third-party devices</span></span>
- <span data-ttu-id="2050d-118">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="2050d-118">Microsoft Threat Protection</span></span>
- <span data-ttu-id="2050d-119">Cargas de trabalho do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2050d-119">Microsoft 365 Workloads</span></span>

<span data-ttu-id="2050d-120">As agendas de trabalho e as runbooks do Facebook podem tornar o monitoramento de segurança *sistemático*.</span><span class="sxs-lookup"><span data-stu-id="2050d-120">Sentinel workbooks and runbooks can make security monitoring *systematic*.</span></span> <span data-ttu-id="2050d-121">Um primeiro passo importante nesse processo é coletar os logs necessários para análise.</span><span class="sxs-lookup"><span data-stu-id="2050d-121">A good first step in this process is collecting the logs needed analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="2050d-122">Mais de uma assinatura do Microsoft 365 pode ser apresentada na mesma instância do Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="2050d-122">More than one Microsoft 365 subscription can be surfaced in the same instance of Azure Sentinel.</span></span> <span data-ttu-id="2050d-123">Isso permitirá o [monitoramento em tempo real](/azure/sentinel/livestream) e a busca por ameaças nos arquivos de logs históricos.</span><span class="sxs-lookup"><span data-stu-id="2050d-123">This will allow for [realtime monitoring](/azure/sentinel/livestream) and hunting for threats in historical log files.</span></span> <span data-ttu-id="2050d-124">Os administradores poderão buscar usando [consultas entre recursos](/azure/azure-monitor/log-query/cross-workspace-query), que estão em um único grupo de recursos, entre grupos de recursos ou em outra assinatura.</span><span class="sxs-lookup"><span data-stu-id="2050d-124">Administrators will be able to hunt using [cross-resource queries](/azure/azure-monitor/log-query/cross-workspace-query), that is within a single resource group, across resource groups, or in another subscription.</span></span>

## <a name="step-1-collect-teams-logs-enable-audit-logs-in-microsoft-365"></a><span data-ttu-id="2050d-125">Etapa 1: coletar logs de equipes: habilitar logs de Auditoria no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2050d-125">Step 1: Collect Teams logs: Enable Audit logs in Microsoft 365</span></span>

<span data-ttu-id="2050d-126">Como o Teams registra a atividade por meio do Microsoft 365, os logs de auditoria não são coletados por padrão.</span><span class="sxs-lookup"><span data-stu-id="2050d-126">Because Teams logs activity through Microsoft 365, audit logs aren't collected by default.</span></span> <span data-ttu-id="2050d-127">Habilite esse recurso por meio [destas etapas](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span><span class="sxs-lookup"><span data-stu-id="2050d-127">Turn on this feature with [these steps](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span></span> <span data-ttu-id="2050d-128">Os dados do Teams são coletados na Auditoria do Microsoft 365 em *Audit.General*.</span><span class="sxs-lookup"><span data-stu-id="2050d-128">Teams data is collected in the Microsoft 365 audit under *Audit.General*.</span></span>

## <a name="step-2-connect-office-365-logs-to-azure-sentinel"></a><span data-ttu-id="2050d-129">Etapa 2: conectar logs do Office 365 ao Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="2050d-129">Step 2: Connect Office 365 logs to Azure Sentinel</span></span>

<span data-ttu-id="2050d-130">O Azure Também fornece um conector integrado para logs do Office 365, que permite que você insira dados do Teams no Azure Sentinel junto com outros dados do Office 365.</span><span class="sxs-lookup"><span data-stu-id="2050d-130">Azure Sentinel provides a built-in connector for Office 365 logs, which enables you to ingest Teams data into Azure Sentinel together with other Office 365 data.</span></span>
 
<span data-ttu-id="2050d-131">Habilita o conector de dados do Office 365 no Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="2050d-131">In Azure Sentinel, enable the Office 365 data connector.</span></span> <span data-ttu-id="2050d-132">Para saber mais, consulte a [Documentação do Azure Sentinel](/azure/sentinel/connect-office-365).</span><span class="sxs-lookup"><span data-stu-id="2050d-132">For more information, see the [Azure Sentinel documentation](/azure/sentinel/connect-office-365).</span></span>

## <a name="helpful-hunting-kql-queries"></a><span data-ttu-id="2050d-133">Consultas úteis de busca KQL</span><span class="sxs-lookup"><span data-stu-id="2050d-133">Helpful hunting KQL queries</span></span>

<span data-ttu-id="2050d-134">Use essas consultas para se familiarizar com os dados e o ambiente do Teams.</span><span class="sxs-lookup"><span data-stu-id="2050d-134">Use these queries to familiarize yourself with your Teams data and Teams environment.</span></span> <span data-ttu-id="2050d-135">Saber como o ambiente deve parecer e se comportar é um primeiro passo importante para reconhecer atividades suspeitas.</span><span class="sxs-lookup"><span data-stu-id="2050d-135">Knowing how the environment should look and behave is a good first step in recognizing suspicious activity.</span></span> <span data-ttu-id="2050d-136">A partir daí, você pode se dedicar na busca por ameaças.</span><span class="sxs-lookup"><span data-stu-id="2050d-136">From there, you can branch out into threat hunting.</span></span>

### <a name="federated-external-users-query"></a><span data-ttu-id="2050d-137">Consulta de usuários externos federados</span><span class="sxs-lookup"><span data-stu-id="2050d-137">Federated external users query</span></span>

<span data-ttu-id="2050d-138">Obtenha a lista de sites do Teams que têm usuários externos federados.</span><span class="sxs-lookup"><span data-stu-id="2050d-138">Get the list of Teams sites that have federated external users.</span></span> <span data-ttu-id="2050d-139">Esses usuários terão um sufixo de nome de domínio/UPN que não pertence à organização.</span><span class="sxs-lookup"><span data-stu-id="2050d-139">These users have a domain name and/or a UPN suffix that isn't owned by your organization.</span></span>

<span data-ttu-id="2050d-140">Nesta consulta de exemplo, a organização é proprietária da contoso.com.</span><span class="sxs-lookup"><span data-stu-id="2050d-140">In this example query, the organization owns contoso.com.</span></span>

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where parse_json(Members)[0].Role == 3
| project TeamName, Operation, UserId, Members
| mv-expand bagexpansion=array Members
| evaluate bag_unpack(Members)
```

> [!TIP]
> <span data-ttu-id="2050d-141">Para saber mais sobre os tipos de acesso Externo e De convidado no Teams, confira [Comunicar-se com usuários de outras organizações](communicate-with-users-from-other-organizations.md)ou a seção [Tipos de Participante ](teams-security-guide.md#participant-types)no Guia de Segurança do Teams.</span><span class="sxs-lookup"><span data-stu-id="2050d-141">To learn more about External and Guest access types in Teams see [Communicate with users from other organizations](communicate-with-users-from-other-organizations.md), or the [Participant Types](teams-security-guide.md#participant-types) section in the Teams Security Guide.</span></span>

### <a name="who-recently-joined--whose-role-changed"></a><span data-ttu-id="2050d-142">Quem entrou recentemente / Quem mudou de função</span><span class="sxs-lookup"><span data-stu-id="2050d-142">Who recently joined / Whose role changed</span></span>

<span data-ttu-id="2050d-143">Consulte um usuário específico para verificar se ele foi adicionado a um canal do Teams nos últimos sete dias ou dentro de uma semana:</span><span class="sxs-lookup"><span data-stu-id="2050d-143">Query a specific user to check if they were added to a Teams channel in the last seven days, or within a week:</span></span>

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where Members has "<DisplayName>" or Members has "<UserPrincipalName>"
| project TeamName, Operation, UserId, Members
```

<span data-ttu-id="2050d-144">Consulte se a função de um usuário foi alterada para uma Equipe nos últimos sete dias:</span><span class="sxs-lookup"><span data-stu-id="2050d-144">Query whether a user's role changed for a Team in the last seven days:</span></span>

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberRoleChanged"
| project TeamName, Operation, UserId, Members
| mv-expand bagexpansion=array Members
| evaluate bag_unpack(Members)
| where Role == '1'
``` 

### <a name="external-users-from-unknown-or-new-organizations"></a><span data-ttu-id="2050d-145">Usuários externos de organizações novas ou desconhecidas</span><span class="sxs-lookup"><span data-stu-id="2050d-145">External users from unknown or new organizations</span></span>

<span data-ttu-id="2050d-146">No Teams, é possível adicionar usuários externos ao ambiente ou canais.</span><span class="sxs-lookup"><span data-stu-id="2050d-146">In Teams, you can add external users to your environment or channels.</span></span> <span data-ttu-id="2050d-147">As organizações geralmente têm um número limitado de parcerias importantes e adicionam usuários entre esses parceiros.</span><span class="sxs-lookup"><span data-stu-id="2050d-147">Organizations often have a limited number of key partnerships and add users from among these partners.</span></span> <span data-ttu-id="2050d-148">Este KQL verifica os usuários externos adicionados às equipes provenientes de organizações que não foram vistas ou adicionadas antes.</span><span class="sxs-lookup"><span data-stu-id="2050d-148">This KQL looks at external users added to teams who come from organizations that haven't been seen or added before.</span></span>

<span data-ttu-id="2050d-149">Para saber mais, confira a consulta no [Git hub da comunidade Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/ExternalUserFromNewOrgAddedToTeams.yaml).</span><span class="sxs-lookup"><span data-stu-id="2050d-149">For more information, see the query in the [Azure Sentinel community git hub](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/ExternalUserFromNewOrgAddedToTeams.yaml).</span></span>

### <a name="external-users-who-were-added-and-then-removed"></a><span data-ttu-id="2050d-150">Usuários externos que foram adicionados e removidos</span><span class="sxs-lookup"><span data-stu-id="2050d-150">External users who were added and then removed</span></span>

<span data-ttu-id="2050d-151">Os invasores com algum nível de acesso existente podem adicionar uma nova conta externa às equipes para acessar e retirar dados.</span><span class="sxs-lookup"><span data-stu-id="2050d-151">Attackers with some level of existing access may add a new external account to Teams to access and exfiltrate data.</span></span> <span data-ttu-id="2050d-152">Eles também podem remover rapidamente esse usuário para ocultar o acesso realizado.</span><span class="sxs-lookup"><span data-stu-id="2050d-152">They may also quickly remove that user to hide that they made access.</span></span> <span data-ttu-id="2050d-153">Essa consulta procura por contas externas que são adicionadas às equipes e removidas rapidamente para ajudar a identificar comportamentos suspeitos.</span><span class="sxs-lookup"><span data-stu-id="2050d-153">This query hunts for external accounts that are added to Teams and swiftly removed to help identify suspicious behavior.</span></span>

<span data-ttu-id="2050d-154">Para saber mais, confira a consulta no [Git hub da comunidade do Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Detections/OfficeActivity/ExternalUserAddedRemovedInTeams.yaml).</span><span class="sxs-lookup"><span data-stu-id="2050d-154">For more information, see the query in the [Azure Sentinel community git hub](https://github.com/Azure/Azure-Sentinel/blob/master/Detections/OfficeActivity/ExternalUserAddedRemovedInTeams.yaml).</span></span>

### <a name="new-bot-or-application-added"></a><span data-ttu-id="2050d-155">Novo bot ou aplicativo adicionado</span><span class="sxs-lookup"><span data-stu-id="2050d-155">New bot or application added</span></span>

<span data-ttu-id="2050d-156">O Teams pode incluir aplicativos ou bots em uma Equipe para estender o conjunto de recursos (incluindo bots e aplicativos personalizados).</span><span class="sxs-lookup"><span data-stu-id="2050d-156">Teams can include apps or bots in a Team to extend the feature set (including custom apps and bots).</span></span> <span data-ttu-id="2050d-157">Em alguns casos, um aplicativo ou bot pode ser usado para a *persistência* no Teams sem precisar de uma conta de usuário e pode acessar arquivos e outros dados.</span><span class="sxs-lookup"><span data-stu-id="2050d-157">In some cases, an app or bot can be used for *persistence* in Teams without needing a user account, and can access files and other data.</span></span> <span data-ttu-id="2050d-158">Esta consulta busca por novos aplicativos ou bots para o Teams.</span><span class="sxs-lookup"><span data-stu-id="2050d-158">This query hunts for apps or bots that are new to Teams.</span></span>

<span data-ttu-id="2050d-159">Para saber mais, confira a consulta no [Git hub da comunidade do Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/NewBotAddedToTeams.yaml).</span><span class="sxs-lookup"><span data-stu-id="2050d-159">For more information, see the query in the [Azure Sentinel community git hub](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/NewBotAddedToTeams.yaml).</span></span>

### <a name="user-accounts-who-are-owners-of-large-numbers-of-teams"></a><span data-ttu-id="2050d-160">Contas de usuário Proprietárias de um grande número de Equipes</span><span class="sxs-lookup"><span data-stu-id="2050d-160">User accounts who are Owners of large numbers of Teams</span></span>

<span data-ttu-id="2050d-161">Invasores que procuram elevar seus privilégios podem atribuir a si mesmos privilégios de proprietário de um grande número de equipes distintas.</span><span class="sxs-lookup"><span data-stu-id="2050d-161">Attackers looking to elevate their privileges may assign themselves Owner privileges of a large number of diverse teams.</span></span> <span data-ttu-id="2050d-162">*Normalmente*, os usuários criam e são os proprietários de grupos sobre tópicos específicos.</span><span class="sxs-lookup"><span data-stu-id="2050d-162">*Usually*, users create and own a few teams around specific topics.</span></span> <span data-ttu-id="2050d-163">Esta consulta KQL procura por comportamentos suspeitos.</span><span class="sxs-lookup"><span data-stu-id="2050d-163">This KQL query looks for suspicious behavior.</span></span>

<span data-ttu-id="2050d-164">Para saber mais, confira a consulta no [Git hub da comunidade do Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultiTeamOwner.yaml).</span><span class="sxs-lookup"><span data-stu-id="2050d-164">For more information, see the query in the [Azure Sentinel community git hub](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultiTeamOwner.yaml).</span></span>

### <a name="many-team-deletions-by-a-single-user"></a><span data-ttu-id="2050d-165">Várias exclusões da equipe por um único usuário</span><span class="sxs-lookup"><span data-stu-id="2050d-165">Many Team deletions by a single user</span></span>

<span data-ttu-id="2050d-166">Os invasores podem provocar interrupções, e comprometer projetos e dados ao excluir várias equipes.</span><span class="sxs-lookup"><span data-stu-id="2050d-166">Attackers can cause disruptions and jeopardize projects and data by deleting multiple teams.</span></span> <span data-ttu-id="2050d-167">Como as equipes geralmente são excluídas por proprietários individuais, uma exclusão central de várias equipes pode ser um sinal de problemas.</span><span class="sxs-lookup"><span data-stu-id="2050d-167">Since teams are usually deleted by individual Owners, central deletion of many teams can be a sign of trouble.</span></span> <span data-ttu-id="2050d-168">Esse KQL procura por usuários únicos que excluem várias equipes.</span><span class="sxs-lookup"><span data-stu-id="2050d-168">This KQL looks for single users who delete multiple teams.</span></span>

<span data-ttu-id="2050d-169">Para saber mais, confira a consulta no [Git hub da comunidade do Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultipleTeamsDeletes.yaml).</span><span class="sxs-lookup"><span data-stu-id="2050d-169">For more information, see the query in the [Azure Sentinel community git hub](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultipleTeamsDeletes.yaml).</span></span>

### <a name="expanding-your-threat-hunting-opportunities"></a><span data-ttu-id="2050d-170">Expandir oportunidades de busca por thread</span><span class="sxs-lookup"><span data-stu-id="2050d-170">Expanding your threat hunting opportunities</span></span>

<span data-ttu-id="2050d-171">A combinação de consultas de recursos como o Azure Active Directory (Azure AD) ou outras cargas de trabalho do Office 365 pode ser usada com consultas do Teams.</span><span class="sxs-lookup"><span data-stu-id="2050d-171">Combining queries from resources like Azure Active Directory (Azure AD), or other Office 365 workloads can be used with Teams queries.</span></span> <span data-ttu-id="2050d-172">Por exemplo, combine a detecção de padrões suspeitos nas SigninLogs do Azure AD e use esse resultado para procurar Proprietários de Equipe.</span><span class="sxs-lookup"><span data-stu-id="2050d-172">For example, combine the detection of suspicious patterns in Azure AD SigninLogs, and use that output while hunting for Team Owners.</span></span>

```Kusto
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
OfficeActivity
| where TimeGenerated > ago(time_window)
| where Operation =~ "MemberRoleChanged"
| mv-expand bagexpansion=array Members
| evaluate bag_unpack(Members)
| where Role == '2'
| where Members in (failed_signins)
```

<span data-ttu-id="2050d-173">Além disso, você pode fazer as detecções específicas do SigninLogs para o Teams adicionando um filtro apenas para entradas com base no Teams usando:</span><span class="sxs-lookup"><span data-stu-id="2050d-173">Also, you can make the SigninLogs detections specific to Teams by adding a filter for only Teams-based logons by using:</span></span>

```Kusto
| where AppDisplayName has 'Teams'
```

<span data-ttu-id="2050d-174">Para ajudar a explicar o uso *em que o AppDisplayName tem o Teams* melhor, o KQL que você vê abaixo demonstra um logon bem-sucedido de um endereço IP com falha de um endereço IP diferente, mas com escopo para *somente* Entradas no Teams:</span><span class="sxs-lookup"><span data-stu-id="2050d-174">To help explain using *where AppDisplayName has Teams* further, the KQL you see below demonstrates a successful logon from one IP address with failure from a different IP address, but scoped to *only* Teams sign-ins:</span></span>

```Kusto
let timeFrame = 1d;
let logonDiff = 10m;
SigninLogs 
  | where TimeGenerated >= ago(timeFrame) 
  | where ResultType == "0" 
  | where AppDisplayName has "Teams"
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

## <a name="important-information-and-updates"></a><span data-ttu-id="2050d-175">Atualizações e informações importantes</span><span class="sxs-lookup"><span data-stu-id="2050d-175">Important information and updates</span></span>

<span data-ttu-id="2050d-176">**Obrigado pela sua colaboração de conteúdo, Pete Bryan, Nicholas DiCola e Matthew Lowe.**</span><span class="sxs-lookup"><span data-stu-id="2050d-176">**Thank you for content collaboration, Pete Bryan, Nicholas DiCola, and Matthew Lowe.**</span></span> <span data-ttu-id="2050d-177">Mila Dias e as pessoas com quem ela colabora continuam a desenvolver consultas de detecção e consultas para Equipes.</span><span class="sxs-lookup"><span data-stu-id="2050d-177">Pete Bryan, and people he collaborates with, continue to develop detection and hunting queries for Teams.</span></span>

<span data-ttu-id="2050d-178">Mantenha-se em contato com este [Git Hub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) para repositório de atualizações.</span><span class="sxs-lookup"><span data-stu-id="2050d-178">Stay in touch with this [Git Hub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) repository for updates.</span></span>

<span data-ttu-id="2050d-179">Monitore as atualizações para o [analisador](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) e o [aplicativo lógico](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) usados neste artigo.</span><span class="sxs-lookup"><span data-stu-id="2050d-179">Watch for updates to the [parser](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) and [logic app](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) used in this article.</span></span>

<span data-ttu-id="2050d-180">Você também pode participar e contribuir com a [comunidade do Azure Sentinel](https://github.com/Azure/Azure-Sentinel/wiki).</span><span class="sxs-lookup"><span data-stu-id="2050d-180">You should also join (and contribute to) the [Azure Sentinel community](https://github.com/Azure/Azure-Sentinel/wiki).</span></span> <span data-ttu-id="2050d-181">Estamos ativamente procurando comentários neste artigo; portanto, use a opção de comentários abaixo.</span><span class="sxs-lookup"><span data-stu-id="2050d-181">We are actively looking for feedback on this article, so please use the feedback option below.</span></span> <span data-ttu-id="2050d-182">Obrigado e feliz busca. </span><span class="sxs-lookup"><span data-stu-id="2050d-182">Thank you & Happy hunting.</span></span>

[<span data-ttu-id="2050d-183">Registrar seu aplicativo no Azure AD</span><span class="sxs-lookup"><span data-stu-id="2050d-183">Registering your application in Azure AD</span></span>](/skype-sdk/ucwa/registeringyourapplicationinazuread%C2%A0%20%20%C2%A0)

[<span data-ttu-id="2050d-184">Ativar ou desativar a pesquisa de log de auditoria</span><span class="sxs-lookup"><span data-stu-id="2050d-184">Turn audit log search on or off</span></span>](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)

[<span data-ttu-id="2050d-185">O que é o Azure Sentinel?</span><span class="sxs-lookup"><span data-stu-id="2050d-185">What is Azure Sentinel?</span></span>](/azure/sentinel/overview)
