---
title: Gerenciar configurações e políticas de aplicativos personalizados
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
description: Saiba como gerenciar políticas e configurações de aplicativos personalizadas para controlar quem em sua organização pode carregar aplicativos personalizados no Microsoft Teams.
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
> Para usar o App Studio, confira a plataforma Microsoft Teams com [C#/.NET](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-dotnet-app-studio) e App Studio A última etapa ainda não está funcionando, portanto, você precisará baixar o zip e instalá-lo da maneira antiga ao carregar um pacote de aplicativos para o [Microsoft Teams.](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload)

Como administrador, você pode usar políticas e configurações de aplicativos personalizadas para controlar quem em sua organização pode carregar aplicativos personalizados para o Microsoft Teams. Os administradores decidem quais usuários podem carregar aplicativos personalizados, e os administradores e proprietários de equipes podem determinar se equipes específicas em sua organização permitem que aplicativos personalizados sejam adicionados a eles.  Depois de editar a política do aplicativo personalizado, pode levar algumas horas para que as alterações entre em vigor. Você deve ser um administrador global ou administrador de serviços do Teams para gerenciar essas políticas.

## <a name="overview-of-custom-apps"></a>Visão geral de aplicativos personalizados

Os usuários podem adicionar um aplicativo personalizado ao Teams carregando um pacote de aplicativos (em um arquivo .zip) diretamente em uma equipe ou no contexto pessoal. Isso é diferente de como os aplicativos são adicionados por meio da loja de aplicativos do Teams. Adicionar um aplicativo personalizado carregando um pacote de aplicativos, também conhecido como sideload, permite testar um aplicativo à medida que ele está sendo desenvolvido, antes de estar pronto para ser distribuído amplamente. Ele também permite que você crie um aplicativo somente para uso interno e compartilhe-o com sua equipe sem o envio para o catálogo de aplicativos do Teams na loja de aplicativos do Teams.

![Captura de tela mostrando a opção carregar um aplicativo personalizado na loja de aplicativos](media/teams-custom-app-policy-and-settings-upload-app.png)

## <a name="custom-app-policy-and-settings"></a>Configurações e política de aplicativos personalizados

Três componentes determinam se um usuário pode carregar um aplicativo personalizado para uma equipe, dando a você um controle granular sobre quem pode adicionar aplicativos personalizados a uma equipe e a quais aplicativos personalizados de equipes podem ser adicionados:

- [Política de aplicativo personalizado do usuário](#user-custom-app-policy)
- [Configuração de aplicativo personalizado da equipe](#team-custom-app-setting)
- [Configuração de aplicativo personalizado para toda a organização](#org-wide-custom-app-setting)

Essas configurações não afetam a capacidade de bloquear aplicativos de terceiros.  

### <a name="user-custom-app-policy"></a>Política de aplicativo personalizado do usuário

Como parte das políticas [de configuração](teams-app-setup-policies.md)de aplicativos, os administradores podem usar uma configuração de **política,** carregar aplicativos personalizados, para controlar se um usuário pode carregar aplicativos personalizados no Teams.
 
Se essa configuração estiver desligada:

- O usuário não pode carregar um aplicativo personalizado para nenhuma equipe em sua organização ou no contexto pessoal.
- O usuário pode interagir com aplicativos personalizados, dependendo da configuração do aplicativo personalizado para toda a organização.

Se essa configuração estiver 2010 2010 2010 20

- O usuário pode carregar aplicativos personalizados para equipes que o permitem e para equipes para as quais eles são proprietários, dependendo da configuração do aplicativo personalizado para toda a organização.
- O usuário pode carregar aplicativos personalizados para o contexto pessoal. 
- O usuário pode interagir com aplicativos personalizados, dependendo da configuração do aplicativo personalizado para toda a organização.

Você pode editar as configurações na política de configuração global do aplicativo para incluir os aplicativos que deseja. Se você quiser personalizar o Teams para diferentes grupos de usuários em sua organização, crie e atribua uma ou mais políticas de configuração de aplicativos personalizadas.

#### <a name="set-a-user-custom-app-policy"></a>Definir uma política de aplicativo personalizada do usuário

1. Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para políticas **de configuração** de aplicativos  >  **do** Teams.
2. Clique em **Adicionar**.
3. Ativar ou desativar o **carregamento de aplicativos personalizados.**
4. Escolha outras configurações que você deseja para a política.
5. Clique em **Salvar**.

### <a name="team-custom-app-setting"></a>Configuração de aplicativo personalizado da equipe

Os administradores e proprietários da equipe podem controlar se uma equipe permite que aplicativos personalizados sejam adicionados a ela. Essa **configuração** permite que os membros carreguem aplicativos personalizados, juntamente com a política de aplicativo personalizado do usuário, determina quem pode adicionar aplicativos personalizados a uma determinada equipe.
 
Se essa configuração estiver desligada:

- Os proprietários de equipe podem adicionar aplicativos personalizados, se a política de aplicativo personalizada permitir.
- Os membros da equipe que não são proprietários da equipe não podem adicionar aplicativos personalizados à equipe.

Se essa configuração estiver 2010 2010 2010 20

- Os proprietários da equipe podem adicionar aplicativos personalizados, se a política de aplicativo personalizada permitir.
- Os membros da equipe que não são proprietários da equipe podem adicionar aplicativos personalizados, se a política de aplicativo personalizada permitir.

#### <a name="configure-the-team-custom-app-setting"></a>Configurar a configuração do aplicativo personalizado da equipe

1. No Teams, vá para a equipe, clique **em Mais opções ̇ ̇ ̇** Gerenciar  >  **equipe.**
2. Clique **em Configurações** e expanda **as permissões de Membro.**
3. Marque ou des limpe **a caixa de seleção Permitir que os membros carreguem aplicativos personalizados.**

    ![Captura de tela mostrando a configuração do aplicativo personalizado da equipe](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a>Configuração de aplicativo personalizado para toda a organização

A **configuração** permitir interação com aplicativos [](manage-apps.md) personalizados em toda a organização na página Gerenciar aplicativos se aplica a todos em sua organização e rege se eles podem carregar ou interagir com aplicativos personalizados. Essa configuração funciona como uma opção de aplicação mestre para as configurações de política de aplicativo personalizada do usuário e da equipe. Destina-se a servir como um botão mestre de a ligar/desligar durante eventos de segurança. Dessa forma, as configurações de política de aplicativo personalizado do usuário e da equipe não terão efeito, a menos que a configuração do aplicativo personalizado de toda a organização esteja habilitada, mesmo que as configurações de política de aplicativo personalizado do usuário e da equipe sejam habilitadas.

#### <a name="configure-the-org-wide-custom-app-setting"></a>Configurar a configuração de aplicativo personalizado para toda a organização

1. Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para Os **aplicativos do Teams**  >  **Gerenciar aplicativos.**
2. Clique **em Configurações de aplicativo em toda a organização.**
3. Em **Aplicativos personalizados,** a ligue ou desligue **Permitir interação com aplicativos personalizados.**

    ![Captura de tela mostrando as configurações do aplicativo personalizado para toda a organização](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a>Como as configurações e políticas personalizadas do aplicativo funcionam em conjunto

Esta tabela resume as configurações e a política de aplicativos personalizadas, como elas funcionam em conjunto e seu efeito combinado no controle de quem em sua organização pode carregar aplicativos personalizados para o Teams.

Por exemplo, você deseja permitir que somente os proprietários de equipe carreguem aplicativos personalizados para equipes específicas. Você definiria o seguinte:
- Ativar a **configuração Permitir interação com aplicativos** personalizados no Centro de administração do Microsoft Teams.
- Desativar o **recurso Permitir que os membros carreguem aplicativos personalizados** para todas as equipes às quais você deseja restringir o acesso.
- Crie e atribua uma política de configuração  de aplicativo personalizada no Centro de administração do Microsoft Teams com a configuração Carregar aplicativos personalizados responsabilidade e atribua-a aos proprietários da equipe.

|Configuração de aplicativo personalizado para toda a organização |Configuração de aplicativo personalizado da equipe |Política de aplicativo personalizado do usuário |Efeito  |
|---------|---------|---------|---------|
| Desabilitado    | Desabilitado    | Desabilitado     |A interação com todos os aplicativos personalizados é bloqueada para sua organização. Os aplicativos personalizados não podem ser carregados por ninguém, exceto um Administrador de Serviço do Teams ou um administrador global. Você pode usar o PowerShell para remover o aplicativo personalizado.   |
| Desabilitado     | Desabilitado     | Habilitado        |A interação com todos os aplicativos personalizados é bloqueada para sua organização. Os aplicativos personalizados não podem ser carregados por ninguém, exceto um Administrador de Serviço do Teams ou um administrador global. Você pode usar o PowerShell para remover o aplicativo personalizado.         |
| Desabilitado    | Habilitado        | Desabilitado        |A interação com todos os aplicativos personalizados é bloqueada para sua organização. Os aplicativos personalizados não podem ser carregados por ninguém, exceto um Administrador de Serviço do Teams ou um administrador global. Você pode usar o Windows PowerShell para excluir aplicativos personalizados.         |
| Desabilitado    | Habilitado      | Habilitado       |A interação com todos os aplicativos personalizados é bloqueada para sua organização. Os aplicativos personalizados não podem ser carregados por ninguém, exceto um Administrador de Serviço do Teams ou um administrador global. Você pode usar o PowerShell para remover o aplicativo personalizado.         |
| Habilitado    | Desabilitado       | Desabilitado         |  O usuário não pode carregar aplicativos personalizados.      |
| Habilitado     | Desabilitado       | Habilitado         | Se o usuário for um proprietário de equipe, ele poderá carregar aplicativos personalizados para a equipe. Se o usuário não for um proprietário de equipe, ele não poderá carregar aplicativos personalizados para a equipe. O usuário pode carregar aplicativos personalizados no contexto pessoal.     |
| Habilitado     | Habilitado     | Desabilitado         | O usuário não pode carregar aplicativos personalizados.       |
| Habilitado    | Habilitado        | Habilitado        | O usuário pode carregar aplicativos personalizados para a equipe, independentemente de o usuário ser o proprietário da equipe. O usuário pode carregar aplicativos personalizados no contexto pessoal.       |

## <a name="related-topics"></a>Tópicos relacionados
 
[Configurações de administrador para aplicativos no Teams](admin-settings.md)

[Atribua políticas a seus usuários no Teams](assign-policies.md)