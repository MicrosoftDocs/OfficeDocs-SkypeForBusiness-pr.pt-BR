---
title: Perguntas frequentes sobre governança do Microsoft Education para administradores
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Respostas para perguntas frequentes de administradores de grupos do Microsoft Education que usam o Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f8f8593d598901c71590cc395eb45b0bac7cf4f9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812901"
---
# <a name="microsoft-education-governance-faq-for-admins"></a>Perguntas frequentes sobre governança do Microsoft Education para administradores

> [!Tip]
> Assista à sessão a seguir para saber mais sobre gerenciamento no Microsoft Teams: [Governança, gerenciamento e ciclo de vida no Microsoft Teams](https://aka.ms/teams-governance)

## <a name="how-do-i-control-team-creation-im-worried-students-are-going-to-create-inappropriate-teams"></a>Como faço para controlar a criação da equipe? Estou preocupado que os alunos criem equipes inadequadas.

Para evitar nomes inadequados ou enganoso ou apenas para fornecer mais estrutura sobre como as equipes são nomeadas, você pode usar a política de nomeação de Grupos do Microsoft 365 (atualmente em visualização):

-   **Política de nomeação prefixo-sufixo** Você pode usar prefixos ou sufixos para definir a convenção de nomen como equipes (grupos), por **exemplo,** GRP_US_My Group_Engineering. Os prefixos e sufixos podem ser cadeias de caracteres fixos ou atributos do usuário (como **[Departamento]**) que são adicionados ao nome com base no usuário que está criando a equipe.
-   **Palavras bloqueadas personalizadas** Você pode carregar um conjunto de palavras que os usuários em uma organização específica são impedidos de usar em nomes de equipes que criam. Por exemplo, você pode bloquear o uso dos termos **CEO,** **Folha** de Pagamento e **RH** em nomes de equipe para grupos aos que eles não se aplicam.
-   **Classificação** Você pode criar classificações que os usuários em sua organização podem definir quando criam um Grupo do Microsoft 365. 

> [!IMPORTANT]
> Usar a Política de Nomeação de Grupos do Microsoft 365 requer licenças do Azure Active Directory Premium P1 ou licenças do Azure AD Basic EDU para cada usuário exclusivo que seja membro de um ou mais grupos do Microsoft 365.

Para obter instruções detalhadas, consulte a política de nomen como [nomear grupos do Office.](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)

> [!Note]
> Se as equipes são criadas automaticamente usando a entrada de outro sistema (por exemplo, Sincronização de Dados da Escola), verifique se os dados de entrada estão de acordo com a política de nomeação que você configurou; se isso não ocorrer, a criação de equipe falhará.

## <a name="can-i-see-who-created-a-team"></a>Posso ver quem criou uma equipe?

Para descobrir quem criou uma equipe específica, consulte Pesquisar o [log de auditoria de eventos no Microsoft Teams.](audit-log-events.md)

## <a name="can-i-control-who-can-create-teams"></a>Posso controlar quem pode criar equipes?

Em geral, recomendamos não impedir que qualquer pessoa criar equipes. Se todos puderem criar equipes, é mais provável que o Teams seja amplamente adotado. Docentes, professores ou alunos podem usar o Teams para criar grupos de estudo ou grupos de interesse especial. Isso ajudará o Teams a ser aceito dentro e fora da sala de aula.

Em nossa experiência, a educação do usuário ajuda a garantir o uso responsável do Teams. Assim que os usuários entendem que a criação de equipes não é anônima, eles entendem as implicações da criação delas de forma eficiente e tendem a se afastar do uso incorretamente da ferramenta.

Se tiver certeza de que deseja controlar quem pode criar equipes, confira Gerenciar quem pode criar Grupos do [Microsoft 365.](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)

## <a name="how-do-i-automatically-create-a-team-for-each-course-at-the-beginning-of-the-semester-or-quarter"></a>Como criar automaticamente uma equipe para cada curso no início do semestre ou trimestre?

No início de cada semestre ou trimestre, você precisará de várias novas equipes. Pode fazer sentido tomar uma abordagem automatizada para criar essas equipes automaticamente, preencher-as com os usuários certos e definir as permissões corretas:

-   O School Data Sync pode criar Grupos do Microsoft 365 para Exchange Online e SharePoint Online, equipes de classe para blocos de anotações do Microsoft Teams e classe do OneNote, grupos escolares do Intune for Education, integração de lista e SSO (inscrição única) para muitos outros aplicativos de terceiros. Saiba mais em [Visão Geral do School Data Sync.](https://docs.microsoft.com/schooldatasync/overview-of-school-data-sync)
-   Com o PowerShell, você pode criar equipes e canais e definir configurações automaticamente. Confira [o Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.
-   Você pode usar a API do Microsoft Graph (atualmente em beta) para criar, configurar, clonar e arquivar equipes. Consulte [Usar a API do Microsoft Graph para trabalhar com o Microsoft Teams](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) para obter mais informações.

> [!TIP]
> O School Data Sync cria um Grupo do Microsoft [](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945) 365 para cada classe sincronizada e habilita a associação oculta a um grupo para que somente professores e alunos da classe possam ver os membros dessa classe. Se estiver usando um processo diferente para criar grupos de classe, use o parâmetro HiddenGroupMembershipEnabled do cmdlet New-UnifiedGroup para atender aos mesmos requisitos de privacidade.

## <a name="how-do-i-deal-with-teams-when-the-semester-or-quarter-ends"></a>Como faço para lidar com equipes quando o semestre ou trimestre termina?

Recomendamos que você pense primeiro em como deseja lidar com os dados do Teams quando o semestre escolar ou o trimestre terminar: se deseja excluí-los ou mantê-los disponíveis para os alunos mesmo depois de concluirem o curso. Você vai querer manter o calendário escolar em mente para que as políticas definidas não conflitam com feriados. Você pode usar as seguintes ferramentas para implementar sua estratégia:

-   **Política de retenção:** Use isso para excluir todos os dados com mais de uma idade especificados para garantir que os dados antigos são removidos de chats (para todos ou alguns usuários) e canais. Você também pode configurar o Teams para reter o conteúdo para que ele não possa ser excluído. Para saber mais, confira [as políticas de retenção do Microsoft Teams.](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011)
-   **Política de expiração:** Configure as equipes para expirarem após um determinado número de dias. Trinta dias antes da expiração, todos os proprietários de uma equipe são notificados de que sua equipe precisa ser renovada, caso contrário, ela será excluída (embora um administrador possa recuperar equipes excluídas por mais 30 dias). Essa configuração é muito útil para garantir que as equipes nãoutiladas sejam pores do sol. Saiba mais na Política de Expiração de Grupo [do Microsoft 365.](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733)

-   **Equipe de arquivo morto:** Essa configuração coloca as equipes no modo somente leitura. Eles ainda podem ser pesquisados e pesquisados, mas ninguém pode adicionar novas postagens. [Arquivar ou restaurar uma equipe](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7) descreve como os proprietários da equipe podem arquivar uma equipe; Os proprietários da equipe também podem usar [a API do Graph (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) para arquivar ou restaurar uma equipe.
 
> [!IMPORTANT]
> Usar a Política de Expiração de Grupos do Microsoft 365 requer licenças do Azure Active Directory Premium P1 para cada usuário exclusivo que seja membro de um ou mais grupos do Microsoft 365.

## <a name="are-there-team-templates-for-my-faculty-members-to-use-when-creating-a-team"></a>Há modelos de equipe para os membros do corpo docente usarem ao criar uma equipe?

Sim. Os usuários  podem selecionar Criar Equipe a partir do modelo existente ao criar uma nova equipe, e os proprietários do Teams também podem usar a API do [Graph (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) para criar uma nova equipe a partir dos modelos disponíveis.

## <a name="what-tasks-can-i-automate-via-powershell-or-graph"></a>Quais tarefas posso automatizar por meio do PowerShell ou do Graph?

A [API do Microsoft Graph (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) pode fazer o seguinte:

-   Criar uma equipe.
-   Adicione membros e proprietários.
-   Adicionar canais.
-   Adicionar aplicativos.
-   Atalho para essas etapas clonando uma equipe existente e obter suas guias também.
-   Dê ao usuário um link para a equipe que você acabou de criar.
-   Remova membros, proprietários, canais e aplicativos quando não precisar mais deles.
-   Arquive a equipe quando ela não estiver mais ativa. 
-   Exclua a equipe.
-   Criar um thread de canal

[O PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) pode fazer o seguinte:

-   Criar uma equipe.
-   Adicione membros e proprietários.
-   Adicionar canais.
-   Remova membros, proprietários e canais quando você não precisar mais deles.
-   Exclua a equipe.

> [!TIP]
> A API do Graph e os cmdlets do PowerShell estão constantemente adicionando funcionalidade. Verifique com frequência os artigos da [API do Microsoft Graph (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) e do [PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para aprimoramentos de recursos.  


## <a name="can-i-control-what-teams-features-my-faculty-and-students-have-access-to"></a>Posso controlar a quais recursos do Teams meus docentes e alunos têm acesso?

Sim. Você pode usar políticas para controlar recursos específicos de mensagens, reuniões, chamada e eventos ao vivo aos seus usuários. Você pode usar as configurações de todo o locatário para aplicar as mesmas configurações a todos ou aplicar políticas no nível do usuário, se necessário. 

Para obter mais detalhes sobre as políticas do Teams, consulte [Gerenciar as configurações do Microsoft Teams para sua organização.](enable-features-office-365.md)
 
## <a name="can-i-control-what-external-parties-my-faculty-and-students-collaborate-with"></a>Posso controlar com quais partes externas meus docentes e alunos colaboram?

Você pode usar o acesso de convidados para convidar usuários de fora do seu locatário, o que pode ser útil para colaboração em pesquisa ou palestras de convidados:

-   Use a lista de domínios para permitir ou bloquear convidados com base em seu domínio.
-   Ativar e desativar o acesso de convidados para grupos e equipes específicos do Microsoft 365 para controlar quais equipes podem (e não podem) convidar convidados.
-   Use o log de auditoria para ver quais alertas foram enviados para convidados.

Para obter mais informações, consulte [Acesso de convidado em Grupos do Microsoft 365.](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage)

## <a name="what-information-can-i-review-about-existing-teams"></a>Quais informações posso revisar sobre equipes existentes?

Você pode verificar os logs de auditoria para ver:

-   Quem foi convidado como convidado para qual equipe.
-   Quem criou qual equipe.

Para obter mais informações, consulte [Pesquisar o log de auditoria de eventos no Microsoft Teams.](audit-log-events.md)

## <a name="teams-evolves-so-quickly-how-can-i-stay-up-to-date"></a>As equipes evoluem tão rapidamente. Como posso me manter atualizado?

Recomendamos os seguintes recursos para obter as atualizações mais recentes no Teams:

-   [Novidades do Microsoft Teams](https://support.office.com/article/What-s-new-in-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
-   [Blog do Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)
