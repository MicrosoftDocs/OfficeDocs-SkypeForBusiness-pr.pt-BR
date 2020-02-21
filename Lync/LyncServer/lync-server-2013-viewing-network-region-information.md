---
title: 'Lync Server 2013: exibindo informações de região de rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region information
ms:assetid: 665740d0-a3ed-460f-8337-5ed945f90589
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688076(v=OCS.15)
ms:contentKeyID: 49733672
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d59e8182c0ebe904d61dd18e9cd3653f58a6fb4a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211287"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-information-in-lync-server-2013"></a>Exibindo informações de região de rede no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-23_

Uma região de rede interconecta várias partes de uma rede entre várias áreas geográficas. Cada região de rede deve ser associada com um local central. O local central é o local do centro de dados no qual o serviço da política de largura de banda CAC está funcionando. Você pode usar o painel de controle do Lync Server para exibir as regiões de rede. As regiões de rede incluem configurações que determinam se os caminhos alternativos através da Internet são permitidos para conexões de áudio e vídeo. Use este tópico para exibir as regiões de rede existentes. Para obter detalhes sobre como criar ou modificar regiões de rede existentes, consulte [criar ou modificar regiões de rede no Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).

<div>

## <a name="to-view-information-about-a-network-region-with-lync-server-control-panel"></a>Para exibir informações sobre uma região de rede com o painel de controle do Lync Server

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à direita, clique em **Configuração de Rede** e clique em **Região**.

4.  Na página **região** , clique na região que você deseja exibir.
    
    <div>
    

    > [!NOTE]  
    > Você só pode exibir uma região por vez.

    
    </div>

5.  No painel **Ações**, clique em **Mostrar detalhes**.

</div>

<div>

## <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a>Exibindo informações de região de rede usando cmdlets do Windows PowerShell

Você pode exibir as informações de região de rede usando o Windows PowerShell e o cmdlet **Get-CsNetworkRegion** . Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.

<div>

## <a name="to-view-network-region-information"></a>Para exibir informações de região de rede

  - Para exibir informações sobre todas as suas regiões de rede, digite o seguinte comando no Shell de gerenciamento do Lync Server e pressione ENTER:
    
        Get-CsNetworkRegion
    
    Isto retorna informações semelhantes à seguinte:
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

</div>

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) .

</div>

<div>

## <a name="see-also"></a>Confira também


[Criar ou modificar regiões de rede no Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md)  
[Excluindo regiões de rede existentes no Lync Server 2013](lync-server-2013-deleting-existing-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

