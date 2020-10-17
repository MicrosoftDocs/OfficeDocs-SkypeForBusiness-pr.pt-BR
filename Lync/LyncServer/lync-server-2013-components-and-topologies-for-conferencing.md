---
title: Componentes e topologias do Lync Server 2013 para conferência
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for conferencing
ms:assetid: eb83052a-3360-4ba1-a6a0-6ee419942809
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399061(v=OCS.15)
ms:contentKeyID: 48185707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cfdb6ae250e3ccb97f044892daa8ac11e7c1b99b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502578"
---
# <a name="components-and-topologies-for-conferencing-in-lync-server-2013"></a>Componentes e topologias para conferências no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-04_

Quando você seleciona conferências no construtor de topologias, a conferência é implantada como parte do servidor front-end ou do servidor Standard Edition. A conferência discada e o compartilhamento de PowerPoint requer componentes e configurações adicionais. As seções a seguir descrevem os componentes e topologias suportados para webconferência, conferência A/V e conferência discada.

<div>

## <a name="supported-components"></a>Componentes suportados

Os únicos componentes de conferência da Web e conferência A/V exigem os servidores front-end da sua organização ou servidores Standard Edition. Para obter uma lista de requisitos de hardware e software para servidores front-end e servidores Standard Edition, consulte [hardware suportado para o Lync server 2013](lync-server-2013-supported-hardware.md) e [suporte a infraestrutura e software de servidor no Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).

