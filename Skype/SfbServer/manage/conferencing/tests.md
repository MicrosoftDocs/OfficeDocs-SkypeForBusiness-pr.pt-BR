---
title: Testar a conferência discada no Skype for Business Server
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
ms.assetid: f4ccbfd4-6075-466f-b459-20561318803d
description: 'Resumo: saiba como testar a conferência discada no Skype for Business Server.'
ms.openlocfilehash: 214ec05c49072825e6a8744cb92db66d864e3d34
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827931"
---
# <a name="test-dial-in-conferencing-in-skype-for-business-server"></a>Testar a conferência discada no Skype for Business Server
 
**Resumo:** Saiba como testar a conferência discada no Skype for Business Server.
  
Como verificação final da configuração da conferência discada, você pode pesquisar planos de discagem com uma região de conferência discada que não seja usada por nenhum número de acesso e números de acesso que não possuem uma região de conferência discada especificada. Você também deve verificar se a página da Web de Configurações de Conferência Discar e os números de acesso de discagem funcionam corretamente.
  
## <a name="find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a>Encontrar planos de discagem com uma região de conferência discada que não seja usada por um número de acesso

1. Efetue logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função Cs-ServerAdministrator ou CsAdministrator.
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**
    
3. Execute o seguinte no prompt de comando:
    
   ```PowerShell
   Get-CsDialinConferencingAccessNumber -EmptyRegion
   ```

    Este cmdlet retorna todos os planos de discagem que possuem uma região de conferência discada que não é usada por um número de acesso.
    
Para obter mais informações, [consulte Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).
  
## <a name="find-access-numbers-without-assigned-regions"></a>Encontrar números de acesso sem regiões atribuídas

1. Efetue logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função Cs-ServerAdministrator ou CsAdministrator.
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**
    
3. Execute o seguinte no prompt de comando:
    
   ```PowerShell
   Get-CsDialinConferencingAccessNumber -Region NULL
   ```

    Este cmdlet retorna todos números de acesso de conferência discada que não estão associados a uma região.
    
Para obter mais informações, [consulte Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).
  
## <a name="test-webpage-and-access-numbers"></a>Testar números de acesso e página da Web

Para verificar se a página da Web de Configurações de Conferência Discada e os números de acesso discado funcionam corretamente, faça o seguinte:
  
- Entre na URL simples para testar a página da Web Configurações de Conferência Discada.
    
- Teste se os números de acesso funcionam corretamente para um pool específico executando o script posteriormente neste tópico. Esse script simula chamadas para números de acesso. Você precisa do endereço SIP e das credenciais de um cliente de UC (comunicações unificadas) que esteja hospedado no pool específico para usar esse script.
    
### <a name="to-test-access-numbers-for-a-specific-pool"></a>Para testar os números de acesso de um pool específico

1. Efetue logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função Cs-ServerAdministrator ou CsAdministrator.
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**
    
3. Execute o seguinte no prompt de comando:
    
   ```PowerShell
   $credentials = Get-Credential
   User name:  testuser1@contoso.com
   Password:  ********
   Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
   ```

    O relatório resultante mostra êxito ou falha, juntamente com informações de diagnóstico específicas. O sinalizador -Verbose fornece informações mais detalhadas sobre quantos números de acesso foram encontrados e detalhes sobre eles.
    
Para obter mais informações, [consulte Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps).
  

