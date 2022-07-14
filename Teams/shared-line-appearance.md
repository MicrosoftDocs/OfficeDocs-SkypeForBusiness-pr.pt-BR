---
title: Aparência de linha compartilhada no Microsoft Teams
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.users.voice.calldelegation.tooltip
- seo-marvel-apr2020
description: Saiba mais sobre como enviar um email aos usuários com suas informações de audioconferência no Microsoft Teams.
ms.openlocfilehash: 3646cf27e22f5224dc825c758f757cc04d5804fc
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66794319"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a>Aparência de linha compartilhada no Microsoft Teams

A aparência de linha compartilhada faz parte do recurso de delegação que permite que um usuário escolha um delegado para atender ou manipular chamadas em seu nome. Esse recurso será útil se um usuário tiver um assistente administrativo que manipula regularmente as chamadas do usuário. No contexto da aparência de linha compartilhada, um gerente é alguém que autoriza um representante a fazer ou receber chamadas em seu nome, e um representante pode fazer e receber chamadas em nome de outra pessoa.

> [!IMPORTANT]
> Esse recurso só está disponível no modo de implantação somente do Teams. Para obter mais detalhes sobre os modos de implantação do Teams, consulte [Entender o Microsoft Teams e Skype for Business coexistência e interoperabilidade](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>Licença necessária

Um usuário deve ter o Sistema de Telefonia com conectividade PSTN (uma licença de Plano de Chamada ou Roteamento Direto OnlineVoiceRoutingPolicy) para ser um representante ou configurar a delegação e permitir que outras pessoas façam ou recebam chamadas em seu nome.

Os gerentes e representantes precisam ter o Sistema de Telefonia com conectividade PSTN (uma licença de Plano de Chamada ou Roteamento Direto OnlineVoiceRoutingPolicy). A experiência de linha compartilhada faz parte da delegação e está incluída no Sistema de Telefonia. Para obter detalhes adicionais sobre o modelo de licenciamento, consulte a [descrição do serviço do Microsoft Teams](/office365/servicedescriptions/teams-service-description).

## <a name="configuring-delegation-and-shared-line-appearance"></a>Configurando a delegação e a aparência de linha compartilhada

Delegação e aparência de linha compartilhada são recursos controlados pelo usuário: não há configurações de administrador a serem definidas. Para obter informações sobre como usar o recurso, consulte [Compartilhar uma linha telefônica com um representante](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

O administrador de locatários pode habilitar a delegação por meio da configuração **Delegação de Permissão do TeamsCallingPolicy** ou por meio do Teams Administração Portal para que esse recurso funcione. 

O administrador de locatários também pode configurar relações de delegação para um usuário no centro de administração do Teams. Além disso, o usuário final também pode configurar suas relações de delegação diretamente no Teams. O administrador do locatário ou o usuário não pode bloquear a configuração entre si, mas o centro de administração do Teams e o cliente do Teams devem mostrar essa relação com precisão em ambos os locais. 

> [!IMPORTANT]
> Quando o administrador do locatário desativa a delegação de um usuário (depois que ele foi ativado), ele também precisa limpar as relações de delegação para esse usuário no centro de administração do Teams para evitar o roteamento de chamadas incorreto.

## <a name="shared-line-appearance-feature-availability"></a>Disponibilidade do recurso de aparência de linha compartilhada

No momento, há suporte para a aparência de linha compartilhada nos aplicativos e dispositivos a seguir.

| Recursos | Área de Trabalho do Teams | Aplicativo Mac do Teams | Aplicativo Web do Teams (Edge) |Aplicativo móvel do Teams para iOS/Android | Telefone IP do Teams |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| Configurar delegação | Sim | Sim | Sim | Não | Sim |
| Receber chamadas em nome de outro | Sim | Sim | Sim | Sim | Sim |
| Ligar para um número de telefone em nome de outro | Sim | Sim | Sim | Sim | Sim |
| Chamar um usuário do Teams em nome de outro | Sim | Sim | Sim | Sim | Sim |
| Ver a exibição delegada de linhas compartilhadas | Sim | Sim | Sim | Não | Sim |
| Consulte a exibição delegada das atividades de chamada do gerente | Sim | Sim | Sim | Não | Sim |
| Ver a exibição de gerente de delegados | Sim | Sim | Sim | Não | Sim |
| O representante ou o gerente pode manter ou retomar | Sim | Sim | Sim | Não | Sim |

## <a name="limitations"></a>Limitações

Os gerentes podem adicionar até 25 representantes, e os representantes podem ter até 25 gerentes. Não há limite para o número de relações de delegação que podem ser criadas em um locatário. 
 
Se o delegante e o delegado não estão na mesma localização geográfica, é 300% do provedor PSTN permitir que a ID do chamador apareça de uma localização geográfica diferente para uma chamada delegada (em nome de). 

A configuração de delegação circular não é permitida. Se os usuários delegados também tiverem delegações entre eles, eles só poderão ver sua delegação e não a delegação inicial.
 
## <a name="more-information"></a>Mais informações

[Compartilhar uma linha telefônica com um representante](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)
