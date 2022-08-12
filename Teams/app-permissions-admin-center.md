---
title: Exibir permissões do aplicativo e conceder consentimento de administrador no Centro de administração do Microsoft Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como exibir permissões solicitadas por aplicativos e conceder consentimento de administrador a aplicativos na página Gerenciar aplicativos do Centro de administração do Microsoft Teams.
ms.localizationpriority: medium
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f5bd84ce2fa19fc7a9aa823250fa77f1980055f0
ms.sourcegitcommit: 63dcc92b2d5d50e2c0c074a1209625e16086ca45
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2022
ms.locfileid: "67299050"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a>Exibir permissões do aplicativo e conceder consentimento de administrador no Centro de administração do Microsoft Teams

A página [Gerenciar aplicativos](manage-apps.md), no Centro de administração do Microsoft Teams, é onde você pode exibir e gerenciar todos os aplicativos do Teams da sua organização. Por exemplo, você pode ver o status no nível da organização e as propriedades dos aplicativos, aprovar ou carregar novos aplicativos personalizados no repositório de aplicativos da sua organização, bloquear ou permitir aplicativos no nível da organização e gerenciar configurações de aplicativos em toda a organização.

Você pode conceder consentimento de administrador em toda a organização a aplicativos que solicitam permissões para acessar dados e exibir permissões RSC (consentimento específico de recurso) para aplicativos.

## <a name="grant-org-wide-admin-consent-to-an-app"></a>Conceder consentimento de administrador em toda a organização a um aplicativo

Se você for um administrador global, poderá examinar e conceder consentimento a aplicativos que solicitam permissões em nome de todos os usuários em sua organização. Faça isso para que os usuários não precisem revisar e aceitar as permissões solicitadas pelo aplicativo quando iniciarem o aplicativo. Além disso, dependendo das [configurações de consentimento](/azure/active-directory/manage-apps/configure-user-consent) do usuário no Azure Active Directory (Azure AD), é possível que alguns usuários não tenham permissão para conceder consentimento aos aplicativos que acessam os dados da empresa.

Exemplos de permissões solicitadas por aplicativos incluem a capacidade de ler informações armazenadas em uma equipe, ler o perfil de um usuário e enviar um email em nome dos usuários. Para saber mais, consulte [Permissões e consentimento no ponto de extremidade da plataforma de identidade da Microsoft](/azure/active-directory/develop/v2-permissions-and-consent).

A coluna **Permissões** indica se um aplicativo tem permissões que precisam de consentimento. Você verá um link **Exibir detalhes** para cada aplicativo registrado no Azure AD que tem permissões que precisam de consentimento. Tenha em mente que isso se aplica somente a aplicativos personalizados e de terceiros. O link não está disponível para aplicativos fornecidos pela Microsoft. Além disso, os administradores não têm que conceder consentimento para esses aplicativos.

Para conceder consentimento em toda a organização a um aplicativo, siga estas etapas:

