---
title: Gerenciar Skype for Business configurações no Microsoft Teams de administração
author: cichur
ms.author: v-mahoffman
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
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba como gerenciar configurações para Skype for Business recursos no centro de administração Microsoft Teams de administração.
ms.openlocfilehash: 90748d968b2540ea6ee7e5c542623ceb0bc0fbb1
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767129"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a>Gerenciar Skype for Business configurações no Microsoft Teams de administração

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-settings"> </a>
<!-- Do not remove the bookmark link above. -->

Como administrador, o Microsoft Teams de administração é onde você gerencia Skype for Business recursos para Skype for Business usuários em sua organização. Você pode gerenciar configurações [para](#manage-skype-for-business-settings-for-your-organization) sua organização na página Skype for Business e configurações para usuários [individuais](#manage-skype-for-business-settings-for-individual-users) **na** guia Skype for Business de páginas de detalhes do usuário. 

Você só verá a página **Skype for Business** se o modo de coexistência da sua organização não estiver definido como Teams **somente**. Da mesma forma, você só verá a guia **Skype for Business** para um usuário se o modo de coexistência do usuário não for Teams **somente**. Para saber mais sobre modos de coexistência, consulte [Understand Teams and Skype for Business coexistence](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and interoperability e Set your [coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).

> [!NOTE]
> Skype for Business configurações estavam anteriormente no **portal herdado** no Microsoft Teams de administração. Com a reforma do portal herdado, migramos as configurações para esses novos locais no centro de administração Teams para Skype for Business gerenciamento.

Você deve ter a função de administrador do [Azure AD](/azure/active-directory/roles/permissions-reference) de administrador global ou Skype for Business para gerenciar Skype for Business recursos no centro de administração do Microsoft Teams.

## <a name="manage-skype-for-business-settings-for-your-organization"></a>Gerenciar Skype for Business configurações da sua organização

Na navegação à esquerda do centro de administração Microsoft Teams, vá para **Configurações** de toda  >  **a organização Skype for Business**. A partir daqui, você pode configurar e gerenciar Reunião do Skype de transmissão, privacidade de presença e notificações de dispositivo móvel para todos os Skype for Business usuários em sua organização.

### <a name="skype-meeting-broadcast"></a>Transmissão de Reunião do Skype

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-broadcast"> </a>
<!-- Do not remove the bookmark link above. -->

Use as configurações a seguir para gerenciar [Reunião do Skype Transmissão](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) em sua organização.

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="Captura de tela de Reunião do Skype configurações de transmissão no centro de administração.":::

- **Reunião do Skype Transmissões**: ative isso para habilitar Reunião do Skype Transmissão para sua organização. Depois de habilitar esse recurso, você precisará [configurar sua rede para Reunião do Skype Transmissão](/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast).
- **Consulte recursos de visualização**: a ligue isso para obter acesso antecipado aos novos recursos.
- **Os organizadores podem agendar** reuniões anônimas : a ligue se você quiser permitir que os organizadores criem eventos de transmissão que permitem que qualquer pessoa de fora da sua organização participe sem precisar entrar. 
- **Registro Reunião do Skype Reuniões de transmissão**: ative isso para permitir que organizadores e apresentadores gravem reuniões.  
- URL de suporte do **Helpdesk** para participantes : Insira a URL de suporte da sua organização que os participantes da reunião podem usar se eles precisarem de ajuda durante uma reunião.

### <a name="presence-and-mobile-notifications"></a>Notificações de presença e dispositivos móveis

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-presence-mobile"> </a>
<!-- Do not remove the bookmark link above. -->


Use as configurações a seguir para gerenciar Skype for Business privacidade de presença e notificações móveis em sua organização.

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="Captura de tela das configurações de presença no centro de administração.":::

#### <a name="presence"></a>Presença

Por padrão, Skype for Business usuários em sua organização podem ver o status de presença (como Available, Busy ou Away) de outros Skype for Business usuários. Escolha um dos seguintes para definir quem pode ver a presença de seus Skype for Business usuários.

- **Exibir automaticamente informações** de presença : qualquer usuário Skype for Business em sua organização  que  não tenha sido adicionado à lista Externa ou Bloqueada do usuário pode ver a presença desse usuário.
- **Exibir informações** de presença somente para os contatos de um usuário : qualquer usuário Skype for Business na lista  contatos  do usuário que não seja adicionado à sua lista Externa ou Bloqueada pode ver a presença desse usuário. Os usuários podem substituir essa configuração no Skype for Business, Configurações  >  **Opções de**  >  **Ferramentas.**

#### <a name="mobile-notifications"></a>Notificações móveis

Você pode definir se seus usuários Skype for Business móveis receberão alertas sobre mensagens instantâneas recebidas e perdidas, mensagens de caixa postal e chamadas perdidas por meio de um serviço de notificação por push. Dependendo dos dispositivos móveis usados em sua organização, você pode usar o Serviço de Notificação por Push da **Microsoft**, o Serviço de Notificação por Push da **Apple** ou ambos.

Considere o seguinte:

- Se você desativar as notificações por push, os usuários receberão todos os alertas na próxima vez que Skype for Business em seu dispositivo móvel.
- Por padrão, as notificações por push são ativas. Os usuários individuais podem a Skype for Business-los em seus dispositivos móveis.
- Quando você desativa as notificações push, os usuários não podem ativá-las. 

> [!IMPORTANT]
> [!IMPORTANTE] A Microsoft usa outras empresas para fornecer notificações por celular para o Skype for Business em tempo real para os usuários do Windows Phone, iPhone e iPad. Consulte esta [Declaração de Privacidade](https://go.microsoft.com/fwlink/p/?linkid=247732).

## <a name="manage-skype-for-business-settings-for-individual-users"></a>Gerenciar Skype for Business configurações para usuários individuais

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-user-settings"> </a>
<!-- Do not remove the bookmark link above. -->

Para gerenciar Skype for Business configurações de usuários individuais, na navegação à esquerda do centro de administração do Teams, vá para **Usuários**, clique no nome de exibição do usuário para abrir a página de detalhes do usuário e selecione Skype for Business **guia** de configurações do Skype for Business. A partir daqui, você pode configurar configurações de acesso externo e reunião para o usuário.

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="Captura de tela Skype for Business guia na página de detalhes do usuário.":::

### <a name="external-access-settings"></a>Configurações de acesso externo

Você pode permitir ou bloquear seletivamente se um usuário pode se comunicar com pessoas de fora da sua organização.

- **Usuários Skype for Business externos**: ata isso se você quiser permitir que o usuário se comunique com Skype for Business usuários em domínios federados.
- **Usuários Skype externos**: ativos se você quiser permitir que o usuário se comunique com Skype usuários. 

### <a name="meeting-settings"></a>Configurações de reunião

Você pode definir as seguintes configurações de reunião para o usuário.

- **Vídeo & áudio**: escolha uma das seguintes configurações de áudio e vídeo:

    - **Nenhum**: o usuário não pode usar áudio ou vídeo.
    - **Somente áudio**: o usuário pode usar áudio, mas não vídeo.
    - **Áudio e vídeo:** o usuário pode usar áudio e vídeo.
    - **Áudio e vídeo (HD)**: O usuário pode usar áudio e vídeo de alta definição.
    
- **Gravar conversas & reuniões**: a ligue para permitir que o usuário grave conversas e reuniões.
- **Conformidade**: a ligue se você for legalmente necessário para reter informações armazenadas eletronicamente.