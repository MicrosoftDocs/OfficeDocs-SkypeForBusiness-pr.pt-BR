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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
description: A tabela a seguir lista as entradas de controle de acesso (ACEs) que a preparação do domínio cria na raiz do domínio. Todas as ACEs são herdadas, a menos que indicado de outra forma.
ms.openlocfilehash: 8a087dfbbd8b670467727803f996694a816cc065
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815539"
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
   

