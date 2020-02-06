---
title: Vinculando regiões de rede
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Você pode configurar links entre duas regiões de rede como parte do controle de admissão de chamadas (CAC). '
ms.openlocfilehash: 4a643f34b9525b53168b9015b77a7f8292abd417
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817520"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a>Vincular regiões de rede no Skype for Business Server

Você pode configurar links entre duas regiões de rede como parte do controle de admissão de chamadas (CAC). Use as seções deste artigo para exibir informações de link da região newtwork ou configurar ou excluir links de região de netwrok. 

## <a name="view-network-region-link-information"></a>Exibir informações de link de região de rede 

Você pode exibir links entre duas regiões de rede como parte do controle de admissão de chamadas (CAC). Regiões dentro de uma rede são vinculadas por meio de conectividade física de rede de longa distância (WAN). Você pode usar o painel de controle do Skype for Business Server para exibir um link existente entre duas regiões de rede. 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a>Para exibir um link de região de rede no painel de controle do Skype for Business Server

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 

3.  Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em **link de região**.

4.  Na página **link de região** , clique no link de região que você deseja exibir.
    
    > [!NOTE]  
    > Você só pode exibir informações sobre um link de região de cada vez.

5.  No menu **Editar** , selecione **Mostrar detalhes**.

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a>Exibir informações de link de região de rede usando cmdlets do Windows PowerShell

Você pode exibir os links de região de rede usando o Windows PowerShell e o cmdlet **Get-CsNetworkRegionLink** . Você pode executar esse cmdlet a partir do Shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell. 


### <a name="to-view-network-region-link-information"></a>Para ver as informações de link da região de rede

  - Para ver as informações sobre todos os seus links de região de rede, digite o seguinte comando no Shell de gerenciamento do Skype for Business Server e pressione ENTER:
    
        Get-CsNetworkRegionLink
    
    Este comando retorna informações semelhantes para o seguinte:
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California


Para obter detalhes, consulte [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).


## <a name="configure-network-region-links"></a>Configurar links de região de rede 

Você pode configurar links entre duas regiões de rede como parte do controle de admissão de chamadas (CAC). Regiões dentro de uma rede são vinculadas por meio de conectividade física de rede de longa distância (WAN). Você pode usar o painel de controle do Skype for Business Server para definir um link entre duas regiões de rede e definir as limitações de largura de banda nas conexões de áudio e vídeo entre essas regiões.

### <a name="to-create-a-network-region-link"></a>Para criar um link de região de rede

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 

3.  Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em **link de região**.

4.  Na página **link de região** , clique em **novo**.

5.  Em **novo link de região**, digite um valor no campo **nome** .
 
    > [!NOTE]  
    > Esse valor deve ser exclusivo na implantação do Skype for Business Server.

6.  Na lista suspensa **região \#de rede 1** , selecione uma das duas regiões a ser vinculada.

7.  Na lista suspensa **região \#de rede 2** , selecione a outra região a ser vinculada. Esta região deve ser diferente da região selecionada para a região \#de rede 1.

8.  Adicionais Se você quiser colocar as limitações de largura de banda em chamadas de áudio ou de vídeo entre essas regiões, selecione um perfil de política de largura de banda na lista suspensa **política de largura de banda** .

9.  Clique em **Confirmar**.

### <a name="to-modify-a-network-region-link"></a>Para modificar um link de região de rede

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 

3.  Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em **link de região**.

4.  Na página **link de região** , clique no link de região que você deseja modificar.

5.  No menu **Editar**, clique em **Exibir detalhes**.

6.  No **link para editar região**, você pode modificar as regiões vinculadas ou o perfil de política de largura de banda para esse link.

7.  Clique em **Confirmar**.


## <a name="delete-network-region-links"></a>Excluir links de região de rede

Você pode configurar links entre duas regiões de rede como parte do controle de admissão de chamadas (CAC). Regiões dentro de uma rede são vinculadas por meio de conectividade física de rede de longa distância (WAN). Você pode usar o painel de controle do Skype for Business Server para excluir um link existente entre duas regiões de rede. 

### <a name="to-delete-a-network-region-link"></a>Para excluir um link de região de rede

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 

3.  Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em **link de região**.

4.  Na página **link de região** , clique no link de região que você deseja excluir.
 
    > [!NOTE]  
    > Você pode excluir mais de um link de região de cada vez. Para fazer isso, pressione CTRL e selecione vários links de região enquanto mantém a tecla CTRL pressionada. Ou, para selecionar todos os links de região, clique em <STRONG>selecionar tudo</STRONG> no menu <STRONG>Editar</STRONG> .

5.  No menu **Editar** , selecione **excluir**.

6.  Clique em **OK**.


## <a name="see-also"></a>Confira também

[New-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  

[Set-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  

[Remove-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  

[Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
