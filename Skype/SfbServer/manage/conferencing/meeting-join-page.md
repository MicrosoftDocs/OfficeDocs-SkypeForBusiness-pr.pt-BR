---
title: Configurar a reunião página de ingresso em Skype para Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: 'Resumo: Saiba como configurar a reunião página de ingresso em Skype para Business Server 2015.'
ms.openlocfilehash: c0b3ed39fc2f7a1a48635353cc1db673a4bd1cd5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server-2015"></a>Configurar a reunião página de ingresso em Skype para Business Server 2015
 
**Resumo:** Saiba como configurar a reunião página de ingresso em Skype para Business Server 2015.
  
Quando um usuário clica em um link da reunião em uma solicitação de reunião, a reunião página de ingresso detecta se um Skype para o cliente de negócios já está instalado no computador do usuário. Se um cliente já estiver instalado, o cliente abre e participa da reunião. Se um cliente não estiver instalado, por padrão da versão de 2015 do Skype para Business client será aberta. 
  
## <a name="configure-the-meeting-join-page"></a>Configurar a reunião página de participação

Você pode modificar o comportamento de participação da reunião se você quiser permitir que os usuários ingressem em reuniões com outras versões do cliente de página. Essas opções de configuração foram removidas do Skype para painel de controle do servidor de negócios, mas você pode configurá-los usando o cmdlet Set-CsWebServiceConfiguration.
  
**Parâmetros de Set-CsWebServiceConfiguration página ingressar em reunião**

|**Parâmetro Set-CsWebServiceConfiguration**|**Descrição**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |Este parâmetro foi reduzido para uso com a versão local do Skype para Business Server 2015.  <br/> Se definido como True, usuários participando de uma reunião usando um aplicativo cliente diferente do Skype para negócios receberá a oportunidade para ingressar na reunião usando o seu aplicativo atual do cliente. O valor padrão é False.  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |Este parâmetro foi reduzido para uso com a versão local do Skype para Business Server 2015.  <br/>  Se definido como True, alternativo opções para ingressar em uma conferência online são expandidos automaticamente e mostrada para os usuários. Se definido como False (o valor padrão), essas opções estarão disponíveis, mas o usuário terá que exibir a lista de opções para si próprios.  <br/> |
   

