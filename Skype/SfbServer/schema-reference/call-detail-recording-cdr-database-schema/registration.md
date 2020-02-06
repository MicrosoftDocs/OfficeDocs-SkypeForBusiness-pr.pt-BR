---
title: Tabela de registro
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
description: Cada registro representa um evento de registro de usuário.
ms.openlocfilehash: bca31b85a0b88854760c2a79528792ee82bd272e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814939"
---
# <a name="registration-table"></a>Tabela de registro
 
Cada registro representa um evento de registro de usuário.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**Id_da_sessãotime** <br/> |datetime  <br/> |Primário, estrangeiro  <br/> |Tempo de solicitação de sessão. Usado em conjunto com o **SessionIdSeq** para identificar exclusivamente uma sessão. Consulte a [tabela de diálogos no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primário, estrangeiro  <br/> |Número de identificação para identificar a sessão. Usado em conjunto com a **identificação_da_sessãotime** para identificar exclusivamente uma sessão. Consulte a [tabela de diálogos no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**ID** <br/> |int  <br/> |Exterior  <br/> |A ID de usuário. Para obter mais informações, consulte a [tabela usuários](users.md) . <br/> |
|**Endpointid** <br/> |identificador  <br/> ||Um GUID para identificar um ponto de extremidade de registro. Geralmente, o evento Register do mesmo computador do mesmo usuário terá a mesma ID de ponto de extremidade. Máquinas diferentes têm uma ID de ponto de extremidade diferente.  <br/> |
|**Ponteiro de fim** <br/> |Identificador  <br/> ||ID usada para diferenciar os registros que envolvem o mesmo usuário e o mesmo ponto de extremidade.  <br/> Este campo foi apresentado no Microsoft Lync Server 2013.  <br/> |
|**ClientVersionId** <br/> |int  <br/> |Exterior  <br/> |Versão cliente do usuário atual. Consulte a [tabela ClientVersions no Skype for Business Server 2015](clientversions.md) para obter mais informações. <br/> |
|**Registrador de registro** <br/> |int  <br/> |Exterior  <br/> |ID do servidor de registrador usado para registro. Consulte a [tabela servidores](servers.md) para obter mais informações. <br/> |
|**Poolid** <br/> |int  <br/> |Exterior  <br/> |ID do pool no qual a sessão foi capturada. Consulte a [tabela de grupos](pools.md) para obter mais informações. <br/> |
|**EdgeServerId** <br/> |int  <br/> |Exterior  <br/> |Servidor de borda no qual o registro está indo. Consulte a [tabela EdgeServers no Skype for Business Server 2015](edgeservers.md) para obter mais informações. <br/> |
|**IsInternal** <br/> |Bit  <br/> ||Se o usuário está conectado de Internal ou not.  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> ||Se o UserService está disponível ou não.  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> ||Se registrar ao registrador principal ou não.  <br/> |
|**IsPrimaryRegistrarCentral** <br/> |bit  <br/> ||Indica se o usuário está ou não registrado em um aparelho de ramificação sobreviventes.  <br/> Este campo foi apresentado no Microsoft Lync Server 2013.  <br/> |
|**Registertime** <br/> |datetime  <br/> ||Hora do registro.  <br/> |
|**Cancelar registro** <br/> |datetime  <br/> ||Hora de cancelamento de registro.  <br/> |
|**ResponseCode** <br/> |int  <br/> ||Código de resposta da solicitação de registro.  <br/> |
|**Diagnosticid** <br/> |int  <br/> ||ID do diagnóstico da solicitação de registro. Isso indica que o tipo de informações de diagnóstico.  <br/> |
|**DeviceId** <br/> |int  <br/> |Exterior  <br/> |O dispositivo do qual a solicitação de registro provém. Consulte a [tabela de dispositivos no Skype for Business Server 2015](devices.md) para obter mais informações. <br/> |
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Exterior  <br/> |O motivo do cancelamento de registro, como ' iniciado pelo usuário ', ' registro expirado ', ' falha do cliente ' e muito mais. Consulte a [tabela Canregistertype no Skype for Business Server 2015](deregistertype.md) para obter mais informações. <br/> |
|**IPAddress** <br/> |nvarchar(256)  <br/> ||Endereço IP do ponto de extremidade ao qual o usuário se cadastrou. Pode ser um endereço IPv4 ou um endereço IPv6.  <br/> Este campo foi apresentado no Microsoft Lync Server 2013.  <br/> |
|**LastModifiedtime** <br/> |DateTime  <br/> ||Para uso interno pelo serviço de monitoramento.  <br/> Este campo foi apresentado no Skype for Business Server 2015.  <br/> |
   

