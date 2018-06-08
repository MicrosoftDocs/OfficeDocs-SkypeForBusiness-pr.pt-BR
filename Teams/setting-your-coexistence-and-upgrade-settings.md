---
title: Definindo as configurações de coexistência
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: bjwhalen
description: Isso ajudará a selecionar o modo de coexistência e definir outras configurações de coexistência.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: b7d96c628744273906f4289f7b82aa4cf28e4216
ms.sourcegitcommit: 9dc1c9afccb1792611b6e6d60dfcf62302dbde81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2018
ms.locfileid: "19713036"
---
# <a name="setting-your-coexistence-settings"></a>Definindo as configurações de coexistência

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Quando você estiver atualizando seu Skype para os usuários corporativos usem equipes, você tem várias opções disponíveis para você para torná-la um processo direto para seus usuários. Você tem a opção para tornar a coexistência e atualizar as configurações para todos os usuários em sua organização ou você pode fazer alterações de configuração referentes a um único ou um conjunto de usuários em sua organização. Você pode encontrar mais lendo [Noções básicas sobre os modos de coexistência e atualização para Skype para equipes e de negócios](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md) para obter uma compreensão melhor dos tipos de modos que estão disponíveis para você.

## <a name="setting-your-upgrade-options-for-all-users-in-your-organization"></a>Definindo suas opções de atualização para todos os usuários em sua organização

![as equipes de logotipo-30x30.png](media/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**

1. No painel de navegação esquerdo, vá para **configurações de toda a organização** > **equipes de atualização**. 

2. Na parte superior da página **página atualização de equipes** , faça as seguintes alterações se eles funcionará para você.
- Definir o modo de **coexistência**
    - **Ilhas** - use esta configuração quando você tem alguns usuários em Skype para alguns usuários que usam equipes e de negócios.
    - **Skype para negócios apenas** - use esta configuração se você tiver apenas Skype para usuários comerciais.
    - **Equipes apenas** - use esta configuração se você tiver apenas os usuários de equipes.
- Definir **Skype notificar para usuários comerciais que às equipes está disponível para atualização.**
    - Se você ativar isso, ele informará o Skype para usuários corporativos que podem ser atualizados para o aplicativo de equipes.
- Defina o **aplicativo preferencial para os usuários ingressem Skype para reuniões de negócios** essa configuração determina qual app é usado para ingressar em Skype para reuniões de negócios e é respeitada independente do valor do modo de coexistência.
    - **Reuniões do Skype app (padrão)**
    - **Skype for Business com os recursos limitados**
- Defina se para **baixar o aplicativo de equipes em segundo plano para Skype para usuários comerciais** esta configuração silenciosamente baixa o aplicativo de equipes para usuários que executam o Skype for Business no Windows. Ela é respeitada somente se o modo de coexistência para o usuário é apenas para equipes ou se as notificações de atualização pendente estão habilitadas no Skype para negócios.
3. Clique em **Salvar** depois de fazer as alterações.

## <a name="setting-your-upgrade-options-for-a-user-in-your-organization"></a>Definindo suas opções de atualização para um usuário em sua organização

![as equipes de logotipo-30x30.png](media/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**

1. No painel de navegação esquerdo, vá para **usuários** , em seguida, selecione o usuário na lista. 
2. Na guia **conta** para o usuário, na seção **Atualizar equipes** , clique em **Editar**.
- Você pode definir o modo de **coexistência** . Escolha entre as seguintes opções:
    - **Configurações de todo o uso Org** Use esta configuração se quiser que o usuário utilize as configurações nas configurações de **toda a organização** . Se você escolher essa opção, você não pode selecionar notificações para o usuário.
    - **Ilhas** - Use essa configuração quando você tiver alguns usuários no Skype para alguns usuários que usam equipes e de negócios. Se você escolher essa opção, você pode habilitar notificações para o usuário, ativando a opção **notificar o Skype para o usuário de negócios** . Ela informa o Skype para usuário de negócios que eles podem atualizar para o aplicativo de equipes.
    - **Skype para negócios apenas** - Use esta configuração se tiver apenas Skype para usuários comerciais. Se você escolher essa opção, você pode habilitar notificações para o usuário, ativando a opção **notificar o Skype para o usuário de negócios** . Ela informa o Skype para usuário de negócios que eles podem atualizar para o aplicativo de equipes.
    - **Equipes apenas** - use esta configuração se você tiver apenas os usuários de equipes. Se você escolher essa opção, você pode habilitar notificações para o usuário, ativando a opção **notificar o Skype para o usuário de negócios** . Ela informa o Skype para usuário de negócios que eles podem atualizar para o aplicativo de equipes.
3. Clique em **Salvar** depois de fazer as alterações.

### <a name="related-topics"></a>Tópicos relacionados
[Planejar a jornada](upgrade-plan-journey.md)
[entender a coexistência e atualizar modos para Skype para equipes e de negócios](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)