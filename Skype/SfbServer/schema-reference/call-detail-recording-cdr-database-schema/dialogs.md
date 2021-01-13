---
title: Tabela Dialogs in Skype for Business Server 2015
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
localization_priority: Normal
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: A tabela Dialogs é uma tabela de suporte que armazena as informações sobre DialogIDs para sessões ponto a ponto.
ms.openlocfilehash: a4f0bb8c63e165985ef09af8f9aafa071529bf1f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816041"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a>Tabela Dialogs in Skype for Business Server 2015
 
A tabela Dialogs é uma tabela de suporte que armazena as informações sobre DialogIDs para sessões ponto a ponto.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primário  <br/> |Hora da solicitação de sessão; usado em conjunto com SessionIDSeq para identificar exclusivamente uma sessão.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primário  <br/> |O número de ID para identificar a sessão. Usado em conjunto com SessionIDTime para identificar exclusivamente uma sessão.  <br/> |
|**ExternalChecksum** <br/> |int  <br/> | <br/> |Checksum of the ExternalID. Esse campo é usado para aumentar a velocidade de pesquisas de banco de dados.  <br/> |
|**ExternalId** <br/> |varbinary(775)  <br/> | <br/> |ID da caixa de diálogo SIP, armazenada como um binário. O formato do binário é:  <br/> dialog;from-tag;to-tag  <br/> Esses dados podem ser convertidos em formato de texto usando esta sintaxe:  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

