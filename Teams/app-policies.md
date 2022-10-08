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
description: Saiba mais sobre políticas de permissão de aplicativo e políticas de configuração usadas para gerenciar aplicativos no Microsoft Teams.
audience: admin
ms.localizationpriority: high
appliesto:
- Microsoft Teams
ms.collection:
- M365-collaboration
ms.openlocfilehash: 1c99cd9c0be3251a237b547cd8a2096d2d0e02af
ms.sourcegitcommit: d6e180791134426445a35fd485dcca18bde2006b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/07/2022
ms.locfileid: "68494644"
---
# <a name="app-policies-used-to-manage-access-to-and-installation-of-apps"></a>Políticas de aplicativo usadas para gerenciar o acesso e a instalação de aplicativos

O Microsoft Teams usa políticas de aplicativo para controlar o comportamento de acesso e instalação de aplicativos. As políticas de aplicativo ajudam os administradores do Teams a controlar o seguinte comportamento de aplicativo:

* Configure o acesso de aplicativos para cada usuário individual ou para um grupo de usuários. Ele ajuda o administrador a controlar os aplicativos permitidos para cada usuário final.

* Fixe esses aplicativos para usuários finais relevantes para as necessidades da sua organização. Além disso, os administradores podem instalar aplicativos para usuários finais sem intervenção do usuário. Ele ajuda os usuários finais a começar facilmente com os aplicativos relevantes.

* Controlar quais desenvolvedores em sua organização podem enviar aplicativos personalizados para aprovação do administrador. Ele ajuda você a controlar o acesso à funcionalidade de upload de aplicativos personalizados.

## <a name="app-permission-policies"></a>Políticas de permissão do aplicativo

Com as políticas de permissão de aplicativo, o administrador do Teams controla quais aplicativos estão disponíveis para cada usuário em sua organização. Você pode permitir alguns aplicativos para todos os usuários, permitir alguns aplicativos para um grupo específico de usuários ou permitir aplicativos específicos para usuários específicos. As políticas de permissão de aplicativo funcionam em conjunto com configurações de toda a organização e permitem ou bloqueiam o status de cada aplicativo individual.

As políticas de permissão do aplicativo se aplicam a todos [os tipos de aplicativos disponíveis no Teams](deploy-apps-microsoft-teams-landing-page.md). Alguns cenários de exemplo em que você usa políticas de permissão de aplicativo são:

* Distribuir gradualmente um aplicativo para alguns usuários inicialmente e para todos os usuários eventualmente.
* Permita um aplicativo personalizado de recrutação e gerenciamento de talentos para apenas membros do departamento de RH e bloqueie-o para todos os outros usuários da organização.

:::image type="content" source="media/app-permission-policy-trimmed.png" alt-text="Captura de tela da política de permissão do aplicativo." lightbox="media/app-permission-policy.png":::

Para saber mais, confira [como gerenciar políticas de permissão de aplicativo](teams-app-permission-policies.md).

## <a name="app-setup-policies"></a>Políticas de configuração do aplicativo

As políticas de configuração de aplicativo permitem que você configure como e onde estão os aplicativos disponíveis para os usuários no cliente do Teams. Escolha os aplicativos que deseja fixar na barra de aplicativos nos clientes do Teams e defina a ordem em que os aplicativos são exibidos.

Fixar ou instalar aplicativos ajuda a promover o reconhecimento e a adoção dos aplicativos desejados em sua organização. As alterações se aplicam a clientes Web, desktop e móveis do Teams.

Alguns cenários de exemplo em que você usa políticas de configuração de aplicativo são:

* Fixe um aplicativo personalizado de gerenciamento de talentos e recrutas para membros da sua equipe de RH.
* Altere a ordem dos aplicativos principais pré-fixados para os usuários da sua organização.

:::image type="content" source="media/app-setup-policy-trimmed.png" alt-text="Captura de tela da política de configuração do aplicativo no centro de administração do Teams." lightbox="media/app-setup-policy.png":::

Para saber mais, confira [como gerenciar políticas de configuração de aplicativo](teams-app-setup-policies.md).

### <a name="option-to-upload-custom-apps"></a>Opção para carregar aplicativos personalizados

A sua organização pode encomendar a criação de aplicativos personalizados para requisitos específicos da organização. Os desenvolvedores em sua organização podem criar, testar e implantar aplicativos personalizados para os usuários internos do Teams da organização. Você usa a política de configuração de aplicativo para controlar quem em sua organização pode carregar aplicativos personalizados. Você usa configurações de toda a organização para permitir que os usuários finais usem aplicativos personalizados. Você usa políticas de permissão para permitir que somente usuários finais específicos usem um aplicativo personalizado.

:::image type="content" source="media/custom-app-policy-trimmed.png" alt-text="Captura de tela que mostra como permitir aplicativos personalizados em sua organização no painel de configurações de toda a organização." lightbox="media/custom-app-policy.png":::

Para saber mais, confira [como gerenciar políticas e configurações para aplicativos personalizados](teams-custom-app-policies-and-settings.md).

## <a name="related-articles"></a>Artigos relacionados

* [Gerenciar o Teams com políticas](manage-teams-with-policies.md)
* [Gerenciar políticas de permissão de aplicativo](teams-app-permission-policies.md)
* [Gerenciar políticas de configuração de aplicativo](teams-app-setup-policies.md)
* [Gerenciar políticas e configurações para aplicativos personalizados](teams-custom-app-policies-and-settings.md)
