---
title: 'Lync Server 2013: controle de admissão de chamada em um tronco SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control on a SIP trunk
ms:assetid: 7eada098-3d47-4be2-839f-8f87d582efe8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398632(v=OCS.15)
ms:contentKeyID: 48184623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7140d77b819f62f0eb2078cc161511653fef1461
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135007"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-admission-control-on-a-sip-trunk-in-lync-server-2013"></a>Controle de admissão de chamada em um tronco SIP no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-22_

Para implantar o controle de admissão de chamadas em um tronco SIP, crie um local de rede para representar o ITSP (provedor de serviço de telefonia da Internet). Para aplicar valores de política de largura de banda no tronco SIP, crie uma política entre locais entre o local de rede na sua empresa e o local de rede criado para representar o ITSP.

A figura a seguir mostra um exemplo de implantação do CAC em um tronco SIP.

**Configuração do CAC em um tronco SIP**

![Diagrama de tronco SIP do controle de admissão de chamadas](images/Gg398632.276c0d8f-1dd5-4883-8499-c202399ddbe9(OCS.15).jpg "Diagrama de tronco SIP do controle de admissão de chamadas")

Para configurar o CAC em um tronco SIP, você terá que executar as seguintes tarefas durante a implantação do CAC:

1.  Crie um site de rede para representar o ITSP. Associe o site de rede a uma região de rede apropriada e aloque a largura de banda de zero para áudio e vídeo para este site de rede. Para obter detalhes, consulte [Configure Network sites for CAC in Lync Server 2013](lync-server-2013-configure-network-sites-for-cac.md) na documentação de implantação.
    
    <div>
    

    > [!NOTE]  
    > Para o ITSP, essa configuração de site de rede não funciona. Os valores da política de largura de banda são, na verdade, aplicados na etapa 2.

    
    </div>

2.  Crie um link entre sites para o tronco SIP usando os valores de parâmetro relevantes para o site criado na etapa 1. Por exemplo, use o nome do site de rede na sua empresa como o valor do parâmetro NetworkSiteID1 e o site de rede ITSP como o valor do parâmetro NetworkSiteID2. Para obter detalhes, consulte [Create Network intersite Policies in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md) na documentação de implantação. Consulte também a documentação do Shell de gerenciamento do Lync Server para o cmdlet New-CsNetworkInterSitePolicy.

3.  Obtenha o endereço IP do ponto de terminação de mídia do SCB (controlador de borda da sessão)  no seu ITSP. Adicione o endereço IP com uma máscara de sub-rede de 32 para o site de rede que representa o ITSP. Para obter detalhes, consulte [associar uma sub-rede a um site de rede no Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).

</div>

<span> </span>

</div>

</div>

</div>

