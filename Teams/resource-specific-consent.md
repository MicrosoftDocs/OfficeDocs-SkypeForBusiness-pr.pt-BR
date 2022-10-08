---
title: Consentimento específico do recurso no Microsoft Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
audience: admin
ms.service: msteams
ms.subservice: teams-apps
ms.date: 09/26/2022
search.appverid: MET150
description: Saiba mais sobre as configurações que você precisa definir para controlar se os proprietários de equipes em sua organização podem dar consentimento a aplicativos.
ms.localizationpriority: high
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: dd47f8e46147e3b4d30052ff4a1b9fcde6c128e1
ms.sourcegitcommit: 6e85f3f70f8488ab827ac352c0f324b6dfd4b856
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68377149"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a>Consentimento específico do recurso no Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

O consentimento específico do recurso no Microsoft Teams permite que os proprietários de equipe deem consentimento aos aplicativos para acessar os dados da equipe. Exemplos desse acesso incluem a capacidade de ler mensagens de canal, criar e excluir canais e criar e remover guias de canal.

Como administrador, você controla se os proprietários de equipe em sua organização podem dar consentimento por meio das configurações definidas usando o módulo do PowerShell do Azure Active Directory (Azure AD) ou o portal do Azure e o centro de administração do Microsoft Teams.  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a>Definir se os proprietários de equipe podem dar consentimento a aplicativos

Aqui estão as configurações que você deve definir para controlar se os proprietários de equipe podem dar consentimento a aplicativos. Examine todas as configurações a seguir.

### <a name="settings-in-azure-active-directory-portal"></a>Configurações no portal do Azure Active Directory

As duas configurações a seguir determinam se os proprietários de equipe podem dar consentimento a aplicativos.

> [!IMPORTANT]
> Alterar qualquer uma dessas configurações não afeta o acesso a dados para aplicativos que já receberam consentimento. Por exemplo, se você definir essas configurações para impedir que os proprietários de equipe deem consentimento, essas alterações não removerão o acesso a dados que já foram concedidos.

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a>Os usuários podem consentir com aplicativos que acessam dados da empresa em sua configuração de nome

Essa configuração controla se os usuários em sua organização podem dar consentimento a aplicativos em seu nome. Para permitir que os proprietários da equipe deem consentimento, essa configuração deve ser definida como **Sim**. Para gerenciar essa configuração, faça o seguinte:

1. No portal do Azure, acesse **Aplicativos empresariais** > **Configurações do usuário**.
2. Em **Aplicativos empresariais**, defina **Os usuários podem consentir que os aplicativos acessem os dados da empresa em seu nome** como **Não** ou **Sim**.

Você também pode gerenciar essa configuração usando o PowerShell. Para saber mais, confira [Configurar o conteúdo do usuário para aplicativos](/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications).

#### <a name="the-enablegroupspecificconsent-setting"></a>A configuração "EnableGroupSpecificConsent"

Essa configuração controla se os usuários em sua organização podem consentir que os aplicativos acessem os dados da empresa para os grupos que eles têm. Essa configuração deve ser habilitada para que os proprietários de equipe deem consentimento. Para obter etapas sobre como gerenciar essa configuração usando o PowerShell, confira [Configurar o consentimento do proprietário do grupo para aplicativos que acessam dados do grupo](/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data).

### <a name="settings-in-the-microsoft-teams-admin-center"></a>Configurações no centro de administração do Microsoft Teams

