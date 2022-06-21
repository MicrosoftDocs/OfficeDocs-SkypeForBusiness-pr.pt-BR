---
title: Gerenciar o acesso a Teams aplicativos em Microsoft 365
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.reviewer: v-tbasra
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba como gerenciar o acesso a Teams aplicativos em Microsoft 365.
ms.openlocfilehash: 34587bd02f9fddb73bce8e159b9df317b3bc619a
ms.sourcegitcommit: 9946c6c1faa78617ccd7bdf115457090ebce5619
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/21/2022
ms.locfileid: "66190606"
---
# <a name="manage-access-to-teams-apps-across-microsoft-365"></a>Gerenciar o acesso a Teams aplicativos em Microsoft 365

Os desenvolvedores de aplicativos podem aprimorar seus aplicativos Microsoft Teams para trabalhar no Outlook e no Office.com, além do aplicativo que está trabalhando no Teams. Os usuários finais podem usar os aplicativos aprimorados no Teams, no Microsoft Outlook e Microsoft Office.com após o aprimoramento. Atualmente, somente os usuários finais na versão direcionada podem exibir e usar esses aplicativos específicos no Teams, Outlook e Office.com. A experiência Teams administrador existente se aplica para controlar o acesso a esses aplicativos. Uma notificação sobre essa alteração está disponível no centro [de mensagens](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter/:/messages/MC334280). Como administrador do Teams, você pode permitir que usuários finais específicos usem os aplicativos aprimorados ou gerenciem seu acesso aos aplicativos aprimorados no Teams, no Outlook e no Office.com. Teams administradores usam o Teams de administração para gerenciar o acesso ao aplicativo.

Para uso no Outlook e Office.com, um aplicativo aprimorado continua a usar as permissões existentes concedidas no Teams. Não há [nenhuma alteração nas permissões do aplicativo aprimorado](https://devblogs.microsoft.com/microsoft365dev/ignite-2021-building-apps-for-collaboration-in-a-hybrid-world/#personal-tabs).

A seguir está uma lista dos aplicativos aprimorados:

* [Monday.com](https://teams.microsoft.com/l/app/eab2d3ce-6d6a-4415-abc4-5f40a8317b1f)
* [Mural](https://teams.microsoft.com/l/app/c738b607-88dd-4f16-aefe-6a824c65d25d)
* [Power BI](https://teams.microsoft.com/l/app/1c4340de-2a85-40e5-8eb0-4f295368978b)
* [SurveyMonkey](https://teams.microsoft.com/l/app/0fd925a0-357f-4d25-8456-b3022aaa41a9)
* [Zoho Projects](https://teams.microsoft.com/l/app/4a39aea9-8537-4c2f-b66d-ca364eb3b80d)
* [YouTube](https://teams.microsoft.com/l/app/com.microsoft.teamspace.tab.youtube)

Você pode controlar o acesso do usuário final aos aplicativos Teams usando os métodos a seguir. Se você for um administrador do Office Apps, entre em contato com o administrador global ou Teams administrador para gerenciar o acesso ao aplicativo.

| Opções para gerenciar o acesso |Portal|Administrador global|Teams administrador|
|--|---|---|--|
| Somente os usuários finais na versão direcionada podem acessar o novo aplicativo. Mova os usuários para a versão Standard. Consulte [Configurar as opções de versão Standard ou Targeted](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) | Centro de administração do Microsoft 365 | Sim | Não |
| Gerencie o acesso ao novo aplicativo para usuários finais específicos. Consulte [Adicionar uma política de permissão personalizada](teams-app-permission-policies.md#create-a-custom-app-permission-policy) [e atribuir a política personalizada a um usuário](policy-assignment-overview.md). | Centro de administração do Teams | Sim | Sim |
| Gerencie o acesso aos novos aplicativos para todos os usuários finais em sua organização. Consulte [Permitir ou bloquear aplicativos](manage-apps.md#allow-and-block-apps). | Centro de administração do Teams | Sim | Sim |

> [!NOTE]
> É recomendável usar [a opção de versão Standard](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) para gerenciar o acesso do usuário final. As outras opções removem o acesso do usuário final e não poderão mais usar o aplicativo existente no Teams.

> [!NOTE]
> Os usuários que instalaram suplementos existentes no mercado do mesmo aplicativo no Outlook e Office continuarão a usar esse aplicativo. Os suplementos não são Teams e Teams administradores não podem controlar o acesso.

## <a name="see-also"></a>Confira também

* [Microsoft Teams aplicativos projetados para Microsoft 365 em versão prévia para Outlook e Office.com](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-teams-apps-designed-for-microsoft-365-coming-in/ba-p/3269538)
* [Entender as funções de administrador no Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide&preserve-view=true)  
* [Sobre Outlook suplementos](/office/dev/add-ins/outlook/outlook-add-ins-overview)
* [Como os desenvolvedores estendem Teams aplicativos para trabalhar em Microsoft 365](/microsoftteams/platform/m365-apps/overview)
