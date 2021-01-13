---
title: Gerenciando rotas de região de rede
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
description: Uma rota de região de rede define a rota entre um par de regiões de rede. Cada par de regiões de rede de sua implantação de controle de admissão de chamadas exige uma rota de região de rede.
ms.openlocfilehash: 23dec126511b941ff3e25b22c37cbba0854b13bc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816431"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a>Gerenciando roteamento de regiões de rede no Skype for Business Server

Uma *rota de região de rede* define a rota entre um par de regiões de rede. Cada par de regiões de rede de sua implantação de controle de admissão de chamadas exige uma rota de região de rede. Isso permite que todas as regiões de rede da implantação acessem todas as outras regiões. Use os procedimentos nesta arte para exibir, criar, modificar ou excluir rotas de região de rede.

## <a name="view-network-region-route-information"></a>Exibir informações de rota de região de rede 

Cada região de um configuração de CAC (controle de admissão de chamadas) deve ter alguma forma de acessar todas as outras regiões. Enquanto os links da região definem limitações nas conexões entre regiões e representam também os links físicos, uma rota determina o caminho vinculado que a conexão percorrerá de uma região a outra. Use os procedimentos a seguir para exibir as rotas de região de rede existentes no Painel de Controle do Skype for Business Server ou no Shell de Gerenciamento do Skype for Business Server. 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a>Para exibir informações de rota de região de rede no Painel de Controle do Skype for Business Server

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 

3.  Na barra de navegação esquerda, clique em **Configuração de** Rede e clique em **Rota de Região.**

4.  Na página **Rota de Região**, clique na rota de região que deseja exibir.


    > [!NOTE]  
    > É possível ver apenas uma rota de região por vez.


5.  No menu **Editar**, clique em **Mostrar detalhes**.


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a>Exibindo informações de rota de região de rede usando cmdlets do Windows PowerShell

As informações de rota de região de rede podem ser exibidas usando o Windows PowerShell e o Get-CsNetworkInterRegionRoute cmdlet. Esse cmdlet pode ser executado a partir do Shell de Gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell. 

### <a name="to-view-network-region-route-information"></a>Para exibir informações de rota de região de rede

  - Para exibir informações sobre todas as rotas de região de rede, digite o seguinte comando no Shell de Gerenciamento do Skype for Business Server e pressione ENTER:
    
        Get-CsNetworkInterRegionRoute
    
    Isto retorna informações semelhantes à seguinte:
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

Para obter mais informações, consulte o tópico de ajuda do cmdlet [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute).


## <a name="create-or-modify-network-region-routes"></a>Criar ou modificar rotas de região de rede

Cada região de um configuração de CAC (controle de admissão de chamadas) deve ter alguma forma de acessar todas as outras regiões. Enquanto os links da região definem limitações nas conexões entre regiões e representam também os links físicos, uma rota determina o caminho vinculado que a conexão percorrerá de uma região a outra. Você pode usar o Painel de Controle do Skype for Business Server para configurar rotas de região de rede. No Painel de Controle do Skype for Business Server, você pode criar, modificar ou excluir uma rota de região de rede. Use este tópico para criar ou modificar uma rota de região de rede. 

### <a name="to-create-a-network-region-route"></a>Para criar uma rota de região de rede

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 

3.  Na barra de navegação esquerda, clique em **Configuração de** Rede e clique em **Rota de Região.**

4.  Na página **Rota de Região**, clique em **Novo**.

5.  Em **Nova Rota de Região**, digite um valor no campo **Nome**.
   
    > [!NOTE]  
    > Esse valor deve ser exclusivo em sua implantação do Skype for Business Server.

6.  Na lista drop-down da Região **\# de rede 1,** selecione uma das duas regiões a serem conectadas por esta rota.

7.  Na lista drop-down da Região de rede **\# 2,** selecione a outra região para essa rota. Essa região deve ser diferente da região selecionada para a Região \# de rede 1.

8.  Use a caixa de listagem **Links de região de rede** para adicionar os links de região para a rota. Clique no botão **Adicionar** para exibir a página **Link de Região**. Clique em um link de região para adicionar a esta rota e clique em **OK**.
    
    > [!NOTE]  
    > Continue a clicar no botão **Adicionar** para adicionar mais links, ou selecione um link e clique em **Remover** para remover um link.

9.  Clique em **Confirmar**.


### <a name="to-modify-a-network-region-route"></a>Para modificar uma rota de região de rede

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 

3.  Na barra de navegação esquerda, clique em **Configuração de** Rede e clique em **Rota de Região.**

4.  Na página **Rota de Região**, clique no roteiro de região que você deseja alterar.

5.  No menu **Editar**, clique em **Exibir detalhes**.

6.  Em **Editar rota de região**, você pode alterar as regiões associadas por essa rota e os links de região associados ao roteiro.

7.  Clique em **Confirmar**.


## <a name="delete-existing-network-region-routes"></a>Excluir rotas de região de rede existentes

Cada região de um configuração de CAC (controle de admissão de chamadas) deve ter alguma forma de acessar todas as outras regiões. Enquanto os links da região definem limitações nas conexões entre regiões e representam também os links físicos, uma rota determina o caminho vinculado que a conexão percorrerá de uma região a outra. Você pode usar o Painel de Controle do Skype for Business Server para configurar rotas de região de rede. No Painel de Controle do Skype for Business Server, você pode criar, modificar ou excluir uma rota de região de rede. Use este tópico para excluir rotas de região de rede existentes. 

### <a name="to-delete-a-network-region-route"></a>Para excluir uma rota de região de rede

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 

3.  Na barra de navegação esquerda, clique em **Configuração de** Rede e clique em **Rota de Região.**

4.  Na página **Rota de Região**, clique na rota de região que deseja excluir.

    > [!NOTE]  
    > Você pode excluir mais de uma rota de região por vez. Para fazer isso, pressione CTRL e selecione várias rotas de região mantendo pressionada a tecla CTRL. Para selecionar todas as rotas da região, clique em **Selecionar tudo** no menu **Editar**.

5.  No menu **Editar**, clique em **Excluir**.

6.  Clique em **OK**.



## <a name="see-also"></a>Confira também

[Gerenciar regiões de rede no Skype for Business Server](managing-network-regions.md)

[New-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
