---
title: 'Lync Server 2013: Suporte a certificado curinga'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Wildcard certificate support
ms:assetid: 0bae2aa8-b6dc-46f5-a3be-3fe7581809d4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202161(v=OCS.15)
ms:contentKeyID: 48183382
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a3e64dcfd16212e618a8ebe152bd2516a25b26d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727491"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="wildcard-certificate-support-in-lync-server-2013"></a>Suporte a certificado curinga no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-03-21_

O Lync Server 2013 usa certificados para fornecer criptografia de comunicação e autenticação de identidade do servidor. Em alguns casos, como a publicação na Web por meio do proxy inverso, a entrada de nome alternativo de assunto (SAN) forte para o nome de domínio totalmente qualificado (FQDN) do servidor que está apresentando o serviço não é necessária. Nesses casos, você pode usar certificados com entradas de SAN curinga (geralmente conhecidas como "certificados curinga") para reduzir o custo de um certificado solicitado de uma autoridade de certificação pública e para reduzir a complexidade do processo de planejamento de certificados .

<div>


> [!WARNING]  
> Para manter a funcionalidade dos dispositivos de comunicação unificada (UC) (por exemplo, telefones de mesa), você deve testar cuidadosamente o certificado implantado para garantir que os dispositivos funcionarão corretamente após a implementação de um certificado curinga.



</div>

Não há suporte para uma entrada de curinga como o nome do requerente (também conhecido como o nome comum ou CN) para qualquer função. As seguintes funções de servidor são suportadas ao usar entradas de curinga na SAN:

  - <span></span>  
    **Proxy reverso.**    Há suporte para a entrada de San curinga para o certificado de publicação URL simples (reunião e discagem).

  - <span></span>  
    **Proxy reverso.**    Há suporte para a entrada de San curinga nas entradas de San para LyncDiscover no certificado de publicação.

  - <span></span>  
    **Diretor.**    Há suporte para a entrada de San curinga para URLs simples (atender e fazer chamadas) e para entradas de San para LyncDiscover e LyncDiscoverInternal em Web Components do director.

  - <span></span>  
    **Servidor front-end (Standard Edition) e pool de front-end (Enterprise Edition).** Há suporte para a entrada de SAN curinga para URLs simples (atender e discagem) e para entradas de SAN para LyncDiscover e LyncDiscoverInternal em componentes de front-end Web.

  - <span></span>  
    **Exchange Unified Messaging (UM).**    O servidor não usa entradas de San quando implantado como um servidor autônomo.

  - <span></span>  
    **Servidor de acesso para cliente do Microsoft Exchange Server.**    As entradas CURINGA na San têm suporte para clientes internos e externos.

  - <span></span>  
    **Exchange Unified Messaging (UM) e servidor de acesso para cliente do Microsoft Exchange Server no mesmo servidor.**    Há suporte para entradas de San curinga.

Funções de servidor que não são abordadas neste tópico:

  - Funções de servidor interno (incluindo, entre outros, o servidor de mediação, o servidor de monitoramento e o servidor de mediação, o aparelho de ramificação sobreviventes ou o servidor de ramificação sobreviventes)

  - Interfaces do servidor de borda externa

  - Servidor de borda interna
    
    <div>
    

    > [!NOTE]  
    > Para a interface do servidor de borda interna, uma entrada de curinga pode ser atribuída à SAN e é compatível. A SAN no servidor de borda interno não é consultada e uma entrada de SAN por curinga tem um valor limitado.

    
    </div>

Para obter detalhes sobre configurações de certificado, incluindo o uso de caracteres curinga em certificados, consulte os seguintes tópicos:

  - [Requisitos de certificado para servidores internos no Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Requisitos de certificado para acesso do usuário externo no Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [Resumo de certificado - Cargas de DNS e de HLB balanceadas no Lync Server 2013](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [Resumo do certificado - Diretor único no Lync Server 2013](lync-server-2013-certificate-summary-single-director.md)

  - [Resumo de certificado - pool Certificate summary - pool de diretores em escala, balanceador de carga de hardware no Lync Server 2013](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [Resumo de certificado - Proxy reverso no Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [Orientações para integração de Unificação de Mensagens local e Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

Para obter detalhes sobre como configurar certificados para Exchange, incluindo o uso de caracteres curinga, consulte a documentação do produto Exchange 2013.

</div>

<span> </span>

</div>

</div>

</div>

