---
title: Gerenciar políticas e configurações de aplicativo personalizadas e sideload
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.subservice: teams-apps
ms.service: msteams
audience: Admin
ms.date: 09/26/2022
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba como gerenciar políticas e configurações para controlar quem em sua organização pode carregar aplicativos personalizados e carregar aplicativos personalizados.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.allowsideloading
- ms.teamsadmincenter.appsetuppolicies.tooltip.allowsideloading
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- seo-marvel-mar2020
ms.openlocfilehash: 7cf290c3f031becab73523fceb031cae4e0a55a8
ms.sourcegitcommit: 22f66e314e631b3c9262c5c7dc5664472f42971e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2022
ms.locfileid: "68912410"
---
# <a name="manage-custom-and-sideloaded-apps-in-teams-admin-center"></a>Gerenciar aplicativos personalizados e sideload no centro de administração do Teams

O Microsoft Teams permite que os desenvolvedores da sua organização criem, testem e implantem aplicativos personalizados para usuários internos da organização. Esses aplicativos são chamados de aplicativos personalizados ou aplicativos LOB (Linha de Negócios). A sua organização pode encomendar a criação de aplicativos personalizados para requisitos específicos da organização. Os administradores controlam a distribuição e as permissões para aplicativos personalizados usando várias configurações e políticas.

:::image type="content" source="media/custom-app-orgwide-setting-trimmed.png" alt-text="Captura de tela que mostra como permitir aplicativos personalizados em sua organização no painel de configurações em toda a organização." lightbox="media/custom-app-orgwide-setting.png":::

Depois de permitir o uso de um aplicativo personalizado, os usuários finais podem encontrá-lo selecionando **Built para sua organização** na navegação à esquerda do armazenamento do Teams.

:::image type="content" source="media/built-for-your-org1.png" alt-text="Captura de tela de aplicativos personalizados na loja do Teams no aplicativo de desktop do Teams." lightbox="media/built-for-your-org2.png":::

Como administrador do Teams, você usa políticas e configurações de aplicativo personalizadas para controlar quem em sua organização pode carregar aplicativos personalizados no Microsoft Teams. Os administradores decidem quais usuários podem carregar aplicativos personalizados e administradores e proprietários de equipe podem determinar se equipes específicas em sua organização permitem que aplicativos personalizados sejam adicionados a eles. Depois de editar a política de aplicativo personalizada, pode levar algumas horas para que as alterações entrem em vigor. Você deve ser um administrador de serviço do Administração Global ou do Teams para gerenciar essas políticas.

Os desenvolvedores em sua organização podem adicionar um aplicativo personalizado ao Teams carregando um pacote de aplicativo (em um arquivo .zip) diretamente para uma equipe ou no contexto pessoal. Isso é diferente de como os aplicativos são adicionados por meio da loja de aplicativos do Teams. Adicionar um aplicativo personalizado carregando um pacote de aplicativo, também conhecido como sideloading, permite que usuários específicos em sua organização testem um aplicativo antes que ele esteja pronto para ser amplamente distribuído.

<!--- During the creation of an app, the developers create and add an app ID to the manifest file. You can view this external app ID on the Manage apps page after you enable the column `External app ID` from the column settings. You can also view it on the app details page of a custom app. The ID is applicable for custom apps only. --->

## <a name="understand-sideloading-of-custom-apps"></a>Entender o sideload de aplicativos personalizados

Ao desenvolver aplicativos personalizados e antes de distribuir esses aplicativos para os usuários finais, os desenvolvedores testam os aplicativos adicionando-os à Teams Store para testar. Os desenvolvedores podem testar por conta própria ou com um grupo especificado de usuários, mas o aplicativo não está disponível para outros usuários finais na organização por meio da loja. Esse método é chamado de sideload de aplicativos e se aplica somente a aplicativos personalizados.

Os desenvolvedores podem fazer sideload de um aplicativo para disponibilizá-lo aos membros de uma equipe específica, normalmente para testar um aplicativo em desenvolvimento. Usar um aplicativo dessa maneira limita seu uso aos desenvolvedores de aplicativos e não requer aprovação do administrador, desde que o administrador permita o sideload no Teams.

Os desenvolvedores podem compartilhar um aplicativo sideload com uma equipe específica sem enviá-lo ao catálogo de aplicativos do Teams. Ele disponibiliza o aplicativo personalizado sideload para um grupo limitado de usuários finais, mas não disponível na loja de aplicativos da sua organização para todos os usuários finais.

Como administrador, você pode proibir o sideload do aplicativo para todos os desenvolvedores. Se você não permitir o sideload, os desenvolvedores ainda poderão testar seus aplicativos [criando um locatário de teste separado](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant). Após a conclusão do desenvolvimento de aplicativos personalizados, os desenvolvedores solicitam que os administradores distribuam seus aplicativos personalizados para os usuários finais. Para obter detalhes, confira [como publicar um aplicativo personalizado](/microsoftteams/upload-custom-apps). Como administrador, você permite (ou bloqueia) o uso de um aplicativo personalizado para todos os usuários ou para usuários específicos.

