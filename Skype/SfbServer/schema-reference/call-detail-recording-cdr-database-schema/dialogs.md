---
title: Tabela de diálogos no Skype para Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: A tabela de caixas de diálogo é uma tabela de suporte que armazena as informações sobre DialogIDs para sessões ponto a ponto.
ms.openlocfilehash: 379956a2c77c60a53e702913d81b25b41dc2fc23
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901126"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a>Tabela de diálogos no Skype para Business Server 2015
 
A tabela de caixas de diálogo é uma tabela de suporte que armazena as informações sobre DialogIDs para sessões ponto a ponto.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primária  <br/> |Hora da solicitação de sessão; usado em conjunto com SessionIDSeq para identificar exclusivamente uma sessão.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primária  <br/> |Número de identificação para identificar a sessão. Usado em conjunto com SessionIDTime para identificar exclusivamente uma sessão.  <br/> |
|**ExternalChecksum** <br/> |int  <br/> | <br/> |Soma de verificação de ExternalID. Este campo é usado para aumentar a velocidade de pesquisas de banco de dados.  <br/> |
|**ExternalId** <br/> |varbinary(775)  <br/> | <br/> |ID de diálogo SIP, armazenado como um binário. O formato do binário é:  <br/> diálogo; da marca; a marca  <br/> Esses dados podem ser convertidos em formato de texto usando esta sintaxe:  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

