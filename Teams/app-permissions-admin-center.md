---
title: Exibir permissões do aplicativo e conceder consentimento de administrador no centro de administração do Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: vaibhava
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como exibir as permissões solicitadas pelos aplicativos e conceder consentimento de administrador aos aplicativos na página Gerenciar aplicativos do centro de administração do Microsoft Teams.
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 737052ba5794b221caa08fa8ccfabec0d597c3ad
ms.sourcegitcommit: 34f407a6a40317056005e3bf38ce58f792c04810
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814603"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a>Exibir permissões do aplicativo e conceder consentimento de administrador no centro de administração do Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

A página [gerenciar aplicativos](manage-apps.md) no centro de administração do Microsoft Teams é onde você vê e gerencia todos os aplicativos do teams para sua organização. Por exemplo, você pode ver o status e as propriedades de nível da organização de aplicativos, aprovar ou carregar novos aplicativos personalizados para a loja de aplicativos da sua organização, bloquear ou permitir aplicativos no nível da organização e gerenciar as configurações do aplicativo de toda a organização.

Aqui, você também pode conceder consentimento de administração em toda a organização para aplicativos que solicitam permissões para acessar dados e exibir permissões de consentimento específico de recurso (RSC) para aplicativos.

## <a name="grant-org-wide-admin-consent-to-an-app"></a>Conceder consentimento de administração de toda a organização a um aplicativo

Como administrador, você pode revisar e conceder consentimento para aplicativos que solicitam permissões em nome de todos os usuários em sua organização. Isso é feito para que os usuários não precisem revisar e aceitar as permissões solicitadas pelo aplicativo quando iniciarem o aplicativo. Além disso, dependendo das [configurações de consentimento](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent) do usuário no Azure Active Directory (Azure AD), alguns usuários podem não ter permissão para conceder consentimento a aplicativos que acessam dados da empresa.

Exemplos de permissões solicitadas por aplicativos incluem a capacidade de ler informações armazenadas em uma equipe, ler o perfil de um usuário e enviar um email em nome dos usuários. Para saber mais, confira [permissões e consentimento no ponto de extremidade da plataforma de identidade da Microsoft](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent). 

Você precisa ser um administrador global para conceder consentimento em toda a organização a um aplicativo. A coluna **permissões** indica se um aplicativo tem permissões que precisam de consentimento. Você verá um link **Exibir detalhes** para cada aplicativo registrado no Azure AD que tenha permissões que precisem de consentimento. Tenha em mente que isso se aplica somente a aplicativos personalizados e de terceiros e. Você não verá esse link nem precisará conceder consentimento de administrador para aplicativos publicados pela Microsoft.

:::image type="content" source="media/app-perm-admin-center-permissions-column.png" alt-text="Captura de tela da coluna permissões na página Gerenciar aplicativos":::

Para conceder consentimento em toda a organização a um aplicativo, siga estas etapas:

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá até **Team apps**  >  **gerenciar aplicativos**.
2. Siga um destes procedimentos:
    - Procure o aplicativo desejado, clique no nome do aplicativo para ir para a página de detalhes do aplicativo e selecione a guia **permissões** .
    - Classifique a coluna **permissões** em ordem decrescente para localizar o aplicativo e, em seguida, selecione **Exibir detalhes**. Fazer isso leva você à guia **permissões** da página de detalhes do aplicativo.

3. Em **permissões de toda a organização**, selecione **revisar permissões e consentimento**. Você deve ser um administrador global para fazer isso. Essa opção não está disponível para administradores do teams Service.

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="Captura de tela de permissões de toda a organização na guia permissões para um aplicativo":::

4. Na guia **permissões** , examine as permissões solicitadas pelo aplicativo.

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="Captura de tela das permissões solicitadas por um aplicativo":::

    > [!IMPORTANT]
    > Conceder consentimento de toda a organização a um aplicativo permite que o aplicativo acesse os dados da sua organização. Revise cuidadosamente as permissões solicitadas pelo aplicativo antes de conceder consentimento.
5. Se você concordar com as permissões solicitadas pelo aplicativo, clique em **aceitar** para conceder consentimento. Uma faixa é exibida temporariamente na parte superior da página para que você saiba que as permissões solicitadas foram concedidas para o aplicativo. Agora o aplicativo tem acesso aos recursos especificados para todos os usuários em sua organização e ninguém mais será solicitado a revisar as permissões.

Depois de aceitar as permissões, você verá uma mensagem em **permissões de toda a organização** na página de detalhes do aplicativo para informar que o consentimento foi concedido. Para exibir detalhes sobre as permissões do aplicativo, clique no link do **Azure Active Directory** para acessar a página do aplicativo no portal do Azure AD.

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted.png" alt-text="Captura de tela da mensagem exibida quando o consentimento é concedido":::

Se os usuários da sua organização puderem conceder consentimento e se um ou mais usuários concederem consentimento a um aplicativo específico, você só verá a mensagem para informar que o consentimento foi concedido e o link do Azure Active Directory. 

## <a name="view-resource-specific-consent-permissions-of-an-app"></a>Exibir permissões de consentimento específicas do recurso de um aplicativo

As permissões de RSC permitem que os proprietários da equipe concederem consentimento para que um aplicativo acesse e modifique os dados de uma equipe. Permissões de RSC são específicas, permissões específicas de equipes que definem o que um aplicativo pode fazer em uma equipe específica. Exemplos de permissões de RSC incluem a capacidade de criar e excluir canais, obter as configurações de uma equipe e criar e remover guias de canal. As permissões de RSC são definidas no manifesto do aplicativo e não no Azure AD.

Conceda consentimento a permissões de RSC quando adiciona o aplicativo a uma equipe. Para saber mais, consulte consentimento [específico do recurso (RSC)](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent) e [consentimento específico do recurso no Teams](resource-specific-consent.md).

Administradores globais e administrador de serviços do teams podem exibir permissões de RSC. Para exibir as permissões de RSC para um aplicativo, siga estas etapas:

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá até **Team apps**  >  **gerenciar aplicativos**.
2. Procure o aplicativo desejado, clique no nome do aplicativo para ir para a página de detalhes do aplicativo e selecione a guia **permissões** .
3. Em **permissões de consentimento específico de recurso do Microsoft Graph (RSC)**, examine as permissões de RSC solicitadas pelo aplicativo.

    :::image type="content" source="media/app-perm-admin-center-rsc.png" alt-text="Captura de tela das permissões de RSC para um aplicativo":::

## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar seus aplicativos no centro de administração do Microsoft Teams](manage-apps.md)
- [Permissões e consentimento no ponto de extremidade da plataforma de identidade da Microsoft](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)
- [Consentimento específico do recurso no Teams](resource-specific-consent.md)
- [Consentimento específico do recurso (RSC)](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)


