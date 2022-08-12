---
title: Experiência de atualização de aplicativos no Microsoft Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Neste artigo, saiba como os aplicativos da Microsoft, aplicativos personalizados e aplicativos de terceiros no Microsoft Teams são atualizados e como os administradores facilitam isso.
ms.openlocfilehash: ed91ad441b773833838796d9ea8c71038c842b88
ms.sourcegitcommit: 63dcc92b2d5d50e2c0c074a1209625e16086ca45
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2022
ms.locfileid: "67299040"
---
# <a name="update-apps-in-microsoft-teams"></a>Atualizar aplicativos no Microsoft Teams

Na maioria dos casos, depois que uma nova versão de um aplicativo estiver disponível no Repositório do Teams, o aplicativo é atualizado automaticamente para os usuários. No entanto, algumas alterações específicas na nova versão do aplicativo exigem a aceitação do usuário para que o aplicativo seja atualizado. A aceitação do usuário garante a conscientização sobre as alterações, como funcionalidade ou acesso. Se os desenvolvedores de aplicativos fizerem as seguintes alterações específicas nos aplicativos do Microsoft Teams, os usuários finais deverão aprovar a atualização do aplicativo:

* Um bot é adicionado.
* A propriedade `botId` ou a propriedade `isNotificationOnly` de um bot existente é alterada.
* A funcionalidade `SupportsCalling`, `SupportsVideo` e `SupportsFiles` do bot é adicionada.
* Uma extensão de mensagens é adicionada.
* As permissões dentro da Autorização são adicionadas ou alteradas.
* `Id` ou `ApplicationPermissionsHash` ou ambos são alterados dentro de `webApplicationInfo`.

<!--- image update
:::image type="content" source="media/manage-your-custom-apps-update1.png" alt-text="New version available." lightbox="media/manage-your-custom-apps-update1.png":::

:::image type="content" source="media/manage-your-custom-apps-update2.png" alt-text="Upgrade option for an app." lightbox="media/manage-your-custom-apps-update2.png":::
--->

## <a name="related-articles"></a>Artigos relacionados

* [Entenda o esquema de manifesto para atualizações feitas em aplicativos](/microsoftteams/platform/resources/schema/manifest-schema).
