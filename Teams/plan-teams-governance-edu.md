---
title: Perguntas frequentes sobre governança do Microsoft Education para administradores
author: cichur
ms.author: v-mahoffman
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Respostas a perguntas frequentes de administradores de grupos do Microsoft Education que usam Teams.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1e9af313bc24919f96008d7f1ff5bf7383df3260
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774441"
---
# <a name="microsoft-education-governance-faq-for-admins"></a>Perguntas frequentes sobre governança do Microsoft Education para administradores

> [!Tip]
> Assista à sessão a seguir para saber mais sobre gerenciamento em Microsoft Teams: [Governança, gerenciamento](https://aka.ms/teams-governance) e ciclo de vida em Microsoft Teams

## <a name="how-do-i-control-team-creation-im-worried-students-are-going-to-create-inappropriate-teams"></a>Como posso controlar a criação de equipe? Estou preocupado que os alunos criem equipes inadequadas.

Para evitar nomes inadequados ou enganoso ou apenas para fornecer mais estrutura para como as equipes são nomeadas, você pode usar a política de nomenis de Microsoft 365 Grupos (atualmente na visualização):

-   **Política de nomen por prefixo-sufixo** Você pode usar prefixos ou sufixos para definir a convenção de nomenis de equipes (grupos), por exemplo, **GRP_US_My Group_Engineering**. Os prefixos e sufixos podem ser cadeias de caracteres fixas ou atributos de usuário (como **[Departamento]**) adicionados ao nome com base no usuário que está criando a equipe.
-   **Palavras bloqueadas personalizadas** Você pode carregar um conjunto de palavras que os usuários em uma organização específica são impedidos de usar em nomes de equipes que eles criam. Por exemplo, você pode impedir que os termos **CEO,** Folha de **Pagamento** e **RH** de serem usados em nomes de equipe para grupos aos que eles não se aplicam.
-   **Classificação** Você pode criar classificações que os usuários em sua organização podem definir quando eles criam um Microsoft 365 Group. 

> [!IMPORTANT]
> O uso Microsoft 365 Política de Nomenis de Grupos requer licenças Azure Active Directory Premium P1 ou licenças EDU básicas do Azure AD para cada usuário exclusivo que seja membro de um ou mais grupos Microsoft 365.

Para obter instruções detalhadas, [consulte Office política de nomenis de nomes de grupos.](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)

> [!Note]
> Se as equipes são criadas automaticamente usando a entrada de outro sistema (por exemplo, School Data Sync), verifique se os dados de entrada estão em conformidade com a política de nomen efetivação que você configurou; se isso não ocorrer, a criação de equipe falhará.

## <a name="can-i-see-who-created-a-team"></a>Posso ver quem criou uma equipe?

Para descobrir quem criou uma equipe específica, consulte Pesquisar o [log de auditoria](audit-log-events.md)para eventos em Microsoft Teams .

## <a name="can-i-control-who-can-create-teams"></a>Posso controlar quem pode criar equipes?

Em geral, recomendamos evitar que qualquer pessoa tenha criado equipes. Se todos puderem criar equipes, Teams é mais provável que seja amplamente adotado. Professores, professores ou alunos podem usar o Teams para criar grupos de estudo ou grupos de interesse especiais. Isso ajudará a Teams ser aceito dentro e fora da sala de aula.

Em nossa experiência, a educação do usuário ajuda a garantir o uso Teams responsável. Assim que os usuários entenderem que a criação de equipes não é anônima, eles entendem as implicações da criação descuidadamente e tendem a se afastar da utilização incorretamente da ferramenta.

Se você tem certeza de que deseja controlar quem pode criar equipes, consulte [Gerenciar quem pode criar](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)Microsoft 365 Grupos .

## <a name="how-do-i-automatically-create-a-team-for-each-course-at-the-beginning-of-the-semester-or-quarter"></a>Como criar automaticamente uma equipe para cada curso no início do semestre ou trimestre?

No início de cada semestre ou trimestre, você precisará de várias novas equipes. Pode fazer sentido tomar uma abordagem automatizada para criar essas equipes automaticamente, preencher-as com os usuários certos e definir as permissões certas:

-   School Data Sync pode criar grupos Microsoft 365 para Exchange Online e SharePoint Online, equipes de classe para blocos de anotações de classe Microsoft Teams e OneNote, grupos escolares para o Intune para Educação e lista e SSO (SSO) ) integração para muitos outros aplicativos de terceiros. Saiba mais em [Visão geral do School Data Sync](/schooldatasync/overview-of-school-data-sync).
-   Com o PowerShell, você pode criar equipes e canais e configurar configurações automaticamente. Consulte [Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) para obter mais informações.
-   Você pode usar a API do Microsoft Graph (atualmente na versão beta) para criar, configurar, clonar e arquivar equipes. Consulte [Usar a API Graph Microsoft para trabalhar com Microsoft Teams](/graph/api/resources/teams-api-overview) para obter mais informações.

> [!TIP]
> School Data Sync cria um grupo Microsoft 365 para cada classe sincronizada e habilita a associação de grupo oculta para que apenas professores e alunos da classe possam ver os membros dessa classe. [](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945) Se usar um processo diferente para criar grupos de classe, use o parâmetro HiddenGroupMembershipEnabled do cmdlet New-UnifiedGroup para atender aos mesmos requisitos de privacidade.

## <a name="how-do-i-deal-with-teams-when-the-semester-or-quarter-ends"></a>Como lidar com equipes quando o semestre ou trimestre termina?

