---
title: tblConfig
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: o tblConfig contém uma configuração sem suporte do servidor de chat persistente, em uma linha.
ms.openlocfilehash: 244eebcb88c67b521022f9d64888678f221d2369
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295451"
---
# <a name="tblconfig"></a>tblConfig
 
o tblConfig contém uma configuração sem suporte do servidor de chat persistente, em uma linha.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|configLabel  <br/> |nvarchar (255), NOT NULL  <br/> |Contém "pool".  <br/> |
|configContent  <br/> |nvarchar (max)  <br/> |Conteúdo de configuração.  <br/> |
|configPoolID  <br/> |GUID, não nulo  <br/> |ID exclusiva da instância do banco de dados.  <br/> |
   
**Chave**

|**Coluna**|**Descrição**|
|:-----|:-----|
|configLabel  <br/> |Chave primária.  <br/> |
   

