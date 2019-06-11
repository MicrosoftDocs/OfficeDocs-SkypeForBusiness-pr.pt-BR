---
title: 'Lync Server 2013: excluindo perfis de política de largura de banda de rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting network bandwidth policy profiles
ms:assetid: 4d6beda8-6aa5-4d5e-8a07-363598f0e0c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688050(v=OCS.15)
ms:contentKeyID: 49733643
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c33f781e8818dbefa3dc37b3f17c789099e6add
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829581"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-network-bandwidth-policy-profiles-in-lync-server-2013"></a>Excluindo perfis de política de largura de banda de rede no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

Como parte do controle de admissão de chamadas (CAC), uma política de largura de banda é usada para definir limitações de largura de banda para determinadas modalidades. No Microsoft Lync Server 2013, somente as modalidades de áudio e vídeo podem ter limitações de largura de banda atribuídas. Você pode definir limitações gerais de largura de banda e limitações de sessão. Você pode usar o painel de controle do Lync Server para criar, modificar ou excluir um perfil de contêiner para essas políticas. Use os procedimentos a seguir para excluir um perfil de política de largura de banda de rede. Para obter detalhes sobre como criar ou modificar um perfil de política de largura de banda de rede, consulte [criando ou modificando perfis de política de largura de banda no Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).

<div>

## <a name="to-delete-a-bandwidth-policy-profile"></a>Para excluir um perfil de política de largura de banda

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **configuração de rede** e, em seguida, em política de **largura de banda**.

4.  Na página **política de largura de banda** , clique no perfil de política de largura de banda que você deseja excluir.
    
    <div>
    

    > [!NOTE]  
    > Você pode excluir mais de um perfil de cada vez. Para fazer isso, pressione CTRL e selecione vários perfis enquanto mantém a tecla CTRL pressionada. Ou, para selecionar todos os perfis, clique em <STRONG>selecionar tudo</STRONG> no menu <STRONG>Editar</STRONG> .

    
    </div>

5.  No menu **Editar** , clique em **excluir**.
    
    <div>
    

    > [!WARNING]  
    > Não é possível excluir um perfil de política de largura de banda associado a um site de rede. Você deve primeiro remover a associação com o site de rede antes de poder excluir o perfil. Para obter detalhes sobre como modificar o site de rede, consulte <A href="lync-server-2013-creating-or-modifying-network-sites.md">criando ou modificando sites de rede no Lync Server 2013</A>.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Criando ou modificando perfis de política de largura de banda no Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[Exibir informações de perfil da política de largura de banda no Lync Server 2013](lync-server-2013-viewing-network-bandwidth-policy-profile-information.md)  


[Configurar o controle de admissão de chamadas no Lync Server 2013](lync-server-2013-configure-call-admission-control.md)  
[Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

