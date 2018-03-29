---
title: Alterações feitas por Grant-CsOUPermission no Skype para Business Server
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
description: Para delegar Skype para a administração do Business Server, você pode adicionar permissões para especificado OUs (unidades organizacionais) para que membros dos grupos universais RTC criados pela preparação de floresta possam acessar as OUs sem que sejam membros do grupo Administradores de domínio.
ms.openlocfilehash: 1313394248da2dcaeb9843bd689b2e2da3c51f96
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="changes-made-by-grant-csoupermission-in-skype-for-business-server"></a>Alterações feitas por Grant-CsOUPermission no Skype para Business Server
 
Para delegar Skype para a administração do Business Server, você pode adicionar permissões para especificado OUs (unidades organizacionais) para que membros dos grupos universais RTC criados pela preparação de floresta possam acessar as OUs sem que sejam membros do grupo Administradores de domínio. 
  
O cmdlet **Grant-CsOuPermission** concede permissões para objetos no OU especificado conforme especificado nas tabelas a seguir.
  
## <a name="granting-permission-for-user-objects"></a>Concedendo permissões para objetos de usuário

Quando você executa o cmdlet **Grant-CsOuPermission** para objetos do usuário em uma unidade Organizacional, grupos são concedidos com permissões conforme mostrado na tabela a seguir.
  
**Permissões concedidas para objetos de usuário**

|**Grupo**|**Permissão**|**Aplica-se a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replicando mudanças de diretório  <br/> |Apenas este objeto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Listar conteúdo  <br/> Ler todas as propriedades  <br/> Permissões de leitura  <br/> |Apenas este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Listar conteúdo  <br/> Ler todas as propriedades  <br/> Permissões de leitura  <br/> |Apenas este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Ler RTCUserSearchPropertySet  <br/> Ler RTCUserProvisioningPropertySet  <br/> Ler RTCPropertySet  <br/> Ler Public-Information  <br/> Ler General-Information  <br/> Leia as restrições de conta de usuário  <br/> |Objetos do usuário descendente  <br/> |
|RTCUniversalUserAdmins  <br/> |Gravar RTCUserSearchPropertySet  <br/> Gravar msExchUCVoiceMailSettings  <br/> Gravar RTCUserProvisioningPropertySet  <br/> Gravar RTCPropertySet  <br/> Gravar proxyAddresses  <br/> |Objetos do usuário descendente  <br/> |
   
## <a name="granting-permission-for-computer-objects"></a>Concedendo permissões para objetos de computador

Quando você executa o cmdlet **Grant-CsOuPermission** para objetos de computador em uma unidade Organizacional, grupos são concedidos com permissões conforme mostrado na tabela a seguir.
  
**Permissões concedidas para objetos de computador**

|**Grupo**|**Permissão**|**Aplica-se a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replicando mudanças de diretório  <br/> |Apenas este objeto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Listar conteúdo  <br/> Ler todas as propriedades  <br/> Permissões de leitura  <br/> |Apenas este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Listar conteúdo  <br/> Ler todas as propriedades  <br/> Permissões de leitura  <br/> |Apenas este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Ler Public-Information  <br/> Leitura validado---nome do Host DNS  <br/> |Objetos de computador descendente  <br/> |
|RTCUniversalUserAdmins  <br/> |Ler Public-Information  <br/> Leitura validado---nome do Host DNS  <br/> |Objetos de computador descendente  <br/> |
   
## <a name="granting-permission-for-contact-or-appcontact-objects"></a>Concedendo permissões para objetos contato ou AppContact

Quando você executa o cmdlet **Grant-CsOuPermission** para objetos de contato ou appcontact em uma unidade Organizacional, grupos são concedidos com permissões conforme mostrado na tabela a seguir.
  
**Permissões concedidas para objetos contato ou AppContact**

