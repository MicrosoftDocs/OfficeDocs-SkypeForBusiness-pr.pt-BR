---
title: 'Lync Server 2013: Habilitando o bypass de mídia de rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling network media bypass
ms:assetid: 95c4fa06-49d3-41ac-acdc-7dcda66e5508
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182552(v=OCS.15)
ms:contentKeyID: 48184846
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca09c54b324f07361a7333fc577a2b3b9e35aaef
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030484"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-network-media-bypass-in-lync-server-2013"></a>Habilitando o bypass de mídia de rede no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

As configurações de bypass de mídia são aplicadas globalmente em uma implantação do Microsoft Lync Server 2013. O desvio de mídia permite que chamadas ignorem o Servidor de Mediação. Para obter detalhes sobre quando usar o bypass de mídia, consulte [Planning for Media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) na seção Planning.

Você pode habilitar e configurar o bypass de mídia no painel de controle do Lync Server.

<div>

## <a name="to-enable-and-configure-media-bypass"></a>Para habilitar e configurar o desvio de mídia

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **Configuração da Rede** e clique em **Global**.

4.  Na página **Global**, clique na configuração **Global**. Sempre existe somente uma configuração, sempre chamada Global.

5.  No menu **Editar**, clique em **Exibir detalhes**.

6.  Na página **Editar Configuração Global**, clique na opção **Habilitar desvio de mídia**.

7.  Selecione uma das seguintes opções:
    
      - **Sempre ignorar**   Selecione essa opção para tentar o bypass de mídia em todas as chamadas. Esta opção estará indisponível se o controle de admissão de chamadas (CAC) estiver habilitado. Se o CAC não estiver habilitado, selecione esta opção nas seguintes situações:
        
          - Não existe a necessidade de controle de largura de banda.
        
          - Não existe a necessidade de uma configuração refinada para determinar quando o desvio deve acontecer.
        
          - Existe conectividade total entre gateways e clientes.
    
      - **Usar a configuração**   de sites e regiões se o CAC estiver habilitado, essa opção será selecionada por padrão e não poderá ser alterada. Quando esta opção está selecionada, a configuração de rede de sites e regiões será usada para determinar quando o desvio de mídia será possível. Se esta opção for selecionada, você pode optar por habilitar o desvio para sites que não estão mapeados. Clique na opção **Habilitar desvio para sites não mapeados** somente se você tiver um ou mais sites grandes associados à mesma região, que não possuem restrições de largura de banda (por exemplo, um site central grande) e se tiver também alguns sites de filial associados à mesma região que executa as restrições de largura de banda. Ao habilitar o desvio para sites não mapeados, a configuração é eficiente porque somente as sub-redes associadas aos sites de filial são especificadas, em vez da necessidade de especificas todas as sub-redes associadas as todos os sites. É recomendável não selecionar a opção **Habilitar desvio para sites não mapeados** se o CAC estiver habilitado.

8.  Clique em **Confirmar** para salvar suas alterações.

</div>

<div>

## <a name="see-also"></a>Confira também


[Desabilitando o bypass de mídia de rede no Lync Server 2013](lync-server-2013-disabling-network-media-bypass.md)  


[Opções de bypass de mídia global no Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  


[Planejamento de bypass de mídia no Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

