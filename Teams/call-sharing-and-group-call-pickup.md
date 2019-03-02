---
title: Compartilhamento de chamadas e atendimento de chamada em grupo no Microsoft Teams
ms.author: lolaj
author: lolaj
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Compartilhamento de chamadas e retirada de chamada do grupo, que permitem aos usuários compartilhar chamadas recebidas com colegas, de forma que as chamadas podem ser capturadas quando o usuário não está disponível.
ms.openlocfilehash: df98dd4df064b23b687ddcc569e6c5a431137527
ms.sourcegitcommit: 59eda0c17ff39a3e6632810391d78bbadc214419
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/01/2019
ms.locfileid: "30351326"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a>Compartilhamento de chamadas e atendimento de chamada em grupo no Microsoft Teams

O compartilhamento de chamada e o grupo de chamada pickup recursos de compartilhamento de permitem que os usuários do Microsoft Teams seu as chamadas de entrada com colegas para que os colegas podem atender as chamadas que ocorrem enquanto o usuário não está disponível.

Retirada de chamada do grupo é menos interrupções para destinatários que outras formas de chamada de compartilhamento (por exemplo, encaminhamento de chamadas ou toque simultâneo) porque os usuários podem configurar como desejam ser notificado sobre uma chamada de entrada compartilhada (por meio de notificação de áudio e vídeo, apenas, visual ou faixas do aplicativo de equipes em), e eles podem decidir atendê-la.

Para compartilhar chamadas com outras pessoas, um usuário cria um grupo de chamada e adiciona os usuários que desejam compartilhar suas chamadas com. Em seguida, eles escolher um toque simultâneo ou encaminham configuração. Para obter detalhes, consulte [chamada Toque simultâneo e de encaminhamento em equipes](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) .

> [!IMPORTANT]
> Membros do grupo de chamada, o proprietário do grupo de chamada e os usuários devem estar no modo somente as equipes de implantação. Para obter mais detalhes sobre modos de implantação de equipes, consulte [entender as equipes da Microsoft e Skype para interoperabilidade e coexistência de negócios](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>É necessária uma licença

Os usuários precisam ser habilitada para configurar e usar o compartilhamento de chamada e chamada retirada de grupo do Enterprise Voice. Para obter detalhes adicionais sobre o modelo de licenciamento, consulte [Licenciamento do Office 365 para equipes da Microsoft](office-365-licensing.md).

## <a name="configure-group-call-pickup"></a>Configurar a retirada de chamada de grupo

Para configurar a retirada de chamada do grupo, um usuário configura pela primeira vez um grupo de chamada (isso não é o mesmo como um grupo de segurança ou de um grupo do Office 365) e, em seguida, adiciona os usuários que desejam compartilhar suas chamadas com. Em seguida, eles escolher um toque simultâneo ou configuração de encaminhamento de chamadas. Para obter mais informações e procedimentos passo a passo, consulte a [chamada Toque simultâneo e de encaminhamento em equipes](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).

Chamar a criação de grupo e notificação preferências são recursos controlado pelo usuário; os administradores não devem configurar esses recursos para seus usuários. Grupos de chamada não não possível criar grupos de segurança ou grupos do Office 365; eles devem ser criados em equipes.

Administradores devem habilitar grupos de chamada por meio da configuração de **TeamsCallingPolicy AllowCallGroups** para um usuário. Os administradores podem controlar apenas, se esse usuário pode configurar grupos de chamada. Depois que o bit for definido como true, administradores não pode impedir o usuário de configuração e adicionando os usuários do grupo de chamada de sua escolha.

## <a name="limitations"></a>Limitações

Um locatário pode conter um máximo de grupos de 32.768 chamada. Pode haver um máximo de 5 usuários em cada grupo de chamada. 

## <a name="more-information"></a>Mais informações

[Encaminhamento de chamadas e toque simultâneo em equipes](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)