|**Grupo**|**Permissão**|**Aplica-se a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replicando mudanças de diretório  <br/> |Apenas este objeto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Listar conteúdo  <br/> Ler todas as propriedades  <br/> Permissões de leitura  <br/> |Apenas este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Listar conteúdo  <br/> Ler todas as propriedades  <br/> Permissões de leitura  <br/> |Apenas este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Ler RTCUserSearchPropertySet  <br/> Ler RTCUserProvisioningPropertySet  <br/> Ler RTCPropertySet  <br/> Ler Public-Information  <br/> Ler General-Information  <br/> Ler Personal-Information  <br/> Leia as restrições de conta de usuário  <br/> |Objetos de contato descendente  <br/> |
|RTCUniversalUserAdmins  <br/> |Gravar RTCUserSearchPropertySet  <br/> Gravar otherIpPhone  <br/> Gravar displayName  <br/> Descrição de gravação  <br/> Gravar telephoneNumber  <br/> Gravar msExchUCVoiceMailSettings  <br/> Gravar RTCUserProvisioningPropertySet  <br/> Gravar RTCPropertySet  <br/> Gravar proxyAddresses  <br/> |Objetos de contato descendente  <br/> |
   
## <a name="granting-permission-for-device-objects"></a>Concedendo permissões para objetos de dispositivo

Quando você executa o cmdlet **Grant-CsOuPermission** para objetos de dispositivo em uma unidade Organizacional, grupos são concedidos com permissões conforme mostrado na tabela a seguir.
  
**Permissões concedidas para objetos de dispositivo**

|**Grupo**|**Permissão**|**Aplica-se a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replicando mudanças de diretório  <br/> |Apenas este objeto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Listar conteúdo  <br/> Ler todas as propriedades  <br/> Permissões de leitura  <br/> |Apenas este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Listar conteúdo  <br/> Ler todas as propriedades  <br/> Permissões de leitura  <br/> |Apenas este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Ler RTCUserSearchPropertySet  <br/> Ler RTCUserProvisioningPropertySet  <br/> Ler RTCPropertySet  <br/> Ler Public-Information  <br/> Ler Personal-Information  <br/> Ler General-Information  <br/> Leia as restrições de conta de usuário  <br/> |Objetos de contato descendente  <br/> |
|RTCUniversalUserAdmins  <br/> |Criar filho  <br/> Excluir filho  <br/> Excluir árvore  <br/> |Contato  <br/> |
|RTCUniversalUserAdmins  <br/> |Gravar displayName  <br/> Descrição de gravação  <br/> Gravar telephoneNumber  <br/> |Objetos do usuário descendente  <br/> |
|RTCUniversalUserAdmins  <br/> |Gravar RTCUserSearchPropertySet  <br/> Gravar otherIpPhone  <br/> Gravar displayName  <br/> Descrição de gravação  <br/> Gravar telephoneNumber  <br/> Gravar msExchUCVoiceMailSettings  <br/> Gravar RTCUserProvisioningPropertySet  <br/> Gravar RTCPropertySet  <br/> Gravar proxyAddresses  <br/> |Objetos de contato descendente  <br/> |
   
## <a name="granting-permission-for-inetorgperson-objects"></a>Concedendo permissões para objetos InetOrgPerson

Quando você executa o cmdlet **Grant-CsOuPermission** para objetos InetOrgPerson em uma unidade Organizacional, grupos são concedidos com permissões conforme mostrado na tabela a seguir.
  
**Permissões concedidas para objetos InetOrgPerson**

|**Grupo**|**Permissão**|**Aplica-se a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replicando mudanças de diretório  <br/> |Apenas este objeto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Listar conteúdo  <br/> Ler todas as propriedades  <br/> Permissões de leitura  <br/> |Apenas este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Listar conteúdo  <br/> Ler todas as propriedades  <br/> Permissões de leitura  <br/> |Apenas este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Ler RTCUserSearchPropertySet  <br/> Ler RTCUserProvisioningPropertySet  <br/> Ler RTCPropertySet  <br/> Ler Personal-Information  <br/> Ler Public-Information  <br/> Ler General-Information  <br/> Leia as restrições de conta de usuário  <br/> |Objetos inetOrgPerson descendentes  <br/> |
|RTCUniversalUserAdmins  <br/> |Gravar RTCUserSearchPropertySet  <br/> Gravar RTCUserProvisioningPropertySet  <br/> Gravar RTCPropertySet  <br/> Gravar proxyAddresses  <br/> |Objetos inetOrgPerson descendentes  <br/> |
   

