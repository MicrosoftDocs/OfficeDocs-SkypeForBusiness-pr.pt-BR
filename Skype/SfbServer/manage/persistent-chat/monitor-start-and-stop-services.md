---
title: Monitorar, iniciar e parar serviços de Chat Persistente no Skype for Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: 'Resumo: Saiba como iniciar, interromper e monitorar os serviços de Chat persistente no Skype para Business Server 2015.'
ms.openlocfilehash: 272ea0f4270b1109ff77b5d809472051705b6f10
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20991586"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a>Monitorar, iniciar e parar serviços de Chat Persistente no Skype for Business Server 2015
 
**Resumo:** Saiba como iniciar, interromper e monitorar os serviços de Chat persistente no Skype para Business Server 2015.
  
Os serviços de Chat persistente e conformidade de Chat persistente fazem parte do Skype para a topologia de servidor de negócios e pode, portanto, ser monitorados, interrompido e iniciados usando os cmdlets a seguir:
  
|||
|:-----|:-----|
|Get-CsWindowsService  <br/> |Retorna informações detalhadas sobre Skype para componentes de negócios Server 2015 que são executados como serviços do Windows.  <br/> |
|Start-CsWindowsService  <br/> |Inicia o serviço.  <br/> |
|Stop-CsWindowsService  <br/> |Interrompe o serviço.  <br/> |
   
> [!NOTE]
> Bate-papo persistente está disponível no Skype para Business Server 2015, mas não é mais suportado no Skype para Business Server 2019. A mesma funcionalidade está disponível em equipes. Para obter mais informações, consulte [jornada do Skype para negócios às equipes da Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Se você precisar utilizar o chat persistente, suas opções são para migrar tanto os usuários que requerem essa funcionalidade para equipes ou para continuar usando o Skype para Business Server 2015. 

Para obter informações detalhadas sobre como usar os cmdlets, consulte [Skype do Shell de gerenciamento do Business Server 2015](../management-shell.md).
  

