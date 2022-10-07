---
title: Pesquisar os logs de auditoria para eventos de gerenciamento de aplicativos
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.date: 08/24/2022
ms.collection:
- M365-collaboration
search.appverid: MET150
f1keywords: ''
description: Saiba como auditar as atividades do aplicativo Teams de usuários e administradores em sua organização.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 7abaed00f8bb02daa63d30cd5092e007f8d5a8f5
ms.sourcegitcommit: 6e85f3f70f8488ab827ac352c0f324b6dfd4b856
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68377529"
---
# <a name="audit-for-app-management-activities-and-events"></a>Auditoria para atividades e eventos de gerenciamento de aplicativos

A Auditoria do Microsoft Purview (Standard) no Microsoft 365 permite pesquisar registros de auditoria de atividades executadas nos vários serviços do Microsoft 365 por usuários finais e administradores.

Antes de pesquisar a auditoria, verifique se você concluiu os seguintes pré-requisitos:

* [Obtenha a assinatura da organização e o licenciamento do usuário](/microsoft-365/compliance/set-up-basic-audit).
* [Ative a auditoria no portal de conformidade do Microsoft Purview](/microsoft-365/compliance/turn-audit-log-search-on-or-off).
* [Atribua permissões para pesquisar o log de auditoria](/microsoft-365/compliance/set-up-basic-audit).

## <a name="search-the-audit-logs-for-app-events-in-teams"></a>Pesquisar os logs de auditoria para eventos do aplicativo no Teams

Os logs de auditoria para eventos de aplicativo no Teams ajudam você a investigar ações específicas. Embora você possa pesquisar nos logs uma ampla variedade de ações, a tabela a seguir lista algumas das ações de aplicativo do Teams registradas. Além disso, você pode pesquisar atividades relacionadas a Conectores, bots, guias e assim por diante.

| Ação do aplicativo Teams                  | Nome da atividade                | Descrição                                              |
|-----------------------------------|------------------------------|:---------------------------------------------------------|
| **Aplicativo instalado**                 | `AppInstalled`               | Um aplicativo é instalado.                                     |
| **Aplicativo atualizado**                  | `AppUpgraded`                | Um aplicativo é atualizado para sua versão mais recente no catálogo. |
| **Aplicativo desinstalado**               | `AppUninstalled`             | Um aplicativo é desinstalado.                                   |
| **Aplicativo publicado**                 | `AppPublishedToCatalog`      | Um aplicativo é adicionado ao catálogo.                          |
| **Aplicativo atualizado**                   | `AppUpdatedInCatalog`        | Um aplicativo é atualizado no catálogo.                        |
| **Aplicativo excluído**                   | `AppDeletedFromCatalog`      | Um aplicativo é excluído do catálogo.                      |
| **Todos os aplicativos da organização excluídos** | `DeletedAllOrganizationApps` | Todos os aplicativos da organização foram excluídos do catálogo.          |

Para obter uma lista completa das atividades do Teams auditadas, consulte [atividades do Teams](audit-log-events.md#teams-activities) e [Turnos nas atividades do Teams](audit-log-events.md#shifts-in-teams-activities).

> [!NOTE]
> Eventos de aplicativo de canais privados também são registrados como esses eventos são para o Teams e canais padrão.

Use a ferramenta de pesquisa de log de Auditoria no portal de conformidade para pesquisar registros de auditoria. Para pesquisar logs de auditoria de eventos de aplicativo, siga estas etapas:

1. Entre no portal de conformidade do Microsoft Purview e vá para **Soluções** > **[Auditoria](https://compliance.microsoft.com/auditlogsearch)**.
1. Na página de auditoria, atualize os seguintes campos de acordo com suas necessidades:

   * **Intervalo de data e hora**: selecione a data de início e término.
   * **Atividades**: insira as atividades do Microsoft Teams. Na lista, selecione uma ou mais atividades do aplicativo. Para localizar rapidamente as atividades do Teams, você pode pesquisar a palavra `Teams activities` no campo de pesquisa **Atividades**.
   * **Arquivo, pasta ou site**: insira o nome do arquivo ou uma URL ou parte dele.
   * **Usuários**: adicione os usuários cujo log de auditoria você deseja pesquisar.

1. Selecione **Pesquisar**.

   :::image type="content" source="media/compliance-search-teams-activities-trimmed.png" alt-text="Pesquise atividades do Teams no portal de conformidade do Microsoft Purview para auditar eventos do Teams." lightbox="media/compliance-search-teams-activities.png":::

Depois de pesquisar o sinal de auditoria no portal de conformidade, você pode exportar os registros de auditoria como um arquivo CSV. Para obter mais informações, consulte [Exportar, configurar e exibir logs de auditoria](/microsoft-365/compliance/export-view-audit-log-records).

> [!NOTE]
> Quando uma das atividades acima é executada por um usuário ou administrador, o Teams gera e armazena um registro de auditoria. Na Auditoria (Padrão), os registros são mantidos por 90 dias, o que significa que você pode pesquisar atividades que ocorreram nos últimos três meses.

> [!TIP]
> Como administrador, se você quiser criar um relatório por usuário para saber se um usuário bloqueou ou desativou o mudo de um bot, consulte Entender quem bloqueou, ative ou desinstalou um [bot](/microsoftteams/platform/bots/how-to/conversations/send-proactive-messages?#understand-who-blocked-muted-or-uninstalled-a-bot).

## <a name="related-articles"></a>Artigos relacionados

* [Use logs de auditoria para investigar a atividade de instalação do Microsoft Power Platform](manage-power-platform-apps.md#use-audit-logs-to-investigate-microsoft-power-platform-installation-activity)
* [Pesquisar a entrada de auditoria no portal de conformidade](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).
* [Visão geral do Auditoria Premium do Microsoft Purview](/microsoft-365/compliance/advanced-audit).
* [Ativar ou desativar a auditoria](/microsoft-365/compliance/turn-audit-log-search-on-or-off).
