---
title: Restrições de caracteres especiais nas políticas do Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policies.naming.error
- seo-marvel-mar2020
description: Veja quais são os problemas que há caracteres especiais nos nomes das políticas e o que você pode fazer para corrigi-lo.
ms.openlocfilehash: 7358bd989b793e988f0a3dacdded275b5232c8cc
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691507"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>Quais são as restrições de caracteres especiais nas políticas do Teams?

**Você não pode criar ou editar políticas (para mensagens, reuniões etc.) que tenham um caractere especial no nome do centro de administração do Microsoft Teams**. 

Se um nome de política contiver caracteres especiais, você será limitado ao gerenciamento dessas políticas no centro de administração do Microsoft Teams. **Assim, recomendamos enfaticamente que os nomes das políticas não incluam caracteres especiais**. 

Os nomes de política que foram criados usando o PowerShell para reuniões e mensagens no Microsoft Teams podem ter caracteres especiais, como @, #, $. No entanto, se você quiser fazer alterações na política no centro de administração do Microsoft Teams, não será possível. 

Se você tiver uma política com caracteres especiais, será necessário editar a política usando o Windows PowerShell (para sempre) ou criar uma nova política no centro de administração do Microsoft Teams com as mesmas configurações da política antiga e atribuí-la ao mesmo grupo de usuários.

## <a name="to-remove-special-characters"></a>Para remover caracteres especiais

**Etapa 1-fazer uma conexão remota com o PowerShell.** 
 [Configure seu computador para Windows PowerShell](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) , se ainda não tiver feito isso.
```PowerShell
 Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
 $credential = Get-Credential
 $session = New-CsOnlineSession -Credential $credential
 Import-PSSession $session
```


**Etapa 2: obter as configurações da política antiga e capturar a saída.**

> [!NOTE]
> Este exemplo é para uma política de [mensagens](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) .  As etapas seriam iguais para outros tipos de política, mas você deve usar o cmdlet correto. 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


**Etapa 3: criar uma nova política.**

Você pode criar uma nova política com a mesma configuração usando o centro de administração do Microsoft Teams ou o PowerShell.

Executar isso criará uma nova política para você, mas você precisará adicionar as configurações corretas vendo [set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) e, em seguida, executá-lo:

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
**Etapa 4-atribuir a política.**
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
Consulte [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) para obter mais informações sobre esse cmdlet.

**Etapa 5-excluir a política antiga.**

Isso excluirá a política antiga com os caracteres especiais.
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
Consulte [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) para obter mais informações sobre esse cmdlet.

Se esse comando tiver êxito, você terminou. Se o comando acima retornar um erro, é porque a antiga política é atribuída aos usuários, portanto, você precisa executar para remover todos os usuários atribuídos da política:

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365?](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o centro de administração do Microsoft 365, como quando você está realizando alterações de configurações para muitos usuários de uma só vez. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > O módulo do Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online e ao Microsoft Teams. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  

