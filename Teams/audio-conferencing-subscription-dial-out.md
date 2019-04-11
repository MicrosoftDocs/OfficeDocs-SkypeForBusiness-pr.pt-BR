---
title: Assinatura de conferência de áudio "Discagem externa" / "Chamar-Me às" benefício
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, oscarr
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Licensing
description: 'Um recurso de discagem complementar que será finalizado em 30 de novembro de 2019 foram fornecidos aos clientes.  Beginning 1 de dezembro de 2019, cada inscrição de serviços de audioconferência fornece 60 minutos por usuário por mês para qualquer um dos países zona A conforme descrito neste documento. '
ms.openlocfilehash: 890441987eb0f08d67afe8a7f231c9a534c59a7f
ms.sourcegitcommit: 7fe8daf07013d7c532f128a3ae3bbf51d1b2aac9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/11/2019
ms.locfileid: "31809420"
---
# <a name="audio-conferencing-subscription-dial-outcall-me-at-benefit"></a>Assinatura de conferência de áudio "Discagem externa" / "Chamar-Me às" benefício

## <a name="microsoft-teams-and-skype-for-business-pstn-audio-conferencing"></a>As equipes da Microsoft e Skype para conferência de áudio de PSTN de negócios

Um [recurso de discagem complementar](complimentary-dial-out-period.md) que será finalizado em 30 de novembro de 2019 foram fornecidos aos clientes. Beginning 1 de dezembro de 2019, cada inscrição de serviços de audioconferência fornece 60 minutos por usuário por mês para qualquer um dos países zona A conforme descrito neste documento. O tamanho do seu pool de minuto de discagem de Inquilino é baseado em licenças *atribuídas* e não adquiriu licenças. Esse benefício é aplicável a licenças de *assinatura mensal* de conferência de áudio e não se estende para licenças de pagamento por minuto de conferência de áudio. 

## <a name="audio-conferencing-dial-out-from-a-meeting--call-me-at-details"></a>Áudio conferência "Discar a partir de uma reunião" & "Chamar-Me às" detalhes

Para os clientes a adotar o nosso serviço de conferência de áudio, a Microsoft fornece a capacidade de discar a partir de reuniões organizadas por usuários atribuídos a uma licença de inscrição de conferência de áudio. Chamadas de discagem para países não incluídos na lista de país "Zona A" são cobradas por minuto usando créditos de comunicações. Para chamadas de discagem que são cobradas por minuto (chamadas excedendo o pool minuto de discagem de locatário ou chamadas para destinos não estejam na lista zona A país), as chamadas e suas taxas de associado se baseiam o destino da chamada e não a país do organizador de residência ou o participante da reunião iniciando a chamada de discagem. Por exemplo, uma chamada de discagem de conferência de áudio para um número de telefone na França, que é um país zona A, será cobrada com a mesma taxa por minuto se ele foram iniciado por um participante de reunião na França, Estados Unidos ou Zimbábue. 


|Local de uso de licença de organizador de reunião |Destino discado |Posso usar Meus minutos de pool de discagem minuto?|Eu preciso créditos de comunicação?|
|---------|---------|---------|---------|
|Estados Unidos |Estados Unidos |Sim (país zona A) |Sim, *depois* consumindo o pool de minuto locatário         |
|Estados Unidos |Reino Unido|Sim (país zona A) |  Sim, *depois* consumindo o pool de minuto locatário       |
|Estados Unidos     |Zimbábue|    Não     |     Sim em *todas as* chamadas    |
|Reino Unido     |Reino Unido|Sim (país zona A) |  Sim, *depois* consumindo o pool de minuto locatário       |
|Reino Unido     |Estados Unidos |Sim (país zona A) |  Sim, *depois* consumindo o pool de minuto locatário       |
|Reino Unido     |Zimbábue|    Não     |   Sim em *todas as* chamadas      |
|Zimbábue     |Zimbábue|    Não     |    Sim em *todas as* chamadas     |
|Zimbábue     |Estados Unidos | Sim (país zona A) | Sim, *depois* consumindo o pool de minuto locatário        |
|Zimbábue     |Reino Unido | Sim (país zona A) | Sim, *depois* consumindo o pool de minuto locatário        |
|Ilhas Cook     |Ilhas Cook |   Não      |    Sim em *todas as* chamadas     |
|Ilhas Cook     |Estados Unidos  | Sim (país zona A) |  Sim, *depois* consumindo o pool de minuto locatário       |
|Ilhas Cook     |Reino Unido | Sim (país zona A) | Sim, *depois* consumindo o pool de minuto locatário        |
|    |         |         |         |

