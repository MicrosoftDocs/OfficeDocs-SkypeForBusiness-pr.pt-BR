---
title: Alterações feitas pelo Grant-CsOUPermission no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
description: Para delegar a administração do Skype for Business Server, você pode adicionar permissões a unidades organizacionais (UOs) especificadas para que os membros dos grupos universais do RTC criados pela preparação da floresta possam acessar as UOs sem serem membros do grupo Domain admins.
ms.openlocfilehash: 48c5921cabf2b1bc8100f796d3e3b7f6a247ff0c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296690"
---
# <a name="changes-made-by-grant-csoupermission-in-skype-for-business-server"></a>Alterações feitas pelo Grant-CsOUPermission no Skype for Business Server
 
Para delegar a administração do Skype for Business Server, você pode adicionar permissões a unidades organizacionais (UOs) especificadas para que os membros dos grupos universais do RTC criados pela preparação da floresta possam acessar as UOs sem serem membros do grupo Domain admins. 
  
O cmdlet **Grant-CsOuPermission** concede permissões a objetos na unidade organizacional especificada, conforme especificado nas tabelas a seguir.
  
## <a name="granting-permission-for-user-objects"></a>Concedendo permissão para objetos de usuário

Quando você executa o cmdlet **Grant-CsOuPermission** para objetos de usuário em uma ou, os grupos recebem permissões para os grupos, conforme mostrado na tabela a seguir.
  
**Permissões concedidas para objetos de usuário**

|**Grupos**|**Permissão**|**Aplica-se a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replicando alterações de diretório  <br/> |Somente este objeto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Conteúdo da lista  <br/> Ler todas as propriedades  <br/> Permissões de leitura  <br/> |Somente este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Conteúdo da lista  <br/> Ler todas as propriedades  <br/> Permissões de leitura  <br/> |Somente este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Ler RTCUserSearchPropertySet  <br/> Ler RTCUserProvisioningPropertySet  <br/> Ler RTCPropertySet  <br/> Ler informações públicas  <br/> Leia informações gerais  <br/> Ler restrições de conta de usuário  <br/> |Objetos de usuário descendentes  <br/> |
|RTCUniversalUserAdmins  <br/> |Escrever RTCUserSearchPropertySet  <br/> Escrever msExchUCVoiceMailSettings  <br/> Escrever RTCUserProvisioningPropertySet  <br/> Escrever RTCPropertySet  <br/> Escrever proxyAddresses  <br/> |Objetos de usuário descendentes  <br/> |
   
## <a name="granting-permission-for-computer-objects"></a>Concedendo permissão para objetos de computador

Quando você executa o cmdlet **Grant-CsOuPermission** para objetos de computador em uma ou, os grupos recebem permissões para os grupos, conforme mostrado na tabela a seguir.
  
**Permissões concedidas para objetos de computador**

|**Grupos**|**Permissão**|**Aplica-se a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replicando alterações de diretório  <br/> |Somente este objeto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Conteúdo da lista  <br/> Ler todas as propriedades  <br/> Permissões de leitura  <br/> |Somente este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Conteúdo da lista  <br/> Ler todas as propriedades  <br/> Permissões de leitura  <br/> |Somente este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Ler informações públicas  <br/> Leitura validada-DNS-nome do host  <br/> |Objetos de computador descendentes  <br/> |
|RTCUniversalUserAdmins  <br/> |Ler informações públicas  <br/> Leitura validada-DNS-nome do host  <br/> |Objetos de computador descendentes  <br/> |
   
## <a name="granting-permission-for-contact-or-appcontact-objects"></a>Concedendo permissão para objetos de contato ou AppContact

Quando você executa o cmdlet **Grant-CsOuPermission** para objetos de contato ou objetos AppContact em uma ou, os grupos recebem permissões como mostrado na tabela a seguir.
  
**Permissões concedidas para objetos de contato ou AppContact**

