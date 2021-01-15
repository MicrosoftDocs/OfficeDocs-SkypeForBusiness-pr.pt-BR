---
title: Gerenciar políticas e configurações de aplicativos personalizados
author: cichur
ms.author: v-cichur
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
localization_priority: Normal
search.appverid: MET150
description: Saiba como gerenciar políticas e configurações de aplicativos personalizados para controlar quem em sua organização pode carregar aplicativos personalizados no Microsoft Teams.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.allowsideloading
- ms.teamsadmincenter.appsetuppolicies.tooltip.allowsideloading
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- seo-marvel-mar2020
ms.openlocfilehash: 4e9863508d7b10c76ed29bfcb0fec79ca7a33dc5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821001"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a>Gerencie políticas e configurações de aplicativo personalizado no Microsoft Teams

> [!NOTE]
> To use App Studio see [Get started on the Microsoft Teams platform with C#/.NET and App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-dotnet-app-studio) The last step is not working yet, so you will need to download the zip and install it the old way at Upload an app package to Microsoft [Teams](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload).

Como administrador, você pode usar políticas e configurações de aplicativo personalizadas para controlar quem em sua organização pode carregar aplicativos personalizados para o Microsoft Teams. Os administradores decidem quais usuários podem carregar aplicativos personalizados, e os administradores e proprietários de equipe podem determinar se equipes específicas em sua organização permitem que aplicativos personalizados sejam adicionados a eles.  Depois de editar a política de aplicativo personalizada, pode levar algumas horas para que as alterações entrem em vigor. Você deve ser um administrador global ou administrador de serviços do Teams para gerenciar essas políticas.

## <a name="overview-of-custom-apps"></a>Visão geral dos aplicativos personalizados

Os usuários podem adicionar um aplicativo personalizado ao Teams carregando um pacote de aplicativo (em um arquivo .zip) diretamente para uma equipe ou no contexto pessoal. Isso é diferente de como os aplicativos são adicionados por meio da loja de aplicativos do Teams. Adicionar um aplicativo personalizado carregando um pacote de aplicativo, também conhecido como sideload, permite testar um aplicativo conforme ele está sendo desenvolvido, antes que ele esteja pronto para ser amplamente distribuído. Ele também permite que você crie um aplicativo apenas para uso interno e compartilhe-o com sua equipe sem repassá-lo ao catálogo de aplicativos do Teams na loja de aplicativos do Teams.

![Captura de tela mostrando o carregamento de uma opção de aplicativo personalizado na loja de aplicativos](media/teams-custom-app-policy-and-settings-upload-app.png)

## <a name="custom-app-policy-and-settings"></a>Configurações e política de aplicativo personalizada

Três componentes determinam se um usuário pode carregar um aplicativo personalizado para uma equipe, dando a você controle granular sobre quem pode adicionar aplicativos personalizados a uma equipe e a quais aplicativos personalizados de equipes podem ser adicionados:

- [Política de aplicativo personalizado do usuário](#user-custom-app-policy)
- [Configuração de aplicativo personalizado de equipe](#team-custom-app-setting)
- [Configuração de aplicativo personalizado em toda a organização](#org-wide-custom-app-setting)

Essas configurações não afetam a capacidade de bloquear aplicativos de terceiros.  

### <a name="user-custom-app-policy"></a>Política de aplicativo personalizado do usuário

Como parte das políticas [de configuração](teams-app-setup-policies.md)de **aplicativos,** os administradores podem usar uma configuração de política, carregar aplicativos personalizados , para controlar se um usuário pode carregar aplicativos personalizados para o Teams.
 
Se essa configuração estiver desligada:

- O usuário não pode carregar um aplicativo personalizado para qualquer equipe em sua organização ou no contexto pessoal.
- O usuário pode interagir com aplicativos personalizados, dependendo da configuração do aplicativo personalizado em toda a organização.

Se essa configuração estiver 2010 2010 2010 20

- O usuário pode carregar aplicativos personalizados para equipes que permitem e para equipes para as quais são proprietários, dependendo da configuração do aplicativo personalizado em toda a organização.
- O usuário pode carregar aplicativos personalizados para o contexto pessoal. 
- O usuário pode interagir com aplicativos personalizados, dependendo da configuração do aplicativo personalizado em toda a organização.

Você pode editar as configurações na política de configuração de aplicativo global para incluir os aplicativos que deseja. Se você quiser personalizar o Teams para diferentes grupos de usuários em sua organização, crie e atribua uma ou mais políticas de configuração de aplicativo personalizadas.

#### <a name="set-a-user-custom-app-policy"></a>Definir uma política de aplicativo personalizada do usuário

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para políticas de Instalação de **aplicativos**  >  **do** Teams.
2. Clique em **Adicionar**.
3. Ativar ou desativar o **carregamento de aplicativos personalizados.**
4. Escolha outras configurações que você deseja para a política.
5. Clique em **Salvar**.

### <a name="team-custom-app-setting"></a>Configuração de aplicativo personalizado de equipe

Os administradores e proprietários da equipe podem controlar se uma equipe permite que aplicativos personalizados sejam adicionados a ela. Essa configuração, **Permitir que** os membros carreguem aplicativos personalizados, juntamente com a política de aplicativo personalizada de um usuário, determina quem pode adicionar aplicativos personalizados a uma equipe específica.
 
Se essa configuração estiver desligada:

- Os proprietários de equipe podem adicionar aplicativos personalizados, se a política de aplicativo personalizada permitir.
- Os membros da equipe que não são proprietários da equipe não podem adicionar aplicativos personalizados à equipe.

Se essa configuração estiver 2010 2010 2010 20

- Os proprietários de equipe podem adicionar aplicativos personalizados, se a política de aplicativo personalizada permitir.
- Os membros da equipe que não são proprietários de equipe podem adicionar aplicativos personalizados, se a política de aplicativo personalizada permitir.

#### <a name="configure-the-team-custom-app-setting"></a>Definir a configuração do aplicativo personalizado da equipe

1. No Teams, vá para a equipe, clique em **Mais opções ̇ ̇ ̇** Gerenciar  >  **equipe.**
2. Clique **em Configurações** e expanda **permissões de membro.**
3. Marque ou des limpe a caixa de seleção Permitir **que os membros carreguem aplicativos personalizados.**

    ![Captura de tela mostrando a configuração do aplicativo personalizado da equipe](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a>Configuração de aplicativo personalizado em toda a organização

A **configuração** de aplicativo personalizado Permitir interação [](manage-apps.md) com aplicativos personalizados em toda a organização na página Gerenciar aplicativos se aplica a todos em sua organização e rege se eles podem carregar ou interagir com aplicativos personalizados. Essa configuração atua como um botão de ligar/desligar mestre para as configurações de política de aplicativo personalizada do usuário e da equipe. Destina-se a servir como um botão de ligar/desligar mestre durante eventos de segurança. Dessa forma, as configurações de política de aplicativo personalizada do usuário e da equipe não terão efeito, a menos que a configuração de aplicativo personalizado em toda a organização esteja habilitada, mesmo que as configurações de política de aplicativo personalizada de usuário e equipe sejam habilitadas.

#### <a name="configure-the-org-wide-custom-app-setting"></a>Definir a configuração do aplicativo personalizado em toda a organização

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **aplicativos do Teams**  >  **Gerenciar aplicativos.**
2. Clique **em Configurações de aplicativos em toda a organização.**
3. Em **aplicativos personalizados,** a turn on or turn off **Allow interaction with custom apps**.

    ![Captura de tela mostrando as configurações de aplicativo personalizado em toda a organização](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a>Como as políticas e configurações de aplicativos personalizados funcionam em conjunto

Esta tabela resume a política e as configurações personalizadas do aplicativo, como eles trabalham juntos e seu efeito combinado no controle de quem em sua organização pode carregar aplicativos personalizados para o Teams.

Por exemplo, você deseja permitir que apenas proprietários de equipe carreguem aplicativos personalizados para equipes específicas. Você definiria o seguinte:
- Ativar a **configuração Permitir interação com aplicativos** personalizados no centro de administração do Microsoft Teams.
- Desativar o **recurso Permitir que os membros carreguem aplicativos personalizados** para cada equipe à qual você deseja restringir o acesso.
- Crie e atribua uma política de configuração  de aplicativo personalizada no centro de administração do Microsoft Teams com a configuração Carregar aplicativos personalizados 2013 e atribua-a aos proprietários da equipe.

|Configuração de aplicativo personalizado em toda a organização |Configuração de aplicativo personalizado de equipe |Política de aplicativo personalizado do usuário |Efeito  |
|---------|---------|---------|---------|
| Desabilitado    | Desabilitado    | Desabilitado     |A interação com todos os aplicativos personalizados é bloqueada para sua organização. Aplicativos personalizados não podem ser carregados por ninguém, exceto um Administrador de Serviço do Teams ou um administrador global. Você pode usar o PowerShell para remover o aplicativo personalizado.   |
| Desabilitado     | Desabilitado     | Habilitado        |A interação com todos os aplicativos personalizados é bloqueada para sua organização. Aplicativos personalizados não podem ser carregados por ninguém, exceto um Administrador de Serviço do Teams ou um administrador global. Você pode usar o PowerShell para remover o aplicativo personalizado.         |
| Desabilitado    | Habilitado        | Desabilitado        |A interação com todos os aplicativos personalizados é bloqueada para sua organização. Aplicativos personalizados não podem ser carregados por ninguém, exceto um Administrador de Serviço do Teams ou um administrador global. Você pode usar Windows PowerShell para excluir aplicativos personalizados.         |
| Desabilitado    | Habilitado      | Habilitado       |A interação com todos os aplicativos personalizados é bloqueada para sua organização. Aplicativos personalizados não podem ser carregados por ninguém, exceto um Administrador de Serviço do Teams ou um administrador global. Você pode usar o PowerShell para remover o aplicativo personalizado.         |
| Habilitado    | Desabilitado       | Desabilitado         |  O usuário não pode carregar aplicativos personalizados.      |
| Habilitado     | Desabilitado       | Habilitado         | Se o usuário for um proprietário de equipe, ele poderá carregar aplicativos personalizados para a equipe. Se o usuário não for um proprietário de equipe, ele não poderá carregar aplicativos personalizados para a equipe. O usuário pode carregar aplicativos personalizados no contexto pessoal.     |
| Habilitado     | Habilitado     | Desabilitado         | O usuário não pode carregar aplicativos personalizados.       |
| Habilitado    | Habilitado        | Habilitado        | O usuário pode carregar aplicativos personalizados para a equipe, independentemente de o usuário ser proprietário da equipe. O usuário pode carregar aplicativos personalizados no contexto pessoal.       |

## <a name="related-topics"></a>Tópicos relacionados
 
[Configurações de administração para aplicativos no Teams](admin-settings.md)

[Atribuir políticas aos usuários no Microsoft Teams](assign-policies.md)