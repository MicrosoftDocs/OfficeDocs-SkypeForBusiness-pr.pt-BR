---
title: 'Lync Server 2013: excluindo regiões de rede existentes'
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
ms.openlocfilehash: c3a1c1e697e681eec4886dca9e942d9bc133b0f5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525398"
---
# <a name="deleting-existing-network-regions-in-lync-server-2013"></a>Excluindo regiões de rede existentes no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-21_

Uma região de rede interconecta várias partes de uma rede entre várias áreas geográficas. Cada região de rede deve ser associada com um local central. O local central é o local do centro de dados no qual o serviço da política de largura de banda CAC está funcionando. Você pode usar o painel de controle do Lync Server para configurar as regiões de rede. As regiões de rede incluem configurações que determinam se os caminhos alternativos através da Internet são permitidos para conexões de áudio e vídeo. No painel de controle do Lync Server, você pode criar, modificar ou excluir uma região de rede. Use este tópico para excluir regiões de rede existentes. Para obter detalhes sobre como criar ou modificar regiões de rede existentes, consulte [criar ou modificar regiões de rede no Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).

<div>

## <a name="to-delete-a-network-region"></a>Para excluir uma região de rede

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à direita, clique em **Configuração de Rede** e clique em **Região**.

4.  Na página **Região**, clique na região que você deseja excluir.
    
    <div>
    

    > [!NOTE]  
    > É possível excluir mais de uma região por vez. Para fazer isso, pressione CTRL e selecione várias regiões enquanto mantém pressionada a tecla CTRL. Ou, para selecionar todas as regiões, clique em <STRONG>Selecionar tudo</STRONG> no menu <STRONG>Editar</STRONG>.

    
    </div>

5.  No menu **Editar**, clique em **Excluir**.

6.  Clique em **OK**.
    
    <div>
    

    > [!WARNING]  
    > Uma região de rede não pode ser removida se estiver associada a um site de rede. Se você quiser tentar remover uma região associada a um site, receberá uma mensagem de erro. Para ver se um região está associada a algum site, selecione a região e clique em <STRONG>Mostrar detalhes</STRONG> no menu <STRONG>Editar</STRONG>.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Criar ou modificar regiões de rede no Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

