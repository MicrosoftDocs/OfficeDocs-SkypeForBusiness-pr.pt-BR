---
title: 'Lync Server 2013: Visão geral de E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of E9-1-1
ms:assetid: c01e6774-bc9f-4c5b-a60b-478b7317b2b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412936(v=OCS.15)
ms:contentKeyID: 48185290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 144f189c119653ddb02316193e78b9156fad2278
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825482"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-e9-1-1-in-lync-server-2013"></a>Visão geral de E9-1-1 no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-29_

O Microsoft Lync Server 2013 dá suporte à chamada Enhanced 9-1-1 (E9-1-1) dos clientes do Lync e dos dispositivos Lync Phone Edition. Quando você configura o Lync Server para E9-1-1, as chamadas de emergência feitas pelo Lync 2013 ou pelo Lync Phone Edition incluem informações de local de resposta de emergência (ERL) do banco de dados do serviço de informações de localização. ERLs consistem em endereços cívicos (rua) e outras informações que ajudam a identificar a localização mais precisa em prédios de escritórios e outras instalações com vários locatários. Quando um usuário faz uma chamada de emergência, o Lync Server roteia o áudio da chamada, juntamente com o local e as informações de retorno de chamada, por meio de um servidor de mediação para um provedor de serviços E9-1-1. O provedor de serviços E9-1-1 usa o endereço cívico do chamador para encaminhar a chamada para PSAP (Ponto de Atendimento Público Seguro), que atende à localização do chamador e envia também uma ESQK (Chave de Consulta de Serviço de Emergência) que PSAP usa para procurar a ERL do chamador.

O Lync Server tem suporte para dois métodos de roteamento de chamadas de emergência para um provedor de serviços E9-1-1:

  - Uma conexão de tronco SIP com um provedor de serviços E9-1-1 qualificado

  - Um gateway ELIN (para um provedor de serviços E9-1-1 baseado em PSTN (Rede Telefônica Pública Comutada)

Quando você usa um provedor de serviço E9 de tronco SIP-1-1, adiciona ERLs ao banco de dados do serviço de informações de localização e, em seguida, valida os locais em relação a uma guia de endereço mestre (MSAG) mantida pelo provedor de serviços E9-1-1. Se um provedor de serviços E9-1-1 receber uma chamada sem informações sobre o local ou com um local não validado com o MSAG, o provedor de serviços E9-1-1 encaminhará a chamada a um ECRC (Centro de Resposta a Chamadas de Emergência) nacional/regional, que conta com pessoas especialmente treinadas para obter verbalmente o local do chamador, se possível, e encaminhar manualmente a chamada ao PSAP apropriado. (Alguns provedores de serviços E9-1-1 de tronco SIP também fornecem aos clientes um número DID (discagem direta interna) de PSTN ao ECRC, que é um meio alternativo de encaminhar as chamadas 9-1-1 se um tronco SIP falhar por algum motivo).

Ao contrário dos telefones de bifurcação de divisão de tempo (TDM) e de PBX (intercâmbio privado) baseados em IP, que têm locais fixos, um ponto de extremidade do Lync pode ser muito móvel. Quando você implanta o recurso E9-1-1, o Lync Server ajuda a garantir que não importa onde um chamador esteja localizado, a chamada de emergência pode ser roteada para o PSAP que serve o local do autor do usuário. Por exemplo, se a sede de um usuário estiver localizada em Redmond, em Washington, mas o usuário fizer uma chamada de emergência de um computador em uma filial em Wichita, no Kansas, o tronco SIP ou o provedor de serviços E9-1-1 com base em PSTN encaminhará a chamada para o PSAP de Wichita, e não para o PSAP de Redmond.

Ao usar um gateway ELIN, você também adiciona ERLs ao banco de dados do serviço de informações de localização, mas também inclui um número ELIN para cada local. O número ELIN se torna o número de discagem de emergência durante a chamada de emergência. Em seguida, é necessário verificar se a operadora PSTN carrega os ELINs no banco de dados de ALI (Identificação Automática de Local).

<div>


> [!NOTE]  
> O Lync-dispositivos analógicos conectados não pode receber informações de localização do serviço de informações de localização ou local de transmissão para o provedor de serviços E9-1-1. Se usar a opção do provedor de serviços E9-1-1 do tronco SIP e precisar dar suporte a E9-1-1 por meio de telefones analógicos, você terá duas opções: 
> <UL>
> <LI>
> <P><STRONG></STRONG>&nbsp;Opção&nbsp;PS&nbsp;-ali tradicional se você tiver gateways PSTN locais em cada site em que os telefones analógicos são implantados e cada telefone analógico tiver um, você pode provisionar a localização do dispositivo analógico diretamente com um comutador particular/automático Provedor de serviços de identificação de localização (PS-ALI). Nesse caso, você configura políticas de voz do Lync especialmente criadas e as atribui aos objetos de contato do dispositivo analógico para que as chamadas E9-1-1 desses telefones sejam roteadas diretamente por meio do gateway local para o provedor de PSTN que presta serviços ao site (em vez de direcionar o chamada para um tronco SIP do provedor de serviços E9-1-1). Quando uma chamada de emergência é efetuada, um banco de dados em um provedor de PS-ALI associado ao tronco PSTN mapeia o DID de cada telefone analógico para um local físico e fornece esse local ao PSAP. Esses registros precisam ser atualizados com o provedor de serviços PS-ALI sempre que os telefones são movidos para ERLs diferentes.</P>
> <LI>
> <P><STRONG></STRONG>&nbsp;Opção&nbsp;de&nbsp;provedor de serviços E9-1-1 você pode registrar o DIDs de telefone analógico e seus ERLs correspondentes com o provedor de serviços E9-1-1, caso isso seja compatível com o provedor de serviços E9-1-1. Se o provedor receber uma chamada do Lync Server que não inclui dados do PIDF-LO, o provedor poderá ver se há um banco de dados correspondente no número do participante da chamada. Usando a ERL recuperada de seu banco de dados, o provedor pode encaminhar automaticamente a chamada de emergência para o PSAP correto, e o PSAP receberá o DID do dispositivo analógico e um registro ESQK que permite ao dispatcher procurar o local do chamador.</P></LI></UL>Se você usar a opção de gateway ELIN e precisar oferecer suporte a E9-1-1 de telefones analógicos, é possível provisionar o local do dispositivo analógico diretamente com o provedor de serviços PS-ALI, como descrito na primeira opção acima.</div>

De uma perspectiva do Lync Server, o processo E9-1-1 pode ser separado em dois estágios:

  - Estágio 1: aquisição de local

  - Estágio 2: encaminhamento de chamada de emergência para um provedor de serviços E9-1-1

Esta seção descreve como esses estágios funcionam.

Se planeja configurar sua infraestrutura para detectar automaticamente o local do cliente, primeiro você precisa decidir quais elementos de rede serão usados para mapear os chamadores para os locais. Para obter detalhes sobre as possíveis opções, consulte [definindo os elementos de rede usados para determinar o local no Lync Server 2013](lync-server-2013-defining-the-network-elements-used-to-determine-location.md).

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Adquirindo um local no Lync Server 2013](lync-server-2013-acquiring-a-location.md)

  - [Roteamento de chamadas E9-1-1 usando tronco SIP no Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md)

  - [Roteamento de chamadas E9-1-1 usando um gateway ELIN no Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

