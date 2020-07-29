---
title: Consentimento específico do recurso no Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: nkramer
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba mais sobre as configurações que você precisa configurar para controlar se os proprietários de equipes em sua organização podem dar consentimento aos aplicativos.
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1ed13f1f85b0c7eccead3737c4549931f016284c
ms.sourcegitcommit: 682566e51a9e5f0fc65540535c7dcdcbd38e04c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/28/2020
ms.locfileid: "45429373"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a>Consentimento específico do recurso no Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

O consentimento específico do recurso no Microsoft Teams permite que os proprietários da equipe atribuam consentimento aos aplicativos para acessar dados da equipe. Exemplos desse tipo de acesso incluem a capacidade de ler mensagens de canal, criar e excluir canais e criar e remover guias de canal.

Como administrador, você controla se os proprietários da equipe em sua organização podem dar consentimento por meio das configurações definidas usando o módulo do PowerShell do Azure Active Directory (Azure AD) ou o portal do Azure e o centro de administração do Microsoft Teams.  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a>Definir se os proprietários da equipe podem dar consentimento aos aplicativos

Aqui estão as configurações que você deve definir para controlar se os proprietários da equipe podem dar consentimento aos aplicativos. Certifique-se de rever todas as configurações a seguir.

### <a name="settings-in-azure-ad"></a>Configurações no Azure AD

As duas configurações a seguir determinam se os proprietários da equipe podem dar consentimento aos aplicativos.

> [!IMPORTANT]
> Alterar qualquer uma dessas configurações não afeta o acesso a dados para aplicativos que já receberam consentimento. Por exemplo, se você definir essas configurações para impedir que os proprietários da equipe tenham consentimento, essas alterações não removerão o acesso aos dados que já foram concedidos.

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a>A configuração "os usuários podem concordar com os aplicativos que acessam dados da empresa em nome"

Esta configuração controla se os usuários em sua organização podem concordar com os aplicativos em seu nome. Para permitir que os proprietários da equipe forneçam consentimento, essa configuração deve ser definida como **Sim**. Para gerenciar essa configuração, siga este procedimento:

1. No portal do Azure, acesse configurações de usuário de **aplicativos corporativos**  >  **User settings**.
2. Em **aplicativos corporativos**, definir **usuários pode concordar com os aplicativos que acessam dados da empresa em nome** de **não** ou **Sim**.

Você também pode gerenciar essa configuração usando o PowerShell. Para saber mais, consulte [Configurar o conteúdo do usuário para aplicativos](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications).

#### <a name="the-enablegroupspecificconsent-setting"></a>A configuração "EnableGroupSpecificConsent"

Esta configuração controla se os usuários em sua organização podem concordar com os aplicativos que acessam dados da empresa para os grupos dos quais eles possuem. Essa configuração deve ser habilitada para os proprietários de equipe concederem consentimento. Para ver as etapas sobre como gerenciar essa configuração usando o PowerShell, consulte [Configurar consentimento de proprietário de grupo para aplicativos que acessam dados de grupo](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data).

### <a name="settings-in-the-microsoft-teams-admin-center"></a>Configurações no centro de administração do Microsoft Teams

Além das configurações nas configurações do Azure AD, do [aplicativo de toda a organização](manage-apps.md#manage-org-wide-app-settings) na página [gerenciar aplicativos](manage-apps.md) , se um aplicativo estiver bloqueado ou permitido na página [gerenciar aplicativos](manage-apps.md#allow-and-block-apps) , e a [política de permissão do aplicativo](teams-app-permission-policies.md) atribuída ao proprietário da equipe determinar se um proprietário da equipe pode conceder consentimento.

> [!IMPORTANT]
> Alterar qualquer uma dessas configurações não afeta o acesso a dados para aplicativos que já receberam consentimento. Por exemplo, se você desabilitar aplicativos de terceiros para toda a organização ou se bloquear aplicativos específicos para impedir que os proprietários da equipe tenham consentimento, essas alterações não removerão o acesso aos dados que já foi concedido.  

#### <a name="the-allow-third-party-apps-setting-in-org-wide-app-settings"></a>A configuração "permitir aplicativos de terceiros" nas configurações de aplicativo de toda a organização

Esta configuração de aplicativo da organização controla se os usuários em sua organização podem usar aplicativos de terceiros. Essa configuração deve ser ativada para permitir que os proprietários de equipe forneçam consentimento. Para gerenciar essa configuração, siga este procedimento:

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá até **Team apps**  >  **gerenciar aplicativos**e clique em **configurações de aplicativo de toda a organização**.
2. Em **aplicativos de terceiros**, desative ou ative **permitir aplicativos**de terceiros.

    ![Captura de tela da configuração "permitir aplicativos de terceiros na equipe"](media/resource-specific-consent-org-wide-setting.png)

Talvez você precise aguardar até 24 horas para que as configurações entrem em vigor.

#### <a name="allow-or-block-the-app-at-the-org-level"></a>Permitir ou bloquear o aplicativo no nível da organização

Quando você bloqueia ou permite um aplicativo na página [gerenciar aplicativos](manage-apps.md#allow-and-block-apps) , esse aplicativo é bloqueado ou permitido para todos os usuários em sua organização. Os proprietários da equipe só podem dar consentimento a um aplicativo se o aplicativo for permitido. Para permitir ou bloquear um aplicativo no nível da organização, faça o seguinte:

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá até **Team apps**  >  **gerenciar aplicativos**.
2. Na página Gerenciar aplicativos, selecione o aplicativo e, em seguida, clique em **Bloquear** para bloqueá-lo ou clique em **permitir** para permitir.

    ![Captura de tela dos aplicativos bloqueados nas configurações de toda a organização](media/resource-specific-consent-allow-block-apps.png)

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a>Política de permissão do aplicativo atribuída ao proprietário da equipe

Os proprietários da equipe só podem dar consentimento aos aplicativos que a política de permissão do aplicativo permite que eles sejam executados. Para exibir e gerenciar a política de permissão do aplicativo atribuída a um proprietário da equipe, faça o seguinte:

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **usuários**.
2. Clique duas vezes no nome de exibição do proprietário da equipe e, em seguida, clique em **políticas**.
3. A política atribuída ao proprietário da equipe está listada em **política de permissão do aplicativo**.
    - Para atribuir uma política diferente, clique em **Editar**e selecione a política que você deseja atribuir.
    - Para editar as configurações da política atribuída ao proprietário da equipe, clique no nome da política e faça as alterações desejadas.  

## <a name="uploading-custom-apps"></a>Carregando aplicativos personalizados

Ao carregar um aplicativo personalizado (também um Sideload conhecido) que usa o consentimento específico do recurso, o aplicativo deve vir do locatário em que ele está sendo instalado. Em outras palavras, o registro do aplicativo Azure AD deve ser desse locatário. Os administradores globais são isentos dessa restrição e podem carregar aplicativos personalizados de qualquer locatário, diretamente para uma equipe (Sideload) ou para o catálogo de aplicativos locatário.

## <a name="related-topics"></a>Tópicos relacionados

- [Permissões de RSC disponíveis](https://aka.ms/teams-rsc)
- [Microsoft Graph](https://developer.microsoft.com/graph)
- [Gerenciar seus aplicativos no centro de administração do Microsoft Teams](manage-apps.md)
- [Gerenciar políticas de permissões de aplicativo no Teams](teams-app-permission-policies.md)
