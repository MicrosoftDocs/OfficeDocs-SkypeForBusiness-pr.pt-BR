---
title: Tabela de registro
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
description: Cada registro representa um evento de registro de usuário.
ms.openlocfilehash: 1a487a01b0f8b3f6a087099daa32da99b7007445
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930599"
---
# <a name="registration-table"></a>Tabela de registro
 
Cada registro representa um evento de registro de usuário.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primária, estrangeira  <br/> |Hora da solicitação de sessão. Usado em conjunto com **SessionIdSeq** para identificar exclusivamente uma sessão. Consulte a [tabela no Skype para Business Server 2015 de diálogos](dialogs.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primária, estrangeira  <br/> |Número de identificação para identificar a sessão. Usado em conjunto com **SessionIdTime** para identificar exclusivamente uma sessão. Consulte a [tabela no Skype para Business Server 2015 de diálogos](dialogs.md) para obter mais informações. <br/> |
|**UserId** <br/> |int  <br/> |Externa  <br/> |ID do usuário. Consulte a [tabela de usuários](users.md) para obter mais informações. <br/> |
|**EndpointId** <br/> |Identificador exclusivo  <br/> ||Um GUID para identificar um ponto de extremidade do registro. Geralmente, o evento register do mesmo computador do mesmo usuário terá a mesma ID de ponto de extremidade. Máquinas diferentes têm uma ID de ponto de extremidade diferente.  <br/> |
|**EndpointEra** <br/> |Identificador exclusivo  <br/> ||ID usado para diferenciar registros que envolvam o mesmo usuário e o mesmo ponto de extremidade.  <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
|**ClientVersionId** <br/> |int  <br/> |Externa  <br/> |Versão de cliente do usuário atual. Consulte a [tabela ClientVersions Skype para Business Server 2015](clientversions.md) para obter mais informações. <br/> |
|**RegistrarId** <br/> |int  <br/> |Externa  <br/> |ID do servidor registrador usados para o registro. Consulte a [tabela de servidores](servers.md) para obter mais informações. <br/> |
|**PoolId** <br/> |int  <br/> |Externa  <br/> |ID do pool no qual a sessão foi capturada. Consulte a [tabela de Pools](pools.md) para obter mais informações. <br/> |
|**EdgeServerId** <br/> |int  <br/> |Externa  <br/> |O registro do servidor de borda está passando pelo. Consulte a [tabela EdgeServers no Skype para Business Server 2015](edgeservers.md) para obter mais informações. <br/> |
|**IsInternal** <br/> |Bit  <br/> ||Se o usuário está conectado internamente ou não.  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> ||Se o UserService esteja disponível ou não.  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> ||Quer registre o registrador principal ou não.  <br/> |
|**IsPrimaryRegistrarCentral** <br/> |bit  <br/> ||Indica se ou não o usuário está registrado com um aparelho de filial persistente.  <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
|**RegisterTime** <br/> |datetime  <br/> ||Período de registro.  <br/> |
|**DeRegisterTime** <br/> |datetime  <br/> ||Cancelamento de registro tempo.  <br/> |
|**ResponseCode** <br/> |int  <br/> ||Código de resposta da solicitação de registro.  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||ID de diagnóstico da solicitação de registro. Isso indica que tipo de informações de diagnóstico.  <br/> |
|**DeviceId** <br/> |int  <br/> |Externa  <br/> |O dispositivo que vem de solicitação de registro. Consulte a [tabela de dispositivos no Skype para Business Server 2015](devices.md) para obter mais informações. <br/> |
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Externa  <br/> |O motivo de de-register, como 'iniciadas pelo usuário', "registro vencido", 'cliente fail' e muito mais. Consulte a [tabela DeRegisterType do Skype para Business Server 2015](deregistertype.md) para obter mais informações. <br/> |
|**IPAddress** <br/> |nvarchar(256)  <br/> ||Endereço IP do ponto de extremidade do usuário se registrou. Isso pode ser um endereço IPv4 ou um endereço IPv6.  <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |DateTime  <br/> ||Para uso interno pelo serviço de monitoramento.  <br/> Este campo foi introduzido no Skype para Business Server 2015.  <br/> |
   

