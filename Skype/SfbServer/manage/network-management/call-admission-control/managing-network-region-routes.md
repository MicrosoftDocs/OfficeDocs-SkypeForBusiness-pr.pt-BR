---
title: Gerenciando rotas de região de rede
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Uma rota de região de rede define a rota entre um par de regiões de rede. Cada par de regiões de rede em sua implantação de controle de admissão de chamadas requer uma rota de região de rede.
ms.openlocfilehash: 174fdd021655f3e338001582a1409107b266582e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279505"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a>Gerenciar roteamento de regiões de rede no Skype for Business Server

Uma *rota de região de rede* define a rota entre um par de regiões de rede. Cada par de regiões de rede em sua implantação de controle de admissão de chamadas requer uma rota de região de rede. Isso permite que cada região da rede dentro da implantação acesse todas as demais regiões. Use os procedimentos deste Artilce para exibir, criar, modificar ou excluir rotas de região de rede.

## <a name="view-network-region-route-information"></a>Exibir informações de rota de região de rede 

Todas as regiões em uma configuração de controle de admissão de chamadas (CAC) devem ter alguma maneira de acessar todas as outras regiões. Enquanto links de região definem as limitações de largura de banda nas conexões entre regiões e também representam os links físicos, uma rota determina qual caminho vinculado a conexão passará de uma região para outra. Use os procedimentos a seguir para exibir as rotas de região de rede existentes no painel de controle do Skype for Business Server ou Shell de gerenciamento do Skype for Business Server. 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a>Para ver as informações de rota de região de rede no painel de controle do Skype for Business Server

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 

3.  Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em **rota de região**.

4.  Na página **rota de região** , clique na rota de região que você deseja exibir.


    > [!NOTE]  
    > Você só pode exibir uma rota de região por vez.


5.  No menu **Editar**, clique em **Exibir detalhes**.


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a>Exibir informações de rota de região de rede usando cmdlets do Windows PowerShell

As informações de rota de região de rede podem ser visualizadas usando o Windows PowerShell e o cmdlet Get-CsNetworkInterRegionRoute. Esse cmdlet pode ser executado no Shell de gerenciamento do Skype for Business Server ou em uma sessão remota do Windows PowerShell. 

### <a name="to-view-network-region-route-information"></a>Para exibir as informações de rota de região de rede

  - Para ver as informações sobre todas as suas rotas de região de rede, digite o seguinte comando no Shell de gerenciamento do Skype for Business Server e pressione ENTER:
    
        Get-CsNetworkInterRegionRoute
    
    Isso retornará informações parecidas com:
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) .


## <a name="create-or-modify-network-region-routes"></a>Criar ou modificar rotas de região de rede

Todas as regiões em uma configuração de controle de admissão de chamadas (CAC) devem ter alguma maneira de acessar todas as outras regiões. Enquanto links de região definem as limitações de largura de banda nas conexões entre regiões e também representam os links físicos, uma rota determina qual caminho vinculado a conexão passará de uma região para outra. Você pode usar o painel de controle do Skype for Business Server para configurar rotas de região de rede. No painel de controle do Skype for Business Server, você pode criar, modificar ou excluir uma rota de região de rede. Use este tópico para criar ou modificar uma rota de região de rede. 

### <a name="to-create-a-network-region-route"></a>Para criar uma rota de região de rede

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 

3.  Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em **rota de região**.

4.  Na página **rota de região** , clique em **novo**.

5.  Em **nova rota de região**, digite um valor no campo **nome** .
   
    > [!NOTE]  
    > Esse valor deve ser exclusivo na implantação do Skype for Business Server.

6.  Na lista suspensa **região \#de rede 1** , selecione uma das duas regiões a serem conectadas por essa rota.

7.  Na lista suspensa **região \#de rede 2** , selecione a outra região para esta rota. Esta região deve ser diferente da região selecionada para a região \#de rede 1.

8.  Use a caixa de listagem de **links de região de rede** para adicionar links de região ao roteiro. Clique no botão **Adicionar** para exibir a página de **link de região** . Clique em um link de região para adicionar a essa rota e, em seguida, clique em **OK**.
    
    > [!NOTE]  
    > Continue a clicar no botão **Adicionar** para adicionar mais links ou selecionar um link e clicar em **remover** para remover um link.

9.  Clique em **Confirmar**.


### <a name="to-modify-a-network-region-route"></a>Para modificar uma rota de região de rede

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 

3.  Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em **rota de região**.

4.  Na página **rota de região** , clique na rota de região que você deseja modificar.

5.  No menu **Editar**, clique em **Exibir detalhes**.

6.  Em **Editar rota de região**, você pode modificar as regiões Unidas por essa rota e os links de região associados à rota.

7.  Clique em **Confirmar**.


## <a name="delete-existing-network-region-routes"></a>Excluir rotas de região de rede existentes

Todas as regiões em uma configuração de controle de admissão de chamadas (CAC) devem ter alguma maneira de acessar todas as outras regiões. Enquanto links de região definem as limitações de largura de banda nas conexões entre regiões e também representam os links físicos, uma rota determina qual caminho vinculado a conexão passará de uma região para outra. Você pode usar o painel de controle do Skype for Business Server para configurar rotas de região de rede. No painel de controle do Skype for Business Server, você pode criar, modificar ou excluir uma rota de região de rede. Use este tópico para excluir as rotas de região de rede existentes. 

### <a name="to-delete-a-network-region-route"></a>Para excluir uma rota de região de rede

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 

3.  Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em **rota de região**.

4.  Na página **rota de região** , clique na rota de região que você deseja excluir.

    > [!NOTE]  
    > Você pode excluir mais de uma rota de região por vez. Para fazer isso, pressione CTRL e selecione várias rotas de região enquanto mantém a tecla CTRL pressionada. Ou, para selecionar todas as rotas de região, clique em **selecionar tudo** no menu **Editar** .

5.  No menu **Editar** , clique em **excluir**.

6.  Clique em **OK**.



## <a name="see-also"></a>Confira também

[Gerenciar regiões de rede no Skype for Business Server](managing-network-regions.md)

[New-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
