---
title: Alterações feitas pela preparação do domínio no Skype para Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
description: A tabela a seguir lista as entradas de controle de acesso (ACEs) que a preparação de domínio cria na raiz do domínio. Todas as ACEs são herdadas, a menos que estipulado de outra forma.
ms.openlocfilehash: 5cf239e37badafee9980140d08fd20a11e3c233d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213449"
---
# <a name="changes-made-by-domain-preparation-in-skype-for-business-server"></a>Alterações feitas pela preparação do domínio no Skype para Business Server
 
A tabela a seguir lista as entradas de controle de acesso (ACEs) que a preparação de domínio cria na raiz do domínio. Todas as ACEs são herdadas, a menos que estipulado de outra forma.
  
**ACEs adicionadas à raiz do domínio**

|**ACE**|**Grupo de UserReadOnly RTCUniversal**|**Grupo de ServerReadOnly RTCUniversal**|**RTCUniversal-UserAdmins**|**Serviços de RTCHSUniversal**|**Usuários autenticados**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Ler contêiner (não herdado)  <br/> |**Sim** <br/> |**Sim** <br/> |Não  <br/> |Não  <br/> |Não  <br/> |
|Ler PropertySet User-Account-Restrictions do usuário  <br/> |**Sim** <br/> |Não  <br/> |Não  <br/> |Não  <br/> |Não  <br/> |
|Ler User PropertySet Personal-Information  <br/> |**Sim** <br/> |Não  <br/> |Não  <br/> |Não  <br/> |Não  <br/> |
|Ler User PropertySet General-Information  <br/> |**Sim** <br/> |Não  <br/> |Não  <br/> |Não  <br/> |Não  <br/> |
|Ler User PropertySet Public-Information  <br/> |**Sim** <br/> |Não  <br/> |Não  <br/> |Não  <br/> |Não  <br/> |
|Ler User PropertySet RTCUserSearchProperty-Set  <br/> |**Sim** <br/> |Não  <br/> |Não  <br/> |Não  <br/> |**Sim** <br/> |
|Ler User PropertySet RTCPropertySet  <br/> |**Sim** <br/> |Não  <br/> |Não  <br/> |Não  <br/> |Não  <br/> |
|Escrever os endereços de Proxy de propriedade de usuário  <br/> |Não  <br/> |Não  <br/> |**Sim** <br/> |Não  <br/> |Não  <br/> |
|Gravar User PropertySet RTCUserSearchProperty-Set  <br/> |Não  <br/> |Não  <br/> |**Sim** <br/> |Não  <br/> |Não  <br/> |
|Gravar User PropertySet RTCPropertySet  <br/> |Não  <br/> |Não  <br/> |**Sim** <br/> |Não  <br/> |Não  <br/> |
|Ler PropertySet DS-Replication-Get-Changes de todos os objetos do Active Directory  <br/> |Não  <br/> |Não  <br/> |Não  <br/> |**Sim** <br/> |Não  <br/> |
   
A tabela a seguir lista as ACEs que preparação de domínio cria dos três contêineres internos: usuários, computadores e controladores de domínio. Todas as ACEs são herdadas, a menos que estipulado de outra forma.
**ACEs adicionadas à contêineres internos**

|**ACE**|**Grupo de UserReadOnly RTCUniversal**|**Grupo de ServerReadOnly RTCUniversal**|
|:-----|:-----|:-----|
|Ler contêiner (não herdado)  <br/> |**Sim** <br/> |**Sim** <br/> |
   

