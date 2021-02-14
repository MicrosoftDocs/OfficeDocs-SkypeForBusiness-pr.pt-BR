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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.users.voice.groupcallpickup.tooltip
- ms.teamsadmincenter.users.voice.callorderanddelay.tooltip
- Phone System
- seo-marvel-mar2020
description: O compartilhamento de chamadas e o recebimento de chamadas em grupo permitem que os usuários compartilhem chamadas recebidas com colegas para que as chamadas possam ser capturadas quando o usuário não estiver disponível.
ms.openlocfilehash: 825e174a6b6f68adcc7b5aade212689b01309c24
ms.sourcegitcommit: 6b24c82837ca2c11f450a162ca4fab3dfa4ac8d4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620716"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a>Compartilhamento de chamadas e atendimento de chamada em grupo no Microsoft Teams

Os recursos de compartilhamento de chamada e retirada de chamada em grupo do Microsoft Teams permitem que os usuários compartilhem suas chamadas recebidas com colegas para que os colegas possam atender chamadas que ocorrem enquanto o usuário não estiver disponível.

O recebimento de chamadas em grupo é menos prejudicial para os destinatários do que outras formas de compartilhamento de chamadas (como encaminhamento de chamadas ou toque simultâneo), pois os usuários podem configurar como eles querem ser notificados de uma chamada compartilhada de entrada (por meio de notificação visual, somente visual ou faixa no aplicativo Teams) e podem decidir se a atenderão.

Para compartilhar chamadas com outras pessoas, um usuário cria um grupo de chamadas e adiciona os usuários com quem deseja compartilhar suas chamadas. Em seguida, eles escolhem um toque simultâneo ou uma configuração de encaminhamento. Consulte [Encaminhamento de chamada e toque simultâneo no Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) para obter detalhes. Observe que os dispositivos móveis só serão notificados se eles estão definidos para faixa e toque.

> [!IMPORTANT]
> Os usuários, o proprietário do grupo de chamada e os membros do grupo de chamada devem estar no modo de implantação somente do Teams. Para obter mais detalhes sobre os modos de implantação do Teams, consulte [Entender a coexistência](teams-and-skypeforbusiness-coexistence-and-interoperability.md) e a interoperabilidade do Microsoft Teams e do Skype for Business

## <a name="license-required"></a>Licença necessária

Os usuários devem estar habilitados para configurar e usar o compartilhamento de chamadas e o recolhimento de chamadas em grupo. Para obter detalhes adicionais sobre o modelo de licenciamento, consulte a [descrição do serviço microsoft teams.](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

## <a name="configure-group-call-pickup"></a>Configurar retirada de chamada em grupo

Para configurar o recolhimento de chamadas em grupo, primeiro um usuário configura um grupo de chamadas (isso não é o mesmo que um grupo de segurança ou um grupo do Microsoft 365) e adiciona os usuários com os quais deseja compartilhar suas chamadas. Em seguida, eles escolhem um toque simultâneo ou uma configuração de encaminhamento de chamada. Para obter mais informações e procedimentos passo a passo, consulte Encaminhamento de chamada e toque [simultâneo no Teams.](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)

As preferências de notificação e criação de grupo de chamada são recursos orientados pelo usuário; os administradores não têm que configurar esses recursos para seus usuários. Grupos de chamada não podem ser criados a partir de grupos de segurança ou grupos do Microsoft 365; eles devem ser criados no Teams.

Os administradores devem habilitar grupos de chamada por meio da **configuração TeamsCallingPolicy AllowCallGroups** para um usuário. Os administradores também podem habilita-los por meio do portal de administração do Teams.  Além disso, o usuário configurado também pode configurar seus grupos de chamada diretamente por meio do cliente. Os usuários finais ou administradores não podem bloquear a configuração uns dos outros, mas o portal de administração do Teams e o cliente do Teams devem mostrar essa relação com precisão em ambos os locais. 

Importante: quando os administradores desativarem grupos de chamadas para usuários (depois que ele tiver sido ligado e as relações de grupo de chamadas estiver configuradas), os administradores terão que limpar as relações de grupo de chamadas para os usuários no Centro de administração do Teams para evitar o roteamento de chamadas incorreto. 

## <a name="limitations"></a>Limitações

Um locatário pode conter no máximo 32.768 grupos de chamada. Pode haver no máximo 25 usuários em cada grupo de chamada. 

## <a name="more-information"></a>Mais informações

[Encaminhamento de chamada e toque simultâneo no Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
