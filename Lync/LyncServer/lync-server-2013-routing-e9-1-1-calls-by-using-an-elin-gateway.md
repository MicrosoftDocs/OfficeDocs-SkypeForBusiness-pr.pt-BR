---
title: 'Lync Server 2013: roteamento de chamadas E9-1-1 usando um gateway ELIN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Routing E9-1-1 calls by using an ELIN gateway
ms:assetid: 5a3997e3-898d-49cb-922a-4184c3373350
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204919(v=OCS.15)
ms:contentKeyID: 48184221
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93e2e3bf94175f2f0ec3f4f7528cc969fe19529c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144527"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-an-elin-gateway-in-lync-server-2013"></a>Roteamento de chamadas E9-1-1 usando um gateway ELIN no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-05_

Alguns parceiros do Programa de interoperabilidade aberta de comunicações unificadas fornecem gateways ELIN (Emergency Location Identification Number) qualificados, que podem servir como uma alternativa para uma conexão de tronco SIP para um provedor de serviços E9-1-1 qualificado. Os gateways ELIN suportam conectividade ISDN ou CAMA (Centralized Automatic Message Accounting) para os serviços E9-1-1 baseados em PSTN (rede telefônica pública comutada). Para obter detalhes sobre os parceiros que fornecem gateways ELIN e links para sua documentação [https://go.microsoft.com/fwlink/p/?LinkId=248425](https://go.microsoft.com/fwlink/p/?linkid=248425), consulte.

Como conexões de tronco SIP para provedores de serviço E9-1-1, os gateways do ELIN também fornecem o meio de roteamento de uma chamada de emergência para o ponto de resposta de segurança pública (PSAP) mais apropriado do chamador, mas esses gateways usam um ELIN como o identificador de local. Você define ELINs para cada local de resposta de emergência (ERL) em sua organização (para obter detalhes, consulte [Managing locations for Elin gateways in Lync Server 2013](lync-server-2013-managing-locations-for-elin-gateways.md)).

Quando você usa um gateway ELIN para chamadas de emergência, usa a mesma infraestrutura do Lync Server E9-1 que você usaria para uma conexão de tronco SIP. Ou seja, o banco de dados do serviço de informações de local fornece o local para o cliente do Lync Server e a política de local habilita o recurso e define o roteamento. Com um gateway ELIN, no entanto, você precisa adicionar o ELINs ao banco de dados do serviço de informações de local e fazer com que sua operadora de PSTN o carregue no banco de dados de identificação de local automática (ALI).

Quando um cliente do Lync obtém seu local do serviço de informações de local, o local inclui o ELIN. Durante uma chamada de emergência, o ELIN é incluído com a localização enviada para o gateway ELIN. O gateway ELIN identifica a chamada como uma chamada de emergência e troca o número do chamador pela Elin. O gateway ELIN, em seguida, encaminha a chamada para o PSTN com o ELIN como o número de chamada. O provedor E9-1-1 do PSTN procura o ELIN no banco de dados ALI, que é um banco de dados que acompanha o banco de dados MSAG (Catálogo de Endereços Principal). O PSTN envia a chamada para o PSAP mais apropriado com base na pesquisa ALI, e o PSAP envia socorristas para a localização do chamador com base na pesquisa ALI. O número da chamada é armazenado em cache no gateway ELIN por uma quantidade de tempo pré-definida para retorno de chamadas. Durante uma chamada de retorno, o PSAP alcança o gateway ELIN, que troca o Elin pelo número da DID (discagem direta interna).

O gateway ELIN suporta chamadas de emergência somente de dentro da rede da sua organização. Eles não suportam chamadas de emergência feitas de fora da rede.

<div>


> [!NOTE]  
> Para obter detalhes sobre como usar uma conexão de tronco SIP para chamadas de emergência, consulte <A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">Routing E9-1-1 calls by using a SIP Trunk in Lync Server 2013</A>.



</div>

O diagrama a seguir mostra como uma chamada de emergência é roteada do Lync Server para o PSAP quando você usa um gateway ELIN.

**Encaminhando chamadas de E9-1-1 com um gateway ELIN**

![ea68f88a-0fc4-43d4-9660-79a7e8936df1](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ea68f88a-0fc4-43d4-9660-79a7e8936df1")

1.  Um SIP INVITE que contém o local, o número de retorno de chamada do chamador e a URL de notificação (opcional) e o número de retorno de chamada de conferência é roteado para o Lync Server.

2.  O Lync Server corresponde ao número de emergência e encaminha a chamada (com base no valor de **uso do PSTN** definido na política de local aplicável) para um servidor de mediação e, a partir daí, para um gateway do Elin.

3.  O gateway ELIN encaminha a chamada para o PSTN através de um tronco CAMA ou ISDN.

4.  O PSTN identifica a chamada como uma chamada de emergência e a encaminha para um roteador E9-1-1 seletivo na rede. O roteador E9-1-1 seletivo pesquisa o número do chamador no banco de dados ALI para obter o local geográfico. O roteador E9-1-1 seletivo envia a chamada para o PSAP mais apropriado com base nas informações de local que foram recuperadas do banco de dados ALI.

5.  Se você configurou a política de local para notificações, um ou mais gerentes de segurança da sua organização receberão uma mensagem instantânea especial de notificação de emergência do Lync. Essa mensagem sempre aparecerá na(s) tela(s) dos funcionários de segurança e contém o nome, o número de telefone, a hora e o local do chamador, permitindo que o pessoal de segurança atenda rapidamente o chamador de emergência usando uma mensagem instantânea ou voz.

6.  Se a chamada for interrompida prematuramente, o PSAP usa o ELIN para entrar diretamente em contato com o chamador. O gateway ELIN troca o ELIN pela DID do chamador.

</div>

<span> </span>

</div>

</div>

</div>

