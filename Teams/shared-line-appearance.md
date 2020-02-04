---
title: Aparência de linha compartilhada no Microsoft Teams
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: conceptual
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
- ms.teamsadmincenter.users.voice.calldelegation.tooltip
ms.custom:
- Phone System
description: A aparência da linha compartilhada permite que um usuário escolha um representante para atender ou manipular chamadas em seu nome.
ms.openlocfilehash: 2d050d341d22d74f0d207873925126ad5f7fdc3b
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41694356"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a>Aparência de linha compartilhada no Microsoft Teams

A aparência da linha compartilhada faz parte do recurso de delegação que permite que um usuário escolha um representante para atender ou manipular chamadas em seu nome. Esse recurso é útil se um usuário tiver um assistente administrativo que manipula regularmente as chamadas do usuário. No contexto de aparência de linha compartilhada, um gerente é alguém que autoriza um representante a fazer ou receber chamadas em seu nome, e um representante pode fazer e receber chamadas em nome de outra pessoa.

> [!IMPORTANT]
> Esse recurso só está disponível no modo de implantação do teams. Para obter mais detalhes sobre os modos de implantação do Teams, consulte [entender o Microsoft Teams e a coexistência e interoperabilidade do Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>Licença necessária

Um usuário deve ter o sistema telefônico com conectividade PSTN (uma licença de plano de chamada ou um OnlineVoiceRoutingPolicy de roteamento direto) para ser um representante ou configurar a delegação e permitir que outras pessoas façam ou recebam chamadas em seu nome.

Os gerentes e representantes precisam ter um sistema telefônico com conectividade PSTN (uma licença de plano de chamada ou um OnlineVoiceRoutingPolicy de roteamento direto). A experiência de linha compartilhada faz parte da delegação e está incluída com o sistema telefônico. Para obter detalhes adicionais sobre o modelo de licenciamento, consulte [Licenciamento do Office 365 para Microsoft Teams](office-365-licensing.md).

## <a name="configuring-delegation-and-shared-line-appearance"></a>Configurar a aparência da delegação e da linha compartilhada

A aparência da delegação e da linha compartilhada são recursos orientados pelo usuário: não há configurações de administração a serem definidas. Para obter informações sobre como usar o recurso, consulte [compartilhar uma linha telefônica com um representante](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

O administrador de locatários pode habilitar a delegação por meio da configuração **TeamsCallingPolicy AllowDelegation** ou por meio do portal de administração do teams para que esse recurso funcione. 

O administrador de locatários também pode configurar relações de delegação para um usuário no centro de administração do teams. Além disso, o usuário final também pode configurar as relações de delegação diretamente no Teams. O administrador de locatários ou o usuário não pode bloquear a configuração entre si, mas o centro de administração do Teams e o cliente das equipes devem mostrar essa relação com precisão em ambos os locais. 

> [!IMPORTANT]
> Quando o administrador de locatário desativa a delegação para um usuário (depois que ele é ativado), ele também precisa limpar as relações de delegação desse usuário no centro de administração do teams para evitar roteamento de chamadas incorreto.

## <a name="shared-line-appearance-feature-availability"></a>Disponibilidade do recurso de aparência da linha compartilhada

A aparência da linha compartilhada tem suporte no momento pelos seguintes aplicativos e dispositivos.

| Potencial | Teams desktop | Aplicativo Teams Mac | Aplicativo Web do Teams (Edge) |Aplicativo móvel do teams para iOS/Android | Telefone IP do teams |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| Configurar a delegação | Sim | Sim | Sim | Não | Não |
| Receber chamadas em nome de outra | Sim | Sim | Sim | Sim | Sim |
| Ligar para um número de telefone em nome de outro | Sim | Sim | Sim | Sim | Sim |
| Chamar um usuário do teams em nome de outro | Sim | Sim | Sim | Sim | Sim |
| Ver o modo de exibição de administração de linhas compartilhadas | Sim | Sim | Sim | Não | Não |
| Consulte o modo de exibição administrador das atividades de chamada do gerente | Sim | Sim | Sim | Não | Não |
| Ver o modo de exibição do Gerenciador de representantes | Sim | Sim | Sim | Não | Não |
| O administrador ou o gerente pode reter ou retomar | Sim | Sim | Sim | Não | Não |

## <a name="limitations"></a>Relacionadas

Os gerentes podem adicionar até 25 representantes, e os representantes podem ter até 25 gerentes. Não há limite quanto ao número de relações de delegação que podem ser criadas em um locatário. 
 
Se o representante e o representante não estiverem na mesma localização geográfica, o provedor PSTN será atualizado para permitir que a identificação de chamadas apareça em uma localização geográfica diferente para uma chamada delegada (em nome de). 
 
## <a name="more-information"></a>Mais informações

[Compartilhar uma linha telefônica com um representante](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)
