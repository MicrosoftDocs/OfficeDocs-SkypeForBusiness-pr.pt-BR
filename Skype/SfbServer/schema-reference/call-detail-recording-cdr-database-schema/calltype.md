---
title: Tabela CallType no Skype for Business Server 2015
ms.reviewer: null
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
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: A tabela CallType é uma tabela estática que armazena a lista de possíveis tipos de chamada.
---

# <a name="calltype-table-in-skype-for-business-server-2015"></a>Tabela CallType no Skype for Business Server 2015
 
A tabela CallType é uma tabela estática que armazena a lista de possíveis tipos de chamada.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |int  <br/> |Primário  <br/> ||
|**CallType** <br/> |nvarchar  <br/> || Valores permitidos: <br/>  0 - Desconhecido <br/>  1 - Mensagens Instantâneas <br/>  2 - Compartilhamento de Aplicativos <br/>  3 - Áudio <br/>  4 - Áudio e Vídeo <br/>  5 - Transferência de Arquivos <br/> |
   

