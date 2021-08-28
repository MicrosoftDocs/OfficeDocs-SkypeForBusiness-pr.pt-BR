---
title: Experiência de atualização de aplicativos Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
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
description: Saiba como atualizar aplicativos em Microsoft Teams.
ms.openlocfilehash: 156bafa45fe51884d6697bb4121143fad98fc7cd
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58593165"
---
# <a name="update-apps-in-microsoft-teams"></a>Atualizar aplicativos no Microsoft Teams

Na maioria dos casos, depois que os desenvolvedores de aplicativos publicam uma atualização de aplicativo, a nova versão aparece automaticamente para os usuários. No entanto, há algumas atualizações para o manifesto <a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams que</a> exigem que a aceitação do usuário seja concluída:

* Um bot foi adicionado ou removido
* A propriedade "botId" de um bot existente foi alterada
* A propriedade "isNotificationOnly" de um bot existente foi alterada
* A funcionalidade SupportsCalling, SupportsVideo e SupportsFiles de um bot foi adicionada
* Uma extensão de mensagens foi adicionada
* Um novo conector foi adicionado
* Propriedades dentro de "webApplicationInfo" alteradas

![nova versão disponível](media/manage-your-custom-apps-update1.png)

![opção de atualização para um aplicativo](media/manage-your-custom-apps-update2.png)

> [!NOTE] 
> O processo de atualização se aplica a todas as atualizações de aplicativos para aplicativos da Microsoft, aplicativos personalizados e aplicativos de terceiros. 

## <a name="related-topics"></a>Tópicos relacionados

[Gerenciar aplicativos](manage-apps.md)
