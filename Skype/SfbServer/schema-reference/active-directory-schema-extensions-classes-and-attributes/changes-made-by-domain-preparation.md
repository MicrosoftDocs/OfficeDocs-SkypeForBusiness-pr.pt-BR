---
title: Alterações feitas pela preparação do domínio no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
description: A tabela a seguir lista as entradas de controle de acesso (ACEs) que a preparação do domínio cria na raiz do domínio. Todas as ACEs são herdadas, a menos que indicado de outra forma.
ms.openlocfilehash: afd6747590e09b0b86b42119ad34eb26eaf9d8db
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296711"
---
# <a name="changes-made-by-domain-preparation-in-skype-for-business-server"></a>Alterações feitas pela preparação do domínio no Skype for Business Server
 
A tabela a seguir lista as entradas de controle de acesso (ACEs) que a preparação do domínio cria na raiz do domínio. Todas as ACEs são herdadas, a menos que indicado de outra forma.
  
**ACEs adicionadas à raiz do domínio**

|**ACE**|**RTCUniversal-userreadonly-Group**|**RTCUniversal-ServerReadOnly-Group**|**RTCUniversal-administradores do useradmin**|**RTCHSUniversal-serviços**|**Usuários autenticados**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Contêiner de leitura (não herdado)  <br/> |**Sim** <br/> |**Sim** <br/> |Não  <br/> |Não  <br/> |Não  <br/> |
|Ler propriedades do usuário-User-Restriction-restrições de conta  <br/> |**Sim** <br/> |Não  <br/> |Não  <br/> |Não  <br/> |Não  <br/> |
|Ler propriedades do usuário pessoal-informações  <br/> |**Sim** <br/> |Não  <br/> |Não  <br/> |Não  <br/> |Não  <br/> |
|Ler propriedades do usuário – informações gerais-informações  <br/> |**Sim** <br/> |Não  <br/> |Não  <br/> |Não  <br/> |Não  <br/> |
|Ler as informações públicas de propriedades do usuário  <br/> |**Sim** <br/> |Não  <br/> |Não  <br/> |Não  <br/> |Não  <br/> |
|Ler conjunto de RTCUserSearchProperty de propriedades do usuário  <br/> |**Sim** <br/> |Não  <br/> |Não  <br/> |Não  <br/> |**Sim** <br/> |
|Ler RTCPropertySet de propriedades do usuário  <br/> |**Sim** <br/> |Não  <br/> |Não  <br/> |Não  <br/> |Não  <br/> |
|Gravar endereços de proxy de propriedade de usuário  <br/> |Não  <br/> |Não  <br/> |**Sim** <br/> |Não  <br/> |Não  <br/> |
|Gravar RTCUserSearchProperty de propriedades do usuário-definir  <br/> |Não  <br/> |Não  <br/> |**Sim** <br/> |Não  <br/> |Não  <br/> |
|Gravar usuário do RTCPropertySet de propriedades  <br/> |Não  <br/> |Não  <br/> |**Sim** <br/> |Não  <br/> |Não  <br/> |
|Ler PropertySet DS-Replication-Get-Changes de todos os objetos do Active Directory  <br/> |Não  <br/> |Não  <br/> |Não  <br/> |**Sim** <br/> |Não  <br/> |
   
A tabela a seguir lista as ACEs que a preparação do domínio cria nos três contêineres internos: usuários, computadores e controladores de domínio. Todas as ACEs são herdadas, a menos que indicado de outra forma.
**ACEs adicionadas a contêineres internos**

|**ACE**|**RTCUniversal-userreadonly-Group**|**RTCUniversal-ServerReadOnly-Group**|
|:-----|:-----|:-----|
|Contêiner de leitura (não herdado)  <br/> |**Sim** <br/> |**Sim** <br/> |
   

