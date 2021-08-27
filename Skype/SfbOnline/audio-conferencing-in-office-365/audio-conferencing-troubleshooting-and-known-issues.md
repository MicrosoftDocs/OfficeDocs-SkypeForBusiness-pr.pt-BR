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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Obter uma lista de problemas conhecidos ao usar a Microsoft como provedor de conferência discado, status e algumas soluções alternativas. '
ms.openlocfilehash: 6304de40d7c7cd9f3d798af2050276ee6fe2b104
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58578155"
---
# <a name="audio-conferencing-troubleshooting-and-known-issues"></a>Solução de problemas e problemas conhecidos da audioconferência

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

 **Este artigo é para usuários Skype for Business usando a Microsoft como provedor de audioconferência. Ele não se aplica aos clientes que estão usando um provedor de audioconferência de terceiros (ACP).**
  
## <a name="troubleshooting-and-known-issues"></a>Solução de problemas e problemas conhecidos

A audioconferência que usa a Microsoft como provedor de audioconferência tem problemas atuais que estão sendo rastreados e investigados ativamente e serão potencialmente resolvidos quando o recurso for atualizado em versões futuras do Microsoft 365.
  
Por enquanto, use isso como uma referência quando você estiver solucionando possíveis problemas com a configuração da Audioconferência e o trabalho para as pessoas que usam Skype for Business em sua organização.

|**Problema**|**Comportamento/Sintomas**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|As notificações de entrada e saída são ativas quando uma reunião é iniciada, mas elas são desligadas logo após o início da reunião.  <br/> |Por padrão, as notificações de entrada e de saída são desabilitadas para reuniões nas quais os participantes participam de aplicativos Skype for Business e quando eles discam. Você pode habilitar os anúncios no **Reunião do Skype Opções** no aplicativo Skype for Business. Em uma reunião na qual todos os participantes discam para ingressar, as notificações de entrada e saída estão habilitadas por padrão, pois a lista de participantes não está disponível para ninguém. Quando uma reunião é iniciada com apenas participantes chamando, as notificações de entrada e saída serão ativas, mas quando um participante ingressar usando um aplicativo Skype for Business, as notificações serão desligadas. Quando desligadas, as notificações podem ser habilitadas novamente **usando Reunião do Skype Opções** no Skype for Business aplicativo. <br/> |Não há solução alternativa.  <br/> |8/30/2017  <br/> |
|Se um usuário for provisionado pela primeira vez ao receber uma licença E5, pode ser possível que o email de boas-vindas de Audioconferência não seja entregue ao usuário se a caixa de correio não estiver habilitada.  <br/> |Se isso acontecer, você sempre poderá ressendê-lo usando **Audioconferência** no centro de administração do Skype for Business ou usando o PowerShell. Consulte [Habilitar ou desabilitar o envio de emails quando as configurações de Audioconferência mudarem](enable-or-disable-sending-emails-when-their-settings-change.md).  <br/> **Observação:** Para reajustar o PIN de audioconferência para o usuário, o PIN precisa ser redefinido. Isso também pode ser feito usando **Audioconferência** no centro de administração Skype for Business ou usando o PowerShell.          |Não há solução alternativa.  <br/> |8/30/2017  <br/> |
|As chamadas de audioconferência podem levar até 24 horas para aparecer nos relatórios de uso.  <br/> |Estamos ansiosos para fazer melhorias nessa área em futuras atualizações de serviço.  <br/> |Não há solução alternativa.  <br/> |8/30/2017  <br/> |
|Quando um chamador disca para uma ponte de conferência após a reunião ser bloqueada por um usuário Skype for Business, não há uma notificação no aplicativo Skype for Business informando que o usuário está aguardando no lobby.  <br/> |Atualmente isso é intencional, mas levaremos em conta o feedback sobre o suporte a esse recurso em atualizações futuras do serviço.  <br/> |Não há solução alternativa.  <br/> |8/30/2017  <br/> |
|Um usuário Skype for Business Server (local) atribuído à licença de Audioconferência antes de 1º de março de 2019, pode não ver a discagem em coordenadas em seus convites de reunião.  <br/> |O provisionamento Skype for Business Server usuários para Teams Audioconferência não foi suportado até essa data. Agora, ele tem suporte e é um componente das [Reuniões Primeiro.](/microsoftteams/meetings-first) O usuário deve ter uma Teams de usuário.  <br/> |O pipeline de provisionamento precisa ser reativado. Remova a licença de Audioconferência do usuário, aguarde algumas horas e reatribua a licença.  <br/> |1/3/2019  <br/> |
   
## <a name="related-topics"></a>Tópicos relacionados

[Experimente ou compre Audioconferência em Microsoft 365 ou Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
