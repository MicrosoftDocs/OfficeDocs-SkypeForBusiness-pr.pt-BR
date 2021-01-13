---
title: Configurar o ingressar em reunião sem PIN no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: 'Resumo: Saiba como configurar a opção de ingressar em reunião sem PIN no Skype for Business Server.'
ms.openlocfilehash: 794bf13d92857a18254f903a1c5dcca98d0a1ec0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827981"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a>Configurar o ingressar em reunião sem PIN no Skype for Business Server
 
**Resumo:** Saiba como configurar a opção de ingressar em reunião sem PIN no Skype for Business Server.
  
Quando um chamador de discagem tenta ingressar em uma reunião, o serviço de CaA (Atendente Automático de Conferência) coloca o chamador em uma caneta de espera diferente do lobby &#x2014; se um apresentador ainda não estiver em uma chamada e o chamador de discagem não tiver inserido um PIN de líder. A opção de ingresso em reunião sem PIN permite que os chamadores de discagem ingressem em uma reunião sem inserir um PIN de líder, mesmo que sejam a primeira pessoa em uma chamada. 
  
Lembre-se do seguinte ao configurar esse recurso:
  
- Aplica-se somente a reuniões privadas.
    
- Permite que chamadores PSTN permaneçam em reuniões privadas sem a presença de usuários autenticados.
    
- Depois que a configuração for alterada, ela se aplicará a todas as reuniões privadas novas e existentes.
    
- Pode ser habilitada no site do organizador ou no nível global.
    
- As opções para quem pode ignorar o lobby podem ser definidas para um dos seguintes: 
    
  - **Qualquer pessoa da minha organização com chamadores entrar diretamente**
    
  - **Qualquer pessoa (sem restrições) com chamadores entrar diretamente** (essa é a configuração padrão).)
    
- Quando configurado para habilitar o pin sem junção, o serviço CAA ainda solicita um PIN de líder. Os usuários podem ingressar na reunião independentemente de um PIN ser inserido ou não. No entanto, manter a capacidade de inserir um PIN de líder permite que um chamador de discagem se autentcie como um líder e gerencie a reunião, se necessário.
    
## <a name="configure-pin-less-meeting-join"></a>Configurar o ingressar em reunião sem PIN

Para habilitar o ingressar na reunião sem PIN para seus usuários, use o cmdlet [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) com o parâmetro AllowAnonymousPstnActivation da seguinte forma:
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

Por exemplo, o seguinte comando habilita o ingressar na reunião sem PIN para o site Redmond:
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

Para fins de segurança, quando o ingressar em uma reunião sem PIN estiver ligado, você pode querer restringir a discagem de usuários anônimos, garantindo que ConferencingPolicy seja definida da seguinte maneira:
  
```PowerShell
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

Para obter mais informações, [consulte Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
  

