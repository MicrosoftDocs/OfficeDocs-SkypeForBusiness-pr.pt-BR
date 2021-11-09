---
title: Skype Sistema de Sala e Skype for Business federados
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.openlocfilehash: ee9d7013df141cfe937f1c006a5e659a9e8a7478
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60841933"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype Sistema de Sala e Skype for Business federados
 
Leia este tópico para saber como configurar o Skype Room System para Skype for Business federados.
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype Sistema de Sala e Skype for Business federados

Skype O Sistema de Sala depende do link Ingressar Skype for Business Reunião na solicitação de reunião do calendário. O link de junção geralmente é encontrado no corpo de uma solicitação de reunião. No entanto, Skype sistema de sala depende desse link para estar presente nas propriedades MAPI da mensagem. Quando essa solicitação de reunião é enviada a organizações remotas (Skype for Business parceiros federados), por padrão, o sistema de sala Skype da organização remota não mostrará o link de junção de reunião no calendário. Na verdade, Outlook usuários da organização remota não poderão participar da reunião Skype for Business com um clique com o botão direito do mouse do item de calendário ou de dentro do lembrete da reunião. Eles devem abrir o convite da reunião e clicar em Skype for Business Reunião no corpo da mensagem. 
  
O motivo dessa limitação é que o Outlook e o Microsoft Exchange não usam um método especial para empacotar informações para o envio de mensagens pela Internet. Esse método, conhecido como Formato de Encapsulamento Neutro de Transporte (TNEF), é desabilitado por padrão para mensagens enviadas externamente de uma organização Exchange transporte. Para que um link de junção de reunião apareça em um sistema de sala Skype remoto, a organização de envio deve habilitar o TNEF usando o seguinte comando:
  
```powershell
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

Depois que o TNEF é habilitado para a organização remota, qualquer mensagem enviada pela Internet para a organização é enviada como um anexo no formato TNEF. Com o TNEF habilitado, quando uma solicitação de reunião Skype for Business for enviada ao parceiro federado do Skype for Business, o sistema de sala do Skype poderá renderizar a Reunião de Skype for Business e os usuários remotos poderão ingressar no Skype for Business reuniões. 
