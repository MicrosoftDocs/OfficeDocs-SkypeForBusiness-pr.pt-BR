---
title: Gerenciar contas de usuário usando o conector online
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
f1keywords: None
ms.custom:
- PowerShell
description: Use o cmdlet Get-CsOnlineUser no Windows PowerShell para obter informações sobre os usuários do Skype for Business online da sua organização.
ms.openlocfilehash: 5be51ac39f4a5bd07788a3341114d72a8556cc1a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284676"
---
# <a name="manage-user-accounts-using-the-online-connector"></a>Gerenciar contas de usuário usando o conector online

## <a name="manage-user-accounts"></a>Gerenciar contas de usuário

Este tópico inclui as seguintes seções:

- [Retornar informações sobre todos os seus usuários do Lync Online](manage-user-accounts-using-the-online-connector.md#BKAllUsers)

- [Retornar informações para um usuário específico no Skype for Business Online](manage-user-accounts-using-the-online-connector.md#BKSpecificUser)

- [Retornar informações específicas para usuários específicos no Skype for Business Online](manage-user-accounts-using-the-online-connector.md#BKSpecificUsers)

- [Retornar uma lista filtrada de usuários no Skype for Business Online](manage-user-accounts-using-the-online-connector.md#BKListofUsers)

> [!NOTE]
> O cmdlet **set-CsUser** também está incluído no conjunto de cmdlets disponíveis para os administradores do Skype for Business online. No entanto, **set-CsUser** não pode ser usado no momento para gerenciar o Skype for Business Online, exceto para configurar o parâmetro _AudioVideoDisabled_ . Se você tentar executar o cmdlet com qualquer outro parâmetro, ele falhará com uma mensagem de erro semelhante a esta: não é possível definir "SipAddress". Esse parâmetro é restrito dentro do PowerShell do locatário remoto.

### <a name="return-information-about-all-your-skype-for-business-online-users"></a>Retornar informações sobre todos os seus usuários do Lync Online
<a name="BKAllUsers"> </a>

Para retornar informações sobre todos os usuários que foram habilitados para o Skype for Business Online, chame o cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) sem parâmetros adicionais.

```
Get-CsOnlineUser
```

Para retornar informações para um único usuário selecionado aleatoriamente (por exemplo, para usar esta conta para fins de teste), chame o cmdlet **Get-CsOnlineUser** e defina __ o parâmetro resulte como 1.

```
Get-CsOnlineUser -ResultSize 1
```

Isso faz com que o cmdlet **Get-CsOnlineUser** retorne informações para apenas um usuário, independentemente de quantos usuários você tem em sua organização. Para retornar informações para cinco usuários, defina o valor do parâmetro _resulte_ como 5.

```
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a>Retornar informações para um usuário específico no Skype for Business Online
<a name="BKSpecificUser"> </a>

Há várias maneiras de fazer referência a uma conta de usuário específica ao chamar o cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) . Você pode usar o nome de exibição dos serviços de domínio Active Directory (AD DS) do usuário.

```
Get-CsOnlineUser -Identity "Ken Myer"
```

Você pode usar o endereço SIP do usuário.

```
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

Você pode usar o nome UPN do usuário.

```
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a>Retornar informações específicas para usuários específicos no Skype for Business Online
<a name="BKSpecificUsers"> </a>

Por padrão, o cmdlet [Get-CsOnlineUser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) retorna uma quantidade enorme de informações para cada conta de usuário do Skype for Business online. Se você estiver interessado em apenas um subconjunto dessas informações, canalize os dados retornados para o cmdlet **Select-Object** . Por exemplo, esse comando retorna todos os dados do usuário Ken Myer e, em seguida, usa o cmdlet **Select-Object** para limitar as informações exibidas na tela para o nome para exibição do AD DS e o plano de discagem de Ken.

```
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

O comando a seguir retorna o nome para exibição e o plano de discagem para todos os usuários.

```
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

Para localizar as propriedades de uma conta de usuário do Skype for Business Online, use o comando a seguir.

```
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a>Retornar uma lista filtrada de usuários no Skype for Business Online
<a name="BKListofUsers"> </a>

Ao usar o cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) e os parâmetros _LdapFilter_ ou _Filter_ , você pode facilmente retornar informações sobre um conjunto direcionado de usuários. Por exemplo, esse comando retorna todos os usuários que trabalham no departamento financeiro.

```
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a>Tópicos relacionados
[Configurar seu computador para o gerenciamento do Skype for Business online usando o Windows PowerShell](set-up-your-computer-for-windows-powershell.md)


