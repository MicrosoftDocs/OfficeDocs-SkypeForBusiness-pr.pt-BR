---
title: Perguntas frequentes sobre governança do Microsoft Education para profissionais de TI ‒ Microsoft Teams
author: lanachin
ms.author: v-lanac
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
ms.openlocfilehash: 719f9429d49dfef7a21670c67bad96c9e26c993e
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837431"
---
# <a name="microsoft-education-governance-faq-for-admins"></a>Perguntas frequentes sobre governança do Microsoft Education para administradores

> [!Tip]
> Assista à sessão a seguir para saber mais sobre o gerenciamento no Microsoft Teams: [governança, gerenciamento e ciclo de vida no Microsoft Teams](https://aka.ms/teams-governance)

## <a name="how-do-i-control-team-creation-im-worried-students-are-going-to-create-inappropriate-teams"></a>Como faço para controlar a criação da equipe? Estou preocupado que os alunos criem equipes inadequadas.

Para evitar nomes inadequados ou enganosas, ou apenas para fornecer mais estruturas sobre como as equipes são nomeadas, você pode usar a política de nomenclatura de grupos do Office 365 (atualmente em visualização):

-   **Política de nomenclatura de sufixo de prefixo** Você pode usar prefixos ou sufixos para definir a Convenção de nomenclatura de Teams (grupos), por exemplo, **GRP_US_My Group_Engineering**. Os prefixos e sufixos podem ser cadeias de caracteres fixas ou atributos de usuário (como **[departamento]**) que são adicionados ao nome com base no usuário que está criando a equipe.
-   **Palavras bloqueadas personalizadas** Você pode carregar um conjunto de palavras que os usuários de uma organização específica são bloqueados usando em nomes de equipes criados por eles. Por exemplo, você pode bloquear os termos **CEO**, **Payroll**e **HR** de uso em nomes de equipe para grupos aos quais não se aplicam.
-   **Classificação** Você pode criar classificações que os usuários em sua organização podem definir quando criarem um grupo do Office 365. 

> [!IMPORTANT]
> O uso da política de nomenclatura de grupos do Office 365 exige licenças do Azure Active Directory Premium P1 ou licenças EDU do Azure AD Basic para cada usuário exclusivo que seja membro de um ou mais grupos do Office 365.

Para obter instruções detalhadas, confira [política de nomenclatura de grupos do Office](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).

> [!Note]
> Se as equipes forem criadas automaticamente usando a entrada de outro sistema (por exemplo, escola de sincronização de dados), verifique se os dados de entrada estão em conformidade com a política de nomenclatura que você configurou; Se não for, a criação de equipe falhará.

## <a name="can-i-see-who-created-a-team"></a>Eu posso ver quem criou uma equipe?

Para descobrir quem criou uma equipe específica, confira [Pesquisar o log de auditoria para eventos no Microsoft Teams](audit-log-events.md).

## <a name="can-i-control-who-can-create-teams"></a>Posso controlar quem pode criar equipes?

Em geral, recomendamos impedir que alguém crie equipes. Se todos podem criar equipes, é mais provável que as equipes sejam amplamente adotadas. Professores, professores ou alunos podem usar o Microsoft Teams para criar grupos de estudos ou grupos de interesses especiais. Isso ajudará as equipes a ser aceitadas dentro e fora da sala de aula.

Na nossa experiência, a educação do usuário ajuda a garantir o uso do teams responsáveis. Assim que os usuários compreenderem que a criação de equipes não são anônimas, compreenderá as implicações de criá-las com cuidado e tendem a não usar a ferramenta de forma indiferente.

Se você tem certeza de que deseja controlar quem pode criar equipes, consulte [gerenciar quem pode criar grupos do Office 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).

## <a name="how-do-i-automatically-create-a-team-for-each-course-at-the-beginning-of-the-semester-or-quarter"></a>Como criar automaticamente uma equipe para cada curso no início do semestre ou trimestre?

No início de cada semestre ou trimestre, você precisará de uma série de novas equipes. Pode fazer sentido fazer uma abordagem automatizada para criar essas equipes automaticamente, preenchê-las com os usuários certos e definir as permissões corretas:

-   O School Data Sync pode criar grupos do Office 365 para o Exchange Online e o SharePoint Online, equipes de classe para Microsoft Teams e blocos de anotações de classe do OneNote, grupos de escolas para o Intune para educação e enlistagem e integração de logon único (SSO) para muitos outros aplicativos de terceiros. Saiba mais em [visão geral da sincronização de dados da escola](https://docs.microsoft.com/schooldatasync/overview-of-school-data-sync).
-   Com o PowerShell, você pode criar equipes e canais e definir as configurações automaticamente. Consulte [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.
-   Você pode usar a API do Microsoft Graph (atualmente em versão beta) para criar, configurar, clonar e arquivar equipes. Consulte [usar a API do Microsoft Graph para trabalhar com o Microsoft Teams](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) para obter mais informações.

> [!TIP]
> O School Data Sync cria um grupo do Office 365 para cada classe sincronizada e [habilita a associação de grupo oculto](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945) para que somente professores e alunos dentro da classe possam ver os membros dessa classe. Se estiver usando um processo diferente para criar grupos de classe, use o parâmetro HiddenGroupMembershipEnabled do cmdlet New-unificado para atender aos mesmos requisitos de privacidade.

## <a name="how-do-i-deal-with-teams-when-the-semester-or-quarter-ends"></a>Como faço para lidar com o Microsoft Teams quando o semestre ou o trimestre termina?

Recomendamos que você primeiro pense em como deseja lidar com os dados do teams quando o semestre ou trimestre da escola terminar: se deseja excluí-lo ou mantê-lo disponível para os alunos, mesmo depois de concluírem o curso. Convém manter o calendário escolar em mente para que as políticas que você definir não entrem em conflito com feriados. Você pode usar as seguintes ferramentas para implementar sua estratégia:

-   **Política de retenção:** Use esta opção para excluir todos os dados anteriores a uma idade que você especificou para garantir que os dados antigos sejam removidos de chats (para todos ou alguns usuários) e canais. Você também pode configurar o Microsoft Teams para manter o conteúdo para que ele não possa ser excluído. Para obter mais informações, consulte [políticas de retenção para Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011).
-   **Política de vencimento:** Configurar o Microsoft Teams para expirar após um determinado número de dias. Trinta dias antes do vencimento, todos os proprietários de uma equipe são notificados de que sua equipe precisa ser renovada; caso contrário, ele será excluído (embora um administrador possa recuperar equipes excluídas por um adicional de 30 dias). Essa configuração é muito útil para garantir que as equipes não usadas sejam subdivididas. Saiba mais na [política de expiração de grupo do Office 365](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733).

-   **Equipe de arquivamento:** Esta configuração coloca as equipes em modo somente leitura. Elas ainda podem ser navegadas e pesquisadas, mas ninguém pode adicionar novas postagens. [Arquivar ou restaurar uma equipe](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7) descreve como os proprietários da equipe podem arquivar uma equipe; Os proprietários da equipe também podem usar a [API do Graph (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) para arquivar ou restaurar uma equipe.
 
> [!IMPORTANT]
> O uso da política de expiração de grupos do Office 365 exige licenças do Azure Active Directory Premium P1 para cada usuário exclusivo que seja membro de um ou mais grupos do Office 365.

## <a name="are-there-team-templates-for-my-faculty-members-to-use-when-creating-a-team"></a>Há modelos de equipe para os membros dos professores usarem ao criar uma equipe?

Sim. Os usuários podem selecionar **criar equipe a partir de um modelo existente** ao criar uma nova equipe, e os proprietários de equipes também podem usar a [API de gráfico (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) para criar uma nova equipe a partir dos modelos disponíveis.

## <a name="what-tasks-can-i-automate-via-powershell-or-graph"></a>Quais tarefas posso automatizar via PowerShell ou Graph?

A [API do Microsoft Graph (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) pode fazer o seguinte:

-   Criar uma equipe.
-   Adicionar membros e proprietários.
-   Adicionar canais.
-   Adicionar aplicativos.
-   Faça o atalho dessas etapas clonando uma equipe existente e obtenha suas guias também.
-   Dê ao usuário um link para a equipe que você acabou de criar.
-   Remova Membros, proprietários, canais e aplicativos quando você não precisar mais deles.
-   Arquivar a equipe quando ela não estiver mais ativa. 
-   Excluir a equipe.
-   Criar um thread de canal

O [PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) pode fazer o seguinte:

-   Criar uma equipe.
-   Adicionar membros e proprietários.
-   Adicionar canais.
-   Remova Membros, proprietários e canais quando você não precisar mais deles.
-   Excluir a equipe.

> [!TIP]
> A API de gráfico e os cmdlets do PowerShell estão constantemente adicionando funcionalidades. Certifique-se de verificar a [API do Microsoft Graph (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) e os artigos do [PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) com frequência para melhorias de recursos.  


## <a name="can-i-control-what-teams-features-my-faculty-and-students-have-access-to"></a>Posso controlar quais recursos de equipe meus professores e alunos têm acesso?

Sim. Você pode usar políticas para controlar recursos específicos de mensagens, reuniões, chamadas e eventos dinâmicos aos quais seus usuários têm acesso. Você pode usar as configurações de todo o locatário para aplicar as mesmas configurações a todos ou aplicar políticas em nível de usuário, se necessário. 

Para obter mais detalhes sobre as políticas do Teams, consulte [gerenciar as configurações do Microsoft Teams para sua organização](enable-features-office-365.md).
 
## <a name="can-i-control-what-external-parties-my-faculty-and-students-collaborate-with"></a>Posso controlar quais festas externos meu docente e seus alunos colaborarão?

Você pode usar o acesso de convidado para convidar usuários de fora do seu locatário, o que pode ser útil para palestras de colaboração ou convidados de pesquisa:

-   Use a lista branca do domínio para permitir ou bloquear convidados com base em seus domínios.
-   Ative e desative o acesso de convidado para grupos e equipes particulares do Office 365, para controlar quais equipes podem (e não podem) convidar convidados.
-   Use o log de auditoria para ver quais alertas foram enviados a convidados convidados.

Para obter mais informações, consulte [acesso de convidado em grupos do Office 365](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage).

## <a name="what-information-can-i-review-about-existing-teams"></a>Que informações eu posso examinar sobre as equipes existentes?

Você pode verificar os logs de auditoria para ver:

-   Quem foi convidado como convidado para a equipe.
-   Quem criou a equipe.

Para obter mais informações, consulte [Pesquisar o log de auditoria para eventos no Microsoft Teams](audit-log-events.md).

## <a name="teams-evolves-so-quickly-how-can-i-stay-up-to-date"></a>O Teams evolui tão rápido. Como posso me manter atualizado?

Recomendamos os seguintes recursos para obter as atualizações mais recentes do teams:

-   [O que há de novo no Microsoft Teams](https://support.office.com/article/What-s-new-in-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
-   [Blog do Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)
