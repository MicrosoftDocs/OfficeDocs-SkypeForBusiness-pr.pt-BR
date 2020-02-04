---
title: Habilitar o controle de chamada remota
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Enable remote call control
ms:assetid: 0b91d418-e6ed-4556-97af-e8523e01f249
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204664(v=OCS.15)
ms:contentKeyID: 48183380
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 190f4e56a291ce48b5cd18b2dcd3e1b3461e3d7d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722981"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-remote-call-control"></a>Habilitar o controle de chamada remota

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-02_

O controle de chamada remota permite que os usuários controlem seus telefones PBX (Private Branch Exchange) da área de trabalho usando o Lync Server 2013. Se você tiver implantado o controle de chamada remota em seu ambiente herdado e quiser migrar o Lync Server 2013, será necessário executar as seguintes tarefas:

1.  Instale um gateway SIP/CSTA e configure-o para se comunicar com o seu PBX. Você precisa fazer esta etapa ao implantar o pool piloto do Lync Server 2013.

2.  Depois de Mesclar sua topologia e migrar suas políticas e configurações, configure o Lync Server 2013 para direcionar as solicitações de CSTA para o gateway SIP/CSTA. Esta etapa é uma etapa manual que segue a migração automatizada. Para configurar o roteamento de solicitações de CSTA, faça o seguinte:
    
      - Remova as entradas de host autorizadas herdadas (conhecidas como *entradas de servidor confiáveis* no Lync Server 2013). Se você estiver migrando usuários da implantação herdada, certifique-se de remover todas as entradas de host autorizadas existentes que você criou para o gateway SIP/CSTA antes de configurar novas entradas de aplicativo confiável no pool piloto do Lync Server 2013. Para obter detalhes sobre como remover entradas de host autorizadas herdadas, consulte [remover uma entrada de host autorizado](remove-an-authorized-host-entry.md).
    
      - Configurar uma rota estática para o controle de chamada remota. Você pode configurar uma rota estática para pools individuais para os quais você deseja dar suporte para controle de chamada remota, ou pode configurar uma rota estática global para que cada pool que não esteja configurado com uma rota estática em nível de pool use a rota estática global. Para obter detalhes sobre como configurar a rota estática, consulte [Configurar uma rota estática para o controle de chamada remota no Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md) na documentação de implantação.
    
      - Configure uma entrada de aplicativo confiável para controle de chamada remota em cada pool para o qual você deseja dar suporte ao controle de chamada remota. Para obter detalhes sobre como configurar uma entrada de aplicativo confiável, consulte [Configurar uma entrada de aplicativo confiável para o controle de chamada remota no Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md) na documentação de implantação.

3.  Se você implantou um gateway SIP/CSTA que usa o protocolo de controle de transmissão (TCP) para se conectar ao Lync Server 2013, defina o endereço IP do gateway no construtor de topologias. Para obter detalhes sobre como definir o endereço IP, consulte [definir um endereço IP de gateway SIP/CSTA no Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) na documentação de implantação.

4.  Configurar os usuários do Lync 2013 para controle de chamada remota habilitando o controle de chamada remota e atribuindo um URI (Uniform Resource Identifier) do servidor de linha e um URI de linha. Quando você migra os usuários da sua implantação herdada para o Lync Server 2013, as configurações do controle de chamada remota são migradas juntamente com as outras configurações do usuário.

5.  Se você tiver personalizado regras de normalização de número de telefone do catálogo de endereços em sua implantação herdada, será necessário executar algumas tarefas manuais após a conclusão da migração automatizada de políticas e configurações para migrar as regras de normalização personalizadas. Se você não tiver personalizado as regras de normalização, o catálogo de endereços será migrado juntamente com o restante da sua topologia. Para obter detalhes sobre a migração manual das regras de normalização personalizada, consulte [migrar catálogo de endereços](migrate-address-book_1.md).

</div>

<span> </span>

</div>

</div>

</div>

