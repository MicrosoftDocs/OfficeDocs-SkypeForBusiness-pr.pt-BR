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
description: Veja quais são os problemas com caracteres especiais nos nomes das políticas e o que você pode fazer para corrigi-lo.
ms.openlocfilehash: 899cffa45bc5ec7a36339e89e3cb97e35e6e4507
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814710"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>Quais são as restrições de caracteres especiais nas políticas do Teams?

Não é possível criar ou editar políticas **(para mensagens, reuniões etc.)** que tenham um caractere especial no nome no Centro de administração do Microsoft Teams. 

Se um nome de política contiver caracteres especiais, você será limitado no gerenciamento dessas políticas no Centro de administração do Microsoft Teams. **Como tal, recomendamos que os nomes de política não incluam caracteres especiais.** 

Os nomes de política que foram criados usando o PowerShell para reuniões e mensagens no Teams podem ter caracteres especiais, como @,#,$. No entanto, se você quiser fazer alterações na política no Centro de administração do Microsoft Teams, não será possível. 

Se você tiver uma política com caracteres especiais, precisará editar a política usando o Windows PowerShell (para sempre) ou criar uma nova política no Centro de administração do Microsoft Teams com as mesmas configurações da política antiga e atribuí-la ao mesmo grupo de usuários.

## <a name="to-remove-special-characters"></a>Para remover caracteres especiais

**Etapa 1 - Fazer uma conexão remota com o PowerShell.**
> [!NOTE]
> No momento, o Skype for Business Online Connector faz parte do módulo mais recente do PowerShell do Teams.
>
> Se você estiver usando a versão pública mais recente do [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)não será necessário instalar o Skype for Business Online Connector.

```PowerShell
 Import-Module -Name MicrosoftTeams
 $credential = Get-Credential
 $session = New-CsOnlineSession -Credential $credential
 Import-PSSession $session
```


**Etapa 2 : obter as configurações da política antiga e capturar a saída.**

> [!NOTE]
> Este exemplo é para uma [política de](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) Mensagens.  As etapas seriam as mesmas para outros tipos de política, mas você deve usar o cmdlet correto. 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


**Etapa 3 : criar uma nova política.**

Você pode criar a nova política com a mesma configuração usando o Centro de administração do Microsoft Teams ou o PowerShell.

Executar isso criará uma nova política para você, mas você precisará adicionar as configurações corretas vendo [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) e executando-a:

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
**Etapa 4 - Atribuir a política.**
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
Consulte [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) para obter mais informações sobre este cmdlet.

**Etapa 5 : excluir a política antiga.**

Isso excluirá a política antiga com os caracteres especiais.
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
Consulte [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) para obter mais informações sobre este cmdlet.

Se esse comando for bem-sucedido, você terminou. Se o comando acima retornar um erro, é porque a política antiga é atribuída aos usuários, portanto, você precisa executar para remover todos os usuários atribuídos da política:

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 usando um ponto único de administração que pode simplificar seu trabalho diário quando você tiver várias tarefas a fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365?](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação ao uso apenas do Centro de administração do Microsoft 365, como quando você está fazendo alterações nas configurações para muitos usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online e ao Microsoft Teams. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  

