---
title: Alterações feitas por Grant-CsOUPermission no Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
description: Para delegar Skype for Business Server administração, você pode adicionar permissões a unidades organizacionais especificadas (OUs) para que os membros dos grupos universais RTC criados pela preparação da floresta possam acessar as OUs sem serem membros do grupo Administradores de Domínio.
ms.openlocfilehash: c8b7841fc6754c5f852945807a68089c922f6497
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60838463"
---
# <a name="changes-made-by-grant-csoupermission-in-skype-for-business-server"></a>Alterações feitas por Grant-CsOUPermission no Skype for Business Server
 
Para delegar Skype for Business Server administração, você pode adicionar permissões a unidades organizacionais especificadas (OUs) para que os membros dos grupos universais RTC criados pela preparação da floresta possam acessar as OUs sem serem membros do grupo Administradores de Domínio. 
  
O cmdlet **Grant-CsOuPermission** concede permissões para objetos no OU especificado conforme mostrado nas tabelas a seguir.
  
## <a name="granting-permission-for-user-objects"></a>Concedendo permissões para objetos do usuário

Ao executar o cmdlet **Grant-CsOuPermission** para objetos do Usuário em um OU, os grupos são concedidos com permissões exibidas na tabela a seguir.
  
**Permissões concedidas para objetos do usuário**

|**Grupo**|**Permissão**|**Aplica-se a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replicando mudanças de diretório  <br/> |Apenas este objeto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Conteúdo da lista  <br/> Ler todas as propriedades  <br/> Permissões de leitura  <br/> |Apenas este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Conteúdo da lista  <br/> Ler todas as propriedades  <br/> Permissões de leitura  <br/> |Apenas este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Ler RTCUserSearchPropertySet  <br/> Ler RTCUserProvisioningPropertySet  <br/> Ler RTCPropertySet  <br/> Ler Public-Information  <br/> Ler General-Information  <br/> Ler User-Account-Restrictions  <br/> |Objetos do usuário descendente  <br/> |
|RTCUniversalUserAdmins  <br/> |Gravara RTCUserSearchPropertySet  <br/> Gravar msExchUCVoiceMailSettings  <br/> Gravar RTCUserProvisioningPropertySet  <br/> Gravar RTCPropertySet  <br/> Gravar proxyAddresses  <br/> |Objetos do usuário descendente  <br/> |
   
## <a name="granting-permission-for-computer-objects"></a>Conceder permissões para objetos do computador

Ao executar o cmdlet **Grant-CsOuPermission** para objetos de computador em um OU, os grupos são concedidos com as permissões mostradas na tabela a seguir.
  
**Permissões concedidas para objetos do computador**

|**Grupo**|**Permissão**|**Aplica-se a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replicando mudanças de diretório  <br/> |Apenas este objeto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Conteúdo da lista  <br/> Ler todas as propriedades  <br/> Permissões de leitura  <br/> |Apenas este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Conteúdo da lista  <br/> Ler todas as propriedades  <br/> Permissões de leitura  <br/> |Apenas este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Ler Public-Information  <br/> Ler Validated-DNS-Host-Name  <br/> |Objetos do computador descendente  <br/> |
|RTCUniversalUserAdmins  <br/> |Ler Public-Information  <br/> Ler Validated-DNS-Host-Name  <br/> |Objetos do computador descendente  <br/> |
   
## <a name="granting-permission-for-contact-or-appcontact-objects"></a>Concedendo permissões para contato ou objetos AppContact

Ao executar o cmdlet **Grant-CsOuPermission** para objetos de Contato ou AppContact em um OU, os grupos são concedidos com permissões conforme mostrado na tabela a seguir.
  
**Permissões concedidas para os objetos Contato ou AppContact**

