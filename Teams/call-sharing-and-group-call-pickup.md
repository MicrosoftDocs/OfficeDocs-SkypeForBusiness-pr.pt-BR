---
title: Atendimento de chamada de grupo e compartilhamento de chamada
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.users.voice.groupcallpickup.tooltip
- ms.teamsadmincenter.users.voice.callorderanddelay.tooltip
- Phone System
- seo-marvel-mar2020
description: O compartilhamento de chamadas e o recebimento de chamadas em grupo permitem que os usuários compartilhem chamadas de entrada com colegas para que as chamadas possam ser capturadas quando o usuário não estiver disponível.
ms.openlocfilehash: 7f9e24114d47ff331ad36a653a2bbe0f31fcad08
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60014125"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a>Compartilhamento de chamadas e atendimento de chamada em grupo no Microsoft Teams

Os recursos de compartilhamento de chamadas e recebimento de chamadas em grupo do Microsoft Teams permitem que os usuários compartilhem suas chamadas de entrada com colegas para que os colegas possam atender chamadas que ocorrem enquanto o usuário não está disponível.

O recebimento de chamadas em grupo é menos prejudicial para destinatários do que outras formas de compartilhamento de chamadas (como encaminhamento de chamadas ou toque simultâneo) porque os usuários podem configurar como eles querem ser notificados de uma chamada compartilhada de entrada (por meio de notificação de áudio e visual, somente visual ou faixa no aplicativo do Teams) e eles podem decidir se a atenderão.

Para compartilhar chamadas com outras pessoas, um usuário cria um grupo de chamadas e adiciona os usuários com os que deseja compartilhar suas chamadas. Em seguida, eles escolhem um anel simultâneo ou uma configuração de encaminhamento. Consulte [Encaminhamento de chamada e toque simultâneo no Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) para obter detalhes. Observe que os dispositivos móveis só serão notificados se eles estão definidos para faixa e toque.

> [!IMPORTANT]
> Os usuários, o proprietário do grupo de chamada e os membros do grupo de chamada devem estar no modo de implantação somente do Teams. Para obter mais detalhes sobre os modos de implantação do Teams, consulte [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).

## <a name="license-required"></a>Licença necessária

Os usuários devem ter uma licença do Sistema de Telefonia do Microsoft Teams para configurar e usar o compartilhamento de chamadas e a retirada de chamadas em grupo. Para obter detalhes adicionais sobre o modelo de licenciamento, consulte Aqui está [o que você obter com o Sistema de Telefonia](/MicrosoftTeams/here-s-what-you-get-with-phone-system).

## <a name="configure-group-call-pickup"></a>Configurar o recolhimento de chamada de grupo

Para configurar o atendimento de chamadas em grupo, um usuário primeiro configura um grupo de chamadas (isso não é o mesmo que um grupo de segurança ou um grupo do Microsoft 365) e adiciona os usuários com os quais deseja compartilhar suas chamadas. Em seguida, eles escolhem um toque simultâneo ou uma configuração de encaminhamento de chamada. Para obter mais informações e procedimentos passo a passo, consulte Encaminhamento de chamada e [toque simultâneo no Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).

As preferências de criação e notificação de grupo de chamada são recursos orientados pelo usuário; os administradores não têm que configurar esses recursos para seus usuários. Os grupos de chamada não podem ser criados a partir de grupos de segurança ou grupos do Microsoft 365; eles devem ser criados no Teams.

Os administradores devem habilitar grupos de chamadas por meio da **configuração TeamsCallingPolicy AllowCallGroups** para um usuário. Os administradores também podem habilitar isso por meio do portal de administração do Teams.  Além disso, o usuário configurado também pode configurar seus grupos de chamada diretamente por meio do cliente. Os usuários administradores ou finais não podem bloquear a configuração uns dos outros, mas o portal de administração do Teams e o cliente do Teams devem mostrar essa relação com precisão em ambos os lugares. 

Importante: quando os administradores desativarem grupos de chamadas para usuários (depois que ele tiver sido ligado e as relações de grupo de chamadas estiver configuradas), os administradores terão que limpar as relações de grupo de chamadas para usuários no centro de administração do Teams para evitar o roteamento de chamadas incorreto. 

## <a name="limitations"></a>Limitações

Cada grupo de chamada configurado pode ter no máximo 25 usuários ou 32.768 caracteres. 

## <a name="more-information"></a>Mais informações

[Encaminhamento de chamada e toque simultâneo no Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
