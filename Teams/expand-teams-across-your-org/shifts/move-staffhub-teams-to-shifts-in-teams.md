---
title: Mover suas equipes do StaffHub para turnos
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu, gumariam
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como mover suas equipes do Microsoft StaffHub e agendar dados para turnos no Microsoft Teams.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- SPO_Content
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f449d20f4364629185f719c3217023107f774dd9
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2020
ms.locfileid: "44350305"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a>Mover suas equipes do Microsoft StaffHub para turnos no Microsoft Teams

> [!IMPORTANT]
> A partir de 30 de junho de 2020, o Microsoft StaffHub será desativado. Estamos criando recursos de StaffHub no Microsoft Teams. Hoje, o Teams inclui o aplicativo turnos para gerenciamento de agendamento e recursos adicionais se acumularão ao longo do tempo. O StaffHub deixará de funcionar para todos os usuários em 30 de junho de 2020. Qualquer pessoa que tentar abrir o StaffHub será exibida uma mensagem direcionando-o para o download do teams. Para saber mais, confira [Microsoft StaffHub para ser desativado](microsoft-staffhub-to-be-retired.md).

O aplicativo turnos no Microsoft Teams oferece uma abordagem simples para o gerenciamento de cronogramas e o fluxo constante de trocas de turnos e cancelamentos que ocorrem diariamente. Os membros da equipe podem acessar o cronograma e deslocar as informações diretamente no aplicativo e em seus dispositivos para definir suas preferências, gerenciar seus cronogramas e solicitar folga.

Este artigo apresenta uma orientação sobre como mover as equipes do StaffHub da sua organização e agendar dados para turnos no Microsoft Teams. Ele aborda:

