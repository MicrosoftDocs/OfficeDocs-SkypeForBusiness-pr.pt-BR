---
title: Configurar ingresso em reunião sem PIN no Skype for Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: 'Resumo: Saiba como configurar o PIN sem a opção de ingresso em Skype para Business Server da reunião.'
ms.openlocfilehash: 4ea20f68b123f6593c5a98fc82dbca62f90f31b1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892284"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a>Configurar ingresso em reunião sem PIN no Skype for Business Server
 
**Resumo:** Saiba como configurar o PIN sem a opção de ingresso em Skype para Business Server da reunião.
  
Quando um chamador discada tenta ingressar em uma reunião, o serviço de atendedor automático da conferência (CAA) coloca o chamador em uma caneta fornecerá que seja diferente do que o & Lobby #x 2014; Se um apresentador não ainda estiver em uma chamada e o chamador discada não tiver inserido um líder de PIN. A opção de ingresso na reunião sem o PIN permite a participação na reunião discada dos chamadores sem inserir PIN de líder, mesmo se eles forem a primeira pessoa que da chamada. 
  
Lembre-se do seguinte ao configurar esse recurso:
  
- Aplica-se somente a reuniões particulares.
    
- Permite que os chamadores PSTN permaneçam na reuniões particulares sem a presença de usuários autenticados.
    
- Depois que a configuração for alterada, aplica-se a todas as reuniões privadas existentes e novas.
    
- Pode ser ativada no site do organizador ou em nível global.
    
- Opções para quem pode ignorar o lobby podem ser definidas para qualquer um dos seguintes itens: 
    
  - **Qualquer pessoa de minha empresa com Chamadores entram diretamente**
    
  - **Qualquer pessoa (sem restrições) com Chamadores entram diretamente** (Esta é a configuração padrão).
    
- Quando configurado para habilitar o ingresso sem PIN, o serviço CAA ainda avisa o PIN do líder. Os usuários podem participar da reunião se um PIN for ou não inserido. No entanto, preservar a capacidade de inserir um líder PIN permite que um chamador dial-in autenticar como um líder e gerenciar a reunião, se necessário.
    
## <a name="configure-pin-less-meeting-join"></a>Configurar o ingresso à reunião sem PIN

Para habilitar a participação de reunião sem PIN para seus usuários, use o cmdlet [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) com o parâmetro AllowAnonymousPstnActivation conforme segue:
  
```
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

Por exemplo, o seguinte comando habilita o ingresso à reunião sem PIN para o site Redmond:
  
```
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

Para fins de segurança, quando o ingresso à reunião sem PIN estiver ativado, você pode querer restringir usuários anônimos de discagem externa, assegurando que ConferencingPolicy seja definida da seguinte maneira:
  
```
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

Para obter mais informações, consulte [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
  

