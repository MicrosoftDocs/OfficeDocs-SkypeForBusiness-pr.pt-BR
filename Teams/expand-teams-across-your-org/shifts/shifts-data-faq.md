---
title: Perguntas frequentes sobre deslocamentos de dados
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Obtenha respostas para perguntas frequentes sobre os dados do Shifts, incluindo onde os dados do Shifts são armazenados, retenção de dados, recuperação e criptografia.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 35447b432118737821f578ddaee364e780f18e0d
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675343"
---
# <a name="shifts-data-faq"></a>Perguntas frequentes sobre deslocamentos de dados

Este artigo aborda as perguntas frequentes sobre os dados do Shifts, incluindo onde os dados do Shifts são armazenados, retenção de dados, recuperação e criptografia.

## <a name="where-is-shifts-data-stored"></a>Onde os dados do Shifts são armazenados?

Os dados de turnos são armazenados em uma das três regiões geográficas : Pacífico Asiático (APAC), União Europeia (UE) ou Estados Unidos. Cada área geográfica armazena dados em pelo menos duas regiões do data center do Azure para alta disponibilidade (HA) e DR (recuperação de desastre). Hoje, o Estados Unidos/América do Norte geogeográfico usa data centers no Centro-Norte e No Centro-Sul Estados Unidos. Para saber mais, confira [Onde estão Microsoft 365 dados do cliente armazenados](/microsoft-365/enterprise/o365-data-locations).

Atualmente, o Shifts oferece residência de dados na Austrália, Canadá, França, Japão e Reino Unido. Estamos trabalhando ativamente para expandir o suporte para mais locais.

## <a name="can-i-choose-where-shifts-data-is-stored"></a>Posso escolher onde os dados do Shifts são armazenados?

Ao configurar o Teams, você escolhe um país ou região, que é definido no nível da assinatura. Os turnos respeitam essa seleção e usam a localidade e a região definidas no Teams se damos suporte a essa região. Se ainda não estamos nessa região, armazenamos dados em uma região próxima à qual damos suporte. No futuro, planejamos migrar dados existentes, se armazenados em uma região próxima, para a região provisionada em Teams.

## <a name="can-i-access-and-export-or-delete-a-users-personal-data-in-shifts"></a>Posso acessar e exportar ou excluir dados pessoais de um usuário no Shifts?

O Shifts está em conformidade com o GDPR (Regulamento Geral sobre a Proteção de Dados). Uma solicitação formal de uma pessoa (conhecida como titular dos dados) para executar uma ação em seus dados pessoais é chamada de DSR (Solicitação de Entidade de Dados). Você pode encontrar e agir em dados pessoais em Turnos em resposta a uma DSR.

Você pode usar a ferramenta Descoberta Eletrônica de Pesquisa de Conteúdo no portal de conformidade do Microsoft Purview para pesquisar e exportar dados de agendamento e relógio para Excel. Para todos os outros dados do Shifts, você pode fazer capturas de tela dos dados.

Para saber mais, confira [Office 365 solicitações de titulares de dados para o RGPD e o CCPA](/microsoft-365/compliance/gdpr-dsr-office365).

## <a name="what-happens-to-shifts-data-if-i-turn-off-shifts-for-my-organization"></a>O que acontecerá com os dados do Shifts se eu desativar o Shifts para minha organização?

Desativar turnos em sua organização *não exclui* dados. Se você desativar o Shifts e, posteriormente, ativar o Shifts, os dados do Shifts ainda estarão disponíveis.

Se você excluir seu locatário, todos os dados do Shifts serão excluídos após o término do período de retenção.

Não há nenhuma opção para excluir apenas os dados do Shifts. Se você excluir uma equipe no Teams, os dados de agendamento de turnos associados a essa equipe serão excluídos após o término do período de retenção. Para saber mais, confira [Retenção, exclusão](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview) e destruição de dados Microsoft 365.

## <a name="can-i-recover-a-shifts-schedule-that-was-deleted"></a>Posso recuperar uma agenda de turnos que foi excluída?

Você poderá recuperar um agendamento excluído se o grupo Microsoft 365 que o dá suporte (ou a equipe no Teams) for restaurado.

Por padrão, um grupo Microsoft 365 excluído é mantido por 30 dias. Esse período de 30 dias é chamado de "exclusão reversível" porque você ainda pode restaurar o grupo. Para saber mais, confira [Restaurar um grupo Microsoft 365 excluído](/microsoft-365/admin/create-groups/restore-deleted-group?tabs=admin-center).

