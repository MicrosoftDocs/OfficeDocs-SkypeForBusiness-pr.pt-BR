---
title: Skype Room System e Skype for Business federados
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: Leia este tópico para saber como configurar o Skype Room System para Skype for Business federados.
ms.openlocfilehash: dc725acfce7e2d55758b3074df538d69ead0d6a1
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399995"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype Room System e Skype for Business federados
 
Leia este tópico para saber como configurar o Skype Room System para Skype for Business federados.
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype Room System e Skype for Business federados

Skype Room System se baseia no link Ingressar Skype for Business Reunião na solicitação de reunião do calendário. O link de junção geralmente é encontrado no corpo de uma solicitação de reunião. No entanto, Skype sistema de sala depende desse link para estar presente nas propriedades MAPI da mensagem. Quando essa solicitação de reunião é enviada a organizações remotas (Skype for Business parceiros federados), por padrão, o sistema de sala Skype da organização remota não mostrará o link de junção de reunião no calendário. Na verdade, Outlook usuários da organização remota não poderão participar da reunião Skype for Business com um clique com o botão direito do mouse do item de calendário ou de dentro do lembrete da reunião. Eles devem abrir o convite da reunião e clicar em Skype for Business Reunião no corpo da mensagem. 
  
O motivo dessa limitação é que o Outlook e o Microsoft Exchange não usam um método especial para empacotar informações para o envio de mensagens pela Internet. Esse método, conhecido como Formato de Encapsulamento Neutro de Transporte (TNEF), é desabilitado por padrão para mensagens enviadas externamente de uma organização Exchange transporte. Para que um link de junção de reunião apareça em um sistema de sala Skype remoto, a organização de envio deve habilitar o TNEF usando o seguinte comando:
  
```powershell
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

Depois que o TNEF é habilitado para a organização remota, qualquer mensagem enviada pela Internet para a organização é enviada como um anexo no formato TNEF. Com o TNEF habilitado, quando uma solicitação de reunião de Skype for Business é enviada para o parceiro federado Skype for Business, o sistema de sala do Skype poderá renderizar a Reunião de Skype for Business e os usuários remotos poderão ingressar Skype for Business reuniões. 
