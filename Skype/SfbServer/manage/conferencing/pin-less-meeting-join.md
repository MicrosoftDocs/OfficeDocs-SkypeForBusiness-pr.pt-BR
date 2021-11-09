---
title: Configurar a junção de reunião sem PIN no Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: 'Resumo: saiba como configurar a opção de junção de reunião sem PIN no Skype for Business Server.'
ms.openlocfilehash: 13af671edaa9ab8853e0390d43c62b6576bed4e2
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60861358"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a>Configurar a junção de reunião sem PIN no Skype for Business Server
 
**Resumo:** Saiba como configurar a opção de junção de reunião sem PIN Skype for Business Server.
  
Quando um chamador discado tenta ingressar em uma reunião, o serviço de Conferência Atendedor Automático (CAA) coloca o chamador em uma caneta de espera diferente do Lobby &#x2014; se um apresentador ainda não estiver em uma chamada e o chamador de discagem não tiver inserido um PIN líder. A opção de ingresso de reunião sem PIN permite que os chamadores de discagem participem de uma reunião sem inserir um PIN líder, mesmo que sejam a primeira pessoa em uma chamada. 
  
Lembre-se do seguinte ao configurar este recurso:
  
- Aplica-se apenas a reuniões privadas.
    
- Permite que os chamadores PSTN permaneçam em reuniões privadas sem a presença de usuários autenticados.
    
- Depois que a configuração for alterada, ela se aplicará a todas as reuniões privadas existentes e novas.
    
- Pode ser habilitado no site do organizador ou no nível global.
    
- As opções para quem pode ignorar o lobby podem ser definidas para um dos seguintes: 
    
  - **Qualquer pessoa da minha organização com chamadores entrar diretamente**
    
  - **Qualquer pessoa (sem restrições) com chamadores entrar diretamente** (Essa é a configuração padrão).)
    
- Quando configurado para habilitar a junção sem PIN, o serviço CAA ainda solicita um PIN líder. Os usuários podem ingressar na reunião se um PIN foi inserido ou não. No entanto, manter a capacidade de inserir um PIN líder permite que um chamador de discagem se autenture como um líder e gerencie a reunião, se necessário.
    
## <a name="configure-pin-less-meeting-join"></a>Configurar a junção de reunião sem PIN

Para habilitar a junção de reunião sem PIN para seus usuários, use o cmdlet [Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) com o parâmetro AllowAnonymousPstnActivation da seguinte forma:
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

Por exemplo, o comando a seguir habilita a junção de reunião sem PIN para o site Redmond:
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

Para fins de segurança, quando a junção de reunião sem PIN estiver ativas, talvez você queira restringir a discagem de usuários anônimos, garantindo que o ConferencingPolicy seja definido da seguinte maneira:
  
```PowerShell
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

Para obter mais informações, [consulte Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
