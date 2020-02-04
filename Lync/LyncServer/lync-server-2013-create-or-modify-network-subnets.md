---
title: 'Lync Server 2013: criar ou modificar sub-redes de rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify network subnets
ms:assetid: 1ba8c4e3-fbc7-4758-88ac-d651fef17bed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520957(v=OCS.15)
ms:contentKeyID: 48183548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d743e5cdbe8dc7f200175b74f55b1b3d003e769
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734251"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-network-subnets-in-lync-server-2013"></a>Criar ou modificar sub-redes de rede no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-21_

Uma sub-rede de rede deve estar associada a um site de rede para fins de determinar a localização geográfica do host pertencente a essa sub-rede. Você pode usar o painel de controle do Lync Server para configurar sub-redes. No painel de controle do Lync Server, você pode criar, modificar ou excluir uma sub-rede de rede. Para obter detalhes sobre como excluir sub-redes de rede, consulte [excluindo sub-redes de rede no Lync Server 2013](lync-server-2013-deleting-network-subnets.md).

Na maioria das implantações do Microsoft Lync Server 2013 em que o controle de admissão de chamadas (CAC) é implementado, normalmente há um grande número de sub-redes. Por isso, geralmente é melhor configurar sub-redes a partir do Shell de gerenciamento do Lync Server. Em seguida, você pode chamar **New-CsNetworkSubnet** em conjunto com o cmdlet **Import-CSV**do Windows PowerShell. Ao usar esses cmdlets juntos, você pode ler as configurações de sub-rede a partir de um arquivo de valores separados por vírgulas (. csv) e criar várias sub-redes ao mesmo tempo. Para obter exemplos de como criar sub-redes a partir de um arquivo. csv, consulte [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).

<div>

## <a name="to-create-a-network-subnet"></a>Para criar uma sub-rede de rede

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **configuração de rede** e, em seguida, clique em **sub-rede**.

4.  Na página **sub-rede** , clique em **novo**.

5.  Em **nova sub-rede**, insira um valor no campo **subnet ID** . Deve ser um endereço IP (por exemplo, 174.11.12.0) e deve ser o primeiro endereço no intervalo de endereços IP definido pela sub-rede.

6.  No campo **máscara** , insira um valor numérico de 1 a 32.
    
    <div>
    

    > [!NOTE]  
    > Esse valor é o bitmask que deve ser aplicado à sub-rede que está sendo criada.

    
    </div>

7.  Em **ID de site de rede**, selecione o site ao qual esta sub-rede pertence.

8.  Adicionais Digite um valor no campo **Descrição** para fornecer mais informações sobre essa sub-rede que não pode ser expressa apenas pelo nome.

9.  Clique em **Confirmar**.

</div>

<div>

## <a name="to-modify-a-network-subnet"></a>Para modificar uma sub-rede de rede

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **configuração de rede** e, em seguida, clique em **sub-rede**.

4.  Na página **sub-rede** , clique na sub-rede que você deseja modificar.

5.  No menu **Editar**, clique em **Exibir detalhes**.

6.  Na página **Editar sub-rede** , você pode modificar o bitmask, o site de rede associado ou a descrição. Se você modificar o bitmask, lembre-se de que a identificação da sub-rede ainda deve ser o primeiro endereço no intervalo de endereços IP definido pela sub-rede.

7.  Clique em **Confirmar**.

</div>

<div>

## <a name="see-also"></a>Confira também


[Excluindo sub-redes de rede no Lync Server 2013](lync-server-2013-deleting-network-subnets.md)  


[Sobre regiões de rede, sites e subredes no Lync Server 2013](lync-server-2013-about-network-regions-sites-and-subnets.md)  


[New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  
[Set-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  
[Remove-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  
[Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

