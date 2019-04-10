---
title: Gerencie políticas de aplicativo personalizado e as configurações no Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/18/2019
ms.reviewer: akino
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como gerenciar políticas de aplicativo personalizado e configurações para controlar quem pode carregar os aplicativos personalizados Teams da Microsoft em sua organização.
ms.openlocfilehash: 3cbd517cdfe8066eebff0164457c8e2e3aa37a5d
ms.sourcegitcommit: 9bb2bfd09ca279752dbedf17911ea46568649c4a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2019
ms.locfileid: "31749753"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a>Gerencie políticas de aplicativo personalizado e as configurações no Microsoft Teams

> [!INCLUDE [feature coming soon](includes/new-feature-coming-soon-article.md)]

Como um administrador, você pode usar políticas de aplicativo personalizado e configurações para controlar quem pode carregar os aplicativos personalizados para o Microsoft Teams em sua organização. Admins decida quais usuários podem carregar os aplicativos personalizados e proprietários de equipe e os administradores podem determinar se as equipes específicas em sua organização permitir que aplicativos personalizados a serem adicionados a eles.  

## <a name="overview-of-custom-apps"></a>Visão geral dos aplicativos personalizados

Os usuários podem adicionar um aplicativo personalizado às equipes carregando um pacote de aplicativos (em um arquivo. zip) diretamente para uma equipe ou o contexto de pessoal. Isso é diferente de como os aplicativos são adicionados por meio da loja de app equipes. Adicionar um aplicativo personalizado carregando um pacote de aplicativos, também conhecido como sideloading, permite que você teste a um aplicativo conforme ele está sendo desenvolvido, antes que ele esteja pronto para ser amplamente distribuída. Ele também permite que você crie um aplicativo somente para uso interno e compartilhá-las com sua equipe sem enviá-la ao catálogo de aplicativos equipes na app store equipes.

![carregar um aplicativo personalizado](media/teams-custom-app-policy-and-settings-upload-app.png)

## <a name="custom-app-policy-and-settings"></a>As configurações e diretivas de aplicativo personalizado

Três componentes determinam se um usuário pode carregar um aplicativo personalizado para uma equipe, proporcionando controle granular quem pode adicionar aplicativos personalizados para uma equipe e que as equipes de aplicativos personalizados podem ser adicionados a:

