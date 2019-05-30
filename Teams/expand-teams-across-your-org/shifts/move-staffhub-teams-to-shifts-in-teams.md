---
title: Mova as suas equipes do StaffHub para Turnos do Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 3/29/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Saiba como mover suas equipes do Microsoft StaffHub e agendar dados para turnos no Microsoft Teams.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: b6354c2edd4d8504aeb2c84715b982f6bf793d33
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548290"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a>Mover suas equipes do Microsoft StaffHub para turnos no Microsoft Teams

> [!IMPORTANT]
> A partir de 1 ° de outubro de 2019, o Microsoft StaffHub será desativado. Estamos criando recursos de StaffHub no Microsoft Teams. Hoje, o Teams inclui o aplicativo turnos para gerenciamento de agendamento e recursos adicionais se acumularão ao longo do tempo. O StaffHub deixará de funcionar para todos os usuários em 1 ° de outubro de 2019. Qualquer pessoa que tentar abrir o StaffHub será exibida uma mensagem direcionando-o para o download do teams. Para saber mais, confira [Microsoft StaffHub para ser desativado](microsoft-staffhub-to-be-retired.md).

> O recurso discutido neste artigo ainda não foi lançado. Ele foi anunciado e estará disponível em breve, no início de junho de 2019. Se você for um administrador, poderá descobrir quando isso estará disponível no centro de mensagens (no centro de administração do [Microsoft 365](https://portal.office.com/adminportal/home)).

O aplicativo turnos no Microsoft Teams oferece uma abordagem simples para o gerenciamento de cronogramas e o fluxo constante de trocas de turnos e cancelamentos que ocorrem diariamente. Os membros da equipe podem acessar o cronograma e deslocar as informações diretamente no aplicativo e em seus dispositivos para definir suas preferências, gerenciar seus cronogramas e solicitar folga.

Este artigo apresenta uma orientação sobre como mover as equipes do StaffHub da sua organização e agendar dados para turnos no Microsoft Teams. Seja você uma pequena empresa com uma ou duas equipes do StaffHub ou uma grande empresa com centenas de equipes do StaffHub, você encontrará as diretrizes de administração necessárias para ajudar a fazer sua transição para o Microsoft Teams com êxito.

Você deve ser um administrador global para executar as etapas neste artigo. Se ainda não tiver feito isso, examine as [perguntas frequentes sobre](microsoft-staffhub-to-be-retired.md) a descontinuação do StaffHub para obter respostas para qualquer pergunta que você tenha. 

## <a name="what-you-need-to-know-about-the-move-to-teams"></a>O que você precisa saber sobre a mudança para o Teams

### <a name="when-to-move-to-teams"></a>Quando mover para o Microsoft Teams

A partir de 1 ° de outubro de 2019, a StaffHub será desativada. Recomendamos que você comece a usar o Microsoft Teams hoje e comece a fazer a transição das equipes e dos usuários da sua organização do StaffHub. Com o gerenciamento de agendamento sendo o recurso mais comumente usado no StaffHub, recomendamos que você use o aplicativo turnos no Microsoft Teams, avançando.

### <a name="what-is-moved-to-teams"></a>O que é movido para o Microsoft Teams

Detalhes do usuário, informações do cronograma e dados de chat e arquivos são migrados para o Microsoft Teams. Isso inclui associação da equipe, cronogramas da equipe e chats e arquivos dos últimos 90 dias.

Cada equipe do StaffHub precisa de um grupo do Office 365 correspondente. Se uma equipe do StaffHub não tiver um grupo do Office 365 associado a ela, uma será criada automaticamente para você dar suporte à transição. Devido à diferença na nomenclatura de equipes e grupos entre o Teams e o StaffHub, você pode ver um nome de equipe diferente no Teams.

À medida que você muda de equipe do StaffHub para o Teams, os usuários não têm mais acesso às suas agendas no StaffHub e são redirecionados para turnos no Microsoft Teams. Recomendamos que você comunique essa alteração a toda a sua organização para minimizar as interrupções e incentivar os usuários a adotar e explorar o Microsoft Teams. Se você tiver o Azure AD Premium, poderá [executar um relatório](run-report-to-show-staffhub-usage.md) para obter uma lista de usuários do StaffHub em sua organização que precisam saber mais sobre essa alteração.  

Não há opção de reversão após mover uma equipe do StaffHub para o Microsoft Teams.

### <a name="user-experience-when-you-move-a-team"></a>Experiência do usuário ao mover uma equipe

Há um tempo de inatividade mínimo (menos de um segundo) para os usuários quando sua equipe é comutada de StaffHub para turnos no Teams. Os usuários podem continuar a usar o StaffHub até que a mudança para o Microsoft Teams seja concluída. Quando a mudança for concluída, os membros da equipe verão uma mensagem para informar que precisam começar a usar os turnos no Teams para acessar o cronograma da equipe. Veja um exemplo da mensagem que os usuários verão no StaffHub depois que a equipe do StaffHub for movida para o Microsoft Teams.

![Exemplo da mensagem exibida pelos usuários.] (../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Exemplo da mensagem que os usuários veem no StaffHub após a equipe do StaffHub ser movida para") o Microsoft Teams

## <a name="prepare"></a>Pare

Veja como se preparar para a mudança para o Teams.

### <a name="assign-teams-licenses"></a>Atribuir licenças do Teams

Cada usuário deve ter uma licença ativa do Microsoft 365 ou do Office 365 de [um plano elegível](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) e deve receber uma licença do teams. Atribuir uma licença do teams aos usuários permite que eles acessem o Microsoft Teams.

Você gerencia as licenças do teams no centro de administração do Microsoft 365. Para saber mais, consulte [gerenciar o acesso do usuário ao Teams](../../user-access.md).

> [!NOTE]
> Se a sua organização usa o Skype for Business e você não está pronto para mover todos os usuários para o Microsoft Teams, você pode habilitar o Microsoft Teams para os seus primeiros trabalhadores que podem executar o Microsoft Teams junto ao Skype for Business. Nesse modo de coexistência, chamado de *ilhas*, cada aplicativo cliente Opera como uma solução separada. Para saber mais, consulte [entender o Microsoft Teams e a coexistência e interoperabilidade do Skype for Business](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).

### <a name="provision-accounts-for-staffhub-users-who-dont-have-an-identity-in-azure-ad"></a>Provisionar contas para usuários do StaffHub que não têm uma identidade no Azure AD

Cada gerente e membro da equipe devem ter uma identidade no Azure Active Directory (Azure AD). Se um usuário ainda não tiver uma identidade no Azure AD, Provisione uma conta para elas. Veja como.

- StaffHub os proprietários e gerentes de equipe podem converter uma conta fictícia ou inativa e vinculá-la a uma conta provisionada no StaffHub alterando o endereço de email do usuário para um UPN válido na página de configurações da equipe do StaffHub.

- Os administradores podem executar os cmdlets [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) e [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) para remover uma conta não provisionada de uma equipe do StaffHub e adicionar a conta novamente usando o UPN.

### <a name="install-the-staffhub-powershell-module"></a>Instalar o módulo PowerShell do StaffHub

Se ainda não fez isso, [Instale o módulo StaffHub PowerShell](install-the-staffhub-powershell-module.md).

Quando você move uma equipe do StaffHub, a solicitação move verifica se há pré-requisitos. Veja os motivos pelos quais uma solicitação de mudança pode falhar:

- O usuário conectado não é um administrador global
- O Microsoft Teams está desabilitado para todos os usuários no locatário
- A criação de grupos do Office 365 está desabilitada no locatário
- O StaffHub TeamID não é válido ou não tem membros
- A equipe do StaffHub inclui membros que não estão vinculados a uma conta do Azure AD  

## <a name="run-a-pilot"></a>Executar um piloto

Recomendamos que você comece movendo duas ou três equipes StaffHub para um grupo seleto de pioneiros. A execução de um piloto ajuda você a refinar seu plano de transição e garantir que você esteja pronto para mover todas as equipes do StaffHub da sua organização para o Microsoft Teams. Ele também identifica campeões que podem ajudar a impulsionar a adoção em toda a sua organização. Se você for uma pequena empresa que não precisa de uma abordagem em fases, as etapas nesta seção podem ser tudo o que você precisa fazer para fazer a mudança do StaffHub para o Microsoft Teams.

### <a name="identify-pilot-teams"></a>Identificar equipes piloto

Tenha acesso à identificação de duas ou três equipes piloto. Todos os membros da equipe devem confirmar o uso de turnos no Teams para gerenciar seus cronogramas e se comunicar e colaborar uns com os outros.

### <a name="identify-team-champions"></a>Identificar especialistas da equipe

Identifique especialistas em nossas equipes piloto e as solicite para ajudar a evangelizar turnos. Os representantes da equipe são apaixonados pelo que fazem, compartilhando suas próprias informações para oferecer suporte e orientação aos membros da equipe. Os campeões da equipe podem ser proprietários ou gerentes da equipe.

Os campeões de equipe devem garantir que os membros da equipe sejam configurados dedicando-se tempo para que todos [obtenham clientes](../../get-clients.md)do Teams, entrem no Teams e confiram suas agendas em turnos e comecem a conversar uns com os outros. Os usuários que já estão familiarizados com o StaffHub estarão em funcionamento rapidamente em turnos. Você também pode apontá-los para a [ajuda](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) de turnos para obter ajuda adicional.

### <a name="move-a-staffhub-team-coming-soon"></a>Mover uma equipe do StaffHub (disponível em breve)

Use estas etapas para mover uma equipe do StaffHub de cada vez. Recomendamos essa abordagem para suas equipes piloto. Mais tarde, quando você estiver pronto para mover todas as equipes do StaffHub da sua organização, consulte [mover suas equipes do StaffHub](#move-your-staffhub-teams-coming-soon) para ver as etapas sobre como mover várias equipes de cada vez.

Execute o seguinte para mover uma equipe do StaffHub.

```
Move-StaffHubTeam -TeamId <String>

Sample:

Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

Veja um exemplo da resposta que você obtém quando envia uma solicitação para mover uma equipe do StaffHub para o Microsoft Teams.

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ---------------------------------------    ----------------------------------------    ---------------------------          
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

Para verificar o status de uma solicitação de movimentação, execute o seguinte.

```
Get-TeamMigrationJobStatus <String>

Sample:
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"

```

Veja um exemplo da resposta que você obtém quando uma mudança está em andamento.

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

## <a name="make-the-transition-from-staffhub-to-teams"></a>Fazer a transição do StaffHub para o Microsoft Teams

### <a name="raise-awareness"></a>Aumentar a conscientização

Quando você estiver pronto para ir além de suas equipes piloto e mover as equipes do StaffHub da sua organização para o Microsoft Teams, é importante primeiro comunicar a alteração em toda a sua organização. Espalhe a palavra sobre turnos e a transição para o Microsoft Teams para aumentar a conscientização, gerar entusiasmo e impulsionar a adoção.

### <a name="move-your-staffhub-teams-coming-soon"></a>Mover suas equipes do StaffHub (em breve)

Use estas etapas para mover as equipes do StaffHub em massa. Você pode optar por mover todas as equipes do StaffHub da sua organização ou mover equipes específicas do StaffHub. Se você quiser mover um StaffHub Teams, um por vez, consulte [mover uma equipe do StaffHub](#move-a-staffhub-team-coming-soon).

#### <a name="move-all-staffhub-teams-coming-soon"></a>Mover todas as equipes do StaffHub (em breve)

Execute o seguinte para obter uma lista de todas as equipes do StaffHub em sua organização.

```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

Em seguida, execute o seguinte para mover todas as equipes.

```
$StaffHubTeams | foreach {Move-StaffHubTeam -TeamId {$_.Id}}
```

Veja um exemplo da resposta.

Para todas as equipes que já foram movidas para o Microsoft Teams ou já existirem no Teams, o jobId será "nulo" porque um trabalho não precisará ser enviado para mover a equipe.

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams-coming-soon"></a>Mover equipes específicas do StaffHub (disponível em breve)

Execute o seguinte para obter uma lista de todas as IDs de equipe do StaffHub em sua organização.

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

Nos resultados retornados pelo `Get-StaffHubteamsForTenant` cmdlet executado anteriormente, selecione as IDs de equipe que você deseja mover e, em seguida, adicione-as a um arquivo CSV (valores separados por vírgula).

Aqui está um exemplo de como o arquivo CSV deve ser formatado.

|%  |
|---------|
|TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f<br>TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000<br>TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000<br>TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000|

Depois de criar o arquivo CSV, execute o seguinte para mover as equipes que você especificou no arquivo CSV.

```
Import-Csv .\teams.txt | foreach {Move-StaffHubTeam -TeamdId {$_.Id}}
```
### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams-coming-soon"></a>Confirme se suas equipes do StaffHub mudaram para o Microsoft Teams (em breve)

Execute o seguinte para obter uma lista de todas as equipes em turnos em sua organização. 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

## <a name="monitor-teams-usage"></a>Monitorar o uso do teams

Os relatórios de uso podem ajudá-lo a entender melhor os padrões de uso e oferecer ideias sobre onde priorizar os esforços de treinamento e comunicação em toda a organização. Como turnos é um aplicativo no Teams, você pode exibir o uso por meio de relatórios do teams. Para obter mais informações, consulte relatórios [do Microsoft Teams no centro de administração do Microsoft Teams](../../teams-analytics-and-reports/teams-reporting-reference.md) e [relatórios de atividade do Microsoft Teams no centro de administração do Microsoft 365](../../teams-activity-reports.md).

## <a name="related-topics"></a>Tópicos relacionados
- [O Microsoft StaffHub será desativado](microsoft-staffhub-to-be-retired.md)
- [Gerencie o aplicativo Turnos para sua organização no Microsoft Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Referência do PowerShell do StaffHub](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