- [O que você precisa saber sobre a mudança para o Teams](#what-you-need-to-know-about-the-move-to-teams)
- [Pare](#prepare)
- [Conduzir um piloto](#conduct-a-pilot) 
- [Vá além do seu piloto e mova todas as equipes do StaffHub](#go-beyond-your-pilot-and-move-all-staffhub-teams)
- [Monitorar o uso do teams](#monitor-teams-usage)
- [Solução de problemas](#troubleshooting)

Seja você uma pequena empresa com uma ou duas equipes do StaffHub ou uma grande empresa com centenas de equipes do StaffHub, você encontrará as diretrizes de administração necessárias para ajudar a fazer sua transição para o Microsoft Teams com êxito.

Você deve ser um administrador global para executar as etapas neste artigo. Se ainda não tiver feito isso, examine as [perguntas frequentes sobre a descontinuação do StaffHub](microsoft-staffhub-to-be-retired.md) para obter respostas para qualquer pergunta que você tenha.

## <a name="what-you-need-to-know-about-the-move-to-teams"></a>O que você precisa saber sobre a mudança para o Teams

### <a name="when-to-move-to-teams"></a>Quando mover para o Microsoft Teams

A partir de 30 de junho de 2020, o StaffHub será desativado. Recomendamos que você comece a usar o Microsoft Teams hoje e comece a fazer a transição das equipes e dos usuários da sua organização do StaffHub. Com o gerenciamento de agendamento sendo o recurso mais comumente usado no StaffHub, recomendamos que você use o aplicativo turnos no Microsoft Teams, avançando.

### <a name="what-is-moved-to-teams"></a>O que é movido para o Microsoft Teams

Quando você move uma equipe do StaffHub, associação da equipe, detalhes do usuário, cronogramas da equipe e dados de chat são movidos para o Microsoft Teams. Os arquivos não são movidos quando você move uma equipe do StaffHub. Se uma equipe do StaffHub contém arquivos que você também deseja mover para o Microsoft Teams, mova os arquivos em uma etapa separada.

Cada equipe do StaffHub precisa de um grupo correspondente do Microsoft 365 ou do Office 365. Se uma equipe do StaffHub estiver associada a um grupo do Microsoft 365, a configuração de privacidade do grupo será mantida quando você mover a equipe. Se uma equipe do StaffHub não tiver um grupo do Microsoft 365 associado a ela, um grupo com uma configuração de privacidade de particular será criado automaticamente para você dar suporte à transição.  Devido à diferença na nomenclatura de equipes e grupos entre o Teams e o StaffHub, você pode ver um nome de equipe diferente no Teams. 

À medida que você muda de equipe do StaffHub para o Teams, os usuários não têm mais acesso às suas agendas no StaffHub e são redirecionados para turnos no Microsoft Teams. Recomendamos que você comunique essa alteração a toda a sua organização para minimizar as interrupções e incentivar os usuários a adotar e explorar o Microsoft Teams. Se você tiver o Azure AD Premium, poderá [executar um relatório](run-report-to-show-staffhub-usage.md) para obter uma lista de usuários do StaffHub em sua organização que precisam saber mais sobre essa alteração.  

Não há opção de reversão após mover uma equipe do StaffHub para o Microsoft Teams.

### <a name="user-experience-when-you-move-a-team"></a>Experiência do usuário ao mover uma equipe

Há um tempo de inatividade mínimo (menos de um segundo) para os usuários quando sua equipe é comutada de StaffHub para turnos no Teams. Os usuários podem continuar a usar o StaffHub até que a mudança para o Microsoft Teams seja concluída. Quando a mudança for concluída, os membros da equipe verão uma mensagem para informar que precisam começar a usar os turnos no Teams para acessar o cronograma da equipe. Veja um exemplo da mensagem que os usuários verão no StaffHub depois que a equipe do StaffHub for movida para o Microsoft Teams.

![Exemplo da mensagem exibida pelos usuários.](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Exemplo da mensagem que os usuários veem no StaffHub após a equipe do StaffHub ser movida para o Microsoft Teams")

## <a name="prepare"></a>Pare

Veja como se preparar para a mudança para o Teams.

### <a name="check-that-prerequisites-are-met"></a>Verificar se os pré-requisitos foram atendidos

Antes de mover uma equipe do StaffHub para o Microsoft Teams, certifique-se de que:

- O usuário conectado é um administrador global.
- O Teams está habilitado para todos os usuários no locatário.
- A criação de grupos do Microsoft 365 está habilitada no locatário.
- O StaffHub TeamID é válido.
- A equipe do StaffHub tem pelo menos um proprietário de equipe.
- A equipe do StaffHub contém membros.
- Todos os membros da equipe do StaffHub são vinculados a uma conta do Azure AD.
- Todos os membros da equipe do StaffHub recebem uma licença do teams.  

Se esses pré-requisitos não forem atendidos, a solicitação de mudança falhará.

### <a name="assign-teams-licenses"></a>Atribuir licenças do Teams

Cada usuário deve ter uma licença ativa do Microsoft 365 ou do Office 365 de [um plano elegível](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) e deve receber uma licença do teams. Atribuir uma licença do teams aos usuários permite que eles acessem o Microsoft Teams.

Você gerencia as licenças do teams no centro de administração do Microsoft 365. Para saber mais, confira [Gerenciar o acesso dos usuários ao Teams](../../user-access.md).

> [!NOTE]
> Se a sua organização usa o Skype for Business e você não está pronto para mover todos os usuários para o Microsoft Teams, você pode habilitar o Microsoft Teams para os seus primeiros trabalhadores que podem executar o Microsoft Teams junto ao Skype for Business. Nesse modo de coexistência, chamado de *ilhas*, cada aplicativo cliente Opera como uma solução separada. Para saber mais, consulte [entender o Microsoft Teams e a coexistência e interoperabilidade do Skype for Business](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).

### <a name="install-the-prerelease-version-of-the-staffhub-powershell-module"></a>Instalar a versão de pré-lançamento do módulo StaffHub PowerShell

Se você ainda não fez isso, [Instale a versão de pré-lançamento do módulo StaffHub PowerShell](install-the-staffhub-powershell-module.md).

Você deve ter a versão de pré-lançamento do módulo instalada para mover suas equipes do StaffHub para o Microsoft Teams.

### <a name="link-an-azure-ad-account-for-staffhub-team-members-who-dont-have-one"></a>Vincular uma conta do Azure AD para os membros da equipe do StaffHub que não têm uma

Cada membro da equipe do StaffHub deve estar vinculado a uma conta do Azure Active Directory (Azure AD). Os usuários em sua organização não serão vinculados a uma conta do Azure AD se qualquer um dos seguintes cenários se aplicarem:

- Um proprietário da equipe adicionou um usuário que não tem uma conta do Azure AD.
- Um proprietário da equipe convidou um usuário para uma equipe do StaffHub e esse usuário não aceitou o convite.

Esses usuários têm contas inativas e mostram o estado do usuário de desconhecido, convidado ou InviteRejected. Você pode vincular uma conta do Azure AD para esses usuários.  Veja como.

#### <a name="get-a-list-of-all-inactive-accounts-on-staffhub-teams"></a>Obter uma lista de todas as contas inativas no StaffHub Teams

Execute a série de comandos a seguir para obter uma lista de todas as contas inativas no StaffHub Teams e exportar a lista para um arquivo CSV. Cada comando deve ser executado separadamente.

```PowerShell
$InvitedUsersObject = @()

$StaffHubTeams = Get-StaffHubTeamsForTenant

$StaffHubTeams[0] = $StaffHubTeams[0] | Where-Object { $_.ManagedBy -eq 'StaffHub' }

foreach($team in $StaffHubTeams[0])
{ 
    Write-host $team.name
    $StaffHubUsers = Get-StaffHubMember -TeamId $team.Id | where {$_.State -eq "Invited"}
    foreach($StaffHubUser in $StaffHubUsers) {
        $InvitedUsersObject  += New-Object PsObject -Property @{
          "TeamID"="$($team.Id)"
          "TeamName"="$($team.name)"
          "MemberID"="$($StaffHubUser.Id)"
            }
    }
}

$InvitedUsersObject | SELECT * | export-csv InvitedUsers.csv -NoTypeInformation  
```

#### <a name="link-the-account"></a>Vincular a conta

Siga um destes procedimentos:

- Converter e vincular a conta.

  Os gerentes e proprietários de equipe do StaffHub podem converter uma conta inativa e vinculá-la a uma conta do Azure AD no StaffHub alterando o endereço de email do usuário para um UPN válido na página de configurações da equipe do StaffHub.

- Remova a conta não vinculada e, em seguida, adicione novamente a conta usando o UPN.
    1. Execute o cmdlet [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubMember?view=staffhub-ps) para remover a conta não provisionada da equipe do StaffHub.
    2. Execute o cmdlet [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) para adicionar a conta de volta à equipe do StaffHub usando o UPN.

- Remover a conta inativa. Use esta opção se a conta do usuário não for mais necessária.

### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a>Atribuir a política de configuração do aplicativo FirstlineWorker aos usuários

O Teams inclui uma política interna de configuração de aplicativos do FirstlineWorker que você pode usar para personalizar o Microsoft Teams para destacar os aplicativos que são mais importantes para os primeiros funcionários da sua organização. Quando você atribui essa política aos usuários, os aplicativos da política são fixados na barra de aplicativos no Microsoft Teams para acesso rápido e fácil. Outros aplicativos adicionados às equipes podem ser encontrados na barra de aplicativos clicando em **... Mais aplicativos** na área de trabalho da equipe e nos clientes Web e passando o dedo para cima no cliente do teams Mobile. Por padrão, a política de configuração do aplicativo FirstlineWorker inclui a atividade, turnos, chat e aplicativos de chamada.

Para ver as etapas sobre como atribuir a política de configuração do aplicativo FirstlineWorker aos usuários, consulte [usar a política de configuração do aplicativo FirstlineWorker para fixar turnos em Teams](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams). Depois de atribuir uma política, pode levar algumas horas para entrar em vigor.

Recomendamos que você conclua esta etapa pelo menos uma semana antes de mover suas equipes e usuários do StaffHub para o Microsoft Teams. Quando os usuários estão em equipes, confirme se eles podem ver e acessar o aplicativo turnos.

Você também pode criar políticas de configuração de aplicativo personalizadas e editar as configurações na política de configuração de aplicativo global. Para saber mais, confira [gerenciar políticas de configuração de aplicativos no Microsoft Teams](../../teams-app-setup-policies.md).

### <a name="onboard-users-to-teams"></a>Usuários integrados ao Microsoft Teams

Como parte da sua estratégia de integração, forneça treinamento e orientação para que os usuários ajudem a se familiarizar com o Microsoft Teams. Compartilhe os recursos a seguir com os usuários para que eles saibam onde obter clientes, treinamento e suporte do teams:

- [Cliente Web do Teams](https://teams.microsoft.com)
- [Links para download de clientes para área de trabalho e dispositivos móveis](https://teams.microsoft.com/downloads)
- [Vídeos de treinamento do Teams](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)
- [Documentação da Ajuda do Teams](https://support.office.com/teams)

Para obter orientação sobre como implantar equipes e conduzir a adoção do Teams, consulte [como implantar equipes](../../How-to-roll-out-teams.md) e [adotar equipes](../../adopt-microsoft-teams-landing-page.md).

## <a name="conduct-a-pilot"></a>Conduzir um piloto

Recomendamos que você comece movendo duas ou três equipes StaffHub para um grupo seleto de pioneiros. A execução de um piloto ajuda você a refinar seu plano de transição e garantir que você esteja pronto para mover todas as equipes do StaffHub da sua organização para o Microsoft Teams. Ele também identifica campeões que podem ajudar a impulsionar a adoção em toda a sua organização. Se você for uma pequena empresa que não precisa de uma abordagem em fases, as etapas nesta seção podem ser tudo o que você precisa fazer para fazer a mudança do StaffHub para o Microsoft Teams.

### <a name="identify-pilot-teams"></a>Identificar equipes piloto

Tenha acesso à identificação de duas ou três equipes piloto. Todos os membros da equipe devem confirmar o uso de turnos no Teams para gerenciar seus cronogramas e se comunicar e colaborar uns com os outros.

### <a name="identify-team-champions"></a>Identificar especialistas da equipe

Identifique especialistas em nossas equipes piloto e as solicite para ajudar a evangelizar turnos. Os representantes da equipe são apaixonados pelo que fazem, compartilhando suas próprias informações para oferecer suporte e orientação aos membros da equipe. Os campeões da equipe podem ser proprietários ou gerentes da equipe.

Os campeões de equipe devem garantir que os membros da equipe sejam configurados dedicando-se tempo para que todos [obtenham clientes](../../get-clients.md)do Teams, entrem no Teams e confiram suas agendas em turnos e comecem a conversar uns com os outros. Os usuários que já estão familiarizados com o StaffHub estarão em funcionamento rapidamente em turnos. Você também pode apontá-los para a [ajuda de turnos](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) para obter ajuda adicional.

### <a name="move-a-staffhub-team"></a>Mover uma equipe do StaffHub

Use estas etapas para mover uma equipe do StaffHub de cada vez. Recomendamos essa abordagem para suas equipes piloto. Mais tarde, quando você estiver pronto para mover todas as equipes do StaffHub da sua organização, consulte [mover suas equipes do StaffHub](#move-your-staffhub-teams) para ver as etapas sobre como mover várias equipes de cada vez.

Execute o seguinte para mover uma equipe do StaffHub.

```PowerShell
Move-StaffHubTeam -TeamId <String>
```
Exemplo

```PowerShell
Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

Veja um exemplo da resposta que você obtém quando envia uma solicitação para mover uma equipe do StaffHub para o Microsoft Teams.

```console
 jobId                                      teamId                                      teamAlreadyInMicrosofteams  
---------------------------------------    ----------------------------------------    ---------------------------          
JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

Para verificar o status de uma solicitação de movimentação, execute o seguinte.

```PowerShell
Get-TeamMigrationJobStatus <String>
```
Exemplo

```PowerShell
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"
```

Veja um exemplo da resposta que você obtém quando uma mudança está em andamento.

```console
jobId                                     status       teamId                                     isO365GroupCreated  Error
----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

### <a name="move-files-from-a-staffhub-team-to-teams"></a>Mover arquivos de uma equipe do StaffHub para o Microsoft Teams

Esta etapa aplica-se apenas se a equipe do StaffHub que você moveu para o Microsoft Teams tiver arquivos que você deseja que também se movam para o Microsoft Teams. Você pode mover arquivos diretamente no SharePoint Online ou usando o PowerShell.

#### <a name="in-sharepoint-online"></a>No SharePoint Online

Veja [como mover arquivos no SharePoint Online](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30).

#### <a name="using-powershell"></a>Usando o PowerShell

Baixe e instale o [Shell de gerenciamento do SharePoint Online](https://www.microsoft.com/download/details.aspx?id=35588), caso ainda não tenha feito isso. Ele contém os cmdlets necessários para mover arquivos.  

Use o cmdlet [Connect-PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) para se conectar ao site de equipe do SharePoint Online.

```PowerShell
Connect-PnPOnline -Url https://<sharepoint URL>/sites/<Group Name>  
```

Para cada arquivo que você deseja mover do StaffHub para o Microsoft Teams, use o cmdlet [move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) para mover o arquivo.

```PowerShell
Move-PnPFile -ServerRelativeUrl "/sites/<Group Name>/Shared Documents/<File Name>" -TargetUrl "/sites/<Group Name>/Shared Documents/General/<File Name>" 
```

Para mover vários arquivos, execute um loop sobre os arquivos e execute o segundo comando no loop. Você não precisa repetir o primeiro comando se a sessão permanecer ativa.

## <a name="go-beyond-your-pilot-and-move-all-staffhub-teams"></a>Vá além do seu piloto e mova todas as equipes do StaffHub

### <a name="raise-awareness"></a>Aumentar a conscientização

Quando você estiver pronto para ir além de suas equipes piloto e mover as equipes do StaffHub da sua organização para o Microsoft Teams, é importante primeiro comunicar a alteração em toda a sua organização. Espalhe a palavra sobre turnos e a transição para o Microsoft Teams para aumentar a conscientização, gerar entusiasmo e impulsionar a adoção.

### <a name="move-your-staffhub-teams"></a>Mover suas equipes do StaffHub

Use estas etapas para mover as equipes do StaffHub em massa. Você pode optar por mover todas as equipes do StaffHub da sua organização ou mover equipes específicas do StaffHub. Se você quiser mover um StaffHub Teams, um por vez, consulte [mover uma equipe do StaffHub](#move-a-staffhub-team).

#### <a name="move-all-staffhub-teams"></a>Mover todas as equipes do StaffHub

Execute o seguinte para obter uma lista de todas as equipes do StaffHub em sua organização.

```PowerShell
$StaffHubTeams = Get-StaffHubTeamsForTenant

$StaffHubTeams[0] | Where-Object { $_.ManagedBy -eq 'StaffHub' }
```

Em seguida, execute o seguinte para mover todas as equipes.

```PowerShell
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

Veja um exemplo da resposta.

Para todas as equipes que já foram movidas para o Microsoft Teams ou já existirem no Teams, o jobId será "nulo" porque um trabalho não precisará ser enviado para mover a equipe.

```console
jobId                                      teamId                                      teamAlreadyInMicrosofteams  
----------------------------------------   -----------------------------------------   --------------------------         
null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams"></a>Mover equipes específicas do StaffHub

Execute o seguinte para obter uma lista de todas as IDs de equipe do StaffHub em sua organização.

```PowerShell
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

Nos resultados retornados pelo `Get-StaffHubteamsForTenant` cmdlet executado anteriormente, selecione as IDs de equipe que você deseja mover e, em seguida, adicione-as a um arquivo CSV (valores separados por vírgula).

Aqui está um exemplo de como o arquivo CSV deve ser formatado.

|%  |
|---------|
|TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f<br>TEAM_81b1f191-3e19-45ce-AB32-3ef51f100000<br>TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000<br>TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000|

Depois de criar o arquivo CSV, execute o seguinte para mover as equipes que você especificou no arquivo CSV.

```PowerShell
$StaffHubTeams = Import-Csv .\teams.csv

foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams"></a>Confirme se suas equipes do StaffHub foram movidas para o Microsoft Teams

Execute o seguinte para obter uma lista de todas as equipes em turnos em sua organização. 

```PowerShell
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

### <a name="move-files-from-your-staffhub-teams-to-teams"></a>Mover arquivos de suas equipes do StaffHub para o Microsoft Teams

Se as equipes do StaffHub que você moveu contiverem arquivos que você também deseja mover para o Microsoft Teams, consulte [mover arquivos de uma equipe do StaffHub para o Microsoft Teams](#move-files-from-a-staffhub-team-to-teams).

## <a name="monitor-teams-usage"></a>Monitorar o uso do teams

Os relatórios de uso podem ajudá-lo a entender melhor os padrões de uso e oferecer ideias sobre onde priorizar os esforços de treinamento e comunicação em toda a organização. Você pode executar relatórios que mostram o uso geral das equipes, os tipos de atividades realizadas pelos usuários no Teams, como os usuários se conectam ao Teams e muito mais. Para obter mais informações, consulte relatórios [do Microsoft Teams no centro de administração do Microsoft Teams](../../teams-analytics-and-reports/teams-reporting-reference.md) e [relatórios de atividade do Microsoft Teams no centro de administração do Microsoft 365](../../teams-activity-reports.md).

## <a name="troubleshooting"></a>Solução de problemas

**Como obter mais informações sobre erros de falha**

Execute o seguinte para obter mais informações sobre erros de "falha" que ocorrem quando você tenta mover uma equipe:

```PowerShell
Move-StaffHubTeam -TeamId <TeamId>

$res = Get-TeamMigrationJobStatus -JobId <JobId>

$res.Status
```

Você verá um dos seguintes status: êxito, falha, InProgress, enfileirado.

Se "falha" for retornado, execute o seguinte procedimento para obter mais informações sobre o erro:

```PowerShell
$res.Result.Error.Innererror
```

**Quando você tenta mover uma equipe do StaffHub, o status é mostrado como "falha" e você recebe uma mensagem de erro "falha ao recuperar categorias de SKU aplicáveis para o usuário"**

Isso pode ocorrer se um ou mais membros da equipe não tiverem uma licença do teams. Vá para portal.office.com, localize o grupo e, em seguida, confirme que os membros do grupo recebem uma licença do teams.

**Quando você tenta mover uma equipe do StaffHub, o status é mostrado como "falha" e você recebe uma mensagem de erro "proprietário da equipe não encontrado"**

Isso pode ocorrer se o grupo associado à equipe do StaffHub não tiver um proprietário da equipe. Vá para portal.office.com, localize o grupo e adicione um ou mais proprietários ao grupo.

**Ao tentar mover arquivos do StaffHub para o Microsoft Teams, você recebe a mensagem de erro "permissão negada".**

Isso pode ocorrer se você estiver tentando mover arquivos em um grupo particular do Microsoft 365 do qual você não é membro. Se esse for o caso, use o cmdlet [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) para se adicionar à equipe do StaffHub e, em seguida, mova os arquivos. Depois de mover os arquivos, use o cmdlet [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) para remover-se da equipe. 

**Ao tentar mover arquivos do StaffHub para o Microsoft Teams, você recebe um erro que diz que a pasta geral não existe.**

Execute o seguinte comando para adicionar a pasta geral ao SharePoint e tente novamente:

  ```PowerShell
  Add-PnPFolder -Name General -Folder 'Shared Documents'
  ```  

## <a name="related-topics"></a>Tópicos relacionados
- [Como implementar o Microsoft Teams](../../How-to-roll-out-teams.md)
- [O Microsoft StaffHub será desativado](microsoft-staffhub-to-be-retired.md)
- [Gerencie o aplicativo Turnos para sua organização no Microsoft Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Referência do PowerShell do StaffHub](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
