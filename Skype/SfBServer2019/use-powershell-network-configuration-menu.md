---
title: Usar o PowerShell para tarefas no menu Configuração de Rede
ms.reviewer: ''
ms.author: ankum
author: ankum
manager: ravrao
ms.date: 11/03/2021
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: ''
description: 'Resumo: Skype for Business Server painel de controle para mapeamento de cmdlet para menu Configuração de Rede.'
ms.openlocfilehash: aa42ac465ffd72a4aff9c03293124c857e5b712c
ms.sourcegitcommit: 3b5ae6ebf4384166c628f66a4f17e6fe4455b708
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/29/2021
ms.locfileid: "61625991"
---
# <a name="network-configuration"></a>Configuração de rede

Este artigo descreve como resultados semelhantes aos do **item** de menu Configuração de Rede no Painel de Controle herdado podem ser obtidos usando cmdlets.

Este artigo descreve os seguintes sub-menus:

- [Configuração de Rede](#network-configuration)
  - [Política local](#location-policy)
  - [Política de Largura de Banda](#bandwidth-policy)
  - [Região](#region)
  - [Site](#site)
  - [Sub-rede](#subnet)
  - [Link de região](#region-link)
  - [Rota da região](#region-route)

## <a name="location-policy"></a>Política de Local

O sub menu **POLÍTICA DE** LOCAL é usado para aplicar configurações relacionadas à funcionalidade E9-1-1. A diretiva de local determina se um usuário está habilitado ou não para o recurso E9-1-1, e se for o caso, qual será o comportamento em uma chamada de emergência.

Vamos considerar as várias tarefas que um usuário pode realizar na **POLÍTICA DE** LOCAL e os cmdlets Skype for Business essas tarefas são mapeados.

---

> **Cenário 1**: Listar todas as Políticas de Localização

   ![Política de Localização de Lista](./media/location-policy-1.png)

***Cmdlet***

[Get-CsLocationPolicy](/powershell/module/skype/get-cslocationpolicy)

***Exemplo***

```powershell
 Get-CsLocationPolicy
```

---

> **Cenário 2**: Criar uma nova Política de Local

   ![Criar Política de Local](./media/location-policy-2.png)

***Cmdlet***

[New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy)  

***Exemplo***

```powershell
 New-CsLocationPolicy -Identity site:Redmond -EnhancedEmergencyServicesEnabled $True
```

---

> **Cenário 3**: Obter detalhes de uma Política de Local escolhida

   ![Obter Política de Local](./media/location-policy-3.png)

***Cmdlet***

[Get-CsLocationPolicy](/powershell/module/skype/get-cslocationpolicy)

***Exemplo***

```powershell
 Get-CsLocationPolicy -Identity Reno
```

---

> **Cenário 4**: Excluir políticas de local escolhidas

   ![Excluir Política de Local](./media/location-policy-4.png)

***Cmdlet***

[Remove-CsLocationPolicy](/powershell/module/skype/remove-cslocationpolicy)

***Exemplo***

```powershell
 Remove-CsLocationPolicy -Identity Reno
```

---

> **Cenário 5**: atualizar uma política de local

   ![Atualizar Política de Local](./media/location-policy-5.png)

***Cmdlet***

[Set-CsLocationPolicy](/powershell/module/skype/set-cslocationpolicy)

***Exemplo***

```powershell
 Set-CsLocationPolicy -Identity site:Redmond -EnhancedEmergencyServicesEnabled $True
```

---

## <a name="bandwidth-policy"></a>Política de Largura de Banda

Como parte de um controle de admissão de chamadas (CAC), uma diretiva de largura de banda é utilizada para definir limites para certas modalidades. (No Skype for Business Server, somente as modalidades de áudio e vídeo podem ser atribuídas a limitações de largura de banda.) Este cmdlet cria um perfil de contêiner para essas políticas. Você define as políticas individuais dentro do contêiner especificando as limitações de largura de banda de áudio e vídeo ao chamar esse cmdlet.

Considere as várias tarefas que um usuário pode realizar na **POLÍTICA** DE LARGURA DE BANDA e os cmdlets Skype for Business essas tarefas são mapeados.

---
> **Cenário 1**: listar todas as políticas de largura de banda

   ![Política de Largura de Banda de Lista](./media/bandwidth-policy-1.png)

***Cmdlet***

[Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/get-csnetworkbandwidthpolicyprofile)

***Exemplo***

```powershell
 Get-CsNetworkBandwidthPolicyProfile
```

---

> **Cenário 2**: Criar uma nova Política de Largura de Banda

   ![Nova Política de Largura de Banda](./media/bandwidth-policy-2.png)

***Cmdlet***

[New-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/new-csnetworkbandwidthpolicyprofile)  

***Exemplo***

```powershell
 New-CsNetworkBandwidthPolicyProfile -Identity LowBWLimits -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400 -VideoBWSessionLimit 500
```

---

> **Cenário 3**: Obter detalhes de uma Política de Largura de Banda escolhida

   ![Obter Política de Largura de Banda](./media/bandwidth-policy-3.png)

***Cmdlet***

[Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/get-csnetworkbandwidthpolicyprofile)

***Exemplo***

```powershell
 Get-CsNetworkBandwidthPolicyProfile -Identity LowBWProfile
```

---

> **Cenário 4**: Excluir políticas de largura de banda escolhidas

   ![Excluir Política de Largura de Banda](./media/bandwidth-policy-4.png)

***Cmdlet***

[Remove-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/remove-csnetworkbandwidthpolicyprofile)

***Exemplo***

```powershell
 Remove-CsNetworkBandwidthPolicyProfile -Identity LowBWProfile
```

---

> **Cenário 5**: atualizar uma política de largura de banda

   ![Atualizar Política de Largura de Banda](./media/bandwidth-policy-5.png)

***Cmdlet***

[Set-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/set-csnetworkbandwidthpolicyprofile)

***Exemplo***

```powershell
 Set-CsNetworkBandwidthPolicyProfile -Identity LowBWLimit -VideoBWLimit 2500 -VideoBWSessionLimit 300
```

---

## <a name="region"></a>Região

Uma região de rede interconecta várias partes de uma rede entre várias áreas geográficas. Cada região de rede deve ser associada com um local central. Os administradores podem usar o menu **REGION** para gerenciar informações sobre uma ou mais regiões de rede, incluindo o site central associado e configurações que determinam se caminhos alternativos são permitidos para conexões de áudio e vídeo e que associam os sites dentro da região a uma configuração de bypass de mídia.

---

> **Cenário 1**: Listar todas as regiões

   ![Região de Lista](./media/network-region-1.png)

***Cmdlet***

[Get-CsNetworkRegion](/powershell/module/skype/get-csnetworkregion)

***Exemplo***

```powershell
 Get-CsNetworkRegion
```

---

> **Cenário 2**: Criar uma nova região

   ![Criar Região](./media/network-region-2.png)

***Cmdlet***

[New-CsNetworkRegion](/powershell/module/skype/new-csnetworkregion)  

***Exemplo***

```powershell
 New-CsNetworkRegion -Identity NorthAmerica -Description "All North American Locations" -CentralSite Redmond-NA-MLS
```

---

> **Cenário 3**: Obter detalhes de uma região escolhida

   ![Obter Região](./media/network-region-3.png)

***Cmdlet***

[Get-CsNetworkRegion](/powershell/module/skype/get-csnetworkregion)

***Exemplo***

```powershell
 Get-CsNetworkRegion -Identity NorthAmerica
```

---

> **Cenário 4**: Excluir regiões escolhidas

   ![Excluir Região](./media/network-region-4.png)

***Cmdlet***

[Remove-CsNetworkRegion](/powershell/module/skype/remove-csnetworkregion)

***Exemplo***

```powershell
 Remove-CsNetworkRegion -Identity NorthAmerica
```

---

> **Cenário 5**: Atualizar uma região

   ![Região de atualização](./media/network-region-5.png)

- **Anotação 1 - Resultado**

    Essa anotação na imagem indica um resultado, ou seja, os dados que estão sendo recuperados e exibidos.

    ***Cmdlet***

    [Get-CsNetworkSite from Region](/powershell/module/skype/get-csnetworksite)

    ***Exemplo***

    ```powershell
     Get-CsNetworkSite | Where-Object {$_.NetworkRegionID -eq "AKR"}
    ```

- **Anotação 2 - Opção (para o usuário)**

    Essa anotação na imagem indica uma opção para o usuário implementar, ou seja, salvar uma região de rede.

    [Set-CsNetworkRegion](/powershell/module/skype/set-csnetworkregion)

   ***Exemplo***

   ```powershell
   Set-CsNetworkRegion -Identity NorthAmerica -Description "North American Region"
   ```

---

## <a name="site"></a>Site

Os sites de rede são os escritórios ou locais configurados em cada região de uma implantação do CAC ou E9-1-1. **O** sub-menu SITE ajuda os administradores a adicionar, remover ou gerenciar suas configurações.

Considere as várias tarefas que um usuário pode realizar no **SITE** e os cmdlets Skype for Business essas tarefas são mapeados.

---

> **Cenário 1**: Listar todos os sites

   ![Site de Lista](./media/network-site-1.png)

***Cmdlet***

[Get-CsNetworkSubnet](/powershell/module/skype/get-csnetworksite)

***Exemplo***

```powershell
 Get-CsNetworkSite
```

---

> **Cenário 2**: Criar um novo site

   ![Criar Site](./media/network-site-2.png)

***Cmdlet***

[New-CsNetworkSubnet](/powershell/module/skype/new-csnetworksite)  

***Exemplo***

```powershell
 New-CsNetworkSite -Identity Vancouver -NetworkRegionID NorthAmerica
```

---

> **Cenário 3**: Obter detalhes de um site escolhido

   ![Obter Site](./media/network-site-3.png)

***Cmdlet***

[Get-CsNetworkSubnet](/powershell/module/skype/get-csnetworksite)

***Exemplo***

```powershell
 Get-CsNetworkSite -Identity Redmond
```

---

> **Cenário 4**: Excluir sites escolhidos

   ![Excluir Site](./media/network-site-4.png)

***Cmdlet***

[Remove-CsNetworkSubnet](/powershell/module/skype/remove-csnetworksite)

***Exemplo***

```powershell
 Remove-CsNetworkSite -Identity Vancouver
```

---

> **Cenário 5**: Atualizar um site

   ![Atualizar Site](./media/network-site-5.png)

- **Anotação 1 - Resultado**

    Essa anotação na imagem indica um resultado, ou seja, os dados que estão sendo recuperados e exibidos.

    ***Cmdlet***

    [Get-CsNetworkSubnet do Site](/powershell/module/skype/get-csnetworksubnet)

    ***Exemplo***

    ```powershell
     Get-CsNetworkSubnet | Where-Object {$_.NetworkSiteID -eq "Vancouver"}
    ```

- **Anotação 2 - Opção (para o usuário)**

    Essa anotação na imagem indica uma opção para o usuário implementar, ou seja, salvar um site de rede.

   ***Cmdlet***

   [Set-CsNetworkSubnet](/powershell/module/skype/set-csnetworksite)

   ***Exemplo***

   ```powershell
    Set-CsNetworkSite -Identity Vancouver - BWPolicyProfileID LowBWLimits
   ```

---

## <a name="subnet"></a>Sub-rede

Os administradores podem usar o sub-menu **SUBNET** para criar, atualizar e gerenciar sub-redes de rede.

Considere as várias tarefas que um usuário pode realizar na **SUBNET** e os cmdlets Skype for Business essas tarefas são mapeados.

---

> **Cenário 1**: Listar todas as sub-redes

   ![Listar Sub-rede](./media/network-subnet-1.png)

***Cmdlet***

[Get-CsNetworkSubnet](/powershell/module/skype/get-csnetworksubnet)

***Exemplo***

```powershell
 Get-CsNetworkSubnet
```

---

> **Cenário 2**: Criar uma nova sub-rede

   ![Criar Sub-rede](./media/network-subnet-2.png)

***Cmdlet***

[New-CsNetworkSubnet](/powershell/module/skype/new-csnetworksubnet)  

***Exemplo***

```powershell
 New-CsNetworkSubnet -Identity 172.11.15.0 -MaskBits 24 -NetworkSiteID Vancouver
```

---

> **Cenário 3**: Obter detalhes de uma sub-rede escolhida

   ![Obter Sub-rede](./media/network-subnet-3.png)

***Cmdlet***

[Get-CsNetworkSubnet](/powershell/module/skype/get-csnetworksubnet)

***Exemplo***

```powershell
 Get-CsNetworkSubnet -Identity 172.11.15.0
```

---

> **Cenário 4**: Excluir sub-redes escolhidas

   ![Excluir Sub-rede](./media/network-subnet-4.png)

***Cmdlet***

[Remove-CsNetworkSubnet](/powershell/module/skype/remove-csnetworksubnet)

***Exemplo***

```powershell
 Remove-CsNetworkSubnet -Identity 172.11.15.0
```

---

> **Cenário 5**: Atualizar uma sub-rede

   ![Atualizar Sub-rede](./media/network-subnet-5.png)

***Cmdlet***

[Set-CsNetworkSubnet](/powershell/module/skype/set-csnetworksubnet)

***Exemplo***

```powershell
 Set-CsNetworkSubnet -Identity 172.11.15.0 -MaskBits 25 -NetworkSiteID Chicago
```

---

## <a name="region-link"></a>Link de região

As regiões dentro de uma rede são vinculadas por meio da conectividade wan física. Os administradores podem usar o sub-menu LINK DE **REGIÃO** para criar, atualizar e gerenciar sub-redes de rede.

Vamos considerar as várias tarefas que um usuário pode realizar no LINK DE **REGIÃO** e os cmdlets Skype for Business essas tarefas são mapeados.

---

> **Cenário 1**: Listar todos os links de região

   ![Link de região de lista](./media/network-regionlink-1.png)

***Cmdlet***

[Get-CsNetworkRegionLink](/powershell/module/skype/get-csnetworkregionLink)

***Exemplo***

```powershell
 Get-CsNetworkRegionLink
```

---

> **Cenário 2**: Criar um novo link de região

   ![Criar Link de Região](./media/network-regionlink-2.png)

***Cmdlet***

[New-CsNetworkRegionLink](/powershell/module/skype/new-csnetworkregionLink)  

***Exemplo***

```powershell
 New-CsNetworkRegionLink -Identity NA_EMEA -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID LowBWLimits
```

---

> **Cenário 3**: Obter detalhes de um link de região escolhido

   ![Obter Link de Região](./media/network-regionlink-3.png)

***Cmdlet***

[Get-CsNetworkRegionLink](/powershell/module/skype/get-csnetworkregionLink)

***Exemplo***

```powershell
 Get-CsNetworkRegionLink -Identity NA_EMEA
```

---

> **Cenário 4**: Excluir links de região escolhidos

   ![Excluir Link de Região](./media/network-regionlink-4.png)

***Cmdlet***

[Remove-CsNetworkRegionLink](/powershell/module/skype/remove-csnetworkregionLink)

***Exemplo***

```powershell
 Remove-CsNetworkRegionLink -Identity NA_EMEA
```

---

> **Cenário 5**: Atualizar um link de região

   ![Atualizar Link da Região](./media/network-regionlink-5.png)

***Cmdlet***

[Set-CsNetworkRegionLink](/powershell/module/skype/set-csnetworkregionLink)

***Exemplo***

```powershell
 Set-CsNetworkRegionLink -Identity NA_EMEA -BWPolicyProfileID HighBWLimits
```

---

## <a name="region-route"></a>Rota da região

Todas as regiões em uma configuração do CAC precisam ter alguma maneira de acessar todas as outras regiões. Enquanto os links de regiões definem limitações de largura de banda nas conexões entre regiões e também representam os links físicos, uma rota determina qual caminho vinculado a conexão irá transpor de uma região para a outra. Os administradores podem usar o sub-menu **ROTA** DA REGIÃO para criar, atualizar e gerenciá-los.

Considere as várias tarefas que um usuário pode realizar na ROTA DA REGIÃO **e** os cmdlets Skype for Business essas tarefas são mapeados.

---

> **Cenário 1**: listar todas as rotas da região

   ![Listar Rota da Região](./media/network-regionroute-1.png)

***Cmdlet***

[Get-CsNetworkInterRegionRoute](/powershell/module/skype/get-csnetworkinterregionroute)

***Exemplo***

```powershell
 Get-CsNetworkInterRegionRoute
```

---

> **Cenário 2**: Criar uma nova rota de região

   ![Criar Rota de Região](./media/network-regionroute-2.png)

***Cmdlet***

[New-CsNetworkInterRegionRoute](/powershell/module/skype/new-csnetworkinterregionroute)  

***Exemplo***

```powershell
 New-CsNetworkInterRegionRoute -Identity NA_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA_EMEA,EMEA_APAC"
```

---

> **Cenário 3**: Obter detalhes de uma rota de região escolhida

   ![Obter Rota da Região](./media/network-regionroute-3.png)

***Cmdlet***

[Get-CsNetworkInterRegionRoute](/powershell/module/skype/get-csnetworkinterregionroute)

***Exemplo***

```powershell
 Get-CsNetworkInterRegionRoute -Filter *APAC*
```

---

> **Cenário 4**: Excluir rotas de região escolhidas

   ![Excluir Rota da Região](./media/network-regionroute-4.png)

***Cmdlet***

[Remove-CsNetworkInterRegionRoute](/powershell/module/skype/remove-csnetworkinterregionroute)

***Exemplo***

```powershell
 Remove-CsNetworkInterRegionRoute -Identity NA_APAC_Route
```

---

> **Cenário 5**: Atualizar uma rota de região

   ![Rota da região de atualização](./media/network-regionroute-5.png)

- **Anotação 1 - Opção (para o usuário)**

    Essa anotação na imagem indica um resultado, ou seja, os dados que estão sendo recuperados e exibidos.

   ***Cmdlet***

   [Get-CsNetworkRegionLink](/powershell/module/skype/get-csnetworkregionLink)

   ***Exemplo***

   ```powershell
   Get-CsNetworkRegionLink
   ```

- **Anotação 2 - Opção (para o usuário)**

    Essa anotação na imagem indica uma opção para o usuário implementar, ou seja, salvar uma rota de região de rede.

    ***Cmdlet***

   [Set-CsNetworkInterRegionRoute](/powershell/module/skype/set-csnetworkinterregionroute)

   ***Exemplo***

   ```powershell
   Set-CsNetworkInterRegionRoute -Identity NA_APAC_Route -NetworkRegionLinkIDs "NA_SA,SA_APAC"
   ```

---
---
