---
title: 'Lync Server 2013: Suporte à integração Exchange UM hospedado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Support for hosted Exchange UM integration
ms:assetid: c7573ec3-013c-48d9-b59b-2a5427e6da35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398821(v=OCS.15)
ms:contentKeyID: 48185376
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56ba107c9a782acb15ccd8d57f82cf567f2b75e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844846"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="support-for-hosted-exchange-um-integration-in-lync-server-2013"></a>Suporte à integração Exchange UM hospedado no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-21_

O aplicativo de roteamento ExUM do Lync Server 2013 é compatível com a integração com a Unificação de mensagens do Exchange em um ambiente local, no qual o Lync Server 2013 e o Exchange UM são instalados localmente na sua empresa ou no UM Exchange UM hospedado por um provedor de serviços, conforme mostrado no diagrama a seguir.

![Implantação do Exchange um do Lync Server local] (images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "Implantação do Exchange um do Lync Server local")

Há suporte para os seguintes modos:

  - **Modo local do**   Lync Server 2013 e do Exchange um são implantados em servidores locais na sua empresa.

  - **O modo**   intersite do Lync Server 2013 é implantado em servidores locais na sua empresa e o Exchange um está hospedado em um recurso do provedor de serviços online, como um Data Center online do Microsoft Exchange.

  - **Modo misto a**   implantação do Lync Server 2013 tem algumas caixas de correio de usuário hospedadas em servidores locais que executam o Microsoft Exchange Server em sua empresa e algumas caixas de correio hospedadas em um data center do serviço do Exchange.
    
    <div>
    

    > [!NOTE]  
    > O modo misto pode ser usado como uma solução de transição durante a avaliação e Stepwise a migração de usuários para o Exchange UM hospedada ou como uma solução permanente se você optar por manter os serviços de UM dos usuários no local após a migração de outras pessoas.

    
    </div>

Para integrar o Lync Server 2013 com o Exchange UM hospedado, você deve configurar um *espaço de endereço SIP compartilhado* (também chamado de *domínio dividido*). Nesta configuração, o Lync Server 2013 e o provedor de serviços do Exchange UM hospedado por terceiros podem acessar o mesmo espaço de endereço de domínio SIP. Para obter detalhes, consulte [arquitetura de integração de um Exchange um hospedada no Lync Server 2013](lync-server-2013-hosted-exchange-um-integration-architecture.md) na documentação de planejamento.

</div>

<span> </span>

</div>

</div>

</div>

