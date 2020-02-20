---
title: 'Lync Server 2013: Implantando o Enterprise Voice'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Enterprise Voice
ms:assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412876(v=OCS.15)
ms:contentKeyID: 48185207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b56065b0e3b7e7ef25c81f20140e8869dbe5376
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151331"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-enterprise-voice-in-lync-server-2013"></a>Implantando o Enterprise Voice no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-03_

Lync Server 2013, o Enterprise Voice é parte da infraestrutura 2013 do Lync Server.

A implantação do Enterprise Voice requer que você:

<div id="sectionSection0" class="section">

1.  Examine a seção [planejamento do Enterprise Voice no Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) da documentação de planejamento.

2.  Finalize os planos de recursos e componentes para implantação com essa carga de trabalho.

3.  Execute a ferramenta de planejamento para projetar uma topologia que reflita suas decisões de implantação.

4.  Abra o design de topologia no construtor de topologias, conforme descrito em [definindo e configurando a topologia no Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) na documentação de implantação.
    
    <div>
    

    > [!NOTE]  
    > A instalação do construtor de topologias faz parte do processo de implantação do pool interno. Para obter detalhes, consulte <A href="lync-server-2013-install-lync-server-administrative-tools.md">install Lync Server 2013 Administrative Tools</A> na documentação de implantação.

    
    </div>

Além disso, você já deve ter implantado o Lync Server, Enterprise Edition em sites centrais e sites de filial que correspondem à topologia de referência que você escolhe implantar. Não é possível implantar componentes do Enterprise Voice até que você tenha definido, publicado e instalado arquivos para pelo menos um pool interno, e você deve usar o construtor de topologias para definir e publicar um pool interno.

</div>

<div id="sectionSection1" class="section">

<div class="subSection">

Para exibir as topologias de referência com exemplos de onde as funções de servidor Enterprise Voice podem ser implantadas (e sua relação com outras funções de servidor do Lync Server 2013), consulte [Reference topologias in Lync server 2013](lync-server-2013-reference-topologies.md) na documentação de planejamento.

Para exibir uma topologia de referência que ilustra e explica um exemplo de implantação de controle de admissão de chamadas, incluindo regiões de rede, sites de rede e sub-redes, consulte [exemplo: reunindo seus requisitos para controle de admissão de chamadas no Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) na documentação de planejamento.

</div>

</div>

<div id="sectionSection2" class="section">

<div>


> [!IMPORTANT]  
> Para implantar o Enterprise Voice em um site central, continue lendo os tópicos desta seção. Para implantar o Enterprise Voice em um site de filial, vá para <A href="lync-server-2013-deploying-branch-sites.md">implantando sites de filial no Lync Server 2013</A> na documentação de implantação.



</div>

Esta seção inclui procedimentos para implantações nas quais um Servidor de mediação é colocado em cada Servidor Front-End ou servidor Standard Edition, conforme recomendado, e também para implantações com um pool de Servidor de mediação autônomo.

Você pode ignorar o seguinte conteúdo se você usou o construtor de topologias para definir e publicar uma topologia que coloca um servidor de mediação em cada servidor front-end ou servidor Standard Edition, porque o assistente de implantação já instalou automaticamente os arquivos para Servidor de mediação quando você instalou arquivos para o pool de servidores front-end ou servidor Standard Edition:

  - [Configurando troncos no Lync Server 2013](lync-server-2013-configuring-trunks.md)

Se você usou o construtor de topologias para definir e publicar um servidor de mediação em um pool autônomo, você pode usar o seguinte conteúdo:

  - Verifique se a topologia atende aos pré-requisitos de software e de ambiente, conforme descrito em [pré-requisitos do Enterprise Voice para Lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md).

</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - <span></span>  
    [Pré-requisitos do Enterprise Voice para Lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md)

  - <span></span>  
    [Implantando servidores de mediação e definindo pares no Lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)

  - <span></span>  
    [Configurando troncos no Lync Server 2013](lync-server-2013-configuring-trunks.md)

  - <span></span>  
    [Configurando planos de discagem no Lync Server 2013](lync-server-2013-configuring-dial-plans.md)

  - <span></span>  
    [Configurando políticas de voz, registros de uso de PSTN e rotas de voz no Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

  - <span></span>  
    [Exportando e importando a configuração de roteamento de voz no Lync Server 2013](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - <span></span>  
    [Testar roteamento de voz no Lync Server 2013](lync-server-2013-test-voice-routing.md)

  - <span></span>  
    [Publicar alterações pendentes na configuração de roteamento de voz no Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - <span></span>  
    [Implantando a UM do Exchange local para fornecer correio de voz do Lync Server 2013](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)

  - <span></span>  
    [Fornecimento de mensagens de voz para usuários do Lync Server 2013 no Exchange UM hospedado](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)

  - <span></span>  
    [Configurando a integração do Lync Server 2013 local com o Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)

  - <span></span>  
    [Implantando recursos avançados do Enterprise Voice no Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)
    
      - [Sobre regiões de rede, sites e sub-redes no Lync Server 2013](lync-server-2013-about-network-regions-sites-and-subnets.md)
    
      - [Criar ou modificar uma região de rede no Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md)
    
      - [Criar ou modificar um site de rede no Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md)
    
      - [Associar uma sub-rede a um site de rede no Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)
    
      - [Configurar o controle de admissão de chamadas no Lync Server 2013](lync-server-2013-configure-call-admission-control.md)
    
      - [Configurar o 9-1-1 avançado no Lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md)
    
      - [Configurar bypass de mídia no Lync Server 2013](lync-server-2013-configure-media-bypass.md)

  - <span></span>  
    [Habilitar usuários para o Enterprise Voice no Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)

</div>

<div>

## <a name="see-also"></a>Confira também


[Implantando sites de filial no Lync Server 2013](lync-server-2013-deploying-branch-sites.md)  
[Configurando a conferência discada no Lync Server 2013](lync-server-2013-configuring-dial-in-conferencing.md)  
[Configurando o estacionamento de chamadas no Lync Server 2013](lync-server-2013-configuring-call-park.md)  
[Configurando comunicados para números não atribuídos no Lync Server 2013](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)  
[Implantando o monitoramento no Lync Server 2013](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

