---
title: Alterações de esquema no Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: 'Antes de implantar e operar Skype for Business Server, você deve preparar os Serviços de Domínio do Active Directory estendendo o esquema. As extensões de esquema adicionam as classes e atributos exigidos pelo Skype for Business Server.'
---

# <a name="schema-changes-in-skype-for-business-server"></a>Alterações de esquema no Skype for Business Server
 
Antes de implantar e operar Skype for Business Server, você deve preparar os Serviços de Domínio do Active Directory estendendo o esquema. As extensões de esquema adicionam as classes e atributos exigidos pelo Skype for Business Server.

> [!NOTE]
> Se você estiver atualizando do Lync Server 2013 para o Skype for Business Server 2015, nenhuma alteração de esquema será feita e, portanto, este artigo não se aplica.
  
Skype for Business Server requer várias novas classes e atributos e modifica algumas classes e atributos existentes. Além disso, muitas informações de configuração para Skype for Business Server são armazenadas no armazenamento de Gerenciamento Central, em vez de no AD DS, como nas versões anteriores. As informações a seguir ainda são armazenadas no AD DS Skype for Business Server:
  
- **Extensões de esquema**:
    
  - Extensões do objeto do usuário
    
  - Extensões para classes para manter a compatibilidade com versões anteriores suportadas do Lync Server.
    
- **Dados** (armazenados em Skype for Business Server esquema estendido e em classes de esquema existentes):
    
  - URI (Uniform Resource Identifier) SIP do usuário e outras configurações de usuário
    
  - Objetos de contato para aplicativos, como Grupo de Respostas e Atendedor de Conferência
    
  - Um ponteiro para o armazenamento de Gerenciamento Central
    
  - Conta de autenticação Kerberos (um objeto de computador opcional)
    
Este tópico descreve as alterações de esquema do Active Directory necessárias Skype for Business Server. Ele não descreve as alterações de esquema introduzidas por versões anteriores do Office Communications Server. Para ver uma lista de classes e suas descrições, consulte [Classes de esquema e descrições em Skype for Business Server](schema-classes-and-descriptions.md). Para ver uma lista de atributos e suas descrições, consulte [Atributos e descrições de esquema em](schema-attributes-and-descriptions.md) Skype for Business Server. Para uma lista de classes com os atributos que podem conter, consulte [Atributos de esquema por classe em Skype for Business Server](schema-attributes-by-class.md).
  
O prefixo msRTCSIP identifica classes e atributos específicos de Skype for Business Server.
  
## <a name="new-active-directory-attributes"></a>Novos atributos do Active Directory

A tabela a seguir descreve os atributos do Active Directory adicionados por Skype for Business Server.
  
**Atributos Adicionados por Skype for Business Server**

|**Atributo**|**Descrição**|
|:-----|:-----|
|msExchUserHoldPolicies  <br/> |Este atributo de vários valores mantém identificadores para manter políticas aplicadas ao usuário. Políticas de retenção preservam os itens das caixas de correio para o usuário pela duração da retenção. Esse atributo é compartilhado com Exchange 2013.  <br/> |
|msRTCSIP-UserRoutingGroupId  <br/> |Este é o ID do grupo de roteamento SIP. Os usuários no mesmo grupo irão ser registrados para o mesmo Servidor de Front-end.  <br/> |
|msRTCSIP-MirrorBackEndServer  <br/> |Esse atributo é usado para armazenar o back-end SQL Server espelhado usado pelo pool de Front-End.  <br/> |
   
## <a name="modified-active-directory-classes"></a>Classes do Active Directory modificadas

A tabela a seguir descreve as classes do Active Directory modificadas por Skype for Business Server.
  
**Classes Modificadas por Skype for Business Server**

|**Classe**|**Alteração**|**Classe ou atributo**|
|:-----|:-----|:-----|
|Usuário  <br/> |add: mayContain  <br/> add: mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Contact  <br/> |add: mayContain  <br/> add: mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Mail-Recipient  <br/> |add:mayContain  <br/> |msExchUserHoldPolicies  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |add: mayContain  <br/> |msRTCSIP-MirrorBackEndServer  <br/> |
   

