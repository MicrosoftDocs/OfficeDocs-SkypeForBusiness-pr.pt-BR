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
description: Use o PowerShell para gerenciar recursos de Unificação de Mensagens do Exchange, como Atendedor Automático e Acesso de Assinante, e caixa postal hospedada no Skype for Business Online.
ms.openlocfilehash: d0c2ff8cad705a2d00685e2c6935616ab8d64ac9
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692676"
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a>Gerenciar a Unificação de Mensagens do Exchange e a caixa postal hospedada

Você pode gerenciar a Unificação de Mensagens do Exchange e a caixa postal hospedada no Skype for Business Online usando um conjunto de cmdlets.
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a>Gerenciar mensagens unificadas do Exchange e caixa postal hospedada

Os cmdlets a seguir podem ser usados para gerenciar a Unificação de Mensagens do Exchange (UM) e políticas de caixa postal hospedadas:
  

| **Cmdlet**                                                                                                                                                                                                                                                                                                                        | **Descrição**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Get-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849628) <br/><br/> [New-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849629) <br/> <br/>[Remove-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849630) <br/> <br/>[Set-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849631) <br/> | Cria e gerencia objetos de contato usados para os serviços de Auto Attendant e Acesso de Assinante, quando o Exchange UM é um serviço hospedado.  <br/><br/> O Skype for Business Online funciona com o Exchange UM para fornecer vários recursos relacionados à voz, incluindo o Auto Attendant e o Acesso de Assinante. O Atender Automático fornece uma maneira de as chamadas serem atendidas e roteada automaticamente para a pessoa correta. O Acesso de Assinante permite que os usuários se conectem à UM do Exchange e recuperem emails, mensagens de voz, contatos e informações de calendário.  <br/><br/> Quando a UM do Exchange é fornecida como um serviço hospedado, os objetos de contato usados para os serviços do Auto Attendant e do Acesso de Assinante devem ser criados usando o Microsoft PowerShell. Esses objetos são criados e gerenciados usando os **cmdlets CsExUmContact.** <br/> |
| [Get-CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849633) <br/> <br/>[Grant-CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849602) <br/>                                                                                                                                                | Gerencia as políticas de caixa postal hospedadas usadas na organização. As políticas de caixa postal hospedadas especificam como as chamadas não atendidas são roteadas para o serviço da UM do Exchange. Essas políticas afetam apenas os usuários que foram habilitados para a caixa postal hospedada da UM do Exchange.  <br/><br/> Para verificar se um usuário está habilitado para a caixa postal hospedada, execute um comando semelhante ao seguinte no prompt do PowerShell.  <br/> \`Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"                                                                                                                                                                                                                                                                                                                                                           |

## <a name="related-topics"></a>Tópicos relacionados
[Configurar seu computador para gerenciamento do Skype for Business Online usando o Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 
