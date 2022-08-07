---
title: Migrar de licenças do Business Voice para o Telefone do Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba como alterar suas licenças do Business Voice para licenças do Telefone do Teams.
appliesto:
- Microsoft Teams
ms.collection:
- M365-voice
ms.openlocfilehash: 6e7622e4b78e57f45209b90a525eb5fefbe8cd66
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271226"
---
# <a name="move-from-business-voice-to-teams-phone-licenses"></a>Migrar de licenças do Business Voice para o Telefone do Teams

Até o final de junho de 2022, o Business Voice será desativado, portanto, recomendamos que as empresas mudem para [licenças Telefonia do Microsoft Teams com plano de chamadas pacote](https://techcommunity.microsoft.com/t5/small-and-medium-business-blog/teams-phone-with-calling-plan-available-in-33-markets-on-january/ba-p/2967643).

O Business Voice empacotou as três licenças de complemento do Teams a seguir:

- **Telefonia do Microsoft Teams** para um Sistema de Telefonia baseado em nuvem no Microsoft Teams.
- **Audioconferência** para conferência discada e discada para reuniões.
- **Planos de Chamadas da Microsoft** para chamadas domésticas para conectividade PSTN (Rede Telefônica Pública Comunada).

Os clientes existentes do Business Voice não serão automaticamente transferidos para o novo modelo de licenciamento.

Este artigo destina-se a administradores de TI que precisam alterar suas licenças do Business Voice para licenças de Telefonia do Microsoft Teams e audioconferência, mantendo os mesmos recursos.

> [!WARNING]
> Siga de perto as instruções deste artigo. Se as instruções dizem para NÃO selecionar o **botão** Salvar, não selecione o **botão** Salvar.
>
> Salvar prematuramente pode resultar na perda de atribuições de número de telefone, planos de discagem, atendedores automáticos e filas de chamadas.

## <a name="acquire-new-licenses"></a>Adquirir novas licenças

Antes de substituir as licenças do Business Voice, primeiro você precisa comprar licenças de substituição para seus usuários.

Você precisará de licenças para fornecer estes recursos:

- Audioconferência
- Sistema de Telefonia baseado em nuvem
- Conectividade PSTN

Use a tabela a seguir para determinar quais licenças comprar com base em suas necessidades:

| Plano de licença antigo | Plano de licença recomendado | Descrição |
| ---------------- | ------------------------ | ----------- |
| Business Voice com Plano de Chamadas | Telefone do Teams com Plano de Chamada e Audioconferência do Microsoft Teams com discagem para EUA/CAN | Fornece recursos do Sistema de Telefonia baseado em nuvem, um Plano de Chamadas Domésticas com a Microsoft como seu provedor PSTN e recursos de discagem e discagem para os participantes da reunião organizados por um usuário licenciado. |
| Business Voice sem Plano de Chamada | Telefonia do Teams Padrão e Audioconferência do Microsoft Teams com discagem para EUA/CAN | Fornece recursos do Sistema de Telefonia baseado em nuvem que podem ser combinados com um plano de chamada de terceiros com um provedor [PSTN](pstn-connectivity.md) usando o Operator Connect ou o Roteamento Direto e recursos de discagem e discagem para os participantes da reunião organizados por um usuário licenciado. |

## <a name="how-to-update-licenses"></a>Como atualizar licenças

Você tem quatro maneiras de atualizar suas licenças:

- Atualização de licença de usuário único por meio Centro de administração do Microsoft 365
- Atualização de licença de usuário em massa por meio Centro de administração do Microsoft 365
- Atualização de licença de usuário em massa usando um script do PowerShell
- Atualização de licença de usuário em massa usando o licenciamento baseado em grupo do Azure

# <a name="option-1-single-user-in-admin-center"></a>[Opção 1: Usuário único no centro de administração](#tab/single-user)

### <a name="option-1-single-user-license-update-via-microsoft-365-admin-center"></a>Opção 1: Atualização de licença de usuário único via Centro de administração do Microsoft 365

Para atualizar um único usuário, você pode usar o Centro de administração do Microsoft 365.

1. Vá para [admin.microsoft.com](https://admin.microsoft.com/) e entre com as credenciais de administrador do locatário.
1. Navegue **até Usuários** > **Ativos** e selecione o usuário desejado.
1. Selecione **Gerenciar licenças de produto** na barra de ferramentas da lista.
1. Na tela **Licenças e aplicativos** , desmarque a licença do Business Voice.
    > [!IMPORTANT]
    > NÃO salve as alterações ainda. Se você salvar as alterações sem adicionar as novas licenças, a conta de usuário será desprovisionada e o número de telefone não será atribuído.
1. Depois de desmarcar o Business Voice, verifique as novas licenças de Telefone e Audioconferência do Teams.
1. Agora você pode salvar suas alterações com segurança selecionando **Salvar alteração**.

As licenças do usuário serão atualizadas e não devem afetar a disponibilidade do serviço.

# <a name="option-2-bulk-users-in-admin-center"></a>[Opção 2: Usuários em massa no centro de administração](#tab/bulk-users-admin-center)

### <a name="option-2-bulk-user-license-update-via-microsoft-365-admin-center"></a>Opção 2: Atualização de licença de usuário em massa via Centro de administração do Microsoft 365

Para atualizar as licenças de vários usuários em massa, você pode usar o Centro de administração do Microsoft 365. Os usuários selecionados terão a mesma atribuição de plano de licença.

1. Vá para [admin.microsoft.com](https://admin.microsoft.com/) e entre com as credenciais de administrador do locatário.
1. Navegue **até Usuários** > **Ativos** e selecione todos os usuários desejados.  
1. Selecione **Gerenciar licenças de produto** na barra de ferramentas da lista.
1. No prompt **O que você gostaria de fazer com as licenças** para esses usuários? Selecione a opção Substituir: Cancelar a atribuição de **licenças existentes** e atribuir novas.
    > [!IMPORTANT]
    > A **opção** Substituir removerá todas as licenças existentes para os usuários selecionados.  Como resultado, você precisará selecionar o estado de licenciamento desejado para os usuários, incluindo quaisquer outras licenças em uso, como Microsoft 365 Business Premium.
    >
    > Além disso, se os usuários selecionados tiverem configurações de licença base diferentes, eles serão substituídos pelas licenças selecionadas, o que pode afetar outras áreas do Microsoft 365.
    >
    > Para locatários com uma configuração de licença mista, é recomendável usar a opção [de atualização em massa com um script do PowerShell](#option-3-bulk-user-license-update-using-a-powershell-script).
1. Na tela **Licenças e aplicativos** , desmarque a licença do Business Voice.
    > [!IMPORTANT]
    > NÃO salve as alterações ainda. Se você salvar as alterações sem adicionar as novas licenças, as contas dos usuários selecionados serão desprovisionadas e o número de telefone não será atribuído.
1. Depois de desmarcar o Business Voice, verifique as novas licenças de Telefone e Audioconferência do Teams.
1. Agora você pode salvar suas alterações com segurança selecionando **Salvar alteração**.
  As licenças dos usuários serão atualizadas e não devem afetar a disponibilidade do serviço.

# <a name="option-3-bulk-users-via-powershell"></a>[Opção 3: Usuários em massa por meio do PowerShell](#tab/powershell)

### <a name="option-3-bulk-user-license-update-using-a-powershell-script"></a>Opção 3: Atualização de licença de usuário em massa usando um script do PowerShell

Substituir o plano de licença do Business Voice usando um script do PowerShell é uma solução eficiente para a maioria dos cenários.  

Para usar esse método, você seguirá estas etapas gerais:

1. Obtenha os identificadores de plano de licença específicos do locatário de suas licenças atuais do Business Voice.
1. Obtenha os identificadores específicos do locatário dos novos planos de licença de Audioconferência e Telefone do Teams.
1. Valide se os novos planos de licença têm os mesmos planos de serviço que a licença atual do Business Voice.
1. Localize usuários de locatário licenciados para o Business Voice (ou modifique o script para incluir um filtro para selecionar um subconjunto de usuários, se desejado).
1. Atualize a configuração de licença dos usuários com planos de Telefone e Audioconferência do Teams.

> [!IMPORTANT]
> O script fornecido é um exemplo de código. O script não deve ser copiado como está e executado em um locatário de produção sem teste, validação e personalização para seu ambiente específico.

### <a name="how-to-bulk-update-licenses-using-powershell"></a>Como atualizar licenças em massa usando o PowerShell

1. Instale e importe o módulo do PowerShell do AzureAD.

    ```powershell
    Install-Module AzureAD
    Import-Module AzureAD
    ```

1. Conecte-se ao seu locatário do Microsoft 365 e forneça as credenciais de administrador do locatário.

    ```powershell
    Connect-AzureAD
    ```

1. Use o commandlet a seguir para listar todos os pacotes de licença no locatário.

    ```powershell
    Get-AzureADSubscribedSku
    ```

1. Use a tabela a seguir para identificar o plano de licença de complemento do Business Voice que será substituído.

    | Código de SKU | Tipo de licença |
    | -------- | ------------ |
    | BUSINESS_VOICE_MED | Business Voice com Plano de Chamadas – Canadá |
    | BUSINESS_VOICE | Business Voice com Plano de Chamada – Reino Unido |
    | BUSINESS_VOICE_MED2_TELCO | Business Voice com Plano de Chamada – EUA |
    | BUSINESS_VOICE_DIRECTROUTING | Business Voice sem Plano de Chamada |
    | BUSINESS_VOICE_DIRECTROUTING_MED | Business Voice sem Plano de Chamada – EUA |

    > [!NOTE]
    > O script fornecido neste documento pressupõe que você tenha um único Código de SKU para Business Voice em seu locatário.  
    >
    > Se você tiver várias SKUs do Business Voice, precisará ajustar o script ou executar várias vezes, uma vez para cada código de SKU.

1. Crie uma variável do PowerShell chamada `$skuSourceBV`.
    1. Substitua o rótulo pelo Código `SkuPartNumber` de SKU do Business Voice do locatário.
    1. Neste exemplo, estamos usando o código `BUSINESS_VOICE_MED2_TELCO` SKU.

    ```powershell
    $skuSourceBV = Get-AzureADSubscribedSku  | where {$_.SkuPartNumber -eq "BUSINESS_VOICE_MED2_TELCO"}
    ```

1. Use a tabela a seguir para identificar seus novos Códigos de SKU de licença de Audioconferência e Telefone do Teams.

    | Código de SKU | Tipo de licença |
    | -------- | ------------ |
    | MCOTEAMS_ESSENTIALS | Telefonia do Teams com Plano de Chamadas |
    | MCOEV | Telefonia do Teams Padrão (sem plano de chamada) |
    | MCOMEETADV | Audioconferência |
    | Microsoft_Teams_Audio_Conferencing_select_dial_out | Audioconferência do Microsoft Teams Selecionar Discagem |

1. Crie variáveis do PowerShell para armazenar os códigos de SKU exclusivos de Telefone e Audioconferência do Teams.
    1. Substitua o rótulo por códigos `SkuPartNumber` de SKU disponíveis em seu locatário.
    1. Neste exemplo, estamos usando os códigos e `MCOTEAM_ESSENTIALS` `MCOMEETADV` SKU.

        ```powershell
        $skuTargetTPCP = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "MCOTEAMS_ESSENTIALS"}
        $skuTargetAC = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "MCOMEETADV"} 
        ```

1. Execute esse script para coletar os dados necessários do Plano de Serviço do SKU de origem em objetos exclusivos.

     ```powershell
     $servicePlan_Phone = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*EV*"}
    $servicePlan_AC = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*MEET*"}
    $servicePlan_CP = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*PSTN*"}
    ```

1. Antes de continuar, valide se o SKU de origem (Business Voice) e os SKUs de destino (Telefone e Audioconferência do Teams) têm os mesmos Planos de Serviço incluídos.
    1. Uma incompatibilidade pode disparar uma alteração de licença que pode interromper os serviços de voz e audioconferência dos usuários.
    2. Crie variáveis para validar se todos os Planos de Serviço no SKU de origem serão substituídos pelo mesmo plano de serviço de destino.

        ```powershell
        $validated_TP = $false
        $validated_AC = $false
        $validated_CP = $false
        ```

    3. Se a licença do Business Voice de origem não tiver nenhum Plano de Chamada incluído, não verifique se ele está incluído.

        ```powershell
        if($skuSourceBV.ServicePlans.Count -eq 2) { $validated_CP = $true }
        ```

    4. Verifique se todos os planos de serviço no SKU de origem têm um plano de serviço correspondente no SKU de destino.

        ```powershell
        For ($i=0; $i -le $skuSourceBV.ServicePlans.Count ; $i++) {
        if($validated_TP -eq $false) { if($skuTargetTP.ServicePlans.Contains($servicePlan_Phone)) { $validated_TP = $true } }
        if($validated_AC -eq $false) { if($skuTargetAC.ServicePlans.Contains($servicePlan_AC)) { $validated_AC = $true } }
        if($validated_CP -eq $false) { if($skuTargetTP.ServicePlans.Contains($servicePlan_CP)) { $validated_CP = $true } }
        }
        ```

    5. Se houver um plano de serviço ausente no SKU de destino, você poderá interromper a disponibilidade do serviço para os usuários e o script deverá parar o processamento.

        ```powershell
        if($validated_TP -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Teams Phone." ; exit }
        if($validated_AC -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Audio Conferencing." ; exit }
        if($validated_CP -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Calling Plan." ; exit }
        ```

1. Se tudo estiver bem, prepare os Objetos do PowerShell para executar as operações de atualização em objetos do usuário. Use o `AssignedLicenses` objeto para isso.

    ```powershell
    $LicenseAddTPCP = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
    $LicenseAddTPCP.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuTargetTPCP.SkuPartNumber -EQ).SkuID
    $LicenseAddAC = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
    $LicenseAddAC.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuTargetAC.SkuPartNumber -EQ).SkuID
    
    $LicensesToUpdate = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
    $LicensesToUpdate.AddLicenses += ($LicenseAddTPCP)
    $LicensesToUpdate.AddLicenses += ($LicenseAddAC)
    $LicensesToUpdate.RemoveLicenses = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuSourceBV.SkuPartNumber -EQ).SkuID
    ```

1. Em seguida, obtenha a lista de usuários que têm as licenças do Business Voice atribuídas e armazene-as em uma lista chamada `$usersLicensedOldSKU`.

    ```powershell
    $usersLicensedOldSKU = New-Object System.Collections.Generic.List[Microsoft.Open.AzureAD.Model.User]
    
    Get-AzureAdUser | ForEach { $BVlicensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If($_.AssignedLicenses[$i].SkuId -eq $skuSourceBV.SkuId) { $BVlicensed=$true } } ; If( $BVlicensed -eq $true) { $usersLicensedOldSKU.Add($_)} }
    ```

1. Agora, usando a nova lista de usuários, execute uma atividade de atualização para remover as licenças do Business Voice e adicionar as licenças de Telefone e Audioconferência do Teams, ``$LicensesToUpdate`` usando o objeto criado anteriormente.

    ```powershell
    $usersLicensedOldSKU | ForEach { Set-AzureADUserLicense -ObjectId $_.ObjectId -AssignedLicenses $LicensesToUpdate; Write-Host "Completed Update of user " $_.UserPrincipalName;  }
    ```

> [!NOTE]
> Se você não tiver licenças suficientes disponíveis de Telefone e/ou Audioconferência do Teams para substituir o Business Voice, você receberá a assinatura de erro com **o guid de SKU** não terá nenhuma licença disponível durante a atribuição do usuário assim que o pool de licenças for esgotado.

### <a name="full-script"></a>Script completo

```powershell
#Install the AzureAD module when required
Install-Module AzureAD
#Import the AzureAD module so you can use the commandlets
Import-Module AzureAD

#Connect to your tenant
Connect-AzureAD

#When necessary, uncomment and use this commandlet to list all the licenses in the tenant and identify which license packages are required
#Get-AzureADSubscribedSku

##Replace the SKU codes below to match your desired scenario
$skuSourceBV = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "BUSINESS_VOICE_MED2_TELCO"}
$skuTargetTP = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "MCOTEAMS_ESSENTIALS"}
$skuTargetAC = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "MCOMEETADV"}

##Replace the SKU codes below to match your desired scenario
$servicePlan_Phone = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*EV*"}
$servicePlan_AC = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*MEET*"}
$servicePlan_CP = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*PSTN*"}

##Create variables to validate if all Service Plans in the source SKU will be replaced with the same target service plan
$validated_TP = $false
$validated_AC = $false
$validated_CP = $false

##If source Business Voice has no Calling Plan included, do not check
if($skuSourceBV.ServicePlans.Count -eq 2) { $validated_CP = $true }

##Verify if all service plans in source SKU have a matching service plan in target SKU
For ($i=0; $i -le $skuSourceBV.ServicePlans.Count ; $i++) { 
    if($validated_TP -eq $false) { if($skuTargetTP.ServicePlans.Contains($servicePlan_Phone)) { $validated_TP = $true } }
    if($validated_AC -eq $false) { if($skuTargetAC.ServicePlans.Contains($servicePlan_AC)) { $validated_AC = $true } }
    if($validated_CP -eq $false) { if($skuTargetTP.ServicePlans.Contains($servicePlan_CP)) { $validated_CP = $true } }
}

##If there's a missing service plan in the target sku, we might impact service availability for a user and therefore stop processing
if($validated_TP -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Teams Phone." ; exit } 
if($validated_AC -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Audio Conferencing." ; exit } 
if($validated_CP -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Calling Plan." ; exit } 


##Prepare variables and update
$LicenseAddTP = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$LicenseAddTP.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuTargetTP.SkuPartNumber -EQ).SkuID
$LicenseAddAC = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$LicenseAddAC.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuTargetAC.SkuPartNumber -EQ).SkuID
$LicensesToUpdate = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToUpdate.AddLicenses += ($LicenseAddTP)
$LicensesToUpdate.AddLicenses += ($LicenseAddAC)
$LicensesToUpdate.RemoveLicenses = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuSourceBV.SkuPartNumber -EQ).SkuID

$usersLicensedOldSKU = New-Object System.Collections.Generic.List[Microsoft.Open.AzureAD.Model.User]
Get-AzureAdUser | ForEach { $BVlicensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If($_.AssignedLicenses[$i].SkuId -eq $skuSourceBV.SkuId) { $BVlicensed=$true } } ; If( $BVlicensed -eq $true) { $usersLicensedOldSKU.Add($_)} }

$usersLicensedOldSKU | ForEach { Set-AzureADUserLicense -ObjectId $_.ObjectId -AssignedLicenses $LicensesToUpdate; Write-Host "Completed Update of user " $_.UserPrincipalName;  }
```

# <a name="option-4-bulk-users-with-azure-group-based-licensing"></a>[Opção 4: Usuários em massa com licenciamento baseado em grupo do Azure](#tab/azure-licensing)

### <a name="option-4-bulk-user-license-update-using-azure-group-based-licensing"></a>Opção 4: Atualização de licença de usuário em massa usando o licenciamento baseado em grupo do Azure

O gerenciamento de licenças baseado em grupo do Azure permite que você atribua assinaturas e planos de serviço a um grupo.

Esse método garante que:

- As licenças são atribuídas a todos os membros do grupo.
- Todos os novos membros que ingressarem no grupo receberão as licenças apropriadas.
- Quando os membros são removidos do grupo, essas licenças também são removidas.

Você precisará validar os [requisitos de licença para licenciamento baseado em grupo](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).

> [!NOTE]
> Para esse método, as atualizações de licença devem ser processadas em uma única etapa.
>
> Recomendamos que você compile uma lista de grupos existentes que têm licenças do Business Voice atribuídas, selecione um pequeno grupo de usuários de teste primeiro e substitua a atribuição do plano de licença com os novos planos de licença preferenciais.

### <a name="how-to-bulk-update-licenses-using-group-based-licensing"></a>Como atualizar licenças em massa usando o licenciamento baseado em grupo

1. Vá para [portal.azure.com](https://portal.azure.com) e entre com as credenciais de administrador.
1. Vá para **o Azure Active Directory** e, no menu à esquerda, selecione **Licenças**.
1. Para verificar quais grupos têm licenças do Business Voice atribuídas, escolha **Todos** os Produtos e selecione o plano do Business Voice.
1. Selecione **Grupos Licenciados** ou **Usuários Licenciados**. Você encontrará a lista de grupos licenciados no painel direito.
1. Selecione o nome do grupo para abrir os detalhes da atribuição de grupo.
1. Selecione **Atribuições** para modificar as licenças atribuídas a esse grupo.
1. Marque as caixas na frente dos planos de licença que você adquiriu para substituir o Business Voice.
1. Desmarque a caixa na frente do plano Microsoft 365 Business Voice licença.
1. Selecione **Salvar**.
1. Retorne ao grupo selecionando o nome do grupo. Você verá uma faixa informando que as **alterações de licença estão pendentes**.
1. Selecione **Reprocessar** para forçar a atualização da atribuição de licença.

---

## <a name="validate-user-license-updates"></a>Validar atualizações de licença de usuário

Depois de concluir o método escolhido, valide se as licenças de usuário foram atualizadas corretamente.

1. Vá para o [Centro de administração do Microsoft 365](https://admin.microsoft.com) e entre com as credenciais de administrador.
1. Navegue **até Usuários** > **Ativos e** selecione um usuário de teste.
1. Selecione **Gerenciar licenças de produto** na barra de ferramentas.
1. Na tela **Licenças e aplicativos** , examine quais licenças eles atribuiram a eles.

Se todos os usuários de destino tiverem as licenças corretas atribuídas, você concluiu a atualização de suas licenças do Business Voice para licenças de Telefone e Audioconferência do Teams.