|**Grupos**|**Permissão**|**Aplica-se a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replicando alterações de diretório  <br/> |Somente este objeto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Conteúdo da lista  <br/> Ler todas as propriedades  <br/> Permissões de leitura  <br/> |Somente este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Conteúdo da lista  <br/> Ler todas as propriedades  <br/> Permissões de leitura  <br/> |Somente este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Ler RTCUserSearchPropertySet  <br/> Ler RTCUserProvisioningPropertySet  <br/> Ler RTCPropertySet  <br/> Ler informações públicas  <br/> Leia informações gerais  <br/> Leia as informações pessoais  <br/> Ler restrições de conta de usuário  <br/> |Objetos de contato descendentes  <br/> |
|RTCUniversalUserAdmins  <br/> |Escrever RTCUserSearchPropertySet  <br/> Escrever otherIpPhone  <br/> Escrever displayName  <br/> Descrição da gravação  <br/> Escrever telephoneNumber  <br/> Escrever msExchUCVoiceMailSettings  <br/> Escrever RTCUserProvisioningPropertySet  <br/> Escrever RTCPropertySet  <br/> Escrever proxyAddresses  <br/> |Objetos de contato descendentes  <br/> |
   
## <a name="granting-permission-for-device-objects"></a>Concedendo permissão para objetos de dispositivo

Quando você executa o cmdlet **Grant-CsOuPermission** para objetos de dispositivo em uma ou, os grupos recebem permissões como mostrado na tabela a seguir.
  
**Permissões concedidas para objetos de dispositivo**

|**Grupos**|**Permissão**|**Aplica-se a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replicando alterações de diretório  <br/> |Somente este objeto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Conteúdo da lista  <br/> Ler todas as propriedades  <br/> Permissões de leitura  <br/> |Somente este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Conteúdo da lista  <br/> Ler todas as propriedades  <br/> Permissões de leitura  <br/> |Somente este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Ler RTCUserSearchPropertySet  <br/> Ler RTCUserProvisioningPropertySet  <br/> Ler RTCPropertySet  <br/> Ler informações públicas  <br/> Leia as informações pessoais  <br/> Leia informações gerais  <br/> Ler restrições de conta de usuário  <br/> |Objetos de contato descendentes  <br/> |
|RTCUniversalUserAdmins  <br/> |Criar filho  <br/> Excluir filho  <br/> Excluir árvore  <br/> |Entrando  <br/> |
|RTCUniversalUserAdmins  <br/> |Escrever displayName  <br/> Descrição da gravação  <br/> Escrever telephoneNumber  <br/> |Objetos de usuário descendentes  <br/> |
|RTCUniversalUserAdmins  <br/> |Escrever RTCUserSearchPropertySet  <br/> Escrever otherIpPhone  <br/> Escrever displayName  <br/> Descrição da gravação  <br/> Escrever telephoneNumber  <br/> Escrever msExchUCVoiceMailSettings  <br/> Escrever RTCUserProvisioningPropertySet  <br/> Escrever RTCPropertySet  <br/> Escrever proxyAddresses  <br/> |Objetos de contato descendentes  <br/> |
   
## <a name="granting-permission-for-inetorgperson-objects"></a>Concedendo permissão para objetos InetOrgPerson

Quando você executa o cmdlet **Grant-CsOuPermission** para objetos inetOrgPerson em uma ou, os grupos recebem permissões como mostrado na tabela a seguir.
  
**Permissões concedidas para objetos InetOrgPerson**

|**Grupos**|**Permissão**|**Aplica-se a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replicando alterações de diretório  <br/> |Somente este objeto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Conteúdo da lista  <br/> Ler todas as propriedades  <br/> Permissões de leitura  <br/> |Somente este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Conteúdo da lista  <br/> Ler todas as propriedades  <br/> Permissões de leitura  <br/> |Somente este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Ler RTCUserSearchPropertySet  <br/> Ler RTCUserProvisioningPropertySet  <br/> Ler RTCPropertySet  <br/> Leia as informações pessoais  <br/> Ler informações públicas  <br/> Leia informações gerais  <br/> Ler restrições de conta de usuário  <br/> |Objetos inetOrgPerson descendentes  <br/> |
|RTCUniversalUserAdmins  <br/> |Escrever RTCUserSearchPropertySet  <br/> Escrever RTCUserProvisioningPropertySet  <br/> Escrever RTCPropertySet  <br/> Escrever proxyAddresses  <br/> |Objetos inetOrgPerson descendentes  <br/> |
   

