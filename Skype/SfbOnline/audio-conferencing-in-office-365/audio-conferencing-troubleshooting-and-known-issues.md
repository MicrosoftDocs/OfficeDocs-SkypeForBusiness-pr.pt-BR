---
title: Solução de problemas e problemas conhecidos da audioconferência
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 72979911-5319-4de2-a275-4dd9a0f44fe6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Obter uma lista de problemas conhecidos ao usar a Microsoft como provedor de conferência discado, seu status e algumas soluções alternativas. '
ms.openlocfilehash: fba5bfff687121c7b1b64c0e51233ccb576497e2
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164511"
---
# <a name="audio-conferencing-troubleshooting-and-known-issues"></a>Solução de problemas e problemas conhecidos da audioconferência

 **Este artigo é destinado a usuários do Skype for Business que usam a Microsoft como provedor de serviços de audioconferência. Ele não se aplica aos clientes que estão usando um provedor de serviços de audioconferência (ACP) de terceiros.**
  
## <a name="troubleshooting-and-known-issues"></a>Solução de problemas e problemas conhecidos

A audioconferência que usa a Microsoft como provedor de audioconferência tem problemas atuais que estão sendo acompanhados e investigados ativamente e serão potencialmente resolvidos quando o recurso for atualizado em versões futuras do Microsoft 365.
  
Por enquanto, use isso como referência quando estiver solucionando possíveis problemas com a configuração da AudioConferência e o trabalho para as pessoas que usam o Skype for Business em sua organização.

|**Problema**|**Comportamento/Sintomas**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|As notificações de entrada e saída são ativas quando uma reunião é iniciada, mas são desligadas logo após o início da reunião.  <br/> |Por padrão, as notificações de entrada e saída são desabilitadas para reuniões nas quais os participantes insaluem de aplicativos do Skype for Business e quando discam. Você pode habilitar os comunicados nas Opções **de Reunião do Skype** no aplicativo Skype for Business. Em uma reunião na qual todos os participantes discam para ingressar, as notificações de entrada e saída estão habilitadas por padrão, pois a lista de participantes não está disponível para ninguém. Quando uma reunião começa com apenas os participantes ligando, as notificações de entrada e saída são ificadas, mas quando um participante entra usando um aplicativo do Skype for Business, as notificações são desligadas. Quando desligadas, as notificações podem ser habilitadas novamente usando as Opções de **Reunião do Skype** no aplicativo Skype for Business. <br/> |Não há solução alternativa.  <br/> |8/30/2017  <br/> |
|Se um usuário for provisionado pela primeira vez ao receber uma licença E5, talvez seja possível que o email de boas-vindas de Audioconferência não seja entregue ao usuário se a caixa de correio não estiver habilitada.  <br/> |Se isso acontecer, você sempre poderá resendê-los das informações de audioconferência do usuário usando a **Audioconferência** no Centro de administração do Skype for Business ou usando o PowerShell. Consulte [Habilitar ou desabilitar o envio de emails quando as configurações de Audioconferência mudarem.](enable-or-disable-sending-emails-when-their-settings-change.md)  <br/> **Observação:** Para resendá-lo, o PIN de audioconferência deve ser redefinido. Isso também pode ser feito usando **a Audioconferência** no Centro de administração do Skype for Business ou usando o PowerShell.          |Não há solução alternativa.  <br/> |8/30/2017  <br/> |
|As chamadas de audioconferência podem levar até 24 horas para aparecerem nos relatórios de uso.  <br/> |Estamos ansiosos para fazer melhorias nessa área em atualizações futuras do serviço.  <br/> |Não há solução alternativa.  <br/> |8/30/2017  <br/> |
|Quando um chamador disca para uma ponte de conferência depois que a reunião foi bloqueada por um usuário do Skype for Business, não há uma notificação no aplicativo Skype for Business informando que o usuário está aguardando no lobby.  <br/> |Atualmente isso é intencional, mas levaremos em conta o feedback sobre o suporte a esse recurso em atualizações futuras do serviço.  <br/> |Não há solução alternativa.  <br/> |8/30/2017  <br/> |
|Um usuário do Skype for Business Server (local) atribuiu a licença de AudioConferência antes de 1º de março de 2019, pode não ver as coordenadas de discagem em seus convites de reunião.  <br/> |O provisionamento de usuários do Skype for Business Server para Audioconferência do Teams não era suportado até essa data. Agora tem suporte e é um componente do [Meetings First.](https://docs.microsoft.com/microsoftteams/meetings-first) O usuário deve ter uma licença do Teams.  <br/> |O pipeline de provisionamento precisa ser reativado. Remova a licença de Audioconferência do usuário, aguarde algumas horas e reatribua a licença.  <br/> |1/3/2019  <br/> |
   
## <a name="related-topics"></a>Tópicos relacionados

[Experimentar ou comprar Audioconferência no Microsoft 365 ou no Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
