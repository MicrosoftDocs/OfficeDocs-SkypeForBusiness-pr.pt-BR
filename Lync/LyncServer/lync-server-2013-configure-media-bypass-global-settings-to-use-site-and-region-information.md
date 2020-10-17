---
title: Definir as configurações globais de bypass de mídia para usar informações do site e da região
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass global settings to use site and region information
ms:assetid: 0a21cdf1-f350-49da-b346-70806f256bea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398150(v=OCS.15)
ms:contentKeyID: 48183360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e730b1e44bbe6e6fbec4d84a2c81ce474cff693
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507618"
---
# <a name="configure-media-bypass-global-settings-in-lync-server-2013-to-use-site-and-region-information"></a>Definir as configurações globais de bypass de mídia no Lync Server 2013 para usar informações do site e da região

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-21_

<div>


> [!NOTE]
> Este tópico considera que você já tenha configurado o desvio de mídia em todas as conexões de tronco do Servidor de Mediação para um ponto (gateway PSTN, PBX IP ou Controlador de Limite de Sessões no Provedor de Serviços de Telefonia pela Internet) de um site ou serviço específico no qual deseja que a mídia ignore o Servidor de Mediação.<BR>Este tópico também pressupõe que você tenha definido todos os sites centrais e sites de filial no construtor de topologias de uma maneira que corresponda à região de rede, ao site de rede e à configuração de sub-rede que você executou de acordo com as etapas em <A href="lync-server-2013-create-or-modify-a-network-region.md">criar ou modificar uma região de rede no Lync server 2013</A>, <A href="lync-server-2013-create-or-modify-a-network-site.md">criar ou modificar um site de rede no Lync 2013 2013 Server</A> <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A> Se elas não forem compatíveis, o desvio de mídia não será bem-sucedido.



</div>

Além de habilitar o desvio de mídia para conexões de tronco individuais associadas a um par, você também precisa definir as configurações globais. Se você usar as etapas deste tópico para definir as configurações globais do desvio de mídia, a hipótese é de que uma ou ambas as situações a seguir afetem sua configuração:

  - Você *não* tem uma boa conectividade entre os pontos de extremidade do Lync Server e os pontos para os quais você configurou o bypass de mídia na conexão do tronco.

  - O controle de admissão de chamadas (CAC) para gerenciamento de largura de banda está habilitado.
    
    <div>
    

    > [!NOTE]
    > Para obter detalhes sobre as considerações para o controle de admissão de chamadas e o bypass de mídia, consulte a seção "controle de admissão de chamadas de conexões PSTN" no <A href="lync-server-2013-media-bypass-and-mediation-server.md">bypass de mídia e no servidor de mediação no Lync server 2013</A> na documentação de planejamento.

    
    </div>

As informações de região de rede e de site de rede são compartilhadas entre os recursos avançados do Enterprise Voice de controle de admissão de chamadas e de desvio de mídia quando os dois estão habilitados. Portanto, se você já configurou o controle de admissão de chamadas, não é preciso usar o procedimento a seguir para editar as informações do site e da região especificamente para o desvio de mídia. Siga as etapas neste procedimento se você ainda não tiver configurado as regiões e os sites de rede quanto ao controle de admissão de chamadas e se quiser alterar as configurações do desvio de chamada.

Ou siga estas etapas se quiser usar as informações do site e da região para tomar a decisão do desvio de mídia, mas não tem a intenção de habilitar o controle de admissão de chamadas. Nesse caso, os links restritos de largura de banda ainda precisam ser representados por meio de políticas entre sites de rede, conforme descrito em [Create Network intersite Policies in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md). As restrições atuais de largura de banda não são tão importantes nesse caso porque o controle de admissão de chamada ainda não foi habilitado. Em vez disso, esses links são usados para sub-redes de partição para especificar aquelas sem limites de largura de banda e podem empregar desvios de mídia. Note que isso também ocorre quando o controle de admissão de chamada e o desvio de mídia estão habilitados.

Além disso, para que o bypass funcione corretamente, deve haver consistência entre um site conforme definido no construtor de topologias e conforme é definido quando você configura regiões de rede e sites de rede. Por exemplo, se você tiver um site de filial que você definiu no construtor de topologias como tendo apenas um gateway PSTN implantado, esse site de filial deverá ser configurado com uma política de Enterprise Voice que permita que os usuários do site de filial tenham suas chamadas PSTN roteadas pelo gateway PSTN no site de filial.

<div>

## <a name="to-configure-site-and-region-information-for-media-bypass"></a>Para configurar informações de site e de região para desvio de mídia

1.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Na barra de navegação à esquerda, clique em **Configurações de rede**.

3.  Dê dois cliques na configuração **Global** na tabela.

4.  Na página **Editar Configurações Globais**, marque a caixa de seleção **Habilitar desvio de mídia**.

5.  Clique em **Usar as configurações de sites e região**.

6.  Se necessário, marque a caixa de seleção **Habilitar desvio de mídia para sites não mapeados**.
    
    <div>
    

    > [!NOTE]
    > Marque essa caixa de seleção somente se você tiver um ou mais sites grandes associados na mesma região e que não possuem restrições de largura de banda (por exemplo, um grande site central), mas também tem sites de filial associados à mesma região e que possuem restrições de largura de banda. Ao habilitar o desvio para sites não mapeados, a configuração é simplificada de forma que você especifica apenas as sub-redes associadas com os sites de filial em vez de precisar especificar todas as sub-redes associadas com todos os sites. Recomendamos que você não marque essa caixa de seleção se o controle de admissão de chamadas estiver habilitado.

    
    </div>

7.  Clique em **Confirmar**.

Em seguida, adicione sub-redes ao site de rede, conforme descrito em [associar sub-redes a sites de rede para bypass de mídia no Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md). (Os procedimentos reais para associar sub-redes a sites de rede são descritos em [associar uma sub-rede a um site de rede no Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).) Após associar todas as sub-redes a sites de rede, a implantação de bypass de mídia estará concluída.

<div>


> [!IMPORTANT]
> Se ainda não tiverem sido criadas as regiões e os sites de rede, é preciso criá-los antes de prosseguir com a implantação do desvio de mídia. Para obter detalhes, consulte <A href="lync-server-2013-create-or-modify-a-network-region.md">criar ou modificar uma região de rede no Lync Server 2013</A> e <A href="lync-server-2013-create-or-modify-a-network-site.md">criar ou modificar um site de rede no Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Associar sub-redes a sites de rede para bypass de mídia no Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

