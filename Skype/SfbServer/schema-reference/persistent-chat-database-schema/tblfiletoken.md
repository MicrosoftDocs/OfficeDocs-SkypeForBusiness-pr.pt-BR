---
title: tblFileToken
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: tblFileToken contém tokens temporários para fins de transferência de arquivo.
ms.openlocfilehash: 573c921278521eb5b9ed7cc754dec9fa3471e9f4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814589"
---
# <a name="tblfiletoken"></a>tblFileToken
 
tblFileToken contém tokens temporários para fins de transferência de arquivo.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|Filetoken  <br/> |nvarchar (50), NOT NULL  <br/> |Token exclusivo (a GUID).  <br/> |
|fileTokenUserID  <br/> |int, não nulo  <br/> |ID da entidade de segurança que está transferindo o arquivo.  <br/> |
|fileTokenChannelID  <br/> |GUID, não nulo  <br/> |GUID do nó da sala de chat.  <br/> |
|fileTokenExpireDate  <br/> |DateTime, não nulo  <br/> |Tempo de expiração. (Os tokens expiram após 30 minutos, a menos que sejam fixados (consulte as descrições a seguir nesta coluna).  <br/> |
|fileTokenComplianceFileUrl  <br/> |nvarchar(256)  <br/> |URL do arquivo transferido (para uso do serviço de conformidade).  <br/> |
|fileTokenComplianceThumbnailUrl  <br/> |nvarchar(256)  <br/> |URL da miniatura do arquivo transferido (para uso do serviço de conformidade).  <br/> |
|fileTokenComplianceTime  <br/> |datetime2  <br/> |Carimbo de data/hora para a operação de transferência de arquivo real (para uso do serviço de conformidade).  <br/> |
|fileTokenComplianceIsUpload  <br/> |bit  <br/> |Verdadeiro se for carregado; Falso se baixar (para uso do serviço de conformidade).  <br/> |
|fileTokenCompliancePinned  <br/> |bit, e não nulo  <br/> |Verdadeiro se o token estiver fixado. Ele é usado para manter o token na tabela até que o serviço de conformidade tenha a chance de recuperar os campos relevantes dele.  <br/> |
   
**As**

|**Coluna**|**Descrição**|
|:-----|:-----|
|Filetoken  <br/> |Chave primária.  <br/> |
|fileTokenChannelID  <br/> |Chave estrangeira com Lookup na tabela tblNode. nodeGuid.  <br/> |
   

