---
title: 'Lync Server 2013: lista de verificação de implantação de tronco SIP'
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
ms.openlocfilehash: 08beaff401b8f261d311ad0d05a07f5221131864
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200304"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sip-trunk-deployment-checklist-for-lync-server-2013"></a>Lista de verificação de implantação de tronco SIP para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-21_

Antes de implantar um tronco SIP, você e seu provedor de serviços devem trocar algumas informações básicas de conexão sobre seus respectivos pontos de extremidade de tronco SIP.

Obtenha as informações a seguir para cada gateway ITSP com o qual você se conectará:

  - Endereço IP

  - FQDN (nome de domínio totalmente qualificado)

<div>


> [!NOTE]  
> O provedor de serviços pode pedir a você que se conecte a mais de um gateway ITSP. Nesse caso, você deve configurar uma conexão entre cada gateway do ITSP e cada servidor de mediação em seu pool.



</div>

As informações que você fornece aos seu provedor de serviços dependem do tipo de conexão do seu tronco SIP:

  - Para MPLS (Multiprotocol Label Switching) ou conexões de rede privada, forneça ao ITSP o Endereço IP roteável publicamente do roteador em sua rede de perímetro (também conhecida como sub-rede filtrada). Verifique se o gateway ou Controlador de Borda de Sessão no ITSP pode alcançar este endereço. Além disso, forneça ao ITSP o FQDN do seu servidor de mediação.

  - Para conexões VPN (rede virtual privada ), forneça ao ITSP o endereço IP do seu servidor VPN.

<div>

## <a name="certificate-considerations"></a>Considerações de Certificado

Para determinar se você precisa de um certificado para tronco SIP, verifique com seu ITSP sobre suporte de protocolo:

1.  Se seu ITSP oferecer suporte somente ao protocolo TCP, não será necessário um certificado.

2.  Se seu ITSP oferecer suporte ao protocolo TLS, o ITSP deverá fornecer um certificado a você.

<div>


> [!NOTE]  
> O SIP funciona em conjunto com protocolo RTP ou SRTP, os protocolos que gerenciam os dados de voz reais em chamadas VoIP.



</div>

</div>

<div>

## <a name="deployment-process"></a>Processo de implantação

Para implementar o lado do Lync Server da conexão do tronco SIP, siga estas etapas:

1.  Usando o construtor de topologias do Lync Server, crie e configure a topologia do domínio SIP. Para obter detalhes, consulte [definir e configurar uma topologia no construtor de topologias para o Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) na documentação de implantação.

2.  Usando o painel de controle do Lync Server, configure o roteamento de voz para o novo domínio SIP. Para obter detalhes, consulte [Configuring Trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) na documentação de implantação.

3.  Teste a conectividade usando o cmdlet **Test-CsPstnOutboundCall**. Para obter detalhes, consulte a documentação do Shell de gerenciamento do Lync Server ou a ajuda do Shell de gerenciamento do Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

