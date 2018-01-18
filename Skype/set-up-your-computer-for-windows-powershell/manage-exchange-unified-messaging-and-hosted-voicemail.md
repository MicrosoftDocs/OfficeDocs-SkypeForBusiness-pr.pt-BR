---
title: "Gerenciar a Unificação de mensagens do Exchange e hospedadas de caixa postal"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 707198df-df85-4833-9c15-aa29b71f085c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: PowerShell
description: "Use o PowerShell para gerenciar recursos de Unificação de mensagens do Exchange, como o atendedor automático e acesso ao assinante e caixa postal hospedada no Skype para negócios Online."
ms.openlocfilehash: a5f358d06ed7c7e805aeffbce6a6898cc2a86b73
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2017
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a>Gerenciar a Unificação de mensagens do Exchange e hospedadas de caixa postal

Você pode gerenciar a Unificação de mensagens do Exchange e hospedado de caixa postal na Skype para Business Online por meio de um conjunto de cmdlets.
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a>Gerenciar o Exchange unificada messaging e hospedadas de caixa postal

Os cmdlets a seguir podem ser usados para gerenciar o Exchange Unified Messaging (UM) e diretivas de caixa postal hospedada:
  
|**Cmdlet**|**Descrição**|
|:-----|:-----|
|[Get-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849628) <br/><br/> [New-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849629) <br/> <br/>[Remove-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849630) <br/> <br/>[Set-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849631) <br/> |Cria e gerencia os objetos de contato usados para serviços de atendedor automático e acesso do assinante, quando o UM do Exchange é um serviço hospedado.  <br/><br/> Skype para Business Online funciona com UM do Exchange para fornecer várias capacidades relacionadas à voz, incluindo o atendedor automático e acesso ao assinante. Atendedor automático oferece uma maneira para chamadas automaticamente ser atendida e roteadas para a pessoa correta. Acesso ao assinante permite aos usuários se conectar a UM do Exchange e recuperar mensagens de voz, email, contatos e informações de calendário.  <br/><br/> Quando UM do Exchange é fornecido como um serviço hospedado, usados para os serviços de atendedor automático e acesso ao assinante de objetos de contato devem ser criados usando o Microsoft PowerShell. Esses objetos são criados e gerenciados usando os cmdlets **CsExUmContact** . <br/> |
|[Get-CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849633) <br/> <br/>[Grant-CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849602) <br/> |Gerencia políticas de caixa postal hospedada usadas na organização. As políticas de caixa postal hospedada especificam como respondidas são roteadas para o serviço UM do Exchange. Essas diretivas afetam somente os usuários que tiverem sido habilitados para UM do Exchange hospedado de caixa postal.  <br/><br/> Para verificar se um usuário está habilitado para caixa postal hospedada, execute um comando semelhante ao seguinte prompt do PowerShell.  <br/> ' Get-CsOnlineUser-Identity "kenmyer@litwareinc.com" | Select-Object HostedVoiceMail'|
   

## <a name="related-topics"></a>Tópicos relacionados
[Configurar seu computador e Skype para gerenciamento online de negócios usando o Windows PowerShell](set-up-your-computer-for-windows-powershell.md)