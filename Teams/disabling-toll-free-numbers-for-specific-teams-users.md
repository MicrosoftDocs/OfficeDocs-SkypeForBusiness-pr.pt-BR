---
title: Desativar números de chamada gratuita para usuários específicos do Microsoft Teams
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Saiba como controlar como os organizadores podem usar números gratuitos para suas reuniões da Ponte de Audioconferência.
ms.openlocfilehash: 6d841a48381609a019a1749095aac4a95901a7c4
ms.sourcegitcommit: 296fbefe0481c0b8b94aee925118474375cdf138
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2022
ms.locfileid: "65016623"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a>Desativar números de chamada gratuita para usuários específicos do Microsoft Teams

Se sua organização tiver números de chamada gratuita em sua Ponte de Audioconferência da Microsoft, você poderá permitir ou impedir seu uso nas reuniões de organizadores específicos.  

Por padrão, todos os usuários em sua organização estão habilitados para usar números de chamada gratuita, o que significa que esses números, se disponíveis, podem ser usados pelos participantes para ingressar em suas reuniões. Se esse não for o comportamento desejado para alguns usuários em sua organização, você poderá impedir que usuários específicos usem esses números em suas reuniões por meio de um controle de habilitação de número de chamada gratuita.

Quando os números de chamada gratuita são desabilitados para um determinado organizador:

- Um número de chamada gratuita não será mais incluído em seus convites de reunião.
- Os números de chamada gratuita não serão mais listados na página "Localizar um número local" que é referenciada em seus convites de reunião.
- Os participantes não poderão ingressar na reunião do organizador especificado se discarem qualquer número de chamada gratuita da organização.
- Os participantes podem continuar ingressando em reuniões do organizador usando números de chamada tarifada.

## <a name="disabling-toll-free-numbers-for-specific-users"></a>Desativar números gratuitos para usuários específicos

Você pode desabilitar números de chamada gratuita para usuários específicos alterando a configuração de *AllowTollFreeDialIn* para **Off** no *TeamsAudioConferencingPolicy* atribuído a esses usuários. Uma vez desativadas as novas reuniões criadas por esses usuários, não incluirão números de chamada gratuita. [As configurações de política de audioconferência para números de chamada tarifada](audio-conferencing-toll-free-numbers-policy.md) e gratuita têm mais informações.

> [!IMPORTANT]
> Reuniões recorrentes antigas e agendadas anteriormente ainda podem mostrar números de chamada gratuita e os participantes não poderão participar dessas reuniões usando um número de chamada gratuita. Você pode reagendar todas as reuniões antigas e recorrentes para esses usuários e remover números de chamada gratuita usando o MMS.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
