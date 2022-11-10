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
ms.openlocfilehash: aac7024730c3f18e1c0f38a2e041dea840a6b869
ms.sourcegitcommit: 22f66e314e631b3c9262c5c7dc5664472f42971e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2022
ms.locfileid: "68912400"
---
# <a name="use-app-permission-policies-to-control-user-access-to-apps"></a>Usar políticas de permissão de aplicativo para controlar o acesso do usuário a aplicativos

Como administrador, você pode usar políticas de permissão de aplicativo para controlar os aplicativos que estão disponíveis para cada usuário em sua organização. As permissões definidas para permitir ou bloquear todos os aplicativos ou aplicativos específicos são aplicáveis a todos os [tipos de aplicativos no Teams](deploy-apps-microsoft-teams-landing-page.md). Você deve ser um administrador de serviço do Administração Global ou do Teams para gerenciar essas políticas.

Para permitir um aplicativo, você deve permitir isso em [configurações de aplicativo em toda a Organização](manage-apps.md#manage-org-wide-app-settings), [na configuração do aplicativo individual](manage-apps.md#allow-and-block-apps) e na política de permissão do aplicativo. Enquanto os outros dois métodos permitem apenas um aplicativo para uso em sua organização, as políticas de permissão permitem controlar quais usuários podem usar um aplicativo específico. Você controla o acesso por usuário e por aplicativo criando e aplicando a política a usuários específicos.

O centro de administração do Teams permite criar dois tipos de políticas de permissões:

* `Global (Org-wide default)` A política existe por padrão e se aplica a todos os usuários. Todas as alterações feitas nessa política afetam todos os usuários, pois essa política é aplicada a todos os usuários por padrão.
* Uma política criada por administrador se aplica apenas aos usuários aos quais ela é aplicada. Crie uma nova política para permitir aplicativos para usuários específicos ou grupo de usuários.

   :::image type="content" source="media/app-permission-policy-trimmed.png" alt-text="Captura de tela mostrando uma nova política de permissão de aplicativo sendo criada." lightbox="media/app-permission-policy.png":::

Se sua organização já estiver no Teams, as configurações de aplicativo configuradas em **configurações de todo o locatário** no Centro de administração do Microsoft 365 serão refletidas em configurações de aplicativo em toda a organização na página [Gerenciar aplicativos](https://admin.teams.microsoft.com/policies/manage-apps) no centro de administração do Teams. Se você for novo no Teams e apenas começar, por padrão, todos os aplicativos serão permitidos na configuração global de toda a organização. Isso inclui aplicativos publicados pela Microsoft, provedores de software de terceiros e sua organização.

> [!NOTE]
> Para saber mais sobre as configurações de aplicativos de terceiros no ambiente do Microsoft 365 Government Community Cloud High (GCCH) e do Departamento de Defesa (DoD), confira [Gerenciar configurações de aplicativo em toda a organização para o Microsoft 365 Government](manage-apps.md#manage-org-wide-app-settings-for-microsoft-365-government).

## <a name="create-an-app-permission-policy"></a>Criar uma política de permissão de aplicativo

Use uma ou mais políticas de permissão de aplicativo personalizadas, se você quiser controlar os aplicativos que estão disponíveis para diferentes grupos de usuários. Você pode criar e atribuir políticas personalizadas separadas com base no fato de os aplicativos serem publicados pela Microsoft, por terceiros ou pela sua organização. Depois de criar uma política personalizada, você não pode alterá-la se os aplicativos de terceiros estiverem desabilitados nas configurações de aplicativos de toda a organização.

1. Entre no centro de administração do Teams e acesse **[políticas de permissão](https://admin.teams.microsoft.com/policies/app-permission)** de **aplicativos** >  do Teams.
1. Selecione **Adicionar**.
1. Forneça um nome e uma descrição para a política.
1. Em **aplicativos da Microsoft**, **aplicativos de terceiros** e **aplicativos personalizados**, selecione uma das seguintes opções:

    * Permitir todos os aplicativos
    * Permita aplicativos específicos e bloqueie todos os outros
    * Bloquear aplicativos específicos e permita todos os outros
    * Bloquear todos os aplicativos

1. Se você selecionou **Permitir aplicativos específicos e bloquear todos os outros**, adicione os aplicativos que deseja permitir:

    1. Selecione **Permitir aplicativos**.
    1. Pesquise os aplicativos que você deseja permitir e selecione **Adicionar**. Os resultados da pesquisa são filtrados para o desenvolvedor de aplicativos (**aplicativos da Microsoft**, **aplicativos de terceiros** ou **aplicativos personalizados**).
    1. Depois de escolher um ou mais aplicativos, selecione **Permitir**.

1. Se você selecionou **Bloquear aplicativos específicos e permitir que todos os outros**, pesquise e escolha os aplicativos que deseja bloquear e selecione **Bloquear**.

1. Selecione **Salvar**.

## <a name="edit-an-app-permission-policy"></a>Editar uma política de permissão de aplicativo

Você pode usar o centro de administração do Teams para editar a política global ou quaisquer políticas personalizadas criadas.

1. Entre no centro de administração do Teams e acesse **[políticas de permissão](https://admin.teams.microsoft.com/policies/app-permission)** **de aplicativos** >  do Teams.
1. Escolha a política clicando à esquerda do nome da política e selecionando **Editar**.
1. Faça as alterações para permitir ou bloquear aplicativos específicos em cada uma das três categorias.
1. Selecione **Salvar**.

## <a name="assign-a-custom-policy-for-app-permissions-to-users"></a>Atribuir uma política personalizada para permissões de aplicativo aos usuários

As políticas de permissão do aplicativo só entrarão em vigor quando você aplica uma política a um usuário ou a um grupo de usuários. Confira as diferentes maneiras de [atribuir a política aos usuários](policy-assignment-overview.md#ways-to-assign-policies).

## <a name="considerations-when-using-app-permission-policies"></a>Considerações ao usar políticas de permissão de aplicativo

Veja a seguir algumas considerações ao usar políticas de permissões de aplicativo para conceder acesso ou não permitir o acesso aos aplicativos:

* As políticas de permissão do aplicativo só entrarão em vigor quando você aplica uma política a um usuário ou a um grupo de usuários.

* Depois de editar ou atribuir uma política, pode levar algumas horas para que as alterações entrem em vigor.

* Um usuário final não pode interagir com nenhuma funcionalidade de um aplicativo que o usuário não tem permissão para usar.

* Os usuários podem pesquisar aplicativos bloqueados e solicitar aprovação de administrador. Os administradores mantêm o controle completo para [aprovar ou ignorar solicitações de usuário](user-requests-approve-apps.md).

* As políticas de instalação do aplicativo funcionam em conjunto com as políticas de permissão do aplicativo. Selecione aplicativos para fixar na política de configuração de um conjunto de aplicativos permitidos. No entanto, se um usuário tiver uma política de permissão de aplicativo que bloqueia o uso de um aplicativo fixado, o usuário não poderá usar o aplicativo.

* As políticas de aplicativo se aplicam aos usuários que usam o Teams na Web, no celular ou na área de trabalho.

## <a name="related-articles"></a>Artigos relacionados

* [Configurações de administrador para aplicativos no Teams](admin-settings.md)
* [Atribua políticas a seus usuários no Teams](policy-assignment-overview.md)
* [Comparação de disponibilidade de recursos do Teams](/office365/servicedescriptions/teams-service-description#feature-availability)
