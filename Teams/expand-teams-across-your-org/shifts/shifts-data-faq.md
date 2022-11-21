---
title: Muda perguntas frequentes sobre dados
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Obtenha respostas para perguntas frequentes sobre dados shifts, incluindo onde os dados shifts são armazenados, retenção de dados, recuperação e criptografia.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- microsoftcloud-healthcare
- m365-frontline
- tier2
- highpri
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 39dcbc391096db8edce7dee90abe6ee26e24f027
ms.sourcegitcommit: ff161779577ce9cc892f1b6b8861ad49ff4c3ca3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2022
ms.locfileid: "69131020"
---
# <a name="shifts-data-faq"></a>Muda perguntas frequentes sobre dados

Este artigo aborda perguntas frequentes sobre dados shifts, incluindo onde os dados shifts são armazenados, retenção de dados, recuperação e criptografia.

## <a name="where-is-shifts-data-stored"></a>Onde os dados do Shifts são armazenados?

Os dados de turnos são armazenados em uma das três geografias (geográficos): Ásia-Pacífico (APAC), União Europeia (UE) ou Estados Unidos. Cada geográfico armazena dados em pelo menos duas regiões do data center do Azure para HA (Alta Disponibilidade) e DR (Recuperação de Desastre). Hoje, a Estados Unidos/América do Norte geograficamente usa data centers no Centro-Norte e Centro-Sul Estados Unidos. Para saber mais, confira [Onde estão armazenados os dados do cliente do Microsoft 365](/microsoft-365/enterprise/o365-data-locations).

Atualmente, o Shifts oferece residência de dados na Austrália, Canadá, França, Japão e Reino Unido. Estamos trabalhando ativamente para expandir o suporte para mais locais.

## <a name="can-i-choose-where-shifts-data-is-stored"></a>Posso escolher onde os dados do Shifts são armazenados?

Ao configurar o Teams pela primeira vez, você escolhe um país ou região, que é definido no nível da assinatura. Os turnos honram essa seleção e usam a localidade e a região definidas no Teams se dermos suporte a essa região. Se ainda não estivermos nessa região, armazenaremos dados em uma região próxima que oferecemos suporte. No futuro, planejamos migrar dados existentes, se armazenados em uma região próxima, para a região provisionada no Teams.

## <a name="can-i-access-and-export-or-delete-a-users-personal-data-in-shifts"></a>Posso acessar e exportar ou excluir dados pessoais de um usuário no Shifts?

Os turnos são compatíveis com o GDPR (Regulamento Geral de Proteção de Dados). Uma solicitação formal de uma pessoa (conhecida como um sujeito de dados) para tomar uma ação em seus dados pessoais é chamada de DSR (Solicitação de Assunto de Dados). Você pode localizar e agir em dados pessoais em Shifts em resposta a um DSR.

Você pode usar a ferramenta pesquisa de conteúdo eDiscovery no portal de conformidade do Microsoft Purview para pesquisar e exportar dados de agendamento e relógio de tempo para o Excel. Para todos os outros dados do Shifts, você pode tirar capturas de tela dos dados.

Para saber mais, consulte [Office 365 Solicitações de Assunto de Dados para o GDPR e o CCPA](/microsoft-365/compliance/gdpr-dsr-office365).

## <a name="what-happens-to-shifts-data-if-i-turn-off-shifts-for-my-organization"></a>O que acontece com os dados do Shifts se eu desativar o Shifts para minha organização?

Desativar turnos em sua organização *não* exclui dados. Se você desativar o Shifts e depois ativar o Shifts, os dados do Shifts ainda estarão disponíveis.

Se você excluir seu locatário, todos os dados do Shifts serão excluídos após o término do período de retenção.

Não há opção de excluir apenas dados do Shifts. Se você excluir uma equipe no Teams, shifts agendar dados associados a essa equipe serão excluídos após o término do período de retenção. Para saber mais, confira [Retenção, exclusão e destruição de dados no Microsoft 365](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview).

## <a name="can-i-recover-a-shifts-schedule-that-was-deleted"></a>Posso recuperar uma agenda de turnos que foi excluída?

Você pode recuperar uma agenda excluída se o grupo do Microsoft 365 que o apoia (ou a equipe no Teams) for restaurado.

Por padrão, um grupo do Microsoft 365 excluído é mantido por 30 dias. Esse período de 30 dias é chamado de "exclusão temporária" porque você ainda pode restaurar o grupo. Para saber mais, confira [Restaurar um grupo do Microsoft 365 excluído](/microsoft-365/admin/create-groups/restore-deleted-group?tabs=admin-center).

## <a name="can-i-use-custom-retention-policies-for-shifts-data"></a>Posso usar políticas de retenção personalizadas para dados shifts?

Atualmente, o Shifts não dá suporte a políticas de retenção personalizadas.

Para saber mais sobre políticas de retenção no Teams, consulte [Saiba mais sobre retenção para o Teams](/microsoft-365/compliance/retention-policies-teams) e [Gerenciar políticas de retenção para o Teams](../../retention-policies.md).

## <a name="can-i-retrieve-shifts-data-for-a-user-whose-license-was-revoked"></a>Posso recuperar dados do Shifts para um usuário cuja licença foi revogada?

Hoje, não oferecemos a capacidade de recuperar dados para um usuário cuja licença foi revogada. Essa funcionalidade é algo para o qual estamos trabalhando.

## <a name="what-type-of-encryption-does-shifts-use-for-data-at-rest-and-in-transit"></a>Que tipo de criptografia o Shifts usa para dados em repouso e em trânsito?

