---
title: 'Lync Server 2013: Componentes e topologias para conferências'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components and topologies for conferencing
ms:assetid: eb83052a-3360-4ba1-a6a0-6ee419942809
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399061(v=OCS.15)
ms:contentKeyID: 48185707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5caf5ba33e863e08bf4f728d2bf11394f37f20b6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836534"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-conferencing-in-lync-server-2013"></a>Componentes e topologias para conferências no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-04_

Quando você seleciona conferência no construtor de topologias, a conferência é implantada como parte do servidor front-end ou do servidor Standard Edition. A conferência discada e o compartilhamento do PowerPoint exigem componentes e configurações adicionais. As seções a seguir descrevem os componentes e topologias com suporte para conferência Web, conferência A/V e conferência discada.

<div>

## <a name="supported-components"></a>Componentes com suporte

Os únicos componentes da webconferência e da Conferência A/V exigem os servidores front-end da sua organização ou servidores Standard Edition. Para obter uma lista dos requisitos de hardware e software para os servidores de front-end e os servidores de edição padrão, consulte suporte a [hardware com suporte para o Lync server 2013](lync-server-2013-supported-hardware.md) e [para o software do servidor e a infraestrutura do Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).

O Lync Server 2013 usa o Office Web Apps e o Office Web Apps Server para lidar com o compartilhamento e a renderização de apresentações do PowerPoint. Para obter detalhes sobre como instalar e configurar o Office Web Apps Server, consulte Configurando a [integração com o Office Web Apps Server e o Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

Além dos requisitos de conferência via Web e conferência A/V, a conferência discada usa os seguintes componentes do Lync Server 2013:

  - ****   Serviço de aplicativo de serviço de aplicativo fornece uma plataforma para implantação, hospedagem e gerenciamento de aplicativos de comunicação unificada (UC). A conferência discada usa dois aplicativos de comunicação unificada que exigem serviço de aplicativo: anúncio de conferência e atendedor de conferências. O serviço de aplicativo é instalado e ativado por padrão em todos os servidores front-end em um pool Front-end e em cada servidor Standard Edition quando você implanta uma carga de trabalho de conferência e seleciona a opção conferência discada.

  - **Assistente de conferência**   o aplicativo atendente do aplicativo de conferência é um aplicativo de comunicação unificado que aceita chamadas PSTN (rede telefônica pública comutada), reproduz solicitações e une as chamadas a uma conferência a/V. O aplicativo assistente de conferência é instalado e ativado por padrão quando você implanta uma carga de trabalho de conferência e seleciona a opção conferência discada.

  - **Aviso de conferência**   o aplicativo de anúncio de conferência do aplicativo é um aplicativo de comunicação unificado que reproduz toques e avisa para participantes PSTN em determinadas ações, como quando os participantes ingressam ou deixam uma conferência, os participantes têm mudo ou mudo, alguém entra no lobby da conferência ou a conferência está bloqueada ou desbloqueada. O aplicativo de anúncio de conferência também oferece suporte a comandos DTMF (Multifrequency) de dois tons do teclado do telefone. O aplicativo de anúncio de conferência é automaticamente instalado e ativado por padrão quando você implanta uma carga de trabalho de conferência e seleciona a opção conferência discada.

  - **Página Configurações de conferência discada**   a página Configurações de conferência discada exibe os números de discagem de conferência com os idiomas disponíveis, as informações de conferência atribuídas (ou seja, para reuniões que não precisam ser agendadas) e controles DTMF em conferência e suporte ao gerenciamento de PIN (número de identificação pessoal) e informações de conferência atribuídas. A página de Configurações da Conferência Discada é automaticamente instalada como parte dos serviços da Web.

  - **A conferência discada do Lync Server 2013, do servidor de mediação e do gateway**   PSTN requer um servidor de mediação para traduzir a sinalização (e mídia, em algumas configurações) entre o Lync Server 2013 e o gateway PSTN e um gateway PSTN para traduzir sinalização e mídia entre o servidor de mediação e o gateway PSTN. Para conferência discada, você deve implantar pelo menos um servidor de mediação e pelo menos um dos seguintes:
    
      - Gateway PSTN
    
      - IP-PBX
    
      - Controlador de Borda de Sessão (SBC) (para um provedor de serviços de telefonia pela Internet ao qual você se conecta configurando um tronco SIP)
    
    <div>
    

    > [!NOTE]  
    > Se você também estiver implantando o Enterprise Voice, o servidor de mediação e os gateways PSTN fazem parte da implantação do Enterprise Voice. Se não estiver implantando o Enterprise Voice, você precisará implantar pelo menos um servidor de mediação e pelo menos um gateway PSTN, PBX IP ou SBC para conferência discada.

    
    </div>

  - ****   O armazenamento de arquivos do armazenamento de arquivos é usado para arquivos de áudio de nome gravados. O Repositório de Arquivos é um componente padrão de todas as implantações do Enterprise Edition ou Standard Edition.

  - ****   Repositório de usuários da loja de usuários é usado para armazenar Pins do usuário do Lync Server 2013. Os PINs são marcados por hash. O armazenamento de Usuários é um componente padrão em todas as implantações de Enterprise Edition ou Standard Edition.

  - **Painel de controle do Lync Server**   algumas configurações de discagem podem ser configuradas usando o painel de controle do Lync Server.

  - **Shell de gerenciamento do Lync Server**   todas as configurações de discagem podem ser configuradas usando cmdlets do shell do Shell de gerenciamento do Lync Server. Os cmdlets do Shell de gerenciamento do Lync Server estão disponíveis para implantar, configurar, executar, monitorar e solucionar problemas do aplicativo atendedor de conferências e do aplicativo de anúncio de conferências. Para obter detalhes sobre cmdlets específicos, consulte documentação do Shell de gerenciamento do Lync Server.

</div>

<div>

## <a name="supported-topologies"></a>Topologias suportadas

No Lync Server 2013, o servidor que executa serviços de conferência é sempre posicionado com os servidores front-end ou servidores Standard Edition. Durante a implantação inicial, o construtor de topologias oferece a opção de incluir conferências na sua topologia. Você também pode usar o Construtor de Topologias para adicionar conferências a uma implantação existente. Para obter detalhes, consulte [definindo e configurando a topologia no Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).

<div>

## <a name="dial-in-conferencing-toplogies"></a>Toplogies de conferência discada

Você pode implantar a conferência discada nas seguintes topologias e configurações:

  - Lync Server 2013 Standard Edition

  - Lync Server 2013 Enterprise Edition

  - Com ou sem Enterprise Voice

Você pode implantar o serviço de aplicativo, o aplicativo do atendente de conferência e o aplicativo de anúncio de conferência em um site central, mas não em um site de filial.

<div>


> [!NOTE]  
> Se você implantar a conferência discada, será necessário implantá-la em cada pool onde implantar a conferência do Lync Server 2013. Não é necessário atribuir números de acesso em cada pool, mas é necessário implantar o recurso de conferência discada em cada pool. Esse requisito dá suporte ao recurso de nome registrado quando um usuário chama um número de acesso de um pool para ingressar em uma conferência do Lync Server 2013 em um pool diferente.



</div>

</div>

<div>

## <a name="supported-topologies-for-lync-server-2013-and-office-web-apps"></a>Topologias com suporte para o Lync Server 2013 e Office Web Apps

O Lync Server 2013 fornece as seguintes maneiras de configurar o servidor do Office Web Apps. Dependendo de seus requisitos, você pode:

  - **Instale o Lync Server 2013 e o Office Web Apps Server no local por trás do firewall da sua organização e na mesma zona de rede.** Com essa topologia, o acesso externo ao servidor do Office Web Apps será fornecido por meio do servidor de proxy reverso. O Lync Server 2013 e o Office Web Apps Server (ou um Office Web Apps Server farm) são instalados no local e atrás do firewall da sua organização. Idealmente, você deve instalar o Office Web Apps Server na mesma zona de rede do Lync Server.
    
    Os clientes externos do Lync podem se conectar ao Lync Server 2013 e ao Office Web Apps Server usando um servidor proxy reverso, que é um servidor que recebe solicitações da Internet e as encaminha para a rede interna. (Os clientes internos não precisam usar o servidor proxy reverso porque podem se conectar ao servidor do Office Web Apps diretamente.) Essa topologia funciona melhor se você quiser usar um farm de servidores dedicado do Office Web Apps que é usado apenas pelo Lync Server 2013.

  - **Usando um servidor Office Web Apps implantado externamente**
    
    Nessa topologia, o Lync Server 2013 é implantado local e usa um servidor Office Web Apps que é implantado fora da zona de rede do Lync Server. Isso pode acontecer quando o Office Web Apps Server é compartilhado entre vários aplicativos na empresa e é implantado em uma rede que requer o Lync Server para usar a interface externa do servidor do Office Web Apps e vice-versa.
    
    Você não precisa instalar um servidor proxy reverso; em vez disso, todas as solicitações do servidor do Office Web Apps para o Lync Server 2013 são roteadas pelo servidor de borda. Os seus clientes internos e externos do Lync se conectam ao servidor do Office Web Apps usando a URL externa.
    
    Se o Office Web Apps Server for implantado fora do seu firewall interno, selecione a opção o **servidor do Office Web Apps será implantado em uma rede externa (ou seja, perímetro/Internet)** no construtor de topologias. Para obter mais detalhes, consulte Configurando [a integração com o Office Web Apps Server e o Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

Independentemente da topologia selecionada, é fundamental que as portas do firewall certas estejam abertas. Você deve certificar-se de que nomes DNS, endereços IP e portas não sejam bloqueados por firewalls no servidor do Office Web Apps, o balanceador de carga ou o Lync Server.

<div>


> [!NOTE]  
> Outra opção para fornecer acesso externo ao servidor do Office Web Apps é implantar o servidor na rede de perímetro. Se você optar por fazer isso, lembre-se de que a instalação do servidor do Office Web Apps exige que o computador do servidor seja membro do seu domínio do Active Directory. A menos que sua política de rede permita que os computadores na rede de perímetro sejam membros do domínio do Active Directory, é recomendável que você não instale o servidor do Office Web Apps na rede de perímetro. Em vez disso, você deve instalar o Office Web Apps Server na rede interna e oferecer acesso externo ao usuário por meio do servidor proxy reverso.



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

