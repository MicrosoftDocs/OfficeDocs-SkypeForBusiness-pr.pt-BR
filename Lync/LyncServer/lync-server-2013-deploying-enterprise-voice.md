---
title: 'Lync Server 2013: implantação do Enterprise Voice'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Enterprise Voice
ms:assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412876(v=OCS.15)
ms:contentKeyID: 48185207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae445d954bd1be7c956d76aa48da2ad7854c6a54
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829561"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-enterprise-voice-in-lync-server-2013"></a>Implantando o Enterprise Voice no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-03_

Lync Server 2013, o Enterprise Voice faz parte da infraestrutura 2013 do Lync Server.

A implantação do Enterprise Voice exige que você:

<div id="sectionSection0" class="section">

1.  Examine a seção [planejando para Enterprise Voice na Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) da documentação de planejamento.

2.  Finalizar planos para recursos e componentes a serem implantados com essa carga de trabalho.

3.  Execute a ferramenta de planejamento para criar uma topologia que reflita suas decisões de implantação.

4.  Abra o design de topologia no construtor de topologias, conforme descrito em [definindo e configurando a topologia no Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) na documentação de implantação.
    
    <div>
    

    > [!NOTE]  
    > A instalação do construtor de topologias faz parte do processo de implantação do pool interno. Para obter detalhes, consulte <A href="lync-server-2013-install-lync-server-administrative-tools.md">instalar as ferramentas administrativas do Lync Server 2013</A> na documentação de implantação.

    
    </div>

Além disso, você já deve ter implantado o Lync Server, Enterprise Edition em sites centrais e sites de ramificação que correspondam à topologia de referência que você escolheu implantar. Você não pode implantar componentes de voz da empresa até ter definido arquivos publicados, publicados e instalados em pelo menos um pool interno e deve usar o construtor de topologias para definir e publicar um pool interno.

</div>

<div id="sectionSection1" class="section">

<div class="subSection">

Para ver as topologias de referência com exemplos de como as funções de servidor Enterprise Voice podem ser implantadas (e sua relação com outras funções de servidor do Lync Server 2013), consulte [topologias de referência no Lync server 2013](lync-server-2013-reference-topologies.md) na documentação de planejamento.

Para exibir uma topologia de referência que ilustra e explica um exemplo de implantação de controle de admissão de chamadas, incluindo regiões de rede, sites de rede e sub-redes, consulte [exemplo: reunir seus requisitos para o controle de admissão de chamadas no Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) na Documentação de planejamento.

</div>

</div>

<div id="sectionSection2" class="section">

<div>


> [!IMPORTANT]  
> Para implantar o Enterprise Voice em um site central, continue a ler os tópicos desta seção. Para implantar o Enterprise Voice em um site de filial, pule para a <A href="lync-server-2013-deploying-branch-sites.md">implantação de sites de filiais no Lync Server 2013</A> na documentação de implantação.



</div>

Esta seção inclui procedimentos para implantações nas quais um Servidor de Mediação é colocado em cada Servidor Front-End ou servidor Standard Edition, conforme recomendado, e também para implantações com um pool de Servidor de Mediação autônomo.

Você pode ignorar o conteúdo a seguir se tiver usado o construtor de topologias para definir e publicar uma topologia que posiciona um servidor de mediação em cada servidor front-end ou um servidor Standard Edition, pois o assistente de implantação já instalou automaticamente os arquivos para Servidor de mediação quando você instalou arquivos para o pool de servidores front-end ou o servidor Standard Edition:

  - [Configurando troncos no Lync Server 2013](lync-server-2013-configuring-trunks.md)

Se você usou o construtor de topologias para definir e publicar um servidor de mediação em um pool autônomo, você pode usar o seguinte conteúdo:

  - Verifique se a sua topologia atende aos pré-requisitos de software e ambiente, conforme descrito em [pré-requisitos do Enterprise Voice para o Lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md).

</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - <span></span>  
    [Pré-requisitos do Enterprise Voice para Lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md)

  - <span></span>  
    [Implantando Servidores de Mediação e definindo pares no Lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)

  - <span></span>  
    [Configurando troncos no Lync Server 2013](lync-server-2013-configuring-trunks.md)

  - <span></span>  
    [Configurando planos de discagem no Lync Server 2013](lync-server-2013-configuring-dial-plans.md)

  - <span></span>  
    [Configurar políticas de voz, registros de uso de PSTN e rotas de voz no Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

  - <span></span>  
    [Exportação e importação da configuração de roteamento de voz no Lync Server 2013](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - <span></span>  
    [Testar roteamento de voz no Lync Server 2013](lync-server-2013-test-voice-routing.md)

  - <span></span>  
    [Publicar alterações pendentes na configuração de roteamento de voz no Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - <span></span>  
    [Implantando Exchange UM no local para fornecer correio de voz do Lync Server 2013](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)

  - <span></span>  
    [Fornecendo caixa postal a usuários do Lync Server 2013 no Exchange UM hospedado](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)

  - <span></span>  
    [Configurando a integração do Lync Server 2013 local com o Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)

  - <span></span>  
    [Implantação de recursos avançados do Enterprise Voice no Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)
    
      - [Sobre regiões de rede, sites e subredes no Lync Server 2013](lync-server-2013-about-network-regions-sites-and-subnets.md)
    
      - [Criar ou modificar uma região de rede no Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md)
    
      - [Criar ou modificar um site da rede no Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md)
    
      - [Associar uma subrede a um site de rede no Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)
    
      - [Configurar o controle de admissão de chamadas no Lync Server 2013](lync-server-2013-configure-call-admission-control.md)
    
      - [Configurar 9-1-1 Avançado no Lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md)
    
      - [Configurar bypass de mídia no Lync Server 2013](lync-server-2013-configure-media-bypass.md)

  - <span></span>  
    [Habilitar usuários para Enterprise Voice no Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)

</div>

<div>

## <a name="see-also"></a>Confira também


[Implantando sites de filial no Lync Server 2013](lync-server-2013-deploying-branch-sites.md)  
[Configurando conferência discada no Lync Server 2013](lync-server-2013-configuring-dial-in-conferencing.md)  
[Configurando Estacionamento de Chamadas no Lync Server 2013](lync-server-2013-configuring-call-park.md)  
[Configurando comunicados de números não atribuídos no Lync Server 2013](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)  
[Implantando o monitoramento no Lync Server 2013](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