## <a name="how-are-minute-pools-calculated"></a>Como são calculados os pools minutos?

Considere o exemplo a seguir. Um cliente adquiriu licenças de assinatura de conferência de áudio 115 e tem 10 usuários nos Estados Unidos, 100 usuários no Reino Unido e 5 usuários no Zimbábue, tudo isso com licenças de assinatura de audioconferência atribuídas. Todos os 115 usuários compartilham um pool de (115 usuários x 60 min = 6,900 conferência discar check-out minutos por mês do calendário) para fazer chamadas de saída para qualquer da zona países, *independentemente* de onde o organizador da reunião é licenciado ou fisicamente localizado. Por exemplo, um organizador de reunião Zimbábue poderão discar para qualquer um dos países zona A até o limite de pool minuto. 

- Todas as chamadas excedendo 6,900 minutos por mês do calendário são cobradas por minuto usando créditos de comunicações em nossas taxas publicadas para esse destino. (Observação: O cliente deve configurar [Créditos de comunicações](what-are-communications-credits.md) e atribuir a licença créditos de comunicação para o organizador da reunião.)
- Todas as chamadas de saída para destinos não estejam na lista zona A país são cobradas por minuto usando créditos de comunicações em nossas taxas publicadas para esse destino (desde que o cliente tiver configurado créditos de comunicações e atribuído a licença créditos de comunicações ao organizador da reunião).

## <a name="how-can-i-monitor-minute-pool-usage"></a>Como monitorar o uso do pool minuto?

- Você pode monitorar o uso em relação a seu pool de minuto de discagem no Skype "herdado" para o Centro de administração de negócios. No Microsoft Teams Admin Center, navegue até o **portal herdada** > **relatórios** > **PSTN minuto Pools**. O minuto de discagem de zona A pool será rotulada no relatório como "Chamadas de saída para países de uma zona."
- Notificações por email serão enviadas para todos os administradores de Inquilino de um determinado cliente quando a utilização do pool de minutos de discagem de locatário atingiu 80% e 100%.

Para obter informações adicionais sobre comunicação créditos, consulte [Créditos de comunicações](what-are-communications-credits.md).


|Países zona A |
|---------|
|Austrália      |
|Áustria     |
|Bélgica     |
|Brasil     |
|Bulgária     |
|Canadá     |
|China     |
|Croácia     |
|República Tcheca      |
|Dinamarca     |
|Estônia     |
|Finlândia     |
|França     |
|Alemanha     |
|Grécia     |
|Hong-Kong     |
|Hungria     |
|Índia     |
|Irlanda     |
|Itália     |
|Japão     |
|Luxemburgo      |
|Malásia     |
|México     |
|Países Baixos     |
|Nova Zelândia     |
|Noruega     |
|Polônia     |
|Portugal     |
|Porto Rico     |
|Romênia     |
|Rússia     |
|Cingapura     |
|República da Eslováquia     |
|Eslovênia     |
|África do Sul     |
|Coreia do Sul     |
|Espanha     |
|Suécia     |
|Suíça     |
|Taiwan     |
|Tailândia     |
|Estados Unidos     |
|Reino Unido|
||

## <a name="related-topics"></a>Tópicos relacionados

[Disponibilidade da Audioconferência e dos Planos de Chamadas por país e região](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)