- [Política de aplicativo personalizado do usuário](#user-custom-app-policy)
- [Configuração de aplicativo personalizado de equipe](#team-custom-app-setting)
- [Configuração de aplicativo personalizado de toda a organização](#org-wide-custom-app-setting)

Essas configurações não afetam a capacidade de bloquear aplicativos de terceiros.  

### <a name="user-custom-app-policy"></a>Política de aplicativo personalizado do usuário

Como parte das [políticas de configuração de aplicativo](teams-app-setup-policies.md), os administradores podem usar uma configuração de política, **Permitir que aplicativos personalizados de carregamento**, para controlar se um usuário pode carregar os aplicativos personalizados para equipes.
 
Se essa configuração estiver desativada:

- O usuário não pode carregar um aplicativo personalizado para qualquer equipe em sua organização ou no contexto pessoal.
- O usuário pode interagir com os aplicativos personalizados, dependendo da configuração de aplicativo personalizado de toda a organização.

Se essa configuração estiver ativada:

- O usuário pode carregar os aplicativos personalizados para equipes que permitem e equipes pelas quais são proprietários, dependendo da configuração de aplicativo personalizado de toda a organização.
- O usuário pode carregar aplicativos personalizados para o contexto de pessoal. 
- O usuário pode interagir com os aplicativos personalizados, dependendo da configuração de aplicativo personalizado de toda a organização.

Você pode editar as configurações na diretiva de instalação de app global para incluir os aplicativos que você deseja. Se você desejar personalizar equipes para diferentes grupos de usuários em sua organização, crie e atribua uma ou mais políticas de configuração de aplicativo personalizado.

#### <a name="set-a-user-custom-app-policy"></a>Definir uma política de aplicativo personalizado do usuário

1. No painel de navegação à esquerda do Centro de administração do Microsoft Teams, vá para **equipes apps** > **políticas de instalação**.
2. Selecione **nova política**.
3. Ativar ou desativar **Permitir carregamento aplicativos personalizados**.
4. Escolha qualquer outra configuração que você deseja para a política.
5. Clique em **Salvar**.

### <a name="team-custom-app-setting"></a>Configuração de aplicativo personalizado de equipe

Proprietários de equipe e os administradores podem controlar se uma equipe permite aplicativos personalizados a ser adicionado a ela. Essa configuração, **Permitir que os membros para carregar os aplicativos personalizados**, junto com a política de aplicativo personalizado de um usuário determina quem pode adicionar aplicativos personalizados para uma determinada equipe.
 
Se essa configuração estiver desativada:

- Os proprietários de equipe podem adicionar aplicativos personalizados, se sua política de aplicativo personalizado permitir.
- Membros da equipe que não são proprietários de equipe não podem adicionar aplicativos personalizados para a equipe.

Se essa configuração estiver ativada:

- Os proprietários de equipe podem adicionar aplicativos personalizados, se sua política de aplicativo personalizado permite a ele.
- Membros da equipe que não são proprietários da equipe podem adicionar aplicativos personalizados, se sua política de aplicativo personalizado permite a ele.

#### <a name="configure-the-team-custom-app-setting"></a>Configurar a definição de aplicativo personalizado de equipe

1. Em equipes, vá para a equipe, clique em **mais ˙˙˙ de opções** > **equipe gerenciar**.
2. Clique em **configurações**e, em seguida, expanda **permissões de membro**.
3. Marque ou desmarque a caixa de seleção **Permitir que os membros para carregar os aplicativos personalizados** .

    ![configuração de aplicativo personalizado de equipe](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a>Configuração de aplicativo personalizado de toda a organização

A definição de aplicativo personalizado de toda a organização, **Permitir a interação com aplicativos personalizados**, se aplica a todas as pessoas na sua organização e rege se eles podem carregar ou interagem com aplicativos personalizados. Essa configuração substitui o usuário e a diretiva de aplicativo personalizado de equipe e a configuração. Ele foi projetado para servir como um mestre chave liga/desliga durante os eventos de segurança.

#### <a name="configure-the-org-wide-custom-app-setting"></a>Configurar a definição de aplicativo personalizado de toda a organização

1. No painel de navegação à esquerda do Centro de administração do Microsoft Teams, vá para **equipes apps** > **políticas de permissão**.
2. Clique em **configurações do aplicativo de toda a organização**.
3. Em **aplicativos personalizados**, ativar ou desativar **Permitir a interação com aplicativos personalizados**.

    ![Configuração de aplicativo personalizado de toda a organização](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a>Como o aplicativo personalizado políticas e configurações trabalham juntos

Esta tabela resume a política de aplicativo personalizado e configurações, como eles funcionam juntos e seu efeito combinado sobre como controlar quem na sua organização pode carregar os aplicativos personalizados para equipes.

Digamos, por exemplo, para permitir que somente os proprietários de equipe carregar os aplicativos personalizados para equipes específicas. Defina o seguinte:
- Ative a configuração **Permitir a interação com aplicativos personalizados** no Centro de administração do Microsoft Teams.
- Desative a **Permitir que os membros para carregar os aplicativos personalizados** para cada equipe ao qual você deseja restringir o acesso.
- Criar e atribuir uma política de instalação de aplicativo personalizado no Centro de administração do Microsoft Teams com a configuração do **usuário pode carregar os aplicativos personalizados** ativada e atribuí-lo para os proprietários de equipe.

|Configuração de aplicativo personalizado de toda a organização |Configuração de aplicativo personalizado de equipe |Política de aplicativo personalizado do usuário |Efeito  |
|---------|---------|---------|---------|
| Desativado    | Desativado    | Desativado     |Interação com todos os aplicativos personalizados seja bloqueada em sua organização. Aplicativos personalizados não podem ser carregados por qualquer pessoa. Você pode usar o PowerShell para remover o aplicativo personalizado.   |
| Desativado     | Desativado     | Ativado        |Interação com todos os aplicativos personalizados seja bloqueada em sua organização. Aplicativos personalizados não podem ser carregados por qualquer pessoa. Você pode usar o PowerShell para remover o aplicativo personalizado.         |
| Desativado    | Ativado        | Desativado        |Interação com todos os aplicativos personalizados seja bloqueada em sua organização. Aplicativos personalizados não podem ser carregados por qualquer pessoa. Você pode usar o Windows PowerShell para excluir os aplicativos personalizados.         |
| Desativado    | Ativado      | Ativado       |Interação com todos os aplicativos personalizados seja bloqueada em sua organização. Aplicativos personalizados não podem ser carregados por qualquer pessoa. Você pode usar o PowerShell para remover o aplicativo personalizado.         |
| Ativado    | Desativado       | Desativado         |  O usuário não pode carregar os aplicativos personalizados.      |
| Ativado     | Desativado       | Ativado         | Se o usuário for um proprietário de equipe, poderão carregar aplicativos personalizados para a equipe. Se o usuário não for um proprietário de equipe, eles não podem carregar os aplicativos personalizados para a equipe. O usuário pode carregar os aplicativos personalizados no contexto pessoal.     |
| Ativado     | Ativado     | Desativado         | O usuário não pode carregar os aplicativos personalizados.       |
| Ativado    | Ativado        | Ativado        | O usuário pode carregar os aplicativos personalizados para a equipe, independentemente se o usuário é um proprietário de equipe. O usuário pode carregar os aplicativos personalizados no contexto pessoal.       |

 ## <a name="related-topics"></a>Tópicos relacionados
- [Configurações de administração para aplicativos no Teams](admin-settings.md)
- [Gerenciar políticas de configuração de aplicativo no Microsoft Teams](teams-app-setup-policies.md)
- [Gerenciar políticas de permissões de aplicativo no Microsoft Teams](teams-app-permission-policies.md)
