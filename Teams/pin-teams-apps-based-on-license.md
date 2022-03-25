---
title: Personalizar Teams aplicativos para seus funcionários de linha de frente
author: LanaChin
ms.author: v-lanachin
ms.reviewer: aaglick
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba mais sobre a experiência de aplicativo personalizada para os funcionários de linha de frente Teams.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: b526733558570e4903d9dce43094c7ffa0f7de17
ms.sourcegitcommit: b91d83739a078b175770c797c17d602eb5c83a4f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2022
ms.locfileid: "63774180"
---
# <a name="tailor-teams-apps-for-your-frontline-workers"></a>Personalizar Teams aplicativos para seus funcionários de linha de frente

> [!NOTE]
> [!INCLUDE [new-feature-coming-soon-section](includes/new-feature-coming-soon-section.md)]

## <a name="overview"></a>Visão Geral

Teams fornece uma maneira fácil de fixar aplicativos para trabalhadores de linha de frente. Esse recurso fixa aplicativos com base na licença para dar aos seus funcionários de linha de frente uma experiência completa em Teams que são adaptados às suas necessidades.

Com a experiência do aplicativo frontline personalizada, os funcionários de linha de frente obterão os aplicativos mais relevantes no Teams sem qualquer ação necessária do administrador.

## <a name="tailored-frontline-app-experience"></a>Experiência de aplicativo de linha de frente personalizada

Os aplicativos são fixados na barra de aplicativos, que é a barra na parte inferior dos clientes móveis do Teams (iOS e Android) e no lado do cliente de Teams desktop. Os seguintes aplicativos são fixados para usuários que têm uma [licença F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt):

