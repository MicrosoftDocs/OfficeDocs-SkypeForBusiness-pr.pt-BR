---
title: 'Lync Server 2013: Habilitando o controle de admissão de chamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling call admission control
ms:assetid: 015f5c8f-2f90-4b9e-8149-b33767e90582
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520942(v=OCS.15)
ms:contentKeyID: 48183228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b89c9b888dc610d60b2abbcefd4c9c67e9b0572e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735831"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-call-admission-control-in-lync-server-2013"></a>Habilitando o controle de admissão de chamadas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

O serviço de controle de admissão de chamadas (CAC) é uma rede de regiões, sites e sub-redes que permite impor restrições às transmissões de áudio e vídeo com base na largura de banda disponível. Depois de configurar a rede do CAC, você deve habilitar o CAC para impor as limitações de largura de banda. Você pode usar o painel de controle do Lync Server para fazer isso.

<div>

## <a name="to-enable-cac-from-lync-server-control-panel"></a>Para habilitar o CAC do painel de controle do Lync Server

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **configuração de rede** e, em seguida, clique em **global**.

4.  Na página **global** , clique em configuração **global** .
    
    <div>
    

    > [!NOTE]  
    > Somente uma rede pode ser configurada para qualquer implantação do Microsoft Lync Server 2013, portanto, nunca haverá mais de uma configuração de rede na lista. Não é possível renomear a configuração global.

    
    </div>

5.  No menu **Editar**, clique em **Exibir detalhes**.

6.  Na página **Editar configuração global** , marque a caixa de seleção **habilitar controle de admissão de chamadas** e clique em **confirmar**.

Quando você clica em **confirmar**, executa um teste de configuração. A caixa de diálogo **Editar configurações globais** é fechada, retornando você à página **global** . Você receberá um aviso se quaisquer erros ou inconsistências forem descobertos em sua configuração de rede que o impedirá de funcionar corretamente (por exemplo, se cada região não estiver conectada a todas as outras regiões por meio de uma rota entre regiões).

Se você fizer alterações em sua configuração de rede, poderá executar a verificação de validação novamente abrindo a configuração global e clicando em **confirmar**. Você não precisa desabilitar o CAC primeiro: Deixe a caixa de seleção marcada e clique em **confirmar**. Você pode fazer isso a qualquer momento sem fazer alterações de configuração.

</div>

<div>

## <a name="see-also"></a>Confira também


[Visão geral do controle de admissão de chamadas no Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md)  


[Planejamento para controle de admissão de chamada no Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md)  
[Configurar o controle de admissão de chamadas no Lync Server 2013](lync-server-2013-configure-call-admission-control.md)  
[Get-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  
[Set-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  
[Remove-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

