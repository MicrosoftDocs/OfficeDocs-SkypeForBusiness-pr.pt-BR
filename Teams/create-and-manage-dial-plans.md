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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Calling Plans
description: Saiba como criar e gerenciar planos de discagem de chamada PSTN (planos de discagem de chamada PSTN) e como gerenciá-los.
ms.openlocfilehash: e61fb8c2ffd5c13816ff0093fc117dfadb251594
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41707256"
---
# <a name="create-and-manage-dial-plans"></a>Criar e gerenciar planos de discagem

Depois de planejar os planos de discagem para a sua organização e descobrir todas as regras de normalização que precisam ser criadas para o encaminhamento de chamadas, você estará pronto para criar os planos de discagem. Você pode usar o centro de administração do Microsoft Teams ou o Windows PowerShell para criar e gerenciar planos de discagem.  

## <a name="using-the-microsoft-teams-admin-center"></a>Usar o centro de administração do Microsoft Teams

### <a name="create-a-dial-plan"></a>Criar um plano de discagem

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para**plano de discagem**por **voz** > .
2. Clique em **Adicionar**e, em seguida, insira um nome e uma descrição para o plano de discagem.
    ![Captura de tela mostrando a página Adicionar para criar um plano de discagem](media/create-dial-plan.png)
3. Em **detalhes do plano de discagem**, especifique um prefixo de discagem externo se os usuários precisarem discar um ou mais dígitos iniciais adicionais (por exemplo, 9) para obter uma linha externa. Para fazer isso:
    1. Na caixa **prefixo de discagem externo** , insira um prefixo de discagem externo. O prefixo pode ter até quatro caracteres (#, * e 0-9).
    2. Ative a **discagem otimizada de dispositivo**. Se você especificar um prefixo de discagem externo, também deverá ativar essa configuração para aplicar o prefixo para que as chamadas possam ser feitas fora de sua organização.
4. Em **regras de normalização**, configure e associe uma ou mais [regras de normalização](what-are-dial-plans.md#normalization-rules) para o plano de discagem. Cada plano de discagem deve ter pelo menos uma regra de normalidade associada a ele.  Para fazer isso, siga um ou mais destes procedimentos:
    - Para criar uma nova regra de normalização e associá-la ao plano de discagem, clique em **Adicionar**e, em seguida, defina a regra.
    - Para editar uma regra de normalização que já esteja associada ao plano de discagem, selecione a regra clicando à esquerda do nome da regra e, em seguida, clique em **Editar**. Faça as alterações desejadas e clique em **salvar**.
    - Para remover uma regra de normalização do plano de discagem, selecione a regra clicando à esquerda do nome da regra e, em seguida, clique em **remover**.
5. Organize as regras de normalização na ordem desejada. Clique em **mover para cima** ou mover para **baixo** para alterar a posição das regras na lista.

    > [!NOTE]
    > O Microsoft Teams percorre a lista de regras de normalização do início e usa a primeira regra que corresponde ao número discado. Se você configurar um plano de discagem para que um número discado possa corresponder a mais de uma regra de normalização, certifique-se de que as regras mais restritivas sejam classificadas acima das menos restritivas.

6. Clique em **Salvar**.
7. Se você quiser testar o plano de discagem, em **testar plano de discagem**, insira um número de telefone e clique em **testar**.

### <a name="edit-a-dial-plan"></a>Editar um plano de discagem

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para**plano de discagem**por **voz** > .
2. Selecione o plano de discagem clicando à esquerda do nome do plano de discagem e, em seguida, clique em **Editar**.
3. Faça as alterações desejadas e clique em **salvar**.

### <a name="add-users-to-a-dial-plan"></a>Adicionar usuários a um plano de discagem

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para**plano de discagem**por **voz** > .
2. Selecione o plano de discagem clicando à esquerda do nome do plano de discagem.
3. Escolha **Gerenciar usuários**.
4. No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e marque **Adicionar**. Repita esta etapa para cada usuário que você deseja adicionar.
5. Quando tiver terminado de adicionar usuários, selecione **aplicar**.

## <a name="using-powershell"></a>Usando o PowerShell
  
### <a name="verify-and-start-remote-powershell"></a>Verificar e iniciar o PowerShell remoto

 **Verifique se você está executando o Windows PowerShell versão 3,0 ou posterior**
  
1. Para verificar se você está executando a versão 3,0 ou superior: **menu** > iniciar**Windows PowerShell**.
    
2. Verifique a versão digitando  _Get-Host_ na janela do **Windows PowerShell**.
    
3. Se você não tiver a versão 3,0 ou posterior, baixe e instale atualizações para o Windows PowerShell. Consulte [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) para baixar e atualizar o Windows PowerShell para a versão 4,0. Reinicie o computador quando for solicitado.
    
4. Você também precisará instalar o módulo do Windows PowerShell para o Skype for Business online que permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business online. Você pode baixar esse módulo, que tem suporte apenas em computadores de 64 bits, no [módulo do Windows PowerShell para Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=294688). Reinicie o computador se for solicitado.
    
Para saber mais, confira [conectar-se a todos os serviços do Office 365 em uma única janela do Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).
  
 **Iniciar uma sessão do Windows PowerShell**
  
1. Clique em **Iniciar** > o**Windows PowerShell**.
    
2. Na janela do **Windows PowerShell**, conecte-se à organização do Office 365 executando:
    
    > [!NOTE]
    > [!OBSERVAçãO] Execute o comando **Import-Module** apenas quando usar o módulo do Windows PowerShell do Skype for Business Online pela primeira vez.
  

    ```PowerShell
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
    ```
  
### <a name="create-and-manage-your-dial-plans"></a>Criar e gerenciar seus planos de discagem

Você pode usar um único cmdlet ou um script do PowerShell para criar e gerenciar planos de discagem de locatário.
  
#### <a name="using-single-cmdlets"></a>Usando cmdlets únicos

- Para criar um novo plano de discagem, execute:
    
  ```PowerShell
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    Para obter outros exemplos e parâmetros, veja [New-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/new-cstenantdialplan).
    
- Para editar as configurações de um plano de discagem existente, execute:
    
  ```PowerShell
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    Para obter outros exemplos e parâmetros, consulte [set-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/set-cstenantdialplan).
    
- Para adicionar usuários a um plano de discagem, execute:
    
  ```PowerShell
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    Para obter outros exemplos e parâmetros, veja [Grant-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-cstenantdialplan).
    
- Para exibir as configurações em um plano de discagem, execute:
    
  ```PowerShell
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    Para obter outros exemplos e parâmetros, veja [Get-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cstenantdialplan?view=skype-ps).
    
- Para excluir um plano de discagem, execute:
    
  ```PowerShell
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    Para obter outros exemplos e parâmetros, veja [Remove-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).
    
- Para ver as configurações do plano de discagem efetivo, execute:
    
  ```PowerShell
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    Para obter outros exemplos e parâmetros, veja [Get-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cseffectivetenantdialplan).
    
- Para testar as configurações efetivas de um plano de discagem, execute:
    
  ```PowerShell
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    Para obter outros exemplos e parâmetros, veja [Test-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).
    
#### <a name="using-a-powershell-script"></a>Usando um script do PowerShell

Execute isso para excluir uma regra de normalização associada a um plano de discagem de locatário sem precisar excluir o plano de discagem de locatário primeiro:
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
Execute esta regra para remover a seguinte regra de normalização do plano de discagem de locatário existente chamado RedmondDialPlan.
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

Execute o seguinte quando você deseja examinar também as regras de normalização existentes, determinar qual delas deseja excluir e, em seguida, use o índice para removê-la. A matriz de regras de normalização começa com o índice 0. Gostaríamos de remover a regra de normalização de 3 dígitos, para que seja o índice 1.
  
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

Execute este procedimento para localizar todos os usuários que receberam o plano de discagem de locatários do RedmondDialPlan.
  
```PowerShell
Get-CsOnlineUser | Where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

Execute isso para remover qualquer TenantDialPlan atribuído de todos os usuários que tenham um hostprovider do sipfed.online.lync.com.
```PowerShell
Get-CsOnlineUser -Filter {HostingProvider -eq “sipfed.online.lync.com”} | Grant-CsTenantDialPlan -policyname $null
```

Execute-os para adicionar o plano de discagem local existente chamado OPDP1 como um plano de discagem de locatário para a sua organização. Primeiro, você precisa salvar o plano de discagem local em um arquivo. xml e usá-lo para criar o novo plano de discagem de locatário.
  
Execute isso para salvar o plano de discagem local para o arquivo. xml.
  
```PowerShell
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

Execute este procedimento para criar o novo plano de discagem de locatário.
  
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
- [Perguntas comuns sobre a transferência de números de telefone](transferring-phone-numbers-common-questions.md)
- [Diferentes tipos de números de telefone usados para Planos de Chamadas](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Gerenciar os números de telefone de sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Termos e condições das Chamadas de Emergência](emergency-calling-terms-and-conditions.md)
- [Rótulo de isenção de isenção de emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
