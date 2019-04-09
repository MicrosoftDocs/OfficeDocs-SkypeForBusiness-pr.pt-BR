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
description: Aprenda a mover suas equipes da Microsoft StaffHub e agendar dados às mudanças na Teams da Microsoft.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: fa224306f3d42d4746f8e8f2276b44208fc568bd
ms.sourcegitcommit: a505869a3cc2fe6fe4ee18bcbe99bf980aa91a86
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2019
ms.locfileid: "31520212"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a>Mover suas equipes da Microsoft StaffHub para mudanças na Teams da Microsoft

> [!IMPORTANT]
> A partir de 1 de outubro de 2019, Microsoft StaffHub será desativada. Estamos compilando recursos StaffHub em Teams da Microsoft. Hoje, equipes inclui o aplicativo desloca para o gerenciamento de agenda e recursos adicionais serão distribuir ao longo do tempo. StaffHub irá parar de funcionar para todos os usuários em 1 de outubro de 2019. Qualquer pessoa que tenta abrir StaffHub será mostrada uma mensagem direcionando-os para baixar as equipes. Para saber mais, consulte [Microsoft StaffHub para ser retirado](microsoft-staffhub-to-be-retired.md).

> O recurso discutido neste artigo ainda não foi liberado. Ela será foi anunciada e estarão disponíveis em breve, até o final de abril de 2019. Se você for um administrador, você pode descobrir quando isso estarão disponível no Centro de mensagens (no [Centro de administração do Microsoft 365](https://portal.office.com/adminportal/home)).

O aplicativo desloca em equipes fornece uma abordagem simples para gerenciar agendamentos e o fluxo constante de trocas de shift e cancelamentos que ocorrem em uma base diária. Os membros da equipe podem acessar sua agenda e shift informações diretamente no aplicativo e nos seus dispositivos para definir suas preferências, gerenciar suas próprias agendas e tempo de solicitação.

Este artigo explora como mover as equipes de StaffHub da sua organização e agendar dados às mudanças na equipes. Se você estiver em uma pequena empresa com uma ou duas equipes de StaffHub ou uma empresa de grande porte com centenas de equipes StaffHub, aqui você encontrará as orientações de admin, que você precisa para ajudar a tornar sua transição para equipes bem-sucedido.

Você deve ser um administrador global para executar as etapas neste artigo. Se você ainda não tiver feito isso, dê uma olhada através de [aposentadoria StaffHub perguntas Frequentes](microsoft-staffhub-to-be-retired.md) para obter respostas às dúvidas que você pode ter. 

## <a name="what-you-need-to-know-about-the-move-to-teams"></a>O que você precisa saber sobre a movimentação para equipes

### <a name="when-to-move-to-teams"></a>Quando se mover para equipes

A partir de 1 de outubro de 2019, StaffHub será desativada. Recomendamos que você inicie com equipes hoje e começar a fazer a transição de equipes e os usuários de StaffHub da sua organização. Com o gerenciamento de agenda sendo o recurso comumente usadas no StaffHub, é recomendável que você usa o aplicativo de mudanças em equipes avançando.

### <a name="what-is-moved-to-teams"></a>O que é movido para equipes

Detalhes do usuário, informações de agenda e bate-papo e o arquivo de dados são uma transição às equipes. Isso inclui a associação da equipe, agendamentos de equipe e bate-papos e arquivos dos últimos 90 dias.

Cada equipe StaffHub necessita de um grupo de 365 correspondente do Office. Se uma equipe StaffHub não tiver um grupo do Office 365 associado a ela, um é criado automaticamente para você ofereça suporte a transição. A diferença na equipe e nomeação de grupo entre equipes e StaffHub, você poderá ver um nome diferente de equipe em equipes.

Como fazer a transição de equipes de StaffHub às equipes, os usuários não terá mais acesso a suas próprias agendas em StaffHub e são redirecionados para mudanças na equipes. Recomendamos que você se comunica essa alteração em toda a organização para minimizar a interrupção e incentivar os usuários a adotar e explore equipes.

## <a name="prepare"></a>Preparar

Aqui está como se preparar para a mudança para equipes.

### <a name="assign-teams-licenses"></a>Atribuir licenças do Teams

Cada usuário deve ter uma licença do Microsoft 365 ou do Office 365 ativa de [um plano de elegível](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) e deve ter uma licença de equipes. Atribuir uma licença de equipes a usuários lhes acesso às equipes.

Você gerenciar licenças de equipes no Centro de administração do Microsoft 365. Para saber mais, consulte [Manage user access às equipes](../../user-access.md).

> [!NOTE]
> Se sua organização usa Skype para negócios e você não estiver pronto para migrar todos os seus usuários para equipes, você poderá habilitar equipes para seus funcionários de Firstline que poderá executar equipes junto com Skype para negócios. Neste modo de coexistência, chamado *Ilhas*, cada aplicativo cliente opera como uma solução separada. Para saber mais, consulte [entender equipes e Skype para interoperabilidade e coexistência de negócios](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).

### <a name="provision-accounts-for-staffhub-users-who-dont-have-an-identity-in-azure-ad"></a>Provisionar contas para usuários StaffHub que não têm uma identidade no Azure AD.

Cada gerente e um membro da equipe precisam ter uma identidade no Windows Azure Active Directory (AD Azure). Se um usuário já não tenha uma identidade no Azure AD, provisione uma conta para eles. Veja como.

- Os gerentes e os proprietários de equipe StaffHub podem converter uma conta fictícia ou inativa e vinculá-lo a uma conta provisionada no StaffHub, alterando o endereço de email do usuário para um UPN válido, na página de configurações da equipe do StaffHub.

- Administradores podem executar o [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) e cmdlets de [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) para remover uma conta não provisionado de uma equipe de StaffHub e adicione a conta de volta usando o UPN.

### <a name="install-the-staffhub-powershell-module"></a>Instale o módulo StaffHub PowerShell

Se você ainda não estiver, [Instale o módulo de StaffHub PowerShell](install-the-staffhub-powershell-module.md).

Quando você move uma equipe StaffHub, a solicitação de movimentação verifica os pré-requisitos. Eis motivos por que uma solicitação de movimentação pode falhar:

- O usuário conectado não é um administrador global
- As equipes está desabilitada para todos os usuários no locatário
- Criação de grupos do Office 365 está desabilitada no locatário
- O teamId StaffHub não é válida ou não possui membros
- A equipe de StaffHub inclui membros que não estão vinculados a uma conta do Windows Azure AD  

## <a name="run-a-pilot"></a>Executar um piloto

Recomendamos que você inicie movendo dois ou três equipes de StaffHub para um grupo seleto de usuários iniciais. Executar um piloto ajuda refinar seu plano de transição e certifique-se de que você está pronto para mover as equipes de StaffHub todos da sua organização para equipes. Ele também identifica campeões que podem ajudar incentivar a adoção em toda a organização. Se você tem uma pequena empresa que não precisa de uma abordagem em fases, as etapas desta seção podem ser tudo o que você precisa para fazer a opção de StaffHub com equipes.

### <a name="identify-pilot-teams"></a>Identificar as equipes piloto

Chegar aos identificar dois ou três equipes piloto. Todos os membros da equipe devem confirmar usando desloca nas equipes para gerenciar suas próprias agendas e se comunicar e colaborar entre si.

### <a name="identify-team-champions"></a>Identificar os campeões de equipe

Identificar campeões entre equipes piloto e inscrevê-los para ajudar a Pregue desloca. Campeões de equipe são entusiasmados pela sobre o que isso acontece, compartilhamento de seus próprios lições para oferecer suporte e orientações para membros da equipe. Campeões da equipe podem ser proprietários de equipe ou gerentes.

Verifique se campeões equipe membros da equipe são configurada pela dedicar tempo todos para [obter os clientes de equipes](../../get-clients.md), entrar com equipes e check-out de suas próprias agendas em desloca e iniciar o bate-papo uns com os outros. Usuários que já estão familiarizados com StaffHub estará em funcionamento rapidamente no desloca. Você também pode apontá-los para [Ajudar a desloca](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) para obter ajuda adicional.

### <a name="move-a-staffhub-team-coming-soon"></a>Mover uma equipe de StaffHub (em breve)

Use estas etapas para mover uma equipe de StaffHub por vez. Recomendamos essa abordagem para suas equipes piloto. Posteriormente, quando estiver pronto para migrar as equipes de StaffHub todos da sua organização, consulte [mover suas equipes StaffHub](#move-your-staffhub-teams-coming-soon) para obter etapas sobre como mover várias equipes de cada vez.

Execute o seguinte procedimento para mover uma equipe de StaffHub.

```
Move-StaffHubTeam -Identity <String>
```

Aqui está um exemplo da resposta obtido quando você envia uma solicitação para mover uma equipe StaffHub para equipes.

```
    jobId   teamId                                      teamAlreadyInMicrosofteams  
    -----   ------                                      ------------          
        1   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   True
```

Para verificar o status de uma solicitação de movimentação, execute o seguinte.

```
Get-TeamMigrationJobStatus <Int32>
```

Aqui está um exemplo da resposta obtido quando uma movimentação está em andamento.

```
    jobId   status       teamId                                     isO365GroupCreated  Error
    -----   ------       ------                                     ------------------  -----    
        1   InProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  True                None
```

## <a name="make-the-transition-from-staffhub-to-teams"></a>Fazer a transição de StaffHub às equipes

### <a name="raise-awareness"></a>Aumente a conscientização

Quando você está pronto para ir além suas equipes piloto e mover as equipes de StaffHub da sua organização para equipes, é importante se comunicar pela primeira vez a alteração em sua organização. Difundir o word sobre mudanças e a transição para equipes atenção, estimular o interesse e direcionar a adoção.

### <a name="move-your-staffhub-teams-coming-soon"></a>Mover suas equipes StaffHub (em breve)

Use estas etapas para mover StaffHub equipes em massa. Você pode optar por mover as equipes de StaffHub todos da sua organização ou mover equipes de StaffHub específicas. Se você deseja mover que staffhub às equipes um de cada vez, consulte [Mover uma equipe de StaffHub](#move-a-staffhub-team-coming-soon).

#### <a name="move-all-staffhub-teams-coming-soon"></a>Mover todas as equipes StaffHub (em breve)

Execute o seguinte procedimento para obter uma lista de todas as equipes de StaffHub em sua organização.

```
$StaffHubTeams = Get-StaffHubTeamsForTenant
```

Em seguida, execute o seguinte procedimento para mover todas as equipes.

```
$StaffHubTeams | foreach {Move-StaffHubTeam -Identity {$_.Id}}
```

Aqui está um exemplo da resposta.

```
    jobId   teamId                                      teamAlreadyInMicrosofteams  
    -----   ------                                      ------------          
        1   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   True
        2   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   False
```

#### <a name="move-specific-staffhub-teams-coming-soon"></a>Mover as equipes de StaffHub específicas (em breve)

Execute o seguinte procedimento para obter uma lista de todas as equipes de StaffHub em sua organização.

```
$StaffHubTeams = Get-StaffHubTeamsForTenant
```

Crie um arquivo de valores separados por vírgula (CSV) e adicione as identificações das equipes que deseja mover.
Aqui está um exemplo.

|ID  |
|---------|
|TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f<br>TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000<br>TEAM_b42d0fa2 - 0fc 9-408b-85ff-c14a26700000<br>TEAM_b42d0fa2 - 0fc 9-408b-85ff-c14a26700000|

Em seguida, execute o seguinte procedimento para mover as equipes que você especificou no arquivo CSV.

```
Import-Csv .\teams.txt | foreach {Move-StaffHubTeam -Identity {$_.Id}}
```

## <a name="monitor-teams-usage"></a>Monitorar o uso de equipes

Relatórios de uso podem ajudá-lo a entender os padrões de uso melhor e a fornecer ideias sobre onde priorizar os esforços de treinamento e comunicação em sua organização. Como desloca é um aplicativo em equipes, você pode visualizar o uso por meio de relatórios de equipes. Para obter mais informações, consulte [equipes relatórios no Centro de administração do Microsoft equipes](../../teams-analytics-and-reports/teams-reporting-reference.md) e [relatórios de atividade de equipes no Centro de administração do Microsoft 365](../../teams-activity-reports.md).

## <a name="related-topics"></a>Tópicos relacionados
- [O Microsoft StaffHub será desativado](microsoft-staffhub-to-be-retired.md)
- [Gerencie o aplicativo Turnos para sua organização no Microsoft Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Referência StaffHub PowerShell](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