Os dados de shifts são criptografados em repouso pelo Azure Cosmos DB e pelo Armazenamento do Azure. Para saber mais, confira [Criptografia de dados do Azure em repouso](/azure/security/fundamentals/encryption-atrest) e [Criptografia de dados no Azure Cosmos DB](/azure/cosmos-db/database-encryption-at-rest).

Os turnos seguem as diretrizes do Microsoft 365 para criptografia de dados em trânsito. Para saber mais, confira [Criptografia para dados em trânsito](/compliance/assurance/assurance-encryption-in-transit).

A criptografia de turnos de dados em repouso e em trânsito é verificada anualmente pela auditoria de conformidade do SOC2.

## <a name="can-i-access-immutable-copies-of-shifts-data"></a>Posso acessar cópias imutáveis de dados shifts?

Não armazenamos cópias imutáveis de dados shifts. Por exemplo, um gerente pode fazer alterações em uma agenda, como adicionar anotações, alterar horários de turno, atribuir tarefas e assim por diante.

## <a name="can-shifts-data-be-edited"></a>Os dados do Shifts podem ser editados?

Há certos aspectos de Shifts que não podem ser alterados e certos aspectos que podem ser alterados. Por exemplo, detalhes de deslocamento, como anotações e cores, podem ser editados de forma semelhante à forma como podem ser alterados no aplicativo Shifts. As solicitações de turno não podem ser editadas a menos que a solicitação seja retirada.

Para ver quais campos foram alterados, você pode pesquisar o log de auditoria do Microsoft 365 em eventos Shifts. Para saber mais sobre os eventos registrados para atividades do Shifts no log de auditoria do Microsoft 365, consulte [Shifts nas atividades do Teams](../../audit-log-events.md#shifts-in-teams-activities).

## <a name="my-organization-uses-a-workforce-management-system-for-scheduling-can-we-integrate-with-and-access-shifts-data"></a>Minha organização usa um sistema de gerenciamento de força de trabalho para agendamento. Podemos nos integrar e acessar dados do Shifts?

As APIs do Graph shifts permitem integrar dados shifts a sistemas de gerenciamento externo de força de trabalho (WFM). Para saber mais, confira [As APIs do Gráfico de Turnos](/graph/api/resources/shift).

Também oferecemos conectores gerenciados do Shifts. Com esses conectores, você pode integrar seu sistema WFM diretamente ao Shifts. Para saber mais sobre conectores shifts e sistemas de WFM com suporte, confira [Conectores do Shifts](/microsoft-365/frontline/shifts-connectors).

## <a name="can-shifts-data-be-deleted-permanently-after-a-specified-period-of-time"></a>Os dados shifts podem ser excluídos permanentemente após um período de tempo especificado?

Hoje, não excluimos seus dados do Shifts. Usando [APIs do Shifts Graph](/graph/api/resources/shift), é possível [criar um aplicativo usando o Power Apps](/powerapps/maker/) para reter dados por um período de tempo especificado. No entanto, não apoiamos isso nativamente.

## <a name="can-shifts-data-be-moved-in-a-tenant-to-tenant-migration"></a>Os dados do Shifts podem ser movidos em uma migração de locatário para locatário?

Para migrar seus dados de Shifts existentes para outro locatário, você precisará exportar agendas de Turnos para um intervalo de datas, modificar nomes de usuário (se necessário) e importar os agendamentos para o locatário de destino. Você pode exportar até 100 dias de dados shifts por vez. O intervalo de datas pode estar no passado ou no futuro. Se você precisar exportar dados por um período maior que 100 dias, repita o processo.

Antes de migrar os dados do Shifts, verifique se os seguintes requisitos são atendidos:

- O domínio de locatário de destino, equipes e membros da equipe já devem existir. A migração não cria equipes nem altera a associação ou a propriedade da equipe.
- O aplicativo Shifts deve ser configurado em equipes no locatário de destino e ter uma agenda vazia. Tenha em mente que a migração não substitui nem exclui dados existentes. Isso significa que, se uma equipe tiver uma agenda existente, os usuários poderão ver turnos duplicados ou conflitantes, que precisam ser resolvidos manualmente.
- As solicitações abertas (como solicitações de troca e de tempo limite) que estão pendentes de aprovação não são migradas. Recomendamos fechar todas as solicitações abertas antes de começar a migrar dados.

Veja uma visão geral das etapas para migrar os dados do Shifts para outro locatário.

1. No locatário de origem, para cada equipe, exporte a agenda Shifts:
    1. Em Turnos, na página **Agendar**, acesse **Mais opções (...)** >  **Agenda de exportação**.
    1. Selecione um intervalo de datas.
    1. Ative **Exportar em um formato que pode ser importado** e selecione **Exportar**. Os dados de agendamento de turnos são exportados para um arquivo do Excel.
1. Como parte da migração, se algum membro da equipe estiver alternando seu domínio de email, atualize manualmente o arquivo do Excel para alterar o UPN (nome da entidade de usuário) desses usuários para o domínio de locatário de destino.
1. No locatário de destino, importe o agendamento para cada equipe.
    1. Em Turnos, na página **Agendar**, acesse **Mais opções (...)** >  **Agenda de importação**.
    1. Selecione **Carregar arquivo**, vá para o arquivo do Excel para essa equipe e selecione **Abrir**.

Para saber mais, confira [O modelo do Excel para Shifts](https://support.microsoft.com/office/the-excel-template-for-shifts-6fc6a206-e7cc-4907-87b8-a296bae84ce3).

## <a name="related-articles"></a>Artigos relacionados

- [Turnos do Teams](../shifts-for-teams-landing-page.md)
- [Gerenciar o aplicativo Shifts](manage-the-shifts-app-for-your-organization-in-teams.md)
