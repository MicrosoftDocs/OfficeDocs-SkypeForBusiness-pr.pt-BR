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
description: Veja quais problemas existem com caracteres especiais nos nomes das políticas e o que você pode fazer para corrigi-lo.
ms.openlocfilehash: c304e292aa10508e7c8b02fe2825b83897f22e38
ms.sourcegitcommit: 1788f852508208a01f230f6f68a5a81ec8594c47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860074"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>Quais são as restrições de caracteres especiais nas políticas do Teams?

**Você não pode criar ou editar políticas (para mensagens, reuniões etc.)** que tenham um caractere especial no nome no centro de administração do Microsoft Teams. 

Se um nome de política contiver caracteres especiais, você será limitado no gerenciamento dessas políticas no Microsoft Teams de administração. **Como tal, é altamente recomendável que os nomes de política não incluam caracteres especiais**. 

Os nomes de política que foram criados usando o PowerShell para reuniões e mensagens Teams podem ter caracteres especiais, como @,#,$. No entanto, se você quiser fazer alterações na política no Microsoft Teams de administração, não será possível. 

Se você tiver uma política com caracteres especiais, precisará editar a política usando o Windows PowerShell (para sempre) ou criar uma nova política no centro de administração do Microsoft Teams com as mesmas configurações da política antiga e atribuí-la ao mesmo grupo de usuários.

## <a name="to-remove-special-characters"></a>Para remover caracteres especiais

**Etapa 1 – Fazer uma conexão remota com o PowerShell.**
> [!NOTE]
> Skype for Business Online Connector atualmente faz parte do módulo Teams PowerShell mais recente.
>
> Se você estiver usando a versão Teams versão pública do [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) mais recente, não precisará instalar o Skype for Business Online.

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```


**Etapa 2 : obter as configurações da política antiga e capturar a saída.**

> [!NOTE]
> Este exemplo é para uma [política de mensagens](/powershell/module/skype/get-csteamsmessagingpolicy) .  As etapas seriam as mesmas para outros tipos de política, mas você deve usar o cmdlet correto. 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


**Etapa 3 – Criar uma nova política.**

Você pode criar a nova política com a mesma configuração usando o centro de administração Microsoft Teams ou o PowerShell.

Executar isso criará uma nova política para você, mas você precisará adicionar as configurações corretas vendo [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy) e, em seguida, executando-a:

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
**Etapa 4 – Atribuir a política.**
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
Consulte [Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy) para obter mais informações sobre esse cmdlet.

**Etapa 5 – Excluir a política antiga.**

Isso excluirá a política antiga com os caracteres especiais.
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
Consulte [Remove-CsTeamsMessagingPolicy](/powershell/module/skype/remove-csteamsmessagingpolicy) para obter mais informações sobre esse cmdlet.

Se esse comando for bem-sucedido, você terminará. Se o comando acima retornar um erro, é porque a política antiga é atribuída aos usuários, portanto, você precisa executar para remover todos os usuários atribuídos da política:

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com Windows PowerShell, você pode gerenciar Microsoft 365 ou Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tem várias tarefas a serem executadas. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Por que você precisa usar Office 365 PowerShell?](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Melhores maneiras de gerenciar Microsoft 365 ou Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em vez de usar apenas o Centro de administração do Microsoft 365, como quando você está fazendo alterações de configurações para muitos usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    [Usar o Windows PowerShell para gerenciar o Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    > [!NOTE]
    > O Windows PowerShell do Skype for Business Online permite que você crie uma sessão Windows PowerShell remota que se conecta ao Skype for Business Online e Microsoft Teams. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector).
