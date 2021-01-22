---
title: Discagem por voz de áudio e ligue para mim em minutos
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, oscarr
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Licensing
- seo-marvel-mar2020
description: Disque e ligue para mim em minutos. A partir de 1 ° de dezembro de 2019 cada assinatura de audioconferência fornece 60 minutos por usuário para zoneamento de um país/região.
ms.openlocfilehash: ee309bc579ae1360763ff0d77fad7eb3c22b3c5a
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918927"
---
# <a name="audio-conferencing-subscription-dial-outcall-me-at-minutes-benefit"></a>Benefícios da assinatura "discagem"/"ligar para mim por" minutos da assinatura de áudio audioconferência

## <a name="microsoft-teams-and-skype-for-business-pstn-audio-conferencing"></a>Conferência de áudio PSTN do Microsoft Teams e do Skype for Business

Cada assinatura de audioconferência fornece 60 minutos por usuário por mês que podem ser usados para discar para números não Premium em qualquer uma das zonas de um país, conforme descrito neste documento. Seu tamanho de pool de minutos de discagem de locatário é baseado em licenças *adquiridas* . Esse benefício se aplica às licenças de *assinatura mensal* da conferência de áudio e não se estende às licenças de pagamento por minuto de audioconferência. 

> [!NOTE]
> A partir de 22 de outubro de 2020, o tamanho do pool de minutos de discagem de o nosso locatário é baseado no número de licenças de assinatura *adquiridas* de conferência de áudio. Antes, o tamanho do pool de minutos de discagem era baseado no número de licenças *atribuídas* aos usuários.


> [!NOTE]
> O final do [período de discagem gratuita](complimentary-dial-out-period.md) não ocorreu em 30 de novembro de 2019, para os países onde a assinatura de audioconferência está disponível, mas não oferecemos a capacidade de configurar créditos de comunicações. Esses países específicos são Rússia, Coréia do Sul e Taiwan.

## <a name="audio-conferencing-dial-out-from-a-meeting--call-me-at-details"></a>Detalhes da "discagem" de conferência de áudio "&" ligar para mim em "

