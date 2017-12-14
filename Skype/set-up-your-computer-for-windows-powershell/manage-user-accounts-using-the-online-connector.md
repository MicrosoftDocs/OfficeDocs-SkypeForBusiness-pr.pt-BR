---
title: "Gerenciar contas de usuário usando o Skype for Business Online Connector"
ms.author: tonysmit
author: tonysmit
ms.date: 5/23/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.assetid: a226b0d4-6359-42b8-808d-4b8ab3736d3b
description: "Use the Get-CsOnlineUser cmdlet in Windows PowerShell to get information about your organization's Skype for Business Online users."
---

# Gerenciar contas de usuário usando o Skype for Business Online Connector

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o [aviso de isenção de responsabilidade](a226b0d4-6359-42b8-808d-4b8ab3736d3b.md#MT_Footer). Para sua referência, veja a versão em inglês deste artigo [aqui](https://support.office.com/en-us/article/a226b0d4-6359-42b8-808d-4b8ab3736d3b). 
  
## Gerenciar contas de usuário

Este tópico contém as seções a seguir:
  
- [Retornar informações sobre todos os seu Skype para usuários Business Online](a226b0d4-6359-42b8-808d-4b8ab3736d3b.md#BKMK_ReturnInfoAboutAllUsers)
    
- [Retornar informações para um usuário específico no Skype for Business Online](a226b0d4-6359-42b8-808d-4b8ab3736d3b.md#BKMK_ReturnInfoSpecificUser)
    
- [Retornar informações específicas para usuários específicos no Skype for Business Online](a226b0d4-6359-42b8-808d-4b8ab3736d3b.md#BKMK_ReturninfoSpecificUsers)
    
- [Retornar uma lista filtrada de usuários do Skype for Business Online](a226b0d4-6359-42b8-808d-4b8ab3736d3b.md#BKMK_ReturnFilteredListofUsers)
    
> [!NOTE]
> O cmdlet **Set-CsUser** também está incluído no conjunto de cmdlets disponível para administradores de Skype for Business Online. No entanto, **Set-CsUser** atualmente não podem ser usados para gerenciar Skype for Business Online, exceto para definir o parâmetro _AudioVideoDisabled_. Se você tentar executar o cmdlet com qualquer outro parâmetro, ele falhará com uma mensagem de erro semelhante a esta: Não é possível definir "SipAddress". Este parâmetro é restrito dentro do PowerShell remoto do locatário.
  
### Retornar informações sobre todos os seu Skype para usuários Business Online
<a name="BKMK_ReturnInfoAboutAllUsers"> </a>

Para retornar informações sobre todos os seus usuários que foram habilitados para Skype for Business Online, ligue para o cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) sem parâmetros adicionais.
  
```
Get-CsOnlineUser
```

Para retornar informações para um usuário único, selecionado aleatoriamente (por exemplo, para usar essa conta para fins de teste), ligue para o cmdlet **Get-CsOnlineUser** e defina o parâmetro _ResultSize_ como 1.
  
```
Get-CsOnlineUser -ResultSize 1
```

Que faz com que o cmdlet **Get-CsOnlineUser** retornar informações para apenas um usuário, independentemente de quantos usuários que você tem em sua organização. Para retornar informações de cinco usuários, defina o valor do parâmetro _ResultSize_ para 5.
  
```
Get-CsOnlineUser -ResultSize 5
```

### Retornar informações para um usuário específico no Skype for Business Online
<a name="BKMK_ReturnInfoSpecificUser"> </a>

Existem várias maneiras de referenciar uma conta de usuário específica ao chamar o cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) . Você pode usar o nome de exibição de Serviços de Domínio do Active Directory (AD DS) do usuário.
  
```
Get-CsOnlineUser -Identity "Ken Myer"
```

Você pode usar o endereço SIP do usuário.
  
```
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

Você pode usar o nome do usuário usuário principal (UPN).
  
```
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### Retornar informações específicas para usuários específicos no Skype for Business Online
<a name="BKMK_ReturninfoSpecificUsers"> </a>

Por padrão, o cmdlet [Get-CsOnlineUser](https://support.office.com/article/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) retorna uma grande quantidade de informações para cada conta de usuário Skype for Business Online. Se você estiver interessado em apenas um subconjunto dessas informações, conduza os dados retornados para o cmdlet **Select-Object**. Por exemplo, esse comando retornará todos os dados do usuário Ken Myer e, em seguida, usa o cmdlet **Select-Object** para limitar as informações exibido na tela ao nome de exibição do AD DS de Ken e plano de discagem.
  
```
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

O comando a seguir retorna o nome de exibição e a discagem planejar para todos os usuários.
  
```
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

Para localizar as propriedades de uma conta de usuário Skype for Business Online, use o comando a seguir.
  
```
Get-CsOnlineUser | Get-Member
```

### Retornar uma lista filtrada de usuários do Skype for Business Online
<a name="BKMK_ReturnFilteredListofUsers"> </a>

Usando o cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) e os parâmetros _LdapFilter_ ou _Filter_, você pode facilmente retornar informações sobre um conjunto direcionado de usuários. Por exemplo, este comando retorna todos os usuários que trabalham no departamento financeiro.
  
```
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Aviso de Isenção de Tradução Automática**: Este artigo foi traduzido por computador, sem intervenção humana. A Microsoft oferece essas traduções automáticas para ajudar as pessoas que não falam inglês a aproveitar os textos escritos sobre produtos, serviços e tecnologias da Microsoft. Como este artigo foi traduzido automaticamente, é possível que contenha erros de vocabulário, sintaxe ou gramática. 
  

