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
ms.localizationpriority: medium
f1.keywords:
  - CSH
ms.custom:
  - Phone System
  - ms.teamsadmincenter.users.voice.calldelegation.tooltip
  - seo-marvel-apr2020
description: Saiba como enviar aos usuários um email com suas informações de audioconferência Microsoft Teams.
---

# <a name="shared-line-appearance-in-microsoft-teams"></a>Aparência de linha compartilhada no Microsoft Teams

A aparência de linha compartilhada faz parte do recurso de delegação que permite que um usuário escolha um representante para atender ou manipular chamadas em seu nome. Esse recurso é útil se um usuário tiver um assistente administrativo que lida regularmente com as chamadas do usuário. No contexto da aparência de linha compartilhada, um gerente é alguém que autoriza um representante a fazer ou receber chamadas em seu nome, e um representante pode fazer e receber chamadas em nome de outra pessoa.

> [!IMPORTANT]
> Esse recurso só está disponível no Teams modo de implantação Somente. Para obter mais detalhes sobre Teams de implantação, consulte [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>Licença necessária

Um usuário deve ter Sistema de Telefonia conectividade PSTN (uma licença de Plano de Chamada ou Roteamento Direto OnlineVoiceRoutingPolicy) para ser um representante ou configurar a delegação e permitir que outras pessoas façam ou recebam chamadas em seu nome.

Os gerentes e representantes precisam ter Sistema de Telefonia conectividade PSTN (uma licença de Plano de Chamadas ou Roteamento Direto OnlineVoiceRoutingPolicy). A experiência de linha compartilhada faz parte da delegação e está incluída no Sistema de Telefonia. Para obter detalhes adicionais sobre o modelo de licenciamento, [consulte Microsoft Teams descrição do serviço](/office365/servicedescriptions/teams-service-description).

## <a name="configuring-delegation-and-shared-line-appearance"></a>Configurando a delegação e a aparência de linha compartilhada

Delegação e aparência de linha compartilhada são recursos orientados pelo usuário: não há configurações de administrador a ser configuradas. Para obter informações sobre como usar o recurso, consulte [Compartilhar uma linha de telefone com um representante](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

O administrador de locatários pode habilitar a delegação por meio da **configuração TeamsCallingPolicy AllowDelegation** ou Teams Portal de Administração para que esse recurso funcione. 

O administrador de locatários também pode configurar relações de delegação para um usuário no Teams de administração. Além disso, o usuário final também pode configurar suas relações de delegação diretamente Teams. O administrador de locatários ou o usuário não podem bloquear a configuração um do outro, mas o centro de administração Teams e o cliente Teams devem mostrar essa relação com precisão em ambos os lugares. 

> [!IMPORTANT]
> Quando o administrador de locatários desliga a delegação de um usuário (depois que ele foi ligado), ele também precisa limpar as relações de delegação para esse usuário no centro de administração Teams para evitar o roteamento de chamadas incorreto.

## <a name="shared-line-appearance-feature-availability"></a>Disponibilidade do recurso de aparência de linha compartilhada

No momento, a aparência de linha compartilhada é compatível com os seguintes aplicativos e dispositivos.

| Recursos | Teams Desktop | Teams Mac App | Teams Web App (Edge) |Teams aplicativo móvel iOS/Android | Teams IP |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| Configurar delegação | Sim | Sim | Sim | Não | Sim |
| Receber chamadas em nome de outro | Sim | Sim | Sim | Sim | Sim |
| Chamar um número de telefone em nome de outro | Sim | Sim | Sim | Sim | Sim |
| Chamar um Teams usuário em nome de outro | Sim | Sim | Sim | Sim | Sim |
| Consulte a exibição delegada de linhas compartilhadas | Sim | Sim | Sim | Não | Sim |
| Consulte a exibição delegada das atividades de chamada do gerente | Sim | Sim | Sim | Não | Sim |
| Consulte a exibição de gerente de representantes | Sim | Sim | Sim | Não | Sim |
| O representante ou o gerente pode segurar ou retomar | Sim | Sim | Sim | Não | Sim |

## <a name="limitations"></a>Limitações

Os gerentes podem adicionar até 25 representantes, e os representantes podem ter até 25 gerentes. Não há limite para o número de relações de delegação que podem ser criadas em um locatário. 
 
Se o representante e o representante não estão na mesma localização geográfica, é responsabilidade do provedor PSTN permitir que a ID do chamador seja a aparecer de um local geográfico diferente para uma chamada delegada (em nome de) delegada. 

A configuração de delegação circular não é permitida. Se os usuários delegados também têm delegações entre eles, eles só poderão ver sua delegação e não a delegação inicial.
 
## <a name="more-information"></a>Mais informações

[Compartilhar uma linha telefônica com um representante](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)
