---
title: Consentimento específico do recurso no Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: nkramer
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba mais sobre as configurações que você precisa configurar para controlar se os proprietários de equipes em sua organização podem dar autorização aos aplicativos.
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d6267f4b42890716ca31fd1b44de435af50ad6ae
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815671"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a>Consentimento específico do recurso no Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

O consentimento específico do recurso no Microsoft Teams permite que os proprietários da equipe dêm autorização aos aplicativos para acessar os dados da equipe. Exemplos desse acesso incluem a capacidade de ler mensagens de canal, criar e excluir canais e criar e remover guias de canal.

Como administrador, você controla se os proprietários da equipe em sua organização podem dar o consentimento por meio das configurações que você configura usando o módulo powershell do Azure Active Directory (Azure AD) ou o portal do Azure e o centro de administração do Microsoft Teams.  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a>Definir se os proprietários da equipe podem dar autorização aos aplicativos

Aqui estão as configurações que você deve definir para controlar se os proprietários da equipe podem dar autorização aos aplicativos. Não deixe de revisar todas as configurações a seguir.

### <a name="settings-in-azure-ad"></a>Configurações no Azure AD

As duas configurações a seguir determinam se os proprietários da equipe podem dar autorização aos aplicativos.

> [!IMPORTANT]
> Alterar qualquer uma dessas configurações não afeta o acesso a dados para aplicativos que já foram concedidos consentimento. Por exemplo, se você configurar essas configurações para impedir que os proprietários da equipe deem autorização, essas alterações não removerão o acesso a dados que já foi concedido.

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a>A configuração "Os usuários podem autorizar os aplicativos que acessam dados da empresa em seu nome"

Essa configuração controla se os usuários em sua organização podem consentir com os aplicativos em nome deles. Para permitir que os proprietários da equipe deem autorização, essa configuração deve ser definida como **Sim.** Para gerenciar essa configuração, faça o seguinte:

1. No portal do Azure, vá para **configurações do usuário**  >  **de aplicativos corporativos.**
2. Em **aplicativos Corporativos,** deverão **autorizar** os usuários para que os aplicativos acessem os dados da empresa em seu nome como **Não** ou **Sim.**

Você também pode gerenciar essa configuração usando o PowerShell. Para saber mais, confira [Configurar o conteúdo do usuário para aplicativos.](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications)

#### <a name="the-enablegroupspecificconsent-setting"></a>A configuração "EnableGroupSpecificConsent"

Essa configuração controla se os usuários em sua organização podem consentir com os aplicativos que acessam os dados da empresa para os grupos que eles têm. Essa configuração deve ser habilitada para que os proprietários da equipe deem autorização. Para ver as etapas sobre como gerenciar essa configuração usando o PowerShell, consulte Configurar autorização do proprietário do grupo [para que os aplicativos acessem dados do grupo.](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data)

### <a name="settings-in-the-microsoft-teams-admin-center"></a>Configurações no Centro de administração do Microsoft Teams

Além das configurações no Azure AD, as configurações de aplicativos em toda a [](manage-apps.md#allow-and-block-apps) organização na página [](teams-app-permission-policies.md) Gerenciar [aplicativos,](manage-apps.md#manage-org-wide-app-settings) se um aplicativo está bloqueado ou permitido na página Gerenciar aplicativos e a política de permissão de aplicativo atribuída ao proprietário da equipe determina se um proprietário da equipe pode dar o consentimento. [](manage-apps.md)

> [!IMPORTANT]
> Alterar qualquer uma dessas configurações não afeta o acesso a dados para aplicativos que já foram concedidos consentimento. Por exemplo, se você desabilitar aplicativos de terceiros em toda a organização ou bloquear aplicativos específicos para impedir que os proprietários da equipe deem autorização, essas alterações não removerão o acesso a dados que já foi concedido.  

#### <a name="the-allow-third-party-apps-setting-in-org-wide-app-settings"></a>A configuração "Permitir aplicativos de terceiros" nas configurações de aplicativos de toda a organização

Essa configuração de aplicativo em toda a organização controla se os usuários em sua organização podem usar aplicativos de terceiros. Essa configuração deve estar ativada para permitir que os proprietários da equipe deem autorização. Para gerenciar essa configuração, faça o seguinte:

1. Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para Os aplicativos do **Teams** Gerenciar aplicativos e clique em Configurações de aplicativos de toda  >  a **organização.**
2. Em **aplicativos de terceiros,** desativar ou ativar **Permitir aplicativos de terceiros.**

    ![Captura de tela da configuração "Permitir aplicativos de terceiros no Teams"](media/resource-specific-consent-org-wide-setting.png)

Talvez você precise aguardar até 24 horas para que as configurações entrem em vigor.

#### <a name="allow-or-block-the-app-at-the-org-level"></a>Permitir ou bloquear o aplicativo no nível da organização

Quando você bloqueia ou permite [](manage-apps.md#allow-and-block-apps) um aplicativo na página Gerenciar aplicativos, esse aplicativo é bloqueado ou permitido para todos os usuários em sua organização. Os proprietários da equipe só poderão dar autorização a um aplicativo se o aplicativo for permitido. Para permitir ou bloquear um aplicativo no nível da organização, faça o seguinte:

1. Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para Os **aplicativos do Teams**  >  **Gerenciar aplicativos.**
2. Na página Gerenciar aplicativos, selecione o  aplicativo e clique em Bloquear para bloqueá-lo ou clique **em Permitir** para permitir.

    ![Captura de tela dos aplicativos bloqueados nas configurações de toda a organização](media/resource-specific-consent-allow-block-apps.png)

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a>Política de permissão de aplicativo atribuída ao proprietário da equipe

Os proprietários da equipe só podem dar autorização aos aplicativos que sua política de permissão de aplicativo permite que eles executem. Para exibir e gerenciar a política de permissão do aplicativo atribuída a um proprietário de equipe, faça o seguinte:

1. Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para **Usuários.**
2. Clique duas vezes no nome de exibição do proprietário da equipe e clique em **Políticas.**
3. A política atribuída ao proprietário da equipe está listada na **política de permissão do aplicativo.**
    - Para atribuir uma política diferente, clique em **Editar** e selecione a política que você deseja atribuir.
    - Para editar as configurações da política atribuída ao proprietário da equipe, clique no nome da política e faça as alterações que você deseja.  

## <a name="uploading-custom-apps"></a>Carregando aplicativos personalizados

Ao carregar um aplicativo personalizado (também conhecido sideload) que usa o consentimento específico do recurso, o aplicativo deve vir do locatário para o qual ele está sendo instalado. Em outras palavras, o registro do aplicativo Azure AD deve ser desse locatário. Os administradores globais estão isentos dessa restrição e podem carregar aplicativos personalizados de qualquer locatário, diretamente para uma equipe (sideloading) ou para o catálogo de aplicativos do locatário.

## <a name="related-topics"></a>Tópicos relacionados

- [Permissões RSC disponíveis](https://aka.ms/teams-rsc)
- [Microsoft Graph](https://developer.microsoft.com/graph)
- [Gerenciar seus aplicativos no Centro de administração do Microsoft Teams](manage-apps.md)
- [Gerenciar políticas de permissões de aplicativo no Teams](teams-app-permission-policies.md)
