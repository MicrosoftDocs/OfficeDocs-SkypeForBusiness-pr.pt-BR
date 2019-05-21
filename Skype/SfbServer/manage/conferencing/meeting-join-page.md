---
title: Configurar a página ingressar na reunião no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: 'Resumo: saiba como configurar a página ingressar na reunião no Skype for Business Server.'
ms.openlocfilehash: 30e220f2a1745aea0a77e3ec3ff491b842a2b221
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283722"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a>Configurar a página ingressar na reunião no Skype for Business Server
 
**Resumo:** Saiba como configurar a página ingressar na reunião no Skype for Business Server.
  
Quando um usuário clica em um link de reunião em uma solicitação de reunião, a página ingressar na reunião detecta se um cliente Skype for Business já está instalado no computador do usuário. Se um cliente já estiver instalado, o cliente abrirá e ingressará na reunião. Se um cliente não estiver instalado, por padrão, o cliente Skype for Business será aberto. 
  
## <a name="configure-the-meeting-join-page"></a>Configurar a página de ingresso na reunião

Você pode modificar o comportamento da página de associação de reunião se desejar permitir que os usuários ingressem em reuniões com outras versões do cliente. Essas opções de configuração foram removidas do painel de controle do Skype for Business Server, mas você as configura usando o cmdlet Set-CsWebServiceConfiguration.
  
**Parâmetros do conjunto de páginas de associação de reunião-CsWebServiceConfiguration**

|**Parâmetro Set-CsWebServiceConfiguration**|**Descrição**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |Esse parâmetro foi preterido para uso com a versão local do Skype for Business Server.  <br/> Se definido como true, os usuários que ingressam em uma reunião usando um aplicativo cliente diferente do Skype for Business terão a oportunidade de ingressar na reunião usando o aplicativo cliente atual. O valor padrão é False.  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |Esse parâmetro foi preterido para uso com a versão local do Skype for Business Server.  <br/>  Se definido como true, as opções alternativas para ingressar em uma conferência online serão automaticamente expandidas e exibidas para os usuários. Se definido como falso (o valor padrão), essas opções estarão disponíveis, mas o usuário precisará exibir a lista de opções para si mesmo.  <br/> |
   

