---
title: Quais são as restrições de caractere especial nas políticas de equipes?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Adm_Skype4B_Online
search.appverid: MET150
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- ms.teamsadmincenter.policies.naming.error
description: Consulte quais problemas que existem com caracteres especiais nos nomes de políticas e o que você pode fazer para corrigi-lo.
ms.openlocfilehash: 61902c3cdeafbacbf316b99834e7ac32286443b4
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23853411"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>Quais são as restrições de caractere especial nas políticas de equipes?

**Você não pode criar ou editar políticas que possuem um caractere especial no nome no Microsoft Teams e Skype para Business Admin Center (para mensagens, reuniões, etc.).** 

Se um nome de política contiver caracteres especiais, você será limitada no gerenciamento essas diretivas no Microsoft Teams e Skype para Business Admin Center. **Sendo assim, é altamente recomendável que os nomes de política não incluem caracteres especiais**. 

Nomes de política que foram criados usando o PowerShell para reuniões e equipes de mensagens podem ter caracteres especiais, como @, #, $. No entanto, se você estiver buscando fazer alterações na política na Microsoft Teams e Skype para Business Admin Center, você não conseguirá. 

Se você tiver uma diretiva com caracteres especiais, você precisará editar a política usando o Windows PowerShell (para sempre) ou criar uma nova política no Microsoft Teams e Skype para centro de administração de negócios com as mesmas configurações como a diretiva old e atribuí-lo para o mesmo agrupar p de usuários.

## <a name="to-remove-special-characters"></a>Para remover caracteres especiais



**Etapa 1 - fazer uma conexão remota com o PowerShell.** 
 [Configurar seu computador para o Windows PowerShell](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) , se ainda não o fez.
```
 Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
 $credential = Get-Credential
 $session = New-CsOnlineSession -Credential $credential
 Import-PSSession $session
```


**Etapa 2 - Obtenha as configurações para a diretiva old e capturar a saída.**

> [!NOTE]
> Este exemplo é para uma política de [mensagens](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) .  As etapas que podem ser as mesmas para outros tipos de política, mas você deve usar o cmdlet correto. 

  ```
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


**Etapa 3: criar uma nova política.**

Você pode criar a nova política com a mesma configuração usando o Microsoft Teams e Skype para o Centro de administração de negócios ou PowerShell.

Executando isso criará uma nova política para você, mas você precisará adicionar as configurações corretas vendo [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) e, em seguida, executá-lo:

  ```
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
**Etapa 4 - atribuir a política.**
 ```
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
Consulte, [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) para obter mais informações sobre esse cmdlet.

**Etapa 5 - excluir a diretiva old.**

Isso excluirá a diretiva old com os caracteres especiais.
  ```
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
Consulte, [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) para obter mais informações sobre esse cmdlet.

Se este comando for bem-sucedido, terminar. Se o comando acima retornará um erro, é porque a diretiva old é atribuída a usuários e, portanto, você precisará executar para remover todos os usuários atribuídos da diretiva:

```
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365?](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o Centro de administração do Office 365, como quando você estiver fazendo alterações nas configurações de muitos usuários de uma só vez. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > O módulo do Windows PowerShell para Skype para Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype para Business Online e Teams da Microsoft. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
### <a name="related-topics"></a>Tópicos relacionados
