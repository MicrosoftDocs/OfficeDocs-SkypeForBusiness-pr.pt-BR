---
title: Gerenciar sua topologia de rede para recursos de voz na nuvem no Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.networktopology.overview
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba como configurar configurações de rede para recursos de voz na nuvem no Microsoft Teams.
ms.openlocfilehash: bdb81fa7f8dee559f7c47e276224ecb2333c7bb5
ms.sourcegitcommit: 95a56dab4e30f7ad6615ebd4a4a0f61996fdc20f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/17/2023
ms.locfileid: "69812688"
---
# <a name="manage-your-network-topology-for-cloud-voice-features-in-microsoft-teams"></a>Gerenciar sua topologia de rede para recursos de voz na nuvem no Microsoft Teams

Se sua organização estiver implantando [roteamento baseado em localização para roteamento direto](location-based-routing-plan.md) ou [chamada de emergência dinâmica](configure-dynamic-emergency-calling.md), você deverá configurar as configurações de rede para uso com esses recursos de voz na nuvem no Microsoft Teams. As configurações de rede são usadas para determinar a localização de um cliente do Teams e incluir regiões de rede, sites de rede, sub-redes e endereços IP confiáveis. Dependendo do recurso de voz na nuvem e da funcionalidade que você está implantando, você configura algumas ou todas essas configurações. Para saber mais sobre esses termos, confira [Configurações de rede para recursos de voz na nuvem](cloud-voice-network-settings.md).

Você configura as configurações de rede na página **topologia de** rede do centro de administração do Microsoft Teams ou usando Windows PowerShell.

## <a name="configure-network-settings-in-the-microsoft-teams-admin-center"></a>Configurar configurações de rede no centro de administração do Microsoft Teams

Você define regiões de rede, sites de rede e sub-redes na guia **Sites** de rede da página **topologia** de rede. Aqui, você pode criar ou modificar um site de rede, associar um site a uma região de rede, associar uma sub-rede ao site, ativar Roteamento baseado em localização e atribuir políticas de emergência ao site. Você também pode adicionar regiões de rede que podem ser usadas globalmente para todos os sites.

#### <a name="add-and-configure-a-network-site"></a>Adicionar e configurar um site de rede

1. Na navegação à esquerda do centro de administração do Microsoft Teams, acesse **Topologia de Rede** de **Locais** >  e clique na guia **Sites de rede**.
2. Clique em **Adicionar** e insira um nome e uma descrição para o site.

    ![Captura de tela da página Adicionar site de rede.](media/manage-network-topology-add-site.png)

3. Para associar o site a uma região de rede, clique em **Adicionar região de rede**, selecione uma região existente ou clique em **Adicionar** para adicionar uma região e clique em **Link**.  
4. Para habilitar Location-Based Roteamento para o site, ative **o roteamento baseado em localização**.
5. Para atribuir políticas de serviços de emergência ao site, faça uma ou as duas seguintes:

    - Se sua organização usar Planos de Chamada, Conexão de Operador ou Roteamento Direto, em **Política de chamada de emergência**, selecione a política desejada.
    - Se sua organização implantou o Roteamento Direto, em **Política de roteamento de chamada de emergência**, selecione a política desejada.

6. Para associar uma sub-rede ao site, em **Sub-redes**, clique em **Adicionar sub-redes**. Especifique a versão IP, o endereço IP, o intervalo de rede, adicione uma descrição e clique em **Aplicar**. Cada sub-rede deve ser associada a um site específico.
7. Clique em **Salvar**.

#### <a name="modify-a-network-site"></a>Modificar um site de rede

1. Na navegação à esquerda do centro de administração do Microsoft Teams, acesse **Topologia de Rede** de **Locais** >  e clique na guia **Sites de rede**.
2. Selecione o site clicando à esquerda do nome do site e clique em **Editar**.
3. Faça as alterações desejadas e clique em **Salvar.**

### <a name="manage-external-trusted-ip-addresses"></a>Gerenciar endereços IP confiáveis externos

Você gerencia endereços IP confiáveis externos na guia **IPs Confiáveis** na página **topologia de** rede do centro de administração do Microsoft Teams. Você pode adicionar um número ilimitado de endereços IP confiáveis externos.

#### <a name="add-a-trusted-ip-address"></a>Adicionar um endereço IP confiável

1. Na navegação à esquerda do centro de administração do Microsoft Teams, acesse **Topologia de Rede** de **Locais** >  e clique na guia **IPs Confiáveis**.
2. Clique em **Novo**.
3. No painel **Adicionar endereço IP confiável** , especifique a versão IP, o endereço IP, o intervalo de rede, adicione uma descrição e clique em **Aplicar**.

    ![Captura de tela do painel Adicionar endereço IP confiável.](media/manage-network-topology-add-trusted-ip.png)

