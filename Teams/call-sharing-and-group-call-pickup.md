---
title: Atendimento de chamada de grupo e compartilhamento de chamada
ms.author: lolaj
author: LolaJacobsen
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
description: Compartilhamento de chamadas e retirada de chamadas em grupo permitem que os usuários compartilhem chamadas com colegas para que as chamadas possam ser capturadas quando o usuário não estiver disponível.
ms.openlocfilehash: 0e21f8ec8b9d913568b87a41b70261ac917260e2
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44638850"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a>Compartilhamento de chamadas e atendimento de chamada em grupo no Microsoft Teams

Os recursos de compartilhamento de chamadas e retirada de chamadas de grupo do Microsoft Teams permitem que os usuários compartilhem suas chamadas de entrada com colegas para que os colegas possam atender chamadas que ocorrem enquanto o usuário está indisponível.

O recebimento de chamadas em grupo é menos prejudicial aos destinatários do que outras formas de compartilhamento de chamadas (como encaminhamento de chamadas ou toque simultâneo) porque os usuários podem configurar como querem ser notificados sobre uma chamada compartilhada de entrada (via áudio e notificação Visual, somente Visual ou em faixa no aplicativo Teams) e podem decidir se devem atendê-la.

Para compartilhar chamadas com outras pessoas, um usuário cria um grupo de chamada e adiciona os usuários com quem deseja compartilhar suas chamadas. Em seguida, escolha uma configuração de toque ou encaminhamento simultânea. Consulte [encaminhamento de chamadas e toque simultâneo no Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) para obter detalhes.

> [!IMPORTANT]
> Os usuários, o proprietário do grupo de chamadas e os membros do grupo de chamadas devem estar no modo de implantação do teams only. Para obter mais detalhes sobre os modos de implantação do Teams, consulte [entender o Microsoft Teams e a coexistência e interoperabilidade do Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>Licença necessária

Os usuários devem ter o Enterprise Voice habilitado para configurar e usar o compartilhamento de chamadas e a retirada de chamadas em grupo. Para obter detalhes adicionais sobre o modelo de licenciamento, consulte [Descrição do serviço Microsoft Teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).

## <a name="configure-group-call-pickup"></a>Configurar a retirada de chamadas em grupo

Para configurar o recebimento de chamadas em grupo, um usuário primeiro configura um grupo de chamadas (isso não é o mesmo que um grupo de segurança ou um grupo do Microsoft 365) e, em seguida, adiciona os usuários com quem deseja compartilhar suas chamadas. Em seguida, eles escolhem uma configuração de toque simultâneo ou encaminhamento de chamadas. Para obter mais informações e procedimentos passo a passo, consulte [encaminhamento de chamadas e toque simultâneo no Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).

A criação de grupos de chamadas e preferências de notificação são recursos controlados pelo usuário; os administradores não precisam configurar esses recursos para seus usuários. Os grupos de chamadas não podem ser criados a partir de grupos de segurança ou de grupos do Microsoft 365; Elas devem ser criadas no Teams.

Os administradores devem habilitar os grupos de chamadas por meio da configuração **TeamsCallingPolicy AllowCallGroups** para um usuário. Os administradores também podem habilitá-lo por meio do portal de administração do teams.  Além disso, o usuário configurado também pode configurar seus grupos de chamadas diretamente por meio do cliente. Os usuários finais ou administradores não podem bloquear a configuração de cada uma, mas o portal de administração do Teams e o cliente das equipes devem mostrar essa relação com precisão em ambos os locais. 

Importante: quando os administradores desativarem os grupos de chamadas para usuários (depois que ele for ativado e os relacionamentos do grupo de chamadas estiverem configurados), os administradores precisarão limpar as relações de grupo de chamadas para usuários no centro de administração do teams para evitar o roteamento de chamadas incorretas. 

## <a name="limitations"></a>Relacionadas

Um locatário pode conter um máximo de grupos de chamadas do 32.768. Pode haver no máximo 25 usuários em cada grupo de chamada. 

## <a name="more-information"></a>Mais informações

[Encaminhamento de chamadas e toque simultâneo no Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
