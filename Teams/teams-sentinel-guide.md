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
ms.localizationpriority: high
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
ms.openlocfilehash: 1cf7d4e9670d8ea282105eaa057347fa7e9f6dac
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/01/2022
ms.locfileid: "65822990"
---
# <a name="azure-sentinel-and-microsoft-teams"></a>Azure Sentinel e Microsoft Teams

> [!IMPORTANT]
> O Azure Sentinel agora tem um conector integrado. Para obter mais informações, confira [Conectar logs do Office 365 ao Azure Sentinel](/azure/sentinel/connect-office-365). Esta é a rota recomendada para coletar esses logs e substitui os métodos de coleta descritos abaixo.

O Teams desempenha um papel central na comunicação e no compartilhamento de dados no Microsoft 365 Cloud. Como o Teams tangencia tantas tecnologias na nuvem, ele pode se beneficiar de análises humanas e automatizadas. Isso se aplica a *registro em logs* e *monitoramento em tempo real de reuniões*. O Azure Sentinel oferece aos administradores essas soluções.

> [!NOTE]
> Precisa de uma atualização no Azure Sentinel? [Este artigo](/azure/sentinel/overview) é ideal para isso.

## <a name="sentinel-and-microsoft-teams-activity-logs"></a>Logs de atividades do Sentinel e do Microsoft Teams

Este artigo foca na coleta de logs de atividades do Teams no Azure Sentinel.

O Sentinel permite que os administradores realizem o gerenciamento de segurança em um local. Isso inclui o gerenciamento de:

- Dispositivos de terceiros
- Proteção contra Ameaças da Microsoft
- Cargas de trabalho do Microsoft 365

As agendas de trabalho e as runbooks do Facebook podem tornar o monitoramento de segurança *sistemático*. Um primeiro passo importante nesse processo é coletar os logs necessários para análise.

> [!NOTE]
> Mais de uma assinatura do Microsoft 365 pode ser apresentada na mesma instância do Azure Sentinel. Isso permitirá o [monitoramento em tempo real](/azure/sentinel/livestream) e a busca por ameaças nos arquivos de logs históricos. Os administradores poderão buscar usando [consultas entre recursos](/azure/azure-monitor/log-query/cross-workspace-query), que estão em um único grupo de recursos, entre grupos de recursos ou em outra assinatura.

## <a name="step-1-collect-teams-logs-enable-audit-logs-in-microsoft-365"></a>Etapa 1: coletar logs de equipes: habilitar logs de Auditoria no Microsoft 365

Como o Teams registra a atividade por meio do Microsoft 365, os logs de auditoria não são coletados por padrão. Habilite esse recurso por meio [destas etapas](/microsoft-365/compliance/turn-audit-log-search-on-or-off). Os dados do Teams são coletados na Auditoria do Microsoft 365 em *Audit.General*.

## <a name="step-2-connect-office-365-logs-to-azure-sentinel"></a>Etapa 2: conectar logs do Office 365 ao Azure Sentinel

O Azure Também fornece um conector integrado para logs do Office 365, que permite que você insira dados do Teams no Azure Sentinel junto com outros dados do Office 365.
 
Habilita o conector de dados do Office 365 no Azure Sentinel. Para saber mais, consulte a [Documentação do Azure Sentinel](/azure/sentinel/connect-office-365).

## <a name="helpful-hunting-kql-queries"></a>Consultas úteis de busca KQL

Use essas consultas para se familiarizar com os dados e o ambiente do Teams. Saber como o ambiente deve parecer e se comportar é um primeiro passo importante para reconhecer atividades suspeitas. A partir daí, você pode se dedicar na busca por ameaças.

### <a name="federated-external-users-query"></a>Consulta de usuários externos federados

Obtenha a lista de sites do Teams que têm usuários externos federados. Esses usuários terão um sufixo de nome de domínio/UPN que não pertence à organização.

