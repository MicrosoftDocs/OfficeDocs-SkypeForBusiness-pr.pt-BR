---
title: Pesquisar os logs de auditoria para eventos de gerenciamento de aplicativos
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.date: 12/02/2022
ms.collection:
- M365-collaboration
search.appverid: MET150
f1keywords: ''
description: Saiba como auditar as atividades do aplicativo Teams de usuários e administradores em sua organização.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 5aee5bf00d486586b4bc8e9583504be5e4a9b922
ms.sourcegitcommit: 54c691bd34980a47a5ebf58555529a618a8cada7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2022
ms.locfileid: "69251874"
---
# <a name="search-audit-logs-for-app-management-activities-and-events"></a>Pesquisar logs de auditoria para atividades e eventos de gerenciamento de aplicativos

A Auditoria do Microsoft Purview (Standard) no Microsoft 365 permite pesquisar registros de auditoria de atividades executadas nos vários serviços do Microsoft 365 por usuários finais e administradores.

Antes de pesquisar os registros de auditoria, verifique se você completa os seguintes pré-requisitos:

* [Obtenha a assinatura da organização e o licenciamento do usuário](/microsoft-365/compliance/set-up-basic-audit).
* [Ative a auditoria no portal de conformidade do Microsoft Purview](/microsoft-365/compliance/turn-audit-log-search-on-or-off).
* [Atribua permissões para pesquisar o log de auditoria](/microsoft-365/compliance/set-up-basic-audit).

## <a name="search-the-audit-logs-for-app-events-in-teams"></a>Pesquisar os logs de auditoria para eventos do aplicativo no Teams

Os logs de auditoria para eventos de aplicativo no Teams ajudam você a investigar ações específicas relacionadas ao gerenciamento de aplicativos por administradores. Embora você possa pesquisar nos logs uma ampla gama de ações, a tabela a seguir lista algumas dessas ações que estão registradas.

| Ação do aplicativo Teams | Nome da atividade no Portal | Descrição  |
|-------|-------|:-------|
| **Aplicativo instalado**                 | `AppInstalled`               | Um aplicativo é instalado ou adicionado a um cliente do Teams. |
| **Aplicativo atualizado**                  | `AppUpgraded`                | Um aplicativo é atualizado para sua versão mais recente no catálogo. |
| **Aplicativo desinstalado**               | `AppUninstalled`             | Um aplicativo é desinstalado ou removido de um cliente do Teams.                                   |
| **Aplicativo publicado**                 | `AppPublishedToCatalog`      | Um aplicativo é adicionado ao catálogo.                          |
| **Aplicativo atualizado**                   | `AppUpdatedInCatalog`        | Um aplicativo é atualizado no catálogo.                        |
| **Aplicativo excluído**                   | `AppDeletedFromCatalog`      | Um aplicativo é excluído do catálogo.                      |
| **Todos os aplicativos da organização excluídos** | `DeletedAllOrganizationApps` | Todos os aplicativos da organização foram excluídos do catálogo.          |

<!--- organization apps = custom or 3p --->

Para obter uma lista completa das atividades do Teams auditadas, consulte [atividades do Teams](audit-log-events.md#teams-activities) e [Turnos nas atividades do Teams](audit-log-events.md#shifts-in-teams-activities).

> [!NOTE]
> Eventos de aplicativo de canais privados também são registrados, pois esses eventos são realizados no Teams e nos canais padrão.

Para pesquisar os logs de auditoria das atividades de aplicativo do Teams, siga estas etapas:

1. Entre no portal de conformidade do Microsoft Purview e vá para **Soluções** > **[Auditoria](https://compliance.microsoft.com/auditlogsearch)**.
1. Na página **Auditoria** , atualize os seguintes campos conforme necessário:

   * **Intervalo de data e hora**: selecione as datas de início e término do período de tempo para o qual você deseja verificar os logs de auditoria.
   * **Atividades**: insira as atividades do Microsoft Teams. Na lista, selecione uma ou mais atividades do aplicativo. Para localizar rapidamente as atividades do Teams, você pode pesquisar a palavra `Teams activities` no campo de pesquisa **Atividades**.
   * **Arquivo, pasta ou site**: insira o nome do arquivo ou uma URL ou parte dele.
   * **Usuários**: adicione os usuários cujo log de auditoria você deseja pesquisar.

1. Selecione **Pesquisar**.

   :::image type="content" source="media/compliance-search-teams-activities-trimmed.png" alt-text="Pesquise atividades do Teams no portal de conformidade do Microsoft Purview para auditar eventos do Teams." lightbox="media/compliance-search-teams-activities.png":::

Você pode exportar os registros de auditoria pesquisados como um arquivo CSV. Para obter mais informações, consulte [Exportar, configurar e exibir logs de auditoria](/microsoft-365/compliance/export-view-audit-log-records).

> [!NOTE]
> Quando uma das atividades acima é executada por um usuário ou administrador, o Teams gera e armazena um registro de auditoria. Na Auditoria (Padrão), os registros são mantidos por 90 dias, o que significa que você pode pesquisar atividades que ocorreram nos últimos três meses.

> [!TIP]
> Como administrador, se você quiser criar um relatório por usuário para saber se um usuário bloqueou ou silenciou um bot, consulte [Entender quem bloqueou, silenciou ou desinstalou um bot](/microsoftteams/platform/bots/how-to/conversations/send-proactive-messages?#understand-who-blocked-muted-or-uninstalled-a-bot).

## <a name="related-articles"></a>Artigos relacionados

* [Use logs de auditoria para investigar a atividade de instalação do Microsoft Power Platform](manage-power-platform-apps.md#use-audit-logs-to-investigate-microsoft-power-platform-installation-activity)
* [Pesquisar a entrada de auditoria no portal de conformidade](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).
* [Visão geral do Auditoria Premium do Microsoft Purview](/microsoft-365/compliance/advanced-audit).
* [Ativar ou desativar a auditoria](/microsoft-365/compliance/turn-audit-log-search-on-or-off).
