---
title: Tabela CallType no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: A tabela CallType é uma tabela estática que armazena a lista de possíveis tipos de chamada.
ms.openlocfilehash: 05bfcf5b13735a460f8122fc6b1ce5eeddf94b97
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743187"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>Tabela CallType no Skype for Business Server 2015
 
A tabela CallType é uma tabela estática que armazena a lista de possíveis tipos de chamada.
  
|**Column**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |int  <br/> |Primário  <br/> ||
|**CallType** <br/> |nvarchar  <br/> || Valores permitidos: <br/>  0 - Desconhecido <br/>  1 - Mensagens Instantâneas <br/>  2 - Compartilhamento de Aplicativos <br/>  3 - Áudio <br/>  4 - Áudio e Vídeo <br/>  5 - Transferência de Arquivos <br/> |
   

