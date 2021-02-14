---
title: Aparência de linha compartilhada no Microsoft Teams
ms.author: serdars
author: SerdarSoysal
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
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.users.voice.calldelegation.tooltip
- seo-marvel-apr2020
description: Saiba como enviar um email aos usuários com suas informações de audioconferência no Microsoft Teams.
ms.openlocfilehash: 7750f85e959f332832c24b60b4efafd784218f61
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583830"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a>Aparência de linha compartilhada no Microsoft Teams

A aparência de linha compartilhada faz parte do recurso de delegação que permite que um usuário escolha um representante para atender ou lidar com chamadas em seu nome. Esse recurso será útil se um usuário tiver um assistente administrativo que lida regularmente com as chamadas do usuário. No contexto de aparência de linha compartilhada, um gerente é alguém que autoriza um representante a fazer ou receber chamadas em seu nome, e um representante pode fazer e receber chamadas em nome de outra pessoa.

> [!IMPORTANT]
> Esse recurso só está disponível no modo de implantação somente do Teams. Para obter mais detalhes sobre os modos de implantação do Teams, consulte [Entender a coexistência](teams-and-skypeforbusiness-coexistence-and-interoperability.md) e a interoperabilidade do Microsoft Teams e do Skype for Business

## <a name="license-required"></a>Licença necessária

Um usuário deve ter o Sistema telefônico com conectividade PSTN (uma licença de Plano de Chamada ou Roteamento Direto OnlineVoiceRoutingPolicy) para ser representante ou configurar delegação e permitir que outras pessoas façam ou recebam chamadas em nome delas.

Os gerentes e os representantes precisam ter o Sistema telefônico com conectividade PSTN (uma licença de Plano de Chamada ou Roteamento Direto OnlineVoiceRoutingPolicy). A experiência de linha compartilhada faz parte da delegação e está incluída no Sistema telefônico. Para obter detalhes adicionais sobre o modelo de licenciamento, consulte a [descrição do serviço microsoft teams.](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

## <a name="configuring-delegation-and-shared-line-appearance"></a>Configurando a delegação e a aparência da linha compartilhada

Delegação e aparência de linha compartilhada são recursos orientados pelo usuário: não há configurações de administrador para configurar. Para obter informações sobre como usar o recurso, consulte [Compartilhar uma linha telefônica com um representante](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

O administrador de locatários pode habilitar a delegação por meio da **configuração de AllowDelegation do TeamsCallingPolicy** ou do Portal de Administração do Teams para que esse recurso funcione. 

O administrador de locatários também pode configurar relações de delegação para um usuário no Centro de administração do Teams. Além disso, o usuário final também pode configurar suas relações de delegação diretamente no Teams. O administrador locatário ou o usuário não pode bloquear a configuração entre si, mas o centro de administração do Teams e o cliente do Teams devem mostrar essa relação com precisão em ambos os locais. 

> [!IMPORTANT]
> Quando o administrador de locatários desabilita a delegação de um usuário (depois de ter sido ligado), ele também precisa limpar as relações de delegação desse usuário no Centro de administração do Teams para evitar o roteamento de chamadas incorreto.

## <a name="shared-line-appearance-feature-availability"></a>Disponibilidade de recursos de aparência de linha compartilhada

No momento, a aparência de linha compartilhada tem suporte nos seguintes aplicativos e dispositivos.

| Recursos | Área de Trabalho do Teams | Aplicativo Teams Para Mac | Teams Web App (Edge) |Aplicativo móvel do Teams para iOS/Android | Telefone IP do Teams |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| Configurar delegação | Sim | Sim | Sim | Não | Sim |
| Receber chamadas em nome de outra pessoa | Sim | Sim | Sim | Sim | Sim |
| Ligar para um número de telefone em nome de outro | Sim | Sim | Sim | Sim | Sim |
| Ligar para um usuário do Teams em nome de outro | Sim | Sim | Sim | Sim | Sim |
| Ver a exibição de administrador de linhas compartilhadas | Sim | Sim | Sim | Não | Não |
| Ver a exibição de administração das atividades de chamada do gerente | Sim | Sim | Sim | Não | Não |
| Ver a exibição gerente dos representantes | Sim | Sim | Sim | Não | Não |
| O administrador ou gerente pode segurar ou retomar | Sim | Sim | Sim | Não | Não |

## <a name="limitations"></a>Limitações

Os gerentes podem adicionar até 25 representantes, e os representantes podem ter até 25 gerentes. Não há limite para o número de relações de delegação que podem ser criadas em um locatário. 
 
Se o delegador e o representante não estão no mesmo local geográfico, é responsabilidade do provedor de PSTN permitir que a ID de chamador seja a partir de um local geográfico diferente para uma chamada delegada (em nome de) delegada. 
 
## <a name="more-information"></a>Mais informações

[Compartilhar uma linha telefônica com um representante](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)
