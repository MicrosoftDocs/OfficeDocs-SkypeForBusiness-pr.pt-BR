---
title: Gerenciando rotas de região de rede
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Uma rota de região de rede define a rota entre um par de regiões de rede. Cada par de regiões de rede em sua implantação de controle de admissão de chamada exige uma rota de região de rede.
ms.openlocfilehash: 98d7f0ce8f6cb89aa443c5dc8863afd34c355ff3
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27223154"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a>Gerenciando rotas de região de rede no Skype para Business Server

Uma *rota de região de rede* define a rota entre um par de regiões de rede. Cada par de regiões de rede em sua implantação de controle de admissão de chamada exige uma rota de região de rede. Isso permite que cada região da rede dentro da implantação acesse todas as demais regiões. Use os procedimentos neste artilce para exibir, criar, modificar ou excluir rotas de região de rede.

## <a name="view-network-region-route-information"></a>Exibir informações de rota de região de rede 

Cada região contida em uma configuração de (CAC) do controle de admissão de chamadas deve ter alguma maneira de acessar outra região. Enquanto os links de região definido limitações de largura de banda nas conexões entre regiões e também representam os links físicos, uma rota determina o caminho vinculado que a conexão percorrerá de uma região para outro. Use os procedimentos a seguir para exibir o rotas de região de rede existentes no Skype para painel de controle de servidor de negócios ou Skype do Shell de gerenciamento do servidor de negócios. 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a>Para exibir informações de rota de região de rede no Skype para painel de controle do servidor de negócios

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 

3.  Na barra de navegação à esquerda, clique em **Configuração de rede**e clique em **Rota de região**.

4.  Na página **Rota de região** , clique na rota de região que você deseja exibir.


    > [!NOTE]  
    > Você só pode exibir uma rota de região por vez.


5.  No menu **Editar**, clique em **Exibir detalhes**.


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a>Visualizando informações de rota de região de rede usando Cmdlets do Windows PowerShell

Informações de rota de região de rede podem ser exibidas usando o Windows PowerShell e o cmdlet Get-CsNetworkInterRegionRoute. Este cmdlet pode ser executado a partir do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell. 

### <a name="to-view-network-region-route-information"></a>Para exibir informações de rota de região de rede

  - Para exibir informações sobre todas as suas rotas de região de rede, digite o seguinte comando no Skype do Shell de gerenciamento do servidor de negócios e pressione ENTER:
    
        Get-CsNetworkInterRegionRoute
    
    Isso retornará informações parecidas com:
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) .


## <a name="create-or-modify-network-region-routes"></a>Criar ou modificar rotas de região de rede

Cada região contida em uma configuração de (CAC) do controle de admissão de chamadas deve ter alguma maneira de acessar outra região. Enquanto os links de região definido limitações de largura de banda nas conexões entre regiões e também representam os links físicos, uma rota determina o caminho vinculado que a conexão percorrerá de uma região para outro. Você pode usar o Skype para painel de controle do Business Server para configurar rotas de região de rede. Skype para painel de controle do Business Server, você pode criar, modificar ou excluir uma rota de região de rede. Use este tópico para criar ou modificar uma rota de região de rede. 

### <a name="to-create-a-network-region-route"></a>Para criar uma rota de região de rede

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 

3.  Na barra de navegação à esquerda, clique em **Configuração de rede**e clique em **Rota de região**.

4.  Na página **Rota de região** , clique em **novo**.

5.  Em **nova rota de região**, digite um valor no campo **nome** .
   
    > [!NOTE]  
    > Este valor deve ser exclusivo dentro de sua Skype para implantação de servidor de negócios.

6.  Da **região de rede \#1** lista suspensa, selecione uma das duas regiões que deve ser conectada por esta rota.

7.  Da **região de rede \#2** lista suspensa, selecione a outra região para esta rota. Essa região deve ser diferente da região selecionada para a região de rede \#1.

8.  Use a caixa de listagem de **links de região de rede** para adicionar links de região à rota. Clique no botão **Adicionar** para exibir a página **Link de região** . Clique em um link para adicionar a esta rota de região e clique em **Okey**.
    
    > [!NOTE]  
    > Continue a clicar no botão **Adicionar** para adicionar mais links, ou selecione um link e clique em **Remover** para remover um link.

9.  Clique em **Confirmar**.


### <a name="to-modify-a-network-region-route"></a>Para modificar uma rota de região de rede

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 

3.  Na barra de navegação à esquerda, clique em **Configuração de rede**e clique em **Rota de região**.

4.  Na página **Rota de região** , clique na rota de região que você deseja modificar.

5.  No menu **Editar**, clique em **Exibir detalhes**.

6.  Em **Editar rota de região**, você pode modificar as regiões associadas por essa rota e os links de região associados ao roteiro.

7.  Clique em **Confirmar**.


## <a name="delete-existing-network-region-routes"></a>Excluir rotas de região de rede existentes

Cada região contida em uma configuração de (CAC) do controle de admissão de chamadas deve ter alguma maneira de acessar outra região. Enquanto os links de região definido limitações de largura de banda nas conexões entre regiões e também representam os links físicos, uma rota determina o caminho vinculado que a conexão percorrerá de uma região para outro. Você pode usar o Skype para painel de controle do Business Server para configurar rotas de região de rede. Skype para painel de controle do Business Server, você pode criar, modificar ou excluir uma rota de região de rede. Use este tópico para excluir rotas de região de rede existente. 

### <a name="to-delete-a-network-region-route"></a>Para excluir uma rota de região de rede

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 

3.  Na barra de navegação à esquerda, clique em **Configuração de rede**e clique em **Rota de região**.

4.  Na página **Rota de região** , clique na rota de região que você deseja excluir.

    > [!NOTE]  
    > Você pode excluir mais de uma rota de região por vez. Para fazer isso, pressione CTRL e selecione várias rotas de região, mantendo pressionada a tecla CTRL. Ou, para selecionar todas as rotas de região, clique em **Selecionar tudo** no menu **Editar** .

5.  No menu **Editar** , clique em **Excluir**.

6.  Clique em **OK**.



## <a name="see-also"></a>Consulte Também

[Gerenciando regiões de rede Skype para Business Server](managing-network-regions.md)

[New-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  