Recomendamos que você pense primeiro em como você deseja lidar com os dados Teams quando o semestre escolar ou o trimestre terminar: se deseja excluí-los ou mantê-los disponíveis para os alunos, mesmo depois de concluirem o curso. Você deve ter em mente o calendário escolar para que as políticas definidas não conflitam com feriados. Você pode usar as seguintes ferramentas para implementar sua estratégia:

-   **Política de retenção:** Use isso para excluir todos os dados mais antigos do que uma idade especificada para garantir que os dados antigos são removidos de chats (para todos ou alguns usuários) e canais. Você também pode configurar Teams para reter o conteúdo para que ele não possa ser excluído. Para obter mais informações, consulte [Políticas de retenção para Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011).
-   **Política de expiração:** Configure as equipes para expirar após um determinado número de dias. Trinta dias antes da expiração, todos os proprietários de uma equipe são notificados de que sua equipe precisa ser renovada, caso contrário, ela será excluída (embora um administrador possa recuperar equipes excluídas por mais 30 dias). Essa configuração é muito útil para garantir que as equipes nãousadas sejam apagadas. Saiba mais em [Microsoft 365 política de expiração de grupo.](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733)

-   **Equipe de arquivamento:** Essa configuração coloca as equipes no modo somente leitura. Eles ainda podem ser navegados e pesquisados, mas ninguém pode adicionar novas postagens. [Arquivar ou restaurar uma equipe](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7) descreve como os proprietários de equipe podem arquivar uma equipe; Os proprietários de equipe também podem usar [a API Graph (beta)](/graph/api/resources/teams-api-overview) para arquivar ou restaurar uma equipe.
 
> [!IMPORTANT]
> O uso Microsoft 365 Política de Expiração de Grupos requer Azure Active Directory Premium P1 licenças para cada usuário exclusivo que seja membro de um ou mais grupos Microsoft 365 grupos.

## <a name="are-there-team-templates-for-my-faculty-members-to-use-when-creating-a-team"></a>Há modelos de equipe para os membros do meu corpo docente usarem ao criar uma equipe?

Sim. Os usuários  podem selecionar Criar Equipe do modelo existente ao criar uma nova equipe, e os proprietários do Teams também podem usar [a API de Graph (beta)](/graph/api/resources/teams-api-overview) para criar uma nova equipe a partir dos modelos disponíveis.

## <a name="what-tasks-can-i-automate-via-powershell-or-graph"></a>Quais tarefas posso automatizar por meio do PowerShell ou Graph?

A [API do Microsoft Graph (beta)](/graph/api/resources/teams-api-overview) pode fazer o seguinte:

-   Crie uma equipe.
-   Adicione membros e proprietários.
-   Adicione canais.
-   Adicionar aplicativos.
-   Atalho dessas etapas clonando uma equipe existente e obter suas guias também.
-   Dê ao usuário um link para a equipe que você acabou de criar.
-   Remova membros, proprietários, canais e aplicativos quando você não precisar mais deles.
-   Arquivar a equipe quando ela não estiver mais ativa. 
-   Exclua a equipe.
-   Criar um thread de canal

[O PowerShell](/powershell/module/teams/?view=teams-ps) pode fazer o seguinte:

-   Crie uma equipe.
-   Adicione membros e proprietários.
-   Adicione canais.
-   Remova membros, proprietários e canais quando você não precisar mais deles.
-   Exclua a equipe.

> [!TIP]
> Os Graph API e os cmdlets do PowerShell estão constantemente adicionando funcionalidade. Verifique frequentemente os artigos da [API do Microsoft Graph (beta)](/graph/api/resources/teams-api-overview) e do [PowerShell](/powershell/module/teams/?view=teams-ps) para aprimoramentos de recursos.  


## <a name="can-i-control-what-teams-features-my-faculty-and-students-have-access-to"></a>Posso controlar quais recursos Teams meus professores e alunos têm acesso?

Sim. Você pode usar políticas para controlar recursos específicos de mensagens, reuniões, chamada e eventos ao vivo aos que os usuários têm acesso. Você pode usar configurações de todo o locatário para aplicar as mesmas configurações a todos ou aplicar políticas no nível do usuário, se necessário. 

Para obter mais detalhes sobre Teams políticas, consulte [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).
 
## <a name="can-i-control-what-external-parties-my-faculty-and-students-collaborate-with"></a>Posso controlar com quais partes externas meus professores e alunos colaboram?

Você pode usar o acesso de convidados para convidar usuários de fora do seu locatário, o que pode ser útil para colaboração de pesquisa ou conferências de convidados:

-   Use uma lista de autorizações de domínio para permitir ou bloquear convidados com base em seu domínio.
-   Ativar e desativar o acesso de convidados Microsoft 365 grupos e equipes específicos, para controlar quais equipes podem (e não podem) convidar convidados.
-   Use o log de auditoria para ver quais alertas foram enviados aos convidados.

Para obter mais informações, consulte [Acesso de convidados Microsoft 365 Grupos](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage).

## <a name="what-information-can-i-review-about-existing-teams"></a>Quais informações posso revisar sobre equipes existentes?

Você pode verificar os logs de auditoria para ver:

-   Who foi convidado como convidado para qual equipe.
-   Who qual equipe foi criada.

Para obter mais informações, consulte [Pesquisar o log de auditoria para eventos em Microsoft Teams](audit-log-events.md).

## <a name="teams-evolves-so-quickly-how-can-i-stay-up-to-date"></a>Teams evolui tão rapidamente. Como posso me manter atualizado?

Recomendamos os seguintes recursos para obter as atualizações mais recentes Teams:

-   [Novidades na Microsoft Teams](https://support.office.com/article/What-s-new-in-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
-   [Microsoft Teams blog](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)