- [Atividade](https://support.microsoft.com/office/explore-the-activity-feed-in-teams-91c635a1-644a-4c60-9c98-233db3e13a56)
- [Chat](https://support.microsoft.com/office/get-started-with-chat-0b506ce2-eb6d-4fca-9668-e56980ba755e)
- [Microsoft Teams](https://support.microsoft.com/office/teams-and-channels-in-microsoft-teams-c6d0e61d-a61e-44a6-a972-04f2a8fa4155)
- [Walkie Talkie](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Tarefas](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070)
- [Turnos](https://support.microsoft.com/office/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821)
- [Aprovações](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3)

**Teams celular**

:::image type="content" source="media/tailored-teams-apps-mobile.png" alt-text="A experiência de aplicativo de frontline personalizada em Teams celular" lightbox="media/tailored-teams-apps-mobile.png"::: 

**Teams desktop**

:::image type="content" source="media/tailored-teams-apps-desktop.png" alt-text="A experiência de aplicativo de linha de frente personalizada na Teams desktop" lightbox="media/tailored-teams-apps-desktop.png"::: 

## <a name="admin-controls"></a>Controles de administrador

> [!NOTE]
> A **configuração de fixação** de usuário deve ser atada na política de configuração de aplicativo global (padrão de toda a [organização) para](teams-app-setup-policies.md) que esse recurso entre em vigor.

A experiência do aplicativo de frontline personalizada é controlada pela  configuração mostrar aplicativos personalizados em toda a organização [](manage-apps.md#manage-org-wide-app-settings) na página Gerenciar aplicativos do centro de administração Teams. Se o recurso estiver em funcionamento, todos os usuários da sua organização que têm uma licença F obterão a experiência de aplicativo personalizada.

Tenha em mente que quaisquer políticas de configuração [de aplicativo](teams-app-setup-policies.md) personalizadas atribuídas aos usuários têm precedência. Isso significa que, se um usuário já tiver uma política de configuração de aplicativo personalizada atribuída a ele, o usuário obtém a configuração definida na política de configuração de aplicativo personalizada. Para saber mais sobre como o recurso funciona com Teams de aplicativos, incluindo a política de configuração de aplicativo global, consulte a seção [Cenários](#scenarios) mais adiante neste artigo.

Esse recurso está habilitado por padrão. No entanto, se você não quiser a experiência de aplicativo de frontline personalizada fornecida pela Microsoft, poderá desativar o recurso. Para desativar ou ativar o recurso:

1. Na navegação à esquerda do centro de administração Microsoft Teams, vá para Teams **appsManage** >  e selecione **Configurações de** aplicativos em toda a organização.
2. Em **Aplicativos personalizados**, alterne a alternância **Mostrar aplicativos** personalizados para **Off** ou **On**.

    :::image type="content" source="media/tailored-teams-apps-admin-center.png" alt-text="Captura de tela da configuração Mostrar aplicativos personalizados na página Gerenciar aplicativos do Teams de administração" lightbox="media/tailored-teams-apps-admin-center.png":::

## <a name="scenarios"></a>Cenários

### <a name="how-does-the-tailored-frontline-app-experience-affect-my-global-app-setup-policy"></a>Como a experiência do aplicativo de frontline personalizada afeta minha política de configuração de aplicativo global?

Saiba como a experiência de aplicativo de frontline personalizada funciona em conjunto com a política de configuração de aplicativo global. Os cenários nesta tabela se aplicam aos trabalhadores de linha de frente que têm uma licença F e a política de configuração de aplicativo global, com o **pinamento do** usuário ligado.

|Se... |Em seguida, ... |
|---------|---------|
|Um trabalhador de linha de frente tem a política de configuração de aplicativo global e o recurso está desligado. |O trabalhador de linha de frente obtém os aplicativos definidos na política de configuração de aplicativo global.|
|Um trabalhador de linha de frente tem a política de configuração de aplicativo global e o recurso está em.     | O trabalhador da linha de frente obtém a experiência de aplicativo de linha de frente personalizada. Os aplicativos definidos na política de configuração de aplicativo global são fixados abaixo dos aplicativos personalizados.      |
|Você atualiza a política de configuração de aplicativo global e o recurso está em.     |O trabalhador de linha de frente obtém a experiência de aplicativo de frontline personalizada e os aplicativos definidos na política de configuração de aplicativo global são fixados abaixo dos aplicativos personalizados.         |
|Um trabalhador de linha de frente tem a política de configuração de aplicativo global e o **pinamento do** usuário está desligado. |O trabalhador de linha de frente obtém os aplicativos definidos na política de configuração de aplicativo global.|
|Um trabalhador de linha de frente tem a política de configuração de aplicativo global e a política de configuração de aplicativo global é alterada para incluir um aplicativo de linha de negócios (LOB) na segunda posição na lista de aplicativos. |O aplicativo LOB é fixado abaixo dos aplicativos personalizados. O trabalhador da linha de frente pode alterar a ordem do aplicativo se **o pinamento do** usuário estiver.         |
|Um trabalhador de linha de frente tem a política de configuração global e a política de configuração de aplicativo global é alterada para incluir Shifts na primeira posição.  |Shifts é fixado na sexta posição, conforme definido pela experiência do aplicativo frontline personalizado. O trabalhador da linha de frente pode alterar a ordem do aplicativo se **o pinamento do** usuário estiver.          |

### <a name="how-does-the-tailored-frontline-app-experience-work-with-other-teams-app-policies"></a>Como a experiência do aplicativo frontline personalizada funciona com outras políticas Teams aplicativos?

Saiba como a experiência de aplicativo de linha de frente personalizada funciona com outras Teams de aplicativos.

|Se...  |Em seguida, ... |
|---------|---------|
O recurso está desligado.   | O trabalhador de linha de frente obtém os aplicativos definidos na política de configuração de aplicativo global ou na política de configuração de aplicativo personalizada atribuída a eles.          |
|Um trabalhador de linha de frente tem uma política de configuração de aplicativo personalizada e o recurso está em.    |O trabalhador de linha de frente obtém os aplicativos definidos na política de configuração de aplicativo personalizada.          |
|Um aplicativo na experiência de aplicativo de linha de frente personalizada é bloqueado para um usuário ou para sua organização.      |A experiência do aplicativo frontline personalizada honra a política [de permissão do aplicativo](teams-app-permission-policies.md). Se um aplicativo for bloqueado, o trabalhador de linha de frente não verá o aplicativo bloqueado.           |
|Um aplicativo na experiência de aplicativo de linha de frente personalizada já está definido em uma política de configuração de aplicativo e o recurso está em. |O aplicativo é fixado com base na ordem definida pela lista de aplicativos personalizados.        |
|Um usuário tem uma licença E, A ou G e o recurso está em.   | O usuário não tem a experiência de aplicativo de linha de frente personalizada. Atualmente, a experiência se aplica somente aos usuários que têm uma licença F.        |

> [!NOTE]
> Não é possível alterar os aplicativos ou a ordem dos aplicativos na experiência do aplicativo frontline personalizado. Por enquanto, se você quiser fazer alterações, poderá configurar sua própria experiência personalizada. Para fazer isso, primeiro desligue o recurso. Em seguida, [crie uma política de configuração de aplicativo personalizada](teams-app-setup-policies.md) e [atribua-a a usuários ou grupos](assign-policies-users-and-groups.md).

## <a name="related-articles"></a>Artigos relacionados

- [Gerenciar o aplicativo Walkie Talkie no Teams](walkie-talkie.md)
- [Gerenciar o aplicativo Tarefas em Teams](manage-tasks-app.md)
- [Gerenciar o aplicativo Shifts no Teams](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)
- [Gerenciar o aplicativo Aprovações em Teams](approval-admin.md)
- [Gerenciar políticas de configuração de aplicativo no Teams](teams-app-setup-policies.md)
- [Gerenciar políticas de permissões de aplicativo no Teams](teams-app-permission-policies.md)
