---
title: Desloca perguntas frequentes sobre dados
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
description: Obter respostas para perguntas frequentes sobre dados shifts, incluindo onde os dados shifts são armazenados, retenção de dados, recuperação e criptografia.
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
ms.openlocfilehash: 2df5c465c9115dce47ee9e80ea649768606c338f
ms.sourcegitcommit: 10bee789272e648ea1e93d7d7c27ec645d0a8bdd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/22/2022
ms.locfileid: "62918946"
---
# <a name="shifts-data-faq"></a>Desloca perguntas frequentes sobre dados

Este artigo aborda perguntas frequentes sobre dados shifts, incluindo onde os dados shifts são armazenados, retenção de dados, recuperação e criptografia.

## <a name="where-is-shifts-data-stored"></a>Onde os dados shifts são armazenados?

Os dados de turnos são armazenados em uma das três geografias (geos): Ásia Pacífico (APAC), União Europeia (UE) ou Estados Unidos. Cada geo armazena dados em pelo menos duas regiões do data center do Azure para Alta Disponibilidade (HA) e Recuperação de Desastres (DR). Hoje, o geo dos Estados Unidos/América do Norte usa data centers no Centro-Norte e no Centro-Sul dos Estados Unidos. Para saber mais, consulte [Where is Microsoft 365 customer data stored](/microsoft-365/enterprise/o365-data-locations).

Atualmente, Shifts oferece residência de dados na Austrália, Canadá, França, Japão e Reino Unido. Estamos trabalhando ativamente para expandir o suporte para mais locais.

## <a name="can-i-choose-where-shifts-data-is-stored"></a>Posso escolher onde os dados shifts são armazenados?

Quando você configura a Teams, você escolhe um país ou região, que é definido no nível da assinatura. Shifts honra essa seleção e usa a localidade e a região definidas em Teams se suportarmos essa região. Se ainda não estamos nessa região, armazenamos dados em uma região próxima que suportamos. No futuro, planejamos migrar dados existentes, se armazenados em uma região próxima, para a região provisionada em Teams.

## <a name="can-i-access-and-export-or-delete-a-users-personal-data-in-shifts"></a>Posso acessar e exportar ou excluir dados pessoais de um usuário em Shifts?

Shifts é compatível com o Regulamento Geral de Proteção de Dados (RGPD).Uma solicitação formal de uma pessoa (conhecida como um assunto de dados) para tomar uma ação em seus dados pessoais é chamada de Solicitação de Assunto de Dados (DSR). Você pode encontrar e agir em dados pessoais em Shifts em resposta a uma DSR.

Você pode usar a ferramenta Descoberta eDiscovery de Pesquisa de Conteúdo no Centro de conformidade do Microsoft 365 para pesquisar e exportar dados de agendamento e relógio para Excel. Para todos os outros dados shifts, você pode fazer capturas de tela dos dados.

Para saber mais, confira [Office 365 Solicitações de Assunto de Dados para o RGPD e CCPA](/microsoft-365/compliance/gdpr-dsr-office365).

## <a name="what-happens-to-shifts-data-if-i-turn-off-shifts-for-my-organization"></a>O que acontece com os dados shifts se eu desativar turnos para minha organização?

A exclusão de turnos em sua *organização não exclui* dados. Se você desativar Shifts e, posteriormente, ativar Turnos, seus dados shifts ainda estarão disponíveis.

Se você excluir seu locatário, todos os dados shifts serão excluídos depois que o período de retenção terminar.

Não há opção para excluir apenas dados shifts. Se você excluir uma equipe no Teams, os dados de agendamento de turnos associados a essa equipe serão excluídos após o fim do período de retenção. Para saber mais, confira [Retenção, exclusão e destruição de dados Microsoft 365](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview).

## <a name="can-i-recover-a-shifts-schedule-that-was-deleted"></a>Posso recuperar um cronograma de Turnos que foi excluído?

Você pode recuperar um cronograma excluído se o grupo de Microsoft 365 que o restitui (ou a equipe no Teams) for restaurado.

Por padrão, um grupo de Microsoft 365 excluído é mantido por 30 dias. Esse período de 30 dias é chamado de "exclusão suave" porque você ainda pode restaurar o grupo. Para saber mais, confira [Restaurar um grupo Microsoft 365 excluído](/microsoft-365/admin/create-groups/restore-deleted-group?view=o365-worldwide&tabs=admin-center).

## <a name="can-i-use-custom-retention-policies-for-shifts-data"></a>Posso usar políticas de retenção personalizadas para dados shifts?

Atualmente, Shifts não dá suporte a políticas de retenção personalizadas.

