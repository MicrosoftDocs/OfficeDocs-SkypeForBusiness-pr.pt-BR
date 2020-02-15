---
title: 'Lync Server 2013: componentes e topologias do servidor de mediação'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Mediation Server
ms:assetid: 71397168-36c3-4d21-b8ef-db6a751634ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398537(v=OCS.15)
ms:contentKeyID: 48184487
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9369c7ab74f19b8ccc53ff0c071e0458b21e6e0f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008743"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-mediation-server-in-lync-server-2013"></a>Componentes e topologias para o servidor de mediação no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-21_

Este tópico descreve os componentes nos quais o servidor de mediação é dependente e as topologias nas quais o servidor de mediação pode ser implantado

<div>

## <a name="dependencies"></a>Dependências

O servidor de mediação tem as seguintes dependências:

  - **Registrador.** Obrigatório. O registrador é o próximo salto para a sinalização nas interações do servidor de mediação com a rede do Lync Server 2013. Observe que o servidor de mediação pode ser colocado em um servidor front-end junto com o registrador, além de ser instalado em um pool autônomo que consiste apenas em servidores de mediação. O registrador está posicionado com um servidor de mediação e um gateway PSTN em um aparelho de filial persistente.

  - **Monitoring Server.** É opcional, mas altamente recomendável. O Monitoring Server permite que o servidor de mediação Registre as métricas de qualidade associadas às suas sessões de mídia.

  - **Servidor de borda.** É necessário para o suporte ao usuário externo. O servidor de borda permite que o servidor de mediação interaja com usuários que estão localizados atrás de um NAT ou firewall.

</div>

<div>

## <a name="topologies"></a>Topologias

O Lync Server 2013, o servidor de mediação é colocado por padrão com uma instância do registrador em um servidor Standard Edition, um pool de front-ends ou um aparelho de filial persistente. Todos os servidores de mediação em um pool de front-ends devem ser configurados de forma idêntica.

Onde o desempenho é um problema, pode ser preferível implantar um ou mais servidores de mediação em um pool autônomo dedicado. Ou, se você estiver implantando o tronco SIP, recomendamos que você implante um pool do servidor de mediação autônomo.

Se você implantar conexões SIP diretas com um gateway PSTN qualificado que oferece suporte a bypass de mídia e balanceamento de carga DNS, um pool do Servidor de Mediação autônomo não será necessário. Um pool de Servidores de Mediação autônomo não é necessário, pois os gateways qualificados são capazes de balanceamento de carga DNS para um pool de Servidores de Mediação e podem receber tráfego de qualquer Servidor de Mediação em um pool.

Também recomendamos que você posicione o Servidor de Mediação em um pool Front-End após implantar o IP-PBXs ou se conectar ao controlador de borda da sessão (SBC) de um Internet Telephony Server Provider, contanto que qualquer uma das seguintes condições seja atendida:

  - O IP-PBX ou SBC está configurado para receber tráfego de qualquer Servidor de Mediação no pool e pode rotear tráfego uniformemente para todos os Servidores de Mediação no pool.

  - O IP-PBX não suporta bypass de mídia, mas o pool de front-ends que está hospedando o servidor de mediação pode lidar com a transcodificação de voz para chamadas às quais o bypass de mídia não se aplica.

Você pode usar a ferramenta de planejamento do Microsoft Lync Server 2013 para avaliar se o pool de front-ends onde você deseja colocar o servidor de mediação pode lidar com a carga. Se o seu ambiente não pode cumprir estes requisitos, você deve implantar um pool do Servidor de Mediação autônomo.

Para obter detalhes sobre a topologia a ser implantada, consulte [Deployment Guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).

A figura a seguir mostra uma topologia simples que consiste em dois sites conectados por um link WAN. O servidor de mediação é colocado com o registrador em um pool de front-ends no local 1. Os servidores de mediação no site 1 controlam o gateway PSTN no local 1 e o gateway no local 2. Nessa topologia, o bypass de mídia é habilitado globalmente para usar as informações do site e da região, e os troncos para cada gateway PSTN (GW1 e GW2) têm bypass habilitado.

**Exemplo de sites conectados por um link WAN com um Servidor de Mediação no Site 1 e um gateway PSTN no Site 2**

![Topologia de voz com gateway WAN do servidor de mediação](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "Topologia de voz com gateway WAN do servidor de mediação")

A figura a seguir mostra uma topologia simples onde o servidor de mediação é colocado no pool de front-ends do registrador no local 1 e tem uma conexão SIP direta com o IP-PBX no local 1. Nesta figura, o servidor de mediação também controla um gateway PSTN no site 2. Suponha que os usuários do Lync existam nos dois sites 1 e 2. Além disso, suponha que o IP-PBX tenha um processador de mídia associado que deve ser percorrido por todas as mídias originárias de pontos de extremidade do Lync antes de ser enviado a pontos de extremidade de mídia controlados pelo IP-PBX. Nessa topologia, o bypass de mídia é habilitado globalmente para usar as informações do site e da região, e os troncos para o PBX e o gateway PSTN têm o bypass de mídia habilitado.

**Exemplo de sites conectados por um link WAN com um Servidor de Mediação no Site 1 e um PBX no Site 2**

![PBX WAN do servidor de mediação de topologia de voz](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "PBX WAN do servidor de mediação de topologia de voz")

Para obter detalhes sobre o planejamento de topologias de PBX, confira [diretrizes de implantação para o servidor de mediação no Lync server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) e [Opções de implantação de SIP direto no Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md).

A última figura neste tópico mostra uma topologia onde o servidor de mediação está conectado ao SBC de um provedor de serviços de telefonia da Internet. Para obter detalhes sobre topologias de tronco SIP, consulte [troncos SIP no Lync Server 2013](lync-server-2013-sip-trunking.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

