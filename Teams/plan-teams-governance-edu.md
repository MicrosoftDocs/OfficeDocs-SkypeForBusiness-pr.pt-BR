---
title: Governança de Microsoft Education perguntas Frequentes para profissionais de TI - Teams da Microsoft
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 08/10/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Respostas a perguntas frequentes dos administradores dos grupos da Microsoft Education que usam equipes.
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4991990143b0292f83b5c71b8b2bf01a5d612184
ms.sourcegitcommit: 5943c41bac520558733d08f4a9ecc4425c422ff9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2018
ms.locfileid: "22599450"
---
# <a name="microsoft-education-governance-faq-for-admins"></a>Governança de Microsoft Education perguntas Frequentes para administradores

## <a name="how-do-i-control-team-creation-im-worried-students-are-going-to-create-inappropriate-teams"></a>Como eu posso controlar a criação da equipe? Tenho receio de alunos pretende criar equipes inadequadas.

Para evitar nomes de falsos ou inadequados ou apenas para fornecer mais estrutura como equipes são nomeadas, você pode usar os grupos de 365 Office diretiva (atualmente em preview) de nomenclatura:

-   **Diretiva de nomenclatura de prefixo sufixo** Você pode usar prefixos ou sufixos para definir a convenção de nomenclatura de equipes (grupos), por exemplo, **GRP_US_My Group_Engineering**. Os prefixos e sufixos podem ser resolvidos cadeias de caracteres ou atributos de usuário (por exemplo, **[departamento]**) que são adicionados ao nome com base no usuário que está criando a equipe.
-   **Sinalizador bloqueados palavras** Você pode carregar um conjunto de palavras que os usuários em uma organização específica são impedidos de usar nos nomes das equipes que eles criam. Por exemplo, você pode bloquear os termos **CEO**, **folha de pagamento**e **RH** de serem usadas em nomes de equipe para grupos, que eles não se aplicam ao.
-   **Classificação** Você pode criar classificações que os usuários em sua organização podem ser definidas quando eles criam um grupo do Office 365. 

> [!IMPORTANT]
> Usando a diretiva de nomenclatura de grupos do Office 365 exige licenças do Azure Active Directory Premium P1 ou licenças EDU básica do Windows Azure AD para cada usuário exclusivo que seja membro de um ou mais grupos do Office 365.

Para obter instruções detalhadas, consulte [grupos de diretiva de nomeação do Office](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).

> [!Note]
> Se as equipes são criadas automaticamente usando a entrada de outro sistema (por exemplo, sincronização de dados da escola), verifique se que os dados de entrada é compatível com a diretiva de nomeação que você configurou; Se ele não estiver, equipe criação falhará.

## <a name="can-i-see-who-created-a-team"></a>Pode ver quem criou uma equipe?

Para descobrir quem criou uma equipe específica, consulte [o log de auditoria para eventos no Microsoft equipes de pesquisa](audit-log-events.md).

## <a name="can-i-control-who-can-create-teams"></a>Eu posso controlar quem pode criar equipes?

Em geral, é recomendável contra impedindo que qualquer pessoa Criando equipes. Se todas as pessoas podem criar equipes, equipes é mais provável de ser adotado. Corpo Docente, professores ou alunos podem usar as equipes para criar grupos de estudo ou grupos de interesse especial. Isso ajudar equipes a ser aceita dentro e fora da sala de aula.

Em nossa experiência, o treinamento do usuário ajuda a garantir o uso de equipes responsável. Assim que os usuários compreendem que criar equipes não é anônima, eles entender as implicações com negligência criá-los e isso tende a evitam uso indevido a ferramenta.

Se você tiver certeza de que deseja controlar quem pode criar equipes, consulte [Manage quem pode criar grupos do Office 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).

## <a name="how-do-i-automatically-create-a-team-for-each-course-at-the-beginning-of-the-semester-or-quarter"></a>Como criar automaticamente uma equipe para cada curso no início do trimestre ou semestre?

No início de cada semestre ou trimestre, você precisará de um número de novas equipes. Pode fazer sentido adotar uma abordagem automatizada para criar essas equipes automaticamente, preenchê-los com os usuários à direita e definir as permissões corretas:

