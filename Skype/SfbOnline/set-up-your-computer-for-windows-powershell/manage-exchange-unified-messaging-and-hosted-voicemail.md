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
description: Use o PowerShell para gerenciar recursos de Unificação de Mensagens do Exchange, como Atendedor Automático e Acesso para Assinantes e caixa postal hospedada no Skype for Business Online.
ms.openlocfilehash: 393b0a43cb55462006ef7701396a3b7840032fb4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113197"
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a>Gerenciar a Unificação de Mensagens do Exchange e a caixa postal hospedada

Você pode gerenciar a Unificação de Mensagens do Exchange e a caixa postal hospedada no Skype for Business Online usando um conjunto de cmdlets.
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a>Gerenciar a unificação de mensagens do Exchange e a caixa postal hospedada

Os cmdlets a seguir podem ser usados para gerenciar a Unificação de Mensagens do Exchange (UM) e políticas de caixa postal hospedadas:
  

| **Cmdlet**                                                                                                                                                                                                                                                                                                                        | **Descrição**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Get-CsExUmContact](/powershell/module/skype/Get-CsExUmContact) <br/><br/> [New-CsExUmContact](/powershell/module/skype/New-CsExUmContact) <br/> <br/>[Remove-CsExUmContact](/powershell/module/skype/Remove-CsExUmContact) <br/> <br/>[Set-CsExUmContact](/powershell/module/skype/Set-CsExUmContact) <br/> | Cria e gerencia objetos de contato usados para Atendedor Automático e serviços de Acesso para Assinantes, quando a UM do Exchange é um serviço hospedado.  <br/><br/> O Skype for Business Online funciona com a UM do Exchange para fornecer vários recursos relacionados à voz, incluindo Atendedor Automático e Acesso para Assinantes. Atendedor Automático fornece uma maneira de as chamadas serem atendidas automaticamente e roteada para a pessoa correta. O Acesso para Assinante permite que os usuários se conectem à UM do Exchange e recuperem emails, mensagens de voz, contatos e informações de calendário.  <br/><br/> Quando a UM do Exchange é fornecida como um serviço hospedado, os objetos de contato usados para os serviços Atendedor Automático e Acesso para Assinantes devem ser criados usando o Microsoft PowerShell. Esses objetos são criados e gerenciados usando os cmdlets **CsExUmContact.** <br/> |
| [Get-CSHostedVoicemailPolicy](/powershell/module/skype/Grant-CsHostedVoicemailPolicy) <br/> <br/>[Grant-CSHostedVoicemailPolicy](/powershell/module/skype/Set-CsTenantPublicProvider) <br/>                                                                                                                                                | Gerencia políticas de caixa postal hospedadas usadas na organização. As políticas de caixa postal hospedadas especificam como as chamadas não respondidas são roteadas para o serviço de UM do Exchange. Essas políticas afetam apenas os usuários que foram habilitados para a caixa postal hospedada da UM do Exchange.  <br/><br/> Para verificar se um usuário está habilitado para caixa postal hospedada, execute um comando semelhante ao seguinte no prompt do PowerShell.  <br/> \`Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"                                                                                                                                                                                                                                                                                                                                                           |

## <a name="related-topics"></a>Tópicos relacionados
[Configurar seu computador para gerenciamento do skype for business online usando o Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
