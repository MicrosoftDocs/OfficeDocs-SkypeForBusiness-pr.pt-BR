---
title: Gerenciar configurações e políticas de aplicativo personalizadas
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.reviewer: akino
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba como gerenciar configurações e políticas de aplicativo personalizadas para controlar quem em sua organização pode carregar aplicativos personalizados Microsoft Teams.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.allowsideloading
- ms.teamsadmincenter.appsetuppolicies.tooltip.allowsideloading
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- seo-marvel-mar2020
ms.openlocfilehash: 120f19472a0438c6bb76e98e0c8ef473c012c7b7
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681382"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a>Gerencie políticas e configurações de aplicativo personalizado no Microsoft Teams

> [!NOTE]
> Para usar o App Studio, consulte Introdução na plataforma [Microsoft Teams com C#/.NET e App Studio](/microsoftteams/platform/get-started/get-started-dotnet-app-studio) A última etapa ainda não está funcionando, portanto, você precisará baixar o [Upload](/microsoftteams/platform/concepts/apps/apps-upload) zip e instalá-lo da maneira antiga em um pacote de aplicativo para Microsoft Teams.

Como administrador, você pode usar configurações e políticas de aplicativo personalizadas para controlar quem em sua organização pode carregar aplicativos personalizados para Microsoft Teams. Os administradores decidem quais usuários podem carregar aplicativos personalizados, e administradores e proprietários de equipe podem determinar se equipes específicas em sua organização permitem que aplicativos personalizados sejam adicionados a eles.  Depois de editar a política de aplicativo personalizada, pode levar algumas horas para que as alterações entre em vigor. Você deve ser um administrador global ou administrador de serviços do Teams para gerenciar essas políticas.

## <a name="overview-of-custom-apps"></a>Visão geral de aplicativos personalizados

Os usuários podem adicionar um aplicativo personalizado Teams carregando um pacote do aplicativo (em um arquivo .zip) diretamente para uma equipe ou no contexto pessoal. Isso é diferente de como os aplicativos são adicionados por meio da Teams de aplicativos. Adicionar um aplicativo personalizado carregando um pacote de aplicativos, também conhecido como sideload, permite testar um aplicativo conforme ele está sendo desenvolvido, antes que ele esteja pronto para ser amplamente distribuído. Ele também permite que você crie um aplicativo somente para uso interno e compartilhe-o com sua equipe sem enviá-lo ao catálogo de aplicativos do Teams na Teams de aplicativos.

![Captura de tela mostrando a opção carregar um aplicativo personalizado na loja de aplicativos.](media/teams-custom-app-policy-and-settings-upload-app.png)

## <a name="custom-app-policy-and-settings"></a>Configurações e política de aplicativo personalizada

Três componentes determinam se um usuário pode carregar um aplicativo personalizado para uma equipe, fornecendo controle granular sobre quem pode adicionar aplicativos personalizados a uma equipe e a quais aplicativos personalizados de equipes podem ser adicionados:

- [Política de aplicativo personalizado do usuário](#user-custom-app-policy)
- [Configuração de aplicativo personalizado da equipe](#team-custom-app-setting)
- [Configuração de aplicativo personalizado em toda a organização](#org-wide-custom-app-setting)

Essas configurações não afetam a capacidade de bloquear aplicativos de terceiros.  

### <a name="user-custom-app-policy"></a>Política de aplicativo personalizado do usuário

Como parte das políticas [de configuração](teams-app-setup-policies.md) de aplicativo, os administradores podem usar uma configuração de **política, Upload** aplicativos personalizados, para controlar se um usuário pode carregar aplicativos personalizados para Teams.

Se essa configuração estiver desativada:

- O usuário não pode carregar um aplicativo personalizado para nenhuma equipe em sua organização ou no contexto pessoal.
- O usuário pode interagir com aplicativos personalizados, dependendo da configuração de aplicativo personalizado em toda a organização.

Se essa configuração estiver ativada:

- O usuário pode carregar aplicativos personalizados para equipes que permitem e para equipes para as quais são proprietários, dependendo da configuração de aplicativo personalizado em toda a organização.
- O usuário pode carregar aplicativos personalizados para o contexto pessoal.
- O usuário pode interagir com aplicativos personalizados, dependendo da configuração de aplicativo personalizado em toda a organização.

Você pode editar as configurações na política de configuração de aplicativo global para incluir os aplicativos desejados. Se você quiser personalizar o Teams grupos diferentes de usuários em sua organização, crie e atribua uma ou mais políticas personalizadas de configuração de aplicativo.

#### <a name="set-a-user-custom-app-policy"></a>Definir uma política de aplicativo personalizada do usuário

1. Na navegação esquerda do centro de administração do Microsoft Teams, acesse **Políticas de configuração** >  de **aplicativos do Teams**.
2. Clique em **Adicionar**.
3. Ative ou **desative Upload aplicativos personalizados**.
4. Escolha as outras configurações que você deseja para a política.
5. Clique em **Salvar**.

### <a name="team-custom-app-setting"></a>Configuração de aplicativo personalizado da equipe

Os administradores e os proprietários da equipe podem controlar se uma equipe permite que aplicativos personalizados sejam adicionados a ela. Essa configuração, **Permitir que** os membros carreguem aplicativos personalizados, juntamente com a política de aplicativo personalizada de um usuário, determina quem pode adicionar aplicativos personalizados a uma equipe específica.

Se essa configuração estiver desativada:

- Os proprietários da equipe podem adicionar aplicativos personalizados, se a política de aplicativo personalizada permitir.
- Os membros da equipe que não são proprietários da equipe não podem adicionar aplicativos personalizados à equipe.

Se essa configuração estiver ativada:

- Os proprietários da equipe podem adicionar aplicativos personalizados, se a política de aplicativo personalizada permitir.
- Os membros da equipe que não são proprietários de equipe podem adicionar aplicativos personalizados, se a política de aplicativo personalizada permitir.

#### <a name="configure-the-team-custom-app-setting"></a>Definir a configuração de aplicativo personalizado da equipe

1. No Teams, vá para a equipe, clique em **Mais opções...** >  **Gerencie a equipe**.
2. Clique **Configurações** e expanda **permissões de membro**.
3. Marque ou desmarque **a caixa de seleção Permitir que os membros carreguem aplicativos personalizados** .

    ![Captura de tela mostrando a configuração do aplicativo personalizado da equipe.](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a>Configuração de aplicativo personalizado em toda a organização

A **configuração** Permitir interação com aplicativos personalizados em toda a organização [](manage-apps.md) na página Gerenciar aplicativos se aplica a todos em sua organização e determina se eles podem carregar ou interagir com aplicativos personalizados. Essa configuração atua como uma opção de ativar/desativar mestre para as configurações de política de aplicativo personalizada do usuário e da equipe. Ele serve como um botão de ligar/desligar mestre durante eventos de segurança. Dessa forma, as configurações de política de aplicativo personalizada do usuário e da equipe não entrarão em vigor, a menos que a configuração de aplicativo personalizado em toda a organização esteja habilitada, mesmo que as configurações de política de aplicativo personalizada do usuário e da equipe estejam habilitadas.

#### <a name="configure-the-org-wide-custom-app-setting"></a>Definir a configuração de aplicativo personalizado em toda a organização

1. Na navegação à esquerda do Centro de Administração do Microsoft Teams, vá para **Aplicativos do Teams** > **Gerenciar aplicativos**.
2. Clique **nas configurações do aplicativo em toda a organização**.
3. Em **Aplicativos personalizados**, ative ou **desative Permitir interação com aplicativos personalizados**.

    ![Captura de tela mostrando as configurações de aplicativo personalizado em toda a organização.](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a>Como as configurações e políticas de aplicativo personalizadas funcionam em conjunto

Esta tabela resume a política e as configurações personalizadas do aplicativo, como elas funcionam em conjunto e seu efeito combinado no controle de quem em sua organização pode carregar aplicativos personalizados para Teams.

Por exemplo, você deseja permitir que apenas os proprietários da equipe carreguem aplicativos personalizados para equipes específicas. Você definiria o seguinte:

- Ative **a configuração Permitir interação com aplicativos** personalizados no Microsoft Teams de administração.
- Desative a **opção Permitir que os membros carreguem aplicativos personalizados** para cada equipe à qual você deseja restringir o acesso.
- Crie e atribua uma política de configuração de aplicativo personalizada no centro de administração do Microsoft Teams  com a configuração de aplicativos personalizados Upload ativada e atribua-a aos proprietários da equipe.

|Configuração de aplicativo personalizado em toda a organização |Configuração de aplicativo personalizado da equipe |Política de aplicativo personalizado do usuário |Efeito  |
|---------|---------|---------|---------|
| Desabilitado    | Desabilitado    | Desabilitado     |A interação com todos os aplicativos personalizados é bloqueada para sua organização. Aplicativos personalizados não podem ser carregados por ninguém, exceto um Teams service Administração ou um administrador global. Você pode usar o PowerShell para remover o aplicativo personalizado.   |
| Desabilitado     | Desabilitado     | Habilitado        |A interação com todos os aplicativos personalizados é bloqueada para sua organização. Aplicativos personalizados não podem ser carregados por ninguém, exceto um Teams service Administração ou um administrador global. Você pode usar o PowerShell para remover o aplicativo personalizado.         |
| Desabilitado    | Habilitado        | Desabilitado        |A interação com todos os aplicativos personalizados é bloqueada para sua organização. Aplicativos personalizados não podem ser carregados por ninguém, exceto um Teams service Administração ou um administrador global. Você pode usar Windows PowerShell para excluir aplicativos personalizados.         |
| Desabilitado    | Habilitado      | Habilitado       |A interação com todos os aplicativos personalizados é bloqueada para sua organização. Aplicativos personalizados não podem ser carregados por ninguém, exceto um Teams service Administração ou um administrador global. Você pode usar o PowerShell para remover o aplicativo personalizado.         |
| Habilitado    | Desabilitado       | Desabilitado         |  O usuário não pode carregar aplicativos personalizados.      |
| Habilitado     | Desabilitado       | Habilitado         | Se o usuário for um proprietário de equipe, ele poderá carregar aplicativos personalizados para a equipe. Se o usuário não for um proprietário de equipe, ele não poderá carregar aplicativos personalizados para a equipe. O usuário pode carregar aplicativos personalizados no contexto pessoal.     |
| Habilitado     | Habilitado     | Desabilitado         | O usuário não pode carregar aplicativos personalizados.       |
| Habilitado    | Habilitado        | Habilitado        | O usuário pode carregar aplicativos personalizados para a equipe, independentemente de o usuário ser um proprietário da equipe. O usuário pode carregar aplicativos personalizados no contexto pessoal.       |

## <a name="related-topics"></a>Tópicos relacionados

[Configurações de administrador para aplicativos no Teams](admin-settings.md)

[Atribua políticas a seus usuários no Teams](assign-policies-users-and-groups.md)
