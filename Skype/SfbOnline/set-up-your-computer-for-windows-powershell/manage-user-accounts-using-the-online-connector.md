---
title: "Gerenciar contas de usuário usando o conector Online"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: a226b0d4-6359-42b8-808d-4b8ab3736d3b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: "Use o cmdlet Get-CsOnlineUser no Windows PowerShell para obter informações sobre Skype da sua organização para usuários corporativos Online."
ms.openlocfilehash: 6cd8f24638622b1581003c1b4f372923ca7c4939
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2018
---
# <a name="manage-user-accounts-using-the-online-connector"></a>Gerenciar contas de usuário usando o conector Online

## <a name="manage-user-accounts"></a>Gerenciar contas de usuário

Este tópico inclui as seguintes seções:
  
- [Retornar informações sobre todos os seu Skype para usuários corporativos Online](manage-user-accounts-using-the-online-connector.md#BKAllUsers)
    
- [Retornar informações para um usuário específico em Skype para negócios Online](manage-user-accounts-using-the-online-connector.md#BKSpecificUser)
    
- [Retornar informações específicas para usuários específicos no Skype para Business Online](manage-user-accounts-using-the-online-connector.md#BKSpecificUsers)
    
- [Retornar uma lista filtrada de usuários em Skype para negócios Online](manage-user-accounts-using-the-online-connector.md#BKListofUsers)
    
> [!NOTE]
> O cmdlet **Set-CsUser** também está incluído no conjunto de cmdlets disponíveis para Skype para os administradores corporativos Online. No entanto, **Set-CsUser** atualmente não podem ser usados para gerenciar o Skype para negócios Online, exceto para a configuração do parâmetro _AudioVideoDisabled_ . Se você tentar executar o cmdlet com outro parâmetro, ele falhará com uma mensagem de erro semelhante a esta: não é possível definir "SipAddress". Esse parâmetro é restrito dentro do PowerShell remoto de locatário.
  
### <a name="return-information-about-all-your-skype-for-business-online-users"></a>Retornar informações sobre todos os seus usuários do Lync Online
<a name="BKAllUsers"> </a>

Para retornar informações sobre todos os usuários que tiverem sido habilitados para Skype para Business Online, chame o cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) sem quaisquer parâmetros adicionais.
  
```
Get-CsOnlineUser
```

Para retornar informações de um usuário único, selecionada aleatoriamente (por exemplo, para usar esta conta para fins de teste), chame o cmdlet **Get-CsOnlineUser** e defina o parâmetro _ResultSize_ como 1.
  
```
Get-CsOnlineUser -ResultSize 1
```

Isso faz com que o cmdlet **Get-CsOnlineUser** retornar informações para apenas um usuário, independentemente de quantos usuários que você tem em sua organização. Para retornar informações para usuários de cinco, defina o valor do parâmetro _ResultSize_ como 5.
  
```
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a>Retornar informações para um usuário específico em Skype para negócios Online
<a name="BKSpecificUser"> </a>

Há várias maneiras de referenciar uma conta de usuário específica ao chamar o cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) . Você pode usar o nome para exibição do usuário os serviços de domínio Active Directory (AD DS).
  
```
Get-CsOnlineUser -Identity "Ken Myer"
```

Você pode usar o endereço SIP do usuário.
  
```
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

Você pode usar o nome principal do usuário do usuário (UPN).
  
```
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a>Retornar informações específicas para usuários específicos no Skype para Business Online
<a name="BKSpecificUsers"> </a>

Por padrão, o cmdlet [Get-CsOnlineUser](http://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) retorna uma grande quantidade de informações para cada Skype para a conta de usuário Business Online. Se você estiver interessado em apenas um subconjunto dessas informações, canaliza os dados retornados para o cmdlet **Select-Object** . Por exemplo, este comando retorna todos os dados para o usuário Ken Myer e, em seguida, usa o cmdlet **Select-Object** para limitar as informações exibido na tela para o nome de exibição de Ken AD DS e o plano de discagem.
  
```
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

O comando a seguir retorna o nome para exibição e discagem planejar todos os seus usuários.
  
```
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

Para localizar as propriedades de um Skype para a conta de usuário Business Online, use o seguinte comando.
  
```
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a>Retornar uma lista filtrada de usuários em Skype para negócios Online
<a name="BKListofUsers"> </a>

Usando o cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) e os parâmetros de _filtro_ ou _LdapFilter_ , você pode facilmente retornar informações sobre um conjunto de destino de usuários. Por exemplo, este comando retorna todos os usuários que trabalham no departamento financeiro.
  
```
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a>Tópicos relacionados
[Configurar seu computador e Skype para gerenciamento online de negócios usando o Windows PowerShell](set-up-your-computer-for-windows-powershell.md)
