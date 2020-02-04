---
title: 'Lync Server 2013: Lista de verificação de tronco SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunk deployment checklist
ms:assetid: 94f4f03e-19d5-4198-92be-e4076dbb959a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398755(v=OCS.15)
ms:contentKeyID: 48184891
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef670fc4ae9e8a9acba3277a00fc0daf6ff766b3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764487"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunk-deployment-checklist-for-lync-server-2013"></a>Lista de verificação de tronco SIP para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-21_

Antes de poder implantar um tronco SIP, você e seu provedor de serviços devem trocar informações básicas de conexão sobre seus respectivos pontos de extremidade de tronco SIP.

Obtenha as seguintes informações para cada gateway do ITSP ao qual você irá se conectar:

  - Endereço IP

  - FQDN (nome de domínio totalmente qualificado)

<div>


> [!NOTE]  
> O provedor de serviço pode solicitar que você se conecte a mais de um gateway do ITSP. Nesse caso, você deve configurar uma conexão entre cada gateway do ITSP e cada servidor de mediação em seu pool.



</div>

As informações que você fornece ao seu provedor de serviço dependem do seu tipo de conexão de tronco SIP:

  - Para conexões de rótulo de multiprotocolo (MPLS) ou de rede privada, forneça ao ITSP o endereço IP publicamente roteável do roteador em sua rede de perímetro (também conhecido como DMZ, zona desmilitarizada e sub-rede filtrada). Verifique se o gateway ou o controle de borda de sessão (SBC) no ITSP pode chegar a este endereço. Além disso, dê ao ITSP o FQDN do servidor de mediação.

  - Para conexões VPN (rede virtual privada), dê ao ITSP o endereço IP do seu servidor VPN.

<div>

## <a name="certificate-considerations"></a>Considerações sobre certificado

Para determinar se você precisa de um certificado para o entroncamento SIP, consulte o ITSP sobre o suporte ao protocolo:

1.  Se o seu ITSP der suporte somente para TCP (Transmission Control Protocol), você não precisará de um certificado.

2.  Se o seu ITSP suporta TLS (Transport Layer Security), o ITSP deve fornecer um certificado.

<div>


> [!NOTE]  
> O SIP funciona em conjunto com o protocolo de transporte em tempo real (RTP) ou SSTP (protocolo de transporte em tempo real seguro), os protocolos que gerenciam os dados de voz reais nas chamadas de protocolo de voz pela Internet (VoIP).



</div>

</div>

<div>

## <a name="deployment-process"></a>Processo de implantação

Para implementar o lado do Lync Server da conexão do tronco SIP, siga estas etapas:

1.  Usando o construtor de topologias do Lync Server, crie e configure a topologia de domínio SIP. Para obter detalhes, consulte [definir e configurar uma topologia no construtor de topologias para o Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) na documentação de implantação.

2.  Usando o painel de controle do Lync Server, configure o roteamento de voz para o novo domínio SIP. Para obter detalhes, consulte [Configurando troncos no Lync Server 2013](lync-server-2013-configuring-trunks.md) na documentação de implantação.

3.  Testar a conectividade usando o cmdlet **Test-CsPstnOutboundCall** . Para obter detalhes, consulte a documentação do Shell de gerenciamento do Lync Server ou a ajuda do Shell de gerenciamento do Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

