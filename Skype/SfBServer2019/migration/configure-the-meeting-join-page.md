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
description: Quando um usuário clica em um link de reunião em uma solicitação de reunião, a página de junção de reunião detecta qual cliente já está instalado no computador do usuário. Se um cliente já estiver instalado, esse cliente abre e participa da reunião. Se um cliente não estiver instalado, por padrão, o Aplicativo Web será aberto.
ms.openlocfilehash: c90e8afa95a73618eb1aa95b3d8d174e950e7e92a49988cb6146209f49cc0e58
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54295118"
---
# <a name="configure-the-meeting-join-page"></a>Configurar a página de ingresso na reunião

Quando um usuário clica em um link de reunião em uma solicitação de reunião, a página de junção de reunião detecta qual cliente já está instalado no computador do usuário. Se um cliente já estiver instalado, esse cliente abre e participa da reunião. Se um cliente não estiver instalado, por padrão, o Aplicativo Web será aberto.
  
Você pode modificar o comportamento da página de junção de reunião se quiser permitir que os usuários participem de reuniões. Essas opções de configuração foram removidas do Painel de Controle, mas você as configura usando o cmdlet CsWebServiceConfiguration.
  
**Parâmetros CsWebServiceConfiguration da página de ingresso em reunião**

|**Parâmetro CsWebServiceConfiguration**|**Descrição**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |Se definido como True, os usuários que ingressarem em uma reunião usando um aplicativo cliente diferente do Lync terão a oportunidade de ingressar na reunião. O valor padrão é False.  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |Quando definido como True, as opções alternativas para ingressar em uma conferência online serão expandidas automaticamente e mostradas aos usuários. Quando definido como False (o valor padrão), essas opções estarão disponíveis, mas o usuário terá que exibir a lista de opções para si mesmo.  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a>Para configurar a página de junção de reunião usando Skype for Business Server Shell de Gerenciamento 2019

1. Inicie o Shell de Gerenciamento Skype for Business Server 2019: clique em **Iniciar,** clique em Todos os **Programas,** clique em **Microsoft Skype for Business Server 2019** e clique em Skype for Business Server **Shell de** Gerenciamento.
    
2. Execute o seguinte cmdlet: 
    
   ```PowerShell
   Get-CsWebServiceConfiguration
   ```

    Este cmdlet retorna as definições de configurações do serviço da Web.
    
3. Execute o seguinte comando, com os parâmetros definidos como True ou False, dependendo de sua preferência (para obter detalhes sobre os parâmetros para este cmdlet, consulte a documentação do Shell de Gerenciamento [Skype for Business Server):](../../SfbServer/manage/management-shell.md)
    
   ```PowerShell
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


