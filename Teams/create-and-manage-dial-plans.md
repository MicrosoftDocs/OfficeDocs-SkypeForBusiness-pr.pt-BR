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
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 'Saiba como criar planos de discagem de chamada (planos de discagem de chamada PSTN) no Office 365 e como gerenciá-los. '
ms.openlocfilehash: 5254a2d63abeffa0b3452ed309d49272affcaf05
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221918"
---
# <a name="create-and-manage-dial-plans"></a>Criar e gerenciar planos de discagem

Depois de planejar os planos de discagem para a sua organização e descobrir todas as regras de normalização que precisam ser criadas para o encaminhamento de chamadas, você precisará usar o Windows PowerShell para criar os planos de discagem e fazer alterações de configuração.
  
> [!NOTE]
> O centro de administração do Skype for Business não pode ser usado para criar e gerenciar planos de discagem. 
  
## <a name="verifying-and-starting-remote-powershell"></a>Verificando e iniciando o PowerShell remoto

 **Verifique se está executando o Windows PowerShell 3.0 ou versão superior**
  
1. Para verificar se você está executando a versão 3.0 ou superior: **Menu Iniciar** > **Windows PowerShell**.
    
2. Verifique a versão digitando  _Get-Host_ na janela do **Windows PowerShell**.
    
3. Se você não tiver a versão 3.0 ou superior, deverá baixar e instalar as atualizações do Windows PowerShell. Consulte [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) para baixar e atualizar o Windows PowerShell para a versão 4,0. Reinicie o computador quando for solicitado.
    
4. Você também precisará instalar o módulo do Windows PowerShell para Skype for Business Online, que permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo do Windows PowerShell para o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se for solicitado, reinicie o seu computador.
    
Se precisar saber mais, confira [Conectar-se a todos os serviços do Office 365 usando uma única janela do Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).
  
 **Iniciar uma sessão do Windows PowerShell**
  
1. No **Menu Iniciar** > **Windows PowerShell**.
    
2. Na janela do **Windows PowerShell**, conecte-se à organização do Office 365 executando:
    
    > [!NOTE]
    > [!OBSERVAçãO] Execute o comando **Import-Module** apenas quando usar o módulo do Windows PowerShell do Skype for Business Online pela primeira vez.
  
> 
>   ```
>     Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
>     $credential = Get-Credential
>     $session = New-CsOnlineSession -Credential $credential
>     Import-PSSession $session
>   ```

