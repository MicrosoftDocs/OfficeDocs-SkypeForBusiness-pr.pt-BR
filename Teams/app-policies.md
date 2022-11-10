---
title: Visão geral das políticas de aplicativo para gerenciar aplicativos no Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: conceptual
ms.service: msteams
ms.subservice: teams-apps
ms.date: 09/25/2022
search.appverid: ''
description: Saiba mais sobre políticas de permissão de aplicativo e políticas de instalação usadas para gerenciar aplicativos no Microsoft Teams.
audience: admin
ms.localizationpriority: high
appliesto:
- Microsoft Teams
ms.collection:
- M365-collaboration
ms.openlocfilehash: 8e059199d4963004e287b456c98bb80717f849b3
ms.sourcegitcommit: 22f66e314e631b3c9262c5c7dc5664472f42971e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2022
ms.locfileid: "68912430"
---
# <a name="know-about-policies-to-manage-access-and-installation-of-teams-apps"></a>Saiba mais sobre políticas para gerenciar o acesso e a instalação de aplicativos do Teams

O Microsoft Teams usa políticas de aplicativo para controlar o comportamento de acesso e instalação de aplicativos. As políticas de aplicativo ajudam os administradores do Teams a controlar o seguinte comportamento do aplicativo:

* Configure o acesso de aplicativos para cada usuário individual ou para um grupo de usuários. Ele ajuda o administrador a controlar os aplicativos permitidos para cada usuário final.

* Fixe esses aplicativos para usuários finais relevantes para as necessidades da sua organização. Além disso, os administradores podem instalar aplicativos para usuários finais sem intervenção do usuário. Ele ajuda os usuários finais a começar facilmente com os aplicativos relevantes.

* Controle quais desenvolvedores em sua organização podem enviar aplicativos personalizados para aprovação de administrador. Ele ajuda você a controlar o acesso à funcionalidade de carregamento de aplicativos personalizados.

## <a name="app-permission-policies"></a>Políticas de permissão do aplicativo

Com políticas de permissão de aplicativo, o administrador do Teams controla quais aplicativos estão disponíveis para cada usuário em sua organização. Você pode permitir alguns aplicativos para todos os usuários, permitir alguns aplicativos para um grupo específico de usuários ou permitir aplicativos específicos para usuários específicos. As políticas de permissão do aplicativo funcionam em conjunto com as configurações de toda a organização e permitem ou bloqueiam o status de cada aplicativo individual.

As políticas de permissão do aplicativo se aplicam a todos os [tipos de aplicativos disponíveis no Teams](deploy-apps-microsoft-teams-landing-page.md). Alguns cenários de exemplo em que você usa políticas de permissão de aplicativo são:

* Implantar gradualmente um aplicativo para alguns usuários inicialmente e para todos os usuários eventualmente.
* Permitir um aplicativo personalizado para recrutamento e gerenciamento de talentos somente para membros do departamento de RH e bloqueá-lo para todos os outros usuários da organização.

:::image type="content" source="media/app-permission-policy-trimmed.png" alt-text="Captura de tela da política de permissão do aplicativo." lightbox="media/app-permission-policy.png":::

Para saber mais, confira [como gerenciar políticas de permissão do aplicativo](teams-app-permission-policies.md).

## <a name="app-setup-policies"></a>Políticas de configuração do aplicativo

As políticas de configuração do aplicativo permitem configurar como e onde estão os aplicativos disponíveis para os usuários em seu cliente do Teams. Escolha os aplicativos que deseja fixar na barra de aplicativos nos clientes do Teams e defina a ordem em que os aplicativos são exibidos.

Fixar ou instalar aplicativos ajuda a promover a conscientização e a adoção dos aplicativos desejados em sua organização. As alterações se aplicam a clientes web, desktop e mobile teams.

Alguns cenários de exemplo em que você usa políticas de configuração de aplicativo são:

* Fixar um aplicativo personalizado de recrutamento e gerenciamento de talentos para membros da sua equipe de RH.
* Altere a ordem dos [aplicativos Core](deploy-apps-microsoft-teams-landing-page.md#core-apps) usando a fixação para os usuários da sua organização.

:::image type="content" source="media/app-setup-policy-trimmed.png" alt-text="Captura de tela da política de configuração do aplicativo no centro de administração do Teams." lightbox="media/app-setup-policy.png":::

Para saber mais, confira [como gerenciar políticas de configuração do aplicativo](teams-app-setup-policies.md).

### <a name="option-to-upload-custom-apps"></a>Opção para carregar aplicativos personalizados

A sua organização pode encomendar a criação de aplicativos personalizados para requisitos específicos da organização. Os desenvolvedores em sua organização podem criar, testar e implantar aplicativos personalizados para usuários internos do Teams da organização. Você usa a política de instalação do aplicativo para controlar quem na sua organização pode carregar aplicativos personalizados. Você usa configurações em toda a organização para permitir que os usuários finais usem aplicativos personalizados. Você usa políticas de permissão para permitir que apenas usuários finais específicos usem um aplicativo personalizado.

:::image type="content" source="media/custom-app-policy-trimmed.png" alt-text="Captura de tela que mostra como permitir aplicativos personalizados em sua organização no painel de configurações em toda a organização." lightbox="media/custom-app-policy.png":::

Para saber mais, confira [como gerenciar políticas e configurações para aplicativos personalizados](teams-custom-app-policies-and-settings.md).

## <a name="related-articles"></a>Artigos relacionados

* [Gerenciar o Teams com políticas](manage-teams-with-policies.md)
* [Gerenciar políticas de permissão de aplicativo](teams-app-permission-policies.md)
* [Gerenciar políticas de configuração de aplicativo](teams-app-setup-policies.md)
* [Gerenciar políticas e configurações para aplicativos personalizados](teams-custom-app-policies-and-settings.md)
