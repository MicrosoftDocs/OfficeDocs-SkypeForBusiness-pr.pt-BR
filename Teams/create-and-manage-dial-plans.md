---
title: Criar e gerenciar planos de discagem
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 7af17c94-5f8f-4452-ae1d-01f495b4dc94
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-apr2020
description: Saiba como usar o centro de administração Microsoft Teams ou Windows PowerShell para criar e gerenciar planos de discagem (planos de discagem de chamada PSTN).
ms.openlocfilehash: 44ecabfb04d8919ac289067818e736e170e6d181
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728700"
---
# <a name="create-and-manage-dial-plans"></a>Criar e gerenciar planos de discagem

Depois de planejar os planos de discagem para sua organização e descobrir todas as regras de normalização que precisam ser criadas para roteamento de voz, você estará pronto para criar os planos de discagem. Com uma conta de administrador com uma licença de Teams válida, você pode usar o centro de administração Microsoft Teams ou Windows PowerShell para criar e gerenciar planos de discagem.  

## <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

### <a name="create-a-dial-plan"></a>Criar um plano de discagem

1. Na navegação à esquerda do centro de administração Microsoft Teams, vá para **Plano de**  >  **Discagem de Voz**.
2. Clique **em Adicionar** e insira um nome e uma descrição para o plano de discagem.
    ![Captura de tela mostrando a página Adicionar para criar um plano de discagem.](media/create-dial-plan.png)
