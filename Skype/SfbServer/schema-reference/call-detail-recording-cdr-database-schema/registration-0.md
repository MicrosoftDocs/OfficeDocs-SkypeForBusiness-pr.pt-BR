---
title: Exibir registro
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
description: O modo de exibição do registro armazena informações sobre o registro do usuário. Este modo de exibição foi introduzido no Lync Server 2013.
ms.openlocfilehash: 820e99296b93743d13709e5296ed1c317079be3b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930655"
---
# <a name="registration-view"></a>Exibir registro
 
O modo de exibição do registro armazena informações sobre o registro do usuário. Este modo de exibição foi introduzido no Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Hora da solicitação de sessão. Usado em conjunto com SessionIdSeq para identificar exclusivamente uma sessão. Consulte a [tabela no Skype para Business Server 2015 de diálogos](dialogs.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Número de identificação para identificar a sessão. Usado em conjunto com SessionIdTime para identificar exclusivamente uma sessão. Consulte a [tabela no Skype para Business Server 2015 de diálogos](dialogs.md) para obter mais informações. <br/> |
|**RegisterTime** <br/> |datetime  <br/> |Hora em que o registro ocorreu.  <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |URI do usuário registrado.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI do usuário registrado. Consulte a [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Locatário do usuário que esteja registrado. Consulte a [tabela de inquilinos](tenants.md) para obter mais informações. <br/> |
|**EndpointId** <br/> |Identificador exclusivo  <br/> |Identificador exclusivo do ponto de extremidade do usuário se registrou.  <br/> |
|**EndpointEra** <br/> |Identificador exclusivo  <br/> |Identificador exclusivo usado para diferenciar registros que envolvam o mesmo usuário e o mesmo ponto de extremidade.  <br/> |
|**DeRegisterType** <br/> |datetime  <br/> |Hora cancelamento.  <br/> |
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> |Motivo para o cancelamento do registro.  <br/> |
|**ClientVersion** <br/> |nvarchar(256)  <br/> |Versão do cliente usado pelo usuário que esteja registrado.  <br/> |
|**ClientType** <br/> |int  <br/> |Cliente usado pelo usuário que esteja registrado. Consulte a [tabela UserAgentDef](useragentdef.md) para obter mais detalhes. <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |Categoria do cliente usado pelo usuário que registrado.  <br/> |
|**IpAddress** <br/> |nvarchar(256)  <br/> |O usuário registrado com o endereço IP. Isso pode ser um endereço IPv4 ou IPv6.  <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |ID de diálogo SIP. O formato do é:  <br/> diálogo; da marca; a marca  <br/> |
|**ResponseCode** <br/> |int  <br/> |Código de resposta SIP para o convite de sessão. Normalmente, este campo é preenchido pelos dados gerados a partir da mensagem de convite inicial da sessão. Se não houver nenhuma mensagem CONVIDAR o campo é preenchido com a data e hora da primeira relevante mensagem SIP (BYE, cancelar, mensagem ou INFO).  <br/> |
|**DiagnosticId** <br/> |int  <br/> |ID de diagnóstico capturado do cabeçalho SIP.  <br/> |
|**Registrador** <br/> |nvarchar(256)  <br/> |FQDN do registrador.  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |FQDN do pool que capturou os dados para a sessão.  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> |FQDN do servidor de borda usado pelo usuário registrado.  <br/> |
|**IsInternal** <br/> |bit  <br/> |Indica se o usuário fez logon da rede interna.  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> |Indica se o UserService estava disponível no momento do registro.  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> |Indica se o registro foi com o registrador principal.  <br/> |
|**DeviceMacAddress** <br/> |bigint  <br/> |Endereço MAC do dispositivo registrado.  <br/> |
|**DeviceManufacturer** <br/> |nvarchar(256)  <br/> |Fabricante do dispositivo registrado. Consulte a [tabela de fabricantes no Skype para Business Server 2015](manufacturers.md) para obter mais informações. <br/> |
|**DeviceHardwareVersion** <br/> |nvarchar(256)  <br/> |Versão de hardware do dispositivo registrado. Consulte a [tabela HardwareVersions no Skype para Business Server 2015](hardwareversions.md) para obter mais informações. <br/> |
   

