---
title: 'Lync Server 2013: Roteamento de chamadas E9-1-1 usando um gateway ELIN'
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
ms.openlocfilehash: 97c921a0b31438103ba74dcc64925e5b2069a8e8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732841"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-an-elin-gateway-in-lync-server-2013"></a>Roteamento de chamadas E9-1-1 usando um gateway ELIN no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-05_

Alguns parceiros do Programa de Interoperabilidade Aberta de Comunicações Unificadas fornecem gateways compatíveis com ELIN (número de identificação de local de emergência) qualificados, que podem servir como uma alternativa a uma conexão de tronco SIP com um provedor de serviços E9-1-1 qualificado. Os gateways ELIN dão suporte à conectividade CAMA (Contabilidade de Mensagem Automática Centralizada) ou ISDN com serviços E9-1-1 baseados em PSTN (Rede Telefônica Pública Comutada). Para obter detalhes sobre os parceiros que fornecem gateways do ELIN e links para a [http://go.microsoft.com/fwlink/p/?LinkId=248425](http://go.microsoft.com/fwlink/p/?linkid=248425)documentação dele, consulte.

Assim como as conexões de tronco SIP com provedores de serviços E9-1-1, os gateways ELIN também fornecem um meio de encaminhar uma chamada de emergência para o PSAP (Ponto de Atendimento Público Seguro) mais apropriado do chamador, mas esses gateways usam um ELIN como identificador do local. Você define ELINs para cada local de resposta de emergência (ERL) em sua organização (para obter detalhes, consulte [Gerenciando locais para gateways Elin no Lync Server 2013](lync-server-2013-managing-locations-for-elin-gateways.md)).

Ao usar um gateway ELIN para chamadas de emergência, use a mesma infraestrutura do Lync Server E9-1 que você usaria para uma conexão de tronco SIP. Ou seja, o banco de dados do serviço de informações de localização fornece o local para o cliente do Lync Server, e a política de localização habilita o recurso e define o roteamento. No entanto, com um gateway ELIN, você precisa adicionar o ELINs ao banco de dados do serviço de informações de localização e ter sua operadora PSTN carregá-los para o banco de dados de identificação automática de local (ALI).

Quando um cliente do Lync obtém seu local do serviço de informações de localização, o local inclui o ELIN. Durante uma chamada de emergência, o ELIN é incluído no local enviado para o gateway ELIN. O gateway ELIN identifica a chamada como uma chamada de emergência e troca o número do chamador pelo ELIN. Em seguida, o gateway de ELIN encaminha a chamada para a PSTN com o ELIN como número chamador. O provedor de E9-1-1 da PSTN pesquisa o ELIN no banco de dados ALI, que é um banco de dados complementar ao banco de dados MSAG (Catálogo de Endereços Principal). A PSTN então envia a chamada para o PSAP mais apropriado com base na pesquisa do ALI, e o PSAP envia as equipes de emergência para o local do chamador com base na pesquisa do ALI. O número chamador é armazenado em cache no gateway ELIN por um tempo predefinido para retornos de chamada. Durante um retorno de chamada, o PSAP chega ao gateway ELIN, que troca o ELIN pelo número DID (discagem direta interna) do chamador.

Os gateways ELIN oferecem suporte a chamadas de emergência somente de dentro da rede da sua organização. Eles não oferecem suporte a chamadas de emergência realizadas fora da sua rede.

<div>


> [!NOTE]  
> Para obter detalhes sobre como usar uma conexão de tronco SIP para chamadas de emergência, consulte <A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">Roteamento E9-1-1 usando um tronco SIP no Lync Server 2013</A>.



</div>

O diagrama a seguir mostra como uma chamada de emergência é roteada do Lync Server para o PSAP quando você usa um gateway ELIN.

**Encaminhar chamadas de E9-1-1 com um gateway ELIN**

![ea68f88a-0fc4-43d4-9660-79a7e8936df1](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ea68f88a-0fc4-43d4-9660-79a7e8936df1")

1.  Um convite SIP que contém o local, o número de retorno de chamada do chamador e a URL de notificação (opcional) e o número de retorno de chamada de conferência é roteado para o Lync Server.

2.  O Lync Server corresponde ao número de emergência e roteia a chamada (com base no valor de **uso de PSTN** definido na política de localização aplicável) para um servidor de mediação e de lá para um gateway Elin.

3.  O gateway ELIN encaminha a chamada para o PSTN por meio de um tronco CAMA ou ISDN.

4.  O PSTN identifica a chamada como uma chamada de emergência e a encaminha para um roteador E9-1-1 seletivo na rede. O roteador E9-1-1 seletivo pesquisa o número do chamador no banco de dados ALI para obter o local geográfico. O roteador E9-1-1 seletivo envia a chamada para o PSAP mais apropriado com base nas informações de local que foram recuperadas do banco de dados ALI. 

5.  Se você configurou a política de localização para notificações, um ou mais gerentes de segurança da sua organização receberão uma mensagem de chat especial de notificação de emergência do Lync. Essa mensagem sempre aparecerá na(s) tela(s) dos funcionários de segurança e contém o nome, o número de telefone, a hora e o local do chamador, permitindo que a equipe de segurança atenda rapidamente ao chamador de emergência usando uma mensagem instantânea ou voz.

6.  Se a chamada for interrompida prematuramente, o PSAP usará o ELIN para contatar diretamente o chamador. O gateway ELIN trocará o ELIN pelo DID do chamador.

</div>

<span> </span>

</div>

</div>

</div>

