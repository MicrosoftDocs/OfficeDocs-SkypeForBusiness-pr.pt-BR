---
title: Atendimento de chamada de grupo e compartilhamento de chamada
author: CarolynRowe
ms.author: crowe
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
ms.openlocfilehash: 70b1be389309d52b01852e575d08093ef7095a04
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789946"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a>Compartilhamento de chamadas e atendimento de chamada em grupo no Microsoft Teams

Os recursos de compartilhamento de chamadas e recebimento de chamadas em grupo do Microsoft Teams permitem que os usuários compartilhem suas chamadas de entrada com colegas para que os colegas possam atender chamadas que ocorrem enquanto o usuário não está disponível.

O recebimento de chamadas em grupo é menos prejudicial para os destinatários do que outras formas de compartilhamento de chamadas (como encaminhamento de chamadas ou toque simultâneo), pois os usuários podem configurar como eles querem ser notificados de uma chamada compartilhada de entrada (por meio de notificação de áudio e visual, somente visual ou faixa no aplicativo Teams) e podem decidir se a atenderão.

Para compartilhar chamadas com outras pessoas, um usuário cria um grupo de chamadas e adiciona os usuários com os quais deseja compartilhar suas chamadas. Em seguida, eles escolhem um anel simultâneo ou uma configuração de encaminhamento. Consulte [Encaminhamento de chamadas e toque simultâneo no Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) para obter detalhes. Observe que os dispositivos móveis só serão notificados se estiverem definidos para faixa e toque.

> [!IMPORTANT]
> Os usuários, o proprietário do grupo de chamadas e os membros do grupo de chamadas devem estar no modo de implantação somente do Teams. Para obter mais detalhes sobre os modos de implantação do Teams, consulte [Entender o Microsoft Teams e Skype for Business coexistência e interoperabilidade](teams-and-skypeforbusiness-coexistence-and-interoperability.md).

## <a name="license-required"></a>Licença necessária

Os usuários devem receber uma licença Telefonia do Microsoft Teams System para configurar e usar o compartilhamento de chamadas e o recebimento de chamadas em grupo. Para obter detalhes adicionais sobre o modelo de licenciamento, [consulte Aqui está o que você obtém com o Sistema de Telefonia](/MicrosoftTeams/here-s-what-you-get-with-phone-system).

## <a name="configure-group-call-pickup"></a>Configurar o recebimento de chamadas em grupo

Para configurar o recebimento de chamadas em grupo, um usuário primeiro configura um grupo de chamadas (isso não é o mesmo que um grupo de segurança ou um grupo do Microsoft 365) e, em seguida, adiciona os usuários com os quais deseja compartilhar suas chamadas. Em seguida, eles escolhem um toque simultâneo ou uma configuração de encaminhamento de chamada. Para obter mais informações e procedimentos passo a passo, consulte [Encaminhamento de chamadas e toque simultâneo no Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).

As preferências de criação e notificação do grupo de chamadas são recursos controlados pelo usuário; os administradores não precisam configurar esses recursos para seus usuários. Grupos de chamadas não podem ser criados de grupos de segurança ou grupos do Microsoft 365; eles devem ser criados no Teams.

Os administradores devem habilitar grupos de chamadas **por meio da configuração TeamsCallingPolicy AllowCallGroups** para um usuário. Os administradores também podem habilitar isso por meio do portal Administração Teams.  Além disso, o usuário configurado também pode configurar seus grupos de chamadas diretamente por meio do cliente. Administração ou usuários finais não podem bloquear a configuração entre si, mas o portal do Teams Administração e o cliente do Teams devem mostrar essa relação com precisão em ambos os locais. 

Importante: quando os administradores desativam grupos de chamadas para usuários (depois que eles são ativados e as relações de grupo de chamadas são configuradas), os administradores precisam limpar as relações do grupo de chamadas para usuários no Centro de administração do Teams para evitar o roteamento de chamadas incorreto. 

## <a name="limitations"></a>Limitações

Cada grupo de chamadas configurado pode ter no máximo 25 usuários ou 32.768 caracteres. 

## <a name="more-information"></a>Mais informações

[Encaminhamento de chamadas e toque simultâneo no Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