3. Em **Detalhes do plano de** discagem, especifique um prefixo de discagem externa se os usuários precisarem discar um ou mais dígitos principais adicionais (por exemplo, 9) para obter uma linha externa. Para fazer isso:
    1. Na caixa **Prefixo de discagem externa,** insira um prefixo de discagem externa. O prefixo pode ter até quatro caracteres (#,*e 0-9).
    2. Ativar **a discagem otimizada do dispositivo**. Se você especificar um prefixo de discagem externa, também deverá ativar essa configuração para aplicar o prefixo para que as chamadas possam ser feitas fora da sua organização.
4. Em **Regras de Normalização,** configure e associe uma ou mais regras [de normalização](what-are-dial-plans.md#normalization-rules) para o plano de discagem. Cada plano de discagem deve ter pelo menos uma regra de normalização associada a ele.  Para fazer isso, faça um ou mais dos seguintes:
    - Para criar uma nova regra de normalização e associá-la ao plano de discagem, clique em **Adicionar** e defina a regra.
    - Para editar uma regra de normalização que já está associada ao plano de discagem, selecione a regra clicando à esquerda do nome da regra e clique em **Editar**. Faça as alterações que você deseja e clique em **Salvar**.
    - Para remover uma regra de normalização do plano de discagem, selecione a regra clicando à esquerda do nome da regra e clique em **Remover**.
5. Organize as regras de normalização na ordem que você deseja. Clique **em Mover para cima** ou Mover **para** baixo para alterar a posição das regras na lista.

    > [!NOTE]
    > Teams percorre a lista de regras de normalização da parte superior para baixo e usa a primeira regra que corresponde ao número discado. Se você configurar um plano de discagem para que um número discado possa corresponder a mais de uma regra de normalização, certifique-se de que as regras mais restritivas sejam ordenadas acima das menos restritivas. Se você configurar um plano de discagem que normalize um número discado sem um "+", o serviço de chamada tentará normalizar o número novamente usando regras de plano de discagem regional e locatário. Para evitar a dupla normalização, é recomendável que todas as regras de normalização resultem em números começando com um "+". Os clientes de Roteamento Direto [podem](direct-routing-translate-numbers.md) usar regras de conversão de tronco para remover o "+" se necessário. 

6. Clique em **Salvar**.
7. Se você quiser testar o plano de discagem, em **Teste** plano de discagem , insira um número de telefone e clique em **Testar**.

### <a name="edit-a-dial-plan"></a>Editar um plano de discagem

1. Na navegação à esquerda do centro de administração Microsoft Teams, vá para **Plano de**  >  **Discagem de Voz**.
2. Selecione o plano de discagem clicando à esquerda do nome do plano de discagem e clique em **Editar**.
3. Faça as alterações que você deseja e clique em **Salvar**.

### <a name="assign-a-dial-plan-to-users"></a>Atribuir um plano de discagem aos usuários

Você atribui um plano de discagem da mesma maneira que atribui políticas. [!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="using-powershell"></a>Usando o Windows PowerShell
  
### <a name="start-powershell"></a>Iniciar o PowerShell
- Abra um prompt Windows PowerShell de comando e execute os seguintes comandos:

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```
  
### <a name="create-and-manage-your-dial-plans"></a>Criar e gerenciar seus planos de discagem

Você pode usar um único cmdlet ou um script do PowerShell para criar e gerenciar planos de discagem de locatários.
  
#### <a name="using-single-cmdlets"></a>Usando cmdlets individuais

- Para criar um novo plano de discagem, execute:
    
  ```PowerShell
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    Para outros exemplos e parâmetros, consulte [New-CsTenantDialPlan](/powershell/module/skype/new-cstenantdialplan).
    
- Para editar as configurações de um plano de discagem existente, execute:
    
  ```PowerShell
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    Para outros exemplos e parâmetros, consulte [Set-CsTenantDialPlan](/powershell/module/skype/set-cstenantdialplan).
    
- Para adicionar usuários a um plano de discagem, execute:
    
  ```PowerShell
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    Para outros exemplos e parâmetros, consulte [Grant-CsTenantDialPlan](/powershell/module/skype/grant-cstenantdialplan).
    
- Para exibir as configurações em um plano de discagem, execute:
    
  ```PowerShell
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    Para outros exemplos e parâmetros, consulte [Get-CsTenantDialPlan](/powershell/module/skype/get-cstenantdialplan?view=skype-ps).
    
- Para excluir um plano de discagem, execute:
    
  ```PowerShell
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    Para outros exemplos e parâmetros, consulte [Remove-CsTenantDialPlan](/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).
    
- Para ver as configurações do plano de discagem efetivo, execute:
    
  ```PowerShell
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    Para outros exemplos e parâmetros, consulte [Get-CsEffectiveTenantDialPlan](/powershell/module/skype/get-cseffectivetenantdialplan).
    
- Para testar as configurações efetivas de um plano de discagem, execute:
    
  ```PowerShell
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    Para outros exemplos e parâmetros, consulte [Test-CsEffectiveTenantDialPlan](/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).
    
#### <a name="using-a-powershell-script"></a>Usando um script do PowerShell

Execute isso para excluir uma regra de normalização associada a um plano de discagem de locatário sem precisar excluir primeiro o plano de discagem do locatário:
```PowerShell
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
Execute isso para adicionar a seguinte regra de normalização ao plano de discagem de locatário existente chamado RedmondDialPlan.
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
Execute isso para remover a seguinte regra de normalização do plano de discagem de locatário existente chamado RedmondDialPlan.
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

Execute o seguinte quando quiser examinar também as regras de normalização existentes, determinar qual delas você deseja excluir e, em seguida, usar seu índice para removê-la. A matriz de regras de normalização começa com o índice 0. Queremos remover a regra de normalização de 3 dígitos, portanto, esse é o índice 1.
  
```PowerShell
Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules
Description         : 4-digit
Pattern             : ^(\\d{4})$
Translation         : +1426666$1
Name                : NR2
IsInternalExtension : False

Description         : 3-digit
Pattern             : ^(\\d{3})$
Translation         : +14255551$1
Name                : NR12
IsInternalExtension : False

$nr1=(Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules[1]
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

Execute isso para encontrar todos os usuários que foram concedidos ao plano de discagem de locatário RedmondDialPlan.
  
```PowerShell
Get-CsOnlineUser | Where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

Execute isso para remover qualquer TenantDialPlan atribuído de todos os usuários que tenham um HostingProvider de sipfed.online.lync.com.
```PowerShell
Get-CsOnlineUser -Filter {HostingProvider -eq "sipfed.online.lync.com"} | Grant-CsTenantDialPlan -policyname $null
```

Execute-os para adicionar o plano de discagem local existente chamado OPDP1 como um plano de discagem de locatário para sua organização. Primeiro, você precisa salvar o plano de discagem local em um arquivo .xml e usá-lo para criar o novo plano de discagem de locatário.
  
Execute isso para salvar o plano de discagem local no arquivo .xml local.
  
```PowerShell
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

Execute isso para criar o novo plano de discagem de locatário.
  
```PowerShell
$DPFileName = "dialplan.xml"
$dp = Import-Clixml $DPFileName
$NormRules = @()
ForEach($nr in $dp.NormalizationRules)
{
 $id1 = "Global/" + $nr.Name
 $nr2 = New-CsVoiceNormalizationRule -Identity $id1 -Description $nr.Description -Pattern $nr.Pattern -Translation $nr.Translation -IsInternalExtension $nr.IsInternalExtension -InMemory
 $NormRules += $nr2
}
New-CsTenantDialPlan -Identity $dp.SimpleName -ExternalAccessPrefix $dp.ExternalAccessPrefix -Description $dp.Description -OptimizeDeviceDialing $dp.OptimizeDeviceDialing -SimpleName $dp.SimpleName -NormalizationRules $NormRules
```
    
## <a name="related-topics"></a>Tópicos relacionados

- [O que são planos de discagem?](what-are-dial-plans.md)
- [Perguntas comuns sobre a transferência de números de telefone](./phone-number-calling-plans/port-order-overview.md)
- [Diferentes tipos de números de telefone usados para Planos de Chamadas](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Gerenciar os números de telefone de sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Termos e condições das Chamadas de Emergência](emergency-calling-terms-and-conditions.md)
- [Rótulo de aviso de isenção de responsabilidade de chamada de emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
