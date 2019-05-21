---
title: Gerenciando sub-redes de rede
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Na maioria das implantações do Skype for Business Server onde o controle de admissão de chamadas (CAC) é implementado, normalmente há um grande número de sub-redes. Por isso, geralmente é melhor configurar sub-redes a partir do Shell de gerenciamento do Skype for Business Server.
ms.openlocfilehash: 354dd43fd526ba2a6c6f88c8e1f30d0aae37b3bb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279477"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a>Gerenciar sub-redes de rede no Skype for Business Server

Você pode usar o painel de controle do Skype for Business Server ou o Shell de gerenciamento do Skype for Business Server para gerenciar sub-redes de rede. Na maioria das implantações do Skype for Business Server onde o controle de admissão de chamadas (CAC) é implementado, normalmente há um grande número de sub-redes. Por isso, geralmente é melhor configurar sub-redes a partir do Shell de gerenciamento do Skype for Business Server.

Use as seções deste artigo para exibir as informações de sub-rede da rede ou criar, modificar ou excluir sub-redes de rede. 

## <a name="view-network-subnet-information"></a>Exibir informações de sub-rede da rede 

Você pode usar o procedimento a seguir para exibir uma sub-rede de rede. No painel de controle do Skype for Business Server, você pode criar, modificar ou excluir uma sub-rede de rede. 

### <a name="to-view-a-network-subnet"></a>Para exibir uma sub-rede de rede

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 

3.  Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em **sub-rede**.

4.  Na página **sub-rede** , clique na sub-rede que você deseja exibir.
 
    > [!NOTE]  
    > Você só pode exibir uma sub-rede de cada vez.

5.  No menu **Editar**, clique em **Exibir detalhes**.

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a>Exibir informações de configuração de sub-rede de rede usando cmdlets do Windows PowerShell

As informações de sub-rede da rede podem ser visualizadas usando o Windows PowerShell e o cmdlet Get-CsNetworkSubnet. Esse cmdlet pode ser executado no Shell de gerenciamento do Skype for Business Server ou em uma sessão remota do Windows PowerShell. 

### <a name="to-view-network-subnet-information"></a>Para ver as informações de sub-rede da rede

  - Para ver as informações sobre todas as suas sub-redes de rede, digite o seguinte comando no Shell de gerenciamento do Skype for Business Server e pressione ENTER:
    
        Get-CsNetworkSubnet
    
    Isso retornará informações parecidas com:
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) .


## <a name="create-or-modify-network-subnets"></a>Criar ou modificar sub-redes de rede 

Uma sub-rede de rede deve estar associada a um site de rede para fins de determinar a localização geográfica do host pertencente a essa sub-rede. Você pode usar o painel de controle do Skype for Business Server para configurar sub-redes. No painel de controle do Skype for Business Server, você pode criar, modificar ou excluir uma sub-rede de rede. 

Na maioria das implantações do Skype for Business Server onde o controle de admissão de chamadas (CAC) é implementado, normalmente há um grande número de sub-redes. Por isso, geralmente é melhor configurar sub-redes a partir do Shell de gerenciamento do Skype for Business Server. Em seguida, você pode chamar **New-CsNetworkSubnet** em conjunto com o cmdlet **Import-CSV**do Windows PowerShell. Ao usar esses cmdlets juntos, você pode ler as configurações de sub-rede a partir de um arquivo de valores separados por vírgulas (. csv) e criar várias sub-redes ao mesmo tempo. Para obter exemplos de como criar sub-redes a partir de um arquivo. csv, consulte [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).


### <a name="to-create-a-network-subnet"></a>Para criar uma sub-rede de rede

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 

3.  Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em **sub-rede**.

4.  Na página **sub-rede** , clique em **novo**.

5.  Em **nova sub-rede**, insira um valor no campo **subnet ID** . Deve ser um endereço IP (por exemplo, 174.11.12.0) e deve ser o primeiro endereço no intervalo de endereços IP definido pela sub-rede.

6.  No campo **máscara** , insira um valor numérico de 1 a 32.

    > [!NOTE]  
    > Esse valor é o bitmask que deve ser aplicado à sub-rede que está sendo criada.

7.  Em **ID de site de rede**, selecione o site ao qual esta sub-rede pertence.

8.  Adicionais Digite um valor no campo **Descrição** para fornecer mais informações sobre essa sub-rede que não pode ser expressa apenas pelo nome.

9.  Clique em **Confirmar**.


### <a name="to-modify-a-network-subnet"></a>Para modificar uma sub-rede de rede

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 

3.  Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em **sub-rede**.

4.  Na página **sub-rede** , clique na sub-rede que você deseja modificar.

5.  No menu **Editar**, clique em **Exibir detalhes**.

6.  Na página **Editar sub-rede** , você pode modificar o bitmask, o site de rede associado ou a descrição. Se você modificar o bitmask, lembre-se de que a identificação da sub-rede ainda deve ser o primeiro endereço no intervalo de endereços IP definido pela sub-rede.

7.  Clique em **Confirmar**.

## <a name="delete-network-subnets"></a>Excluir sub-redes de rede

Você pode usar o procedimento a seguir para excluir uma sub-rede. No painel de controle do Skype for Business Server, você pode criar, modificar ou excluir uma sub-rede de rede. 

Na maioria das implantações do Skype for Business Server onde o controle de admissão de chamadas (CAC) é implementado, normalmente há um grande número de sub-redes. Por isso, geralmente é melhor configurar sub-redes a partir do Shell de gerenciamento do Skype for Business Server. Em seguida, você pode chamar **New-CsNetworkSubnet** em conjunto com o cmdlet **Import-CSV**do Windows PowerShell. Ao usar esses cmdlets juntos, você pode ler as configurações de sub-rede a partir de um arquivo de valores separados por vírgulas (. csv) e criar várias sub-redes ao mesmo tempo. Para obter exemplos de como criar sub-redes a partir de um arquivo. csv, consulte [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).


### <a name="to-delete-a-network-subnet"></a>Para excluir uma sub-rede de rede

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 

3.  Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em **sub-rede**.

4.  Na página **sub-rede** , clique na sub-rede que você deseja excluir.
 
    > [!NOTE]  
    > Você pode excluir mais de uma sub-rede de cada vez. Para fazer isso, pressione CTRL e selecione várias sub-redes enquanto mantém a tecla CTRL pressionada. Ou, para selecionar todas as sub-redes, clique em **selecionar tudo** no menu **Editar** .

5.  No menu **Editar** , clique em **excluir**.

6.  Clique em **OK**.


## <a name="see-also"></a>Confira também

[New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  

[Set-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  

[Remove-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  

[Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
