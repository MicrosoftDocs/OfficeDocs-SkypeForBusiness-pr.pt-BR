---
title: Alterações de esquema no Skype para Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: Antes de implantar e operar o Skype para Business Server, você deve preparar o Active Directory Domain Services estendendo o esquema. As extensões de esquema adicionam as classes e atributos que são exigidos pelo Skype para Business Server.
ms.openlocfilehash: ba76f57197e9cd812163c8abac5f51005933eace
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213351"
---
# <a name="schema-changes-in-skype-for-business-server"></a>Alterações de esquema no Skype para Business Server
 
Antes de implantar e operar o Skype para Business Server, você deve preparar o Active Directory Domain Services estendendo o esquema. As extensões de esquema adicionam as classes e atributos que são exigidos pelo Skype para Business Server.

> [!NOTE]
> Se você estiver atualizando do Lync Server 2013 para Skype para Business Server 2015, sem alterações de esquema são feitas e, portanto, este artigo não se aplica.
  
Skype para Business Server requer várias novas classes e atributos e modifica alguns atributos e classes existentes. Além disso, a quantidade informações de configuração de Skype para Business Server são armazenadas no repositório de gerenciamento Central ao invés de no AD DS como nas versões anteriores. As seguintes informações ainda estão armazenadas no AD DS em Skype para Business Server:
  
- **Extensões de esquema**:
    
  - Extensões de objetos de usuário
    
  - Extensões para classes manter compatibilidade com versões anteriores do Microsoft Lync Server.
    
- **Dados** (armazenados no Skype para esquema estendido do servidor de negócios e nas classes de esquema existentes):
    
  - Usuário SIP URI Uniform Resource Identifier () e outras configurações do usuário
    
  - Objetos de contato para aplicativos, como o grupo de resposta e Atendedor de conferência
    
  - Um ponteiro para o repositório de gerenciamento Central
    
  - Conta de autenticação Kerberos (um objeto de computador opcional)
    
Este tópico descreve as alterações de esquema do Active Directory exigidas pelo Skype para Business Server. Alterações de esquema introduzidas por versões anteriores do Office Communications Server não são descritos. Para obter uma lista das classes e suas descrições, consulte [classes de esquema e descrições Skype para Business Server](schema-classes-and-descriptions.md). Para obter uma lista de atributos e suas descrições, consulte [atributos de esquema e descrições Skype para Business Server](schema-attributes-and-descriptions.md). Para obter uma lista das classes com os atributos, eles podem conter, consulte [atributos de esquema por classe no Skype para Business Server](schema-attributes-by-class.md).
  
O prefixo msRTCSIP identifica classes e atributos específicos do Skype para Business Server.
  
## <a name="new-active-directory-attributes"></a>Novos atributos do Active Directory

A tabela a seguir descreve os atributos do Active Directory que são adicionados pelo Skype para Business Server.
  
**Atributos adicionados pelo Skype para Business Server**

|**Atributo**|**Descrição**|
|:-----|:-----|
|msExchUserHoldPolicies  <br/> |Este atributo de valor múltiplos contém identificadores para manter as políticas que se aplicam ao usuário. Mantenha políticas preservem itens de caixa de correio para o usuário para a duração da retenção. Este atributo é compartilhado com o Exchange 2013.  <br/> |
|msRTCSIP-UserRoutingGroupId  <br/> |Este é o SIP roteamento identificação do grupo. Os usuários no mesmo grupo, registre-se para o mesmo servidor Front-End.  <br/> |
|msRTCSIP-MirrorBackEndServer  <br/> |Este atributo é usado para armazenar o backend do SQL Server espelhado usado pelo pool de Front-End.  <br/> |
   
## <a name="modified-active-directory-classes"></a>Classes do Active Directory modificadas

A tabela a seguir descreve as classes do Active Directory que são modificadas pelo Skype para Business Server.
  
**Classes modificadas pelo Skype para Business Server**

|**Classe**|**Alteração**|**Classe ou atributo**|
|:-----|:-----|:-----|
|Usuário  <br/> |Adicionar: mayContain  <br/> Adicionar: mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Contato  <br/> |Adicionar: mayContain  <br/> Adicionar: mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Destinatário do email  <br/> |Adicionar: mayContain  <br/> |msExchUserHoldPolicies  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |Adicionar: mayContain  <br/> |msRTCSIP-MirrorBackEndServer  <br/> |
   

