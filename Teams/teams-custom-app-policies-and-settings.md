---
title: Gerenciar configurações e políticas de aplicativo personalizadas
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.subservice: teams-apps
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba como gerenciar configurações e políticas de aplicativo personalizadas para controlar quem em sua organização pode carregar aplicativos personalizados no Microsoft Teams.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.allowsideloading
- ms.teamsadmincenter.appsetuppolicies.tooltip.allowsideloading
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- seo-marvel-mar2020
ms.openlocfilehash: d52fe50ba3fa02b3b39269fd06ce66ea0dfb5b32
ms.sourcegitcommit: ceba5fd8f098c8d0eafaffe5c5301c845a3ae7ab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2022
ms.locfileid: "67837161"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a>Gerencie políticas e configurações de aplicativo personalizado no Microsoft Teams

Como administrador, você pode usar configurações e políticas de aplicativo personalizadas para controlar quem em sua organização pode carregar aplicativos personalizados no Microsoft Teams. Os administradores decidem quais usuários podem carregar aplicativos personalizados, e administradores e proprietários de equipe podem determinar se equipes específicas em sua organização permitem que aplicativos personalizados sejam adicionados a eles.  Depois de editar a política de aplicativo personalizada, pode levar algumas horas para que as alterações entre em vigor. Você deve ser um administrador de serviços Administração global ou do Teams para gerenciar essas políticas.

Os desenvolvedores em sua organização podem adicionar um aplicativo personalizado ao Teams carregando um pacote do aplicativo (em um arquivo .zip) diretamente para uma equipe ou no contexto pessoal. Isso é diferente de como os aplicativos são adicionados por meio da loja de aplicativos do Teams. Adicionar um aplicativo personalizado carregando um pacote de aplicativos, também conhecido como sideload, permite que usuários específicos em sua organização testem um aplicativo antes que ele esteja pronto para ser amplamente distribuído.

## <a name="custom-app-policy-and-settings"></a>Configurações e política de aplicativo personalizada

Três componentes determinam se um usuário pode carregar um aplicativo personalizado para uma equipe, fornecendo controle granular sobre quem pode adicionar aplicativos personalizados a uma equipe e a quais aplicativos personalizados de equipes podem ser adicionados:

