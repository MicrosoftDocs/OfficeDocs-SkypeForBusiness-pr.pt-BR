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
ms.localizationpriority: medium
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policies.naming.error
- seo-marvel-mar2020
description: Veja quais são os problemas com caracteres especiais nos nomes das políticas e o que você pode fazer para corrigi-lo.
ms.openlocfilehash: c06c5053452c1c55c9e8de09d6b18dd5e97deaca
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589603"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>Quais são as restrições de caracteres especiais nas políticas do Teams?

Não é possível criar ou editar políticas **(para mensagens, reuniões etc.)** que tenham um caractere especial no nome no centro de administração Microsoft Teams. 

Se um nome de política contiver caracteres especiais, você será limitado ao gerenciar essas políticas no centro de administração Microsoft Teams de administração. **Como tal, recomendamos que os nomes de política não incluam caracteres especiais.** 

Os nomes de política criados usando o PowerShell para reuniões e mensagens no Teams podem ter caracteres especiais como @,#,$. No entanto, se você estiver desejando fazer alterações na política no centro de administração Microsoft Teams, não será possível. 

Se você tiver uma política com caracteres especiais, precisará editar a política usando o Windows PowerShell (para sempre) ou criar uma nova política no centro de administração do Microsoft Teams com as mesmas configurações da política antiga e atribuí-la ao mesmo grupo de usuários.

## <a name="to-remove-special-characters"></a>Para remover caracteres especiais

**Etapa 1 : Fazer uma conexão remota com o PowerShell.**
> [!NOTE]
> Skype for Business No momento, o Conector Online faz parte do módulo Teams PowerShell mais recente.
>
> Se você estiver usando a versão pública mais [recente Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)não será necessário instalar o conector Skype for Business Online.

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```


**Etapa 2 : Obter as configurações da política antiga e capturar a saída.**

> [!NOTE]
> Este exemplo é para uma [política de](/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) Mensagens.  As etapas seriam as mesmas para outros tipos de política, mas você deve usar o cmdlet correto. 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


**Etapa 3 - Criar uma nova política.**

Você pode criar a nova política com a mesma configuração usando o centro de administração Microsoft Teams ou o PowerShell.

Executar isso criará uma nova política para você, mas você precisará adicionar as configurações corretas, vendo [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) e executando-a:

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
**Etapa 4 - Atribuir a política.**
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
Consulte [Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) para obter mais informações sobre este cmdlet.

**Etapa 5 - Excluir a política antiga.**

Isso excluirá a política antiga com os caracteres especiais.
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
Consulte [Remove-CsTeamsMessagingPolicy](/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) para obter mais informações sobre este cmdlet.

Se esse comando for bem-sucedido, você terminará. Se o comando acima retornar um erro, é porque a política antiga é atribuída aos usuários, portanto, você precisa executar para remover todos os usuários atribuídos da política:

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com Windows PowerShell, você pode gerenciar Microsoft 365 ou Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tem várias tarefas a fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Por que você precisa usar Office 365 PowerShell?](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Melhores maneiras de gerenciar Microsoft 365 ou Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre o uso apenas do Centro de administração do Microsoft 365, como quando você está fazendo alterações de configurações para muitos usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    [Usar o Windows PowerShell para gerenciar o Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    > [!NOTE]
    > O Windows PowerShell módulo do Skype for Business Online permite que você crie uma sessão de Windows PowerShell remota que se conecta ao Skype for Business Online e Microsoft Teams. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).