Para saber mais sobre políticas de retenção no Teams, consulte [Saiba](/microsoft-365/compliance/retention-policies-teams) mais sobre retenção para Teams e Gerenciar políticas de [retenção para Teams](../../retention-policies.md).

## <a name="can-i-retrieve-shifts-data-for-a-user-whose-license-was-revoked"></a>Posso recuperar dados shifts para um usuário cuja licença foi revogada?

Hoje, não oferecemos a capacidade de recuperar dados para um usuário cuja licença foi revogada. Esse recurso é algo para o que estamos trabalhando.

## <a name="is-shifts-supported-in-government-cloud-community-gcc-environments"></a>Os Shifts são suportados em ambientes de nuvem Community (GCC) do Governo?

Shifts está disponível em GCC ambientes, mas não em ambientes GCC High ou DoD.

## <a name="what-type-of-encryption-does-shifts-use-for-data-at-rest-and-in-transit"></a>Que tipo de criptografia Shifts usa para dados em repouso e em trânsito?

Os dados de turnos são criptografados em repouso pelo Azure Cosmos DB e o Azure Armazenamento. Para saber mais, confira [Criptografia de dados do Azure em repouso](/azure/security/fundamentals/encryption-atrest) e [Criptografia de dados no Azure Cosmos DB](/azure/cosmos-db/database-encryption-at-rest).

As mudanças seguem Microsoft 365 diretrizes para criptografia de dados em trânsito. Para saber mais, confira [Criptografia para dados em trânsito](/compliance/assurance/assurance-encryption-in-transit).

A criptografia desloca dados em repouso e em trânsito são verificadas anualmente pela auditoria de conformidade do SOC2.

## <a name="can-i-access-immutable-copies-of-shifts-data"></a>Posso acessar cópias imutáveis de dados shifts?

Não armazenamos cópias imutáveis de dados shifts. Por exemplo, um gerente pode fazer alterações em um cronograma, como adicionar anotações, alterar horários de turno, atribuir tarefas e assim por diante.

## <a name="can-shifts-data-be-edited"></a>Os dados shifts podem ser editados?

Há certos aspectos de Shifts que não podem ser alterados e determinados aspectos que podem ser alterados. Por exemplo, detalhes de turno, como notas e cores, podem ser editados da mesma forma que podem ser alterados no aplicativo Shifts. As solicitações de turno não podem ser editadas, a menos que a solicitação seja retirada.

Para ver quais campos foram alterados, você pode pesquisar o log Microsoft 365 de auditoria para eventos Shifts. Para saber mais sobre os eventos que estão registrados para atividades shifts no log de auditoria Microsoft 365, consulte [Shifts in Teams activities](../../audit-log-events.md#shifts-in-teams-activities).

## <a name="my-organization-uses-a-workforce-management-system-for-scheduling-can-we-integrate-with-and-access-shifts-data"></a>Minha organização usa um sistema de gerenciamento de força de trabalho para agendamento. Podemos integrar e acessar dados shifts?

As mudanças Graph APIs permitem integrar dados shifts com sistemas WFM (gerenciamento de força de trabalho externo). Para saber mais, confira [Shifts Graph APIs](/graph/api/resources/shift).

Também oferecemos conectores shifts gerenciados e conectores shifts de código aberto. Com esses conectores, você pode integrar seu sistema WFM diretamente com Shifts. Para saber mais sobre conectores Shifts e sistemas WFM compatíveis, consulte [Shifts connectors](shifts-connectors.md).

## <a name="can-shifts-data-be-deleted-permanently-after-a-specified-period-of-time"></a>Os dados shifts podem ser excluídos permanentemente após um período especificado?

Hoje, não excluimos seus dados shifts. Usando [apIs shifts Graph](/graph/api/resources/shift), é possível criar um aplicativo usando Power Apps para [](/powerapps/maker/) reter dados por um período de tempo especificado. No entanto, não suportamos isso de forma nativa.

## <a name="can-shifts-data-be-moved-in-a-tenant-to-tenant-migration"></a>Os dados shifts podem ser movidos em uma migração de locatário para locatário?

Os dados de turnos podem ser migrados de um locatário para outro locatário mediante solicitação específica. Lembre-se de que a migração de locatário para locatário não é suportada de forma in-locada, mas pode ser criada como uma solicitação do cliente.

## <a name="related-articles"></a>Artigos relacionados

- [Turnos do Teams](../shifts-for-teams-landing-page.md)
- [Gerenciar o aplicativo Shifts](manage-the-shifts-app-for-your-organization-in-teams.md)
