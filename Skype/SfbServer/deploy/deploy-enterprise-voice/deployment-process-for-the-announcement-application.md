---
title: Processo de implantação para o aplicativo de anúncio no Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: Processo de implantação e etapas para o aplicativo de anúncio no Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 6aabc5090d233b991e1fd89ef61f364a6b1c5666
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20968910"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a>Processo de implantação para o aplicativo de anúncio no Skype para Business Server
 
Processo de implantação e etapas para o aplicativo de anúncio no Skype para Business Server Enterprise Voice.
  
O aplicativo de anúncio é um recurso de Enterprise Voice que permite que você configure o que acontece às chamadas para extensões não atribuídas (extensões que são válidos para a sua organização, mas não estão atribuídas a uma pessoa ou um telefone). Por exemplo, você pode configurar chamadas a números não atribuídos para que reproduzam uma mensagem ou sejam transferidas para um destino diferente, ou ambos.
  
O aplicativo de anúncio está instalado como um recurso do aplicativo do grupo de resposta no servidor Front-End ou Standard Edition servidor quando você implanta o Enterprise Voice. Você precisa configurar Comunicados carregando arquivos de áudio ou configurando o mecanismo TTS (conversão de texto em fala) e a tabela de números não atribuídos.
  
Esta seção fornece uma visão geral das etapas envolvidas na implantação do aplicativo de anúncio. Você deve implantar o Enterprise Voice antes de configurar comunicados. Os componentes necessários para o aplicativo de anúncio estão instalados e ativados quando você implanta o Enterprise Voice.
  
**Processo de implantação do comunicado**

|**Fase**|**Etapas**|**Funções**|**Documentação de implantação**|
|:-----|:-----|:-----|:-----|
|Definir configurações do comunicado  <br/> | Crie o comunicado através da gravação e carregamento de arquivos de áudio ou usando texto em fala (TTS). <br/>  Configure os intervalos de números não atribuídos na tabela de número não atribuída e os associe com o comunicado adequado. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsViewOnlyAdministrator  <br/> |[Criar ou excluir um anúncio no Skype para Business Server](create-an-announcement.md) <br/> [Criar ou modificar um intervalo de números não atribuído no Skype para Business Server](create-or-modify-an-unassigned-number-range.md) <br/> |
|Verifique a implantação do comunicado  <br/> |Faça o teste escutando os comunicados para verificar se sua configuração funciona como o esperado.  <br/> |-  <br/> |[(Opcional) Verificar a implantação do comunicado na Skype para negócios](optional-verify-announcement-deployment.md) <br/> |
   

