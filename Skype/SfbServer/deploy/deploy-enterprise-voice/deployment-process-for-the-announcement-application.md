---
title: Processo de implantação do aplicativo de anúncio no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: Processo de implantação e etapas para o aplicativo de anúncio no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 77d15c4ce749a97ec11ed5d5e083ccf6fa2aecfa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275605"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a>Processo de implantação do aplicativo de anúncio no Skype for Business Server
 
Processo de implantação e etapas para o aplicativo de anúncio no Skype for Business Server Enterprise Voice.
  
O aplicativo de anúncio é um recurso de voz empresarial que permite que você configure o que acontece às chamadas para extensões não atribuídas (extensões que são válidas para sua organização, mas não são atribuídas a uma pessoa ou telefone). Por exemplo, você pode configurar chamadas a números não atribuídos para que reproduzam uma mensagem ou sejam transferidas para um destino diferente, ou ambos.
  
O aplicativo de anúncio é instalado como um recurso do aplicativo de grupo de resposta no servidor front-end ou Standard Edition ao implantar o Enterprise Voice. Você precisa configurar Comunicados carregando arquivos de áudio ou configurando o mecanismo TTS (conversão de texto em fala) e a tabela de números não atribuídos.
  
Esta seção fornece uma visão geral das etapas envolvidas na implantação do aplicativo de anúncio. Você deve implantar o Enterprise Voice antes de configurar comunicados. Os componentes exigidos pelo aplicativo de anúncio são instalados e habilitados durante a implantação do Enterprise Voice.
  
**Processo de implantação do comunicado**

|**Fase**|**Etapas**|**Funções**|**Documentação de implantação**|
|:-----|:-----|:-----|:-----|
|Definir configurações do comunicado  <br/> | Crie o comunicado através da gravação e carregamento de arquivos de áudio ou usando texto em fala (TTS). <br/>  Configure os intervalos de números não atribuídos na tabela de número não atribuída e os associe com o comunicado adequado. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsViewOnlyAdministrator  <br/> |[Criar ou excluir um comunicado no Skype for Business Server](create-an-announcement.md) <br/> [Criar ou modificar um intervalo de números não atribuídos no Skype for Business Server](create-or-modify-an-unassigned-number-range.md) <br/> |
|Verifique a implantação do comunicado  <br/> |Faça o teste escutando os comunicados para verificar se sua configuração funciona como o esperado.  <br/> |-  <br/> |[Adicionais Verificar a implantação do lançamento no Skype for Business](optional-verify-announcement-deployment.md) <br/> |
   

