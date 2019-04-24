---
title: tblFileToken
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: tblFileToken inclui tokens temporários para fins de transferência de arquivo.
ms.openlocfilehash: 46553a4b8752e2a95691dc2042a2632845166fc7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212597"
---
# <a name="tblfiletoken"></a>tblFileToken
 
tblFileToken inclui tokens temporários para fins de transferência de arquivo.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|fileToken  <br/> |nvarchar (50), não nulo  <br/> |Token exclusivo (GUID).  <br/> |
|fileTokenUserID  <br/> |int, não nulo  <br/> |ID da entidade que está transferindo o arquivo.  <br/> |
|fileTokenChannelID  <br/> |GUID, não nulo  <br/> |GUID do nó de sala de chat.  <br/> |
|fileTokenExpireDate  <br/> |DateTime, não nulo  <br/> |Tempo de expiração. (Tokens expiram após 30 minutos, a menos que fixados (consulte as seguintes descrições nessa coluna).  <br/> |
|fileTokenComplianceFileUrl  <br/> |nvarchar(256)  <br/> |URL do arquivo transferido (para uso do serviço de conformidade).  <br/> |
|fileTokenComplianceThumbnailUrl  <br/> |nvarchar(256)  <br/> |URL da miniatura para o arquivo transferido (para uso do serviço de conformidade).  <br/> |
|fileTokenComplianceTime  <br/> |datetime2  <br/> |Carimbo de hora para a operação de transferência de arquivo real (para uso do serviço de conformidade).  <br/> |
|fileTokenComplianceIsUpload  <br/> |bit  <br/> |True se carregar; False se download (para uso do serviço de conformidade).  <br/> |
|fileTokenCompliancePinned  <br/> |bit, não nulo  <br/> |True se o token é fixado. Ele é usado para manter o token na tabela até que tenha o serviço de conformidade a oportunidade de se recuperar os campos relevantes a partir dele.  <br/> |
   
**Chaves**

|**Coluna**|**Descrição**|
|:-----|:-----|
|fileToken  <br/> |Chave primária.  <br/> |
|fileTokenChannelID  <br/> |Chave estrangeira com pesquisa na tabela Nodeguid.  <br/> |
   

