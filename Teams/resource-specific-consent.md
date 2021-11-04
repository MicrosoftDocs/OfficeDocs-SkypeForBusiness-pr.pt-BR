---
title: Consentimento específico do recurso em Microsoft Teams
author: cichur
ms.author: v-mahoffman
ms.reviewer: nkramer
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba mais sobre as configurações que você precisa configurar para controlar se os proprietários de equipes em sua organização podem dar consentimento aos aplicativos.
ms.localizationpriority: medium
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f12acd7d99f8ab841f47ca84bc677f104cc0f164
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60740227"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a>Consentimento específico do recurso em Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

O consentimento específico do recurso em Microsoft Teams permite que os proprietários da equipe dêm consentimento aos aplicativos para acessar dados da equipe. Exemplos desse acesso incluem a capacidade de ler mensagens de canal, criar e excluir canais e criar e remover guias de canal.

Como administrador, você controla se os proprietários de equipe em sua organização podem dar consentimento por meio das configurações que você configura usando o módulo do PowerShell do Azure Active Directory (Azure AD) ou o portal do Azure e o centro de administração do Microsoft Teams.  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a>Definir se os proprietários de equipe podem dar consentimento a aplicativos

Aqui estão as configurações que você deve definir para controlar se os proprietários da equipe podem dar consentimento aos aplicativos. Revise todas as configurações a seguir.

### <a name="settings-in-azure-ad"></a>Configurações no Azure AD

As duas configurações a seguir determinam se os proprietários da equipe podem dar consentimento aos aplicativos.

> [!IMPORTANT]
> Alterar qualquer uma dessas configurações não afeta o acesso a dados para aplicativos que já tiveram o consentimento concedido. Por exemplo, se você definir essas configurações para impedir que os proprietários da equipe concedam consentimento, essas alterações não removem o acesso de dados que já foi concedido.

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a>A configuração "Os usuários podem consentir que os aplicativos acessem dados da empresa em seu nome"

Essa configuração controla se os usuários em sua organização podem consentir com aplicativos em seu nome. Para permitir que os proprietários da equipe deem consentimento, essa configuração deve ser definida como **Sim**. Para gerenciar essa configuração, faça o seguinte:

1. No portal do Azure, acesse Enterprise   >  **aplicativos Configurações do usuário.**
2. Em **Enterprise aplicativos**, definir **Usuários podem consentir** com aplicativos acessando dados da empresa em seu nome **como Não** ou **Sim**.

Você também pode gerenciar essa configuração usando o PowerShell. Para saber mais, consulte [Configure user content to applications](/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications).

#### <a name="the-enablegroupspecificconsent-setting"></a>A configuração "EnableGroupSpecificConsent"

Essa configuração controla se os usuários em sua organização podem consentir que os aplicativos acessem os dados da empresa para os grupos que eles têm. Essa configuração deve ser habilitada para que os proprietários da equipe deem consentimento. Para ver as etapas sobre como gerenciar essa configuração usando o PowerShell, consulte [Configure group owner consent to apps accessing group data](/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data).

### <a name="settings-in-the-microsoft-teams-admin-center"></a>Configurações no centro de Microsoft Teams de administração

Além das configurações no Azure AD, as configurações de aplicativos em toda a [](manage-apps.md#allow-and-block-apps) organização na página [](teams-app-permission-policies.md) Gerenciar [aplicativos,](manage-apps.md#manage-org-wide-app-settings) se um aplicativo está bloqueado ou permitido na página Gerenciar aplicativos e a política de permissão do aplicativo atribuída ao proprietário da equipe determina se um proprietário da equipe pode dar consentimento. [](manage-apps.md)

> [!IMPORTANT]
> Alterar qualquer uma dessas configurações não afeta o acesso a dados para aplicativos que já tiveram o consentimento concedido. Por exemplo, se você desabilitar aplicativos de terceiros em toda a organização ou se bloquear aplicativos específicos para impedir que os proprietários de equipe concedam consentimento, essas alterações não removem o acesso de dados que já foi concedido.  

#### <a name="the-allow-third-party-apps-setting-in-org-wide-app-settings"></a>A configuração "Permitir aplicativos de terceiros" em configurações de aplicativos em toda a organização

Essa configuração de aplicativo em toda a organização controla se os usuários em sua organização podem usar aplicativos de terceiros. Essa configuração deve estar ativada para permitir que os proprietários da equipe deem consentimento. Para gerenciar essa configuração, faça o seguinte:

1. Na navegação à esquerda do centro de administração Microsoft Teams, vá para Teams **aplicativos** Gerenciar aplicativos e clique em  >   **Configurações de aplicativos em** toda a organização.
2. Em **Aplicativos de terceiros**, desativar ou ativar Permitir **aplicativos de terceiros**.

    ![Captura de tela da configuração "Permitir aplicativos de terceiros Teams"](media/resource-specific-consent-org-wide-setting.png)

Talvez você precise aguardar até 24 horas para que as configurações entrem em vigor.

#### <a name="allow-or-block-the-app-at-the-org-level"></a>Permitir ou bloquear o aplicativo no nível da organização

Quando você bloqueia ou permite um aplicativo na página [Gerenciar aplicativos,](manage-apps.md#allow-and-block-apps) esse aplicativo é bloqueado ou permitido para todos os usuários em sua organização. Os proprietários da equipe só poderão dar consentimento a um aplicativo se o aplicativo for permitido. Para permitir ou bloquear um aplicativo no nível da organização, faça o seguinte:

1. Na navegação à esquerda do Centro de Administração do Microsoft Teams, vá para **Aplicativos do Teams** > **Gerenciar aplicativos**.
2. Na página Gerenciar aplicativos, selecione o aplicativo e clique em **Bloquear** para bloqueá-lo ou clique em **Permitir** para permitir.

    ![Captura de tela dos aplicativos bloqueados em configurações em toda a organização.](media/resource-specific-consent-allow-block-apps.png)

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a>Política de permissão de aplicativo atribuída ao proprietário da equipe

Os proprietários de equipe só podem dar consentimento a aplicativos que sua política de permissão de aplicativo permite que eles executem. Para exibir e gerenciar a política de permissão do aplicativo atribuída a um proprietário de equipe, faça o seguinte:

1. Na navegação à esquerda do centro de administração Microsoft Teams, vá para **Usuários**.
2. Clique duas vezes no nome de exibição do proprietário da equipe e clique em **Políticas**.
3. A política atribuída ao proprietário da equipe está listada em **Política de permissão do aplicativo.**
    - Para atribuir uma política diferente, clique em **Editar** e selecione a política que você deseja atribuir.
    - Para editar as configurações da política atribuída ao proprietário da equipe, clique no nome da política e faça as alterações que você deseja.  

## <a name="uploading-custom-apps"></a>Carregando aplicativos personalizados

Ao carregar um aplicativo personalizado (também conhecido sideload) que usa o consentimento específico do recurso, o aplicativo deve vir do locatário para o qual ele está sendo instalado. Em outras palavras, o registro do aplicativo do Azure AD deve ser desse locatário. Os administradores globais são isentos dessa restrição e podem carregar aplicativos personalizados de qualquer locatário, diretamente para uma equipe (sideload) ou para o catálogo de aplicativos de locatário.

## <a name="related-topics"></a>Tópicos relacionados

- [Permissões RSC disponíveis](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
- [Microsoft Graph](https://developer.microsoft.com/graph)
- [Gerenciar seus aplicativos no Microsoft Teams de administração](manage-apps.md)
- [Gerenciar políticas de permissões de aplicativo no Teams](teams-app-permission-policies.md)