## <a name="can-i-use-custom-retention-policies-for-shifts-data"></a>Posso usar políticas de retenção personalizadas para dados do Shifts?

Atualmente, o Shifts não dá suporte a políticas de retenção personalizadas.

Para saber mais sobre as políticas de retenção no Teams, consulte Saiba [](/microsoft-365/compliance/retention-policies-teams) mais sobre retenção para Teams e Gerenciar políticas de retenção [para Teams](../../retention-policies.md).

## <a name="can-i-retrieve-shifts-data-for-a-user-whose-license-was-revoked"></a>Posso recuperar dados do Shifts para um usuário cuja licença foi revogada?

Hoje, não oferecemos a capacidade de recuperar dados para um usuário cuja licença foi revogada. Essa funcionalidade é algo para o que estamos trabalhando.

## <a name="what-type-of-encryption-does-shifts-use-for-data-at-rest-and-in-transit"></a>Que tipo de criptografia o Shifts usa para dados em repouso e em trânsito?

Os dados de deslocamentos são criptografados em repouso pelo Azure Cosmos DB e pelo Azure Armazenamento. Para saber mais, confira Criptografia de dados em repouso do [Azure](/azure/security/fundamentals/encryption-atrest) e criptografia de [dados no Azure Cosmos DB](/azure/cosmos-db/database-encryption-at-rest).

Os turnos seguem Microsoft 365 diretrizes para criptografia de dados em trânsito. Para saber mais, confira [Criptografia para dados em trânsito](/compliance/assurance/assurance-encryption-in-transit).

A criptografia de deslocamentos de dados em repouso e em trânsito são verificadas anualmente pela auditoria de conformidade do SOC2.

## <a name="can-i-access-immutable-copies-of-shifts-data"></a>Posso acessar cópias imutáveis de dados do Shifts?

Não armazenamos cópias imutáveis de dados do Shifts. Por exemplo, um gerente pode fazer alterações em um agendamento, como adicionar anotações, alterar horários de turno, atribuir tarefas e assim por diante.

## <a name="can-shifts-data-be-edited"></a>Os dados do Shifts podem ser editados?

Há certos aspectos de Turnos que não podem ser alterados e determinados aspectos que podem ser alterados. Por exemplo, detalhes de deslocamento, como anotações e cores, podem ser editados de forma semelhante a como podem ser alterados no aplicativo Shifts. As solicitações de deslocamento não podem ser editadas, a menos que a solicitação seja retirada.

Para ver quais campos foram alterados, você pode pesquisar os Microsoft 365 log de auditoria para eventos shifts. Para saber mais sobre os eventos que são registrados para atividades de Turnos no log de auditoria do Microsoft 365, consulte [Turnos em Teams atividades](../../audit-log-events.md#shifts-in-teams-activities).

## <a name="my-organization-uses-a-workforce-management-system-for-scheduling-can-we-integrate-with-and-access-shifts-data"></a>Minha organização usa um sistema de gerenciamento de força de trabalho para agendamento. Podemos integrar e acessar dados do Shifts?

Turnos Graph APIs permitem integrar dados shifts com sistemas WFM (gerenciamento de força de trabalho externa). Para saber mais, confira [Shifts Graph APIs](/graph/api/resources/shift).

Também oferecemos conectores shifts gerenciados e conectores shifts de software livre. Com esses conectores, você pode integrar seu sistema WFM diretamente com o Shifts. Para saber mais sobre conectores shifts e sistemas WFM com suporte, consulte [conectores shifts](shifts-connectors.md).

## <a name="can-shifts-data-be-deleted-permanently-after-a-specified-period-of-time"></a>Os dados shifts podem ser excluídos permanentemente após um período de tempo especificado?

Hoje, não excluímos seus dados do Shifts. Usando [shifts Graph APIs](/graph/api/resources/shift), é possível criar um aplicativo usando Power Apps para [](/powerapps/maker/) reter dados por um período de tempo especificado. No entanto, não há suporte para isso nativamente.

## <a name="can-shifts-data-be-moved-in-a-tenant-to-tenant-migration"></a>Os dados do Shifts podem ser movidos em uma migração de locatário para locatário?

Os dados de turnos podem ser migrados de um locatário para outro locatário mediante solicitação específica. Tenha em mente que a migração de locatário para locatário não tem suporte inicial, mas pode ser gerada como uma solicitação do cliente.

## <a name="related-articles"></a>Artigos relacionados

- [Turnos do Teams](../shifts-for-teams-landing-page.md)
- [Gerenciar o aplicativo Shifts](manage-the-shifts-app-for-your-organization-in-teams.md)
