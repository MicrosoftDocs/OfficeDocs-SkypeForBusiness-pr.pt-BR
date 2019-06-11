---
title: 'Lync Server 2013: Tarefas de implantação de controle de chamada remota'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment tasks for remote call control
ms:assetid: 20218871-4f27-4611-9b7e-c0ca55908284
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558624(v=OCS.15)
ms:contentKeyID: 48183599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f63c9cba56ccedf3559b1e9f1da1ee58cc03e195
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829456"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-tasks-for-remote-call-control-in-lync-server-2013"></a>Tarefas de implantação de controle de chamada remota no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-05_

Este tópico descreve as tarefas de implantação que devem ser realizadas para habilitar o controle de chamada remota para usuários em seu ambiente do Lync Server.

<div>


> [!NOTE]  
> Se você estiver migrando usuários anteriormente habilitados para controle de chamada remota no Microsoft Office Communicator 2007 R2, deverá executar uma tarefa de implantação adicional antes de começar a executar as tarefas de implantação do controle de chamada remota descritas neste tópico. Durante o processo de migração para o Lync Server, as entradas de aplicativo confiáveis (anteriormente conhecidas como <EM>entradas de host autorizadas</EM>) devem ser removidas usando as ferramentas administrativas do Office Communications Server 2007 R2, conforme apropriado.<BR>Para obter detalhes sobre como remover hosts autorizados, consulte <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">remover um host autorizado herdado no Lync Server 2013 (opcional)</A>.



</div>

<div>

## <a name="step-1-install-and-configure-the-sipcsta-gateway-to-communicate-with-your-pbx"></a>Etapa 1: instalar e configurar o gateway SIP/CSTA para se comunicar com o seu PBX

Você precisa instalar pelo menos um gateway SIP/CSTA que possa se conectar ao Lync Server e ao PBX (Private Branch Exchange) existente em seu ambiente para fornecer recursos de controle de chamada remota para seus usuários. Um gateway SIP/CSTA é um gateway entre o SIP e um aplicativo de telecomunicações compatível com o computador (CSTA). Não importa se você instala vários gateways ou apenas um, cada usuário pode ser configurado com apenas um gateway ou PBX. Se o seu PBX existente não tiver uma interface SIP/CSTA, certifique-se de implantar um gateway SIP/CSTA compatível com o PBX, incluindo o suporte a protocolos de sinalização específicos do fornecedor de PBX proprietário. Para obter detalhes sobre os recursos, consulte cada fornecedor diretamente.

Quando estiver pronto para implantar um gateway SIP/CSTA que possa ser integrado ao Lync Server para controle de chamada remota, consulte também o fornecedor do gateway ou a documentação do gateway do fornecedor em relação à sintaxe exigida pelo gateway para as seguintes informações:

  - URI do servidor de linha do gateway

  - URI de linha para os usuários que serão atribuídos ao gateway

As configurações anteriores são necessárias durante a configuração do usuário e devem ser especificadas como esperado pelo gateway para direcionar e conectar-se ao PBX corretamente.

Você pode consultar fornecedores no site do programa de interoperabilidade aberto da Microsoft Unified Communications em [http://go.microsoft.com/fwlink/p/?linkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309).

</div>

<div>

## <a name="step-2-configure-lync-server-to-route-csta-requests-to-the-sipcsta-gateway"></a>Etapa 2: configurar o Lync Server para direcionar solicitações de CSTA para o gateway SIP/CSTA

Você deve criar rotas estáticas nos pools do Lync Server para o endereço de destino (URI de servidor) de todos os gateways SIP/CSTA em sua implantação para os quais você pretende rotear solicitações de controle de chamada remota. Você também deve criar uma entrada de aplicativo confiável que corresponda a cada endereço de destino. Quando você designa o gateway como um aplicativo confiável, ele recebe um status de confiança para ser executado como parte do ambiente do Lync Server, apesar de ser desenvolvido por terceiros (e executa o que é conhecido como um *serviço externo* porque é um serviço que não é um parte interna do produto). Por fim, se o Lync Server se conectar ao gateway SIP/CSTA usando uma conexão TCP (Transmission Control Protocol) em vez de uma conexão TLS (Transport Layer Security), você também deve definir o endereço IP do gateway usando o construtor de topologias.

Para obter detalhes sobre como configurar rotas estáticas, consulte [Configurar uma rota estática para o controle de chamada remota no Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md).

Para obter detalhes sobre como configurar entradas de aplicativos confiáveis, consulte [Configurar uma entrada de aplicativo confiável para o controle de chamada remota no Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md).

Para obter detalhes sobre como definir um endereço IP do gateway SIP/CSTA no construtor de topologias, consulte [definir um endereço IP de gateway SIP/CSTA no Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md).

</div>

<div>

## <a name="step-3-configure-lync-users-for-remote-call-control"></a>Etapa 3: Configurar usuários do Lync para controle de chamada remota

Depois que os usuários tiverem sido habilitados para o Lync Server, você poderá usar o painel de controle do Lync Server ou o Shell de gerenciamento do Lync Server para habilitá-los para o controle de chamada remota. É durante esta etapa de implantação que você atribui a cada usuário um URI de servidor de linha e um URI de linha. O URI do servidor de linha é o URI SIP do gateway SIP/CSTA que você planeja atribuir ao usuário. O URI da linha é o número de telefone exclusivo atribuído ao usuário.

Para obter detalhes sobre a configuração de usuários para controle de chamada remota, consulte [habilitar usuários do Lync para controle de chamada remota no Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).

</div>

<div>

## <a name="step-4-define-the-lync-server-phone-number-normalization-rules"></a>Etapa 4: definir as regras de normalização do número de telefone do Lync Server

Em cenários de controle de chamada remota, o Lync Server usa regras de normalização de número de telefone para converter números de telefone recebidos do gateway SIP/CSTA para o formato E. 164. Os números de telefone devem estar nesse formato padronizado para que determinados recursos de controle de chamada remota funcionem corretamente. O controle de chamada remota usa as mesmas regras de normalização de número de telefone que você configura para a normalização do número de telefone do serviço de catálogo de endereços, que são diferentes das regras de normalização do número de telefone usadas para o Enterprise Voice.

Para obter detalhes sobre como o controle de chamada remota usa as regras de normalização do número de telefone, consulte [normalização do número de telefone e controle de chamada remota no Lync Server 2013](lync-server-2013-remote-call-control-and-phone-number-normalization.md). Para obter detalhes sobre regras de normalização de número de telefone para o serviço de catálogo de endereços, consulte [Administração do serviço de catálogo de endereços no tópico do Lync Server 2013](lync-server-2013-administering-the-address-book-service.md) na documentação de operações.

</div>

</div>

<span> </span>

</div>

</div>

</div>

