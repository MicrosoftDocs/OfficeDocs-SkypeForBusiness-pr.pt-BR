---
title: tblFileToken
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: tblFileToken inclui tokens temporários para fins de transferência de arquivos.
ms.openlocfilehash: 73958e48814a27e5871b2a0af73d77a55531e49b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60831775"
---
# <a name="tblfiletoken"></a>tblFileToken
 
tblFileToken inclui tokens temporários para fins de transferência de arquivos.
  
**Columns**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|fileToken  <br/> |nvarchar (50), not null  <br/> |Token exclusivo (uma GUID).  <br/> |
|fileTokenUserID  <br/> |int, not null  <br/> |ID da entidade de segurança que está transferindo o arquivo.  <br/> |
|fileTokenChannelID  <br/> |GUID, não vazio  <br/> |GUID do nó da sala de chat.  <br/> |
|fileTokenExpireDate  <br/> |datetime, not null  <br/> |Tempo de expiração. (Tokens expiram após 30 minutos, a menos que fixado (consultar as descrições a seguir nesta coluna).  <br/> |
|fileTokenComplianceFileUrl  <br/> |nvarchar(256)  <br/> |URL do arquivo transferido (para uso do serviço de Conformidade).  <br/> |
|fileTokenComplianceThumbnailUrl  <br/> |nvarchar(256)  <br/> |URL da miniatura para o arquivo transferido (para uso do serviço de Conformidade).  <br/> |
|fileTokenComplianceTime  <br/> |datetime2  <br/> |Carimbo de data e hora para a operação de transferência de arquivo atual (para uso do serviço de Conformidade).  <br/> |
|fileTokenComplianceIsUpload  <br/> |bit  <br/> |Verdadeiro em caso de upload; Falso se download (para uso do serviço de Conformidade).  <br/> |
|fileTokenCompliancePinned  <br/> |bit, não vazio  <br/> |Verdadeiro se fixado. Ele é usado para manter o token na tabela até que o serviço de Conformidade tenha a chance de recuperar os campos relevantes dele.  <br/> |
   
**Teclas**

|**Coluna**|**Descrição**|
|:-----|:-----|
|fileToken  <br/> |Chave primária.  <br/> |
|fileTokenChannelID  <br/> |Chave estrangeira com pesquisa na tabela tblNode.nodeGuid.  <br/> |
   

