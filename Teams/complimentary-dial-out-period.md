---
title: Período de discagem gratuita
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, OscarR
ms.topic: conceptual
ms.assetid: dc6e95cd-51e8-49ca-bcd3-78dc9dae486a
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: None
f1.keywords:
- CSH
ms.custom:
- Legal
- seo-marvel-mar2020
description: Saiba mais sobre o período de discagem gratuita do plano de chamadas do Microsoft 365 ou do Office 365 e do Office 365 audioconferência no Microsoft Teams.
ms.openlocfilehash: 0f40e35e30de5698ffcb4bf9592868685d8223ed
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918877"
---
# <a name="audio-conferencing-complimentary-dial-out-period"></a>Período complementar de discagem de audioconferência

## <a name="skype-for-business-pstn-services"></a>Serviços PSTN do Skype for Business

Os clientes podem usar o Microsoft 365 ou o plano de chamadas do Office 365 e o plano de áudio do Office 365, conforme permitido nos termos de uso dos serviços PSTN do Skype for Business Online e no contrato de licenciamento por volume do cliente. Os termos de uso dos serviços PSTN podem ser encontrados em [termos de licenciamento e documentação](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=2&amp;Keyword=PSTN).
  
### <a name="end-of-complimentary-dial-out-period"></a>Fim do período de discagem grátis

A funcionalidade de discagem gratuita foi encerrada em 1º de dezembro de 2019. Para obter mais informações, consulte [assinatura de áudio da conferência discada e ligue para mim em benefício](audio-conferencing-subscription-dial-out.md). 

Esta alteração não ocorre para os países em que a assinatura de audioconferência está disponível, mas não habilitamos a configuração de créditos de comunicações no momento. Esses países específicos são Rússia, Coréia do Sul e Taiwan.

### <a name="complimentary-dial-out-period-details"></a>Detalhes do período de discagem grátis

Para os clientes que estão adotando o serviço de conferência de áudio do Microsoft 365 ou do Office 365, a Microsoft está fornecendo um benefício complementar adicional relacionado à discagem de reuniões que são organizadas por usuários que recebem uma licença de assinatura do Microsoft 365 ou do Office 365 de conferência de áudio em novembro de 2019. Durante esse período de tempo, a Microsoft permite que os organizadores da reunião ou participantes autorizados, conforme definido nas configurações da política de reunião, façam chamadas discada de dentro da reunião para números de telefone não Premium na zona do 44 em [países e regiões](audio-conferencing-zones.md). Esse benefício se aplica às licenças de assinatura mensal da conferência de áudio e não se estende às licenças de pagamento por minuto de audioconferência.

Além disso, há um limite de 900 minutos durante o período de discagem complementar da seguinte forma:

Usuários com um local de uso de licenças (o local é o local do país do usuário que é definido na área de licenciamento do centro de administração do Microsoft 365) em _qualquer_ país pode discar de uma conferência para qualquer [um dos países e regiões](audio-conferencing-zones.md)do 44 Zone. Cada usuário recebe 900 minutos por mês para _qualquer_ uma das zonas de [países e regiões](audio-conferencing-zones.md), que são agrupadas no nível do locatário. Por exemplo, um cliente comprou licenças de assinatura de audioconferência do 115 e tem 10 usuários nos EUA, 100 usuários do Reino Unido e cinco usuários na Índia, tudo com licenças de assinatura de audioconferência atribuídas a seus usuários.

- Todos os usuários do 115 compartilham um pool de (115 usuários X 900 min) = 103.500 conferência dial-out minutos por mês do calendário, que pode ser usado para fazer chamadas de saída para qualquer [uma das zonas de países e regiões](audio-conferencing-zones.md).

- Todas as chamadas que excedem os minutos de 103.500 por mês são cobradas por minuto usando créditos de comunicações em nossas tarifas publicadas para esse destino. (Observação: o locatário deve configurar créditos de comunicações e atribuir a licença de créditos de comunicações ao organizador da reunião).

- Todas as chamadas de saída para destinos que não estão na [zona uma lista de países e regiões](audio-conferencing-zones.md) são cobradas por minuto usando créditos de comunicações em nossas tarifas publicadas para esse destino (o locatário fornecido configurou créditos de comunicações e atribuiu a licença de créditos de comunicação ao organizador da reunião).

> [!NOTE]
> Você pode monitorar o uso com o pool de minutos de discagem externa no centro de administração do Skype for Business. No centro de administração do Microsoft Teams & Skype, acesse **portal herdado**  >    >  **pools de minutos PSTN**. Este pool de minutos complementares será rotulado no relatório como "chamadas de saída para a zona de países e regiões".

As notificações por email serão enviadas para todos os administradores de locatários de um determinado cliente quando a utilização do pool de minutos de discagem de locatário do locatário tiver atingido 80% e 100%.

Para chamadas discadas cobradas por minuto (chamadas que excedem o pool de minutos de discagem de locatário ou chamadas para destinos fora da lista de [países e regiões](audio-conferencing-zones.md) ), as chamadas e suas tarifas associadas se baseiam principalmente no destino da chamada e não no país ou região do organizador ou no participante que inicia a chamada de discagem. Por exemplo, uma chamada para um número de telefone na França será cobrada com a mesma taxa se for iniciada por um participante da reunião nos Estados Unidos ou uma na França.

Para obter mais informações sobre créditos de comunicação, consulte [créditos de comunicações](what-are-communications-credits.md).
     
## <a name="related-topics"></a>Tópicos relacionados

- [Disponibilidade de audioconferência e Planos de Chamadas por país e região](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [Regiões de país e região para videoconferência](audio-conferencing-zones.md)
