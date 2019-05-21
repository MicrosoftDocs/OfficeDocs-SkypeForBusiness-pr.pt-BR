---
title: Exibição FocusJoinsAndLeaves
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 226460ef-766f-4d61-80cb-f332b65a210d
description: A exibição FocusJoinsAndLeaves armazena informações sobre as informações de ingressar e sair de uma conferência. Cada conferência é representada por um registro escrito a cada vez que um usuário entra e sai da conferência. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
ms.openlocfilehash: f739ae390b636913d96b49dd516d2618c72515e6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296214"
---
# <a name="focusjoinsandleaves-view"></a>Exibição FocusJoinsAndLeaves
 
A exibição FocusJoinsAndLeaves armazena informações sobre as informações de ingressar e sair de uma conferência. Cada conferência é representada por um registro escrito a cada vez que um usuário entra e sai da conferência. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|**Id_da_sessãotime** <br/> |datetime  <br/> |Hora da ocorrência da conferência. Usado em conjunto com SessionIdSeq para identificar uma instância de conferência de maneira exclusiva. Consulte a [tabela conferências no Skype for Business Server 2015](conferences.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Número de identificação para identificar a instância de conferência. Usado em conjunto com a Identificação_da_sessãotime para identificar exclusivamente uma instância de conferência. Consulte a [tabela conferências no Skype for Business Server 2015](conferences.md) para obter mais informações. <br/> |
|**UserUri** <br/> |nvarchar (450)  <br/> |URI do usuário cujas informações de associação/licença da conferência foram capturadas.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI do usuário cujas informações de associação/licença de conferência foram capturadas. Consulte a [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
|**Userlocatário** <br/> |nvarchar(256)  <br/> |Locatário do usuário cujas informações de associação/licença da conferência foram capturadas. Consulte a [tabela locatários](tenants.md) para obter mais informações. <br/> |
|**Userendpointid** <br/> |identificador  <br/> |Identificador exclusivo do usuário cujas informações de associação/licença da conferência foram capturadas.  <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |Versão do cliente usada pelo usuário cujas informações de associação/licença da conferência foram capturadas.  <br/> |
|**Userclienttype** <br/> |int  <br/> |Cliente usado pelo usuário cujas informações de associação/licença da conferência foram capturadas. Consulte a [tabela UserAgentDef](useragentdef.md) para obter mais detalhes. <br/> |
|**UserClientCategory** <br/> |nvarchar (64)  <br/> |Nome da categoria do cliente usado pelo usuário cujas informações de associação/licença da conferência foram capturadas.  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||
|**IsuserInternal** <br/> |bit  <br/> |Bit que representa se o usuário é um usuário interno ou não.  <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Tempo de solicitação de sessão. Usado em conjunto com o SessionIdSeq para identificar exclusivamente uma sessão. Consulte a [tabela de diálogos no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Se um usuário estiver conectado em vários computadores ou dispositivos ao mesmo tempo, o UserInstance será usado para identificar exclusivamente a combinação de usuário/dispositivo.  <br/> |
|**Caixa de diálogo** <br/> |varchar (775)  <br/> |ID da caixa de diálogo SIP da sessão. O formato é: caixa de diálogo; de-marca; para-marca.  <br/> |
|**Userjointime** <br/> |datetime  <br/> |Hora em que o usuário ingressou na conferência.  <br/> |
|**Userleavetime** <br/> |datetime  <br/> |Tempo em que o usuário saiu da conferência.  <br/> |
|**Função** <br/> |nvarchar(256)  <br/> |Função do usuário na conferência, como apresentador ou participante.  <br/> |
   

