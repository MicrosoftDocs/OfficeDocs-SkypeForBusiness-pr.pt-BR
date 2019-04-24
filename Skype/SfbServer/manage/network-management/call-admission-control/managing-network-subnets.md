---
title: Gerenciar subredes
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Na maioria das implantações do Skype para Business Server onde o controle de admissão de chamadas (CAC) é implementado, normalmente haverá um grande número de sub-redes. Por esse motivo, geralmente é melhor configurar sub-redes a partir do Skype para Business Server Management Shell.
ms.openlocfilehash: 3b61ad1b4e1eb7f11d61b32c15e337bcd4ff77c8
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32198905"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a>Gerenciar sub-redes de rede no Skype for Business Server

Você pode usar ambos o Skype para painel de controle do Business Server ou o Skype do Shell de gerenciamento do servidor de negócios para gerenciar sub-redes da rede. Na maioria das implantações do Skype para Business Server onde o controle de admissão de chamadas (CAC) é implementado, normalmente haverá um grande número de sub-redes. Por esse motivo, geralmente é melhor configurar sub-redes a partir do Skype para Business Server Management Shell.

Use as seções deste artigo para exibir informações de sub-rede de rede ou criar, modificar ou excluir subredes. 

## <a name="view-network-subnet-information"></a>Exibir informações de sub-rede de rede 

Você pode usar o procedimento a seguir para visualizar uma sub-rede de rede. Skype para painel de controle do Business Server, você pode criar, modificar ou excluir uma sub-rede de rede. 

### <a name="to-view-a-network-subnet"></a>Para visualizar uma sub-rede de rede

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 

3.  Na barra de navegação à esquerda, clique em **Configuração de rede**e clique em **subrede**.

4.  Na página **subrede** , clique na sub-rede que deseja exibir.
 
    > [!NOTE]  
    > Você só pode exibir uma sub-rede por vez.

5.  No menu **Editar**, clique em **Exibir detalhes**.

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a>Exibir informações de configuração da sub-rede de rede pelos cmdlets usando o Windows PowerShell

Informações de sub-rede de rede podem ser exibidas usando o Windows PowerShell e o cmdlet Get-CsNetworkSubnet. Este cmdlet pode ser executado a partir do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell. 

### <a name="to-view-network-subnet-information"></a>Para exibir informações de sub-rede de rede

  - Para exibir informações sobre todas as sub-redes da rede, digite o seguinte comando no Skype do Shell de gerenciamento do servidor de negócios e pressione ENTER:
    
        Get-CsNetworkSubnet
    
    Isso retornará informações parecidas com:
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) .


## <a name="create-or-modify-network-subnets"></a>Criar ou modificar subredes 

Uma sub-rede de rede deve ser associada um site de rede para fins de determinar a localização geográfica do host que pertencem a esta sub-rede. Você pode usar o Skype para painel de controle do Business Server para configurar sub-redes. Skype para painel de controle do Business Server, você pode criar, modificar ou excluir uma sub-rede de rede. 

Na maioria das implantações do Skype para Business Server onde o controle de admissão de chamadas (CAC) é implementado, normalmente haverá um grande número de sub-redes. Por esse motivo, geralmente é melhor configurar sub-redes a partir do Skype para Business Server Management Shell. A partir daí, você pode chamar **New-CsNetworkSubnet** junto com o cmdlet **Import-CSV**do Windows PowerShell. Usando esses cmdlets juntos, você pode ler configurações de sub-rede de um arquivo de valores separados por vírgula (. csv) e criar várias sub-redes ao mesmo tempo. Para obter exemplos de como criar sub-redes de um arquivo. csv, consulte [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).


### <a name="to-create-a-network-subnet"></a>Para criar uma sub-rede de rede

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 

3.  Na barra de navegação à esquerda, clique em **Configuração de rede**e clique em **subrede**.

4.  Na página **subrede** , clique em **novo**.

5.  Na **Nova sub-rede**, insira um valor no campo **ID de sub-rede** . Isso deve ser um endereço IP (por exemplo, 174.11.12.0) e deve ser o primeiro endereço no intervalo de endereços IP definido pela sub-rede.

6.  No campo **máscara** , insira um valor numérico de 1 a 32.

    > [!NOTE]  
    > Esse valor é o bitmask que deve ser aplicada à sub-rede que está sendo criada.

7.  **ID do site de rede**, selecione o site ao qual esta sub-rede pertence.

8.  (Opcional) Digite um valor no campo **Descrição** para fornecer mais informações sobre essa sub-rede que não pode ser expressa somente pelo nome.

9.  Clique em **Confirmar**.


### <a name="to-modify-a-network-subnet"></a>Para modificar uma sub-rede de rede

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 

3.  Na barra de navegação à esquerda, clique em **Configuração de rede**e clique em **subrede**.

4.  Na página **subrede** , clique na sub-rede que deseja modificar.

5.  No menu **Editar**, clique em **Exibir detalhes**.

6.  Na página **Editar sub-rede** , você pode modificar o bitmask, o site de rede associado ou a descrição. Se você modificar o bitmask, tenha em mente que a ID de sub-rede ainda deve ser o primeiro endereço no intervalo de endereços IP definido pela sub-rede.

7.  Clique em **Confirmar**.

## <a name="delete-network-subnets"></a>Excluir subredes

Você pode usar o procedimento a seguir para excluir uma sub-rede. Skype para painel de controle do Business Server, você pode criar, modificar ou excluir uma sub-rede de rede. 

Na maioria das implantações do Skype para Business Server onde o controle de admissão de chamadas (CAC) é implementado, normalmente haverá um grande número de sub-redes. Por esse motivo, geralmente é melhor configurar sub-redes a partir do Skype para Business Server Management Shell. A partir daí, você pode chamar **New-CsNetworkSubnet** junto com o cmdlet **Import-CSV**do Windows PowerShell. Usando esses cmdlets juntos, você pode ler configurações de sub-rede de um arquivo de valores separados por vírgula (. csv) e criar várias sub-redes ao mesmo tempo. Para obter exemplos de como criar sub-redes de um arquivo. csv, consulte [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).


### <a name="to-delete-a-network-subnet"></a>Para excluir uma sub-rede de rede

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 

3.  Na barra de navegação à esquerda, clique em **Configuração de rede**e clique em **subrede**.

4.  Na página **subrede** , clique na sub-rede que deseja excluir.
 
    > [!NOTE]  
    > Você pode excluir mais de uma sub-rede por vez. Para fazer isso, pressione CTRL e selecione várias sub-redes, mantendo pressionada a tecla CTRL. Ou, para selecionar todas as sub-redes, clique em **Selecionar tudo** no menu **Editar** .

5.  No menu **Editar** , clique em **Excluir**.

6.  Clique em **OK**.


## <a name="see-also"></a>Consulte Também

[New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  

[Set-CsNetworkSubnet.](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  

[Remove-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  

[Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
