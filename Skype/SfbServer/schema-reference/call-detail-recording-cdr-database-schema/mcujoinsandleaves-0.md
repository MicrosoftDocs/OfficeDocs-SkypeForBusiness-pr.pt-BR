---
title: Exibição McuJoinsAndLeaves
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
ms.assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
description: A exibição McuJoinsAndLeaves armazena informações sobre como os usuários unem e deixam informações para um servidor de conferência. Cada registro nesse modo de exibição contém detalhes da chamada sobre uma combinação de um servidor de ingresso ou de saída e conferência do usuário. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
ms.openlocfilehash: 7a7569795d55620051e617d9312d87f3c96c628a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815089"
---
# <a name="mcujoinsandleaves-view"></a>Exibição McuJoinsAndLeaves
 
A exibição McuJoinsAndLeaves armazena informações sobre como os usuários unem e deixam informações para um servidor de conferência. Cada registro nesse modo de exibição contém detalhes da chamada sobre uma combinação de um servidor de ingresso ou de saída e conferência do usuário. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|**Id_da_sessãotime** <br/> |datetime  <br/> |Hora da ocorrência da conferência. Usado em conjunto com SessionIdSeq para identificar uma instância de conferência de maneira exclusiva. Consulte a [tabela conferências no Skype for Business Server 2015](conferences.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Número de identificação para identificar a instância de conferência. Usado em conjunto com a Identificação_da_sessãotime para identificar exclusivamente uma instância de conferência. Consulte a [tabela conferências no Skype for Business Server 2015](conferences.md) para obter mais informações. <br/> |
|**McuUri** <br/> |nvarchar(256)  <br/> |O URI do servidor de conferência ao qual o usuário se conectou.  <br/> |
|**McuUriType** <br/> |nvarchar(256)  <br/> |O URI do servidor de conferência ao qual o usuário se conectou. Consulte a [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
|**UserUri** <br/> |nvarchar (450)  <br/> |O URI do usuário cujas informações de associação/licença do servidor de conferência foram capturadas.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |O tipo de URI do usuário cujas informações de associação/licença do servidor de conferência foram capturadas. Consulte a [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
|**Userlocatário** <br/> |nvarchar(256)  <br/> |O locatário do usuário cujas informações de associação/licença do servidor de conferência foram capturadas. Consulte a [tabela locatários](tenants.md) para obter mais informações. <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |A versão do cliente usada pelo usuário cujas informações de associação/licença do servidor de conferência foram capturadas.  <br/> |
|**Userclienttype** <br/> |int  <br/> |O cliente usado pelo usuário cujas informações de associação/licença do servidor de conferência foram capturadas. Consulte a [tabela UserAgentDef](useragentdef.md) para obter mais detalhes. <br/> |
|**UserClientCategory** <br/> |nvarchar (64)  <br/> |O nome da categoria do cliente usado pelo usuário cujas informações de associação/licença do servidor de conferência foram capturadas.  <br/> |
|**McuUserInstance** <br/> |int  <br/> |Identifica exclusivamente a combinação de usuário/dispositivo para usuários conectados simultaneamente a vários dispositivos.  <br/> |
|**IsUserFromPstn** <br/> |bit  <br/> |Bit que representa se o usuário é um usuário interno ou não.  <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Tempo de solicitação de sessão. Usado em conjunto com o SessionIdSeq para identificar exclusivamente uma sessão. Consulte a [tabela de diálogos no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Número de identificação para identificar a sessão. Usado em conjunto com a Identificação_da_sessãotime para identificar exclusivamente uma sessão. Consulte a [tabela de diálogos no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**Caixa de diálogo** <br/> |varchar (775)  <br/> |ID da caixa de diálogo SIP da sessão. O formato é: caixa de diálogo; de-marca; para-marca.  <br/> |
|**Userjointime** <br/> |datetime  <br/> |Vez que o usuário ingressou no servidor de conferência.  <br/> |
|**Userleavetime** <br/> |datetime  <br/> |Vez que o usuário saiu do servidor de conferência.  <br/> |
   