|**Grupo**|**Permissão**|**Aplica-se a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replicando mudanças de diretório  <br/> |Apenas este objeto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Conteúdo da lista  <br/> Ler todas as propriedades  <br/> Permissões de leitura  <br/> |Apenas este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Conteúdo da lista  <br/> Ler todas as propriedades  <br/> Permissões de leitura  <br/> |Apenas este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Ler RTCUserSearchPropertySet  <br/> Ler RTCUserProvisioningPropertySet  <br/> Ler RTCPropertySet  <br/> Ler Public-Information  <br/> Ler General-Information  <br/> Ler Personal-Information  <br/> Ler User-Account-Restrictions  <br/> |Objetos de contato descendente  <br/> |
|RTCUniversalUserAdmins  <br/> |Gravar RTCUserSearchPropertySet  <br/> Gravar otherIpPhone  <br/> Gravar displayName  <br/> Descrição de gravação  <br/> Gravar telephoneNumber  <br/> Gravar msExchUCVoiceMailSettings  <br/> Gravar RTCUserProvisioningPropertySet  <br/> Gravar RTCPropertySet  <br/> Gravar proxyAddresses  <br/> |Objetos de contato descendente  <br/> |
   
## <a name="granting-permission-for-device-objects"></a>Concedendo permissões para objetos de dispositivo

Ao executar o cmdlet **Grant-CsOuPermission** para objetos de Dispositivo em um OU, os grupos são concedidos com permissões conforme mostrado na tabela a seguir.
  
**Permissões concedidos para objetos de Dispositivo**

|**Grupo**|**Permissão**|**Aplica-se a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replicando mudanças de diretório  <br/> |Apenas este objeto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Conteúdo da lista  <br/> Ler todas as propriedades  <br/> Permissões de leitura  <br/> |Apenas este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Conteúdo da lista  <br/> Ler todas as propriedades  <br/> Permissões de leitura  <br/> |Apenas este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Ler RTCUserSearchPropertySet  <br/> Ler RTCUserProvisioningPropertySet  <br/> Ler RTCPropertySet  <br/> Ler Public-Information  <br/> Ler Personal-Information  <br/> Ler General-Information  <br/> Ler User-Account-Restrictions  <br/> |Objetos de contato descendente  <br/> |
|RTCUniversalUserAdmins  <br/> |Criar filho  <br/> Excluir filho  <br/> Excluir árvore  <br/> |Contact  <br/> |
|RTCUniversalUserAdmins  <br/> |Gravar displayName  <br/> Descrição de gravação  <br/> Gravar telephoneNumber  <br/> |Objetos do usuário descendente  <br/> |
|RTCUniversalUserAdmins  <br/> |Gravar RTCUserSearchPropertySet  <br/> Gravar otherIpPhone  <br/> Gravar displayName  <br/> Descrição de gravação  <br/> Gravar telephoneNumber  <br/> Gravar msExchUCVoiceMailSettings  <br/> Gravar RTCUserProvisioningPropertySet  <br/> Gravar RTCPropertySet  <br/> Gravar proxyAddresses  <br/> |Objetos de contato descendente  <br/> |
   
## <a name="granting-permission-for-inetorgperson-objects"></a>Concedendo permissões para objetos InetOrgPerson

Ao executar o cmdlet **Grant-CsOuPermission** para objetos InetOrgPerson em um OU, os grupos são concedidos com permissões conforme mostrado na tabela a seguir.
  
**Permissões concedidas para objetos InetOrgPerson**

|**Grupo**|**Permissão**|**Aplica-se a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replicando mudanças de diretório  <br/> |Apenas este objeto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Conteúdo da lista  <br/> Ler todas as propriedades  <br/> Permissões de leitura  <br/> |Apenas este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Conteúdo da lista  <br/> Ler todas as propriedades  <br/> Permissões de leitura  <br/> |Apenas este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Ler RTCUserSearchPropertySet  <br/> Ler RTCUserProvisioningPropertySet  <br/> Ler RTCPropertySet  <br/> Ler Personal-Information  <br/> Ler Public-Information  <br/> Ler General-Information  <br/> Ler User-Account-Restrictions  <br/> |Objetos inetOrgPerson descendentes  <br/> |
|RTCUniversalUserAdmins  <br/> |Gravar RTCUserSearchPropertySet  <br/> Gravar RTCUserProvisioningPropertySet  <br/> Gravar RTCPropertySet  <br/> Gravar proxyAddresses  <br/> |Objetos inetOrgPerson descendentes  <br/> |
   

