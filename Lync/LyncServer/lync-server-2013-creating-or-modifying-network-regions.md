---
title: 'Lync Server 2013: Criando ou modificando regiões de rede'
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
ms.openlocfilehash: fbebccd02b74c4fbfb69225a6397c1dd7cef862d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756275"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-regions-in-lync-server-2013"></a>Criando ou modificando regiões de rede no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

Uma região de rede interconecta várias partes de uma rede em várias áreas geográficas. Todas as regiões de rede devem estar associadas a um site central. O site central é o site do Data Center no qual o serviço de política de largura de banda do controle de admissão de chamadas (CAC) está em execução. Você pode usar o painel de controle do Lync Server para configurar regiões de rede. As regiões de rede incluem configurações que determinam se caminhos alternativos pela Internet são permitidos para conexões de áudio e vídeo. No painel de controle do Lync Server, você pode criar, modificar ou excluir uma região de rede. Use este tópico para criar e modificar regiões de rede. Para obter detalhes sobre como excluir regiões de rede existentes, consulte [excluindo regiões de rede existentes no Lync Server 2013](lync-server-2013-deleting-existing-network-regions.md).

<div>

## <a name="to-create-a-network-region"></a>Para criar uma região de rede

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **configuração de rede** e, em seguida, clique em **região**.

4.  Na página **região** , clique em **novo**.

5.  Na página **nova região** , digite um valor no campo **nome** . Esse valor deve ser exclusivo na implantação do Microsoft Lync Server 2013.

6.  Na lista suspensa **site central** , selecione o site central para esta região de rede.

7.  A caixa de seleção **habilitar caminho alternativo de áudio** está marcada por padrão. Esse campo determina se as chamadas de áudio serão roteadas por meio de um caminho alternativo se a largura de banda adequada não existir no caminho principal. Desmarque essa caixa de seleção apenas se precisar desativar o Offload para a Internet. Se qualquer uma de suas chamadas for chamada pela Internet, essa caixa de seleção deve ser marcada, independentemente das configurações de largura de banda.

8.  A caixa de seleção **habilitar caminho alternativo de vídeo** está marcada por padrão. Esse campo determina se as chamadas com vídeo serão roteadas por meio de um caminho alternativo se a largura de banda adequada não existir no caminho principal. Desmarque essa caixa de seleção apenas se precisar desativar o Offload para a Internet. Se qualquer uma de suas chamadas for chamada pela Internet, essa caixa de seleção deve ser marcada, independentemente das configurações de largura de banda.

9.  Adicionais Digite um valor no campo **Descrição** para fornecer mais informações sobre essa região que não pode ser expressa apenas pelo nome.

10. Clique em **Confirmar**.

A tabela de **sites associados** não é usada para criar uma região de rede. Você associa um site com uma região quando cria ou modifica o site. Para obter detalhes, consulte [criando ou modificando sites de rede no Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).

</div>

<div>

## <a name="to-modify-a-network-region"></a>Para modificar uma região de rede

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **configuração de rede** e, em seguida, clique em **região**.

4.  Na página **região** , clique na região que você deseja modificar.

5.  No menu **Editar**, clique em **Exibir detalhes**.

6.  Na página **Editar região** , você pode modificar as configurações para habilitar e desabilitar caminhos alternativos de áudio e vídeo e alterar a descrição (para obter detalhes, consulte a seção "para criar uma região de rede" anteriormente neste tópico.

7.  Clique em **Confirmar**.

Não é possível modificar os **sites associados** nesta página. A lista de sites associados é fornecida para referência para que você saiba quais sites serão afetados quando você modificar as configurações de região.

</div>

<div>

## <a name="see-also"></a>Confira também


[Excluindo regiões de rede existentes no Lync Server 2013](lync-server-2013-deleting-existing-network-regions.md)  
[Configurar regiões de rede para o CAC no Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md)  


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

