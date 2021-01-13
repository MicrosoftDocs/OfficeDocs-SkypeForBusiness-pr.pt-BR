---
title: Alterações de esquema no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: Antes de implantar e operar o Skype for Business Server, você deve preparar os Serviços de Domínio Active Directory estendendo o esquema. As extensões de esquema adicionam as classes e atributos exigidos pelo Skype for Business Server.
ms.openlocfilehash: 4ca18b0ccfde6b247f1c29e140004804462d0f56
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813571"
---
# <a name="schema-changes-in-skype-for-business-server"></a>Alterações de esquema no Skype for Business Server
 
Antes de implantar e operar o Skype for Business Server, você deve preparar os Serviços de Domínio Active Directory estendendo o esquema. As extensões de esquema adicionam as classes e atributos exigidos pelo Skype for Business Server.

> [!NOTE]
> Se você estiver atualizando do Lync Server 2013 para o Skype for Business Server 2015, nenhuma alteração de esquema será feita e, portanto, este artigo não se aplica.
  
O Skype for Business Server requer várias classes e atributos novos e modifica algumas classes e atributos existentes. Além disso, muitas informações de configuração do Skype for Business Server são armazenadas no armazenamento de Gerenciamento Central, e não no AD DS, como nas versões anteriores. As informações a seguir ainda são armazenadas no AD DS no Skype for Business Server:
  
- **Extensões de esquema**:
    
  - Extensões do objeto do usuário
    
  - Extensões para classes para manter a compatibilidade com versões anteriores suportadas do Lync Server.
    
- **Dados** (armazenados no esquema estendido do Skype for Business Server e em classes de esquema existentes):
    
  - URI (Uniform Resource Identifier) SIP do usuário e outras configurações de usuário
    
  - Objetos de contato para aplicativos, como Grupo de Respostas e Atendedor de Conferência
    
  - Um ponteiro para o armazenamento de Gerenciamento Central
    
  - Conta de autenticação Kerberos (um objeto de computador opcional)
    
Este tópico descreve as alterações de esquema do Active Directory exigidas pelo Skype for Business Server. Ele não descreve as alterações de esquema introduzidas por versões anteriores do Office Communications Server. Para uma lista de classes e suas descrições, consulte Classes e descrições de esquema [no Skype for Business Server.](schema-classes-and-descriptions.md) Para uma lista de atributos e suas descrições, consulte Atributos e descrições do esquema [no Skype for Business Server.](schema-attributes-and-descriptions.md) Para uma lista de classes com os atributos que elas podem conter, consulte Atributos de esquema por [classe no Skype for Business Server](schema-attributes-by-class.md).
  
O prefixo msRTCSIP identifica classes e atributos específicos do Skype for Business Server.
  
## <a name="new-active-directory-attributes"></a>Novos atributos do Active Directory

A tabela a seguir descreve os atributos do Active Directory adicionados pelo Skype for Business Server.
  
**Atributos adicionados pelo Skype for Business Server**

|**Atributo**|**Descrição**|
|:-----|:-----|
|msExchUserHoldPolicies  <br/> |Este atributo de vários valores mantém identificadores para manter políticas aplicadas ao usuário. Políticas de retenção preservam os itens das caixas de correio para o usuário pela duração da retenção. Esse atributo é compartilhado com o Exchange 2013.  <br/> |
|msRTCSIP-UserRoutingGroupId  <br/> |Este é o ID do grupo de roteamento SIP. Os usuários no mesmo grupo irão ser registrados para o mesmo Servidor de Front-end.  <br/> |
|msRTCSIP-MirrorBackEndServer  <br/> |Esse atributo é usado para armazenar o back-end espelhado do SQL Server usado pelo pool de Front-End.  <br/> |
   
## <a name="modified-active-directory-classes"></a>Classes do Active Directory modificadas

A tabela a seguir descreve as classes do Active Directory modificadas pelo Skype for Business Server.
  
**Classes modificadas pelo Skype for Business Server**

|**Classe**|**Alteração**|**Classe ou atributo**|
|:-----|:-----|:-----|
|Usuário  <br/> |add: mayContain  <br/> add: mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Contato  <br/> |add: mayContain  <br/> add: mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Mail-Recipient  <br/> |add:mayContain  <br/> |msExchUserHoldPolicies  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |add: mayContain  <br/> |msRTCSIP-MirrorBackEndServer  <br/> |
   

