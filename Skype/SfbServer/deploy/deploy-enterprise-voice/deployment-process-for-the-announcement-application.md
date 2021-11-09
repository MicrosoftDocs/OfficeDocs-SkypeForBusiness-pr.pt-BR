---
title: Processo de implantação para o aplicativo De comunicado no Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: Processo de implantação e etapas para o aplicativo De comunicado Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 7ea0024bfda4846bc02d32d70d37f0ec91250cd5
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60830665"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a>Processo de implantação para o aplicativo De comunicado no Skype for Business Server
 
Processo de implantação e etapas para o aplicativo De comunicado Skype for Business Server Enterprise Voice.
  
O aplicativo De comunicado é um recurso Enterprise Voice que permite configurar o que acontece com as chamadas para extensões não atribuídas (extensões que são válidas para sua organização, mas não são atribuídas a uma pessoa ou um telefone). Por exemplo, você pode configurar chamadas a números não atribuídos para que reproduzam uma mensagem ou sejam transferidas para um destino diferente, ou ambos.
  
O aplicativo De comunicado é instalado como um recurso do aplicativo Grupo de Resposta no Servidor de Front-End ou Edição Standard servidor quando você implanta Enterprise Voice. Você precisa configurar Comunicados carregando arquivos de áudio ou configurando o mecanismo TTS (conversão de texto em fala) e a tabela de números não atribuídos.
  
Esta seção fornece uma visão geral das etapas envolvidas na implantação do aplicativo Comunicado. Você deve implantar Enterprise Voice antes de configurar comunicados. Os componentes exigidos pelo aplicativo Comunicado são instalados e habilitados quando você implanta Enterprise Voice.
  
**Processo de implantação do comunicado**

|**Fase**|**Etapas**|**Funções**|**Documentação de Implantação**|
|:-----|:-----|:-----|:-----|
|Definir configurações do comunicado  <br/> | Crie o comunicado através da gravação e carregamento de arquivos de áudio ou usando texto em fala (TTS). <br/>  Configure os intervalos de números não atribuídos na tabela de número não atribuída e os associe com o comunicado adequado. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsViewOnlyAdministrator  <br/> |[Criar ou excluir um comunicado no Skype for Business Server](create-an-announcement.md) <br/> [Criar ou modificar um intervalo de números não atribuídos Skype for Business Server](create-or-modify-an-unassigned-number-range.md) <br/> |
|Verifique a implantação do comunicado  <br/> |Faça o teste escutando os comunicados para verificar se sua configuração funciona como o esperado.  <br/> |-  <br/> |[(Opcional) Verificar a implantação do Comunicado no Skype for Business](optional-verify-announcement-deployment.md) <br/> |
   