Além das configurações no Azure AD, as [configurações de aplicativo em toda a organização](manage-apps.md#manage-org-wide-app-settings) na página [Gerenciar aplicativos](manage-apps.md), se um aplicativo estiver bloqueado ou permitido na página [Gerenciar aplicativos](manage-apps.md#allow-and-block-apps) e a [política de permissão do aplicativo](teams-app-permission-policies.md) atribuída ao proprietário da equipe, determina se um proprietário da equipe pode dar consentimento.

> [!IMPORTANT]
> Alterar qualquer uma dessas configurações não afeta o acesso a dados para aplicativos que já receberam consentimento. Por exemplo, se você desabilitar aplicativos de terceiros em toda a organização ou se bloquear aplicativos específicos para impedir que os proprietários da equipe deem consentimento, essas alterações não removerão o acesso a dados que já foi concedido.  

#### <a name="the-allow-third-party-apps-option-in-org-wide-app-settings"></a>A opção Permitir aplicativos de terceiros nas configurações de aplicativo em toda a organização

Essa configuração de aplicativo em toda a organização controla se os usuários em sua organização podem usar aplicativos de terceiros. Essa configuração deve estar habilitada para permitir que os proprietários de equipe deem consentimento. Para gerenciar essa configuração, faça o seguinte:

1. Entre no centro de administração do Teams e acesse os aplicativos **do Teams Gerenciar** > **[aplicativos](https://admin.teams.microsoft.com/policies/manage-apps)**.
1. Selecione **configurações de aplicativo em** toda a organização e, em **Aplicativos** de terceiros, desative ou ative **Permitir aplicativos de terceiros**.

   :::image type="content" source="media/resource-specific-consent-org-wide-setting.png" alt-text="Captura de tela mostrando a opção Permitir aplicativos de terceiros na configuração do Teams.":::

Pode levar até 24 horas para que suas alterações entre em vigor.

#### <a name="allow-or-block-the-app-at-the-org-level"></a>Permitir ou bloquear o aplicativo no nível da organização

Quando você bloqueia ou permite um aplicativo na página [Gerenciar aplicativos](manage-apps.md#allow-and-block-apps), esse aplicativo é bloqueado ou permitido para todos os usuários em sua organização. Os proprietários de equipe só poderão dar consentimento a um aplicativo se o aplicativo for permitido. Para permitir ou bloquear um aplicativo no nível da organização, faça o seguinte:

1. Entre no centro de administração do Teams e acesse os aplicativos **do Teams Gerenciar** > **[aplicativos](https://admin.teams.microsoft.com/policies/manage-apps)**.
1. Na página Gerenciar aplicativos, selecione o aplicativo e, em seguida, selecione **Bloquear** para bloqueiá-lo **ou selecione Permitir** para permitir.

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a>Política de permissão de aplicativo atribuída ao proprietário da equipe

Os proprietários de equipe só podem dar consentimento a aplicativos que sua política de permissão de aplicativo permite que eles executem. Para exibir e gerenciar a política de permissão do aplicativo atribuída a um proprietário de equipe, faça o seguinte:

1. Na navegação à esquerda do centro de administração do Microsoft Teams, acesse **Usuários**.
1. Clique duas vezes no nome de exibição do proprietário da equipe e selecione **Políticas**.
1. A política atribuída ao proprietário de equipe é listada na **política de permissão do aplicativo**.

    * Para atribuir uma política diferente, selecione **Editar** e, em seguida, selecione a política que você deseja atribuir.
    * Para editar as configurações da política atribuída ao proprietário da equipe, selecione o nome da política e faça as alterações desejadas.  

## <a name="upload-custom-apps"></a>Carregar aplicativos personalizados

Ao carregar um aplicativo personalizado (também conhecido sideload) que usa o consentimento específico do recurso, o aplicativo deve vir do locatário para o qual ele está sendo instalado. Em outras palavras, o registro do aplicativo Azure AD deve ser desse locatário. Os administradores globais são isentos dessa restrição e podem carregar aplicativos personalizados de qualquer locatário, diretamente para uma equipe (sideload) ou para o catálogo de aplicativos do locatário.

## <a name="related-articles"></a>Artigos relacionados

* [Permissões RSC disponíveis](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
* [Microsoft Graph](https://developer.microsoft.com/graph)
* [Gerenciar seus aplicativos no Centro de Administração do Microsoft Teams](manage-apps.md)
* [Gerenciar políticas de permissões de aplicativo no Teams](teams-app-permission-policies.md)
