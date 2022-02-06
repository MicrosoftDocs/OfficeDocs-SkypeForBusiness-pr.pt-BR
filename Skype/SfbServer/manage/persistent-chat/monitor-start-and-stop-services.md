---
title: 'Monitorar, iniciar e interromper os serviços de Chat Persistente no Skype for Business Server 2015'
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: 'Resumo: saiba como iniciar, parar e monitorar os serviços de Chat Persistente no Skype for Business Server 2015.'
---

# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a>Monitorar, iniciar e interromper os serviços de Chat Persistente no Skype for Business Server 2015
 
**Resumo:** Saiba como iniciar, parar e monitorar os serviços de Chat Persistente no Skype for Business Server 2015.
  
Os serviços de Chat Persistente e Conformidade de Chat Persistente fazem parte da topologia Skype for Business Server e, portanto, podem ser monitorados, interrompidos e iniciados usando os seguintes cmdlets:
  
|Cmdlet|Função|
|:-----|:-----|
|get-CsWindowsService  <br/> |Retorna informações detalhadas sobre Skype for Business Server componentes 2015 que são executados como serviços Windows.  <br/> |
|start-CsWindowsService  <br/> |Inicia o serviço.  <br/> |
|stop-CsWindowsService  <br/> |Interrompe o serviço.  <br/> |
   
> [!NOTE]
> O chat persistente está disponível no Skype for Business Server 2015, mas não tem mais suporte no Skype for Business Server 2019. A mesma funcionalidade está disponível no Teams. Para obter mais informações, consulte [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here). Se você precisar usar o chat persistente, suas opções são migrar usuários que exigem essa funcionalidade para Teams ou continuar usando o Skype for Business Server 2015. 

Para obter informações detalhadas sobre como usar os cmdlets, [consulte Skype for Business Server Shell de Gerenciamento 2015](../management-shell.md).
  

