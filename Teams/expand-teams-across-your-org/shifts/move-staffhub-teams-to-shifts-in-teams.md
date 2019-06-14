---
title: Mova as suas equipes do StaffHub para o Shifts no Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Aprenda a mover suas equipes e os dados agendados do Microsoft StaffHub para o Shifts no Microsoft Teams.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e2e8b0ac4f1c4eb0cce2cae97481fc428f588ec5
ms.sourcegitcommit: 8f9bf1acdcdc2104fa8c343c030d64838e2c31eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/07/2019
ms.locfileid: "34780805"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a>Mova as suas equipes do Microsoft StaffHub para o Shifts no Teams

> [!IMPORTANT]
> A partir 1 de outubro de 2019, o Microsoft StaffHub será desativado. Estamos criando recursos StaffHub no Microsoft Teams. Hoje, o Teams inclui o aplicativo Shifts para o gerenciamento de cronogramas e os recursos adicionais serão implantados com o tempo. O StaffHub deixará de funcionar para todos os usuários em 1 de outubro de 2019. Todas as pessoas que tentarem abrir o StaffHub receberão uma mensagem direcionando-as para o download do Teams. Para saber mais, confira [O Microsoft StaffHub será desativado](microsoft-staffhub-to-be-retired.md).

O aplicativo Shifts no Teams oferece uma abordagem simples para o gerenciamento de cronogramas e o fluxo constante de trocas de turnos e cancelamentos que ocorrem diariamente. Os membros da equipe podem acessar o cronograma e as informações de turno diretamente no aplicativo e em seus dispositivos para definir suas preferências, gerenciar seus cronogramas e solicitar folgas.

Este artigo descreve como mover as equipes StaffHub da sua organização e os dados agendados para o Shifts no Teams. Ele abrange:

