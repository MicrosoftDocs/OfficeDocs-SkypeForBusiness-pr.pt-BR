---
title: 'Lync Server 2013: Criando ou modificando perfis de política de largura de banda'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying bandwidth policy profiles
ms:assetid: 08a2e18f-9b0d-4a2f-aa14-13bbf79ec745
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520945(v=OCS.15)
ms:contentKeyID: 48183336
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06019464d6d37c601c9077d36c81976d43b6e37c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733681"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-bandwidth-policy-profiles-in-lync-server-2013"></a>Criando ou modificando perfis de política de largura de banda no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-15_

Como parte do controle de admissão de chamadas (CAC), uma política de largura de banda é usada para definir limitações de largura de banda para determinadas modalidades. No Microsoft Lync Server 2013, somente as modalidades de áudio e vídeo podem ter limitações de largura de banda atribuídas. Você pode definir limitações gerais de largura de banda e limitações de sessão. Você pode usar o painel de controle do Lync Server para criar, modificar ou excluir um perfil de contêiner para essas políticas. Cada perfil de política de largura de banda pode ser associado a um ou mais sites de rede. Use os procedimentos a seguir para criar ou modificar um perfil de política de largura de banda. Para excluir um perfil de política de largura de banda, consulte [excluindo perfis de política de largura de banda de rede no Lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)

<div>

## <a name="to-create-a-new-bandwidth-policy-profile"></a>Para criar um novo perfil de política de largura de banda

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **configuração de rede** e, em seguida, em política de **largura de banda**.

4.  Na página **política de largura de banda** , clique em **novo**.

5.  Em **novo perfil de política de largura de banda**, digite um nome no campo **nome** . Esse nome deve ser exclusivo entre todos os perfis de política de largura de banda.

6.  No campo **limite de áudio** , digite um valor numérico. Esse valor é a quantidade máxima de largura de banda a ser alocada para todas as conexões de áudio, expressa em Kbps.

7.  Insira um valor numérico no campo **limite da sessão de áudio** . Esse valor é a quantidade máxima de largura de banda a ser alocada para uma conexão de áudio individual, expressa em Kbps. Esse valor deve ser 40 ou superior.

8.  Insira um valor numérico no campo **limite de vídeo** . Esse valor é a quantidade máxima de largura de banda a ser alocada para todas as conexões de vídeo, expressa em Kbps.

9.  Insira um valor numérico no campo **limite da sessão de vídeo** . Esse valor é a quantidade máxima de largura de banda a ser alocada para uma conexão de vídeo individual, expressa em Kbps. Esse valor deve ser 100 ou superior.

10. Adicionais Digite um valor no campo **Descrição** para fornecer mais informações sobre esse perfil de política de largura de banda que não pode ser expresso apenas com o nome.

11. Clique em **Confirmar**.
    
    <div>
    

    > [!NOTE]  
    > A criação de um novo perfil de política de largura de banda não impõe automaticamente restrições de largura de banda. Você deve primeiro associar o perfil de política a um site. Para obter detalhes sobre como associar um perfil de política a um site, consulte <A href="lync-server-2013-creating-or-modifying-network-sites.md">criando ou modificando sites de rede no Lync Server 2013</A>.

    
    </div>

</div>

<div>

## <a name="to-modify-a-bandwidth-policy-profile"></a>Para modificar um perfil de política de largura de banda

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **configuração de rede** e, em seguida, em política de **largura de banda**.

4.  Na página **política de largura de banda** , clique no perfil de política de largura de banda que você deseja modificar.

5.  No menu **Editar**, clique em **Exibir detalhes**.

6.  Na página **Editar perfil da política de largura de banda** , modifique os campos conforme necessário (para obter detalhes, consulte a seção "para criar um perfil de política de largura de banda" anteriormente neste tópico).

7.  Clique em **Confirmar**.
    
    <div>
    

    > [!NOTE]  
    > Quando você modifica o perfil da política de largura de banda, ele atualiza imediatamente as limitações de largura de banda de todos os sites de rede associados a este perfil de política de largura de banda.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Excluindo perfis de política de largura de banda de rede no Lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[Configurar o controle de admissão de chamadas no Lync Server 2013](lync-server-2013-configure-call-admission-control.md)  
[New-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  
[Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  
[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

