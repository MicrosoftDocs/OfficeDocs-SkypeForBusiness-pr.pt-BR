---
title: Suporte ao certificado curinga do Lync Server 2013
description: Suporte a certificado curinga do Lync Server 2013.
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
ms.openlocfilehash: 46cc362eb925a86b5e90d51569db6d425ba88fa6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546107"
---
# <a name="wildcard-certificate-support-in-lync-server-2013"></a>Suporte a certificados curinga no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-03-21_

O Lync Server 2013 usa certificados para fornecer criptografia de comunicação e autenticação de identidade do servidor. Em alguns casos, como em publicações na web através do proxy reverso, uma entrada forte de nome alternativo da entidade (SAN) que corresponda ao nome de domínio totalmente qualificado (FQDN) do servidor apresentando o serviço não é necessária. Nesses casos, é possível usar certificados com entradas curingas de SAN (comumente conhecidos como "certificados curinga") para reduzir o custo de um certificado solicitado por uma autoridade de certificação pública e para reduzir a complexidade do processo de planejamento para certificados.

<div>


> [!WARNING]  
> Para reter a funcionalidade de dispositivos de comunicações unificadas (UC) (por exemplo, telefones de mesa), você deve testar o certificado implantado com cuidado para garantir que os dispositivos funcionem adequadamente depois de implantar um certificado curinga.



</div>

Não há suporte para uma entrada curinga como nome de entidade (também conhecido como nome comum ou CN) para nenhuma função. As funções do servidor apresentadas a seguir são suportadas quando são usadas entradas curinga no SAN:

  - <span></span>  
    **Proxy reverso.**     A entrada de SAN curinga é suportada para o certificado de publicação URL simples (reunião e discagem).

  - <span></span>  
    **Proxy reverso.**     A entrada de SAN curinga é suportada para as entradas de SAN do LyncDiscover no certificado de publicação.

  - <span></span>  
    **Diretor.**     A entrada de SAN curinga é suportada para URLs simples (atender e discar) e para entradas de SAN para o LyncDiscover e o LyncDiscoverInternal nos componentes Web do diretor.

  - <span></span>  
    **Servidor front-end (Standard Edition) e pool de front-ends (Enterprise Edition).** A entrada de SAN curinga é suportada para URLs simples (atender e discar) e para entradas de SAN para o LyncDiscover e o LyncDiscoverInternal em componentes da Web de front-end.

  - <span></span>  
    **Unificação de mensagens (um) do Exchange.**     O servidor não usa entradas SAN quando implantado como um servidor autônomo.

  - <span></span>  
    **Servidor de acesso para cliente do Microsoft Exchange Server.**     As entradas curinga na SAN têm suporte para clientes internos e externos.

  - <span></span>  
    **Unificação de mensagens (um) do Exchange e servidor de acesso para cliente do Microsoft Exchange Server no mesmo servidor.**     Há suporte para as entradas SAN curinga.

As funções do servidor que não são abordadas neste tópico:

  - Funções de servidor interno (incluindo, mas não limitado ao servidor de mediação, servidor de arquivamento e monitoramento, aparelho de filial persistente ou servidor de filial persistente)

  - Interfaces do servidor de borda externo

  - Servidor de borda interno
    
    <div>
    

    > [!NOTE]  
    > Para a interface do servidor de borda interna, uma entrada curinga pode ser atribuída à SAN e é suportada. A SAN no servidor de borda interno não é consultada e uma entrada de SAN curinga é de valor limitado.

    
    </div>

Para obter detalhes sobre as configurações de certificado, incluindo o uso de caracteres curinga em certificados, consulte os seguintes tópicos:

  - [Requisitos de certificado para servidores internos no Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Requisitos de certificado para acesso de usuário externo no Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [Resumo de certificado-carga de DNS e HLB balanceada no Lync Server 2013](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [Resumo de certificado-diretor único no Lync Server 2013](lync-server-2013-certificate-summary-single-director.md)

  - [Resumo de certificado-pool de diretores em escala, balanceador de carga de hardware no Lync Server 2013](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [Resumo de certificado-proxy reverso no Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [Diretrizes para integrar a Unificação de mensagens local e o Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

Para obter detalhes sobre como configurar certificados para o Exchange, incluindo o uso de curingas, consulte a documentação do produto Exchange 2013.

</div>

<span> </span>

</div>

</div>

</div>

