---
title: Exibição McuJoinsAndLeaves
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
description: A exibição McuJoinsAndLeaves armazena informações sobre ingresso e saída de usuários de um servidor de conferências. Cada registro nessa exibição inclui os detalhes da chamada sobre uma combinação da entrada ou saída de um usuário e o servidor de conferência. Essa exibição foi introduzida no Microsoft Lync Server 2013.
---

# <a name="mcujoinsandleaves-view"></a>Exibição McuJoinsAndLeaves
 
A exibição McuJoinsAndLeaves armazena informações sobre ingresso e saída de usuários de um servidor de conferências. Cada registro nessa exibição inclui os detalhes da chamada sobre uma combinação da entrada ou saída de um usuário e o servidor de conferência. Essa exibição foi introduzida no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Hora da instância da conferência. Usada em conjunto com SessionIdSeq para identificar uma instância da conferência de maneira exclusiva. Consulte a [tabela Conferências no Skype for Business Server 2015](conferences.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Número de ID para identificar a instância da conferência. Usada em conjunto com SessionIdTime para identificar uma instância da conferência de maneira exclusiva. Consulte a [tabela Conferências no Skype for Business Server 2015](conferences.md) para obter mais informações. <br/> |
|**McuUri** <br/> |nvarchar(256)  <br/> |URI do servidor de conferências ao qual o usuário está conectado.  <br/> |
|**McuUriType** <br/> |nvarchar(256)  <br/> |URI do servidor de conferências ao qual o usuário está conectado. Consulte a [tabela UriTypes para](uritypes.md) obter mais informações. <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |URI do usuário cujas informações de ingresso/saída do servidor de conferências foram capturadas.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI do usuário cujas informações de ingresso/saída do servidor de conferências foram capturadas. Consulte a [tabela UriTypes para](uritypes.md) obter mais informações. <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Locatário do usuário cujas informações de ingresso/saída do servidor de conferências foram capturadas. Consulte a [tabela Locatários](tenants.md) para obter mais informações. <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |Versão do cliente usado pelo usuário cujas informações de ingresso/saída do servidor de conferências foram capturadas.  <br/> |
|**UserClientType** <br/> |int  <br/> |Cliente usado pelo usuário cujas informações de ingresso/saída do servidor de conferências foram capturadas. Consulte a [tabela UserAgentDef](useragentdef.md) para obter mais detalhes. <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |Nome da categoria do cliente usado pelo usuário cujas informações de ingresso/saída do servidor de conferências foram capturadas.  <br/> |
|**McuUserInstance** <br/> |int  <br/> |Identificador exclusivo da combinação de usuário/dispositivo para usuários que fizeram logon simultâneo em vários dispositivos.  <br/> |
|**IsUserFromPstn** <br/> |bit  <br/> |Bit que representa se o usuário é interno ou não.  <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Hora da solicitação da sessão. Utilizada em conjunto com o SessionIdSeq para identificar de forma exclusiva uma sessão. Consulte a [tabela Dialogs no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Número de identificação para identificar a sessão. Utilizado em conjunto com o SessionIdTime para identificar de forma exclusiva uma sessão. Consulte a [tabela Dialogs no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**DialogId** <br/> |varchar(775)  <br/> |ID de diálogo SIP da sessão. O formato é: diálogo;de-marca;para-marca.  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> |Hora em que o usuário ingressou no servidor de conferências.  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> |Hora em que o usuário saiu do servidor de conferências.  <br/> |
   

