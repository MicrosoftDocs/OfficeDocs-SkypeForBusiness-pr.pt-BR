---
title: Exibir permissões de aplicativo e conceder consentimento de administrador no centro de administração do Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: vaibhava
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como exibir permissões solicitadas por aplicativos e conceder o consentimento do administrador aos aplicativos na página Gerenciar aplicativos do Centro de administração do Microsoft Teams.
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6ec41760a7edd7de52d15995f39365b300cd797e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827531"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a>Exibir permissões de aplicativo e conceder consentimento de administrador no centro de administração do Microsoft Teams

A [página Gerenciar aplicativos](manage-apps.md) no centro de administração do Microsoft Teams é onde você visualiza e gerencia todos os aplicativos do Teams para sua organização. Por exemplo, você pode ver o status e as propriedades de aplicativos no nível da organização, aprovar ou carregar novos aplicativos personalizados na loja de aplicativos da sua organização, bloquear ou permitir aplicativos no nível da organização e gerenciar configurações de aplicativos em toda a organização.

Aqui, você também pode conceder o consentimento de administrador em toda a organização para aplicativos que solicitam permissões para acessar dados e exibir permissões de consentimento específico do recurso (RSC) para aplicativos.

## <a name="grant-org-wide-admin-consent-to-an-app"></a>Conceder consentimento de administrador em toda a organização a um aplicativo

Se você for um administrador global, poderá revisar e conceder consentimento a aplicativos que solicitam permissões em nome de todos os usuários em sua organização. Faça isso para que os usuários não tenham que revisar e aceitar as permissões solicitadas pelo aplicativo quando iniciarem o aplicativo. Além disso, dependendo das configurações de consentimento do usuário no Azure Active Directory (Azure AD), alguns usuários podem não ter permissão para conceder consentimento a [aplicativos](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent) que acessam dados da empresa.

Exemplos de permissões solicitadas por aplicativos incluem a capacidade de ler informações armazenadas em uma equipe, ler o perfil de um usuário e enviar um email em nome dos usuários. Para saber mais, consulte Permissões e consentimento no ponto de extremidade [da plataforma de identidade da Microsoft.](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent) 

A **coluna Permissões** indica se um aplicativo tem permissões que precisam de consentimento. Você verá um link **exibir detalhes** para cada aplicativo registrado no Azure AD que tenha permissões que precisam de consentimento. Lembre-se de que isso se aplica somente a aplicativos personalizados e de terceiros. Você não verá esse link ou precisará conceder o consentimento do administrador para aplicativos publicados pela Microsoft.

:::image type="content" source="media/app-perm-admin-center-permissions-column.png" alt-text="Captura de tela da coluna Permissões na página Gerenciar aplicativos":::

Para conceder consentimento de toda a organização a um aplicativo, siga estas etapas:

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **aplicativos do Teams**  >  **Gerenciar aplicativos.**
2. Siga um destes procedimentos:
    - Pesquise o aplicativo que você deseja, clique no nome do aplicativo para ir para a página de detalhes do aplicativo e selecione a **guia** Permissões.
    - Sort the **Permissions** column in descending order to find the app, and then select **View details**. Isso leva você para a guia **Permissões da** página de detalhes do aplicativo.

3. Em **Permissões em toda a organização,** selecione Permissões de revisão e **consentimento.**

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="Captura de tela de permissões em toda a organização na guia Permissões de um aplicativo":::

    Você deve ser um administrador global para fazer isso. Essa opção não está disponível para administradores de serviço do Teams.

4. Na guia **Permissões,** revise as permissões solicitadas pelo aplicativo.

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="Captura de tela das permissões solicitadas por um aplicativo":::

    > [!IMPORTANT]
    > Conceder o consentimento de toda a organização a um aplicativo permite que o aplicativo acesse os dados da sua organização. Revise cuidadosamente as permissões solicitadas pelo aplicativo antes de conceder o consentimento.
