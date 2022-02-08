---
title: Alterações feitas pela preparação do domínio Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
description: A tabela a seguir lista as ACEs (entradas de controle de acesso) que a preparação de domínio cria na raiz do domínio. Todas as ACEs serão herdadas, salvo indicação em contrário.
ms.openlocfilehash: 4bf190e0b74e082cf187cde94b3a3062906f0c53
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62389913"
---
# <a name="changes-made-by-domain-preparation-in-skype-for-business-server"></a>Alterações feitas pela preparação do domínio Skype for Business Server
 
A tabela a seguir lista as ACEs (entradas de controle de acesso) que a preparação de domínio cria na raiz do domínio. Todas as ACEs serão herdadas, salvo indicação em contrário.
  
**ACEs adicionadas à raiz do domínio**

|**ACE**|**RTCUniversal-UserReadOnly-Group**|**RTCUniversal-ServerReadOnly-Group**|**RTCUniversal-UserAdmins**|**RTCHSUniversal-Services**|**Authenticated-Users**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Ler contêiner (não herdado)  <br/> |**Sim** <br/> |Sim <br/> |Não  <br/> |Não  <br/> |Não  <br/> |
|Ler User PropertySet User-Account-Restrictions  <br/> |Sim <br/> |Não  <br/> |Não  <br/> |Não  <br/> |Não  <br/> |
|Ler User PropertySet Personal-Information  <br/> |Sim <br/> |Não  <br/> |Não  <br/> |Não  <br/> |Não  <br/> |
|Ler User PropertySet General-Information  <br/> |Sim <br/> |Não  <br/> |Não  <br/> |Não  <br/> |Não  <br/> |
|Ler User PropertySet Public-Information  <br/> |Sim <br/> |Não  <br/> |Não  <br/> |Não  <br/> |Não  <br/> |
|Ler User PropertySet RTCUserSearchProperty-Set  <br/> |Sim <br/> |Não  <br/> |Não  <br/> |Não  <br/> |**Sim** <br/> |
|Ler User PropertySet RTCPropertySet  <br/> |Sim <br/> |Não  <br/> |Não  <br/> |Não  <br/> |Não  <br/> |
|Gravar User Property Proxy-Addresses  <br/> |Não  <br/> |Não  <br/> |Sim <br/> |Não  <br/> |Não  <br/> |
|Gravar User PropertySet RTCUserSearchProperty-Set  <br/> |Não  <br/> |Não  <br/> |Sim <br/> |Não  <br/> |Não  <br/> |
|Gravar User PropertySet RTCPropertySet  <br/> |Não  <br/> |Não  <br/> |Sim <br/> |Não  <br/> |Não  <br/> |
|Ler PropertySet DS-Replication-Get-Changes de todos os objetos do Active Directory  <br/> |Não  <br/> |Não  <br/> |Não  <br/> |Sim <br/> |Não  <br/> |
   
A tabela a seguir lista as ACEs que a preparação do domínio cria nos três contêineres internos: Usuários, Computadores e Controladores de Domínio. Todas as ACEs são herdadas, a menos que especificado de outra forma.
**ACEs adicionadas à contêineres internos**

|**ACE**|**RTCUniversal-UserReadOnly-Group**|**RTCUniversal-ServerReadOnly-Group**|
|:-----|:-----|:-----|
|Ler contêiner (não herdado)  <br/> |**Sim** <br/> |**Sim** <br/> |
   

