---
title: Modo de exibição registro
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
ms.assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
description: O modo de exibição de registro armazena informações sobre o registro de usuário. Este modo de exibição foi apresentado no Lync Server 2013.
ms.openlocfilehash: 0ee19d4addae9ee7318828c4ab294dc15bd72f86
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814949"
---
# <a name="registration-view"></a>Modo de exibição registro
 
O modo de exibição de registro armazena informações sobre o registro de usuário. Este modo de exibição foi apresentado no Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|**Id_da_sessãotime** <br/> |datetime  <br/> |Tempo de solicitação de sessão. Usado em conjunto com o SessionIdSeq para identificar exclusivamente uma sessão. Consulte a [tabela de diálogos no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Número de identificação para identificar a sessão. Usado em conjunto com a Identificação_da_sessãotime para identificar exclusivamente uma sessão. Consulte a [tabela de diálogos no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**Registertime** <br/> |datetime  <br/> |Hora em que ocorreu o registro.  <br/> |
|**UserUri** <br/> |nvarchar (450)  <br/> |URL do usuário que se cadastrou.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI do usuário que se cadastrou. Consulte a [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
|**Userlocatário** <br/> |nvarchar(256)  <br/> |Locatário do usuário que se cadastrou. Consulte a [tabela locatários](tenants.md) para obter mais informações. <br/> |
|**Endpointid** <br/> |identificador  <br/> |Identificador exclusivo do ponto de extremidade do usuário registrado.  <br/> |
|**Ponteiro de fim** <br/> |identificador  <br/> |Identificador exclusivo usado para diferenciar os registros que envolvem o mesmo usuário e o mesmo ponto de extremidade.  <br/> |
|**DeRegisterType** <br/> |datetime  <br/> |Tempo em que o cancelamento ocorreu.  <br/> |
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> |Motivo do cancelamento de registro.  <br/> |
|**ClientVersion** <br/> |nvarchar(256)  <br/> |Versão do cliente usada pelo usuário que se cadastrou.  <br/> |
|**ClientType** <br/> |int  <br/> |Cliente usado pelo usuário que se cadastrou. Consulte a [tabela UserAgentDef](useragentdef.md) para obter mais detalhes. <br/> |
|**ClientCategory** <br/> |nvarchar (64)  <br/> |Categoria do cliente usada pelo usuário que se cadastrou.  <br/> |
|**IP** <br/> |nvarchar(256)  <br/> |Endereço IP com o qual o usuário se cadastrou. Pode ser um endereço IPv4 ou IPv6.  <br/> |
|**Caixa de diálogo** <br/> |VARSTRING (775)  <br/> |ID da caixa de diálogo SIP. O formato do é:  <br/> caixa de diálogo; de-marca; até-marca  <br/> |
|**ResponseCode** <br/> |int  <br/> |Código de resposta SIP para o convite da sessão. Geralmente, esse campo é preenchido por dados gerados da mensagem de convite inicial na sessão. Se não houver nenhuma mensagem de convite, o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (até mais, cancelamento, mensagem ou informações).  <br/> |
|**Diagnosticid** <br/> |int  <br/> |ID de diagnóstico capturada do cabeçalho SIP.  <br/> |
|**Registrador** <br/> |nvarchar(256)  <br/> |FQDN do registrador.  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |FQDN do pool que capturou os dados da sessão.  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> |FQDN do servidor de borda usado pelo usuário que se cadastrou.  <br/> |
|**IsInternal** <br/> |bit  <br/> |Indica se o usuário está conectado à rede interna.  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> |Indica se o UserService estava disponível no momento do registro.  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> |Indica se o registro foi com o registrador principal.  <br/> |
|**DeviceMacAddress** <br/> |bigint  <br/> |Endereço MAC do dispositivo registrado.  <br/> |
|**DeviceManufacturer** <br/> |nvarchar(256)  <br/> |Fabricante do dispositivo registrado. Consulte a [tabela fabricantes no Skype for Business Server 2015](manufacturers.md) para obter mais informações. <br/> |
|**DeviceHardwareVersion** <br/> |nvarchar(256)  <br/> |Versão de hardware do dispositivo registrada. Consulte a [tabela HardwareVersions no Skype for Business Server 2015](hardwareversions.md) para obter mais informações. <br/> |
   

