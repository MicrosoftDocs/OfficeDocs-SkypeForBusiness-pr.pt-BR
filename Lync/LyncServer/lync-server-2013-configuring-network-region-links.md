---
title: 'Lync Server 2013: Configurando links de região de rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring network region links
ms:assetid: 952bc93e-e6aa-4539-85c7-2b15f14eb382
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182551(v=OCS.15)
ms:contentKeyID: 48184829
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13204945482c130c65aea7725db5e06a1eb5a3da
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134727"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-network-region-links-in-lync-server-2013"></a>Configurando links de região de rede no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

Você pode configurar links entre duas regiões de rede como parte do controle de admissão de chamadas. Regiões dentro de uma rede são vinculadas por conectividade de WAN física. Você pode usar o painel de controle do Lync Server para definir um link entre duas regiões de rede e definir as limitações de largura de banda em conexões de áudio e vídeo entre essas regiões. Para obter detalhes sobre como excluir um link de região de rede existente, consulte [excluindo links de região de rede no Lync Server 2013](lync-server-2013-deleting-network-region-links.md).

<div>

## <a name="to-create-a-network-region-link"></a>Para criar um link de região de rede

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Configuração da rede** e em **Link da região**.

4.  Na página **Link de Região**, clique em **Novo**.

5.  Em **Novo Link de Região**, digite um valor no campo **Nome**.
    
    <div>
    

    > [!NOTE]  
    > Esse valor deve ser exclusivo na sua implantação do Lync Server 2013.

    
    </div>

6.  Na lista suspensa **região \#de rede 1** , selecione uma das duas regiões a serem vinculadas.

7.  Na lista suspensa **região \#de rede 2** , selecione a outra região a ser vinculada. Essa região deve ser diferente da região selecionada para a região \#de rede 1.

8.  (Opcional) Se você desejar colocar limites de largura de banda em chamadas de áudio e vídeo entre essas regiões, selecione um perfil de política de largura de banda na lista suspensa **Política de largura de banda**.

9.  Clique em **Confirmar**.

</div>

<div>

## <a name="to-modify-a-network-region-link"></a>Para modificar um link de região de rede

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **Configuração de Rede** e em **Link de Região**.

4.  Na página **Link de Região**, clique no link de região que deseja modificar.

5.  No menu **Editar**, clique em **Exibir detalhes**.

6.  Em **Editar Link de Região**, você pode modificar as regiões que estão vinculadas ou o perfil de política de largura de banda para este link.

7.  Clique em **Confirmar**.

</div>

<div>

## <a name="see-also"></a>Confira também


[Excluindo links de região de rede no Lync Server 2013](lync-server-2013-deleting-network-region-links.md)  


[New-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  
[Set-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  
[Remove-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  
[Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