-   Sincronização de dados da escola pode criar grupos do Office 365 para Exchange Online e SharePoint Online, as equipes de classe de blocos de anotações do Microsoft Teams e a classe do OneNote, grupos de escola para Intune para educação e rostering e single sign-on (SSO) integração com muitos outros aplicativos de terceiros. Saiba mais em [Visão geral de sincronização de dados da escola](https://docs.microsoft.com/schooldatasync/overview-of-school-data-sync).
-   Com o PowerShell, você pode criar equipes e canais e definir as configurações automaticamente. Consulte [PowerShell de equipes da Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.
-   Você pode usar a API do Microsoft Graph (atualmente em beta) para criar, configurar, clone e arquivar equipes. Consulte [Use a API do Microsoft Graph para trabalhar com as equipes da Microsoft](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) para obter mais informações.

> [!TIP]
> Sincronização de dados da escola cria um grupo do Office 365 para cada classe sincronizados e [permite a associação ao grupo oculto](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945) para que apenas professores e alunos dentro da classe podem ver os membros dessa classe. Se estiver usando um processo diferente para criar grupos de classe usam o parâmetro HiddenGroupMembershipEnabled do cmdlet New-UnifiedGroup para cumprir os mesmos requisitos de privacidade.

## <a name="how-do-i-deal-with-teams-when-the-semester-or-quarter-ends"></a>Como lidar com as equipes quando termina o semestre ou trimestre?

Recomendamos que você pensa sobre como você deseja controlar os dados de equipes, quando o semestre escola ou trimestre está sobre primeiro: se deseja mantê-la disponível para alunos mesmo depois que eles concluir o curso ou excluí-la. Você vai querer manter o calendário de escola em mente, portanto quaisquer políticas que você definir não entram em conflito com os feriados. Você pode usar as seguintes ferramentas para implementar sua estratégia de:

-   **Política de retenção:** Use esta opção para excluir todos os dados mais antigos do que um tempo especificado para certificar-se de que os dados antigos são removidos do bate-papos (para usuários de todos ou alguns) e canais. Você também pode configurar equipes para reter conteúdo, ele não pode ser excluído. Para obter mais informações, consulte [políticas de retenção para equipes da Microsoft](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011).
-   **Política de expiração:** Configure equipes para expirar após um determinado número de dias. Trinta dias antes do vencimento, todos os proprietários de uma equipe são notificados que sua equipe precisa ser renovada, caso contrário, ele será excluído (embora um administrador pode recuperar equipes excluídas por mais 30 dias). Essa configuração é muito útil para tornar-se de que as equipes não utilizadas sunsetted. Saiba mais em [Política de expiração de grupo do Office 365](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733).

-   **Equipe de arquivo morto:** Essa configuração coloca equipes em modo somente leitura. Eles ainda podem ser procurados e pesquisados, mas ninguém pode adicionar quaisquer novas postagens. [Arquivo morto ou restauração uma equipe](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7) descreve como os proprietários de equipe podem arquivar uma equipe; Os proprietários de equipe também podem usar a [API de gráfico (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) para arquivar ou a restauração de uma equipe.
 
> [!IMPORTANT]
> Usando a política de expiração de grupos do Office 365 exige licenças do Azure Active Directory Premium P1 para cada usuário único que seja membro de um ou mais grupos do Office 365.

## <a name="are-there-team-templates-for-my-faculty-members-to-use-when-creating-a-team"></a>Existem modelos de equipe para os membros de Meus Corpo Docente usar ao criar uma equipe?

Sim. Os usuários podem selecionar **Criar equipe de modelo existente** ao criar uma nova equipe e os proprietários de equipes também podem usar a [API de gráfico (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) para criar uma nova equipe a partir de modelos disponíveis.

## <a name="what-tasks-can-i-automate-via-powershell-or-graph"></a>Tarefas que podem automatizar via PowerShell ou gráfico?

A [API do Microsoft Graph (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) pode fazer o seguinte:

-   Crie uma equipe.
-   Adicione membros e proprietários.
-   Adicione canais.
-   Adicione aplicativos.
-   Atalho essas etapas clonando existente da equipe e fazer suas guias muito.
-   Conceda ao usuário um link para a equipe que você acabou de criar.
-   Remova membros, os proprietários, canais e aplicativos quando não precisar mais-los.
-   Arquive a equipe quando ele não está mais ativo. 
-   Exclua a equipe.
-   Criar um segmento de canal

[PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) pode fazer o seguinte:

-   Crie uma equipe.
-   Adicione membros e proprietários.
-   Adicione canais.
-   Remova membros, proprietários e canais quando não precisar mais-los.
-   Exclua a equipe.

> [!TIP]
> Os cmdlets do PowerShell e de API do gráfico constantemente adicionando funcionalidade. Certifique-se de verificar os artigos de [API do Microsoft Graph (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) e do [PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) frequentemente para aprimoramentos de recursos.  


## <a name="can-i-control-what-teams-features-my-faculty-and-students-have-access-to"></a>Eu posso controlar quais recursos de equipes meu corpo docente e alunos tenham acesso?

Sim. Você pode usar diretivas para controlar mensagens específicas, reuniões, chamadas e live recursos de evento que seus usuários têm acesso. Você pode usar configurações de todo o locatário para aplicar as mesmas configurações a todos ou aplicar políticas de nível de usuário, se necessário. 

Para obter mais detalhes sobre as diretivas de equipes, consulte [os recursos de gerenciar equipes da Microsoft em sua organização do Office 365](enable-features-office-365.md).
 
## <a name="can-i-control-what-external-parties-my-faculty-and-students-collaborate-with"></a>Eu posso controlar quais partes externas meus professores e alunos colaboram com?

Você pode usar o acesso de convidado convidem usuários de fora do seu locatário, que pode ser útil para colaboração de pesquisa ou palestras convidado:

-   Use a lista de exceções de domínio para permitir ou bloquear convidados com base no seu domínio.
-   Ative o acesso de convidado e desativando para determinado, equipes e grupos do Office 365 controlar o que as equipes podem (e não podem) convidar pessoas.
-   Use o log de auditoria para ver quais alertas eram enviadas para os convidados.

Para obter mais informações, consulte [acesso de convidado em grupos do Office 365](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage).

## <a name="what-information-can-i-review-about-existing-teams"></a>Quais informações pode revisar sobre equipes existentes?

Você pode verificar os logs de auditoria para ver:

-   Que foi convidado como convidado para a qual equipe.
-   Quem criou qual equipe.

Para obter mais informações, consulte [o log de auditoria para eventos no Microsoft equipes de pesquisa](audit-log-events.md).

## <a name="teams-evolves-so-quickly-how-can-i-stay-up-to-date"></a>As equipes se desenvolve tão rapidamente. Como posso permanecer atualizado?

Recomendamos os seguintes recursos para obter as últimas atualizações nas equipes:

-   [O que há de novo no Microsoft Teams](https://support.office.com/article/What-s-new-in-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
-   [Blog do Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)
