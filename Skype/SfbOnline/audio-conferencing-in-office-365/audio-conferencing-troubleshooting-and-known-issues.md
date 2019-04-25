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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Obtenha uma lista de problemas conhecidos ao usar o Microsoft como seu provedor de conferência discada, status e algumas soluções alternativas. '
ms.openlocfilehash: 997cc5007df35b307cb714b891bc60764bd4a645
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229180"
---
# <a name="audio-conferencing-troubleshooting-and-known-issues"></a>Solução de problemas e problemas conhecidos da audioconferência

 **Este artigo destina-se Skype para usuários comerciais usando o Microsoft como seu provedor de serviços de audioconferência. Ela não se aplica aos clientes que estão usando um provedor de serviços de audioconferência de terceiros (ACP).**
  
## <a name="troubleshooting-and-known-issues"></a>Problemas conhecidos e solução de problemas

Conferência de áudio que usa o Microsoft que o provedor de serviços de audioconferência tenha problemas atuais que estão sendo rastreados e ativamente investigados e serão potencialmente resolvidos quando o recurso é atualizado em futuras versões do Office 365.
  
No momento, use isso como uma referência ao solucionar possíveis problemas com a obtenção de conferência de áudio configurado e funcionando para as pessoas que usam o Skype para negócios em sua organização.

|**Problema**|**Comportamento/Sintomas**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Notificações de entrada e saída são ativadas quando uma reunião é iniciado, mas eles estiver desativados logo depois do início da reunião.  <br/> |Por padrão, as notificações de entrada e saída estão desabilitadas para reuniões, onde os participantes ingressar de ambos os Skype para aplicativos de negócios e quando eles discam. Você pode habilitar os comunicados nas **Opções de reunião Skype** no Skype para o aplicativo de negócios. Em uma reunião na qual todos os participantes discam para ingressar, as notificações de entrada e saída estão habilitadas por padrão, pois a lista de participantes não está disponível para ninguém. Quando uma reunião foi iniciada com somente os participantes chamando em, a entrada e saída notificações serão ativadas, mas quando um participante junções usando um Skype para o aplicativo de negócios, as notificações será desativado. Quando desativado, as notificações podem estar habilitadas novamente usando as **Opções de reunião do Skype** no Skype para o aplicativo de negócios. <br/> |Não há solução alternativa.  <br/> |8/30/2017  <br/> |
|Se um usuário é provisionado na primeira vez por sendo atribuído a uma licença E5, talvez seja possível para o e-mail de boas vindas de conferência de áudio não sejam entregues ao usuário se a caixa de correio não está habilitada.  <br/> |Se isso acontecer, você sempre pode reenviar as informações de conferência de áudio do usuário usando **conferência de áudio** no Skype para centro de administração de negócios ou usando o PowerShell. Consulte [Habilitar ou desabilitar o envio de emails ao alteram as configurações de conferência de áudio](enable-or-disable-sending-emails-when-their-settings-change.md).  <br/> **Observação:** Para reenviar o PIN de conferência de áudio para o usuário, o PIN deve ser redefinido. Isso também pode ser feito usando a **conferência de áudio** no Skype para centro de administração de negócios ou usando o PowerShell.          |Não há solução alternativa.  <br/> |8/30/2017  <br/> |
|Chamadas de conferência de áudio poderá demorar até 24 horas para mostrar os relatórios de uso.  <br/> |Que queremos encaminhar para fazer melhorias nesta área no serviço futuras atualizações.  <br/> |Não há solução alternativa.  <br/> |8/30/2017  <br/> |
|Quando um chamador disca para uma ponte de conferência após a reunião foi bloqueada por um Skype para o usuário de negócios, não há uma notificação no Skype para aplicativos de negócios informando que o usuário está aguardando no lobby.  <br/> |Atualmente isso é intencional, mas levaremos em conta o feedback sobre o suporte a esse recurso em atualizações futuras do serviço.  <br/> |Não há solução alternativa.  <br/> |8/30/2017  <br/> |
   
## <a name="related-topics"></a>Tópicos relacionados

[Experimentar ou comprar a audioconferência no Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
