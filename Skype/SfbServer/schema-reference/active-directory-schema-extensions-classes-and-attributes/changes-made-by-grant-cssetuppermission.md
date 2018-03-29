---
title: Alterações feitas por Grant-CsSetupPermission no Skype para Business Server
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
description: Para delegar a instalação, você pode conceder permissões ao grupo RTCUniversalServerAdmins universal um específicos do Active Directory na unidade organizacional (UO), permitindo que os membros do grupo RTCUniversalServerAdmins nessa UO para instalar o Skype para Business Server na domínio especificado sem que sejam membros do grupo Administradores de domínio.
ms.openlocfilehash: 6c87ad11e0c125f2a58f2518218060b2a3636f0e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="changes-made-by-grant-cssetuppermission-in-skype-for-business-server"></a>Alterações feitas por Grant-CsSetupPermission no Skype para Business Server
 
Para delegar a instalação, você pode conceder permissões ao grupo RTCUniversalServerAdmins universal um específicos do Active Directory na unidade organizacional (UO), permitindo que os membros do grupo RTCUniversalServerAdmins nessa UO para instalar o Skype para Business Server na domínio especificado sem que sejam membros do grupo Administradores de domínio. 
  
O cmdlet **Grant-CsSetupPermission** concede permissões do grupo RTCUniversalServerAdmins em uma unidade Organizacional, conforme especificado na tabela a seguir:
  
**Permissões concedidas para objetos na unidade Organizacional**

|**Permissões se aplicam a:**|**Permissões concedidas são:**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> | Acesso especial: <br/>  Ler servicePrincipalName <br/>  Gravar servicePrincipalName <br/>  Excluir árvore <br/>  Replicando mudanças de diretório <br/> |
|Objetos do serviceConnectionPoint descendente  <br/> | Acesso especial: <br/>  Permissões de leitura <br/>  Permissões de gravação <br/>  Criar filho <br/>  Excluir filho <br/>  Listar conteúdo <br/>  Propriedade de gravação <br/>  Ler propriedade <br/>  Excluir árvore <br/> |
|Objetos msRTCSIP-Server descendentes  <br/> | Acesso especial: <br/>  Propriedade de gravação <br/>  Ler propriedade <br/>  Excluir árvore <br/> |
|Objetos msRTCSIP-WebComponents descendentes  <br/> | Acesso especial: <br/>  Propriedade de gravação <br/>  Ler propriedade <br/>  Excluir árvore <br/> |
|Objetos msRTCSIP-MCU descendentes  <br/> | Acesso especial: <br/>  Propriedade de gravação <br/>  Ler propriedade <br/>  Excluir árvore <br/> |
|Objetos msRTCSIP-MediationServer descendentes  <br/> | Acesso especial: <br/>  Propriedade de gravação <br/>  Ler propriedade <br/>  Excluir árvore <br/> |
|Objetos msRTCSIP-ApplicationServer descendentes  <br/> | Acesso especial: <br/>  Propriedade de gravação <br/>  Ler propriedade <br/>  Excluir árvore <br/> |
|Objetos msRTCSIP-ConnectionPoint descendentes  <br/> | Acesso especial: <br/>  Propriedade de gravação <br/>  Ler propriedade <br/>  Excluir árvore <br/> |
|Objetos de computador descendente  <br/> | Acesso especial para serviceConnectionPoint: <br/>  Criar objetos filhos <br/>  Excluir objetos filhos <br/>  Excluir árvore <br/>  Acesso especial para informação pública: <br/>  Ler propriedade <br/>  Acesso especial para nome de host DNS: <br/>  Ler propriedade <br/> |
   

