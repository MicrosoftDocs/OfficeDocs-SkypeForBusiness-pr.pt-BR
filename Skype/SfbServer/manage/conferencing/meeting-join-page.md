---
title: Configurar a página de junção de reunião no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: 'Resumo: Saiba como configurar a página de junção de reunião no Skype for Business Server.'
ms.openlocfilehash: 247664a3ff4bbc4ee055775d26f1d077b662752b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828031"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a>Configurar a página de junção de reunião no Skype for Business Server
 
**Resumo:** Saiba como configurar a página de junção de reunião no Skype for Business Server.
  
Quando um usuário clica em um link de reunião em uma solicitação de reunião, a página de entrada da reunião detecta se um cliente do Skype for Business já está instalado no computador do usuário. Se um cliente já estiver instalado, ele abre e participa da reunião. Se um cliente não estiver instalado, por padrão, o cliente Skype for Business será aberto. 
  
## <a name="configure-the-meeting-join-page"></a>Configurar a página de ingresso na reunião

Você pode modificar o comportamento da página de entrada da reunião se quiser permitir que os usuários participem de reuniões com outras versões do cliente. Essas opções de configuração foram removidas do Painel de Controle do Skype for Business Server, mas você as configura usando o Set-CsWebServiceConfiguration cmdlet.
  
**Parâmetros de página de Set-CsWebServiceConfiguration reunião**

|**Parâmetro Set-CsWebServiceConfiguration**|**Descrição**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |Esse parâmetro foi preterido para uso com a versão local do Skype for Business Server.  <br/> Se for definido como True, os usuários que ingressarem em uma reunião usando um aplicativo cliente diferente do Skype for Business terão a oportunidade de participar da reunião usando seu aplicativo cliente atual. O valor padrão é False.  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |Esse parâmetro foi preterido para uso com a versão local do Skype for Business Server.  <br/>  Se for definido como True, as opções alternativas para ingressar em uma conferência online serão automaticamente expandidas e mostradas aos usuários. Se for definido como False (o valor padrão), essas opções estarão disponíveis, mas o usuário terá que exibir a lista de opções por conta própria.  <br/> |
   

