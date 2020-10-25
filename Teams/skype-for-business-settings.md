---
title: Gerenciar as configurações do Skype for Business no centro de administração do Microsoft Teams
author: lanachin
ms.author: v-lanac
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
description: Saiba como gerenciar as configurações dos recursos do Skype for Business no centro de administração do Microsoft Teams.
ms.openlocfilehash: 18f1de99964a36485e69a210c71b6350313aa1cb
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753556"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a>Gerenciar as configurações do Skype for Business no centro de administração do Microsoft Teams

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-settings"> </a>
<!-- Do not remove the bookmark link above. -->

Como administrador, o centro de administração do Microsoft Teams é onde você gerencia os recursos do Skype for Business para os usuários do Skype for Business em sua organização. Você pode gerenciar as configurações [de sua organização](#manage-skype-for-business-settings-for-your-organization) na página do **Skype for Business** e as configurações [para usuários individuais](#manage-skype-for-business-settings-for-individual-users) na guia **Skype for Business** de páginas de detalhes do usuário.

Você só verá a página do **Skype for Business** se o modo de coexistência de sua organização não estiver definido **somente como Teams**. Da mesma forma, você só verá a guia **Skype for Business** para um usuário se o modo de coexistência do usuário não for **somente de equipe**. Para saber mais sobre os modos de coexistência, consulte [entender equipes e a coexistência e interoperabilidade do Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md) e [definir suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md).

> [!NOTE]
> As configurações do Skype for Business estavam anteriormente no **portal herdado** no centro de administração do Microsoft Teams. Com o descontinuação do portal herdado, migramos as configurações para esses novos locais no centro de administração do teams para gerenciamento do Skype for Business.

Você deve receber a função de administrador global do [Azure ad](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) ou administrador do Skype for Business para gerenciar os recursos do Skype for Business no centro de administração do Microsoft Teams.

## <a name="manage-skype-for-business-settings-for-your-organization"></a>Gerenciar as configurações do Skype for Business para sua organização

Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **configurações de toda a organização**  >  **Skype for Business**. A partir daqui, você pode configurar e gerenciar a transmissão de reunião do Skype, a privacidade de presença e as notificações de dispositivos móveis para todos os usuários do Skype for Business em sua organização.

### <a name="skype-meeting-broadcast"></a>Transmissão de Reunião do Skype

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-broadcast"> </a>
<!-- Do not remove the bookmark link above. -->

Use as configurações a seguir para gerenciar a [transmissão de reunião do Skype](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) em sua organização.

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="Captura de tela das configurações de transmissão de reunião do Skype no centro de administração":::

- **Transmissões de reunião do Skype**: Ative esta opção para habilitar a transmissão de reunião do Skype para sua organização. Depois de habilitar esse recurso, você precisará [configurar sua rede para a transmissão de reunião do Skype](https://docs.microsoft.com/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast).
- **Consulte recursos de visualização**: ative esse recurso para obter acesso antecipado aos novos recursos.
- Os **organizadores podem agendar reuniões anônimas**: Ative esta opção se quiser que os organizadores criem eventos de transmissão que permitam que qualquer pessoa de fora da sua organização ingresse sem precisar entrar. 
- **Grave reuniões de transmissão de reunião do Skype**: Ative esta opção para habilitar os organizadores e apresentadores para gravar reuniões.  
- **URL de suporte da assistência técnica para participantes**: digite a URL de suporte da sua organização que os participantes da reunião poderão usar se precisarem de ajuda durante uma reunião.

### <a name="presence-and-mobile-notifications"></a>Presença e notificações móveis

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-presence-mobile"> </a>
<!-- Do not remove the bookmark link above. -->


Use as configurações a seguir para gerenciar a privacidade de presença do Skype for Business e as notificações do celular em sua organização.

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="Captura de tela das configurações de presença no centro de administração":::

#### <a name="presence"></a>Presença

Por padrão, os usuários do Skype for Business em sua organização podem ver o status de presença (como disponível, ocupado ou ausente) de outros usuários do Skype for Business. Escolha uma das opções a seguir para definir quem pode ver a presença de seus usuários do Skype for Business.

- **Exibir automaticamente as informações de presença**: qualquer usuário do Skype for Business em sua organização que não tenha sido adicionado à lista **externa** ou **bloqueada** do usuário poderá ver a presença do usuário.
- **Exibir informações de presença somente para os contatos de um usuário**: qualquer usuário do Skype for Business na lista de contatos do usuário que não é adicionado à lista **externa** ou **bloqueada** pode ver a presença do usuário. Os usuários podem substituir essa configuração no Skype for Business indo até **configurações**  >  **ferramentas**  >  **Opções**.

#### <a name="mobile-notifications"></a>Notificações de celular

Você pode definir se seus usuários móveis do Skype for Business recebem alertas sobre mensagens instantâneas recebidas e perdidas, mensagens de correio de voz e chamadas perdidas por meio de um serviço de notificação por push. Dependendo dos dispositivos móveis usados em sua organização, você pode usar o serviço de **notificação por push da Microsoft**, o **serviço de notificação por push da Apple**ou ambos.

Considere o seguinte:

- Se você desativar as notificações por push, os usuários receberão todos os alertas da próxima vez que iniciarem o Skype for Business em seu dispositivo móvel.
- Por padrão, as notificações por push estão ativadas. Usuários individuais podem desativá-los no Skype for Business em seu dispositivo móvel.
- Quando você desativa as notificações push, os usuários não podem ativá-las. 

> [!IMPORTANT]
> [!IMPORTANTE] A Microsoft usa outras empresas para fornecer notificações por celular para o Skype for Business em tempo real para os usuários do Windows Phone, iPhone e iPad. Consulte esta [política de privacidade](https://go.microsoft.com/fwlink/p/?linkid=247732).

## <a name="manage-skype-for-business-settings-for-individual-users"></a>Gerenciar as configurações do Skype for Business para usuários individuais

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-user-settings"> </a>
<!-- Do not remove the bookmark link above. -->

Para gerenciar as configurações do Skype for Business para usuários individuais, na navegação à esquerda do centro de administração do Teams, vá para **usuários**, clique no nome de exibição do usuário para abrir a página de detalhes do usuário e, em seguida, selecione a guia **configurações do Skype for Business** . Aqui, você pode configurar o acesso externo e as configurações de reunião para o usuário.

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="Captura de tela da guia do Skype for Business na página de detalhes do usuário":::

### <a name="external-access-settings"></a>Configurações de acesso externo

Você pode permitir ou bloquear seletivamente se um usuário pode se comunicar com pessoas de fora da sua organização.

- **Usuários externos do Skype for Business**: Ative esta opção se quiser permitir que o usuário se comunique com usuários do Skype for Business em domínios federados.
- **Usuários externos do Skype**: Ative esta opção se quiser permitir que o usuário se comunique com usuários do Skype. 

### <a name="meeting-settings"></a>Configurações de reunião

Você pode definir as seguintes configurações de reunião para o usuário.

- **Áudio & vídeo**: escolha uma das seguintes configurações de áudio e vídeo:

    - **None**: o usuário não pode usar áudio ou vídeo.
    - **Somente áudio**: o usuário pode usar áudio, mas não vídeo.
    - **Áudio e vídeo**: o usuário pode usar áudio e vídeo.
    - **Áudio e vídeo (HD)**: o usuário pode usar áudio e vídeo de alta definição.
    
- **Grave conversas & reuniões**: Ative esta opção para permitir que o usuário grave conversas e reuniões.
- **Conformidade**: Ative esta opção se você for obrigado legalmente a reter informações armazenadas eletronicamente. 
