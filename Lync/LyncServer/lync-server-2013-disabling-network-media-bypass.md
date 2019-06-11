---
title: 'Lync Server 2013: desativando o bypass de mídia de rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Disabling network media bypass
ms:assetid: 936d2678-d712-4589-b172-b5793013652f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688141(v=OCS.15)
ms:contentKeyID: 49733741
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9bfab9fbf8174a1124a45681098196c84ac5444
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829377"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disabling-network-media-bypass-in-lync-server-2013"></a>Desativando o bypass de mídia de rede no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-15_

As configurações de bypass de mídia se aplicam globalmente em uma implantação do Microsoft Lync Server 2013. O bypass de mídia permite que as chamadas ignorem o servidor de mediação. Para obter detalhes sobre quando usar o bypass de mídia, consulte [planejando a bypass de mídia no Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) na seção planejamento. Você pode desativar o bypass de mídia no painel de controle do Lync Server. Para obter detalhes sobre como habilitar e configurar o bypass de mídias média, consulte Habilitando o [bypass de mídia de rede no Lync Server 2013](lync-server-2013-enabling-network-media-bypass.md)

<div>

## <a name="to-disable-media-bypass"></a>Para desativar o bypass de mídia

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **configuração de rede** e, em seguida, clique em **global**.

4.  Na página **global** , clique em configuração **global** . Sempre existe apenas uma configuração, e ela é sempre chamada de global.

5.  No menu **Editar** , clique em **Exibir detalhes**.

6.  Na página **Editar configuração global** , desmarque a caixa de seleção **habilitar bypass de mídia** .

7.  Clique em **confirmar** para salvar as alterações.

</div>

<div>

## <a name="see-also"></a>Confira também


[Habilitando o bypass de mídia de rede no Lync Server 2013](lync-server-2013-enabling-network-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

