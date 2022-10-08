---
title: Gerenciar políticas de permissão de aplicativos no Microsoft Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.date: 09/29/2022
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: Saiba mais sobre as políticas de permissão de aplicativo no Microsoft Teams e como controlar a disponibilidade de aplicativos para seus usuários finais.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.overview
- ms.teamsadmincenter.appsetuppolicies.addpinnedapp.permissions
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 24c4b85bb1c4b97597bad6a38e6a67c35dc1abb0
ms.sourcegitcommit: 6e85f3f70f8488ab827ac352c0f324b6dfd4b856
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68377039"
---
# <a name="manage-access-to-teams-apps-using-app-permission-policies"></a>Gerenciar o acesso a aplicativos do Teams usando políticas de permissão de aplicativo

Como administrador, você pode usar políticas de permissão de aplicativo para controlar os aplicativos que estão disponíveis para cada usuário em sua organização. As permissões definidas para permitir ou bloquear todos os aplicativos ou aplicativos específicos são aplicáveis a todos os [tipos de aplicativos no Teams](deploy-apps-microsoft-teams-landing-page.md). Você deve ser um administrador de serviços Administração global ou do Teams para gerenciar essas políticas.

Para permitir um aplicativo, você deve permitir isso nas configurações de aplicativo [em](manage-apps.md#manage-org-wide-app-settings) toda a organização, na configuração do aplicativo [individual](manage-apps.md#allow-and-block-apps) e na política de permissão do aplicativo. Embora os outros dois métodos apenas permitam que um aplicativo seja usado em sua organização, as políticas de permissão permitem controlar quais usuários podem usar um aplicativo específico. Você controla o acesso por usuário e por aplicativo criando e aplicando a política a usuários específicos.

O Centro de administração do Teams permite que você crie dois tipos de políticas de permissões:

* `Global (Org-wide default)` a política existe por padrão e se aplica a todos os usuários. Todas as alterações feitas nessa política afetam todos os usuários, pois essa política é aplicada a todos os usuários por padrão.
* Uma política criada pelo administrador aplica-se somente aos usuários aos quais ela é aplicada. Crie uma nova política para permitir aplicativos para usuários específicos ou grupo de usuários.

   :::image type="content" source="media/app-permission-policy-trimmed.png" alt-text="Captura de tela mostrando uma nova política de permissão de aplicativo sendo criada." lightbox="media/app-permission-policy.png":::

Se sua organização já estiver no Teams, as configurações de aplicativo que você definiu nas configurações de todo o locatário no Centro de administração do Microsoft 365 serão refletidas nas configurações de aplicativo em toda a [](https://admin.teams.microsoft.com/policies/manage-apps) organização na página Gerenciar aplicativos no Centro de administração do Teams. Se você for novo no Teams e estiver apenas começando, por padrão, todos os aplicativos serão permitidos na configuração global de toda a organização. Isso inclui aplicativos publicados pela Microsoft, provedores de software de terceiros e sua organização.

> [!NOTE]
> Para saber mais sobre as configurações de aplicativos de terceiros no ambiente GCCH (Microsoft 365 Government Community Cloud High) e DoD (Departamento de Defesa), consulte Gerenciar configurações de aplicativos em toda a organização para [o Microsoft 365 Government](manage-apps.md#manage-org-wide-app-settings-for-microsoft-365-government).

## <a name="create-an-app-permission-policy"></a>Criar uma política de permissão de aplicativo

Use uma ou mais políticas de permissão de aplicativo personalizadas, se você quiser controlar os aplicativos que estão disponíveis para diferentes grupos de usuários. Você pode criar e atribuir políticas personalizadas separadas com base no fato de os aplicativos serem publicados pela Microsoft, por terceiros ou pela sua organização. Depois de criar uma política personalizada, você não pode alterá-la se os aplicativos de terceiros estiverem desabilitados nas configurações de aplicativos de toda a organização.

1. Entre no centro de administração do Teams e acesse as políticas **de permissão de aplicativos** > **[do](https://admin.teams.microsoft.com/policies/app-permission)** Teams.
1. Selecione **Adicionar**.
1. Forneça um nome e uma descrição para a política.
1. Em **aplicativos da Microsoft**, **aplicativos de terceiros** e **aplicativos personalizados**, selecione uma das seguintes opções:

    * `Allow all apps`
    * `Allow specific apps and block all others`
    * `Block specific apps and allow all others`
    * `Block all apps`

1. Se você selecionou **Permitir aplicativos específicos e bloquear todos os outros**, adicione os aplicativos que deseja permitir:

    1. Selecione **Permitir aplicativos**.
    1. Pesquise os aplicativos que você deseja permitir e selecione **Adicionar**. Os resultados da pesquisa são filtrados para o desenvolvedor de aplicativos (**aplicativos da Microsoft**, **aplicativos de terceiros** ou **aplicativos personalizados**).
    1. Depois de escolher um ou mais aplicativos, selecione **Permitir**.

1. Se você **selecionou Bloquear** aplicativos específicos e permitir todos os outros, pesquise e escolha os aplicativos que deseja bloquear e selecione **Bloquear**.

1. Selecione **Salvar**.

## <a name="edit-an-app-permission-policy"></a>Editar uma política de permissão de aplicativo

Você pode usar o Centro de administração do Teams para editar a política global ou quaisquer políticas personalizadas que você criou.

1. Entre no centro de administração do Teams e acesse as políticas **de permissão de aplicativos** > **[do](https://admin.teams.microsoft.com/policies/app-permission)** Teams.
1. Escolha a política clicando à esquerda do nome da política e selecionando **Editar**.
1. Faça as alterações para permitir ou bloquear aplicativos específicos em cada uma das três categorias.
1. Selecione **Salvar**.

## <a name="assign-a-custom-app-permission-policy-to-users"></a>Atribuir uma política de permissão de aplicativo personalizada aos usuários

As políticas de permissão de aplicativo entram em vigor somente quando você aplica uma política a um usuário ou a um grupo de usuários. Veja as diferentes maneiras de [atribuir a política aos usuários](policy-assignment-overview.md#ways-to-assign-policies).

## <a name="considerations-when-using-app-permission-policies"></a>Considerações ao usar políticas de permissão de aplicativo

A seguir estão algumas considerações ao usar políticas de permissões de aplicativo para conceder acesso ou para não permitir o acesso a aplicativos:

* As políticas de permissão de aplicativo entram em vigor somente quando você aplica uma política a um usuário ou a um grupo de usuários.

* Depois de editar ou atribuir uma política, pode levar algumas horas para que as alterações entrem em vigor.

* Um usuário final não pode interagir com nenhuma funcionalidade de um aplicativo que o usuário não tem permissão para usar.

* Os usuários podem pesquisar aplicativos bloqueados e solicitar aprovação do administrador. Os administradores mantêm controle total para [aprovar ou ignorar solicitações de usuário](user-requests-approve-apps.md).

* As políticas de configuração de aplicativo funcionam em conjunto com as políticas de permissão do aplicativo. Selecione aplicativos para fixar na política de configuração de um conjunto de aplicativos permitidos. No entanto, se um usuário tiver uma política de permissão de aplicativo que bloqueie o uso de um aplicativo fixado, o usuário não poderá usar o aplicativo.

* As políticas de aplicativo se aplicam aos usuários que usam qualquer Teams na Web, móvel ou área de trabalho.

## <a name="related-articles"></a>Artigos relacionados

* [Configurações de administrador para aplicativos no Teams](admin-settings.md)
* [Atribua políticas a seus usuários no Teams](policy-assignment-overview.md)
* [Comparação de disponibilidade de recursos do Teams](/office365/servicedescriptions/teams-service-description#feature-availability)
