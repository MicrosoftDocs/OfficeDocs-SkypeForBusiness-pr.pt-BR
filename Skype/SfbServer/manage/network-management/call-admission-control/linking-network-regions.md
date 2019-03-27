---
title: Vinculação de regiões de rede
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Você pode configurar links entre duas regiões de rede como parte do controle de admissão de chamadas (CAC). '
ms.openlocfilehash: 4ea6ddcc72d2cadea32608288d1db93ba8505aee
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884681"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a>Vincular regiões de rede no Skype for Business Server

Você pode configurar links entre duas regiões de rede como parte do controle de admissão de chamadas (CAC). Use as seções deste artigo para exibir informações de link de região newtwork ou configurar ou excluir links de região de rede. 

## <a name="view-network-region-link-information"></a>Exibir informações de link de região de rede 

Você pode exibir links entre duas regiões de rede como parte do controle de admissão de chamadas (CAC). Regiões dentro de uma rede são vinculadas por meio da conectividade de rede (WAN) de longa distância físico. Você pode usar o Skype para painel de controle do Business Server para exibir um link existente entre duas regiões de rede. 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a>Para exibir um link de região de rede no Skype para painel de controle do servidor de negócios

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 

3.  Na barra de navegação à esquerda, clique em **Configuração de rede**e clique no **Link de região**.

4.  Na página **Link de região** , clique no link de região que você deseja exibir.
    
    > [!NOTE]  
    > Você só pode exibir informações sobre um link da região por vez.

5.  No menu **Editar** , selecione **Mostrar detalhes**.

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a>Exibir informações de link de região de rede usando os cmdlets do Windows PowerShell

Você pode exibir os links de região de rede usando o Windows PowerShell e o cmdlet **Get-CsNetworkRegionLink** . Você pode executar esse cmdlet a partir do Skype do Shell de gerenciamento do servidor de negócios ou uma sessão remota do Windows PowerShell. 


### <a name="to-view-network-region-link-information"></a>Para exibir informações de link de região de rede

  - Para exibir informações sobre todos os links da região de rede, digite o seguinte comando no Skype do Shell de gerenciamento do servidor de negócios e pressione ENTER:
    
        Get-CsNetworkRegionLink
    
    Este comando retorna informações semelhantes para o seguinte:
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California


Para obter detalhes, consulte [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).


## <a name="configure-network-region-links"></a>Configurar links de região de rede 

Você pode configurar links entre duas regiões de rede como parte do controle de admissão de chamadas (CAC). Regiões dentro de uma rede são vinculadas por meio da conectividade de rede (WAN) de longa distância físico. Você pode usar o Skype para painel de controle do Business Server para definir um link entre duas regiões de rede e definir as limitações de largura de banda em conexões de áudio e vídeo entre essas regiões.

### <a name="to-create-a-network-region-link"></a>Para criar um link de região de rede

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 

3.  Na barra de navegação à esquerda, clique em **Configuração de rede**e clique no **Link de região**.

4.  Na página **Link de região** , clique em **novo**.

5.  Em **Novo Link de região**, digite um valor no campo **nome** .
 
    > [!NOTE]  
    > Este valor deve ser exclusivo dentro de sua Skype para implantação de servidor de negócios.

6.  Da **região de rede \#1** lista suspensa, selecione uma das duas regiões a serem vinculadas.

7.  Da **região de rede \#2** lista suspensa, selecione a outra região a serem vinculadas. Essa região deve ser diferente da região selecionada para a região de rede \#1.

8.  (Opcional) Se você deseja colocar as limitações de largura de banda em chamadas de áudio ou vídeos entre essas regiões, selecione um perfil de política de largura de banda na lista suspensa **política de largura de banda** .

9.  Clique em **Confirmar**.

### <a name="to-modify-a-network-region-link"></a>Para modificar um link de região de rede

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 

3.  Na barra de navegação à esquerda, clique em **Configuração de rede**e clique no **Link de região**.

4.  Na página **Link de região** , clique no link de região que você deseja modificar.

5.  No menu **Editar**, clique em **Exibir detalhes**.

6.  Em **Editar Link de região**, você pode modificar as regiões que estão vinculadas ou o perfil de política de largura de banda para este link.

7.  Clique em **Confirmar**.


## <a name="delete-network-region-links"></a>Excluir links de região de rede

Você pode configurar links entre duas regiões de rede como parte do controle de admissão de chamadas (CAC). Regiões dentro de uma rede são vinculadas por meio da conectividade de rede (WAN) de longa distância físico. Você pode usar o Skype para painel de controle do Business Server para excluir um link existente entre duas regiões de rede. 

### <a name="to-delete-a-network-region-link"></a>Para excluir um link de região de rede

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 

3.  Na barra de navegação à esquerda, clique em **Configuração de rede**e clique no **Link de região**.

4.  Na página **Link de região** , clique no link de região que você deseja excluir.
 
    > [!NOTE]  
    > Você pode excluir mais de um link de região por vez. Para fazer isso, pressione CTRL e selecione vários links de região, mantendo pressionada a tecla CTRL. Ou, para selecionar todos os links de região, clique em <STRONG>Selecionar tudo</STRONG> no menu <STRONG>Editar</STRONG> .

5.  No menu **Editar** , selecione **Excluir**.

6.  Clique em **OK**.


## <a name="see-also"></a>Consulte Também

[New-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  

[Set-CsNetworkRegionLink.](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  

[Remove-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  

[Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
