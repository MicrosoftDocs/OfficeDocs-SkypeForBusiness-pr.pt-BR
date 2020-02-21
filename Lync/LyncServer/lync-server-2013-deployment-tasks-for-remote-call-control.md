---
title: 'Lync Server 2013: tarefas de implantação para controle de chamada remota'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment tasks for remote call control
ms:assetid: 20218871-4f27-4611-9b7e-c0ca55908284
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558624(v=OCS.15)
ms:contentKeyID: 48183599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b81da85fb7aff98728d0a79478164436cce5194a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198184"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-tasks-for-remote-call-control-in-lync-server-2013"></a>Tarefas de implantação para o controle de chamada remota no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-05_

Este tópico descreve as tarefas de implantação que devem ser realizadas para habilitar o controle de chamada remota para usuários no seu ambiente do Lync Server.

<div>


> [!NOTE]  
> Se você estiver migrando usuários previamente habilitados para controle de chamada remota no Microsoft Office Communicator 2007 R2, deverá executar uma tarefa de implantação adicional antes de começar a executar as tarefas de implantação de controle de chamada remota descritas neste tópico. Durante o processo de migração para o Lync Server, as entradas de aplicativos confiáveis (anteriormente conhecidas como <EM>entradas de host autorizadas</EM>) devem ser removidas usando as ferramentas administrativas do Office Communications Server 2007 R2, conforme apropriado.<BR>Para obter detalhes sobre como remover hosts autorizados, consulte <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">remover um host autorizado herdado no Lync Server 2013 (opcional)</A>.



</div>

<div>

## <a name="step-1-install-and-configure-the-sipcsta-gateway-to-communicate-with-your-pbx"></a>Etapa 1: Instale e configure o Gateway SIP/CSTA para se comunicar com seu PBX

Você precisa instalar pelo menos um gateway SIP/CSTA que possa se conectar ao Lync Server e ao servidor de filial privada (PBX) existente no seu ambiente para fornecer recursos de controle de chamada remota aos seus usuários. Um gateway SIP/CSTA é um gateway entre o SIP e um CSTA (aplicativo de telecomunicações com suporte por computador). Independente de você instalar múltiplos gateways ou somente um, cada usuário pode ser configurado somente com um gateway ou PBX. Se o PBX existente não tiver uma interface SIP/CSTA, implante um gateway SIP/CSTA que possa suportar o PBX, incluindo o suporte para protocolos de sinalização específicos do fornecedor do PBX proprietário. Para obter os detalhes das capacidades, consulte cada fornecedor diretamente.

Quando estiver pronto para implantar um gateway SIP/CSTA que possa se integrar ao Lync Server para controle de chamada remota, consulte também o fornecedor do gateway ou a documentação do gateway do fornecedor sobre a sintaxe necessária para o gateway para as seguintes informações:

  - URI do Servidor de linha do gateway

  - URI da linha para usuários que serão atribuídos ao gateway

As configurações acima são exigidas durante a configuração do usuário e devem ser especificadas como esperado pelo gateway, para encaminhar e se conectar corretamente ao PBX.

Você pode consultar fornecedores no site do programa de interoperabilidade aberta do Microsoft Unified Communications em [https://go.microsoft.com/fwlink/p/?linkId=203309](https://go.microsoft.com/fwlink/p/?linkid=203309).

</div>

<div>

## <a name="step-2-configure-lync-server-to-route-csta-requests-to-the-sipcsta-gateway"></a>Etapa 2: configurar o Lync Server para rotear solicitações de CSTA para o gateway SIP/CSTA

Você deve criar rotas estáticas em pools do Lync Server para o endereço de destino (URI de servidor) de todos os gateways SIP/CSTA em sua implantação para o qual você pretende rotear as solicitações de controle de chamada remota. Crie também uma entrada de aplicativo confiável que corresponda a cada endereço de destino. Quando você designar o gateway como um aplicativo confiável, ele receberá um status confiável para ser executado como parte do ambiente do Lync Server, embora seja desenvolvido por um terceiro (e execute o que é conhecido como um *serviço externo* , pois é um serviço que não é uma parte interna do produto). Por fim, se o Lync Server se conectar ao gateway SIP/CSTA usando uma conexão TCP (Transmission Control Protocol) em vez de uma conexão TLS (Transport Layer Security), você também deve definir o endereço IP do gateway usando o construtor de topologias.

Para obter detalhes sobre como configurar rotas estáticas, consulte [Configurar uma rota estática para controle de chamada remota no Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md).

Para obter detalhes sobre como configurar as entradas de aplicativos confiáveis, consulte [Configurar uma entrada de aplicativo confiável para controle de chamada remota no Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md).

Para obter detalhes sobre como definir um endereço IP de gateway SIP/CSTA no construtor de topologias, consulte [definir um endereço IP de gateway SIP/CSTA no Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md).

</div>

<div>

## <a name="step-3-configure-lync-users-for-remote-call-control"></a>Etapa 3: Configurar usuários do Lync para controle de chamada remota

Depois que os usuários tiverem sido habilitados para o Lync Server, você poderá usar o painel de controle do Lync Server ou o Shell de gerenciamento do Lync Server para habilitá-los para controle de chamada remota. É durante esta etapa da implementação que você atribui a cada usuário um URI de servidor de linha e um URI de linha. O URI do servidor de linha é o URI SIP do gateway SIP/CSTA que você planeja atribuir ao usuário. O URI de linha é o número de telefone exclusivo atribuído ao usuário.

Para obter detalhes sobre como configurar usuários para controle de chamada remota, consulte [habilitar usuários do Lync para controle de chamada remota no Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).

</div>

<div>

## <a name="step-4-define-the-lync-server-phone-number-normalization-rules"></a>Etapa 4: Defina as regras de normalização do número de telefone do Lync Server

Em cenários de controle de chamada remota, o Lync Server usa regras de normalização de número de telefone para converter números de telefone que ele recebe do gateway SIP/CSTA para o formato E. 164. Os números de telefone devem estar neste formato padronizado para que certos recursos do controle de chamada remota funcionem corretamente. O controle de chamada remota utiliza as mesmas regras de normalização do número de telefone que você configura para o Serviço de Agenda, que são diferentes das regras usadas para o Enterprise Voice.

Para obter detalhes sobre como o controle de chamada remota usa regras de normalização de número de telefone, consulte [controle de chamada remota e normalização de número de telefone no Lync Server 2013](lync-server-2013-remote-call-control-and-phone-number-normalization.md). Para obter detalhes sobre as regras de normalização de número de telefone do serviço de catálogo de endereços, consulte [Administração do serviço de catálogo de endereços no Lync Server 2013](lync-server-2013-administering-the-address-book-service.md) , na documentação operações.

</div>

</div>

<span> </span>

</div>

</div>

</div>

