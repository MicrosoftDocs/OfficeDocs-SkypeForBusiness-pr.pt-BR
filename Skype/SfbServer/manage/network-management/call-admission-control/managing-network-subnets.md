---
title: Gerenciando sub-redes de rede
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
description: Na maioria das implantações do Skype for Business Server onde o cac (controle de admissão de chamadas) é implementado, normalmente haverá um grande número de sub-redes. Por isso, geralmente é melhor configurar sub-redes do Shell de Gerenciamento do Skype for Business Server.
ms.openlocfilehash: e2ac69190ab93b4b6d81fed13538cc6fcaa91f20
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816391"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a>Gerenciando sub-redes de rede no Skype for Business Server

Você pode usar o Painel de Controle do Skype for Business Server ou o Shell de Gerenciamento do Skype for Business Server para gerenciar sub-redes de rede. Na maioria das implantações do Skype for Business Server onde o cac (controle de admissão de chamadas) é implementado, normalmente haverá um grande número de sub-redes. Por isso, geralmente é melhor configurar sub-redes do Shell de Gerenciamento do Skype for Business Server.

Use as seções deste artigo para exibir informações de sub-rede de rede ou criar, modificar ou excluir sub-redes de rede. 

## <a name="view-network-subnet-information"></a>Exibir informações da sub-rede da rede 

Você pode utilizar o seguinte procedimento para visualizar uma sub-rede da rede. No Painel de Controle do Skype for Business Server, você pode criar, modificar ou excluir uma sub-rede de rede. 

### <a name="to-view-a-network-subnet"></a>Para visualizar uma sub-rede de rede

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 

3.  Na barra de navegação esquerda, clique em **Configuração de** Rede e em **Sub-rede.**

4.  Na página de **Sub-rede**, clique na sub-rede que deseja visualizar.
 
    > [!NOTE]  
    > Você só pode visualizar uma sub-rede por vez.

5.  No painel **Ações**, clique em **Mostrar detalhes**.

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a>Exibir informações de configuração de sub-rede de rede usando cmdlets do Windows PowerShell

As informações da sub-rede da rede podem ser exibidas usando o Windows PowerShell e o Get-CsNetworkSubnet cmdlet. Esse cmdlet pode ser executado a partir do Shell de Gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell. 

### <a name="to-view-network-subnet-information"></a>Para exibir informações da sub-rede da rede

  - Para exibir informações sobre todas as sub-redes de rede, digite o seguinte comando no Shell de Gerenciamento do Skype for Business Server e pressione ENTER:
    
        Get-CsNetworkSubnet
    
    Isto retorna informações semelhantes à seguinte:
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


Para mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet).


## <a name="create-or-modify-network-subnets"></a>Criar ou modificar sub-redes de rede 

É necessário associar uma subrede da rede com um site de rede para fins de determinar o local geográfico do host que pertence a esta subrede. Você pode usar o Painel de Controle do Skype for Business Server para configurar sub-redes. No Painel de Controle do Skype for Business Server, você pode criar, modificar ou excluir uma sub-rede de rede. 

Na maioria das implantações do Skype for Business Server onde o cac (controle de admissão de chamadas) é implementado, normalmente haverá um grande número de sub-redes. Por isso, geralmente é melhor configurar sub-redes do Shell de Gerenciamento do Skype for Business Server. A partir daí, você **pode chamar New-CsNetworkSubnet** em conjunto com o cmdlet Do Windows PowerShell **Import-CSV**. Usando estes cmdlets em conjunto, é possível ler nas configurações de subrede de um arquivo de valores separados por vírgula (.csv) e criar várias subredes ao mesmo tempo. Para obter exemplos de como criar sub-redes a partir de um arquivo .csv, consulte [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).


### <a name="to-create-a-network-subnet"></a>Para criar uma sub-rede

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 

3.  Na barra de navegação esquerda, clique em **Configuração de** Rede e em **Sub-rede.**

4.  Na página **Sub-rede** clique em **Novo**.

5.  Em **Nova Sub-rede**, digite um valor no campo **ID da sub-rede**. Esse valor deve ser um endereço IP (por exemplo, 174.11.12.0) e deve ser o primeiro endereço no intervalo de endereço IP definido pela sub-rede.

6.  No campo **Máscara**, digite um valor numérico de 1 a 32.

    > [!NOTE]  
    > Este valor é o bitmask que será aplicado na sub-rede criada.

7.  Em **ID do site da rede**, selecione o site ao qual a sub-rede pertence.

8.  (Opcional) Digite um valor no campo **Descrição** para fornecer mais informações essa sub-rede que não pode ser expressa somente pelo nome.

9.  Clique em **Confirmar**.


### <a name="to-modify-a-network-subnet"></a>Para modificar uma sub-rede de rede

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 

3.  Na barra de navegação esquerda, clique em **Configuração de** Rede e em **Sub-rede.**

4.  Na página **Sub-rede**, clique na sub-rede que deseja modificar.

5.  No menu **Editar**, clique **Exibir detalhes**.

6.  Na página **Editar sub-rede**, é possível modificar o bitmask, o local de rede associado ou a descrição. Se for mudar o bitmask, tenha em mente que o ID da sub-rede deve ser ainda o primeiro endereço do intervalo de endereço IP definido pela sub-rede.

7.  Clique em **Confirmar**.

## <a name="delete-network-subnets"></a>Excluir sub-redes de rede

É possível usar o seguinte procedimento para excluir uma subrede. No Painel de Controle do Skype for Business Server, você pode criar, modificar ou excluir uma sub-rede de rede. 

Na maioria das implantações do Skype for Business Server onde o cac (controle de admissão de chamadas) é implementado, normalmente haverá um grande número de sub-redes. Por isso, geralmente é melhor configurar sub-redes do Shell de Gerenciamento do Skype for Business Server. A partir daí, você **pode chamar New-CsNetworkSubnet** em conjunto com o cmdlet Do Windows PowerShell **Import-CSV**. Usando estes cmdlets em conjunto, é possível ler nas configurações de subrede de um arquivo de valores separados por vírgula (.csv) e criar várias subredes ao mesmo tempo. Para ver exemplos de como criar subredes de um arquivo .csv, consulte [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).


### <a name="to-delete-a-network-subnet"></a>Para excluir uma subrede

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 

3.  Na barra de navegação esquerda, clique em **Configuração de** Rede e em **Sub-rede.**

4.  Na página **Subrede**, clique na subrede que deseja excluir.
 
    > [!NOTE]  
    > Você pode excluir mais de uma subrede simultaneamente. Para isso, pressione a tecla CTRL e selecione várias subredes mantendo a tecla CTRL pressionada. Em alternativa, para selecionar todas as subredes, clique em **Selecionar todas** no menu **Editar**.

5.  No menu **Editar**, clique em **Excluir**.

6.  Clique em **OK**.


## <a name="see-also"></a>Confira também

[New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  

[Set-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  

[Remove-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  

[Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
