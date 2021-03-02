---
title: Definir suas configurações de coexistência e atualização
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: bjwhalen
search.appverid: MET150
description: Saiba como definir as configurações de coexistência e atualização para todos os usuários da sua organização de uma só vez ou para um único ou conjunto de usuários em sua organização.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: c2dbeb4d93273aab848f1b4436b46e6b22e08e53
ms.sourcegitcommit: 79b19b326ef40bf04af03021a7c6506fdd9417ba
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2021
ms.locfileid: "50397566"
---
# <a name="set-your-coexistence-and-upgrade-settings"></a>Definir suas configurações de coexistência e atualização


Ao atualizar seus usuários do Skype for Business para usar o Teams, você tem várias opções para ajudá-lo a tornar um processo contínuo para seus usuários. Você tem a opção de fazer configurações de coexistência e atualização para todos os usuários em sua organização de uma só vez ou pode fazer alterações de configurações para um único ou conjunto de usuários em sua organização. Observe que as versões mais antigas dos clientes do Skype for Business podem não honrar essas configurações. Para obter mais informações sobre versões do cliente do Skype for Business, acesse a página Downloads e atualizações do [Skype for Business.](https://docs.microsoft.com/skypeforbusiness/software-updates) 

Você pode entender melhor os modos que estão disponíveis para você lendo Entender a [coexistência](teams-and-skypeforbusiness-coexistence-and-interoperability.md) e a interoperabilidade do Microsoft Teams e do Skype for Business ou coexistência com o [Skype for Business.](coexistence-chat-calls-presence.md)  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a>Definir opções de atualização para todos os usuários em sua organização

![Um ícone mostrando o logotipo do Microsoft Teams](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**

1. No centro [de administração do Microsoft Teams](https://admin.teams.microsoft.com/), na navegação à esquerda, acesse **Configurações** em toda a organização  >  **Atualização do Teams**. 

2. Na parte superior da página **de atualização do Teams,** modifique as opções a seguir conforme desejado.
    - De definir **o modo coexistência.**
        - **Ilhas** - Use essa configuração se quiser que os usuários sejam capazes de usar o Skype for Business e o Teams simultaneamente.
        - **Somente Skype for Business** - Use essa configuração se quiser que seus usuários usem apenas o Skype for Business.
        - **Colaboração do Skype for Business com o Teams** - Use essa configuração se quiser que os usuários usem o Skype for Business, além de usar o Teams para colaboração em grupo (canais).
        - **Colaboração e** reuniões do Skype for Business com o Teams - Use essa configuração se quiser que os usuários usem o Skype for Business, além de usar o Teams para colaboração em grupo (canais) e reuniões do Teams.
        - **Somente equipes** - Use essa configuração se quiser que seus usuários usem apenas o Teams. Observe que, mesmo com essa configuração, os usuários ainda podem participar de reuniões hospedadas no Skype for Business.
        
    - Definir **Notificar usuários do Skype for Business de que o Teams está disponível para atualização.** Se você ativar isso, ele dirá aos usuários do Skype for Business que eles serão atualizados em breve para o aplicativo do Teams.
    - De definir **o aplicativo Preferencial para que os usuários participem de reuniões do Skype for Business.** Essa configuração determina qual aplicativo é usado para ingressar em reuniões do Skype for Business e é atendida independentemente do valor do modo de coexistência.
      - **Aplicativo reuniões do Skype**
      - **Skype for Business com recursos limitados**
    - Definir se o aplicativo do Teams deve ser baixado em **segundo plano para usuários do Skype for Business.**  Essa configuração baixa silenciosamente o aplicativo do Teams para usuários que executam o Skype for Business no Windows. Ela só será atendida se o modo de coexistência do usuário for apenas o Teams ou se as notificações da atualização pendente estão habilitadas no Skype for Business.
3. Clique **em Salvar** depois de fazer suas alterações.

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a>Definir opções de atualização para um único usuário em sua organização

![Um ícone mostrando o logotipo do Microsoft Teams](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**

1. Na navegação à esquerda, vá para **Usuários** e selecione o usuário na lista. 
2. Na guia **Conta** do usuário, em Atualização **do Teams,** clique em **Editar**.
3. Você pode definir o **modo coexistência**. Escolha entre as seguintes opções:
     - **Use configurações em toda a** organização - Use essa configuração se quiser que o usuário use as configurações nas **configurações em** toda a organização. 
     - **Ilhas** - Use essa configuração se quiser que o usuário possa usar o Skype for Business e o Teams. 
     - **Somente Skype for Business** - Use essa configuração se quiser que o usuário use o Skype for Business.
     - **Colaboração do Skype for Business com o Teams** - Use essa configuração se quiser que o usuário use o Skype for Business, além de usar o Teams para colaboração em grupo (canais).
      - **Colaboração e** reuniões do Skype for Business com o Teams - Use essa configuração se quiser que o usuário use o Skype for Business, além de usar o Teams para colaboração em grupo (canais) e reuniões do Teams.
     - **Somente equipes** - Use essa configuração se você quiser que o usuário use apenas o Teams. O usuário ainda poderá participar de reuniões do Skype for Business.
4. Se você selecionar qualquer modo de **coexistência** diferente de Usar configurações em toda a **organização,** você terá a opção de habilitar notificações no aplicativo do Skype for Business do usuário que atualize para o Teams em breve. Você pode habilitar essa notificação para o usuário ativando a opção **Notificar o usuário do Skype for Business.**
5. Clique **em Salvar** depois de fazer suas alterações.

### <a name="related-topics"></a>Tópicos relacionados
[Planejar a jornada](upgrade-plan-journey.md)

[Compreender a coexistência e a jornada de atualização para o Skype for Business e o Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](migration-interop-guidance-for-teams-with-skype.md)
