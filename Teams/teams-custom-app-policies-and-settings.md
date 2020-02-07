---
title: Gerencie políticas e configurações de aplicativo personalizado no Microsoft Teams
author: lanachin
ms.author: v-lanac
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
description: Saiba como gerenciar políticas e configurações personalizadas do aplicativo para controlar quem em sua organização pode carregar aplicativos personalizados no Microsoft Teams.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.allowsideloading
- ms.teamsadmincenter.appsetuppolicies.tooltip.allowsideloading
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
ms.openlocfilehash: c86e140c917300d1d9a05a42e81cf8095ed3a670
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837701"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a>Gerencie políticas e configurações de aplicativo personalizado no Microsoft Teams

> [!NOTE]
> Para usar o app Studio [, consulte Introdução à plataforma Microsoft Teams com C#/.net e app Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-dotnet-app-studio) a última etapa ainda não está funcionando, portanto, será necessário baixar o zip e instalá-lo da maneira antiga de [carregar um pacote do aplicativo para o Microsoft Teams](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload).

Como administrador, você pode usar políticas e configurações personalizadas do aplicativo para controlar quem em sua organização pode carregar aplicativos personalizados para o Microsoft Teams. Os administradores decidem quais usuários podem carregar aplicativos personalizados, e administradores e proprietários de equipe podem determinar se equipes específicas em sua organização permitem que aplicativos personalizados sejam adicionados a eles.  Depois de editar a política de aplicativo personalizada, pode levar até 24 horas para que as alterações entrem em vigor.

## <a name="overview-of-custom-apps"></a>Visão geral dos aplicativos personalizados

Os usuários podem adicionar um aplicativo personalizado ao Teams carregando um pacote de aplicativo (em um arquivo. zip) diretamente a uma equipe ou no contexto pessoal. Isso é diferente do modo como os aplicativos são adicionados por meio da loja de aplicativos Teams. Adicionar um aplicativo personalizado carregando um pacote de aplicativo, também conhecido como Sideload, permite que você teste um aplicativo como ele está sendo desenvolvido antes de estar pronto para ser amplamente distribuído. Ele também permite criar um aplicativo para uso interno somente e compartilhá-lo com sua equipe sem enviá-lo para o catálogo de aplicativos do teams na loja de aplicativos do teams.

![Captura de tela mostrando a opção carregar um aplicativo personalizado na App Store](media/teams-custom-app-policy-and-settings-upload-app.png)

## <a name="custom-app-policy-and-settings"></a>Política e configurações personalizadas do aplicativo

Três componentes determinam se um usuário pode carregar um aplicativo personalizado para uma equipe, dando a você controle granular sobre quem pode adicionar aplicativos personalizados a uma equipe e quais aplicativos personalizados de equipe podem ser adicionados a:

- [Política de aplicativo personalizada do usuário](#user-custom-app-policy)
- [Configuração do aplicativo personalizado da equipe](#team-custom-app-setting)
- [Configuração de aplicativo personalizado em toda a organização](#org-wide-custom-app-setting)

Essas configurações não afetam a capacidade de bloquear aplicativos de terceiros.  

### <a name="user-custom-app-policy"></a>Política de aplicativo personalizada do usuário

Como parte das [políticas de configuração do aplicativo](teams-app-setup-policies.md), os administradores podem usar uma configuração de política, **permitir o upload de aplicativos personalizados**, para controlar se um usuário pode carregar aplicativos personalizados para o Microsoft Teams.
 
Se essa configuração estiver desativada:

- O usuário não pode carregar um aplicativo personalizado para qualquer equipe em sua organização ou no contexto pessoal.
- O usuário pode interagir com aplicativos personalizados, dependendo da configuração do aplicativo personalizado em toda a organização.

Se essa configuração estiver ativada:

- O usuário pode carregar aplicativos personalizados para o Microsoft Teams que permite e para as equipes das quais eles são proprietários, dependendo da configuração do aplicativo personalizado em toda a organização.
- O usuário pode carregar aplicativos personalizados para o contexto pessoal. 
- O usuário pode interagir com aplicativos personalizados, dependendo da configuração do aplicativo personalizado em toda a organização.

Você pode editar as configurações na política de configuração do aplicativo global para incluir os aplicativos desejados. Se você quiser personalizar o Microsoft Teams para diferentes grupos de usuários em sua organização, crie e atribua uma ou mais políticas de configuração de aplicativos personalizadas.

#### <a name="set-a-user-custom-app-policy"></a>Definir uma política de aplicativo personalizada do usuário

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para > **políticas de configuração**de **aplicativos do teams**.
2. Clique em **Adicionar**.
3. Ative ou desative a opção **permitir upload de aplicativos personalizados**.
4. Escolha qualquer outra configuração que você queira para a política.
5. Clique em **Salvar**.

### <a name="team-custom-app-setting"></a>Configuração do aplicativo personalizado da equipe

Administradores e proprietários de equipe podem controlar se uma equipe permite que aplicativos personalizados sejam adicionados a ele. Essa configuração, **permitir que os membros carreguem aplicativos personalizados**juntamente com a política de aplicativo personalizada de um usuário determina quem pode adicionar aplicativos personalizados a uma equipe específica.
 
Se essa configuração estiver desativada:

- Os proprietários da equipe podem adicionar aplicativos personalizados, se a política personalizada do aplicativo permitir.
- Os membros da equipe que não são proprietários da equipe não podem adicionar aplicativos personalizados à equipe.

Se essa configuração estiver ativada:

- Os proprietários da equipe podem adicionar aplicativos personalizados, caso a política personalizada do aplicativo permita isso.
- Os membros da equipe que não são proprietários da equipe podem adicionar aplicativos personalizados, caso a política personalizada do aplicativo permita isso.

#### <a name="configure-the-team-custom-app-setting"></a>Configurar a configuração do aplicativo personalizado da equipe

1. No Microsoft Teams, vá para a equipe, clique em **mais opções ̇ ̇ ̇** > **Gerenciar equipe**.
2. Clique em **configurações**e, em seguida, expanda **permissões do membro**.
3. Marque ou desmarque a caixa de seleção **permitir que os membros carreguem aplicativos personalizados** .

    ![Captura de tela mostrando a configuração do aplicativo personalizado da equipe](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a>Configuração de aplicativo personalizado em toda a organização

A configuração de aplicativo personalizada em toda a organização, **permitir interação com aplicativos personalizados**, se aplica a todos em sua organização e controla se elas podem ou não carregar ou interagir com aplicativos personalizados. Essa configuração substitui a configuração e a política de aplicativos personalizados do usuário e da equipe. Ele tem o objetivo de servir como uma chave mestre liga/desliga durante eventos de segurança.

#### <a name="configure-the-org-wide-custom-app-setting"></a>Configurar a configuração de aplicativo personalizado em toda a organização

1. Na navegação à esquerda do [centro de administração do Microsoft Teams](https://admin.teams.microsoft.com/), vá para**políticas de permissão**de aplicativos > do **Teams**.
2. Clique em **configurações de aplicativo de toda a organização**.
3. Em **aplicativos personalizados**, ative ou desative **a interação de permissão com aplicativos personalizados**.

    ![Captura de tela mostrando as configurações personalizadas do aplicativo de toda a organização](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a>Como as configurações e políticas personalizadas do aplicativo funcionam em conjunto

Esta tabela resume as configurações e a política personalizadas do aplicativo, como elas funcionam em conjunto, e o efeito combinado sobre como controlar quem em sua organização pode carregar aplicativos personalizados para o Microsoft Teams.

Digamos, por exemplo, que você queira permitir que apenas proprietários de equipes carreguem aplicativos personalizados para equipes específicas. Você definiria o seguinte:
- Ative a configuração **permitir interação com aplicativos personalizados** no centro de administração do Microsoft Teams.
- Desative a opção **permitir que os membros carreguem aplicativos personalizados** para cada equipe à qual você deseja restringir o acesso.
- Criar e atribuir uma política de configuração de aplicativo personalizada no centro de administração do Microsoft Teams com o **usuário pode carregar** a configuração de aplicativos personalizados ativada e atribuí-la aos proprietários da equipe.

|Configuração de aplicativo personalizado em toda a organização |Configuração do aplicativo personalizado da equipe |Política de aplicativo personalizada do usuário |Efeito  |
|---------|---------|---------|---------|
| Desativado    | Desativado    | Desativado     |A interação com todos os aplicativos personalizados está bloqueada para sua organização. Os aplicativos personalizados não podem ser carregados por qualquer pessoa. Você pode usar o PowerShell para remover o aplicativo personalizado.   |
| Desativado     | Desativado     | Ativado        |A interação com todos os aplicativos personalizados está bloqueada para sua organização. Os aplicativos personalizados não podem ser carregados por qualquer pessoa. Você pode usar o PowerShell para remover o aplicativo personalizado.         |
| Desativado    | Ativado        | Desativado        |A interação com todos os aplicativos personalizados está bloqueada para sua organização. Os aplicativos personalizados não podem ser carregados por qualquer pessoa. Você pode usar o Windows PowerShell para excluir aplicativos personalizados.         |
| Desativado    | Ativado      | Ativado       |A interação com todos os aplicativos personalizados está bloqueada para sua organização. Os aplicativos personalizados não podem ser carregados por qualquer pessoa. Você pode usar o PowerShell para remover o aplicativo personalizado.         |
| Ativado    | Desativado       | Desativado         |  O usuário não pode carregar aplicativos personalizados.      |
| Ativado     | Desativado       | Ativado         | Se o usuário for um proprietário da equipe, ele pode carregar aplicativos personalizados para a equipe. Se o usuário não for um proprietário da equipe, ele não poderá carregar aplicativos personalizados para a equipe. O usuário pode carregar aplicativos personalizados no contexto pessoal.     |
| Ativado     | Ativado     | Desativado         | O usuário não pode carregar aplicativos personalizados.       |
| Ativado    | Ativado        | Ativado        | O usuário pode carregar aplicativos personalizados para a equipe, independentemente de o usuário ser um proprietário da equipe. O usuário pode carregar aplicativos personalizados no contexto pessoal.       |

 ## <a name="related-topics"></a>Tópicos relacionados
- [Configurações de administração para aplicativos no Teams](admin-settings.md)
