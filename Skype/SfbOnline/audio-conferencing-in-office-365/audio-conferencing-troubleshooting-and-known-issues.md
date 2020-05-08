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
description: 'Obtenha uma lista de problemas conhecidos ao usar a Microsoft como provedor de conferência discada, status e soluções alternativas. '
ms.openlocfilehash: fba5bfff687121c7b1b64c0e51233ccb576497e2
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164511"
---
# <a name="audio-conferencing-troubleshooting-and-known-issues"></a>Solução de problemas e problemas conhecidos da audioconferência

 **Este artigo se destina a usuários do Skype for Business que usam a Microsoft como provedor de serviços de audioconferência. Ele não se aplica aos clientes que usam o ACP (provedor de serviços de audioconferência) de terceiros.**
  
## <a name="troubleshooting-and-known-issues"></a>Solução de problemas e problemas conhecidos

A conferência de áudio que usa a Microsoft como provedor de serviços de audioconferência tem problemas atuais que estão sendo rastreados e investigados ativamente e serão potencialmente resolvidos quando o recurso for atualizado em versões futuras do Microsoft 365.
  
Por enquanto, use-o como referência quando estiver solucionando problemas em potencial com a configuração de videoconferências e como trabalhar para as pessoas que usam o Skype for Business em sua organização.

|**Problema**|**Comportamento/Sintomas**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|As notificações de entrada e saída são ativadas quando uma reunião é iniciada, mas elas são desativadas logo após o início da reunião.  <br/> |Por padrão, as notificações de entrada e de saída são desabilitadas para reuniões em que os participantes se unem de ambos os aplicativos do Skype for Business e quando eles discam. Você pode habilitar os comunicados nas **Opções de reunião do Skype** no aplicativo Skype for Business. Em uma reunião na qual todos os participantes discam para ingressar, as notificações de entrada e saída estão habilitadas por padrão, pois a lista de participantes não está disponível para ninguém. Quando uma reunião tiver começado somente a chamada de participantes, as notificações de entrada e saída serão ativadas, mas quando um participante se associar usando um aplicativo Skype for Business, as notificações serão desativadas. Quando desligado, as notificações podem ser ativadas novamente usando **as opções de reunião do Skype** no aplicativo Skype for Business. <br/> |Não há solução alternativa.  <br/> |8/30/2017  <br/> |
|Se um usuário for provisionado pela primeira vez ao receber uma licença e5, talvez seja possível que o email de boas-vindas da videoconferência não seja entregue ao usuário se a caixa de correio não estiver habilitada.  <br/> |Se isso acontecer, você sempre poderá reenviar as informações de conferência de áudio do usuário usando a **videoconferência** no centro de administração do Skype for Business ou usando o PowerShell. Consulte [habilitar ou desabilitar o envio de emails quando as configurações de audioconferência forem alteradas](enable-or-disable-sending-emails-when-their-settings-change.md).  <br/> **Observação:** Para reenviar o PIN da conferência de áudio para o usuário, o PIN deve ser redefinido. Isso também pode ser feito usando **conferências de áudio** no centro de administração do Skype for Business ou usando o PowerShell.          |Não há solução alternativa.  <br/> |8/30/2017  <br/> |
|As chamadas de audioconferência podem levar até 24 horas para serem exibidas nos relatórios de uso.  <br/> |Estamos ansiosos para fazer melhorias nessa área em futuras atualizações do serviço.  <br/> |Não há solução alternativa.  <br/> |8/30/2017  <br/> |
|Quando um chamador disca para uma ponte de conferência após o bloqueio da reunião por um usuário do Skype for Business, não há uma notificação no aplicativo Skype for Business informando que o usuário está aguardando no lobby.  <br/> |Atualmente isso é intencional, mas levaremos em conta o feedback sobre o suporte a esse recurso em atualizações futuras do serviço.  <br/> |Não há solução alternativa.  <br/> |8/30/2017  <br/> |
|Um usuário do Skype for Business Server (local) que atribuiu a licença de conferência de áudio antes de 1º de março de 2019 pode não ver as coordenadas de discagem nos convites de reunião.  <br/> |Provisionar usuários do Skype for Business Server para Team não há suporte para conferências de áudio até esta data. Agora ele tem suporte e é um componente de [reuniões primeiro](https://docs.microsoft.com/microsoftteams/meetings-first). O usuário deve ter uma licença do teams.  <br/> |O pipeline de provisionamento precisa ser reativado. Remova a licença de audioconferência do usuário, aguarde algumas horas e reatribua a licença.  <br/> |1/3/2019  <br/> |
   
## <a name="related-topics"></a>Tópicos relacionados

[Experimentar ou comprar videoconferências no Microsoft 365 ou no Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
