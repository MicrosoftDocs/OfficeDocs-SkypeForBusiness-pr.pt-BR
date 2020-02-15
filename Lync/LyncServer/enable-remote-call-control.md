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
ms.openlocfilehash: 9e7e6fef4b882a7358a49a994c10829ad5c8a257
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006387"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-remote-call-control"></a>Habilitar o controle de chamada remota

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-02_

O controle de chamada remota permite que os usuários controlem seus telefones de PBX (central privada de comutação telefônica) de área de trabalho usando o Lync Server 2013. Se você implantou o controle de chamada remota no seu ambiente herdado e deseja migrar o Lync Server 2013, é necessário executar as seguintes tarefas:

1.  Instalar um gateway SIP/CSTA e configura-lo para comunicar-se com sua PBX. Você precisa executar esta etapa ao implantar o pool piloto do Lync Server 2013.

2.  Após mesclar sua topologia e migrar suas políticas e configurações, configure o Lync Server 2013 para rotear solicitações de CSTA para o gateway SIP/CSTA. Esta etapa pe uma etapa manual que segue a migração automatizada. Para configurar o encaminhamento de solicitações CSTA, faço o seguinte:
    
      - Remova as entradas de host autorizadas herdadas (conhecidas como *entradas de servidor confiável* no Lync Server 2013). Se você estiver migrando usuários de sua implantação herdada, certifique-se de remover todas as entradas de host autorizadas existentes que você criou para o gateway SIP/CSTA antes de configurar novas entradas de aplicativo confiável no pool piloto do Lync Server 2013. Para obter detalhes sobre como remover as entradas de host autorizadas herdadas, consulte [remover uma entrada de host autorizada](remove-an-authorized-host-entry.md).
    
      - Configure uma rota estática para o controle de chamadas remotas. Você pode configurar uma rota estática para pool individuais que você queira que de suporte ao controle de chamadas remotas ou você pode configurar uma rota estática global, assim cada pool que não estiver configurado com a rota estática a nível de pool usa a rota estática globa. Para obter detalhes sobre como configurar a rota estática, consulte [Configurar uma rota estática para controle de chamada remota no Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md) na documentação de implantação.
    
      - Configure uma entrada de aplicação confiável para ocontrol de chamadas remotas em cada pool para aqueles que você queira que suporte o controle de chamadas remotas. Para obter detalhes sobre como configurar uma entrada de aplicativo confiável, consulte [Configurar uma entrada de aplicativo confiável para controle de chamada remota no Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md) na documentação de implantação.

3.  Se você implantou um gateway SIP/CSTA que usa TCP (Transmission Control Protocol) para se conectar ao Lync Server 2013, defina o endereço IP do gateway no construtor de topologias. Para obter detalhes sobre como definir o endereço IP, consulte [definir um endereço IP de gateway SIP/CSTA no Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) na documentação de implantação.

4.  Configure os usuários do Lync 2013 para controle de chamada remota habilitando o controle de chamada remota e atribuindo um URI (Uniform Resource Identifier) do servidor de linha e um URI de linha. Ao migrar usuários da implantação herdada para o Lync Server 2013, as configurações de controle de chamada remota são migradas junto com as outras configurações do usuário.

5.  Se você personalizou a regras na sua implementação herdada,  é necessário realizar algumas terefas manuais após a migração automatizada das políticas e configuração esteja concluída para migrar as regras personalizadas. Caso não tenha personalizado as regras, o Catálogo de Endereços é migrado juntamente com sua topologia. Para mais detalhes sobre como migrar manualmente as regras, consulte [Migrate Address Book](migrate-address-book_1.md).

</div>

<span> </span>

</div>

</div>

</div>

