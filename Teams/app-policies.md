---
title: Visão geral das políticas de aplicativo para gerenciar aplicativos no Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: conceptual
ms.service: msteams
ms.subservice: teams-apps
search.appverid: ''
description: Saiba mais sobre políticas de permissão de aplicativo, políticas de configuração de aplicativo e políticas de aplicativo personalizadas usadas para gerenciar aplicativos no Microsoft Teams.
audience: admin
ms.localizationpriority: high
appliesto:
- Microsoft Teams
ms.collection:
- M365-collaboration
ms.openlocfilehash: ad7e99d10ebf53c7a85394edda84061f6caf0d29
ms.sourcegitcommit: ceba5fd8f098c8d0eafaffe5c5301c845a3ae7ab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2022
ms.locfileid: "67837561"
---
# <a name="overview-of-app-policies-used-to-manage-access-to-apps"></a>Visão geral das políticas de aplicativo usadas para gerenciar o acesso a aplicativos

O Microsoft Teams usa políticas para controlar o comportamento de acesso e instalação. As políticas ajudam os administradores do Teams a controlar o seguinte comportamento de aplicativo:

* Configure o acesso de aplicativos para os usuários em um nível granular. Ele ajuda cada usuário final a usar apenas os aplicativos que um administrador permitiu para eles.

* Fixe os aplicativos relevantes para um usuário específico. Ele ajuda os usuários finais a começar facilmente e a acessar os aplicativos relevantes rapidamente, já que os aplicativos fixados são instalados automaticamente sem intervenção.

## <a name="app-permission-policies"></a>Políticas de permissão do aplicativo

Com as políticas de permissão de aplicativo, o administrador do Teams pode controlar quais aplicativos estão disponíveis para quais usuários específicos em sua organização. Você pode definir o mapeamento de acesso exato entre o aplicativo e o usuário ou qualquer combinação de ambos. Por exemplo, você pode permitir alguns aplicativos para todos os usuários, permitir alguns aplicativos para um grupo específico de usuários ou permitir um aplicativo específico para um usuário específico.

As políticas de permissão do aplicativo se aplicam a todos os tipos de aplicativos disponíveis no Teams. Por exemplo, você pode usar políticas de permissão de aplicativo para distribuir gradualmente um aplicativo de terceiros ou um aplicativo personalizado, permitindo-o para usuários específicos.

:::image type="content" source="media/app-permission-policy-trimmed.png" alt-text="Captura de tela da política de permissão do aplicativo." lightbox="media/app-permission-policy.png":::

Para saber mais, confira [como gerenciar configurações e políticas de aplicativo personalizadas](teams-app-permission-policies.md).

## <a name="app-setup-policies"></a>Políticas de configuração do aplicativo

As políticas de configuração de aplicativo permitem que você personalize a experiência do aplicativo para seus usuários. Escolha os aplicativos que deseja fixar na barra de aplicativos nos clientes do Teams e a ordem em que eles aparecem, na Web, na área de trabalho e em clientes móveis.

Aqui estão alguns exemplos de como você pode usar políticas de configuração de aplicativo:

* Instalar aplicativos para usuários finais em seu ambiente pessoal do Teams. Ele ajuda a impulsionar a conscientização e a adoção dos aplicativos desejados. Por exemplo, fixe um aplicativo personalizado de gerenciamento de talentos e recrutação para membros da sua equipe de RH.
* Fixe seletivamente os principais aplicativos, como Chat, Teams e Chamadas.

:::image type="content" source="media/app-setup-policy-trimmed.png" alt-text="Captura de tela da política de configuração do aplicativo no centro de administração do Teams." lightbox="media/app-setup-policy.png":::

Para saber mais, confira [como gerenciar políticas de configuração de aplicativo](teams-app-setup-policies.md).

## <a name="custom-app-policies"></a>Políticas de aplicativo personalizados

O Teams permite que os desenvolvedores em sua organização criem, testem e implantem aplicativos personalizados para os usuários internos da organização. Os desenvolvedores podem enviar seus aplicativos personalizados por meio do Teams para aprovação dos administradores do Teams. Você pode usar políticas de configuração de aplicativo para controlar quem em sua organização pode carregar aplicativos personalizados. Os administradores podem permitir que os usuários finais da organização usem aplicativos personalizados e desenvolvedores para carregar aplicativos personalizados, usando as configurações de aplicativo em toda a organização.

:::image type="content" source="media/custom-app-policy-trimmed.png" alt-text="Captura de tela que mostra como permitir aplicativos personalizados em sua organização no painel de configurações de toda a organização." lightbox="media/custom-app-policy.png":::

Para saber mais, veja [como gerenciar configurações e políticas de aplicativo personalizadas](teams-custom-app-policies-and-settings.md).

## <a name="related-articles"></a>Artigos relacionados

* [Gerenciar o Teams com políticas](manage-teams-with-policies.md)
