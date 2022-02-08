---
title: Tabela de registro
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
description: Cada registro representa um evento de registro de usuário.
ms.openlocfilehash: df06364cc466d40ec571328089a7fab5d4970761
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394883"
---
# <a name="registration-table"></a>Tabela de registro
 
Cada registro representa um evento de registro de usuário.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primário, Estrangeiro  <br/> |Tempo da solicitação de sessão. Usado em conjunto com **SessionIdSeq** para identificar exclusivamente uma sessão. Consulte a [tabela Dialogs no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primário, Estrangeiro  <br/> |O número de ID para identificar a sessão. Usado em conjunto com **SessionIdTime** para identificar exclusivamente uma sessão. Consulte a [tabela Dialogs no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**UserId** <br/> |int  <br/> |Foreign  <br/> |A ID do usuário. Consulte a [tabela Usuários para](users.md) obter mais informações. <br/> |
|**EndpointId** <br/> |uniqueidentifier  <br/> ||Um GUID para identificar um ponto de extremidade de registro. Geralmente, o evento de registro do mesmo computador do mesmo usuário terá a mesma ID de ponto de extremidade. Máquinas diferentes possuem uma ID de ponto de extremidade diferente.  <br/> |
|**EndpointEra** <br/> |uniqueIdentifier  <br/> ||ID usado para diferenciar registros que envolvem o mesmo usuário e o mesmo ponto de extremidade.  <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
|**ClientVersionId** <br/> |int  <br/> |Foreign  <br/> |Versão do cliente do usuário atual. Consulte a [tabela ClientVersions no Skype for Business Server 2015](clientversions.md) para obter mais informações. <br/> |
|**RegistrarId** <br/> |int  <br/> |Foreign  <br/> |ID do Servidor Registrador usado para registro. Consulte a [tabela Servidores para](servers.md) obter mais informações. <br/> |
|**PoolId** <br/> |int  <br/> |Foreign  <br/> |A ID do pool no qual a sessão foi capturada. Consulte a [tabela Pools para](pools.md) obter mais informações. <br/> |
|**EdgeServerId** <br/> |int  <br/> |Foreign  <br/> |Servidor de Borda pelo qual o registro está passando. Consulte a [tabela EdgeServers no Skype for Business Server 2015](edgeservers.md) para obter mais informações. <br/> |
|**IsInternal** <br/> |Bit  <br/> ||Quer o usuário esteja conectado internamente ou não.  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> ||Quer o UserService esteja disponível ou não.  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> ||Quer registre-se no primeiro Registrador ou não.  <br/> |
|**IsPrimaryRegistrarCentral** <br/> |bit  <br/> ||Indica se o usuário é registrado com um Aparelho de Filial Persistente.  <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
|**RegisterTime** <br/> |datetime  <br/> ||Período de registro.  <br/> |
|**DeRegisterTime** <br/> |datetime  <br/> ||Período de cancelamento de registro.  <br/> |
|**ResponseCode** <br/> |int  <br/> ||Código de resposta da solicitação de registro.  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||ID do diagnóstico da solicitação de registro, que indica o tipo de informação de diagnóstico.  <br/> |
|**DeviceId** <br/> |int  <br/> |Foreign  <br/> |O dispositivo do qual a solicitação de registro está vindo. Consulte a [tabela Dispositivos no Skype for Business Server 2015](devices.md) para obter mais informações. <br/> |
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Foreign  <br/> |O motivo do descadastramento, como "iniciado pelo usuário", "registro expirado", "falha do cliente" e muito mais. Consulte a [tabela DeRegisterType no Skype for Business Server 2015](deregistertype.md) para obter mais informações. <br/> |
|**IPAddress** <br/> |nvarchar(256)  <br/> ||Iendereço de IP address do ponto da extremidade que o usuário é registrado. Pode ser um endereço IPv4 ou IPv6 address.  <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Para uso interno pelo serviço de Monitoramento.  <br/> Este campo foi introduzido no Skype for Business Server 2015.  <br/> |
   

