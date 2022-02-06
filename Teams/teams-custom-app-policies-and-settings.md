---
title: Gerenciar políticas e configurações personalizadas de aplicativos
author: SerdarSoysal
ms.author: serdars
manager: serdars
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
description: Saiba como gerenciar políticas e configurações de aplicativos personalizadas para controlar quem em sua organização pode carregar aplicativos personalizados em Microsoft Teams.
f1.keywords:
  - CSH
ms.custom:
  - ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
  - ms.teamsadmincenter.appsetuppolicies.allowsideloading
  - ms.teamsadmincenter.appsetuppolicies.tooltip.allowsideloading
  - ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
  - seo-marvel-mar2020
---

# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a>Gerencie políticas e configurações de aplicativo personalizado no Microsoft Teams

> [!NOTE]
> Para usar o App Studio, confira Começar [na plataforma Microsoft Teams com o C#/.NET e o App Studio](/microsoftteams/platform/get-started/get-started-dotnet-app-studio) A última etapa ainda não está funcionando, portanto, você precisará baixar o [Upload](/microsoftteams/platform/concepts/apps/apps-upload) zip e instalá-lo da maneira antiga em um pacote de aplicativos para Microsoft Teams.

Como administrador, você pode usar políticas e configurações de aplicativo personalizadas para controlar quem em sua organização pode carregar aplicativos personalizados para Microsoft Teams. Os administradores decidem quais usuários podem carregar aplicativos personalizados, e os administradores e proprietários de equipe podem determinar se equipes específicas em sua organização permitem que aplicativos personalizados sejam adicionados a eles.  Depois de editar a política de aplicativo personalizada, pode levar algumas horas para que as alterações entre em vigor. Você deve ser um administrador global ou administrador de serviços do Teams para gerenciar essas políticas.

## <a name="overview-of-custom-apps"></a>Visão geral dos aplicativos personalizados

Os usuários podem adicionar um aplicativo personalizado ao Teams carregando um pacote de aplicativos (em um arquivo .zip) diretamente para uma equipe ou no contexto pessoal. Isso é diferente de como os aplicativos são adicionados por meio do Teams de aplicativos. Adicionar um aplicativo personalizado carregando um pacote de aplicativos, também conhecido como sideload, permite testar um aplicativo enquanto ele está sendo desenvolvido, antes de estar pronto para ser amplamente distribuído. Ele também permite que você crie um aplicativo apenas para uso interno e compartilhe-o com sua equipe sem enviar para o catálogo de aplicativos Teams no Teams app store.

![Captura de tela mostrando o carregamento de uma opção de aplicativo personalizada na loja de aplicativos.](media/teams-custom-app-policy-and-settings-upload-app.png)

## <a name="custom-app-policy-and-settings"></a>Configurações e políticas de aplicativos personalizados

Três componentes determinam se um usuário pode carregar um aplicativo personalizado em uma equipe, dando a você controle granular sobre quem pode adicionar aplicativos personalizados a uma equipe e a quais aplicativos personalizados de equipe podem ser adicionados:

- [Política de aplicativo personalizado do usuário](#user-custom-app-policy)
- [Configuração de aplicativo personalizado de equipe](#team-custom-app-setting)
- [Configuração de aplicativo personalizado em toda a organização](#org-wide-custom-app-setting)

Essas configurações não afetam a capacidade de bloquear aplicativos de terceiros.  

### <a name="user-custom-app-policy"></a>Política de aplicativo personalizado do usuário

Como parte das políticas de [configuração](teams-app-setup-policies.md) de aplicativos, os administradores podem usar uma configuração de política, Upload **aplicativos** personalizados, para controlar se um usuário pode carregar aplicativos personalizados para Teams.
 
Se essa configuração estiver desligada:

- O usuário não pode carregar um aplicativo personalizado para qualquer equipe em sua organização ou no contexto pessoal.
- O usuário pode interagir com aplicativos personalizados, dependendo da configuração de aplicativo personalizado em toda a organização.

Se essa configuração estiver configurada:

- O usuário pode carregar aplicativos personalizados em equipes que permitem e para equipes para as quais são proprietários, dependendo da configuração de aplicativo personalizado em toda a organização.
- O usuário pode carregar aplicativos personalizados no contexto pessoal. 
- O usuário pode interagir com aplicativos personalizados, dependendo da configuração de aplicativo personalizado em toda a organização.

Você pode editar as configurações na política de configuração de aplicativo global para incluir os aplicativos que deseja. Se você quiser personalizar o Teams para diferentes grupos de usuários em sua organização, crie e atribua uma ou mais políticas de configuração de aplicativo personalizadas.

#### <a name="set-a-user-custom-app-policy"></a>Definir uma política de aplicativo personalizada do usuário

1. Na navegação à esquerda do centro de administração Microsoft Teams, acesse **Teams** **appsSetup** >  policies.
2. Clique em **Adicionar**.
3. Ativar ou desativar Upload **aplicativos personalizados**.
4. Escolha quaisquer outras configurações que você deseja para a política.
5. Clique em **Salvar**.

### <a name="team-custom-app-setting"></a>Configuração de aplicativo personalizado de equipe

Os administradores e proprietários de equipe podem controlar se uma equipe permite que aplicativos personalizados sejam adicionados a ela. Essa configuração, **Permitir** que os membros carreguem aplicativos personalizados, juntamente com a política de aplicativo personalizada de um usuário, determina quem pode adicionar aplicativos personalizados a uma equipe específica.
 
Se essa configuração estiver desligada:

- Os proprietários de equipe podem adicionar aplicativos personalizados, se a política de aplicativo personalizada permitir.
- Os membros da equipe que não são proprietários de equipe não podem adicionar aplicativos personalizados à equipe.

Se essa configuração estiver configurada:

- Os proprietários de equipe podem adicionar aplicativos personalizados, se a política de aplicativo personalizada permitir isso.
- Os membros da equipe que não são proprietários de equipe podem adicionar aplicativos personalizados, se a política de aplicativo personalizada permitir isso.

#### <a name="configure-the-team-custom-app-setting"></a>Configurar a configuração de aplicativo personalizado da equipe

1. Em Teams, vá para a equipe, clique em **Mais opções ̇ ̇ ̇** >  **Manage equipe**.
2. Clique **Configurações** e expanda **permissões de membro**.
3. Marque ou deslele **a caixa de seleção Permitir que os membros carreguem aplicativos personalizados** .

    ![Captura de tela mostrando a configuração do aplicativo personalizado da equipe.](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a>Configuração de aplicativo personalizado em toda a organização

A **configuração** Permitir interação com aplicativos personalizados em toda a organização [](manage-apps.md) na página Gerenciar aplicativos se aplica a todos na sua organização e rege se eles podem carregar ou interagir com aplicativos personalizados. Essa configuração atua como um botão mestre de ligar/desligar para as configurações de política de aplicativo personalizada do usuário e da equipe. Destina-se a servir como um botão mestre de ligar/desligar durante eventos de segurança. Dessa forma, as configurações de política de aplicativo personalizada do usuário e da equipe não terão efeito, a menos que a configuração do aplicativo personalizado em toda a organização esteja habilitada, mesmo que as configurações de política de aplicativo personalizada do usuário e da equipe sejam habilitadas.

#### <a name="configure-the-org-wide-custom-app-setting"></a>Configurar a configuração de aplicativo personalizado em toda a organização

1. Na navegação à esquerda do Centro de Administração do Microsoft Teams, vá para **Aplicativos do Teams** > **Gerenciar aplicativos**.
2. Clique **em Configurações de aplicativo em toda a organização**.
3. Em **Aplicativos personalizados**, a ligue ou desligue **Permitir interação com aplicativos personalizados**.

    ![Captura de tela mostrando as configurações de aplicativo personalizado em toda a organização.](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a>Como as políticas e configurações de aplicativos personalizadas funcionam em conjunto

Esta tabela resume a política e as configurações personalizadas do aplicativo, como eles trabalham juntos e seu efeito combinado no controle de quem em sua organização pode carregar aplicativos personalizados para Teams.

Por exemplo, você deseja permitir que apenas proprietários de equipe carreguem aplicativos personalizados para equipes específicas. Você definiria o seguinte:

- A opção Permitir **interação com aplicativos personalizados** no Microsoft Teams de administração.
- Desativar o **Permitir que os membros carreguem aplicativos personalizados** para cada equipe à qual você deseja restringir o acesso.
- Crie e atribua uma política de configuração de aplicativo personalizada no centro de administração Microsoft Teams com  a configuração de aplicativos personalizados Upload configuração personalizada e atribua-a aos proprietários da equipe.

|Configuração de aplicativo personalizado em toda a organização |Configuração de aplicativo personalizado de equipe |Política de aplicativo personalizado do usuário |Efeito  |
|---------|---------|---------|---------|
| Desabilitado    | Desabilitado    | Desabilitado     |A interação com todos os aplicativos personalizados é bloqueada para sua organização. Aplicativos personalizados não podem ser carregados por ninguém, exceto um administrador Teams serviço ou um administrador global. Você pode usar o PowerShell para remover o aplicativo personalizado.   |
| Desabilitado     | Desabilitado     | Habilitado        |A interação com todos os aplicativos personalizados é bloqueada para sua organização. Aplicativos personalizados não podem ser carregados por ninguém, exceto um administrador Teams serviço ou um administrador global. Você pode usar o PowerShell para remover o aplicativo personalizado.         |
| Desabilitado    | Habilitado        | Desabilitado        |A interação com todos os aplicativos personalizados é bloqueada para sua organização. Aplicativos personalizados não podem ser carregados por ninguém, exceto um administrador Teams serviço ou um administrador global. Você pode usar Windows PowerShell para excluir aplicativos personalizados.         |
| Desabilitado    | Habilitado      | Habilitado       |A interação com todos os aplicativos personalizados é bloqueada para sua organização. Aplicativos personalizados não podem ser carregados por ninguém, exceto um administrador Teams serviço ou um administrador global. Você pode usar o PowerShell para remover o aplicativo personalizado.         |
| Habilitado    | Desabilitado       | Desabilitado         |  O usuário não pode carregar aplicativos personalizados.      |
| Habilitado     | Desabilitado       | Habilitado         | Se o usuário for um proprietário de equipe, ele poderá carregar aplicativos personalizados para a equipe. Se o usuário não for um proprietário de equipe, ele não poderá carregar aplicativos personalizados para a equipe. O usuário pode carregar aplicativos personalizados no contexto pessoal.     |
| Habilitado     | Habilitado     | Desabilitado         | O usuário não pode carregar aplicativos personalizados.       |
| Habilitado    | Habilitado        | Habilitado        | O usuário pode carregar aplicativos personalizados para a equipe, independentemente de o usuário ser um proprietário da equipe. O usuário pode carregar aplicativos personalizados no contexto pessoal.       |

## <a name="related-topics"></a>Tópicos relacionados

[Configurações de administrador para aplicativos no Teams](admin-settings.md)

[Atribua políticas a seus usuários no Teams](assign-policies-users-and-groups.md)