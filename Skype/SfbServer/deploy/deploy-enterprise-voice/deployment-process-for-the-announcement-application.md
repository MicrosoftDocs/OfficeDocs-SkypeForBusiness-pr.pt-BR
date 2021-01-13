---
title: Processo de implantação do aplicativo Comunicado no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: Processo de implantação e etapas para o aplicativo Comunicado no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: cfb1436f22681b45de5c399907d4776a9d1db5de
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812301"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a>Processo de implantação do aplicativo Comunicado no Skype for Business Server
 
Processo de implantação e etapas para o aplicativo Comunicado no Skype for Business Server Enterprise Voice.
  
O aplicativo Comunicado é um recurso do Enterprise Voice que permite configurar o que acontece com chamadas a ramais não atribuídos (extensões válidas para sua organização, mas que não estão atribuídas a uma pessoa ou telefone). Por exemplo, você pode configurar chamadas a números não atribuídos para que reproduzam uma mensagem ou sejam transferidas para um destino diferente, ou ambos.
  
O aplicativo Comunicado é instalado como um recurso do aplicativo Grupo de Resposta no servidor front-end ou servidor Standard Edition quando você implanta o Enterprise Voice. Você precisa configurar Comunicados carregando arquivos de áudio ou configurando o mecanismo TTS (conversão de texto em fala) e a tabela de números não atribuídos.
  
Esta seção fornece uma visão geral das etapas envolvidas na implantação do aplicativo Comunicado. Você deve implantar o Enterprise Voice antes de configurar os comunicados. Os componentes exigidos pelo aplicativo Comunicado são instalados e habilitados quando você implanta o Enterprise Voice.
  
**Processo de implantação do comunicado**

|**Fase**|**Etapas**|**Funções**|**Documentação de Implantação**|
|:-----|:-----|:-----|:-----|
|Definir configurações do comunicado  <br/> | Crie o comunicado através da gravação e carregamento de arquivos de áudio ou usando texto em fala (TTS). <br/>  Configure os intervalos de números não atribuídos na tabela de número não atribuída e os associe com o comunicado adequado. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsViewOnlyAdministrator  <br/> |[Criar ou excluir um comunicado no Skype for Business Server](create-an-announcement.md) <br/> [Criar ou modificar um intervalo de números não atribuídos no Skype for Business Server](create-or-modify-an-unassigned-number-range.md) <br/> |
|Verifique a implantação do comunicado  <br/> |Faça o teste escutando os comunicados para verificar se sua configuração funciona como o esperado.  <br/> |-  <br/> |[(Opcional) Verificar a implantação do Comunicado no Skype for Business](optional-verify-announcement-deployment.md) <br/> |
   

