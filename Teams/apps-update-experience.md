---
title: Experiência de atualização de aplicativos no Microsoft Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.date: 10/22/2022
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Neste artigo, saiba como os aplicativos da Microsoft, aplicativos personalizados e aplicativos de terceiros no Microsoft Teams são atualizados e como os administradores facilitam isso.
ms.openlocfilehash: d419e1ed29c6a1cd7a7390bdc0d5eb69371d8547
ms.sourcegitcommit: 22f66e314e631b3c9262c5c7dc5664472f42971e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2022
ms.locfileid: "68912790"
---
# <a name="role-of-an-admin-in-upgrading-teams-apps"></a>Função de um administrador na atualização de aplicativos do Teams

Os administradores do Teams podem ajudar seus usuários finais a obter a versão mais recente dos aplicativos. Para fazer isso, eles realizam uma ou ambas as tarefas a seguir:

* [Atualize aplicativos de terceiros](#updates-to-third-party-apps) que estão disponíveis na loja do Teams quando uma nova versão for fornecida pelo desenvolvedor ou fornecedor do aplicativo.
* [Atualize aplicativos personalizados](#updates-to-custom-apps) que estão disponíveis somente em sua organização quando o desenvolvedor enviar uma nova versão.

## <a name="updates-to-third-party-apps"></a>Atualizações para aplicativos de terceiros

Para que os usuários instalem e usem um aplicativo, eles devem dar permissões ao aplicativo para acessar os serviços e informações necessários. Na maioria dos casos, quando uma nova versão de um aplicativo instalado está disponível na loja do Teams, o aplicativo é atualizado automaticamente para todos os usuários. No entanto, algumas alterações específicas na nova versão do aplicativo exigem uma permissão do usuário novamente. Essa aceitação repetida do usuário garante a conscientização sobre as alterações, como funcionalidade ou acesso a informações pessoais. Os administradores do Teams podem [fornecer permissões a um aplicativo em nome dos usuários](app-permissions-admin-center.md).

Se os desenvolvedores de aplicativos fizerem uma ou mais alterações a seguir em seus aplicativos, os usuários finais devem aprovar a atualização do aplicativo.

* Adicione um bot. Altere a ID do bot usando a `botId` propriedade.
* Altere a `isNotificationOnly` propriedade de um bot existente que pode alterar as notificações do bot.
* Altere `SupportsCalling`, `SupportsVideo`e `SupportsFiles` propriedades de um bot existente para adicionar recursos para chamar, reproduzir vídeo e carregar ou baixar arquivos.
* Adicionar ou remover permissões na autorização.
* Adicione ou remova uma extensão de mensagens, adicione uma guia de grupo, adicione um conector ou adicione um canal.
* Altere parâmetros [`webApplicationInfo`](/microsoftteams/platform/resources/schema/manifest-schema#webapplicationinfo) no arquivo de manifesto.

<!--- image update
:::image type="content" source="media/manage-your-custom-apps-update1.png" alt-text="New version available." lightbox="media/manage-your-custom-apps-update1.png":::

:::image type="content" source="media/manage-your-custom-apps-update2.png" alt-text="Upgrade option for an app." lightbox="media/manage-your-custom-apps-update2.png":::
--->

## <a name="updates-to-custom-apps"></a>Atualizações para aplicativos personalizados

Aplicativos personalizados que são criados e implantados em sua organização estão disponíveis para os usuários em seu locatário ou organização. O administrador do Teams atualiza um aplicativo personalizado para sua nova versão quando uma nova versão é fornecida pelos desenvolvedores de sua organização. Para obter mais informações, confira [como os administradores gerenciam aplicativos personalizados](custom-app-overview.md).

## <a name="related-articles"></a>Artigos relacionados

* [Entenda o esquema de manifesto para atualizações feitas em aplicativos](/microsoftteams/platform/resources/schema/manifest-schema).
* [Saiba mais sobre o gerenciamento de aplicativos personalizados](custom-app-overview.md).
