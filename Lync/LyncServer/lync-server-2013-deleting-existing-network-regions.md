---
title: 'Lync Server 2013: excluir regiões de rede existentes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting existing network regions
ms:assetid: c7293a2f-2b49-4c4a-903f-f7edcea2bc5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721882(v=OCS.15)
ms:contentKeyID: 49733815
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57af552f82dfb3ca30943fd68c348cd5315b969b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763039"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-existing-network-regions-in-lync-server-2013"></a>Excluindo regiões de rede existentes no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-21_

Uma região de rede interconecta várias partes de uma rede em várias áreas geográficas. Todas as regiões de rede devem estar associadas a um site central. O site central é o site do Data Center no qual o serviço de política de largura de banda do controle de admissão de chamadas (CAC) está em execução. Você pode usar o painel de controle do Lync Server para configurar regiões de rede. As regiões de rede incluem configurações que determinam se caminhos alternativos pela Internet são permitidos para conexões de áudio e vídeo. No painel de controle do Lync Server, você pode criar, modificar ou excluir uma região de rede. Use este tópico para excluir regiões de rede existentes. Para obter detalhes sobre como criar ou modificar regiões de rede existentes, consulte [criando ou modificando regiões de rede no Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).

<div>

## <a name="to-delete-a-network-region"></a>Para excluir uma região de rede

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **configuração de rede** e, em seguida, clique em **região**.

4.  Na página **região** , clique na região que você deseja excluir.
    
    <div>
    

    > [!NOTE]  
    > Você pode excluir mais de uma região de cada vez. Para fazer isso, pressione CTRL e selecione várias regiões enquanto mantém a tecla CTRL pressionada. Ou, para selecionar todas as regiões, clique em <STRONG>selecionar tudo</STRONG> no menu <STRONG>Editar</STRONG> .

    
    </div>

5.  No menu **Editar** , clique em **excluir**.

6.  Clique em **OK**.
    
    <div>
    

    > [!WARNING]  
    > Uma região de rede não poderá ser removida se estiver associada a um site de rede. Se você tentar remover uma região associada a um site, receberá uma mensagem de erro. Para ver se uma região está associada a qualquer site, selecione a região e clique em <STRONG>Mostrar detalhes</STRONG> no menu <STRONG>Editar</STRONG> .

    
    </div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Criando ou modificando regiões de rede no Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

