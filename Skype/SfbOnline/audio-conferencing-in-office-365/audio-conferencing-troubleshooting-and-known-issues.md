---
title: "Solução de conferência de áudio e problemas conhecidos"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 72979911-5319-4de2-a275-4dd9a0f44fe6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Obtenha uma lista de problemas conhecidos ao usar o Microsoft como seu provedor de conferência discada, status e algumas soluções alternativas. "
ms.openlocfilehash: 6d10e797ef052cafc22555b26a27a1aaeae1fc76
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2018
---
# <a name="audio-conferencing-troubleshooting-and-known-issues"></a>Solução de conferência de áudio e problemas conhecidos

 **Este artigo destina-se Skype para usuários empresariais e Teams da Microsoft usando o Microsoft como seu provedor de serviços de audioconferência. Ela não se aplica aos clientes que estão usando um provedor de serviços de audioconferência de terceiros (ACP).**
  
## <a name="troubleshooting-and-known-issues"></a>Problemas conhecidos e solução de problemas

Conferência de áudio que usa o Microsoft que o provedor de serviços de audioconferência tenha problemas atuais que estão sendo rastreados e ativamente investigados e serão potencialmente resolvidos quando o recurso é atualizado em futuras versões do Office 365.
  
No momento, use isso como uma referência ao solucionar possíveis problemas com a obtenção de conferência de áudio configurado e funcionando para as pessoas que usam o Skype para aplicativos de negócios ou Teams da Microsoft em sua organização.
  
### <a name="microsoft-teams-app"></a>As equipes da Microsoft app

|**Problema**|**Comportamento/sintomas**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Os chamadores da PSTN com o mesmo "número From" são mostrados como o mesmo usuário na lista de participação de reunião.  <br/> |Quando vários chamadores por PSTN ingressem em uma reunião, e seus IDs do chamador são mascarados como um único número, eles serão exibidas como um chamador único na lista de participação da reunião.  <br/> |Não há solução alternativa.  <br/> |25/9/2017  <br/> |
|Painel de informações da reunião não está aparecendo forma intermitente.  <br/> |Painel de informações da reunião pode não aparecer no cliente de equipes, quando os usuários tentam procurar para números de telefone de ponte de conferência ou ID de conferência.  <br/> |Examinar detalhes da reunião ou calendário do Outlook para exibir números de telefone de ponte de conferência ou ID de conferência.  <br/> |25/9/2017  <br/> |
|Convites de reunião de suplemento do Outlook mostram caracteres corrompidos em coordenadas PSTN para localidades fora dos EUA.  <br/> |Ao agendar reuniões privadas usando o suplemento do Outlook for Microsoft Teams em um computador com localidades fora dos EUA, coordenadas PSTN podem conter caracteres corrompidos.  <br/> |Não há solução alternativa.  <br/> |25/9/2017  <br/> |
|Discagem externa precisa usar 5 dígitos ou mais.  <br/> |Os usuários que tentarem discar a partir de uma reunião precisam digitar em 5 ou mais dígitos, mesmo que a regra de normalização do plano de discagem está disponível para normalizar discagem curto dígitos em e. 164.  <br/> |Discar digitando o número total de DID ou o formato de número local em vez do número de ramal interno.  <br/> |25/9/2017  <br/> |
|Discagem externa de controle não está aparecendo forma intermitente.  <br/> |Discagem externa controle pode não estar visível do painel de informações da reunião.  <br/> |Não há solução alternativa.  <br/> |25/9/2017  <br/> |
|ID de conferência estático não tem suportado para reuniões de Teams da Microsoft.  <br/> |Se o administrador substitui a configuração de padrão de ID de conferência dinâmico a ID de conferência estático, essa configuração não terá efeito para reuniões de Teams da Microsoft. Consulte as [IDs de conferência de áudio usando dinâmicos em sua organização](using-audio-conferencing-dynamic-ids-in-your-organization.md).  <br/> |Não há solução alternativa.  <br/> |25/9/2017  <br/> |
|As coordenadas de reunião de PSTN não estão disponíveis para Skype para usuários do local de negócios  <br/> |Se o usuário for um Skype para usuário local de negócios, atribuído com Skype para Business Online, conferência de áudio e licenças de equipes, todas as reuniões agendadas usando equipes não incluirá as coordenadas de reunião de PSTN. <br/> |Não há solução alternativa.  <br/> |2/1/2018  <br/> |
   
### <a name="skype-for-business-app"></a>Skype para o aplicativo de negócios

|**Problema**|**Comportamento/sintomas**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Notificações de entrada e saída são ativadas quando uma reunião é iniciado, mas eles estiver desativados logo depois do início da reunião.  <br/> |Por padrão, as notificações de entrada e saída estão desabilitadas para reuniões, onde os participantes ingressar de ambos os Skype para aplicativos de negócios e quando eles discam. Você pode habilitar os comunicados nas **Opções de reunião Skype** no Skype para o aplicativo de negócios. Em uma reunião na qual todos os participantes discam para ingressar, as notificações de entrada e saída estão habilitadas por padrão, pois a lista de participantes não está disponível para ninguém. Quando uma reunião foi iniciada com somente os participantes chamando em, a entrada e saída notificações serão ativadas, mas quando um participante junções usando um Skype para o aplicativo de negócios, as notificações será desativado. Quando desativado, as notificações podem estar habilitadas novamente usando as **Opções de reunião do Skype** no Skype para o aplicativo de negócios. <br/> |Não há solução alternativa.  <br/> |8/30/2017  <br/> |
|Se um usuário é provisionado na primeira vez por sendo atribuído a uma licença E5, talvez seja possível para o e-mail de boas vindas de conferência de áudio não sejam entregues ao usuário se a caixa de correio não está habilitada.  <br/> |Se isso acontecer, você sempre pode reenviar as informações de conferência de áudio do usuário usando **conferência de áudio** no Skype para centro de administração de negócios ou usando o PowerShell. Consulte [Habilitar ou desabilitar o envio de emails ao alteram as configurações de conferência de áudio](enable-or-disable-sending-emails-when-their-settings-change.md).  <br/> **Observação:** Para reenviar o PIN de conferência de áudio para o usuário, o PIN deve ser redefinido. Isso também pode ser feito usando a **conferência de áudio** no Skype para centro de administração de negócios ou usando o PowerShell.          |Não há solução alternativa.  <br/> |8/30/2017  <br/> |
|Chamadas de conferência de áudio poderá demorar até 24 horas para mostrar os relatórios de uso.  <br/> |Que queremos encaminhar para fazer melhorias nesta área no serviço futuras atualizações.  <br/> |Não há solução alternativa.  <br/> |8/30/2017  <br/> |
|Quando um chamador disca para uma ponte de conferência após a reunião foi bloqueada por um Skype para o usuário de negócios, não há uma notificação no Skype para aplicativos de negócios informando que o usuário está aguardando no lobby.  <br/> |Atualmente isso é intencional, mas levaremos em conta o feedback sobre o suporte a esse recurso em atualizações futuras do serviço.  <br/> |Não há solução alternativa.  <br/> |8/30/2017  <br/> |
   
## <a name="related-topics"></a>Tópicos relacionados

[Configurar conferência de áudio para o Skype for Business e Teams da Microsoft](set-up-audio-conferencing.md)
