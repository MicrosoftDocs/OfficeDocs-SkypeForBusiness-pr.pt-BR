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
ms.date: 09/04/2022
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Neste artigo, saiba como os aplicativos da Microsoft, aplicativos personalizados e aplicativos de terceiros no Microsoft Teams são atualizados e como os administradores facilitam isso.
ms.openlocfilehash: 14c327c2a24536f5441b318767e301ffe9a3196d
ms.sourcegitcommit: 6e85f3f70f8488ab827ac352c0f324b6dfd4b856
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68376809"
---
# <a name="teams-app-updates-and-admin-role"></a>Atualizações de aplicativos do Teams e função de administrador

Os administradores do Teams podem ajudar os usuários finais a obter a versão mais recente dos aplicativos. Para fazer isso, eles realizam uma ou ambas as seguintes tarefas:

* [Atualize aplicativos de](#updates-to-third-party-apps) terceiros que estão disponíveis na loja do Teams quando uma nova versão for fornecida pelo desenvolvedor ou fornecedor do aplicativo.
* [Atualize os aplicativos](#updates-to-custom-apps) personalizados que estão disponíveis somente em sua organização quando o desenvolvedor enviar uma nova versão.

## <a name="updates-to-third-party-apps"></a>Atualizações aplicativos de terceiros

Para que os usuários instalem e usem um aplicativo, eles devem conceder permissões ao aplicativo para acessar os serviços e informações necessários. Na maioria dos casos, quando uma nova versão de um aplicativo instalado está disponível na loja do Teams, o aplicativo é atualizado automaticamente para todos os usuários. No entanto, algumas alterações específicas na nova versão do aplicativo exigem uma permissão de usuário novamente. Essa aceitação repetida do usuário garante a conscientização sobre as alterações, como funcionalidade ou acesso a informações pessoais. Os administradores do Teams [podem fornecer permissões para um aplicativo em nome dos usuários](app-permissions-admin-center.md).

Se os desenvolvedores de aplicativos fizerem uma ou mais alterações a seguir em seus aplicativos, os usuários finais deverão aprovar a atualização do aplicativo.

* Adicionar ou remover um bot. Altere a ID do bot usando a `botId` propriedade.
* Altere `isNotificationOnly` a propriedade de um bot existente que pode alterar as notificações do bot.
* Altere `SupportsCalling``SupportsVideo`e as propriedades `SupportsFiles` de um bot existente para adicionar a capacidade de chamar, reproduzir vídeo e carregar ou baixar arquivos.
* Adicionar ou remover permissões na autorização.
* Adicione ou remova uma extensão de mensagens, adicione uma guia de grupo, adicione um conector ou adicione um canal.
* Altere os parâmetros no [`webApplicationInfo`](/microsoftteams/platform/resources/schema/manifest-schema#webapplicationinfo) arquivo de manifesto.

<!--- image update
:::image type="content" source="media/manage-your-custom-apps-update1.png" alt-text="New version available." lightbox="media/manage-your-custom-apps-update1.png":::

:::image type="content" source="media/manage-your-custom-apps-update2.png" alt-text="Upgrade option for an app." lightbox="media/manage-your-custom-apps-update2.png":::
--->

## <a name="updates-to-custom-apps"></a>Atualizações aplicativos personalizados

Aplicativos personalizados criados e implantados em sua organização estão disponíveis para os usuários em seu locatário ou organização. O administrador do Teams atualiza os aplicativos personalizados para novas versões, conforme fornecido pelos desenvolvedores dentro da organização. Para obter mais informações, veja [como os administradores gerenciam aplicativos personalizados](custom-app-overview.md).

## <a name="related-article"></a>Artigo relacionado

* [Entenda o esquema de manifesto para atualizações feitas em aplicativos](/microsoftteams/platform/resources/schema/manifest-schema).
* [Saiba mais sobre o gerenciamento de aplicativos personalizado](custom-app-overview.md).
