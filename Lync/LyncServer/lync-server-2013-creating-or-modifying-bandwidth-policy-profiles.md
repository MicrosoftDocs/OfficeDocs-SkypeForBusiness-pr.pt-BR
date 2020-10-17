---
title: 'Lync Server 2013: Criando ou modificando perfis de política de largura de banda'
description: 'Lync Server 2013: Criando ou modificando perfis de política de largura de banda.'
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
ms.openlocfilehash: de8450cf8f4da53bf4a7e096fd7618b7fc6d055b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562967"
---
# <a name="creating-or-modifying-bandwidth-policy-profiles-in-lync-server-2013"></a>Criando ou modificando perfis de política de largura de banda no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-15_

Como parte de um controle de admissão de chamadas (CAC), uma diretiva de largura de banda é utilizada para definir limites para certas modalidades. No Microsoft Lync Server 2013, somente as modalidades de áudio e vídeo podem ser atribuídas a limitações de largura de banda. Você pode configurar os limites gerais de banda e os limites de sessão. Você pode usar o painel de controle do Lync Server para criar, modificar ou excluir um perfil de contêiner para essas políticas. Cada perfil de política de largura de banda pode ser associado a um ou mais sites de rede. Use os procedimentos a seguir para criar ou modificar um perfil de política de largura de banda. Para excluir um perfil de política de largura de banda, consulte [excluindo perfis de política de largura de banda de rede no Lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)

<div>

## <a name="to-create-a-new-bandwidth-policy-profile"></a>Para criar um novo perfil de política de largura de banda

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **Configuração de Rede** e depois em **Política de largura de banda**.

4.  Na página **Política de largura de banda**, clique em **Novo**.

5.  Em **Novo Perfil de Política de Largura de Banda**, digite um nome no campo **Nome**. Esse nome deve ser único entre todos os perfis de política de largura de banda.

6.  No campo **Limite de áudio**, digite um valor numérico. Esse valor é a quantidade máxima de largura de banda a ser alocada a todas as conexões de áudio, expressa em kbps.

7.  Insira um valor numérico no campo **Limite da sessão de áudio**. Esse valor é a quantidade máxima de largura de banda a ser alocada para uma conexão de áudio individual, expressa em kbps. Esse valor precisa ser igual a ou maior que 40.

8.  Insira um valor numérico no campo **Limite de vídeo**. Esse valor é quantidade máxima de largura de banda a ser alocada para todas as conexões de vídeo, expressa em kbps.

9.  Insira um valor numérico no campo **Limite de sessão de vídeo**. Esse valor é a quantidade máxima de largura de banda a ser alocada para uma conexão de vídeo individual, expressa em kbps. Esse valor precisa ser igual a ou maior que 100.

10. (Opcional) Digite um valor no campo **Descrição** para fornecer mais informações sobre esse perfil da política de largura de banda que não pode ser expressa somente pelo nome.

11. Clique em **Confirmar**.
    
    <div>
    

    > [!NOTE]  
    > Criar um novo perfil de política de largura de banda não reforça as restrições de largura de banda automaticamente. É preciso, primeiro, associar o perfil da política com um site. Para obter detalhes sobre como associar um perfil de política a um site, consulte <A href="lync-server-2013-creating-or-modifying-network-sites.md">criando ou modificando sites de rede no Lync Server 2013</A>.

    
    </div>

</div>

<div>

## <a name="to-modify-a-bandwidth-policy-profile"></a>Para modificar um perfil de política de largura de banda

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **Configuração de rede** e clique em **Política de largura de banda**.

4.  Na página **Política de largura de banda**, clique no perfil da política de largura de banda que você quer modificar.

5.  No menu **Editar**, clique em **Mostrar detalhes**.

6.  Na página **Editar Perfil de Política de Largura de Banda**, modifique os campos conforme necessário (para obter mais detalhes, consulte a seção "Para criar um novo perfil de política de largura de banda", já vista neste tópico).

7.  Clique em **Confirmar**.
    
    <div>
    

    > [!NOTE]  
    > Ao modificar o perfil de política de largura de banda, as limitações de largura de banda de todos os sites da rede associados a esse perfil serão atualizadas imediatamente.

    
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