- [Política de aplicativo personalizado do usuário](#user-custom-app-policy)
- [Configuração de aplicativo personalizado da equipe](#team-custom-app-setting)
- [Configuração de aplicativo personalizado em toda a organização](#org-wide-custom-app-setting)

Essas configurações não afetam a capacidade de bloquear aplicativos de terceiros.  

### <a name="user-custom-app-policy"></a>Política de aplicativo personalizado do usuário

Como parte das políticas [de configuração](teams-app-setup-policies.md) de aplicativo, os administradores podem usar uma configuração de **política, Carregar** aplicativos personalizados, para controlar se um usuário pode carregar aplicativos personalizados no Teams.

Se essa configuração estiver desativada:

- O usuário não pode carregar um aplicativo personalizado para nenhuma equipe em sua organização ou no contexto pessoal.
- O usuário pode interagir com aplicativos personalizados, dependendo da configuração de aplicativo personalizado em toda a organização.

Se essa configuração estiver ativada:

- O usuário pode carregar aplicativos personalizados para equipes que permitem e para equipes para as quais são proprietários, dependendo da configuração de aplicativo personalizado em toda a organização.
- O usuário pode carregar aplicativos personalizados para o contexto pessoal.
- O usuário pode interagir com aplicativos personalizados, dependendo da configuração de aplicativo personalizado em toda a organização.

Você pode editar as configurações na política de configuração de aplicativo global para incluir os aplicativos desejados. Se você quiser personalizar o Teams para diferentes grupos de usuários em sua organização, crie e atribua uma ou mais políticas de configuração de aplicativo personalizadas.

#### <a name="set-a-user-custom-app-policy"></a>Definir uma política de aplicativo personalizada do usuário

1. Entre no centro de administração do Teams e acesse as políticas **de Instalação de aplicativos** > **[do](https://admin.teams.microsoft.com/policies/app-setup)** Teams.
1. Selecione **Adicionar**.
1. Ativar ou desativar o **carregamento de aplicativos personalizados**.
1. Escolha as outras configurações que você deseja para a política.
1. Selecione **Salvar**.

### <a name="team-custom-app-setting"></a>Configuração de aplicativo personalizado da equipe

Os administradores e os proprietários da equipe podem controlar se uma equipe permite que aplicativos personalizados sejam adicionados a ela. Essa configuração, **Permitir que** os membros carreguem aplicativos personalizados, juntamente com a política de aplicativo personalizada de um usuário, determina quem pode adicionar aplicativos personalizados a uma equipe específica.

Se essa configuração estiver desativada:

- Os proprietários da equipe podem adicionar aplicativos personalizados, se a política de aplicativo personalizada permitir.
- Os membros da equipe que não são proprietários da equipe não podem adicionar aplicativos personalizados à equipe.

Se essa configuração estiver ativada:

- Os proprietários da equipe podem adicionar aplicativos personalizados, se a política de aplicativo personalizada permitir.
- Os membros da equipe que não são proprietários de equipe podem adicionar aplicativos personalizados, se a política de aplicativo personalizada permitir.

#### <a name="configure-the-team-custom-app-setting"></a>Definir a configuração de aplicativo personalizado da equipe

1. No Teams, vá para uma equipe e selecione **Mais opções...** >  **Gerencie a equipe**.
2. Selecione **Configurações** e expanda **permissões de membro**.
3. Marque ou desmarque **a caixa de seleção Permitir que os membros carreguem aplicativos personalizados** .

    ![Captura de tela mostrando a configuração do aplicativo personalizado da equipe.](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a>Configuração de aplicativo personalizado em toda a organização

A **configuração** Permitir interação com aplicativos personalizados em toda a organização [](manage-apps.md) na página Gerenciar aplicativos se aplica a todos em sua organização e determina se eles podem carregar ou interagir com aplicativos personalizados. Essa configuração atua como uma opção de ativar/desativar mestre para as configurações de política de aplicativo personalizada do usuário e da equipe. Ele serve como um botão de ligar/desligar mestre durante eventos de segurança. Dessa forma, as configurações de política de aplicativo personalizada do usuário e da equipe não entrarão em vigor, a menos que a configuração de aplicativo personalizado em toda a organização esteja habilitada, mesmo que as configurações de política de aplicativo personalizada do usuário e da equipe estejam habilitadas.

#### <a name="configure-the-org-wide-custom-app-setting"></a>Definir a configuração de aplicativo personalizado em toda a organização

1. Entre no centro de administração do Teams e acesse os aplicativos **do Teams Gerenciar** > **[aplicativos](https://admin.teams.microsoft.com/policies/manage-apps)**.
1. Selecione **configurações de aplicativo em toda a organização**.
1. Em **Aplicativos personalizados**, ative ou **desative Permitir interação com aplicativos personalizados**.

    ![Captura de tela mostrando as configurações de aplicativo personalizado em toda a organização.](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a>Como as configurações e políticas de aplicativo personalizadas funcionam em conjunto

Esta tabela resume a política e as configurações personalizadas do aplicativo, como elas funcionam em conjunto e seu efeito combinado no controle de quem em sua organização pode carregar aplicativos personalizados no Teams.

Por exemplo, você deseja permitir que apenas os proprietários da equipe carreguem aplicativos personalizados para equipes específicas. Você definiria o seguinte:

- Ative **a configuração Permitir interação com aplicativos** personalizados no centro de administração do Microsoft Teams.
- Desative a **opção Permitir que os membros carreguem aplicativos personalizados** para cada equipe à qual você deseja restringir o acesso.
- Crie e atribua uma política de configuração de aplicativo personalizada no centro de administração  do Microsoft Teams com a configuração Carregar aplicativos personalizados ativada e atribua-a aos proprietários da equipe.

|Configuração de aplicativo personalizado em toda a organização |Configuração de aplicativo personalizado da equipe |Política de aplicativo personalizado do usuário |Efeito  |
|---------|---------|---------|---------|
| Desabilitado    | Desabilitado    | Desabilitado     |A interação com todos os aplicativos personalizados é bloqueada para sua organização. Aplicativos personalizados não podem ser carregados por ninguém, exceto por um serviço do Teams Administração ou um administrador global. Você pode usar o PowerShell para remover o aplicativo personalizado.   |
| Desabilitado     | Desabilitado     | Habilitado        |A interação com todos os aplicativos personalizados é bloqueada para sua organização. Aplicativos personalizados não podem ser carregados por ninguém, exceto por um serviço do Teams Administração ou um administrador global. Você pode usar o PowerShell para remover o aplicativo personalizado.         |
| Desabilitado    | Habilitado        | Desabilitado        |A interação com todos os aplicativos personalizados é bloqueada para sua organização. Aplicativos personalizados não podem ser carregados por ninguém, exceto por um serviço do Teams Administração ou um administrador global. Você pode usar Windows PowerShell para excluir aplicativos personalizados.         |
| Desabilitado    | Habilitado      | Habilitado       |A interação com todos os aplicativos personalizados é bloqueada para sua organização. Aplicativos personalizados não podem ser carregados por ninguém, exceto por um serviço do Teams Administração ou um administrador global. Você pode usar o PowerShell para remover o aplicativo personalizado.         |
| Habilitado    | Desabilitado       | Desabilitado         |  O usuário não pode carregar aplicativos personalizados.      |
| Habilitado     | Desabilitado       | Habilitado         | Se o usuário for um proprietário de equipe, ele poderá carregar aplicativos personalizados para a equipe. Se o usuário não for um proprietário de equipe, ele não poderá carregar aplicativos personalizados para a equipe. O usuário pode carregar aplicativos personalizados no contexto pessoal.     |
| Habilitado     | Habilitado     | Desabilitado         | O usuário não pode carregar aplicativos personalizados.       |
| Habilitado    | Habilitado        | Habilitado        | O usuário pode carregar aplicativos personalizados para a equipe, independentemente de o usuário ser um proprietário da equipe. O usuário pode carregar aplicativos personalizados no contexto pessoal.       |

## <a name="related-articles"></a>Artigos relacionados

- [Administração configurações para aplicativos no Teams](admin-settings.md).
- [Atribua políticas aos usuários no Teams](assign-policies-users-and-groups.md).
