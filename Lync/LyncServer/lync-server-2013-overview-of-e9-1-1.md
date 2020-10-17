---
title: 'Lync Server 2013: visão geral de E9-1-1'
description: 'Lync Server 2013: visão geral de E9-1-1.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of E9-1-1
ms:assetid: c01e6774-bc9f-4c5b-a60b-478b7317b2b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412936(v=OCS.15)
ms:contentKeyID: 48185290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fa13d8bfd1c273e8cbbb1d70f1fb3d733ac6167
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571897"
---
# <a name="overview-of-e9-1-1-in-lync-server-2013"></a>Visão geral do E9-1-1 no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-29_

O Microsoft Lync Server 2013 oferece suporte à chamada avançada 9-1-1 (E9-1-1) de clientes Lync e dispositivos do Lync Phone Edition. Ao configurar o Lync Server para E9-1-1, as chamadas de emergência feitas do Lync 2013 ou do Lync Phone Edition incluem informações de local de resposta de emergência (ERL) do banco de dados de serviço de informações de local. ERLs são compostos por endereços cívicos (rua) e outras informações que ajudam a identificar um local mais preciso em escritórios em edifícios e em outras instalações com vários locatários. Quando um usuário faz uma chamada de emergência, o Lync Server roteia o áudio da chamada, juntamente com as informações de local e de retorno de chamada, por meio de um servidor de mediação para um provedor de serviços E9-1-1. O provedor de serviço E9-1-1 usa o endereço cívico do chamador para encaminhar a chamada ao PSAP (Ponto de atendimento público seguro) que atende ao local do chamador e envia também uma ESQK (Chave de consulta de serviço de emergência) que o PSAP usa para procurar o ERL do chamador.

O Lync Server suporta dois métodos para rotear chamadas de emergência para um provedor de serviços E9-1-1:

  - Uma conexão de tronco SIP com um provedor de serviço qualificado E9-1-1

  - Um gateway ELIN (para um provedor de serviço E9-1-1 baseado em PSTN (Rede Telefônica Pública Comutada)

Quando você usa um provedor de serviços E9-1-1 do tronco SIP, você adiciona ERLs ao banco de dados do serviço de informações de local e, em seguida, valida os locais em relação a uma guia de endereço mestre (MSAG) que é mantida pelo provedor de serviços E9-1-1. Se um provedor de serviço E9-1-1 recebe uma chamada sem informações sobre o local ou com um local que não foi validado com o MSAG, o provedor de serviço E9-1-1 encaminha a chamada a um ECRC (Centro de resposta à chamada de emergência) nacional/regional, equipado com pessoas especialmente treinadas que obtém verbalmente o local do chamador, se for possível, e encaminha manualmente a chamada ao PSAP apropriado. (Alguns provedores de serviço E9-1-1 de tronco SIP também fornecem aos clientes um DID (discagem direta interna) de PSTN ao ECRC, o que proporciona um meio alternativo de encaminhar as chamadas de 9-1-1, se um tronco SIP falhar por qualquer motivo).

Diferentemente dos telefones de multiplexação de divisão de tempo (TDM) e de PBX (central privada de comutação telefônica) com base em IP, que têm locais fixos, um ponto de extremidade do Lync pode ser muito móvel. Quando você implanta o recurso E9-1-1, o Lync Server ajuda a garantir que não importa onde um chamador esteja localizado, a chamada de emergência pode ser roteada para o PSAP que serve o local do chamador. Por exemplo, se a sede de um usuário fica localizada em Redmond, Washington, mas o usuário faz uma chamada de emergência de um computador em uma filial em Wichita, Kansas, o tronco SIP ou o provedor de serviço E9-1-1 com base em PSTN encaminhará a chamada ao PSAP em Wichita, não ao PSAP em Redmond.

Ao usar um gateway ELIN, você também adiciona ERLs ao banco de dados do serviço de informações de local, mas também inclui um número ELIN para cada local. O número ELIN se torna o número de discagem de emergência durante a chamada de emergência. Em seguida, é necessário certificar-se de que a operadora PSTN carrega os ELINs no banco de dados de ALI (Identificação automática de local).

<div>


> [!NOTE]  
> Os dispositivos analógicos conectados ao Lync não podem receber informações de local do serviço de informações de local ou local de transmissão para o provedor de serviços E9-1-1. Se você usar a opção do provedor de serviço E9-1-1 do tronco SIP e precisar oferecer suporte ao E9-1-1 a partir de telefones analógicos, terá duas opções: 
> <UL>
> <LI>
> <P>Opção PS- <STRONG>ali tradicional</STRONG> &nbsp; &nbsp; &nbsp; Se você tiver gateways PSTN locais em cada site em que os telefones analógicos são implantados e cada telefone analógico tiver um, você poderá provisionar o local do dispositivo analógico diretamente com um provedor de serviços de comutador de local privado/identificação automática (PS-ALI). Nesse caso, você configura políticas de voz do Lync criadas especialmente e as atribui aos objetos de contato com o dispositivo analógico, de modo que as chamadas E9-1-1 desses telefones sejam encaminhadas diretamente pelo gateway local para o provedor de PSTN que atende ao site (em vez de encaminhá-las ao tronco SIP de um provedor de serviço E9-1-1). Quando uma chamada de emergência é feita, um banco de dados em um provedor PS-ALI associado ao tronco do PSTN mapeia o DID de cada telefone analógico para um local físico e fornece esse local ao PSAP. Esses registros precisam ser atualizados com o provedor de serviço PS-ALI sempre que os telefones são movidos para ERLs diferentes.</P>
> <LI>
> <P>Opção de provedor <STRONG>de serviços E9-1-1</STRONG> &nbsp; &nbsp; &nbsp; Você pode registrar o DIDs de telefone analógico e o ERLs correspondente com o provedor de serviço E9-1-1, se houver suporte para o provedor de serviços E9-1-1. Se o provedor receber uma chamada do Lync Server que não inclui os dados do PIDF-LO, o provedor poderá ver se há uma correspondência de banco de dados no número do participante da chamada. Usando o ERL recuperado de seu banco de dados, o provedor pode rotear automaticamente a chamada de emergência para o PSAP correto, e o PSAP receberá o DID do dispositivo analógico e um registro ESQK que permite ao despachante procurar o local do chamador.</P></LI></UL>Se você usar a opção de gateway ELIN e precisar oferecer suporte a E9-1-1 de telefones analógicos, é possível prover o local do dispositivo analógico diretamente com o provedor de serviços PS-ALI, como descrito na primeira opção acima.</div>

A partir de uma perspectiva do Lync Server, o processo E9-1-1 pode ser separado em dois estágios:

  - Estágio 1: adquirindo um local

  - Estágio 2: roteando a chamada de emergência para um provedor de serviço E9-1-1

Esta seção descreve como esses estágios funcionam.

Se você planeja configurar sua infraestrutura para detectar automaticamente o local do cliente, primeiro você precisa decidir quais elementos de rede serão usados para mapear os chamadores aos locais. Para obter detalhes sobre as opções possíveis, consulte [definindo os elementos de rede usados para determinar o local no Lync Server 2013](lync-server-2013-defining-the-network-elements-used-to-determine-location.md).

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Adquirindo um local no Lync Server 2013](lync-server-2013-acquiring-a-location.md)

  - [Roteamento de chamadas E9-1-1 usando um tronco SIP no Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md)

  - [Roteamento de chamadas E9-1-1 usando um gateway ELIN no Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

