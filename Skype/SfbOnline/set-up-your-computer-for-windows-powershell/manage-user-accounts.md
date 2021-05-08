---
title: Gerenciar contas de usuário
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: a226b0d4-6359-42b8-808d-4b8ab3736d3b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: Use o cmdlet Get-CsOnlineUser no Windows PowerShell para obter informações sobre os usuários Skype for Business Online da sua organização.
ms.openlocfilehash: aec79f589f6b1fb0c9d38fd4bc70421b30f66a56
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238717"
---
# <a name="manage-user-accounts"></a>Gerenciar contas de usuário

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

## <a name="manage-user-accounts"></a>Gerenciar contas de usuário

Este tópico inclui as seguintes seções:

- [Retornar informações sobre todos os seus usuários do Lync Online](manage-user-accounts.md#BKMKReturnInfoAboutAllUsers)

- [Retornar informações para um usuário específico no Skype for Business Online](manage-user-accounts.md#BKMKReturnInfoSpecificUser)

- [Retornar informações específicas para usuários específicos no Skype for Business Online](manage-user-accounts.md#BKMKReturninfoSpecificUsers)

- [Retornar uma lista filtrada de usuários no Skype for Business Online](manage-user-accounts.md#BKMKReturnFilteredListofUsers)

> [!NOTE]
> O cmdlet **Set-CsUser** também está incluído no conjunto de cmdlets disponíveis para administradores Skype for Business Online. No entanto, **Set-CsUser** não pode ser usado no momento para gerenciar o Skype for Business Online, exceto para definir o parâmetro _AudioVideoDisabled._ Se você tentar executar o cmdlet com qualquer outro parâmetro, ele falhará com uma mensagem de erro semelhante a esta: Não é possível definir "SipAddress". Esse parâmetro é restrito no PowerShell de Locatário Remoto.

### <a name="return-information-about-all-your-skype-for-business-online-users"></a>Retornar informações sobre todos os seus usuários do Lync Online
<a name="BKMKReturnInfoAboutAllUsers"> </a>

Para retornar informações sobre todos os seus usuários que foram habilitados para o Skype for Business Online, chame o cmdlet [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) sem nenhum parâmetro adicional.

```PowerShell
Get-CsOnlineUser
```

Para retornar informações para um único usuário selecionado aleatoriamente (por exemplo, para usar essa conta para fins de teste), chame o cmdlet **Get-CsOnlineUser** e de definir o parâmetro _ResultSize_ como 1.

```PowerShell
Get-CsOnlineUser -ResultSize 1
```

Isso faz com que o cmdlet **Get-CsOnlineUser** retorne informações para apenas um usuário, independentemente de quantos usuários você tenha em sua organização. Para retornar informações para cinco usuários, de definir o valor do parâmetro _ResultSize_ como 5.

```PowerShell
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a>Retornar informações para um usuário específico no Skype for Business Online
<a name="BKMKReturnInfoSpecificUser"> </a>

Há várias maneiras de fazer referência a uma conta de usuário específica ao chamar o cmdlet [Get-CsOnlineUser.](/powershell/module/skype/Get-CsOnlineUser) Você pode usar o nome de exibição do Active Directory Domain Services (AD DS) do usuário.

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer"
```

Você pode usar o endereço SIP do usuário.

```PowerShell
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

Você pode usar o nome principal do usuário (UPN).

```PowerShell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a>Retornar informações específicas para usuários específicos no Skype for Business Online
<a name="BKMKReturninfoSpecificUsers"> </a>

Por padrão, o cmdlet [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) retorna uma grande quantidade de informações para cada conta de usuário Skype for Business Online. Se você estiver interessado em apenas um subconjunto dessas informações, pipe os dados retornados para o cmdlet **Select-Object.** Por exemplo, este comando retorna todos os dados do usuário Ken Myer e usa o cmdlet **Select-Object** para limitar as informações exibidas na tela para o nome de exibição e o plano de discagem do AD DS de Ken.

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

O comando a seguir retorna o nome de exibição e o plano de discagem para todos os usuários.

```PowerShell
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

Para encontrar as propriedades de uma conta de usuário Skype for Business Online, use o comando a seguir.

```PowerShell
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a>Retornar uma lista filtrada de usuários no Skype for Business Online
<a name="BKMKReturnFilteredListofUsers"> </a>

Usando o cmdlet [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) e os parâmetros _LdapFilter_ ou _Filter,_ você pode facilmente retornar informações sobre um conjunto direcionado de usuários. Por exemplo, este comando retorna todos os usuários que trabalham no departamento de Finanças.

```PowerShell
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a>Tópicos relacionados
[Configurar seu computador para gerenciamento do skype for business online usando Windows PowerShell](set-up-your-computer-for-windows-powershell.md)