## <a name="custom-app-policy-and-settings"></a>Política e configurações de aplicativo personalizados

Três configurações determinam se um usuário pode carregar um aplicativo personalizado em uma equipe. Ele fornece aos administradores controle granular sobre quem pode adicionar aplicativos personalizados a uma equipe e a quais aplicativos personalizados do teams podem ser adicionados. Essas configurações não afetam a capacidade de bloquear aplicativos de terceiros.

* [Política de aplicativo personalizado do usuário](#user-custom-app-policy)
* [Configuração de aplicativo personalizado da equipe](#team-custom-app-setting)
* [Configuração de aplicativo personalizado em toda a organização](#org-wide-custom-app-setting)

### <a name="user-custom-app-policy"></a>Política de aplicativo personalizado do usuário

Como parte das [políticas de instalação do aplicativo](teams-app-setup-policies.md), os administradores podem usar a configuração **Carregar aplicativos personalizados** para controlar se um usuário pode carregar aplicativos personalizados no Teams.

Se essa configuração estiver desativada:

* O usuário não pode carregar um aplicativo personalizado para qualquer equipe em sua organização ou no contexto pessoal.
* O usuário pode interagir com aplicativos personalizados, dependendo da configuração do aplicativo personalizado em toda a organização.

Se essa configuração estiver ativada:

* O usuário pode carregar aplicativos personalizados para equipes que permitem e para equipes para as quais eles são proprietários, dependendo da configuração de aplicativo personalizado em toda a organização.
* O usuário pode carregar aplicativos personalizados no contexto pessoal.
* O usuário pode interagir com aplicativos personalizados, dependendo da configuração do aplicativo personalizado em toda a organização.

Você pode editar as configurações na política global de configuração do aplicativo para incluir os aplicativos desejados. Se você quiser personalizar o Teams para diferentes grupos de usuários em sua organização, crie e atribua uma ou mais políticas de configuração de aplicativo personalizadas.

#### <a name="set-a-user-custom-app-policy"></a>Definir uma política de aplicativo personalizado do usuário

1. Entre no centro de administração do Teams e acesse **[políticas de instalação](https://admin.teams.microsoft.com/policies/app-setup)** de **aplicativos** >  do Teams.
1. Selecione **Adicionar**.
1. Forneça um nome e uma descrição para a política.
1. Ative ou desative **Carregar configuração de aplicativos personalizados** .
1. Escolha as outras configurações que você deseja para a política.
1. Selecione **Salvar**.
1. [Aplique a política aos usuários](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users) que desenvolvem aplicativos personalizados e têm permissão para carregar esses aplicativos.

> [!NOTE]
> Para alterar essa configuração, permita aplicativos [personalizados nas configurações do aplicativo em toda a organização](manage-apps.md#manage-org-wide-app-settings).

### <a name="team-custom-app-setting"></a>Configuração de aplicativo personalizado da equipe

Administradores e proprietários de equipe podem controlar se uma equipe permite que aplicativos personalizados sejam adicionados a ele. Essa configuração permite **que os membros carreguem aplicativos personalizados**, juntamente com a política de aplicativo personalizado de um usuário, determina quem pode adicionar aplicativos personalizados a uma equipe específica.

Se essa configuração estiver desativada:

* Os proprietários da equipe poderão adicionar aplicativos personalizados, se a política de aplicativo personalizada permitir.
* Os membros da equipe que não são proprietários de equipe não podem adicionar aplicativos personalizados à equipe.

Se essa configuração estiver ativada:

* Os proprietários da equipe poderão adicionar aplicativos personalizados, se a política de aplicativo personalizada permitir.
* Os membros da equipe que não são proprietários de equipe podem adicionar aplicativos personalizados, se sua política de aplicativo personalizada permitir isso.

#### <a name="configure-the-team-custom-app-setting"></a>Configurar a configuração do aplicativo personalizado da equipe

1. No Teams, vá para uma equipe e selecione **Mais opções ...** >  **Gerenciar equipe**.
1. Selecione **Configurações** e expanda **permissões de membro**.
1. Selecione ou desmarque a caixa de seleção **Permitir que os membros carreguem aplicativos personalizados** .

   :::image type="content" source="media/teams-custom-app-policy-and-settings-team-trim.png" alt-text="Captura de tela mostrando a configuração do aplicativo personalizado da equipe." lightbox="media/teams-custom-app-policy-and-settings-team.png":::

### <a name="org-wide-custom-app-setting"></a>Configuração de aplicativo personalizado em toda a organização

A **configuração Permitir interação com aplicativos personalizados** em toda a organização na página [Gerenciar aplicativos](manage-apps.md) se aplica a todos na sua organização e rege se eles podem carregar ou interagir com aplicativos personalizados. Essa configuração atua como um botão mestre de ativação/desativação para as configurações de política de aplicativo personalizadas do usuário e da equipe. Ele destina-se a servir como um botão de ativação/desativação mestre durante eventos de segurança. Como tal, as configurações de política de aplicativo personalizado do usuário e da equipe não entrarão em vigor, a menos que a configuração de aplicativo personalizado em toda a organização esteja habilitada mesmo se as configurações de política de aplicativo personalizado do usuário e da equipe estiverem habilitadas.

#### <a name="configure-the-org-wide-custom-app-setting"></a>Configurar a configuração de aplicativo personalizado em toda a organização

1. Entre no centro de administração do Teams e acesse aplicativos  > **do Teams****[Gerenciar aplicativos](https://admin.teams.microsoft.com/policies/manage-apps)**.
1. Selecione **Configurações de aplicativo em toda a organização**.
1. Em **Aplicativos personalizados**, ative ou desative **Permitir interação com aplicativos personalizados**.

    :::image type="content" source="media/teams-custom-app-policy-and-settings-org-wide.png" alt-text="Captura de tela mostrando as configurações do aplicativo personalizado em toda a organização.":::

## <a name="how-custom-app-policies-and-settings-work-together"></a>Como as políticas e configurações de aplicativo personalizados funcionam juntas

Esta tabela resume a política e as configurações de aplicativo personalizadas, como elas funcionam juntas e seu efeito combinado no controle de quem em sua organização pode carregar aplicativos personalizados no Teams.

Por exemplo, você deseja permitir que apenas proprietários de equipe carreguem aplicativos personalizados em equipes específicas. Você definiria o seguinte:

* Ative a **configuração Permitir interação com aplicativos personalizados** no centro de administração do Microsoft Teams.
* Desative o **Permitir que os membros carreguem aplicativos personalizados** para cada equipe para a qual você deseja restringir o acesso.
* Crie e atribua uma política personalizada na política de instalação do aplicativo no centro de administração do Microsoft Teams com a configuração **Carregar aplicativos personalizados** ativada e atribua-a aos proprietários da equipe.

|Configuração de aplicativo personalizado em toda a organização |Configuração de aplicativo personalizado da equipe |Política de aplicativo personalizado do usuário |Efeito  |
|---------|---------|---------|---------|
| Desabilitado    | Desabilitado    | Desabilitado     |A interação com todos os aplicativos personalizados está bloqueada para sua organização. Aplicativos personalizados não podem ser carregados por ninguém, exceto um Administração do Serviço do Teams ou um administrador global. Você pode usar o PowerShell para remover o aplicativo personalizado.   |
| Desabilitado     | Desabilitado     | Habilitado        |A interação com todos os aplicativos personalizados está bloqueada para sua organização. Aplicativos personalizados não podem ser carregados por ninguém, exceto um Administração do Serviço do Teams ou um administrador global. Você pode usar o PowerShell para remover o aplicativo personalizado.         |
| Desabilitado    | Habilitado        | Desabilitado        |A interação com todos os aplicativos personalizados está bloqueada para sua organização. Aplicativos personalizados não podem ser carregados por ninguém, exceto um Administração do Serviço do Teams ou um administrador global. Você pode usar Windows PowerShell para excluir aplicativos personalizados.         |
| Desabilitado    | Habilitado      | Habilitado       |A interação com todos os aplicativos personalizados está bloqueada para sua organização. Aplicativos personalizados não podem ser carregados por ninguém, exceto um Administração do Serviço do Teams ou um administrador global. Você pode usar o PowerShell para remover o aplicativo personalizado.         |
| Habilitado    | Desabilitado       | Desabilitado         |  O usuário não pode carregar aplicativos personalizados.      |
| Habilitado     | Desabilitado       | Habilitado         | Se o usuário for um proprietário da equipe, ele poderá carregar aplicativos personalizados para a equipe. Se o usuário não for um proprietário da equipe, ele não poderá carregar aplicativos personalizados para a equipe. O usuário pode carregar aplicativos personalizados no contexto pessoal.     |
| Habilitado     | Habilitado     | Desabilitado         | O usuário não pode carregar aplicativos personalizados.       |
| Habilitado    | Habilitado        | Habilitado        | O usuário pode carregar aplicativos personalizados para a equipe, independentemente de o usuário ser um proprietário da equipe. O usuário pode carregar aplicativos personalizados no contexto pessoal.       |

## <a name="related-articles"></a>Artigos relacionados

* [Administração configurações para aplicativos no Teams](admin-settings.md).
* [Atribua políticas aos usuários no Teams](assign-policies-users-and-groups.md).
