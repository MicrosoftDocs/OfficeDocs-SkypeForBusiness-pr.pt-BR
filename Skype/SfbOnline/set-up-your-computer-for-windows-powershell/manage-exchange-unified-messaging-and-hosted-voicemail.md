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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: Use o PowerShell para gerenciar recursos de Unificação de mensagens do Exchange, como o atendedor automático e acesso ao assinante e caixa postal hospedada no Skype para negócios Online.
ms.openlocfilehash: 02fda8c315807899983741f94c1f825de1ebf1a9
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873507"
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a>Gerenciar a Unificação de Mensagens do Exchange e a caixa postal hospedada

Você pode gerenciar a Unificação de mensagens do Exchange e hospedado de caixa postal na Skype para Business Online por meio de um conjunto de cmdlets.
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a>Gerenciar o Exchange unificada messaging e hospedadas de caixa postal

Os cmdlets a seguir podem ser usados para gerenciar o Exchange Unified Messaging (UM) e diretivas de caixa postal hospedada:
  

| **Cmdlet**                                                                                                                                                                                                                                                                                                                        | **Descrição**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Get-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849628) <br/><br/> [New-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849629) <br/> <br/>[Remove-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849630) <br/> <br/>[Set-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849631) <br/> | Cria e gerencia os objetos de contato usados para serviços de atendedor automático e acesso do assinante, quando o UM do Exchange é um serviço hospedado.  <br/><br/> Skype para Business Online funciona com UM do Exchange para fornecer várias capacidades relacionadas à voz, incluindo o atendedor automático e acesso ao assinante. Atendedor automático oferece uma maneira para chamadas automaticamente ser atendida e roteadas para a pessoa correta. Acesso ao assinante permite aos usuários se conectar a UM do Exchange e recuperar mensagens de voz, email, contatos e informações de calendário.  <br/><br/> Quando UM do Exchange é fornecido como um serviço hospedado, usados para os serviços de atendedor automático e acesso ao assinante de objetos de contato devem ser criados usando o Microsoft PowerShell. Esses objetos são criados e gerenciados usando os cmdlets **CsExUmContact** . <br/> |
| [Get-CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849633) <br/> <br/>[Grant-CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849602) <br/>                                                                                                                                                | Gerencia políticas de caixa postal hospedada usadas na organização. As políticas de caixa postal hospedada especificam como respondidas são roteadas para o serviço UM do Exchange. Essas diretivas afetam somente os usuários que tiverem sido habilitados para UM do Exchange hospedado de caixa postal.  <br/><br/> Para verificar se um usuário está habilitado para caixa postal hospedada, execute um comando semelhante ao seguinte prompt do PowerShell.  <br/> \`Get-CsOnlineUser-Identity "kenmyer@litwareinc.com"                                                                                                                                                                                                                                                                                                                                                           |

## <a name="related-topics"></a>Tópicos relacionados
[Configurar seu computador e Skype para gerenciamento online de negócios usando o Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 
