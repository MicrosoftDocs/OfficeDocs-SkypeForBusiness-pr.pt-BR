---
title: Configurar a página de junção de reunião Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: 'Resumo: saiba como configurar a página de junção de reunião Skype for Business Server.'
ms.openlocfilehash: ba90c771321732956b38f5f07af10798829fc54f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58587087"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a>Configurar a página de junção de reunião Skype for Business Server
 
**Resumo:** Saiba como configurar a página de junção de reunião Skype for Business Server.
  
Quando um usuário clica em um link de reunião em uma solicitação de reunião, a página de junção de reunião detecta se um cliente Skype for Business já está instalado no computador do usuário. Se um cliente já estiver instalado, ele abre e participa da reunião. Se um cliente não estiver instalado, por padrão, o Skype for Business cliente será aberto. 
  
## <a name="configure-the-meeting-join-page"></a>Configurar a página de ingresso na reunião

Você pode modificar o comportamento da página de junção de reunião se quiser permitir que os usuários participem de reuniões com outras versões do cliente. Essas opções de configuração foram removidas do Painel de Controle Skype for Business Server, mas você as configura usando o cmdlet Set-CsWebServiceConfiguration.
  
**Parâmetros da Página de Set-CsWebServiceConfiguration de Reunião**

|**Parâmetro Set-CsWebServiceConfiguration**|**Descrição**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |Esse parâmetro foi preterido para uso com a versão local do Skype for Business Server.  <br/> Se definido como True, os usuários que ingressarem em uma reunião usando um aplicativo cliente diferente do Skype for Business terão a oportunidade de ingressar na reunião usando seu aplicativo cliente atual. O valor padrão é False.  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |Esse parâmetro foi preterido para uso com a versão local do Skype for Business Server.  <br/>  Se definido como True, as opções alternativas para ingressar em uma conferência online serão expandidas automaticamente e mostradas aos usuários. Se definido como False (o valor padrão), essas opções estarão disponíveis, mas o usuário terá que exibir a lista de opções para si mesmo.  <br/> |
   

