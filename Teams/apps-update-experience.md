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
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Neste artigo, saiba como os aplicativos da Microsoft, aplicativos personalizados e aplicativos de terceiros no Microsoft Teams são atualizados.
ms.openlocfilehash: 27d51a487af918e6fcee2b7806c81d31506bd1af
ms.sourcegitcommit: 70185cd963c5a9d539e65e302d4230018209ecae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2022
ms.locfileid: "66958036"
---
# <a name="update-apps-in-microsoft-teams"></a>Atualizar aplicativos no Microsoft Teams

Na maioria dos casos, depois que os desenvolvedores de aplicativos publicam uma atualização de aplicativo, a nova versão aparece automaticamente para os usuários. No entanto, há algumas atualizações no manifesto do [Microsoft Teams que](/microsoftteams/platform/resources/schema/manifest-schema) exigem que a aceitação do usuário seja concluída:

* Um bot foi adicionado ou removido.
* A propriedade "botId" de um bot existente foi alterada.
* A propriedade "isNotificationOnly" de um bot existente foi alterada.
* A funcionalidade SupportsCalling, SupportsVideo e SupportsFiles de um bot foi adicionada.
* Uma extensão de mensagens foi adicionada.
* Um novo conector foi adicionado.
* As permissões dentro de "Autorização" foram adicionadas ou alteradas.

:::image type="content" source="media/manage-your-custom-apps-update1.png" alt-text="Nova versão disponível." lightbox="media/manage-your-custom-apps-update1.png":::

:::image type="content" source="media/manage-your-custom-apps-update2.png" alt-text="Opção de atualização para um aplicativo." lightbox="media/manage-your-custom-apps-update2.png":::

> [!NOTE]
> O processo de atualização se aplica a todas as atualizações de aplicativos para aplicativos da Microsoft, aplicativos personalizados e aplicativos de terceiros.
