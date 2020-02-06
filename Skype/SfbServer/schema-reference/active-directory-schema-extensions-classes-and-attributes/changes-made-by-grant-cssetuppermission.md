---
title: Alterações feitas pelo Grant-CsSetupPermission no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
description: Para delegar a instalação, você pode conceder permissões ao grupo universal RTCUniversalServerAdmins para uma unidade organizacional (OU) específica do Active Directory, permitindo que os membros do grupo RTCUniversalServerAdmins dessa UO instalem o Skype for Business Server na domínio especificado sem ser membro do grupo Domain admins.
ms.openlocfilehash: 844cfa586523750b804564482146c0e76b39fc38
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815509"
---
# <a name="changes-made-by-grant-cssetuppermission-in-skype-for-business-server"></a>Alterações feitas pelo Grant-CsSetupPermission no Skype for Business Server
 
Para delegar a instalação, você pode conceder permissões ao grupo universal RTCUniversalServerAdmins para uma unidade organizacional (OU) específica do Active Directory, permitindo que os membros do grupo RTCUniversalServerAdmins dessa UO instalem o Skype for Business Server na domínio especificado sem ser membro do grupo Domain admins. 
  
O cmdlet **Grant-CsSetupPermission** concede as permissões do grupo RTCUniversalServerAdmins em uma UO, conforme especificado na tabela a seguir:
  
**Permissões concedidas a objetos na OU**

|**As permissões se aplicam a:**|**Permissões concedidas são:**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> | Acesso especial: <br/>  Leia servicePrincipalName <br/>  Gravar servicePrincipalName <br/>  Excluir árvore <br/>  Replicando alterações de diretório <br/> |
|Objetos serviceConnectionPoint do descendant  <br/> | Acesso especial: <br/>  Permissões de leitura <br/>  Permissões de gravação <br/>  Criar filho <br/>  Excluir filho <br/>  Conteúdo da lista <br/>  Propriedade de gravação <br/>  Propriedade ler <br/>  Excluir árvore <br/> |
|Objetos msRTCSIP-Server descendentes  <br/> | Acesso especial: <br/>  Propriedade de gravação <br/>  Propriedade ler <br/>  Excluir árvore <br/> |
|Objetos msRTCSIP descendentes-WebComponents  <br/> | Acesso especial: <br/>  Propriedade de gravação <br/>  Propriedade ler <br/>  Excluir árvore <br/> |
|Objetos descendentes msRTCSIP-MCU  <br/> | Acesso especial: <br/>  Propriedade de gravação <br/>  Propriedade ler <br/>  Excluir árvore <br/> |
|Objetos msRTCSIP-MediationServer descendentes  <br/> | Acesso especial: <br/>  Propriedade de gravação <br/>  Propriedade ler <br/>  Excluir árvore <br/> |
|Objetos msRTCSIP-ApplicationServer descendentes  <br/> | Acesso especial: <br/>  Propriedade de gravação <br/>  Propriedade ler <br/>  Excluir árvore <br/> |
|Objetos descendentes msRTCSIP-ConnectionPoint  <br/> | Acesso especial: <br/>  Propriedade de gravação <br/>  Propriedade ler <br/>  Excluir árvore <br/> |
|Objetos de computador descendentes  <br/> | Acesso especial para serviceConnectionPoint: <br/>  Criar objetos filho <br/>  Excluir objetos filho <br/>  Excluir árvore <br/>  Acesso especial para informações públicas: <br/>  Propriedade ler <br/>  Acesso especial para o nome do host DNS: <br/>  Propriedade ler <br/> |
   