5. Se você concordar com as permissões solicitadas pelo aplicativo, clique em **Aceitar** para conceder consentimento. Uma faixa aparece temporariamente na parte superior da página para que você saiba que as permissões solicitadas foram concedidas para o aplicativo. O aplicativo agora tem acesso aos recursos especificados para todos os usuários em sua organização e ninguém mais será solicitado a revisar as permissões.

Depois de aceitar as permissões, você verá  uma mensagem em permissões em toda a organização na página de detalhes do aplicativo para que você saiba que o consentimento foi concedido. Para exibir detalhes sobre as permissões do aplicativo, clique no link do **Azure Active Directory** para ir para a página do aplicativo no portal do Azure AD.

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted.png" alt-text="Captura de tela da mensagem exibida quando o consentimento concedido":::

Se os usuários em sua organização têm permissão para conceder consentimento e se um ou mais usuários concederem consentimento a um aplicativo específico, você também verá a mesma mensagem para que você saiba que o consentimento foi concedido e o link do Azure Active Directory para a página do aplicativo no portal do Azure AD.

> [!NOTE]
> Embora a  opção Revisar permissões e consentimento não está disponível para administradores de serviço do Teams e eles não podem conceder  consentimento para administradores de toda a organização para aplicativos, os administradores de serviço do Teams podem exibir o conteúdo na guia Permissões de um aplicativo. Por exemplo, um administrador de serviço do Teams pode clicar no link **do Azure Active Directory** para exibir detalhes de permissões do aplicativo no portal do Azure AD. 

## <a name="view-resource-specific-consent-permissions-of-an-app"></a>Exibir permissões de consentimento específicas do recurso de um aplicativo

As permissões RSC permitem que os proprietários da equipe concedam consentimento para que um aplicativo acesse e modifique os dados de uma equipe. As permissões RSC são granulares, permissões específicas do Teams que definem o que um aplicativo pode fazer em uma equipe específica. Exemplos de permissões RSC incluem a capacidade de criar e excluir canais, obter as configurações de uma equipe e criar e remover guias de canal. 

As permissões RSC são definidas no manifesto do aplicativo e não no Azure AD. Você concede consentimento para permissões RSC ao adicionar o aplicativo a uma equipe. Para saber mais, consulte [Consentimento específico do recurso (RSC).](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)

Administradores globais e administradores de serviço do Teams podem exibir permissões RSC para um aplicativo na guia **Permissões** da página de detalhes do aplicativo. 

Para exibir permissões RSC para um aplicativo, siga estas etapas:

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **aplicativos do Teams**  >  **Gerenciar aplicativos.**
2. Pesquise o aplicativo que você deseja, clique no nome do aplicativo para ir para a página de detalhes do aplicativo e selecione a **guia** Permissões.
3. Sob **permissões de RSC (consentimento** específico de recurso) do Microsoft Graph, revise as permissões RSC solicitadas pelo aplicativo.

    :::image type="content" source="media/app-perm-admin-center-rsc.png" alt-text="Captura de tela de permissões RSC para um aplicativo":::

## <a name="known-issues"></a>Problemas conhecidos

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a>O link "Exibir detalhes" não é exibido na coluna Permissões para alguns aplicativos de terceiros que solicitam permissões

Atualmente, a capacidade de revisar permissões e conceder consentimento não está disponível para todos os aplicativos de terceiros registrados no Azure AD que solicitam permissões. Em vez do link **Exibir detalhes,** você verá **--** na coluna **Permissões.** Estamos trabalhando com ISVs para habilitar esse recurso para seus aplicativos.

## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar seus aplicativos no centro de administração do Microsoft Teams](manage-apps.md)
- [Permissões e consentimento no ponto de extremidade da plataforma de identidade da Microsoft](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)
- [Consentimento específico do recurso no Teams](resource-specific-consent.md)
- [Consentimento específico do recurso (RSC)](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
- [Navegando pelo ciclo de vida](https://aka.ms/PR132) do aplicativo Teams (sessão do Ignite 2020)