- [O que você precisa saber sobre a mudança para o Teams](#what-you-need-to-know-about-the-move-to-teams)
- [Preparar](#prepare)
- [Conduzir um piloto](#conduct-a-pilot) 
- [Ir além do seu piloto e mover todas as equipes do StaffHub](#go-beyond-your-pilot-and-move-all-staffhub-teams)
- [Monitorar o uso do Teams](#monitor-teams-usage)
- [Solução de Problemas](#troubleshooting)

Seja você uma pequena empresa com uma ou duas equipes do StaffHub ou uma grande empresa com centenas de equipes do StaffHub, aqui você encontrará as diretrizes de administração necessárias que ajudarão a tornar sua transição para o Teams bem-sucedida.

Você deve ser um administrador global para realizar as etapas deste artigo. Se você ainda não fez isso, dê uma olhada nas [Perguntas frequentes sobre a desativação do StaffHub](microsoft-staffhub-to-be-retired.md) para obter respostas para quaisquer dúvidas que possa ter.

## <a name="what-you-need-to-know-about-the-move-to-teams"></a>O que você precisa saber sobre a mudança para o Teams

### <a name="when-to-move-to-teams"></a>Quando ir para o Teams

A partir 1 de outubro de 2019, o StaffHub será desativado. Incentivamos você a começar a usar o Teams hoje e a começar a fazer a transição das equipes e dos usuários da sua organização do StaffHub. Com o gerenciamento de agendamento sendo o recurso mais usado no StaffHub, recomendamos que você use o aplicativo Shifts no Teams em andamento.

### <a name="what-is-moved-to-teams"></a>O que é movido para o Teams

Os detalhes do usuário, as informações do cronograma e os dados de chat e arquivos são transicionados para ao Teams. Isso inclui membros da equipe, cronograma da equipe, bate-papos e arquivos dos últimos 90 dias.

Cada equipe do StaffHub precisa de um Grupo do Office 365 correspondente. Se uma equipe do StaffHub não tiver um Grupo do Office 365 associado a ele, um será criado automaticamente para você para dar suporte à transição. Devido à diferença na nomeação da equipe e do grupo entre o Teams e o StaffHub, você poderá ver um nome de equipe diferente no Teams.

À medida que você faz a transição das equipes do StaffHub para o Teams, os usuários não terão mais acesso a seus cronogramas no StaffHub e serão redirecionados para o Shifts no Teams. É recomendável comunicar essa alteração a toda a sua organização para minimizar as interrupções e incentivar os usuários a adotar e explorar o Teams. Caso tenha o Azure AD Premium, você pode [executar um relatório](run-report-to-show-staffhub-usage.md) para obter uma lista de usuários do StaffHub em sua organização que precisam saber mais sobre essa alteração.  

Não há uma opção de reversão após mover uma equipe do StaffHub para o Teams.

### <a name="user-experience-when-you-move-a-team"></a>Experiência do usuário ao mover uma equipe

O tempo de inatividade é mínimo (menos de um segundo, se houver) para os usuários quando sua equipe for migrada do StaffHub para o Shifts no Teams. Os usuários podem continuar usando o StaffHub até que a mudança para o Teams seja concluída. Quando a mudança estiver concluída, os membros da equipe verão uma mensagem informando que eles precisam começar a usar o Shifts no Teams para acessar o cronograma da equipe. Veja um exemplo da mensagem que os usuários veem no StaffHub após a equipe do StaffHub ser movida para o Teams.

![Exemplo da mensagem que os usuários visualizam. ](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Exemplo da mensagem que os usuários veem no StaffHub depois que a equipe do StaffHub é movida para o Teams")

## <a name="prepare"></a>Preparação

Veja como se preparar para a mudança para o Teams.

### <a name="check-that-prerequisites-are-met"></a>Verifique se os pré-requisitos foram atendidos

Antes de mudar uma equipe do StaffHub para o Teams, certifique-se de que:

- O usuário conectado é um administrador global.
- O Teams está habilitado para todos os usuários no locatário.
- A criação de grupos do Office 365 está habilitada no locatário.
- O teamId do StaffHub é válido.
- A equipe do StaffHub contém membros. 
- Todos os membros da equipe do StaffHub estão vinculados a uma conta do Azure AD. 

Se esses pré-requisitos não forem atendidos, a solicitação de movimentação falhará. 

### <a name="assign-teams-licenses"></a>Atribuir licenças ao Teams

Cada usuário deve ter uma licença ativa do Microsoft 365 ou do Office 365 de um [plano elegível](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) e deve ter uma licença do Teams. Atribuir uma licença do Teams aos usuários lhes concede acesso ao Teams.

Gerencie as licenças do Teams no centro de administração do Microsoft 365. Para saber mais, confira [Gerenciar o acesso dos usuários ao Teams](../../user-access.md).

> [!NOTE]
> Se a sua organização usa o Skype for Business e você não está pronto para mover todos os usuários para o Temas, é possível habilitar o Teams para os seus Firstline Workers que possam executar o Teams junto com o Skype for Business. Neste modo de coexistência, chamado *Ilhas*, cada aplicativo cliente funciona como uma solução separada. Para saber mais, confira [Entender a coexistência e a interoperabilidade do Microsoft Teams e do Skype for Business](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).

### <a name="install-the-staffhub-powershell-module"></a>Instalar o módulo PowerShell do StaffHub

Se você ainda não [instalou o módulo PowerShell do StaffHub](install-the-staffhub-powershell-module.md). 

### <a name="provision-accounts-for-staffhub-users-who-dont-have-an-identity-in-azure-ad"></a>Provisionar contas para usuários do StaffHub que não têm uma identidade no Azure AD

Cada gerente e membro da equipe devem ter uma identidade no Azure Active Directory (Azure AD). Se um usuário ainda não tiver uma identidade no Azure AD, provisione uma conta para ele. Veja como. 

#### <a name="get-a-list-of-all-users-on-staffhub-teams-that-have-team-members-that-arent-provisioned-with-an-azure-ad-account"></a>Obtenha uma lista de todos os usuários na equipe do StaffHub que têm membros da equipe que não estão provisionados com uma conta do Azure AD

Execute:
```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
foreach($team in $StaffHubTeams[0]) {Get-StaffHubMember -TeamId $team.Id | where {$_.Email -eq $null -or $_.State -eq "Invited"}}
```

#### <a name="provision-the-account"></a>Provisionar a conta

Siga um destes procedimentos:

- Converta e vincule a conta a uma conta provisionada.

  Os gerentes e proprietários da equipe do StaffHub podem converter uma conta fictícia ou inativa e vinculá-la a uma conta provisionada no StaffHub alterando o endereço de email do usuário para um UPN válido na página de configurações da equipe do StaffHub.

- Remova a conta não provisionada e, em seguida, adicione a conta novamente usando o UPN.
    1. Execute o cmdlet [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) para remover a conta não provisionada da equipe do StaffHub.
    2. Execute o cmdlet [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) para adicionar a conta novamente à equipe do StaffHub usando o UPN. 

### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a>Atribua a política de configuração do aplicativo FirstlineWorker aos usuários

O Teams possui uma política interna de configuração de aplicativos FirstlineWorker que você pode usar para personalizar o Teams para destacar os aplicativos mais importantes para os Firstline Workers da sua organização. Quando você atribui essa política aos usuários, os aplicativos da política são fixados na barra de aplicativos do Teams para um acesso rápido e fácil. Outros aplicativos adicionados ao Teams podem ser encontrados na barra do aplicativo clicando em **... Mais aplicativos** na área de trabalho do Teams e nos clientes Web e ao passar o dedo para cima no cliente para dispositivo móvel do Teams. Por padrão, a política de configuração do aplicativo FirstlineWorker inclui a atividade, turnos, chat e aplicativos de chamada.

Para obter as etapas sobre como atribuir a política de configuração do aplicativo FirstlineWorker aos [usuários, confira ](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams) usar a política de configuração do aplicativo FirstlineWorker para fixar turnos em equipes. Depois de atribuir uma política, pode levar até 24 horas para entrar em vigor.

É recomendável concluir esta etapa pelo menos uma semana antes de mover as equipes e usuários do StaffHub para o Teams. Quando os usuários estão no Teams, confirme se eles podem ver e acessar o aplicativo turnos.

Você também pode criar políticas personalizadas de configuração de aplicativos e editar as configurações na política de configuração do aplicativo global. Para saber mais, confira [o gerenciamento de políticas de configuração de aplicativos no Teams](../../teams-app-setup-policies.md).

### <a name="onboard-users-to-teams"></a>Integrar usuários ao Teams

Como parte da sua estratégia de integração, forneça treinamento e orientações para os usuários que os ajudem a se familiarizar com o Teams. Compartilhe os seguintes recursos com usuários, para que eles saibam onde obter os clientes, os treinamentos e o suporte do Teams:

- [Cliente Web do Teams](https://teams.microsoft.com)
- [Links para download de clientes para área de trabalho e dispositivos móveis](https://teams.microsoft.com/downloads)
- [Vídeos de treinamento do Teams](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)
- [Documentação da Ajuda do Teams](https://support.office.com/teams)

Para obter instruções sobre como implantar o Teams e conduzir a adoção do Teams, confira [como implantar o Teams](../../How-to-roll-out-teams.md)e [adotar o Teams](../../adopt-microsoft-teams-landing-page.md).

## <a name="conduct-a-pilot"></a>Conduzir um piloto

Recomendamos que você comece movendo duas ou três equipes de StaffHub para um grupo seleto de pioneiros. Executar um piloto ajuda você a refinar seu plano de transição e garantir que você esteja pronto para migrar todas as equipes de StaffHub da sua organização do Teams. Também identifica os especialistas que podem ajudar a impulsionar a adoção em toda a organização. Se você for um pequeno negócio que não precisa de uma abordagem em fases, as etapas nesta seção talvez sejam tudo o que você precisa fazer no StaffHub para o Teams.

### <a name="identify-pilot-teams"></a>Identificar equipes piloto

Aproxime para identificar duas ou três equipes piloto. Todos os membros da equipe devem se comprometer com o uso de turnos no Teams para gerenciar suas agendas e se comunicar e colaborar entre si.

### <a name="identify-team-champions"></a>Identificar os campeões da equipe

Identifique campeões nas equipes piloto e os convoque para ajudar a começar difundir turnos. Os campeões da equipe são apaixonados pelo que fazem, compartilhando suas próprias novidades para oferecer suporte e orientações aos membros da equipe. Os campeões da equipe podem ser proprietários ou gerentes da equipe.

Os campeões da equipe devem garantir que os membros da equipe sejam configurados por um tempo dedicado para que todos possam [ obter clientes do Teams](../../get-clients.md), entre no Teams e verifique suas agendas em turnos e comece a conversar com os outros. Os usuários que já conhecem o StaffHub estarão funcionando rapidamente em turnos. Você também pode apontá-los para a [Ajuda de turnos](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) para obter ajuda adicional.

### <a name="move-a-staffhub-team"></a>Mover uma equipe do StaffHub

Use estas etapas para mover uma equipe do StaffHub por vez. Recomendamos essa abordagem para suas equipes piloto. Mais tarde, quando você estiver pronto para migrar todas as equipes do StaffHub da sua organização, confira[ o artigo migrar suas equipes do StaffHub](#move-your-staffhub-teams) para obter as etapas sobre como mover várias equipes de cada vez.

Execute o seguinte para mover uma equipe do StaffHub.

```
Move-StaffHubTeam -TeamId <String>
```
Exemplo:

```
Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

Veja um exemplo da resposta que você obtém ao enviar uma solicitação para mover uma equipe do StaffHub para o Teams.

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ---------------------------------------    ----------------------------------------    ---------------------------          
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

Faça o seguinte para verificar o status das suas solicitações de movimentação.

```
Get-TeamMigrationJobStatus <String>
```
Exemplo:

```
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"
```

Veja um exemplo da resposta que você obtém quando uma mudança está em andamento.

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

### <a name="move-files-from-a-staffhub-team-to-teams"></a>Mova os arquivos de uma equipe do StaffHub para o Teams

Essa etapa só será aplicada se a equipe do StaffHub que você moveu para o Teams tiver arquivos que você deseja migrar para o Teams. Você pode mover os arquivos diretamente no SharePoint Online ou usando o PowerShell. 

#### <a name="in-sharepoint-online"></a>No SharePoint Online

Veja [como mover arquivos no SharePoint Online](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30).

#### <a name="using-powershell"></a>Usando o PowerShell

Baixe e instale o [Shell de Gerenciamento do SharePoint Online](https://www.microsoft.com/download/details.aspx?id=35588), caso ainda não tenha feito. Ela contém os cmdlets de que você precisa para mover arquivos.  

Use o [cmdlet Connect-PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) para conectar-se ao site de equipe do SharePoint Online.

```
Connect-PnPOnline -Url https://<sharepoint URL>/sites/<Group Name>  
```

Para cada arquivo que você deseja mover de StaffHub para o Teams, use o [cmdlet Move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) para mover o arquivo.

```
Move-PnPFile -ServerRelativeUrl "/sites/<Group Name>/Shared Documents/<File Name>" -TargetUrl "/sites/<Group Name>/Shared Documents/General/<File Name>" 
```

Para mover vários arquivos, execute o loop sobre os arquivos e execute o segundo comando no loop. Não é necessário repetir o primeiro comando se a sessão permanecer ativa.

## <a name="go-beyond-your-pilot-and-move-all-staffhub-teams"></a>Ir além do seu piloto e mover todas as equipes do StaffHub

### <a name="raise-awareness"></a>Aumentar a conscientização

Quando estiver pronto para ir além das suas equipes piloto e mover as equipes de StaffHub da sua organização para o Teams, é importante primeiro comunicar a alteração em toda a organização. Divulgue a palavra sobre turnos e a transição para as equipes aumentar a conscientização, gerar entusiasmo e impulsionar a adoção.

### <a name="move-your-staffhub-teams"></a>Migrar suas equipes do StaffHub

Use estas etapas para mover equipes do StaffHub em massa. Você pode optar por mover todas as equipes de StaffHub da sua organização ou mover equipes específicas do StaffHub. Se você quiser mover uma equipe do StaffHub por vez, confira [migrar para uma equipe do StaffHub](#move-a-staffhub-team).

#### <a name="move-all-staffhub-teams"></a>Migrar todas as equipes do StaffHub

Execute o seguinte procedimento para obter uma lista de todas as equipes de StaffHub na sua organização.

```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

Então, execute o seguinte para mover todas as equipes.

```
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

Veja um exemplo de resposta.

Para todas as equipes que já foram movidas para o Teams ou já existem no Teams, a jobId será "nula", uma vez que não será necessário enviar um trabalho para migrar essa equipe.

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams"></a>Mover equipes StaffHub específicas

Execute o seguinte procedimento para obter uma lista de todas as equipes lds de StaffHub na sua organização.

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

Nos resultados retornados pelo `Get-StaffHubteamsForTenant` cmdlet executado anteriormente, selecione as IDs da equipe que você deseja mover e, em seguida, adicione-as a um arquivo CSV (valores separados por vírgula).

Veja um exemplo de como o arquivo CSV deve ser formatado.

|Id  |
|---------|
|TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f<br>TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000<br>TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000<br>TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000|

Depois de criar o arquivo CSV, execute o seguinte procedimento para mover as equipes especificadas no arquivo CSV.

```
$StaffHubTeams = Import-Csv .\teams.csv
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```
### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams"></a>Confirme se suas equipes do StaffHub migraram para o Teams

Execute o seguinte procedimento para obter uma lista de todas as equipes em turnos na sua organização. 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

### <a name="move-files-from-your-staffhub-teams-to-teams"></a>Mova os arquivos de suas equipes do StaffHub para o Teams

Se as equipes do StaffHub que você moveu contiverem arquivos que você também deseja migrar para o Teams, confira [migrar arquivos de uma equipe do StaffHub para o Teams](#move-files-from-a-staffhub-team-to-teams).

## <a name="monitor-teams-usage"></a>Monitorar o uso do Teams

Os relatórios de uso podem ajudar você a entender melhor os padrões de uso e, com os comentários dos usuários, fornecer informações para orientar a implantação geral e indicar onde priorizar os esforços de treinamento e comunicação. Como turnos é um aplicativo do Teams, você pode exibir o uso por meio de relatórios da equipe. Para obter mais informações, confira [relatórios do Teams no centro de Administração do Microsoft Teams](../../teams-analytics-and-reports/teams-reporting-reference.md) e[do relatórios de atividades do Teams o centro de administração do Microsoft 365.](../../teams-activity-reports.md)

## <a name="troubleshooting"></a>Solução de Problemas 

**Quando você tenta migrar arquivos do StaffHub para o Teams, você recebe a mensagem de erro "permissão negada".**

Isso pode ocorrer se você estiver tentando migrar arquivos em um grupo privado do Office 365 para o qual você não é membro. Se esse for o caso, use o [cmdlet AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) para adicionar-se à equipe do StaffHub e, em seguida, mova os arquivos. Depois de mover os arquivos, use o [cmdlet Remove-](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) StaffHubMember para remover-se da equipe. 

**Quando tenta migrar arquivos do StaffHub para o Teams, você recebe uma mensagem de erro informando que a pasta geral não existe.**

Execute o seguinte comando para adicionar a pasta Geral ao SharePoint e, em seguida, tente novamente:

  ```
  Add-PnPFolder -Name General -Folder 'Shared Documents'
  ```  

## <a name="related-topics"></a>Tópicos relacionados
- [Como implementar o Microsoft Teams](../../How-to-roll-out-teams.md)
- [O Microsoft StaffHub será desativado](microsoft-staffhub-to-be-retired.md)
- [Gerencie o aplicativo Turnos para sua organização no Microsoft Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Referência do PowerShell do StaffHub](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
