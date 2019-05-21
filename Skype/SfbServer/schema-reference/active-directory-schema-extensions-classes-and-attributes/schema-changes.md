---
title: Alterações de esquema no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: Antes de implantar e operar o Skype for Business Server, você deve preparar os serviços de domínio Active Directory estendendo o esquema. As extensões de esquema adicionam as classes e os atributos necessários para o Skype for Business Server.
ms.openlocfilehash: 34f97f7a37adc23635f938fb12c9a72e22429538
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296655"
---
# <a name="schema-changes-in-skype-for-business-server"></a>Alterações de esquema no Skype for Business Server
 
Antes de implantar e operar o Skype for Business Server, você deve preparar os serviços de domínio Active Directory estendendo o esquema. As extensões de esquema adicionam as classes e os atributos necessários para o Skype for Business Server.

> [!NOTE]
> Se você estiver atualizando do Lync Server 2013 para o Skype for Business Server 2015, nenhuma alteração de esquema será feita e, portanto, este artigo não se aplica.
  
O Skype for Business Server exige várias classes e atributos novos e modifica algumas classes e atributos existentes. Além disso, muitas informações de configuração do Skype for Business Server são armazenadas no repositório de gerenciamento central, em vez de no AD DS, como nas versões anteriores. As informações a seguir ainda são armazenadas no AD DS no Skype for Business Server:
  
- **Extensões de esquema**:
    
  - Extensões de objetos de usuário
    
  - Extensões para classes que mantêm a compatibilidade com versões anteriores do Lync Server com suporte.
    
- **Dados** do (armazenado no esquema estendido do Skype for Business Server e em classes de esquema existentes):
    
  - URI (Uniform Resource Identifier) do usuário SIP e outras configurações do usuário
    
  - Objetos de contato para aplicativos como o assistente de grupo de resposta e conferência
    
  - Um ponteiro para o repositório de gerenciamento central
    
  - Conta de autenticação Kerberos (um objeto de computador opcional)
    
Este tópico descreve as alterações de esquema do Active Directory exigidas pelo Skype for Business Server. Ele não descreve as alterações de esquema que foram introduzidas por versões anteriores do Office Communications Server. Para obter uma lista de classes e suas descrições, consulte [classes e descrições de esquema no Skype for Business Server](schema-classes-and-descriptions.md). Para obter uma lista de atributos e suas descrições, consulte [atributos e descrições do esquema no Skype for Business Server](schema-attributes-and-descriptions.md). Para obter uma lista de classes com os atributos que elas podem conter, consulte [atributos de esquema por classe no Skype for Business Server](schema-attributes-by-class.md).
  
O prefixo msRTCSIP identifica classes e atributos que são específicos do Skype for Business Server.
  
## <a name="new-active-directory-attributes"></a>Novos atributos do Active Directory

A tabela a seguir descreve os atributos do Active Directory que são adicionados pelo Skype for Business Server.
  
**Atributos adicionados pelo Skype for Business Server**

|**Atributo**|**Descrição**|
|:-----|:-----|
|msExchUserHoldPolicies  <br/> |Esse atributo de vários valores contém identificadores para políticas de retenção que se aplicam ao usuário. As políticas de retenção preservam os itens da caixa de correio para o usuário durante o período de espera. Esse atributo é compartilhado com o Exchange 2013.  <br/> |
|msRTCSIP-UserRoutingGroupId  <br/> |Esta é a ID do grupo de roteamento SIP. Os usuários no mesmo grupo serão registrados no mesmo servidor front-end.  <br/> |
|msRTCSIP-MirrorBackEndServer  <br/> |Esse atributo é usado para armazenar o back-end do SQL Server espelhado usado pelo pool de front-ends.  <br/> |
   
## <a name="modified-active-directory-classes"></a>Classes modificadas do Active Directory

A tabela a seguir descreve as classes do Active Directory modificadas pelo Skype for Business Server.
  
**Classes modificadas pelo Skype for Business Server**

|**Classe**|**Alteração**|**Classe ou atributo**|
|:-----|:-----|:-----|
|Usuário  <br/> |Adicionar: mayContain  <br/> Adicionar: mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Entrando  <br/> |Adicionar: mayContain  <br/> Adicionar: mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|E-mail-destinatário  <br/> |Adicionar: mayContain  <br/> |msExchUserHoldPolicies  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |Adicionar: mayContain  <br/> |msRTCSIP-MirrorBackEndServer  <br/> |
   

