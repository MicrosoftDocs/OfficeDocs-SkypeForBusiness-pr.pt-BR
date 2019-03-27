---
title: Teste a conferência discada no Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4ccbfd4-6075-466f-b459-20561318803d
description: 'Resumo: Saiba como testar conferência discada em Skype para Business Server.'
ms.openlocfilehash: 99d91a4d3e9729da7b86f723f4a980a887d88b5f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880914"
---
# <a name="test-dial-in-conferencing-in-skype-for-business-server"></a>Teste a conferência discada no Skype para Business Server
 
**Resumo:** Saiba como testar conferência discada em Skype para Business Server.
  
Como verificação final da configuração da conferência discada, você pode pesquisar planos de discagem com uma região de conferência discada que não seja usada por nenhum número de acesso e para números de acesso que não especificaram uma região de conferência discada. Você também deve verificar se a página da web de Configurações de Conferência Discada e os números de acesso discado funcionam corretamente.
  
## <a name="find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a>Encontre planos de discagem com uma região de conferência discada que não seja usada por um número de acesso

1. Faça logon no computador como membro do grupo  RTCUniversalServerAdmins  ou como membro da função  Cs-ServerAdministrator  ou  CsAdministrator.
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
3. Execute o seguinte no prompt de comando:
    
   ```
   Get-CsDialinConferencingAccessNumber -EmptyRegion
   ```

    Este cmdlet retorna todos os planos de discagem que possuem uma região de conferência discada que não é usada por um número de acesso.
    
Para obter mais informações, consulte [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).
  
## <a name="find-access-numbers-without-assigned-regions"></a>Encontre números de acesso sem regiões atribuídas

1. Faça logon no computador como membro do grupo  RTCUniversalServerAdmins  ou como membro da função  Cs-ServerAdministrator  ou  CsAdministrator.
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
3. Execute o seguinte no prompt de comando:
    
   ```
   Get-CsDialinConferencingAccessNumber -Region NULL
   ```

    Este cmdlet retorna todos números de acesso de conferência discada que não estão associados a uma região.
    
Para obter mais informações, consulte [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).
  
## <a name="test-webpage-and-access-numbers"></a>Teste a página da web e os números de acesso

Para verificar se a página da Web de Configurações de Conferência Discada e os números de acesso discado funcionam corretamente, faça o seguinte:
  
- Entre na URL simples para testar a página da Web Configurações de Conferência Discada.
    
- Teste se os números de acesso funcionam corretamente para um pool específico executando o script posteriormente neste tópico. Esse script simula chamadas para números de acesso. Você precisa do endereço SIP e das credenciais de um cliente de UC (comunicações unificadas) que esteja hospedado no pool específico para usar esse script.
    
### <a name="to-test-access-numbers-for-a-specific-pool"></a>Para testar os números de acesso de um pool específico

1. Faça logon no computador como membro do grupo  RTCUniversalServerAdmins  ou como membro da função  Cs-ServerAdministrator  ou  CsAdministrator.
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
3. Execute o seguinte no prompt de comando:
    
   ```
   $credentials = Get-Credential
   User name:  testuser1@contoso.com
   Password:  ********
   Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
   ```

    O relatório resultante mostra êxito ou falha, juntamente com informações de diagnóstico específicas. -Verbose sinalizador fornece mais informações detalhadas sobre o acesso de quantos números foram encontrados e detalhes sobre cada um deles.
    
Para obter mais informações, consulte [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps).
  

