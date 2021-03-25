---
title: Gerenciar configurações do Skype for Business no centro de administração do Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection: ''
f1.keywords:
- CSH
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.overview
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.presence
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.skypemeetingbroadcast
- ms.teamsadmincenter.users.skypeforbusiness.settings
ms.custom: ''
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como gerenciar configurações para recursos do Skype for Business no centro de administração do Microsoft Teams.
ms.openlocfilehash: 6e1052b4f4a0e85d4d18123b3c0a0f051f6065f8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116999"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a>Gerenciar configurações do Skype for Business no centro de administração do Microsoft Teams

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-settings"> </a>
<!-- Do not remove the bookmark link above. -->

Como administrador, o Centro de administração do Microsoft Teams é onde você gerencia os recursos do Skype for Business para usuários do Skype for Business em sua organização. Você pode gerenciar configurações [para](#manage-skype-for-business-settings-for-your-organization) sua organização na página **Skype for Business** e configurações para usuários individuais na guia Skype for **Business** de páginas de detalhes do usuário. [](#manage-skype-for-business-settings-for-individual-users)

Você só verá a página **do Skype for Business** se o modo de coexistência da sua organização não estiver definido apenas como **Teams**. Da mesma forma, você só verá a guia **Skype for Business** para um usuário se o modo de coexistência do usuário não for apenas o **Teams.** Para saber mais sobre modos de coexistência, consulte [Understand Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and Set your [coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).

> [!NOTE]
> As configurações do Skype for Business estavam anteriormente **no portal herdado** no centro de administração do Microsoft Teams. Com a reforma do portal herdada, migramos as configurações para esses novos locais no Centro de administração do Teams para gerenciamento do Skype for Business.

Você deve ter a função de administrador do [Azure AD](/azure/active-directory/roles/permissions-reference) de administrador global ou administrador do Skype for Business para gerenciar recursos do Skype for Business no centro de administração do Microsoft Teams.

## <a name="manage-skype-for-business-settings-for-your-organization"></a>Gerenciar configurações do Skype for Business para sua organização

Na navegação à esquerda do Centro de administração do Microsoft Teams, acesse **Configurações** em toda a organização  >  **Skype for Business**. A partir daqui, você pode configurar e gerenciar a Transmissão de Reunião do Skype, privacidade de presença e notificações de dispositivo móvel para todos os usuários do Skype for Business em sua organização.

### <a name="skype-meeting-broadcast"></a>Transmissão de Reunião do Skype

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-broadcast"> </a>
<!-- Do not remove the bookmark link above. -->

Use as configurações a seguir para gerenciar [a Transmissão de Reunião do Skype](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) em sua organização.

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="Captura de tela das configurações de Transmissão de Reunião do Skype no centro de administração":::

- **Transmissões de reunião do Skype**: ative isso para habilitar a Transmissão de Reunião do Skype para sua organização. Depois de habilitar esse recurso, você precisará [configurar sua rede para Transmissão de Reunião do Skype.](/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast)
- **Consulte recursos de visualização**: a ligue isso para obter acesso antecipado aos novos recursos.
- **Os organizadores podem agendar** reuniões anônimas : a ligue se você quiser permitir que os organizadores criem eventos de transmissão que permitem que qualquer pessoa de fora da sua organização participe sem precisar entrar. 
- **Gravar reuniões de Transmissão de Reunião do Skype**: ative isso para permitir que organizadores e apresentadores gravem reuniões.  
- URL de suporte do **Helpdesk** para participantes : Insira a URL de suporte da sua organização que os participantes da reunião podem usar se eles precisarem de ajuda durante uma reunião.

### <a name="presence-and-mobile-notifications"></a>Notificações de presença e dispositivos móveis

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-presence-mobile"> </a>
<!-- Do not remove the bookmark link above. -->


Use as configurações a seguir para gerenciar a privacidade de presença do Skype for Business e notificações móveis em sua organização.

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="Captura de tela das configurações de presença no centro de administração":::

#### <a name="presence"></a>Presença

Por padrão, os usuários do Skype for Business em sua organização podem ver o status de presença (como Available, Busy ou Away) de outros usuários do Skype for Business. Escolha um dos seguintes para definir quem pode ver a presença de seus usuários do Skype for Business.

- **Exibir automaticamente informações** de presença : qualquer usuário do Skype for Business  em  sua organização que não tenha sido adicionado à lista Externa ou Bloqueada do usuário pode ver a presença desse usuário.
- **Exibir informações** de presença somente para os contatos de um usuário : Qualquer usuário do Skype  for  Business na lista contatos do usuário que não seja adicionado à sua lista Externa ou Bloqueada pode ver a presença desse usuário. Os usuários podem substituir essa configuração no Skype for Business, indo para **Opções de Ferramentas**  >  **de**  >  **Configurações.**

#### <a name="mobile-notifications"></a>Notificações móveis

Você pode definir se os usuários móveis do Skype for Business receberão alertas sobre mensagens instantâneas recebidas e perdidas, mensagens de caixa postal e chamadas perdidas por meio de um serviço de notificação por push. Dependendo dos dispositivos móveis usados em sua organização, você pode usar o Serviço de Notificação por Push da **Microsoft**, o Serviço de Notificação por Push da **Apple** ou ambos.

Considere o seguinte:

- Se você desativar as notificações por push, os usuários receberão todos os alertas na próxima vez que iniciarem o Skype for Business em seu dispositivo móvel.
- Por padrão, as notificações por push são ativas. Usuários individuais podem desativar no Skype for Business em seus dispositivos móveis.
- Quando você desativa as notificações push, os usuários não podem ativá-las. 

> [!IMPORTANT]
> [!IMPORTANTE] A Microsoft usa outras empresas para fornecer notificações por celular para o Skype for Business em tempo real para os usuários do Windows Phone, iPhone e iPad. Consulte esta [Declaração de Privacidade](https://go.microsoft.com/fwlink/p/?linkid=247732).

## <a name="manage-skype-for-business-settings-for-individual-users"></a>Gerenciar configurações do Skype for Business para usuários individuais

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-user-settings"> </a>
<!-- Do not remove the bookmark link above. -->

Para gerenciar as configurações do Skype for Business para usuários individuais, na navegação à esquerda do Centro de administração do Teams, vá para **Usuários**, clique no nome de exibição do usuário para abrir a página de detalhes do usuário e selecione a guia **Configurações do Skype for Business.** A partir daqui, você pode configurar configurações de acesso externo e reunião para o usuário.

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="Captura de tela da guia Skype for Business na página de detalhes do usuário":::

### <a name="external-access-settings"></a>Configurações de acesso externo

Você pode permitir ou bloquear seletivamente se um usuário pode se comunicar com pessoas de fora da sua organização.

- **Usuários externos do Skype for Business**: ativos se você quiser permitir que o usuário se comunique com usuários do Skype for Business em domínios federados.
- **Usuários externos do Skype**: ativos se você quiser permitir que o usuário se comunique com os usuários do Skype. 

### <a name="meeting-settings"></a>Configurações de reunião

Você pode definir as seguintes configurações de reunião para o usuário.

- **Vídeo & áudio**: escolha uma das seguintes configurações de áudio e vídeo:

    - **Nenhum**: o usuário não pode usar áudio ou vídeo.
    - **Somente áudio**: o usuário pode usar áudio, mas não vídeo.
    - **Áudio e vídeo:** o usuário pode usar áudio e vídeo.
    - **Áudio e vídeo (HD)**: O usuário pode usar áudio e vídeo de alta definição.
    
- **Gravar conversas & reuniões**: a ligue para permitir que o usuário grave conversas e reuniões.
- **Conformidade**: a ligue se você for legalmente necessário para reter informações armazenadas eletronicamente.