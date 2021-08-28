---
title: Tabela caixas de diálogo no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: A tabela Dialogs é uma tabela de suporte que armazena as informações sobre DialogIDs para sessões ponto a ponto.
ms.openlocfilehash: 6f5abd6326ca1f00a631462c43c8814fb3822f41
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580425"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a>Tabela caixas de diálogo no Skype for Business Server 2015
 
A tabela Dialogs é uma tabela de suporte que armazena as informações sobre DialogIDs para sessões ponto a ponto.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primário  <br/> |Hora da solicitação de sessão; usado em conjunto com SessionIDSeq para identificar exclusivamente uma sessão.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primário  <br/> |O número de ID para identificar a sessão. Usado em conjunto com SessionIDTime para identificar exclusivamente uma sessão.  <br/> |
|**ExternalChecksum** <br/> |int  <br/> | <br/> |Checksum do ExternalID. Esse campo é usado para aumentar a velocidade das pesquisas de banco de dados.  <br/> |
|**ExternalId** <br/> |varbinary(775)  <br/> | <br/> |ID da caixa de diálogo SIP, armazenada como um binário. O formato do binário é:  <br/> dialog;from-tag;to-tag  <br/> Esses dados podem ser convertidos em formato de texto usando esta sintaxe:  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

