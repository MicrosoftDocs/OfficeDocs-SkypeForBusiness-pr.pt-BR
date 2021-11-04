---
title: Exibição de registro
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
description: A visualização "Registro" armazena informações sobre o registro do usuário. Essa exibição foi introduzida no Lync Server 2013.
ms.openlocfilehash: 4714a4cb0f24a359157ede44b5ab2271a2ff1c7a
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763299"
---
# <a name="registration-view"></a>Exibição de registro
 
A visualização "Registro" armazena informações sobre o registro do usuário. Essa exibição foi introduzida no Lync Server 2013.
  
|**Column**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Hora da solicitação da sessão. Utilizada em conjunto com o SessionIdSeq para identificar de forma exclusiva uma sessão. Consulte a [tabela Dialogs no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Número de identificação para identificar a sessão. Utilizado em conjunto com o SessionIdTime para identificar de forma exclusiva uma sessão. Consulte a [tabela Dialogs no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**RegisterTime** <br/> |datetime  <br/> |Hora do registro.  <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |URI do usuário registrado.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Tipo de  URI do usuário registrado. Consulte a [tabela UriTypes para](uritypes.md) obter mais informações. <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Locatário do usuário registrado. Consulte a [tabela Locatários](tenants.md) para obter mais informações. <br/> |
|**EndpointId** <br/> |uniqueidentifier  <br/> |Identificador exclusivo do ponto de extremidade em que o usuário se registrou.  <br/> |
|**EndpointEra** <br/> |uniqueidentifier  <br/> |Identificador exclusivo usado para diferenciar registros que envolvam o mesmo usuário e o mesmo ponto de extremidade.  <br/> |
|**DeRegisterType** <br/> |datetime  <br/> |Hora do cancelamento do registro.  <br/> |
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> |Motivo para o cancelamento do registro.  <br/> |
|**ClientVersion** <br/> |nvarchar(256)  <br/> |Versão do cliente usada no registro.  <br/> |
|**ClientType** <br/> |int  <br/> |Cliente usado pelo usuário no registro. Consulte a [tabela UserAgentDef](useragentdef.md) para obter mais detalhes. <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |Categoria do cliente do usuário no registro.  <br/> |
|**IpAddress** <br/> |nvarchar(256)  <br/> |Endereço IP com o qual o usuário se registrou. Pode ser um endereço IPv4 ou IPv6.  <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |ID do diálogo de SIP. O formato é:  <br/> dialog;from-tag;to-tag  <br/> |
|**ResponseCode** <br/> |int  <br/> |Código de resposta SIP para convite de sessão. Este campo é normalmente preenchido por dados gerados na mensagem CONVIDAR inicial na sessão. Caso não haja nenhuma mensagem CONVIDAR, o campo é preenchidos com a data e horário da primeira mensagem de SIP relevante (ATÉ LOGO, CANCELAR, MENSAGEM ou INFO).  <br/> |
|**DiagnosticId** <br/> |int  <br/> |ID de diagnóstico registrado do cabeçalho do SIP.  <br/> |
|**Registrador** <br/> |nvarchar(256)  <br/> |FQDN do registrador.  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |FQDN do pool que registrou os dados da sessão.  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> |FQDN do servidor de borda usado pelo usuário que se registrou.  <br/> |
|**IsInternal** <br/> |bit  <br/> |Indica se o usuário fez logon a partir da rede interna.  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> |Indica se o UserService estava disponível no momento do registro.  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> |Indica se o registro foi feito com o registrador principal.  <br/> |
|**DeviceMacAddress** <br/> |bigint  <br/> |Endereço MAC do dispositivo registrado.  <br/> |
|**DeviceManufacturer** <br/> |nvarchar(256)  <br/> |Fabricante do dispositivo registrado. Consulte a [tabela Fabricantes no Skype for Business Server 2015](manufacturers.md) para obter mais informações. <br/> |
|**DeviceHardwareVersion** <br/> |nvarchar(256)  <br/> |Versão do hardware do dispositivo registrado. Consulte a [tabela HardwareVersions no Skype for Business Server 2015](hardwareversions.md) para obter mais informações. <br/> |
   

