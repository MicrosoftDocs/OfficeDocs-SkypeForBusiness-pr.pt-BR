---
title: "Criar e gerenciar planos de discagem"
ms.author: tonysmit
author: tonysmit
ms.date: 11/10/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: 7af17c94-5f8f-4452-ae1d-01f495b4dc94
description: "Learn how to create calling dial plans (PSTN Calling dial plans) in Office 365 and how to manage them. "
---

# Criar e gerenciar planos de discagem

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o [aviso de isenção de responsabilidade](7af17c94-5f8f-4452-ae1d-01f495b4dc94.md#MT_Footer). Para sua referência, veja a versão em inglês deste artigo [aqui](https://support.office.com/en-us/article/7af17c94-5f8f-4452-ae1d-01f495b4dc94). 
  
Depois de ter planejado os planos de discagem para a sua organização e descobriu a todas as regras de normalização que precisam ser criados para o roteamento de chamada, você precisará usar o Windows PowerShell para criar os planos de discagem e faça as alterações de configuração.
  
> [!NOTE]
> O Centro de administração do Skype for Business não pode ser usado para criar e gerenciar planos de discagem. 
  
## Verificar e iniciar o PowerShell Remoto

 **Verifique se está executando o Windows PowerShell 3.0 ou versão superior**
  
1. Para verificar se você está executando a versão 3.0 ou superior: **Menu Iniciar** > **Windows PowerShell**.
    
2. Verifique a versão digitando  _Get-Host_ na janela do **Windows PowerShell**.
    
3. Se você não tiver a versão 3.0 ou superior, deverá baixar e instalar as atualizações do Windows PowerShell. Confira [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para baixar e atualizar o Windows PowerShell para a versão 4.0. Reinicie o computador quando for solicitado.
    
4. Você também precisará instalar o módulo do Windows PowerShell para Skype for Business Online, que permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo do Windows PowerShell para o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se for solicitado, reinicie o seu computador.
    
Se precisar saber mais, confira [Conectar-se a todos os serviços do Office 365 usando uma única janela do Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).
  
 **Iniciar uma sessão do Windows PowerShell**
  
1. No **Menu Iniciar** > **Windows PowerShell**.
    
2. Na janela do **Windows PowerShell**, conecte-se à organização do Office 365 executando:
    
    > [!NOTE]
    > Execute o comando **Import-Module** apenas quando usar o módulo do Windows PowerShell do Skype for Business Online pela primeira vez.
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  ```

> 
  ```
  $credential = Get-Credential
  ```

> 
  ```
  $session = New-CsOnlineSession -Credential $credential
  ```

> 
  ```
  Import-PSSession $session
  ```

Confira mais informações sobre como iniciar o Windows PowerShell em [Conectar-se a todos os serviços do Office 365 usando uma única janela do Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) ou[Conectar-se ao Skype for Business Online usando o Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).
  
## Criar e gerenciar planos de discagem

Você pode usar um único cmdlet ou um script do PowerShell para criar e gerenciar os planos de discagem de locatário.
  
### Usar cmdlets únicos

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

    Para obter outros exemplos e parâmetros, veja [Set-CsTenantDialPlan](https://technet.microsoft.com/library/mt775023.aspx).
    
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
    
- Para ver as configurações de plano de discagem eficaz, execute:
    
  ```
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    Para obter outros exemplos e parâmetros, veja [Get-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775022.aspx).
    
- Para testar as configurações efetivas de um plano de discagem, execute:
    
  ```
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255551234 -Identity 1849827b-a810-40a8-8f77-e94250d4680b_US_TenantDialPlanRedmond
  ```

    Para obter outros exemplos e parâmetros, veja [Test-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775025.aspx).
    
### Usar um script do PowerShell

Execute este script para excluir uma regra de normalização que esteja associada a um plano de discagem de locatário sem precisar excluir primeiro o plano de discagem de locatário:
  
```
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
```

```
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
```

```
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
```

```
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
```

```
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```

Execute esse recurso para adicionar a seguinte regra de normalização ao plano de discagem de locatário existente denominado RedmondDialPlan.
  
```
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
```

```
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```

Execute este script para remover a seguinte regra de normalização do plano de discagem de locatário existente chamado RedmondDialPlan.
  
```
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
```

```
Set-CsTenantDialPlan -Identity DP1 -NormalizationRules @{remove=$nr1}
```

Execute o seguinte quando quiser também examinar as regras de normalização existente, determinar qual deles você deseja excluir e, em seguida, usar seu índice para removê-lo. Matriz de regras de normalização começa com índice 0. Podemos gostaria de remover a regra de normalização de 3 dígitos, forma que é o índice 1.
  
```
Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules
```

```
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
```

```
$nr1=(Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules[1]
```

```
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

Execute este script para localizar todos os usuários que receberam o plano de discagem de locatário RedmondDialPlan.
  
```
Get-CsOnlineuser | where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

Execute essas para adicionar que nomeado OPDP1 como um plano de discagem de locatário para sua organização de plano de discagem do existente no local. Você precisa primeiro salvar as locais discar plano para um arquivo. XML e, em seguida, usá-lo para criar o novo plano de discagem de locatário.
  
Execute esse para salvar o plano de discagem locais para o arquivo. XML.
  
```
$DPName = "OPDP1"
```

```
$DPFileName = "dialplan.xml"
```

```
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

Execute este script para criar o novo plano de discagem de locatário.
  
```
$DPFileName = "dialplan.xml"
```

```
$DP = Import-Clixml $DPFileName
```

```
$NormRules = @()
```

```
ForEach($nr in $dp.NormalizationRules)
```

```
{
```

```
 $id1 = "Global/" +$nr.Name
```

```
$nr2 = New-CsVoiceNormalizationRule -Identity $id1 -Description $nr.Description -Pattern $nr.Pattern -Translation $nr.Translation  -IsInternalExtension $nr.IsInternalExtension -InMemory
```

```
$NormRules += $nr2
```

```
}
```

```
New-CsTenantDialPlan -Identity $dp.SimpleName -ExternalAccessPrefix $dp.ExternalAccessPrefix -Description $dp.Description -OptimizeDeviceDialing $dp.OptimizeDeviceDialing -SimpleName $dp.SimpleName -NormalizationRules $NormRules
```

## Quer saber mais sobre o Windows PowerShell?

- O Windows PowerShell serve para o gerenciamento de usuários e do que os usuários podem ou não podem fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis motivos para usar o Windows PowerShell para gerenciar o Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Aviso de Isenção de Tradução Automática**: Este artigo foi traduzido por computador, sem intervenção humana. A Microsoft oferece essas traduções automáticas para ajudar as pessoas que não falam inglês a aproveitar os textos escritos sobre produtos, serviços e tecnologias da Microsoft. Como este artigo foi traduzido automaticamente, é possível que contenha erros de vocabulário, sintaxe ou gramática. 
  

