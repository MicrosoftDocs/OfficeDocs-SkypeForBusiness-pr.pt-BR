---
title: 'Lync Server 2013: criar ou modificar regiões de rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network regions
ms:assetid: bd08bb66-5976-4ece-b45c-7de19569f814
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182579(v=OCS.15)
ms:contentKeyID: 48185266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04f85e4546d8cfa3154c2fc5a87676ff0377795b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030965"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-regions-in-lync-server-2013"></a>Criar ou modificar regiões de rede no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

Uma região de rede interconecta várias partes de uma rede entre várias áreas geográficas. Cada região de rede deve ser associada com um local central. O local central é o local do centro de dados no qual o serviço da política de largura de banda CAC está funcionando. Você pode usar o painel de controle do Lync Server para configurar as regiões de rede. As regiões de rede incluem configurações que determinam se os caminhos alternativos através da Internet são permitidos para conexões de áudio e vídeo. No painel de controle do Lync Server, você pode criar, modificar ou excluir uma região de rede. Use este tópico para criar e modificar regiões de rede. Para obter detalhes sobre como excluir regiões de rede existentes, consulte [excluindo regiões de rede existentes no Lync Server 2013](lync-server-2013-deleting-existing-network-regions.md).

<div>

## <a name="to-create-a-network-region"></a>Para criar uma região de rede

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à direita, clique em **Configuração de Rede** e clique em **Região**.

4.  Na página **Região**, clique em **Novo**.

5.  Na página **Nova Região**, digite um valor no campo **Nome**. Esse valor deve ser exclusivo na sua implantação do Microsoft Lync Server 2013.

6.  Na lista suspensa **Site central**, selecione o site central para essa região de rede.

7.  A caixa de seleção **Habilitar caminho alternativo do áudio** está marcada por padrão. Esse campo determina se as chamadas de áudio serão roteadas por um caminho alternativo, caso a largura de banda adequada não exista no caminho primário. Desmarque essa caixa de seleção somente se precisar desativar o descarregamento para a Internet. Se qualquer uma de suas chamadas for uma chamada pela Internet, essa caixa de seleção deverá ser marcada, independente das configurações de largura de banda.

8.  A caixa de seleção **Habilitar caminho alternativo do vídeo** está marcada por padrão. Esse campo determina se as chamadas de vídeo serão roteadas por um caminho alternativo, caso a largura de banda adequada não exista no caminho primário. Desmarque essa caixa de seleção somente se precisar desativar o descarregamento para a Internet. Se qualquer uma de suas chamadas for uma chamada pela Internet, essa caixa de seleção deverá ser marcada, independente das configurações de largura de banda.

9.  (Opcional) Digite um valor no campo **Descrição** para fornecer mais informações sobre essa região que não podem ser expressas somente pelo nome.

10. Clique em **Confirmar**.

A tabela **Sites associados** não é usada para criar uma região de rede. Você associa um site a uma região quando cria ou modifica o site. Para obter detalhes, consulte [criando ou modificando sites de rede no Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).

</div>

<div>

## <a name="to-modify-a-network-region"></a>Para modificar uma região de rede

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à direita, clique em **Configuração de Rede** e clique em **Região**.

4.  Na página **Região**, clique na região que você deseja modificar.

5.  No menu **Editar**, clique em **Mostrar detalhes**.

6.  Na página **Editar Região**, é possível modificar as configurações para habilitar e desabilitar caminhos alternativos de áudio e vídeo e alterar a descrição (para obter detalhes, consulte a seção "Para criar uma região de rede" acima neste tópico.

7.  Clique em **Confirmar**.

Não é possível modificar os **Sites associados** nesta página. A lista de sites associados é fornecida para referência de modo que você fique ciente de quais sites serão afetados quando você modificar as configurações de região.

</div>

<div>

## <a name="see-also"></a>Confira também


[Excluindo regiões de rede existentes no Lync Server 2013](lync-server-2013-deleting-existing-network-regions.md)  
[Configurar regiões de rede para CAC no Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md)  


[New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  
[Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  
[Remove-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  
[Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

