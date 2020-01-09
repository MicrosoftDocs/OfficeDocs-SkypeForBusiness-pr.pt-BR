---
title: Configurar a página de ingresso na reunião
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: End User
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Quando um usuário clica em um link de reunião em uma solicitação de reunião, a página ingressar na reunião detecta qual cliente já está instalado no computador do usuário. Se um cliente já estiver instalado, esse cliente abrirá e ingressará na reunião. Se um cliente não estiver instalado, por padrão o aplicativo Web será aberto.
ms.openlocfilehash: 5c9e6653783d90411e0f701b5d3395c569d8bdff
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40989556"
---
# <a name="configure-the-meeting-join-page"></a>Configurar a página de ingresso na reunião

Quando um usuário clica em um link de reunião em uma solicitação de reunião, a página ingressar na reunião detecta qual cliente já está instalado no computador do usuário. Se um cliente já estiver instalado, esse cliente abrirá e ingressará na reunião. Se um cliente não estiver instalado, por padrão o aplicativo Web será aberto.
  
Você pode modificar o comportamento da página de associação de reunião se desejar permitir que os usuários ingressem em reuniões. Essas opções de configuração foram removidas do painel de controle, mas você as configura usando o cmdlet CsWebServiceConfiguration.
  
**Parâmetros de CsWebServiceConfiguration da página de ingresso na reunião**

|**Parâmetro CsWebServiceConfiguration**|**Descrição**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |Se definido como verdadeiro, os usuários que ingressam em uma reunião usando um aplicativo cliente que não seja o Lync terão a oportunidade de ingressar na reunião. O valor padrão é False.  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |Quando definida como true, as opções alternativas para ingressar em uma conferência online serão expandidas automaticamente e exibidas para os usuários. Quando definido como falso (o valor padrão), essas opções estarão disponíveis, mas o usuário precisará exibir a lista de opções para si mesmo.  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a>Para configurar a página ingressar na reunião usando o Shell de gerenciamento do Skype for Business Server 2019

1. Inicie o Shell de gerenciamento do Skype for Business Server 2019: clique em **Iniciar**, em **todos os programas**, em **Microsoft Skype for Business Server 2019**e, em seguida, clique em **Shell de gerenciamento do Skype for Business Server**.
    
2. Execute o seguinte cmdlet: 
    
   ```PowerShell
   Get-CsWebServiceConfiguration
   ```

    Esse cmdlet retorna as configurações de serviço Web.
    
3. Execute o seguinte comando, com os parâmetros definidos como verdadeiro ou falso, dependendo da sua preferência (para obter detalhes sobre os parâmetros para esse cmdlet, consulte a documentação do [Shell de gerenciamento do Skype for Business Server](../../SfbServer/manage/management-shell.md) ):
    
   ```PowerShell
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


