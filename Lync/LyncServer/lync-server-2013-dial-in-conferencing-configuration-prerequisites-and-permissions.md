---
title: Pré-requisitos e permissões de configuração de conferência discada
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing configuration prerequisites and permissions
ms:assetid: b3b251e5-78ac-44a2-8c36-2a061c9b2314
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412865(v=OCS.15)
ms:contentKeyID: 48185165
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33ac1b54f03463972c49b2e4584f1b9f72d16c03
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044653"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-configuration-prerequisites-and-permissions-in-lync-server-2013"></a>Pré-requisitos e permissões de configuração de conferência discada no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-06-20_

A conferência discada é um componente opcional da carga de trabalho de conferência do Lync Server 2013. Os componentes que precisam ser instalados para que você possa configurar a conferência discada são implantados quando você usa o construtor de topologias para criar sua topologia e, em seguida, configurar seu pool de front-ends ou servidor Standard Edition. Este tópico descreve o que você precisa fazer para poder configurar a conferência discada.

Esta seção supõe que você leu as seções de planejamento relacionadas à carga de trabalho Conferência e conferência discada em particular.

<div>

## <a name="dial-in-conferencing-configuration-prerequisites"></a>Pré-requisitos de configuração de conferência discada

A conferência discada requer os seguintes componentes do Lync Server 2013:

  - UCAS (Unified Communications Application Service) (chamado de *Serviço de Aplicativo*)

  - Aplicativo Atendedor de Conferência

  - Aplicativo Comunicado de Conferência

  - Página da Web Configurações de Conferência Discada

  - Pelo menos um servidor de mediação do Lync Server 2013 e pelo menos um gateway PSTN

Você implanta esses componentes quando usa o construtor de topologias para definir e publicar sua topologia e, em seguida, implantar um pool de front-ends ou um servidor Standard Edition. Se você estiver implantando o Enterprise Voice, deverá implantá-lo antes de configurar a conferência discada. Se você não estiver implantando o Enterprise Voice, poderá implantar um servidor de mediação e um gateway PSTN (rede telefônica pública comutada) ao implantar seu pool de front-ends ou servidor Standard Edition.

<div>


> [!NOTE]
> Se você estiver atualizando do Office Communications Server 2007 R2 para o Lync Server 2013, implante a conferência discada em todos os pools que pretende usar para hospedar as conferências do Lync Server 2013. Para obter detalhes sobre a migração de conferência discada, consulte <A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">migração do Office Communications Server 2007 R2 para o Lync server 2013</A>.



</div>

Esta seção supõe que você fez o seguinte:

  - Aplicadas as atualizações mais recentes para o seu ambiente do Office Communications Server 2007 R2, se você estiver migrando para o Lync Server 2013.

  - Usou o construtor de topologias para projetar e configurar sua topologia. Durante a especificação da carga de trabalho Conferência, você selecionou a opção de conferência discada. Para obter detalhes sobre como definir sua topologia, consulte [definindo e configurando a topologia no Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) na documentação de implantação.

  - Publicou sua topologia e configurou o pool Front-End ou servidor Standard Edition. Para obter detalhes sobre como publicar a topologia e instalar o Lync Server 2013, consulte [Deploying Lync server 2013](lync-server-2013-deploying-lync-server.md) na documentação de implantação.
    
    <div>
    

    > [!NOTE]
    > Ao instalar sua topologia publicada, a página da Web Configurações de Conferência Discada é instalada no servidor Front-End ou servidor Standard Edition como parte dos Serviços da Web.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > Se você alterar o caminho para o repositório de arquivos no construtor de topologias depois de implantar o Lync Server 2013, será necessário reiniciar o atendedor de conferência e os aplicativos de anúncio de conferência para usar o novo caminho.

    
    </div>

  - Enterprise Voice implantado. Se você não estiver implantando o Enterprise Voice, colocará um servidor de mediação no servidor de front-ends Enterprise Edition ou o servidor Standard Edition, ou implantou um servidor de mediação autônomo e implantou um gateway PSTN. Para obter detalhes sobre a implantação do Enterprise Voice, consulte [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) na documentação de implantação. Para obter detalhes sobre como instalar um servidor de mediação autônomo e gateway PSTN, consulte [implantando servidores de mediação e definindo pares no Lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md) na documentação de implantação.

O fluxograma a seguir mostra as etapas que devem ser executadas antes de você poder configurar a conferência discada e as etapas executadas para configurar a conferência discada.

**Implantando a conferência discada**

![Fluxograma de implantação de conferência discada](images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "Fluxograma de implantação de conferência discada")

</div>

<div>

## <a name="dial-in-conferencing-permissions"></a>Permissões de conferência discada

Para configurar a conferência discada, é necessário usar as seguintes ferramentas administrativas:

  - Painel de Controle do Lync Server 2013

  - Shell de Gerenciamento do Lync Server

Use essas ferramentas administrativas para definir as configurações de conferência discada e os planos, políticas e outras configurações de discagem exigidas pela conferência discada.

A configuração de uma conferência discada exige qualquer uma das funções administrativas a seguir, dependendo da tarefa:

  - **CsVoiceAdministrator**   essa função de administrador pode criar, configurar e gerenciar configurações e políticas relacionadas à voz.

  - **CsUserAdministrator**   essa função de administrador pode habilitar e desabilitar usuários para o Lync Server e atribuir políticas existentes, como políticas de conferência e políticas de PIN, aos usuários.

  - **CsAdministrator**   essa função de administrador pode realizar todas as tarefas do CsVoiceAdministrator e do CsUserAdministrator.

</div>

<div>

## <a name="see-also"></a>Confira também


[Implantando o Enterprise Voice no Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

