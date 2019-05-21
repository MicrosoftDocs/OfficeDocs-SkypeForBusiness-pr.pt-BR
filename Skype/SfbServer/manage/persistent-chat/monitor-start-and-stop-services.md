---
title: Monitorar, iniciar e parar serviços de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: 'Resumo: saiba como iniciar, parar e monitorar os serviços de chat persistente no Skype for Business Server 2015.'
ms.openlocfilehash: 161bda3cb02bf6208b4db9f1c6825d3fe433eeca
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279288"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a>Monitorar, iniciar e parar serviços de Chat Persistente no Skype for Business Server 2015
 
**Resumo:** Saiba como iniciar, parar e monitorar os serviços de chat persistente no Skype for Business Server 2015.
  
Os serviços de chat persistente e os serviços de conformidade de chat persistente fazem parte da topologia do Skype for Business Server e, portanto, podem ser monitorados, interrompidos e iniciados usando os seguintes cmdlets:
  
|||
|:-----|:-----|
|get-CsWindowsService  <br/> |Retorna informações detalhadas sobre os componentes do Skype for Business Server 2015 executados como serviços do Windows.  <br/> |
|start-CsWindowsService  <br/> |Inicia o serviço.  <br/> |
|stop-CsWindowsService  <br/> |Interrompe o serviço.  <br/> |
   
> [!NOTE]
> O chat persistente está disponível no Skype for Business Server 2015, mas não é mais compatível com o Skype for Business Server 2019. A mesma funcionalidade está disponível no Microsoft Teams. Para obter mais informações, consulte [jornada do Skype for Business para o Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams). Se você precisar usar chats persistentes, suas opções serão migrar os usuários que exigem essa funcionalidade para o Microsoft Teams ou para continuar usando o Skype for Business Server 2015. 

Para obter informações detalhadas sobre como usar os cmdlets, consulte [Skype for Business Server 2015 Management Shell](../management-shell.md).
  

