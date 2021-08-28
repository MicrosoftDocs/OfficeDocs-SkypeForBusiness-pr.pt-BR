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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: Use o PowerShell para gerenciar Exchange de Unificação de Mensagens, como Atendedor Automático e Acesso para Assinantes e caixa postal hospedada no Skype for Business Online.
ms.openlocfilehash: bb7aa3dc025551fe2759efe3f4bb35ca0dc7ae17
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58601996"
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a>Gerenciar a Unificação de Mensagens do Exchange e a caixa postal hospedada

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Você pode gerenciar Exchange Unificação de Mensagens e caixa postal hospedada no Skype for Business Online usando um conjunto de cmdlets.
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a>Gerenciar Exchange unificação de mensagens e caixa postal hospedada

Os cmdlets a seguir podem ser usados para gerenciar Exchange Unificação de Mensagens (UM) e políticas de caixa postal hospedadas:
  

| **Cmdlet**                                                                                                                                                                                                                                                                                                                        | **Descrição**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Get-CsExUmContact](/powershell/module/skype/Get-CsExUmContact) <br/><br/> [New-CsExUmContact](/powershell/module/skype/New-CsExUmContact) <br/> <br/>[Remove-CsExUmContact](/powershell/module/skype/Remove-CsExUmContact) <br/> <br/>[Set-CsExUmContact](/powershell/module/skype/Set-CsExUmContact) <br/> | Cria e gerencia objetos de contato usados para Atendedor Automático e serviços de Acesso para Assinantes, quando Exchange UM é um serviço hospedado.  <br/><br/> Skype for Business Online funciona com Exchange UM para fornecer vários recursos relacionados à voz, incluindo o Atendedor Automático e o Acesso para Assinantes. Atendedor Automático fornece uma maneira de as chamadas serem atendidas automaticamente e roteada para a pessoa correta. O Acesso para Assinante permite que os usuários se conectem Exchange UM e recuperem emails, mensagens de voz, contatos e informações de calendário.  <br/><br/> Quando Exchange UM é fornecido como um serviço hospedado, os objetos de contato usados para os serviços Atendedor Automático e Acesso para Assinantes devem ser criados usando o Microsoft PowerShell. Esses objetos são criados e gerenciados usando os cmdlets **CsExUmContact.** <br/> |
| [Get-CSHostedVoicemailPolicy](/powershell/module/skype/Grant-CsHostedVoicemailPolicy) <br/> <br/>[Grant-CSHostedVoicemailPolicy](/powershell/module/skype/Set-CsTenantPublicProvider) <br/>                                                                                                                                                | Gerencia políticas de caixa postal hospedadas usadas na organização. As políticas de caixa postal hospedadas especificam como as chamadas não respondidas são roteadas para o serviço Exchange UM. Essas políticas afetam apenas os usuários que foram habilitados para Exchange caixa postal hospedada da UM.  <br/><br/> Para verificar se um usuário está habilitado para caixa postal hospedada, execute um comando semelhante ao seguinte no prompt do PowerShell.  <br/> \`Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"                                                                                                                                                                                                                                                                                                                                                           |

## <a name="related-topics"></a>Tópicos relacionados
[Configurar seu computador para gerenciamento do skype for business online usando Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
