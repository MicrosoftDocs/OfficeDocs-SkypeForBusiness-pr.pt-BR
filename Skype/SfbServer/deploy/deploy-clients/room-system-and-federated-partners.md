---
title: Parceiros federados do Sistema de Salas do Skype e Skype for Business
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: Leia este tópico para saber como configurar o Sistema de Salas do Skype para parceiros federados do Skype for Business.
ms.openlocfilehash: e954bf5d7586c651d9d045b2d428f86f01de8a30
ms.sourcegitcommit: d3c3467320a2928d3bad14a1a44a31ee5a9a988c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/23/2018
ms.locfileid: "25699541"
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