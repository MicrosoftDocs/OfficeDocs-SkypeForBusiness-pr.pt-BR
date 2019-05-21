---
title: Tabela de caixas de diálogo no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: A tabela de caixas de diálogo é uma tabela de suporte que armazena as informações sobre DialogIDs em sessões ponto a ponto.
ms.openlocfilehash: 61230cf7f72405c4c5f27ff7b159afe4e5a7842e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296319"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a>Tabela de caixas de diálogo no Skype for Business Server 2015
 
A tabela de caixas de diálogo é uma tabela de suporte que armazena as informações sobre DialogIDs em sessões ponto a ponto.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**Id_da_sessãotime** <br/> |datetime  <br/> |Primária  <br/> |Tempo de solicitação de sessão; usado em conjunto com o SessionIDSeq para identificar exclusivamente uma sessão.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primária  <br/> |Número de identificação para identificar a sessão. Usado em conjunto com a Identificação_da_sessãotime para identificar exclusivamente uma sessão.  <br/> |
|**ExternalChecksum** <br/> |int  <br/> | <br/> |Checksum da externalId. Este campo é usado para aumentar a velocidade das pesquisas do banco de dados.  <br/> |
|**ExternalId** <br/> |varbinary (775)  <br/> | <br/> |ID da caixa de diálogo SIP, armazenada como um binário. O formato do binário é:  <br/> caixa de diálogo; de-marca; até-marca  <br/> Esses dados podem ser convertidos em um formato de texto usando esta sintaxe:  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

