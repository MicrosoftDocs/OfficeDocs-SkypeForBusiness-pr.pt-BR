---
title: Pesquisar o log de auditoria de eventos no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.reviewer: anach
search.appverid: MET150
description: Saiba como recuperar dados do Microsoft Teams a partir do log de auditoria do Office 365.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3f53d1a0b5e600de9d38233b243dba3486b88bf1
ms.sourcegitcommit: 6cfaadec5782ca7316db36472bd0be20217da693
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341619"
---
# <a name="search-the-audit-log-for-events-in-microsoft-teams"></a>Pesquisar o log de auditoria de eventos no Microsoft Teams

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

O log de auditoria pode ajudar na investigação de atividades específicas em todos os serviços do Office 365. Para o Microsoft Teams, estas são algumas das atividades auditadas:

- Criação de equipes

- Exclusão de equipes

- Canal adicionado

- Configuração alterada

> [!NOTE]
> Os eventos de auditoria de canais privados também são registrados como são para equipes e canais padrão.

Para ver a lista completa de atividades que são auditadas no Office 365, consulte [Pesquisar no log de auditoria no Centro de Conformidade e Segurança do Office 365](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c).

## <a name="turn-on-auditing-in-teams"></a>Ativar a auditoria no Microsoft Teams

Antes de poder ver os dados de auditoria, você deve primeiro ativar a auditoria no centro de [conformidade do & de segurança](https://protection.office.com). Para obter ajuda para ativar a auditoria, consulte [Ativar ou desativar a pesquisa no log de auditoria do Office 365](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).

> [!IMPORTANT]
> Os dados de auditoria estão disponíveis apenas a partir do momento em que a auditoria foi ativada.

## <a name="retrieve-teams-data-from-the-audit-log"></a>Recuperar dados do Microsoft Teams a partir do log de auditoria

1. Para recuperar logs de auditoria, vá até o [Centro de Conformidade e Segurança](https://go.microsoft.com/fwlink/?linkid=855775). Em **Pesquisar**, selecione **pesquisa de log de auditoria**.
1. Use a **Pesquisa** para filtrar pelas atividades, datas e usuários que você deseja auditar.
1. Exporte os resultados para o Excel para analisá-los melhor.

> [!IMPORTANT]
> Os dados de auditoria estarão visíveis no Log de Auditoria somente se a auditoria estiver ativada.

## <a name="external-user-scenario"></a>Cenário de usuário externo

Um cenário do qual você pode querer ficar atento, do ponto de vista dos negócios, é a adição de usuários externos ao seu ambiente de equipe. Se usuários externos estiverem habilitados, então a monitoração da presença será uma boa ideia.

![Captura de tela de uma lista de eventos disparados por exclusões em massa](media/TeamsExternalUserAddPolicy.png)

A captura de tela desta política para monitorar o usuário externo permite que você nomeie a política, defina a gravidade de acordo com suas necessidades comerciais, defina-a como (nesse caso) uma única atividade e, em seguida, estabeleça os parâmetros que monitorarão especificamente apenas a adição de usuários não internos e limitar essa atividade ao Microsoft Teams.

Em seguida, os resultados dessa política poderão ser visualizados no log de atividades:

![Captura de tela de uma lista de eventos disparados por exclusões em massa](media/TeamsExternalUserList.png)

Aqui você pode revisar as correspondências da política que definiu e fazer os ajustes necessários ou exportar os resultados para usar em outro lugar.

## <a name="mass-delete-scenario"></a>Cenário de exclusão em massa

Conforme mencionado acima, você pode monitorar cenários de exclusão. É possível criar uma política que monitoria a exclusão em massa de sites de equipe:

![Captura de tela da página Criar política mostrando a configuração de uma política para a detecção de exclusão da equipe em massa](media/TeamsMassDeletePolicy.png)

Conforme mostrado na captura de tela, você pode definir vários parâmetros diferentes para essa política para monitorar as exclusões do Teams, incluindo gravidade, ação única ou repetida e parâmetros que limitam isso a equipes e exclusão de sites. Isso pode ser feito independentemente de um modelo, ou você pode ter um modelo criado para basear essa política, dependendo das suas necessidades organizacionais.

Depois de estabelecer uma política que funcionará para a sua empresa, você pode revisar os resultados no registro de atividades à medida que os eventos são disparados:

![Captura de tela de uma lista de eventos disparados por exclusões em massa](media/TeamsMassDeleteList.png)

Você pode filtrar para baixo até a política definida para ver os resultados dessa política. Se os resultados que você está recebendo no registro de atividades não forem satisfatórios (talvez você esteja vendo muitos resultados ou nada), isso pode ajudá-lo a ajustar a consulta para torná-la mais relevante para o que você precisa.

## <a name="video-techtip-using-audit-log-search-in-teams"></a>Vídeo: Dicas de tecnologia: Como usar a pesquisa de log de auditoria no Microsoft Teams

Conheça Ansuman Acharya, gerente de programas do Microsoft Teams, que demonstra como realizar uma pesquisa de Log de Auditoria do Microsoft Teams no Centro de Conformidade e Segurança do Office 365.

> [!VIDEO https://www.youtube.com/embed/UBxaRySAxyE]
