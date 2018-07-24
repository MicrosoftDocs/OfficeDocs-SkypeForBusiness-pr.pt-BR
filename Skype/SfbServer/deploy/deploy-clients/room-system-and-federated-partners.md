---
title: Parceiros federados do Sistema de Salas do Skype e Skype for Business
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: Leia este tópico para saber como configurar o Sistema de Salas do Skype para parceiros federados do Skype for Business.
ms.openlocfilehash: 8099b5af72d4ce8e5a8be25c7fabc8563387dd46
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20997948"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Parceiros federados do Sistema de Salas do Skype e Skype for Business
 
Leia este tópico para saber como configurar o Sistema de Salas do Skype para parceiros federados do Skype for Business.
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Parceiros federados do Sistema de Salas do Skype e Skype for Business

Sistema de sala Skype depende do Skype ingressar para o link da reunião de negócios na solicitação de reunião de calendário. O link de ingresso normalmente é encontrado no corpo de uma solicitação de reunião. No entanto, o sistema de sala de Skype depende neste link estar presentes nas propriedades da mensagem MAPI. Quando esta reunião solicitação é enviada ao organizações remotas (Skype para parceiros de negócios federado), por padrão será de sistema de sala Skype remoto da organização não mostrar link de participação da reunião no calendário. Na verdade, nenhum usuário do Outlook na organização remota poderão ingressar o Skype para reunião de negócios com o botão direito do mouse do calendário, item ou de dentro do lembrete da reunião. Eles devem abrir o convite de reunião e clique em ingressar Skype para negócios de reunião no corpo da mensagem. 
  
O motivo para esta limitação é que o Outlook e o Microsoft Exchange não usam um método especial para organizar informações para enviar mensagens pela Internet. Esse método, conhecido como Formato de Encapsulamento Neutro de Transporte (TNEF), está desabilitado por padrão para mensagens enviadas externamente de uma organização do Exchange. Para uma reunião link de ingresso apareça em um sistema de sala Skype remoto, a organização de envio deve habilitar o TNEF usando o seguinte comando:
  
```
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

Depois que o TNEF estiver habilitado para a organização remota, qualquer mensagem enviada através da Internet para a organização será enviada como um anexo no formato TNEF. Com o TNEF habilitada, quando um Skype para solicitação de reunião de negócios é enviado para o Skype para parceiro federado de negócios, Skype sala sistema será capaz de renderizar Skype a participação de reunião de negócios e usuários remotos poderão ingressar Skype para reuniões de negócios. 