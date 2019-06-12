---
title: Configurar ingresso em reunião sem PIN no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: 'Resumo: saiba como configurar a opção de junção de reunião sem PIN no Skype for Business Server.'
ms.openlocfilehash: ecd1d2bf184dd6b9e1ff78e16c2ca1eb8da73ef9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280380"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a>Configurar ingresso em reunião sem PIN no Skype for Business Server
 
**Resumo:** Saiba como configurar a opção de junção de reunião sem PIN no Skype for Business Server.
  
Quando um chamador de discagem tenta ingressar em uma reunião, o serviço de atendedor automático da conferência (CAA) coloca o chamador em uma caneta segurando diferente da &#x2014; de lobby se um apresentador ainda não estiver em uma chamada, e o chamador de discagem não inseriu um pino principal. A opção de ingresso na reunião sem o PIN permite a participação na reunião discada dos chamadores sem inserir PIN de líder, mesmo se eles forem a primeira pessoa que da chamada. 
  
Lembre-se do seguinte ao configurar esse recurso:
  
- Aplica-se somente a reuniões particulares.
    
- Permite que os chamadores PSTN permaneçam na reuniões particulares sem a presença de usuários autenticados.
    
- Depois que a configuração for alterada, aplica-se a todas as reuniões privadas existentes e novas.
    
- Pode ser ativada no site do organizador ou em nível global.
    
- Opções para quem pode ignorar o lobby podem ser definidas para qualquer um dos seguintes itens: 
    
  - **Qualquer pessoa de minha empresa com Chamadores entram diretamente**
    
  - **Qualquer pessoa (sem restrições) com Chamadores entram diretamente** (Esta é a configuração padrão).
    
- Quando configurado para habilitar o ingresso sem PIN, o serviço CAA ainda avisa o PIN do líder. Os usuários podem participar da reunião se um PIN for ou não inserido. No entanto, manter a capacidade de digitar um PIN de líderes permite que um chamador de discagem seja autenticado como líder e gerenciar a reunião, se necessário.
    
## <a name="configure-pin-less-meeting-join"></a>Configurar o ingresso à reunião sem PIN

Para habilitar a junção de reunião sem PIN para seus usuários, use o cmdlet [set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) com o parâmetro AllowAnonymousPstnActivation da seguinte maneira:
  
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

Para obter mais informações, consulte [set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
  