Para os clientes adotarem o nosso serviço de audioconferência, a Microsoft oferece a capacidade de discar de reuniões organizadas por usuários com uma licença de assinatura de audioconferência atribuída. As chamadas discada para países não incluídos na [zona uma lista de países e regiões](audio-conferencing-zones.md) são cobradas por minuto usando créditos de comunicações. Para chamadas discadas cobradas por minuto (chamadas que excedem o pool de minutos de discagem de locatário ou chamadas para destinos que não estão na [zona uma lista de países e regiões](audio-conferencing-zones.md) , as chamadas e suas tarifas associadas se baseiam no destino da chamada e não no país de residência do organizador ou no participante da reunião que inicia a chamada de discagem. Por exemplo, uma chamada de discagem de conferência de áudio para um número de telefone na França, que é uma zona para um país, será cobrada com a mesma tarifa por minuto se ela tiver sido iniciada por um participante da reunião nos Estados Unidos, na França ou no Zimbábue. 


|Localização do uso da licença do organizador da reunião |Destino discado |Posso usar meus minutos de pool de minutos de discagem externa?|Preciso de créditos de comunicações?|
|---------|---------|---------|---------|
|Estados Unidos |Estados Unidos |Sim (zona A país) |Sim *após* consumir o pool de minutos do locatário         |
|Estados Unidos |Reino Unido|Sim (zona A país) |  Sim *após* consumir o pool de minutos do locatário       |
|Estados Unidos     |Zimbábue|    Não     |     Sim em *todas as* chamadas    |
|Reino Unido     |Reino Unido|Sim (zona A país) |  Sim *após* consumir o pool de minutos do locatário       |
|Reino Unido     |Estados Unidos |Sim (zona A país) |  Sim *após* consumir o pool de minutos do locatário       |
|Reino Unido     |Zimbábue|    Não     |   Sim em *todas as* chamadas      |
|Zimbábue     |Zimbábue|    Não     |    Sim em *todas as* chamadas     |
|Zimbábue     |Estados Unidos | Sim (zona A país) | Sim *após* consumir o pool de minutos do locatário        |
|Zimbábue     |Reino Unido | Sim (zona A país) | Sim *após* consumir o pool de minutos do locatário        |
|Ilhas Cook     |Ilhas Cook |   Não      |    Sim em *todas as* chamadas     |
|Ilhas Cook     |Estados Unidos  | Sim (zona A país) |  Sim *após* consumir o pool de minutos do locatário       |
|Ilhas Cook     |Reino Unido | Sim (zona A país) | Sim *após* consumir o pool de minutos do locatário        |
|    |         |         |         |

## <a name="how-are-minute-pools-calculated"></a>Como os pools de minutos são calculados?

Considere o exemplo a seguir. Um cliente comprou licenças de assinatura do 115 Audio Conferencing e tem 10 usuários nos Estados Unidos, 100 usuários do Reino Unido e 5 usuários no Zimbábue, tudo com licenças de assinatura de audioconferência atribuídas. Todos os usuários do 115 compartilham um pool de (115 usuários x 60 min = 6.900 conferência discada minutos por mês) para fazer chamadas feitas para números não-Premium em qualquer [uma das zonas de países e regiões](audio-conferencing-zones.md), *independentemente* de onde o organizador da reunião estiver licenciado ou fisicamente localizado. Por exemplo, um organizador da reunião do Zimbábue poderá discar para qualquer [zona de países e regiões](audio-conferencing-zones.md) até o limite do pool de minutos.

- Todas as chamadas discadas que excedem 6.900 minutos por mês são cobradas por minuto usando créditos de comunicações em nossas tarifas publicadas para esse destino. (Observação: o cliente deve configurar [créditos de comunicações](what-are-communications-credits.md) e atribuir a licença de créditos de comunicações ao organizador da reunião.)
- Todas as chamadas discadas para destinos que não estão na [zona uma lista de países e regiões](audio-conferencing-zones.md) são cobradas por minuto usando créditos de comunicações em nossas tarifas publicadas para esse destino (desde que o cliente tenha configurado créditos de comunicações e atribuiu a licença de créditos de comunicação ao organizador da reunião).

## <a name="how-can-i-monitor-minute-my-pool-usage"></a>Como faço para monitorar o uso do meu pool em minutos?

- Você pode monitorar o uso em seu pool de minutos de discagem externa no centro de administração do Microsoft Teams. No painel de navegação esquerdo, vá para **análises &** relatórios de  >  **uso** de relatórios e selecione **pools de minutos PSTN**. A zona um pool de minutos de discagem externa será rotulado no relatório como "chamadas de saída para a região A países".
- As notificações de email serão enviadas para os seguintes administradores quando a utilização do pool de minutos de discagem de sua organização tiver atingido 80% e 100%:

  - Administrador de cobrança
  - Administrador do Skype for Business
  - Administrador da empresa
  - Administrador de conta de usuário
  - Administrador da assistência técnica
  - Administrador de suporte do serviço
  - Administradores de dispositivo
  - Administrador do aplicativo
  - Administrador de licenças
  - Administrador de dispositivo na nuvem
  - Administrador de autenticação
  - Administrador de autenticação privilegiada
  - Administrador de Comunicações de Equipes
  - Engenheiro de Suporte de Comunicações de Equipes
  - Especialista em suporte do teams Communications
  - Administrador de Serviço do Teams

Para obter informações adicionais sobre créditos de comunicação, consulte [créditos de comunicações](what-are-communications-credits.md).

## <a name="related-topics"></a>Tópicos relacionados

- [Disponibilidade de audioconferência e Planos de Chamadas por país e região](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [Regiões de país e região para videoconferência](audio-conferencing-zones.md)
