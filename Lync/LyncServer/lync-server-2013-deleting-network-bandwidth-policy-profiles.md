---
title: 'Lync Server 2013: excluir perfis de política de largura de banda de rede'
description: 'Lync Server 2013: excluindo perfis de política de largura de banda de rede.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network bandwidth policy profiles
ms:assetid: 4d6beda8-6aa5-4d5e-8a07-363598f0e0c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688050(v=OCS.15)
ms:contentKeyID: 49733643
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69f460d9620158d1857dae41e0033f6d36078868
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552657"
---
# <a name="deleting-network-bandwidth-policy-profiles-in-lync-server-2013"></a>Excluindo perfis de política de largura de banda de rede no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

Como parte de um controle de admissão de chamadas (CAC), uma diretiva de largura de banda é utilizada para definir limites para certas modalidades. No Microsoft Lync Server 2013, somente as modalidades de áudio e vídeo podem ser atribuídas a limitações de largura de banda. Você pode configurar os limites gerais de banda e os limites de sessão. Você pode usar o painel de controle do Lync Server para criar, modificar ou excluir um perfil de contêiner para essas políticas. Use os seguintes procedimentos para excluir um perfil de política de largura de banda de rede. Para obter detalhes sobre como criar ou modificar um perfil de política de largura de banda de rede, consulte [criando ou modificando perfis de política de largura de banda no Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).

<div>

## <a name="to-delete-a-bandwidth-policy-profile"></a>Para excluir um perfil de política de largura de banda

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **Configuração de rede** e, em seguida, clique em **Política de largura de banda**.

4.  Na página **Política de largura de banda**, clique no perfil de política de largura de banda que você deseja excluir.
    
    <div>
    

    > [!NOTE]  
    > Você pode excluir mais de um perfil por vez. Para isso, pressione CTRL e selecione vários perfis mantendo a tecla CTRL pressionada. Ou, para selecionar perfis, clique em <STRONG>Selecionar tudo</STRONG> no menu <STRONG>Editar</STRONG>.

    
    </div>

5.  No menu **Editar**, clique em **Excluir**.
    
    <div>
    

    > [!WARNING]  
    > Você não pode excluir um perfil de política de largura de banda que esteja associado a um site da rede. É preciso primeiro remover a associação com o site antes de poder excluir o perfil. Para obter detalhes sobre como modificar o site de rede, consulte <A href="lync-server-2013-creating-or-modifying-network-sites.md">criando ou modificando sites de rede no Lync Server 2013</A>.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Criando ou modificando perfis de política de largura de banda no Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[Exibindo informações de perfil da política de largura de banda no Lync Server 2013](lync-server-2013-viewing-network-bandwidth-policy-profile-information.md)  


[Configurar o controle de admissão de chamadas no Lync Server 2013](lync-server-2013-configure-call-admission-control.md)  
[Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

