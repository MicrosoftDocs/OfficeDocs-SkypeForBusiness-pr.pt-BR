---
title: Alterações feitas por Grant-CsSetupPermission no Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
description: 'Para delegar a instalação, você pode conceder permissões ao grupo universal RTCUniversalServerAdmins para uma unidade organizacional (OU) específica do Active Directory, permitindo que os membros do grupo RTCUniversalServerAdmins nessa UO instalem o Skype for Business Server no domínio especificado sem serem membros do grupo Administradores de Domínio.'
---

# <a name="changes-made-by-grant-cssetuppermission-in-skype-for-business-server"></a>Alterações feitas por Grant-CsSetupPermission no Skype for Business Server
 
Para delegar a instalação, você pode conceder permissões ao grupo universal RTCUniversalServerAdmins para uma unidade organizacional (OU) específica do Active Directory, permitindo que os membros do grupo RTCUniversalServerAdmins nessa UO instalem o Skype for Business Server no domínio especificado sem serem membros do grupo Administradores de Domínio. 
  
O cmdlet **Grant-CsSetupPermission** concede permissões do grupo RTCUniversalServerAdmins em um OU, conforme especificado na tabela a seguir:
  
**Permissões concedidas para Objetos no OU**

|**As permissões aplicam-se:**|**As permissões concedidas são:**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> | Acesso especial: <br/>  Ler servicePrincipalName <br/>  Gravar servicePrincipalName <br/>  Excluir árvore <br/>  Replicando mudanças de diretório <br/> |
|Objetos do serviceConnectionPoint descendente  <br/> | Acesso especial: <br/>  Permissões de leitura <br/>  Permissões de gravação <br/>  Criar filho <br/>  Excluir filho <br/>  Conteúdo da lista <br/>  Gravar propriedade <br/>  Ler propriedade <br/>  Excluir árvore <br/> |
|Objetos msRTCSIP-Server descendentes  <br/> | Acesso especial: <br/>  Gravar propriedade <br/>  Ler propriedade <br/>  Excluir árvore <br/> |
|Objetos msRTCSIP-WebComponents descendentes  <br/> | Acesso especial: <br/>  Gravar propriedade <br/>  Ler propriedade <br/>  Excluir árvore <br/> |
|Objetos msRTCSIP-MCU descendentes  <br/> | Acesso especial: <br/>  Gravar propriedade <br/>  Ler propriedade <br/>  Excluir árvore <br/> |
|Objetos msRTCSIP-MediationServer descendentes  <br/> | Acesso especial: <br/>  Gravar propriedade <br/>  Ler propriedade <br/>  Excluir árvore <br/> |
|Objetos msRTCSIP-ApplicationServer descendentes  <br/> | Acesso especial: <br/>  Gravar propriedade <br/>  Ler propriedade <br/>  Excluir árvore <br/> |
|Objetos msRTCSIP-ConnectionPoint descendentes  <br/> | Acesso especial: <br/>  Gravar propriedade <br/>  Ler propriedade <br/>  Excluir árvore <br/> |
|Objetos do computador descendentes  <br/> | Acesso especial para serviceConnectionPoint: <br/>  Criar objetos filhos <br/>  Excluir objetos filhos <br/>  Excluir árvore <br/>  Acesso especial para informação pública: <br/>  Ler propriedade <br/>  Acesso especial para nome de host DNS: <br/>  Ler propriedade <br/> |
   

