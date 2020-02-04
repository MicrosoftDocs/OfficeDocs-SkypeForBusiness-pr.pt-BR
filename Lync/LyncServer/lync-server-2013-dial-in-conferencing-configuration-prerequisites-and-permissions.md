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
ms.openlocfilehash: e6610272c39583b70c1ab20d8271551796f65372
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762299"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-configuration-prerequisites-and-permissions-in-lync-server-2013"></a>Pré-requisitos e permissões de configuração de conferência discada no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-06-20_

A conferência discada é um componente opcional da carga de trabalho de conferência do Lync Server 2013. Os componentes que você precisa instalar antes de configurar a conferência discada são implantados quando você usa o construtor de topologias para criar sua topologia e, em seguida, configurar seu pool de front-end ou o servidor Standard Edition. Este tópico descreve o que você precisa ter feito antes de poder configurar a conferência discada.

Esta seção pressupõe que você tenha lido as seções de planejamento relacionadas à carga de trabalho de conferência e conferência discada em particular.

<div>

## <a name="dial-in-conferencing-configuration-prerequisites"></a>Pré-requisitos de configuração da conferência discada

A conferência discada requer os seguintes componentes do Lync Server 2013:

  - UCAS (Unified Communications Application Service) (chamado de *Serviço de aplicativos*)

  - Aplicativo Atendedor de Conferência

  - Aplicativo Comunicado de Conferência

  - Página da Web Configurações de Conferência Discada

  - Pelo menos um servidor de mediação do Lync Server 2013 e pelo menos um gateway PSTN

Você implanta esses componentes quando usa o construtor de topologias para definir e publicar sua topologia e, em seguida, implantar um pool de front-ends ou um servidor Standard Edition. Se você estiver implantando o Enterprise Voice, deve implantá-lo antes de configurar a conferência discada. Se você não estiver implantando o Enterprise Voice, poderá implantar um servidor de mediação e um gateway PSTN (rede telefônica pública comutada) ao implantar seu pool de front-end ou o servidor Standard Edition.

<div>


> [!NOTE]
> Se você estiver atualizando do Office Communications Server 2007 R2 para o Lync Server 2013, implante a conferência discada em todos os pools que planeja usar para hospedar conferências do Lync Server 2013. Para obter detalhes sobre a migração de conferência discada, consulte <A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">migração do Office Communications Server 2007 R2 para o Lync server 2013</A>.



</div>

Esta seção pressupõe que você tenha feito o seguinte:

  - Aplicadas as atualizações mais recentes para o seu ambiente do Office Communications Server 2007 R2, se você estiver migrando para o Lync Server 2013.

  - Usou o construtor de topologias para projetar e configurar sua topologia. Ao especificar a carga de trabalho de conferência, você selecionou a opção de conferência discada. Para obter detalhes sobre como definir sua topologia, consulte [definindo e configurando a topologia no Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) na documentação de implantação.

  - Publicou sua topologia e configurar o pool de front-end ou o servidor Standard Edition. Para obter detalhes sobre como publicar a topologia e instalar o Lync Server 2013, consulte [implantação do Lync server 2013](lync-server-2013-deploying-lync-server.md) na documentação de implantação.
    
    <div>
    

    > [!NOTE]
    > Quando você instala sua topologia publicada, a página da Web configurações de conferência discada é instalada no servidor front-end ou no servidor Standard Edition como parte dos serviços Web.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > Se você alterar o caminho para o repositório de arquivos no construtor de topologias depois de implantar o Lync Server 2013, será necessário reiniciar o atendedor de conferências e os aplicativos de anúncio de conferência para usar o novo caminho.

    
    </div>

  - Enterprise Voice implantado. Se não estiver implantando o Enterprise Voice, você colocaria um servidor de mediação no servidor front-end do Enterprise Edition ou do servidor Standard Edition ou implantou um servidor de mediação autônomo e implantou um gateway PSTN. Para obter detalhes sobre a implantação do Enterprise Voice, consulte [implantação do Enterprise Voice no Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) na documentação de implantação. Para obter detalhes sobre como instalar um servidor autônomo de mediação e um gateway PSTN, consulte [implantação de servidores de mediação e definição de pares no Lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md) na documentação de implantação.

O fluxograma a seguir mostra as etapas que você deve executar antes de poder configurar a conferência discada e as etapas que você executa para configurar a conferência discada.

**Implantando conferência discada**

![Fluxograma de implantação de conferência discada](images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "Fluxograma de implantação de conferência discada")

</div>

<div>

## <a name="dial-in-conferencing-permissions"></a>Permissões de conferência discada

Para configurar a conferência discada, você precisará usar as seguintes ferramentas administrativas:

  - Painel de Controle do Lync Server 2013

  - Shell de Gerenciamento do Lync Server

Use essas ferramentas administrativas para configurar as configurações de conferência discada e os planos de discagem, as políticas e outras configurações necessárias para a conferência discada.

A configuração da conferência discada requer qualquer uma das seguintes funções administrativas, dependendo da tarefa:

  - **CsVoiceAdministrator**   essa função de administrador pode criar, configurar e gerenciar configurações e políticas relacionadas à voz.

  - **CsUserAdministrator**   essa função de administrador pode habilitar e desabilitar usuários do Lync Server e atribuir políticas existentes, como políticas de conferência e políticas de PIN, a usuários.

  - **CsAdministrator**   essa função de administrador pode executar todas as tarefas do CsVoiceAdministrator e do CsUserAdministrator.

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

