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
description: Gerencie o acesso Teams aplicativos em Microsoft 365.
ms.openlocfilehash: 3fe95852fe88f64539ffa562d64619c1300b083b
ms.sourcegitcommit: abe942c294ed5fca70efdf039d38d611b9c21fe9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2022
ms.locfileid: "63689065"
---
# <a name="manage-access-to-teams-apps-across-microsoft-365"></a>Gerenciar o acesso a Teams aplicativos em Microsoft 365

Os desenvolvedores de aplicativos podem atualizar seus aplicativos Microsoft Teams para trabalhar no Outlook e no Office.com, além do aplicativo que está trabalhando Teams. Os usuários finais podem usar os aplicativos atualizados no Teams, no Microsoft Outlook e Microsoft Office.com após a atualização. Atualmente, somente os usuários finais na versão direcionada podem exibir e usar esses aplicativos específicos em Teams, Outlook e Office.com. A experiência de Teams administrador existente se aplica ao acesso de governança a esses aplicativos. Uma notificação sobre essa alteração está disponível no centro [de mensagens](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter/:/messages/MC334280). Como administrador Teams, você pode permitir que usuários finais específicos usem os aplicativos atualizados ou gerenciem o acesso aos aplicativos atualizados no Teams, no Outlook e no Office.com. Teams administradores usam o Teams de administração para gerenciar o acesso ao aplicativo.

Para uso em Outlook e Office.com, um aplicativo atualizado continua a usar as permissões existentes concedidas no Teams. Não há [nenhuma alteração nas permissões do aplicativo atualizado](https://devblogs.microsoft.com/microsoft365dev/ignite-2021-building-apps-for-collaboration-in-a-hybrid-world/#personal-tabs).

Você pode controlar o acesso do usuário final aos aplicativos Teams usando os métodos a seguir. Se você for um administrador Office Apps, entre em contato com o administrador global ou Teams para gerenciar o acesso ao aplicativo.

| Opções para gerenciar o acesso |Portal|Administrador global|Teams administrador|
|--|---|---|--|
| Somente os usuários finais em Versão direcionada podem acessar o novo aplicativo. Mova os usuários para a versão Padrão. Consulte [Configurar as opções de versão Padrão ou Direcionada](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) | Centro de administração do Microsoft 365 | Sim | Não |
| Gerencie o acesso ao novo aplicativo para usuários finais específicos. Consulte [Adicionar uma política de permissão personalizada](teams-app-permission-policies.md#create-a-custom-app-permission-policy) e [atribuir a política personalizada a um usuário](policy-assignment-overview.md). | Teams de administração | Sim | Sim |
| Gerencie o acesso aos novos aplicativos para todos os usuários finais em toda a sua organização. Consulte [Permitir ou bloquear aplicativos](manage-apps.md#allow-and-block-apps). | Teams de administração | Sim | Sim |

> [!NOTE]
> Recomendamos usar [a opção De versão padrão](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) para gerenciar o acesso do usuário final. As outras opções removem o acesso do usuário final e não poderão mais usar o aplicativo existente no Teams.

> [!NOTE]
> Os usuários que instalaram um complemento existente no mercado do mesmo aplicativo no Outlook e Office continuarão a usar esse aplicativo. Os complementos não são Teams aplicativos e Teams administradores não podem reger o acesso.

## <a name="see-also"></a>Confira também

* [Entenda as funções de administrador no Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide&preserve-view=true)  
* [Sobre Outlook de complementos](/office/dev/add-ins/outlook/outlook-add-ins-overview)
* [Como os desenvolvedores estendem Teams aplicativos para trabalhar em Microsoft 365](/microsoftteams/platform/m365-apps/overview)
