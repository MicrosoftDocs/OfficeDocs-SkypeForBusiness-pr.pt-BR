---
title: Definir as configurações globais de bypass de mídia para usar informações locais e da região
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure media bypass global settings to use site and region information
ms:assetid: 0a21cdf1-f350-49da-b346-70806f256bea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398150(v=OCS.15)
ms:contentKeyID: 48183360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd070e6380a896548b851ac7d3472cd86eeba75b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836359"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-global-settings-in-lync-server-2013-to-use-site-and-region-information"></a>Configure media bypass global settings in Lync Server 2013 to use site and region information

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-21_

<div>


> [!NOTE]
> Este tópico pressupõe que você já configurou a bypass de mídia para todas as conexões de tronco do servidor de mediação para um par (um gateway PSTN (rede telefônica pública comutada), um PBX IP ou um controlador de borda de sessão (SBC) em um serviço de telefonia pela Internet Provedor (ITSP) para um site ou serviço específico para o qual você deseja que a mídia ignore o servidor de mediação.<BR>Este tópico também pressupõe que você definiu todos os sites centrais e sites de ramificação no construtor de topologias de uma maneira que corresponde à região de rede, ao site de rede e à configuração de sub-rede que você executou de acordo com as etapas em <A href="lync-server-2013-create-or-modify-a-network-region.md">criar ou modificar uma região de rede no Lync Server 2013</A>, <A href="lync-server-2013-create-or-modify-a-network-site.md">criar ou modificar um site de rede no lync Server 2013</A>e <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">associar uma sub-rede a um site de rede no Lync Server 2013</A>. Se eles não corresponderem, o bypass do Media não será bem-sucedido.



</div>

Além de habilitar a bypass de mídia para conexões de tronco individuais associadas a um par, você também deve definir configurações globais. Se você usar as etapas deste tópico para definir configurações globais para bypass de mídia, pressupõe-se que uma ou ambas as situações a seguir afetem sua configuração:

  - Você *não* tem uma boa conectividade entre os pontos de extremidade do Lync Server e os pares para os quais configurou a mídia ignorada na conexão do tronco.

  - O controle de admissão de chamadas (CAC) para gerenciamento de largura de banda está habilitado.
    
    <div>
    

    > [!NOTE]
    > Para obter detalhes sobre as considerações para o controle de admissão de chamadas e o bypass de mídia, consulte a seção "controle de admissão de chamadas de conexão PSTN" em <A href="lync-server-2013-media-bypass-and-mediation-server.md">ignorar mídias e servidor de mediação no Lync Server 2013</A> na documentação de planejamento.

    
    </div>

As informações de região de rede e de site de rede são compartilhadas entre os recursos avançados do Enterprise Voice de controle de admissão de chamadas e de desvio de mídia quando os dois estão habilitados. Portanto, se você já configurou o controle de admissão de chamadas, não é preciso usar o procedimento a seguir para editar as informações do site e da região especificamente para o bypass de mídia. Siga as etapas neste procedimento se você ainda não tiver configurado as regiões e os sites de rede quanto ao controle de admissão de chamadas e se quiser alterar as configurações do bypass de chamada.

Ou siga estas etapas se quiser usar as informações de site e região para tomar a decisão de ignorar, mas não tiver intenção de habilitar o controle de admissão de chamadas. Nesse caso, os links restritos de largura de banda ainda precisarão ser representados pelas políticas entre sites de rede, conforme descrito em [criar políticas entre sites de rede no Lync Server 2013](lync-server-2013-create-network-intersite-policies.md). As restrições de largura de banda reais não são tão importantes nesse caso porque o controle de admissão de chamadas não foi habilitado. Em vez disso, esses links são usados para sub-redes de partição para especificar aqueles que não têm limites de largura de banda e podem, portanto, empregar o bypass de mídia. Observe que isso também é verdadeiro quando o controle de admissão de chamadas e o bypass de mídia estão habilitados.

Além disso, para bypass funcionar corretamente, deve haver consistência entre um site conforme definido no construtor de topologias e conforme é definido quando você configura regiões de rede e sites de rede. Por exemplo, se você tiver um site de ramificação que você definiu no construtor de topologias como tendo apenas um gateway PSTN implantado, esse site de filial deve ser configurado com uma política de voz empresarial que permita que os usuários do site de filial tenham suas chamadas PSTN roteadas por meio da PSTN Gateway no site da filial.

<div>

## <a name="to-configure-site-and-region-information-for-media-bypass"></a>Para configurar informações de site e de região para bypass de mídia

1.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Na barra de navegação esquerda, clique em **Configuração de rede**.

3.  Dê dois cliques na configuração **Global** na tabela.

4.  Na página **Editar Configuração Global**, marque a caixa de seleção **Ativar bypass de mídia**.

5.  Clique em **Usar as configurações de sites e região**.

6.  Se necessário, marque a caixa de seleção **Habilitar bypass de mídia para sites não mapeados**.
    
    <div>
    

    > [!NOTE]
    > Marque essa caixa de seleção somente se você tiver um ou mais sites grandes associados na mesma região e que não possuem restrições de largura de banda (por exemplo, um grande site central), mas também tem sites de filial associados à mesma região e que possuem restrições de largura de banda. Ao habilitar o bypass para sites não mapeados, a configuração é simplificada de forma que você especifica apenas as sub-redes associadas com os sites de filial em vez de precisar especificar todas as sub-redes associadas com todos os sites. Recomendamos que você não marque essa caixa de seleção se o controle de admissão de chamadas estiver habilitado.

    
    </div>

7.  Clique em **Confirmar**.

Em seguida, adicione sub-redes ao site de rede, conforme descrito em [associar sub-redes a sites de rede para ignorar mídia no Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md). (Os procedimentos reais para associar sub-redes com sites de rede estão descritos em [associar uma sub-rede a um site de rede no Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).) Após associar todas as sub-redes com sites de rede, a implantação de bypass de mídia é concluída.

<div>


> [!IMPORTANT]
> Se ainda não tiverem sido criadas as regiões e os sites de rede, é preciso criá-los antes de prosseguir com a implantação do bypass de mídia. Para obter detalhes, consulte <A href="lync-server-2013-create-or-modify-a-network-region.md">criar ou modificar uma região de rede no Lync server 2013</A> e <A href="lync-server-2013-create-or-modify-a-network-site.md">criar ou modificar um site de rede no Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Associar sub-redes a sites de rede para ignorar mídia no Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

