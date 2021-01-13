---
title: Vinculando regiões de rede
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
description: 'Você pode configurar links entre duas regiões de rede como parte do controle de admissão de chamadas. '
ms.openlocfilehash: 0a4f5c63b4470fbfe6d2677f0e9e6f52841f7ebb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816461"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a>Vincular regiões de rede no Skype for Business Server

Você pode configurar links entre duas regiões de rede como parte do controle de admissão de chamadas. Use as seções deste artigo para exibir informações de link de região nova ou configurar ou excluir links de região netwrok. 

## <a name="view-network-region-link-information"></a>Exibir informações de link de região de rede 

Você pode visualizar os links entre duas regiões de redes como parte do controle de admissão de chamadas (CAC). Regiões dentro de uma rede são vinculadas por conectividade de WAN física. Você pode usar o Painel de Controle do Skype for Business Server para exibir um link existente entre duas regiões de rede. 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a>Para exibir um link de região de rede no Painel de Controle do Skype for Business Server

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 

3.  Na barra de navegação esquerda, clique em **Configuração de** Rede e clique em **Link de Região.**

4.  Na página **Link da região**, clique no link da região que você deseja ver.
    
    > [!NOTE]  
    > Você pode ver informações somente sobre um link da região por vez.

5.  No menu **Editar**, selecione **Mostras detalhes**.

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a>Exibir informações de link de região de rede usando cmdlets do Windows PowerShell

Você pode exibir links de região de rede usando o Windows PowerShell e o cmdlet **Get-CsNetworkRegionLink.** Você pode executar este cmdlet usando o Shell de gerenciamento do Skype for Business Server ou uma sessão remota do Windows PowerShell. 


### <a name="to-view-network-region-link-information"></a>Para ver informações do link de região de rede

  - Para exibir informações sobre todos os links de região de rede, digite o seguinte comando no Shell de Gerenciamento do Skype for Business Server e pressione ENTER:
    
        Get-CsNetworkRegionLink
    
    Esse comando retornará informações parecidas com:
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California


Para detalhes, consulte [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).


## <a name="configure-network-region-links"></a>Configurar links de região de rede 

Você pode configurar links entre duas regiões de rede como parte do controle de admissão de chamadas. Regiões dentro de uma rede são vinculadas por conectividade de WAN física. Você pode usar o Painel de Controle do Skype for Business Server para definir um link entre duas regiões de rede e definir as limitações de largura de banda em conexões de áudio e vídeo entre essas regiões.

### <a name="to-create-a-network-region-link"></a>Para criar um link de região de rede

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 

3.  Na barra de navegação esquerda, clique em **Configuração de** Rede e clique em **Link de Região.**

4.  Na página **Link de Região**, clique em **Novo**.

5.  Em **Novo Link de Região**, digite um valor no campo **Nome**.
 
    > [!NOTE]  
    > Esse valor deve ser exclusivo em sua implantação do Skype for Business Server.

6.  Na lista **drop-down da Região de rede \# 1,** selecione uma das duas regiões a serem vinculadas.

7.  Na lista drop-down da Região de rede **\# 2,** selecione a outra região a ser vinculada. Essa região deve ser diferente da região selecionada para a Região \# de rede 1.

8.  (Opcional) Se você desejar colocar limites de largura de banda em chamadas de áudio e vídeo entre essas regiões, selecione um perfil de política de largura de banda na lista suspensa **Política de largura de banda**.

9.  Clique em **Confirmar**.

### <a name="to-modify-a-network-region-link"></a>Para modificar um link de região de rede

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 

3.  Na barra de navegação esquerda, clique em **Configuração de** Rede e clique em **Link de Região.**

4.  Na página **Link de Região**, clique no link de região que deseja modificar.

5.  No menu **Editar**, clique em **Exibir detalhes**.

6.  Em **Editar Link de Região**, você pode modificar as regiões que estão vinculadas ou o perfil de política de largura de banda para este link.

7.  Clique em **Confirmar**.


## <a name="delete-network-region-links"></a>Excluir links de região de rede

Você pode configurar links entre duas regiões de rede como parte do controle de admissão de chamadas. Regiões dentro de uma rede são vinculadas por conectividade de WAN física. Você pode usar o Painel de Controle do Skype for Business Server para excluir um link existente entre duas regiões de rede. 

### <a name="to-delete-a-network-region-link"></a>Para excluir um link de região de rede

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 

3.  Na barra de navegação esquerda, clique em **Configuração de** Rede e clique em **Link de Região.**

4.  Na página **Link de** Região, clique no link de região que você deseja excluir.
 
    > [!NOTE]  
    > Você pode excluir mais de um link de região por vez. Para fazer isso, pressione CTRL e selecione vários links de região mantendo pressionada a tecla CTRL. Ou, para selecionar todos os links de região, clique <STRONG>em Selecionar tudo</STRONG> no menu Editar. <STRONG></STRONG>

5.  No menu **Editar,** selecione **Excluir**.

6.  Clique em **OK**.


## <a name="see-also"></a>Confira também

[New-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  

[Set-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  

[Remove-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  

[Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