#### <a name="edit-a-trusted-ip-address"></a>Editar um endereço IP confiável

1. Na navegação à esquerda do centro de administração do Microsoft Teams, acesse **Topologia de Rede** de **Locais** >  e clique na guia **IPs Confiáveis**.
2. Selecione o endereço IP clicando à esquerda dele e clique em **Editar**.
3. No painel **Editar endereço IP confiável** , faça as alterações desejadas e clique em **Aplicar**.

## <a name="configure-network-settings-using-powershell"></a>Configurar configurações de rede usando o PowerShell

Para concluir as etapas nesta seção, você precisará de alguma familiaridade com os cmdlets do PowerShell. Para saber mais, confira [Visão geral do Teams PowerShell](teams-powershell-overview.md).

### <a name="define-network-regions"></a>Definir regiões de rede

 Use o cmdlet [New-CsTenantNetworkRegion](/powershell/module/skype/New-CsTenantNetworkRegion) para definir regiões de rede. Observe que o parâmetro RegionID é um nome lógico que representa a geografia da região e não tem dependências ou restrições e o parâmetro ID&gt; do site do CentralSite &lt;é opcional.

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

Neste exemplo, criamos uma região de rede chamada Índia.

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

Consulte também [Set-CsTenantNetworkRegion](/powershell/module/skype/set-cstenantnetworkregion).

### <a name="define-network-sites"></a>Definir sites de rede

Use o cmdlet [New-CsTenantNetworkSite](/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) para definir sites de rede. Cada site de rede deve ser associado a uma região de rede.

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

Neste exemplo, criamos dois novos sites de rede, Delhi e Hyderabad, na região da Índia.

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"
```

A tabela a seguir mostra os sites de rede definidos neste exemplo.

|&nbsp;|Site 1 |Site 2 |
|---------|---------|---------|
|Site ID    |    Site 1 (Delhi)     |  Site 2 (Hyderabad)       |
|ID da região  |     Região 1 (Índia)    |   Região 1 (Índia)      |

Consulte também [Set-CsTenantNetworkRegion](/powershell/module/skype/set-cstenantnetworksite).

### <a name="define-network-subnets"></a>Definir sub-redes de rede

Use o cmdlet [New-CsTenantNetworkSubnet](/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) para definir sub-redes de rede e associá-las a sites de rede. Cada sub-rede de rede só pode ser associada a um site.

```PowerShell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

Neste exemplo, criamos uma associação entre a sub-rede 192.168.0.0 e o site de rede de Delhi e entre a sub-rede 2001:4898:e8:25:844e:926f:85ad:dd8e e o site de rede Hyderabad.

```PowerShell
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad"
```

A tabela a seguir mostra as sub-redes definidas neste exemplo.

|&nbsp;|Site 1 |Site 2 |
|---------|---------|---------|
|ID da sub-rede   |    192.168.0.0     |  2001:4898:e8:25:844e:926f:85ad:dd8e     |
|Máscara  |     24    |   120      |
|Site ID  | Site (Delhi) | Site 2 (Hyderabad) |

Para várias sub-redes, você pode importar um arquivo CSV usando um script como o seguinte.

```PowerShell
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.Identity -MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```

Neste exemplo, o arquivo CSV tem uma aparência semelhante a esta:

```console
Identity, Mask, SiteID
172.11.12.0, 24, Redmond
172.11.13.0, 24, Chicago
172.11.14.0, 25, Vancouver
172.11.15.0, 28, Paris
```


Consulte também [Set-CsTenantNetworkSubnet](/powershell/module/skype/set-cstenantnetworksubnet).


### <a name="define-external-subnets-external-trusted-ip-addresses"></a>Definir sub-redes externas (endereços IP confiáveis externos)

Use o cmdlet [New-CsTenantTrustedIPAddress](/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) para definir sub-redes externas e atribuí-las ao locatário. Você pode definir um número ilimitado de sub-redes externas para um locatário.

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```

Por exemplo:

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

Consulte também [Set-CsTenantTrustedIPAddress](/powershell/module/skype/set-cstenanttrustedipaddress).

## <a name="enabling-network-roaming-policies"></a>Habilitando políticas de roaming de rede

Depois de configurar suas políticas de roaming de rede, você precisa habilitar a **pesquisa de configuração de rede** _ em cada uma de suas *políticas _Meeting** no Centro de Administração do Teams em **Reuniões > Políticas de Reunião.**

Você pode querer editar a política global ou criar uma nova política e atribuir a política a usuários específicos.

## <a name="related-topics"></a>Tópicos relacionados

- [Configurações de rede para recursos de voz na nuvem no Teams](cloud-voice-network-settings.md)
