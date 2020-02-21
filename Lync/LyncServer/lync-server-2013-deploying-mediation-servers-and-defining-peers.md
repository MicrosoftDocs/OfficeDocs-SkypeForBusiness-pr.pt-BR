---
title: 'Lync Server 2013: implantando servidores de mediação e definindo pares'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Mediation Servers and defining peers
ms:assetid: a684f1da-6671-4011-adf6-2db49e2528e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412780(v=OCS.15)
ms:contentKeyID: 48185077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03eca427f644d6f94ae7a52900b80320e2517ed2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195324"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-mediation-servers-and-defining-peers-in-lync-server-2013"></a>Implantando servidores de mediação e definindo pares no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-21_

A carga de trabalho do Enterprise Voice, conferência discada e aplicativos avançados do Enterprise Voice (aplicativo de grupo de resposta, aplicativo de estacionamento de chamada, controle de admissão de chamadas (CAC) e assim por diante), estão disponíveis em pools de front-ends. Com o Lync Server 2013, a funcionalidade do servidor de mediação está incorporada ao servidor front-end. Um servidor de mediação autônomo separado não é mais necessário. Os pools de front-ends podem se comunicar diretamente com os gateways com suporte (um gateway PSTN (rede telefônica pública comutada) ou um IP-PBX, removendo a necessidade de um servidor de mediação servir como intermediário.

A única exceção é se você configurar um tronco SIP para se conectar a um Controlador de Borda de Sessão de um Provedor de Serviços de Telefonia e Internet. Para conectar sua infraestrutura do Enterprise Voice ao seu provedor de tronco SIP, um servidor de mediação separado deve ser implantado.

A conexão entre o Lync Server (o componente do servidor de mediação em um pool de front-ends ou servidor de mediação autônomo) e um gateway é definido como uma associação lógica chamada de *tronco*. Os tópicos nesta seção descrevem como definir um tronco e como implantar um Servidor de Mediação autônomo, se você se conectar a um tronco SIP.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Definir um servidor de mediação no construtor de topologias no Lync Server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md)

  - [Definir um gateway no construtor de topologia no Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md)

  - [Instalar os arquivos para o servidor de mediação no Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md)

  - [Definir troncos adicionais no construtor de topologias no Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md)

</div>

<div>

## <a name="related-sections"></a>Seções Relacionadas

[Configurando a conferência discada no Lync Server 2013](lync-server-2013-configuring-dial-in-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