Nesta consulta de exemplo, a organização é proprietária da contoso.com.

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
> Para saber mais sobre os tipos de acesso Externo e De convidado no Teams, confira [Comunicar-se com usuários de outras organizações](communicate-with-users-from-other-organizations.md)ou a seção [Tipos de Participante ](teams-security-guide.md#participant-types)no Guia de Segurança do Teams.

### <a name="who-recently-joined--whose-role-changed"></a>Quem entrou recentemente / Quem mudou de função

Consulte um usuário específico para verificar se ele foi adicionado a um canal do Teams nos últimos sete dias ou dentro de uma semana:

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where Members has "<DisplayName>" or Members has "<UserPrincipalName>"
| project TeamName, Operation, UserId, Members
```

Consulte se a função de um usuário foi alterada para uma Equipe nos últimos sete dias:

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberRoleChanged"
| project TeamName, Operation, UserId, Members
| mv-expand bagexpansion=array Members
| evaluate bag_unpack(Members)
| where Role == '1'
``` 

### <a name="external-users-from-unknown-or-new-organizations"></a>Usuários externos de organizações novas ou desconhecidas

No Teams, é possível adicionar usuários externos ao ambiente ou canais. As organizações geralmente têm um número limitado de parcerias importantes e adicionam usuários entre esses parceiros. Este KQL verifica os usuários externos adicionados às equipes provenientes de organizações que não foram vistas ou adicionadas antes.

Para saber mais, confira a consulta no [Git hub da comunidade Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/ExternalUserFromNewOrgAddedToTeams.yaml).

### <a name="external-users-who-were-added-and-then-removed"></a>Usuários externos que foram adicionados e removidos

Os invasores com algum nível de acesso existente podem adicionar uma nova conta externa às equipes para acessar e retirar dados. Eles também podem remover rapidamente esse usuário para ocultar o acesso realizado. Essa consulta procura por contas externas que são adicionadas às equipes e removidas rapidamente para ajudar a identificar comportamentos suspeitos.

Para saber mais, confira a consulta no [Git hub da comunidade do Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Detections/OfficeActivity/ExternalUserAddedRemovedInTeams.yaml).

### <a name="new-bot-or-application-added"></a>Novo bot ou aplicativo adicionado

O Teams pode incluir aplicativos ou bots em uma Equipe para estender o conjunto de recursos (incluindo bots e aplicativos personalizados). Em alguns casos, um aplicativo ou bot pode ser usado para a *persistência* no Teams sem precisar de uma conta de usuário e pode acessar arquivos e outros dados. Esta consulta busca por novos aplicativos ou bots para o Teams.

Para saber mais, confira a consulta no [Git hub da comunidade do Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/NewBotAddedToTeams.yaml).

### <a name="user-accounts-who-are-owners-of-large-numbers-of-teams"></a>Contas de usuário Proprietárias de um grande número de Equipes

Invasores que procuram elevar seus privilégios podem atribuir a si mesmos privilégios de proprietário de um grande número de equipes distintas. *Normalmente*, os usuários criam e são os proprietários de grupos sobre tópicos específicos. Esta consulta KQL procura por comportamentos suspeitos.

Para saber mais, confira a consulta no [Git hub da comunidade do Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultiTeamOwner.yaml).

### <a name="many-team-deletions-by-a-single-user"></a>Várias exclusões da equipe por um único usuário

Os invasores podem provocar interrupções, e comprometer projetos e dados ao excluir várias equipes. Como as equipes geralmente são excluídas por proprietários individuais, uma exclusão central de várias equipes pode ser um sinal de problemas. Esse KQL procura por usuários únicos que excluem várias equipes.

Para saber mais, confira a consulta no [Git hub da comunidade do Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultipleTeamsDeletes.yaml).

### <a name="expanding-your-threat-hunting-opportunities"></a>Expandir oportunidades de busca por thread

A combinação de consultas de recursos como o Azure Active Directory (Azure AD) ou outras cargas de trabalho do Office 365 pode ser usada com consultas do Teams. Por exemplo, combine a detecção de padrões suspeitos nas SigninLogs do Azure AD e use esse resultado para procurar Proprietários de Equipe.

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

Além disso, você pode fazer as detecções específicas do SigninLogs para o Teams adicionando um filtro apenas para entradas com base no Teams usando:

```Kusto
| where AppDisplayName has 'Teams'
```

Para ajudar a explicar o uso *em que o AppDisplayName tem o Teams* melhor, o KQL que você vê abaixo demonstra um logon bem-sucedido de um endereço IP com falha de um endereço IP diferente, mas com escopo para *somente* Entradas no Teams:

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

## <a name="important-information-and-updates"></a>Atualizações e informações importantes

**Obrigado pela sua colaboração de conteúdo, Pete Bryan, Nicholas DiCola e Matthew Lowe.** Mila Dias e as pessoas com quem ela colabora continuam a desenvolver consultas de detecção e consultas para Equipes.

Mantenha-se em contato com este [Git Hub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/) para repositório de atualizações.

Monitore as atualizações para o [analisador](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) e o [aplicativo lógico](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) usados neste artigo.

Você também pode participar e contribuir com a [comunidade do Azure Sentinel](https://github.com/Azure/Azure-Sentinel/wiki). Estamos ativamente procurando comentários neste artigo; portanto, use a opção de comentários abaixo. Obrigado e feliz busca. 

[Registrar seu aplicativo no Azure AD](/skype-sdk/trusted-application-api/docs/registrationinazureactivedirectory)

[Ativar ou desativar a pesquisa de log de auditoria](/microsoft-365/compliance/turn-audit-log-search-on-or-off)

[O que é o Azure Sentinel?](/azure/sentinel/overview)
