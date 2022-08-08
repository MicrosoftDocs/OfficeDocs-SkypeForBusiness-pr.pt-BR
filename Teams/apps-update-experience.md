---
title: Experiência de atualização de aplicativos no Microsoft Teams
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
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: Neste artigo, saiba como os aplicativos da Microsoft, aplicativos personalizados e aplicativos de terceiros no Microsoft Teams são atualizados.
ms.openlocfilehash: bcd06b9814b03d917014d8136f51a280e30007d1
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272056"
---
# <a name="update-apps-in-microsoft-teams"></a>Atualizar aplicativos no Microsoft Teams

Na maioria dos casos, depois que os desenvolvedores publicam uma atualização do aplicativo, a nova versão aparece automaticamente para os usuários. No entanto, existem algumas atualizações no [manifesto do Microsoft Teams](/microsoftteams/platform/resources/schema/manifest-schema) que exigem a aceitação do usuário para serem concluídas:

* Um bot foi adicionado ou removido.
* A propriedade "botId" de um bot existente foi alterada.
* A propriedade "isNotificationOnly" de um bot existente foi alterada.
* Os recursos SupportsCalling, SupportsVideo e SupportsFiles de um bot foram adicionados.
* Uma extensão de mensagens foi adicionada.
* Um novo conector foi adicionado.
* As permissões dentro da “Autorização” foram adicionadas ou alteradas.

:::image type="content" source="media/manage-your-custom-apps-update1.png" alt-text="Nova versão disponível." lightbox="media/manage-your-custom-apps-update1.png":::

:::image type="content" source="media/manage-your-custom-apps-update2.png" alt-text="Opção de atualização para um aplicativo." lightbox="media/manage-your-custom-apps-update2.png":::

> [!NOTE]
> O processo de atualização se aplica a todas as atualizações de aplicativos da Microsoft, aplicativos personalizados e aplicativos de terceiros.