1. Na navegação à esquerda do Centro de Administração do Microsoft Teams, acesse **Aplicativos do Teams** > **[Gerenciar aplicativos](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Siga um destes procedimentos:
    * Pesquise o aplicativo desejado, clique no nome do aplicativo para ir para a página de detalhes do aplicativo e selecione a guia **Permissões**.
    * Classifique a coluna **Permissões** em ordem decrescente para localizar o aplicativo e selecione **Exibir detalhes**. Isso leva você para a guia **Permissões** da página de detalhes do aplicativo.

1. Em **Permissões em toda a organização**, selecione **Exibir permissões e consentimento**.

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text=" Captura de tela das permissões em toda a organização na guia Permissões de um aplicativo.":::

    Você deve ser um administrador global para fazer isso. Essa opção não está disponível para administradores de serviço do Teams.

1. Na guia **Permissões**, examine as permissões solicitadas pelo aplicativo.

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text=" Captura de tela das permissões solicitadas por um aplicativo.":::

    > [!IMPORTANT]
    > Conceder consentimento em toda a organização a um aplicativo permite que o aplicativo acesse os dados da sua organização. Examine cuidadosamente as permissões solicitadas pelo aplicativo antes de conceder consentimento.

1. Se você concordar com as permissões solicitadas pelo aplicativo, clique em **Aceitar** para conceder consentimento. Uma faixa é exibida temporariamente na parte superior da página para informar que as permissões solicitadas foram concedidas para o aplicativo. O aplicativo agora tem acesso aos recursos especificados para todos os usuários em sua organização e ninguém mais será solicitado a examinar as permissões.

Depois de aceitar as permissões, você verá uma mensagem em **Permissões em toda a organização** na página de detalhes do aplicativo para informar que o consentimento foi concedido. Para exibir detalhes sobre as permissões do aplicativo, clique no link **Azure Active Directory** para ir para a página do aplicativo no portal do Azure AD.

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted-new.png" alt-text="Captura de tela da mensagem exibida quando o consentimento é concedido.":::

Se os usuários em sua organização têm permissão para conceder consentimento e se um ou mais usuários concederam consentimento a um aplicativo específico, você também verá a mesma mensagem para informar que o consentimento foi concedido e o link do Azure Active Directory para a página do aplicativo no portal do Azure AD.

> [!NOTE]
> Embora a opção **Examinar permissões e consentimento** não esteja disponível para administradores de serviço do Teams e eles não possam conceder consentimento de administrador em toda a organização a aplicativos, os administradores de serviço do Teams podem exibir o conteúdo na guia **Permissões** de um aplicativo. Por exemplo, um administrador de serviço do Teams pode clicar no link do **Azure Active Directory** para exibir detalhes de permissões de aplicativo no portal do Azure AD.

## <a name="view-resource-specific-consent-permissions-of-an-app"></a>Exibir permissões de consentimento específicas do recurso de um aplicativo

As permissões de RSC permitem que os proprietários da equipe concedam consentimento para que um aplicativo acesse e modifique os dados de uma equipe. As permissões RSC são permissões granulares específicas do Teams que definem o que um aplicativo pode fazer em uma equipe específica. Exemplos de permissões RSC incluem a capacidade de criar e excluir canais, obter as configurações de uma equipe e criar e remover guias de canal.

As permissões RSC são definidas no manifesto do aplicativo e não no Azure AD. Você concede consentimento a permissões RSC ao adicionar o aplicativo a uma equipe. Para saber mais, confira [RSC (consentimento específico de recurso).](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)

Administradores globais e administradores de serviço do Teams podem exibir permissões RSC para um aplicativo na guia **Permissões** da página de detalhes do aplicativo.

Para exibir as permissões RSC para um aplicativo, siga estas etapas:

1. Na navegação à esquerda do Centro de Administração do Microsoft Teams, vá para **Aplicativos do Teams** > **Gerenciar aplicativos**.
1. Pesquise o aplicativo desejado, clique no nome do aplicativo para ir para a página de detalhes do aplicativo e selecione a guia **Permissões**.
1. Em **Permissões RSC (consentimento específico de recurso) do Microsoft Graph**, examine as permissões RSC solicitadas pelo aplicativo.

    :::image type="content" source="media/app-perm-admin-center-rsc-new.png" alt-text=" Captura de tela das permissões RSC de um aplicativo.":::

## <a name="known-issues"></a>Problemas conhecidos

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a>O link "Exibir detalhes" não é exibido na coluna Permissões para alguns aplicativos de terceiros que solicitam permissões

A capacidade de examinar permissões e conceder consentimento não está disponível para todos os aplicativos de terceiros. Normalmente, os aplicativos de terceiros são registrados no Azure Active Directory quando os aplicativos solicitam permissões. Em vez do link **Exibir detalhes**, você verá `--` na coluna **Permissões**.

## <a name="related-articles"></a>Artigos relacionados

* [Gerenciar seus aplicativos no Centro de Administração do Microsoft Teams](manage-apps.md)
* [Permissões e consentimento no ponto de extremidade da plataforma de identidade da Microsoft](/azure/active-directory/develop/v2-permissions-and-consent)
* [Consentimento específico de recursos no Teams](resource-specific-consent.md)
* [RSC (consentimento específico de recurso)](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
* [Navegar pelo ciclo de vida do aplicativo Teams](https://aka.ms/PR132) (sessão do Ignite 2020)
