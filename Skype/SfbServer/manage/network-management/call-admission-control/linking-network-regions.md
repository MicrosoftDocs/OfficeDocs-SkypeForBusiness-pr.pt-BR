---
title: Vinculando regiões de rede
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
description: 'Você pode configurar links entre duas regiões de rede como parte do controle de admissão de chamadas. '
---


# <a name="linking-network-regions-in-skype-for-business-server"></a>Vincular regiões de rede no Skype for Business Server

Você pode configurar links entre duas regiões de rede como parte do controle de admissão de chamadas. Use as seções deste artigo para exibir informações de link de região de trabalho mais recente ou configurar ou excluir links de região netwrok. 

## <a name="view-network-region-link-information"></a>Exibir informações de link de região de rede 

Você pode visualizar os links entre duas regiões de redes como parte do controle de admissão de chamadas (CAC). Regiões dentro de uma rede são vinculadas por conectividade de WAN física. Você pode usar o painel Skype for Business Server de controle para exibir um link existente entre duas regiões de rede. 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a>Para exibir um link de região de rede no Skype for Business Server Painel de Controle

1.  De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou é atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. 

3.  Na barra de navegação esquerda, clique em **Configuração de** Rede e clique em **Link de Região**.

4.  Na página **Link da região**, clique no link da região que você deseja ver.
    
    > [!NOTE]
    > Você pode ver informações somente sobre um link da região por vez.

5.  No menu **Editar**, selecione **Mostras detalhes**.

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a>Exibir informações de link de região de rede usando Windows PowerShell cmdlets

Você pode exibir links de região de rede usando Windows PowerShell e o cmdlet **Get-CsNetworkRegionLink**. Você pode executar este cmdlet usando o Shell de gerenciamento do Skype for Business Server ou uma sessão remota do Windows PowerShell. 


### <a name="to-view-network-region-link-information"></a>Para ver informações do link de região de rede

  - Para exibir informações sobre todos os links de região de rede, digite o seguinte comando no Shell de Gerenciamento Skype for Business Server e pressione ENTER:
    
    **Get-CsNetworkRegionLink**
    
    Esse comando retornará informações parecidas com:
    
       Identidade : NorthwestToCalifornia BWPolicyProfileID : NetworkRegionLinkID : NorthwestToCalifornia NetworkRegionID1 : Pacific Northwest NetworkRegionID2 : Califórnia


Para detalhes, consulte [Get-CsNetworkRegionLink](/powershell/module/skype/Get-CsNetworkRegionLink).


## <a name="configure-network-region-links"></a>Configurar links de região de rede 

Você pode configurar links entre duas regiões de rede como parte do controle de admissão de chamadas. Regiões dentro de uma rede são vinculadas por conectividade de WAN física. Você pode usar o painel Skype for Business Server de controle para definir um link entre duas regiões de rede e definir as limitações de largura de banda em conexões de áudio e vídeo entre essas regiões.

### <a name="to-create-a-network-region-link"></a>Para criar um link de região de rede

1.  De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou é atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. 

3.  Na barra de navegação esquerda, clique em **Configuração de** Rede e clique em **Link de Região**.

4.  Na página **Link de Região**, clique em **Novo**.

5.  Em **Novo Link de Região**, digite um valor no campo **Nome**.
 
    > [!NOTE]  
    > Esse valor deve ser exclusivo em sua Skype for Business Server implantação.

6.  Na lista **listada \#** da região de rede 1, selecione uma das duas regiões a serem vinculadas.

7.  Na lista **listada \#** da região de rede 2, selecione a outra região a ser vinculada. Essa região deve ser diferente da região selecionada para a região de rede \#1.

8.  (Opcional) Se você desejar colocar limites de largura de banda em chamadas de áudio e vídeo entre essas regiões, selecione um perfil de política de largura de banda na lista suspensa **Política de largura de banda**.

9.  Clique em **Confirmar**.

### <a name="to-modify-a-network-region-link"></a>Para modificar um link de região de rede

1.  De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou é atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. 

3.  Na barra de navegação esquerda, clique em **Configuração de** Rede e clique em **Link de Região**.

4.  Na página **Link de Região**, clique no link de região que deseja modificar.

5.  No menu **Editar**, clique em **Exibir detalhes**.

6.  Em **Editar Link de Região**, você pode modificar as regiões que estão vinculadas ou o perfil de política de largura de banda para este link.

7.  Clique em **Confirmar**.


## <a name="delete-network-region-links"></a>Excluir links de região de rede

Você pode configurar links entre duas regiões de rede como parte do controle de admissão de chamadas. Regiões dentro de uma rede são vinculadas por conectividade de WAN física. Você pode usar o painel Skype for Business Server de controle para excluir um link existente entre duas regiões de rede. 

### <a name="to-delete-a-network-region-link"></a>Para excluir um link de região de rede

1.  De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou é atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. 

3.  Na barra de navegação esquerda, clique em **Configuração de** Rede e clique em **Link de Região**.

4.  Na página **Link da Região** , clique no link de região que você deseja excluir.
 
    > [!NOTE]  
    > Você pode excluir mais de um link de região por vez. Para fazer isso, pressione CTRL e selecione vários links de região ao segurar a tecla CTRL. Ou, para selecionar todos os links de região, clique <STRONG>em Selecionar tudo</STRONG> <STRONG>no menu</STRONG> Editar.

5.  No menu **Editar** , selecione **Excluir**.

6.  Clique em **OK**.


## <a name="see-also"></a>Confira Também

[New-CsNetworkRegionLink](/powershell/module/skype/New-CsNetworkRegionLink)  

[Set-CsNetworkRegionLink](/powershell/module/skype/Set-CsNetworkRegionLink)  

[Remove-CsNetworkRegionLink](/powershell/module/skype/Remove-CsNetworkRegionLink)  

[Get-CsNetworkRegionLink](/powershell/module/skype/Get-CsNetworkRegionLink)