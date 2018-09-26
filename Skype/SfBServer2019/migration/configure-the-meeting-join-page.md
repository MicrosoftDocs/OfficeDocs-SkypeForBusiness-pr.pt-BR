---
title: Configurar a reunião página de participação
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: End User
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Quando um usuário clica em um link da reunião em uma solicitação de reunião, a reunião página de ingresso detecta qual cliente já estiver instalado no computador do usuário. Se um cliente já estiver instalado, o que o cliente abre e participa da reunião. Se um cliente não estiver instalado, por padrão, que o aplicativo Web é aberta.
ms.openlocfilehash: 5e56641ce2e19c3194a92cb60bd7291380bc965a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027365"
---
# <a name="configure-the-meeting-join-page"></a>Configurar a reunião página de participação

Quando um usuário clica em um link da reunião em uma solicitação de reunião, a reunião página de ingresso detecta qual cliente já estiver instalado no computador do usuário. Se um cliente já estiver instalado, o que o cliente abre e participa da reunião. Se um cliente não estiver instalado, por padrão, que o aplicativo Web é aberta.
  
Você pode modificar o comportamento de participação da reunião se você quiser permitir que os usuários ingressem em reuniões de página. Essas opções de configuração foram removidas do painel de controle, mas você pode configurá-los usando o cmdlet CsWebServiceConfiguration.
  
**Parâmetros de CsWebServiceConfiguration da página de participação de reunião**

|**Parâmetro CsWebServiceConfiguration**|**Descrição**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |Se definido como True, usuários participando de uma reunião usando um aplicativo cliente diferente do Lync receberá a oportunidade de ingressar na reunião. O valor padrão é False.  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |Quando definido como True, alternados opções para ingressar em uma conferência online será automaticamente expandida e exibido aos usuários. Quando definido como False (o valor padrão), essas opções estarão disponíveis, mas o usuário terá que exibir a lista de opções para si próprios.  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a>Para configurar a reunião página de ingresso usando Skype do Shell de gerenciamento do Business Server 2019

1. Inicie o Skype do Shell de gerenciamento do Business Server 2019: clique em **Iniciar**, clique em **Todos os programas**, clique em **Microsoft Skype para Business Server 2019**e, em seguida, clique em **Skype do Shell de gerenciamento do servidor de negócios**.
    
2. Execute o seguinte cmdlet: 
    
  ```
  Get-CsWebServiceConfiguration
  ```

    Este cmdlet retorna as definições de configuração de serviço de web.
    
3. Execute o seguinte comando, com os parâmetros definidos para verdadeiro ou falso, dependendo da sua preferência (para obter detalhes sobre os parâmetros deste cmdlet, consulte a documentação do [Skype do Shell de gerenciamento do servidor de negócios](../../SfbServer/manage/management-shell.md) ):
    
  ```
  Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
  ```


