---
title: Gerenciar a Unificação de Mensagens do Exchange e a caixa postal hospedada
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 707198df-df85-4833-9c15-aa29b71f085c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: Use o PowerShell para gerenciar recursos de Unificação de mensagens do Exchange, como atendedor automático e acesso do assinante e correio de voz hospedado no Skype for Business online.
ms.openlocfilehash: d0c2ff8cad705a2d00685e2c6935616ab8d64ac9
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692676"
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a>Gerenciar a Unificação de Mensagens do Exchange e a caixa postal hospedada

Você pode gerenciar a Unificação de mensagens do Exchange e o correio de voz hospedado no Skype for Business online usando um conjunto de cmdlets.
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a>Gerenciar a Unificação de mensagens do Exchange e a caixa postal hospedada

Os cmdlets a seguir podem ser usados para gerenciar as políticas de correio unificado do Exchange e de correio de voz hospedado:
  

| **Cmdlet**                                                                                                                                                                                                                                                                                                                        | **Descrição**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Get-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849628) <br/><br/> [New-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849629) <br/> <br/>[Remove-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849630) <br/> <br/>[Set-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849631) <br/> | Cria e gerencia objetos de contato usados para serviços de atendedor automático e de acesso ao Assinante, quando o Exchange UM é um serviço hospedado.  <br/><br/> O Skype for Business online funciona com o Exchange UM para fornecer vários recursos relacionados à voz, incluindo atendedor automático e acesso do Assinante. O atendedor automático fornece uma maneira de as chamadas serem respondidas automaticamente e encaminhadas para a pessoa correta. O acesso ao Assinante permite que os usuários se conectem ao Exchange UM e recuperem emails, mensagens de voz, contatos e informações de calendário.  <br/><br/> Quando o Exchange UM é fornecido como um serviço hospedado, objetos de contato usados para o atendedor automático e serviços de acesso ao Assinante devem ser criados usando o Microsoft PowerShell. Esses objetos são criados e gerenciados usando cmdlets **CsExUmContact** . <br/> |
| [Get-CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849633) <br/> <br/>[Grant-CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849602) <br/>                                                                                                                                                | Gerencia as políticas de correio de voz hospedadas usadas na organização. As políticas de correio de voz hospedadas especificam como as chamadas não atendidas são roteadas para o serviço UM do Exchange. Essas políticas afetam somente os usuários que foram habilitados para o correio de voz hospedado para UM Exchange UM.  <br/><br/> Para verificar se um usuário está habilitado para correio de voz hospedado, execute um comando semelhante ao seguinte no prompt do PowerShell.  <br/> \`Get-CsOnlineUser-Identity "kenmyer@litwareinc.com"                                                                                                                                                                                                                                                                                                                                                           |

## <a name="related-topics"></a>Tópicos relacionados
[Configurar seu computador para o gerenciamento do Skype for Business online usando o Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 