O Lync Server 2013 usa o Office Web Apps e o servidor do Office Web Apps para lidar com o compartilhamento e a renderização de apresentações do PowerPoint. Para obter detalhes sobre como instalar e configurar o servidor do Office Web Apps, consulte [Configurando a integração com o servidor do Office Web Apps e o Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

Além dos requisitos de conferência da Web e conferência A/V, a conferência discada usa os seguintes componentes do Lync Server 2013:

  - **Serviço**     de aplicativo O serviço de aplicativo fornece uma plataforma para implantar, hospedar e gerenciar aplicativos de comunicação unificada (UC). A conferência discada usa dois aplicativos de comunicação unificada que exigem o serviço de aplicativo: o atendedor de conferência e o comunicado de conferência. O Serviço de aplicativo é instalado e ativado por padrão em cada Servidor Front-End em um pool de Front-Ends e em cada Servidor Standard Edition ao implantar uma carga de trabalho de Conferência e selecionar a opção de conferência de discagem.

  - Aplicativo de atendedor de **conferência**     O aplicativo de atendedor de conferência é um aplicativo de comunicações unificado que aceita chamadas PSTN (rede telefônica pública comutada), reproduz prompts e une as chamadas a uma conferência A/V. O aplicativo atendedor de conferência é instalado e ativado por padrão ao implantar uma carga de trabalho de conferência e selecionar a opção de conferência discada.

  - Aplicativo comunicado de **conferência**     O aplicativo de anúncio de conferência é um aplicativo de comunicações unificado que reproduz tons e avisa para os participantes de PSTN em determinadas ações, como quando os participantes ingressam ou saem de uma conferência, os participantes são habilitados ou desativados, alguém entra no lobby da conferência ou a conferência é bloqueada ou desbloqueada. O aplicativo de anúncio de conferência também suporta comandos DTMF (multifrequência de tom dual) do teclado numérico do telefone. O aplicativo de anúncio de conferência é automaticamente instalado e ativado por padrão ao implantar uma carga de trabalho de conferência e selecionar a opção de conferência discada.

  - Página de configurações **de conferência discada**     A página de configurações de conferência discada exibe os números de discagem de conferência com seus idiomas disponíveis, as informações de conferência atribuídas (ou seja, para reuniões que não precisam ser agendadas) e para o gerenciamento de DTMF de conferência e oferece suporte ao gerenciamento de PIN (número de identificação pessoal) e informações de conferência atribuídas. A página de configurações de conferência discada é instalada automaticamente como parte dos serviços Web.

  - **Lync server 2013, servidor de mediação e gateway PSTN**     A conferência discada requer um servidor de mediação para converter a sinalização (e mídia, em algumas configurações) entre o Lync Server 2013 e o gateway PSTN e um gateway PSTN para converter a sinalização e mídia entre o servidor de mediação e o gateway PSTN. Para a Conferência de Discagem, você deve implantar pelo menos um Servidor de Mediação e pelo menos um dos seguintes:
    
      - Gateway PSTN
    
      - IP-PBX
    
      - Controlador de Borda de Sessão (SBC) (para um provedor de serviços de telefonia pela Internet ao qual você se conecta configurando um tronco SIP)
    
    <div>
    

    > [!NOTE]  
    > Se você também estiver implantando o Enterprise Voice, o servidor de mediação e os gateways PSTN serão parte da implantação do Enterprise Voice. Se você não estiver implantando o Enterprise Voice, será necessário implantar pelo menos um Servidor de Mediação e um gateway PSTN, IP-PBX ou SBC para a conferência de discagem.

    
    </div>

  - **Repositório**     de arquivos O repositório de arquivos é usado para arquivos de áudio de nome gravados. O repositório de arquivos é um componente padrão em cada implantação Enterprise Edition ou Standard Edition.

  - **Repositório**     do usuário O repositório do usuário é usado para armazenar os PINs do Lync Server 2013 do usuário. Os PINs estão em hash. O repositório de usuário é um componente padrão em cada implantação Enterprise Edition ou Standard Edition.

  - Painel de controle **do Lync Server**     Algumas configurações de discagem podem ser configuradas usando o painel de controle do Lync Server.

  - Shell de gerenciamento **do Lync Server**     Todas as configurações de discagem podem ser configuradas usando os cmdlets do Shell de gerenciamento do Lync Server. Os cmdlets do Shell de gerenciamento do Lync Server estão disponíveis para implantação, configuração, execução, monitoramento e solução de problemas de aplicativo e anúncio de conferência do atendedor de conferência. Para obter detalhes sobre cmdlets específicos, consulte Lync Server Management Shell Documentation.

</div>

<div>

## <a name="supported-topologies"></a>Topologias suportadas

No Lync Server 2013, o servidor que executa o serviços de conferência é sempre colocado com os servidores front-end ou servidores Standard Edition. Durante a implantação inicial, o construtor de topologias oferece a opção de incluir a conferência em sua topologia. Você também pode usar o construtor de topologias para adicionar conferências a uma implantação existente. Para obter detalhes, consulte [definindo e configurando a topologia no Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).

<div>

## <a name="dial-in-conferencing-toplogies"></a>Topologias de conferência discada

É possível implantar a conferência discada nas seguintes topologias e configurações:

  - Lync Server 2013 Standard Edition

  - Lync Server 2013 Enterprise Edition

  - Com ou sem Enterprise Voice

Você pode implantar o serviço de aplicativo, o aplicativo de atendedor de conferência e o aplicativo de anúncio de conferência em um site central, mas não em um site de filial.

<div>


> [!NOTE]  
> Se você implantar a conferência discada, deverá implantá-la em todos os pools onde você implantar a conferência do Lync Server 2013. Não é necessário atribuir números de acesso em cada pool, mas é necessário implantar o recurso de conferência discada em cada pool. Esse requisito suporta o recurso de nome registrado quando um usuário chama um número de acesso de um pool para ingressar em uma conferência do Lync Server 2013 em um pool diferente.



</div>

</div>

<div>

## <a name="supported-topologies-for-lync-server-2013-and-office-web-apps"></a>Topologias suportadas para Lync Server 2013 e Office Web Apps

O Lync Server 2013 oferece as seguintes maneiras de configurar o servidor do Office Web Apps. Dependendo das suas necessidades, você pode:

  - **Instale o Lync Server 2013 e o servidor do Office Web Apps no local por meio do firewall da sua organização e na mesma zona de rede.** Com essa topologia, o acesso externo ao servidor do Office Web Apps será fornecido pelo servidor de proxy reverso. O Lync Server 2013 e o servidor do Office Web Apps (ou um farm do servidor do Office Web Apps) estão instalados no local e por trás do firewall da sua organização. O ideal é que você instale o servidor do Office Web Apps na mesma zona de rede do Lync Server.
    
    Os clientes externos do Lync podem se conectar ao Lync Server 2013 e ao servidor do Office Web Apps usando um servidor proxy reverso, que é um servidor que toma solicitações da Internet e as encaminha para a rede interna. (Os clientes internos não precisam usar o servidor proxy reverso, pois podem se conectar diretamente ao servidor do Office Web Apps.) Essa topologia funciona melhor se você quiser usar um farm dedicado do servidor do Office Web Apps que é usado apenas pelo Lync Server 2013.

  - **Usando um servidor do Office Web Apps implantado externamente**
    
    Nesta topologia, o Lync Server 2013 é implantado localmente e usa um servidor do Office Web Apps implantado fora da zona de rede do Lync Server. Isso pode acontecer quando o servidor do Office Web Apps é compartilhado entre vários aplicativos na empresa e é implantado em uma rede que requer o Lync Server para usar a interface externa do servidor do Office Web Apps e vice-versa.
    
    Não é necessário instalar um servidor de proxy reverso; em vez disso, todas as solicitações do servidor do Office Web Apps para o Lync Server 2013 são roteadas através do servidor de borda. Os seus clientes internos e externos do Lync se conectam ao servidor do Office Web Apps usando a URL externa.
    
    Se o servidor do Office Web Apps for implantado fora do seu firewall interno, selecione a opção o **servidor do Office Web Apps é implantado em uma rede externa (ou seja, perímetro/Internet)** no construtor de topologias. Para obter mais detalhes, consulte [Configurando a integração com o servidor do Office Web Apps e o Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

Independente da topologia selecionada, é fundamental que as portas de firewall certas estejam abertas. Você deve verificar se os nomes DNS, endereços IP e portas não são bloqueados por firewalls no servidor do Office Web Apps, no balanceador de carga ou no Lync Server.

<div>


> [!NOTE]  
> Outra opção para fornecer acesso externo ao servidor do Office Web Apps é implantar o servidor na rede de perímetro. Se você optar por fazer isso, tenha em mente que a instalação do servidor do Office Web Apps exige que o computador servidor seja membro do seu domínio do Active Directory. A menos que a política de rede permita que os computadores na rede de perímetro sejam membros do domínio do Active Directory, é recomendável que você não instale o servidor do Office Web Apps na rede de perímetro. Em vez disso, você deve instalar o servidor do Office Web Apps na rede interna e fornecer acesso de usuário externo através do servidor de proxy reverso.



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