Se você quiser mais informações sobre como iniciar o Windows PowerShell, consulte [conectar-se a todos os serviços do Office 365 em uma única janela do Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou conectar-se [ao Skype for Business online usando o Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).
  
## <a name="creating-and-managing-your-dial-plans"></a>Criar e gerenciar seus planos de discagem

Você pode usar um único cmdlet ou um script do PowerShell para criar e gerenciar planos de discagem de locatário.
  
### <a name="using-single-cmdlets"></a>Usando cmdlets únicos

- Para criar um novo plano de discagem, execute:
    
  ```
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    Para obter outros exemplos e parâmetros, veja [New-CsTenantDialPlan](https://technet.microsoft.com/library/mt775026.aspx).
    
- Para fazer alterações de configuração em um plano de discagem existente, execute:
    
  ```
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    Para obter outros exemplos e parâmetros, consulte [set-CsTenantDialPlan](https://technet.microsoft.com/library/mt775023.aspx).
    
- Para adicionar usuários a um plano de discagem, execute:
    
  ```
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    Para obter outros exemplos e parâmetros, veja [Grant-CsTenantDialPlan](https://technet.microsoft.com/library/mt775021.aspx).
    
- Para exibir as configurações em um plano de discagem, execute:
    
  ```
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    Para obter outros exemplos e parâmetros, veja [Get-CsTenantDialPlan](https://technet.microsoft.com/library/mt775024.aspx).
    
- Para excluir um plano de discagem, execute:
    
  ```
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    Para obter outros exemplos e parâmetros, veja [Remove-CsTenantDialPlan](https://technet.microsoft.com/library/mt775020.aspx).
    
- Para ver as configurações do plano de discagem efetivo, execute:
    
  ```
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    Para obter outros exemplos e parâmetros, veja [Get-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775022.aspx).
    
- Para testar as configurações efetivas de um plano de discagem, execute:
    
  ```
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255551234 -Identity 1849827b-a810-40a8-8f77-e94250d4680b_US_TenantDialPlanRedmond
  ```

    Para obter outros exemplos e parâmetros, veja [Test-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775025.aspx).
    
### <a name="using-a-powershell-script"></a>Usando um script do PowerShell

Execute isso para excluir uma regra de normalização associada a um plano de discagem de locatário sem precisar excluir o plano de discagem de locatário primeiro:
```
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
Execute isso para adicionar a seguinte regra de normalização ao plano de discagem de locatário existente chamado RedmondDialPlan.
```
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
Execute esta regra para remover a seguinte regra de normalização do plano de discagem de locatário existente chamado RedmondDialPlan.
```
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity DP1 -NormalizationRules @{remove=$nr1}
```

Execute o seguinte quando você deseja examinar também as regras de normalização existentes, determinar qual delas deseja excluir e, em seguida, use o índice para removê-la. A matriz de regras de normalização começa com o índice 0. Gostaríamos de remover a regra de normalização de 3 dígitos, para que seja o índice 1.
  
```
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

$nr1=(Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules[Number 1]
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

Execute este procedimento para localizar todos os usuários que receberam o plano de discagem de locatários do RedmondDialPlan.
  
```
Get-CsOnlineuser | where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

Execute este procedimento para excluir PolicyName para todos os usuários que têm o Hostingprovider sipfed.online.lync.com.
```
Get-CsOnlineUser -Filter {HostingProvider -eq “sipfed.online.lync.com”} | Grant-CsTenantDialPlan -policyname $null
```

Execute-os para adicionar o plano de discagem local existente chamado OPDP1 como um plano de discagem de locatário para a sua organização. Primeiro, você precisa salvar o plano de discagem local em um arquivo. xml e usá-lo para criar o novo plano de discagem de locatário.
  
Execute isso para salvar o plano de discagem local para o arquivo. xml.
  
```
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

Execute este procedimento para criar o novo plano de discagem de locatário.
  
```
$DPFileName = "dialplan.xml"
$DP = Import-Clixml $DPFileName
$NormRules = @()
ForEach($nr in $dp.NormalizationRules)
{
 $id1 = "Global/" +$nr.Name
$nr2 = New-CsVoiceNormalizationRule -Identity $id1 -Description $nr.Description -Pattern $nr.Pattern -Translation $nr.Translation  -IsInternalExtension $nr.IsInternalExtension -InMemory
$NormRules += $nr2
}
New-CsTenantDialPlan -Identity $dp.SimpleName -ExternalAccessPrefix $dp.ExternalAccessPrefix -Description $dp.Description -OptimizeDeviceDialing $dp.OptimizeDeviceDialing -SimpleName $dp.SimpleName -NormalizationRules $NormRules
```
## <a name="want-to-know-more-about-windows-powershell"></a>Quer saber mais sobre o Windows PowerShell?

- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o centro de administração do Microsoft 365, como quando você está usando alterações de configuração para muitos usuários de uma só vez. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Tópicos relacionados
[Perguntas comuns sobre a transferência de números de telefone](transferring-phone-numbers-common-questions.md)

[Diferentes tipos de números de telefone usados para Planos de Chamadas](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gerenciar os números de telefone de sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Termos e condições das Chamadas de Emergência](emergency-calling-terms-and-conditions.md)

[Skype for Business Online: etiqueta de aviso de isenção de responsabilidade por Chamadas de Emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 
