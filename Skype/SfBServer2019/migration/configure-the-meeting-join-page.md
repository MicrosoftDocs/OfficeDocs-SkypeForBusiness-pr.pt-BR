---
title: Configurar a página de ingresso na reunião
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: End User
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Quando um usuário clica em um link de reunião em uma solicitação de reunião, a página de ingresso na reunião detecta qual cliente já está instalado no computador do usuário. Se um cliente já estiver instalado, esse cliente abre e participa da reunião. Se um cliente não estiver instalado, por padrão, o aplicativo Web será aberto.
ms.openlocfilehash: a7bb0983438708bbc0d30cd527eb494491c3cbf2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754021"
---
# <a name="configure-the-meeting-join-page"></a>Configurar a página de ingresso na reunião

Quando um usuário clica em um link de reunião em uma solicitação de reunião, a página de ingresso na reunião detecta qual cliente já está instalado no computador do usuário. Se um cliente já estiver instalado, esse cliente abre e participa da reunião. Se um cliente não estiver instalado, por padrão, o aplicativo Web será aberto.
  
Você pode modificar o comportamento da página de ingresso na reunião se quiser permitir que os usuários ingressem em reuniões. Essas opções de configuração foram removidas do painel de controle, mas você as configura usando o cmdlet CsWebServiceConfiguration.
  
**Parâmetros CsWebServiceConfiguration da página de ingresso em reunião**

|**Parâmetro CsWebServiceConfiguration**|**Descrição**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |Se for definido como true, os usuários que ingressarem em uma reunião usando um aplicativo cliente que não seja o Lync terão a oportunidade de participar da reunião. O valor padrão é False.  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |Quando definido como true, as opções alternativas para ingressar em uma conferência online serão expandidas automaticamente e mostradas para os usuários. Quando definido como false (o valor padrão), essas opções estarão disponíveis, mas o usuário terá que exibir a lista de opções para elas.  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a>Para configurar a página de ingresso na reunião usando o Shell de gerenciamento do Skype for Business Server 2019

1. Inicie o Shell de gerenciamento do Skype for Business Server 2019: clique em **Iniciar**, em **todos os programas**, em **Microsoft Skype for Business Server 2019**e em **Shell de gerenciamento do Skype for Business Server**.
    
2. Execute o seguinte cmdlet: 
    
   ```PowerShell
   Get-CsWebServiceConfiguration
   ```

    Este cmdlet retorna as definições de configurações do serviço da Web.
    
3. Execute o seguinte comando, com os parâmetros definidos como true ou false, dependendo da sua preferência (para obter detalhes sobre os parâmetros desse cmdlet, consulte a documentação do [Shell de gerenciamento do Skype for Business Server](../../SfbServer/manage/management-shell.md) ):
    
   ```PowerShell
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


