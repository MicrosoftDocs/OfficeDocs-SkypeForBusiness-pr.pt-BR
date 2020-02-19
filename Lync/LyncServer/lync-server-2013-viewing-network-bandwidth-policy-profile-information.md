---
title: 'Lync Server 2013: exibindo informações de perfil da política de largura de banda'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network bandwidth policy profile information
ms:assetid: eed453fc-04e9-4971-959c-6fad54bf1c96
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721931(v=OCS.15)
ms:contentKeyID: 49733866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51e0ec43758823666809321c2abe424ce7f480ef
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136548"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-network-bandwidth-policy-profile-information-in-lync-server-2013"></a>Exibindo informações de perfil da política de largura de banda no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-23_

Como parte de um controle de admissão de chamadas (CAC), uma diretiva de largura de banda é utilizada para definir limites para certas modalidades. No Microsoft Lync Server 2013, somente as modalidades de áudio e vídeo podem ser atribuídas a limitações de largura de banda. Você pode configurar os limites gerais de banda e os limites de sessão. Você pode usar o painel de controle do Lync Server para criar, modificar ou excluir um perfil de contêiner para essas políticas. Cada perfil de política de largura de banda pode ser associado a um ou mais sites de rede. Use os procedimentos a seguir para exibir um perfil de política de largura de banda. Para criar ou modificar um perfil de política de largura de banda, consulte [criando ou modificando perfis de política de largura de banda no Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).

<div>

## <a name="to-view-a-bandwidth-policy-profile"></a>Para exibir um perfil de política de largura de banda

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **Configuração de rede** e, em seguida, clique em **Política de largura de banda**.

4.  Na página **política de largura de banda** , clique no perfil de política de largura de banda que você deseja exibir.

5.  No painel **Ações**, clique em **Mostrar detalhes**.

</div>

<div>

## <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a>Exibindo informações de perfil de política de largura de banda usando cmdlets do Windows PowerShell

Os perfis de largura de banda de rede podem ser exibidos usando o Windows PowerShell e o cmdlet Get-CsNetworkBandwidthPolicyProfile. Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.

<div>

## <a name="to-view-network-bandwidth-policy-profile-information"></a>Para exibir informações de perfil da política de largura de banda

  - Para exibir informações sobre todos os perfis de política de largura de banda de rede, digite o seguinte comando no Shell de gerenciamento do Lync Server e pressione ENTER:
    
        Get-CsNetworkBandwidthPolicyProfile
    
    Isto retorna informações semelhantes à seguinte:
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :

</div>

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) .

</div>

<div>

## <a name="see-also"></a>Confira também


[Criando ou modificando perfis de política de largura de banda no Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[Excluindo perfis de política de largura de banda de rede no Lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[Configurar o controle de admissão de chamadas no Lync Server 2013](lync-server-2013-configure-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

