---
title: 'Lync Server 2013: definindo o escopo da implantação de E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the scope of the E9-1-1 deployment
ms:assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425775(v=OCS.15)
ms:contentKeyID: 48183707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be9dee7f4e79492e62e04441b6fa56d4e04ff45a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043773"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-scope-of-the-e9-1-1-deployment-in-lync-server-2013"></a>Definindo o escopo da implantação do E9-1-1 no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-06-06_

Antes de configurar o Microsoft Lync Server 2013 para E9-1-1, você precisa planejar sua implantação do E9-1-1. Algumas das questões a serem consideradas são:

  - **Qual é a política de sua organização e as obrigações locais com relação ao E9-1-1?**  
    Os requisitos legais de E9-1-1 para PBXs (chamados de Multi-line Telephone Systems, ou MLTS, no linguajar de E9-1-1) diferem de acordo com o estado. Você deve consultar sua equipe jurídica para entender as obrigações que podem se aplicar à sua implantação do Lync Server em suas geografias relevantes.

<!-- end list -->

  - **Quais áreas dentro de sua empresa precisam estar habilitadas para E9-1-1?**  
    É possível habilitar o E9-1-1 para toda a empresa ou para locais selecionados. Por exemplo, talvez você tenha requisitos variados de E9-1-1 para escritórios em estados diferentes ou queira excluir sites fora dos EUA.

<!-- end list -->

  - **Como você implantará o E9-1-1 em sites de filiais?**  
    A resiliência de voz é um conceito importante para compreender quando implantar o E9-1-1 no site local. Se houver troncos SIP e-9-1-1 intercentralizados e ocorrer uma interrupção de WAN, os clientes que estiverem entrando podem não conseguir obter um local do serviço de informações de local ou para se conectarem ao provedor de serviços de emergência. O Lync Server oferece várias estratégias para lidar com a resiliência de voz em filiais, incluindo: redes de dados resistentes, implantação de um tronco SIP em cada filial ou envio de chamadas de emergência para o gateway local durante interrupções. Para obter detalhes, consulte [Planning for Branch-site Voice resiliência no Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).

<!-- end list -->

  - **Você habilitará o E9-1-1 para usuários trabalhando fora da rede?**  
    A aquisição automática de local fica disponível somente para clientes localizados dentro da rede da organização, portanto, sua organização precisa decidir se suportará chamadas de E9-1-1 feitas de clientes Lync no local. Por exemplo, você habilitará usuários para fazer chamadas de emergência se eles estiverem trabalhando de cada ou no local de um cliente? Se um cliente estiver localizado fora da rede empresarial, ele poderá ser configurado para solicitar ao usuário um local. No entanto, como esses locais fornecidos pelo usuário não podem ser pré-validados com base no MSAG (Catálogo de Endereços Principal), o despachante do provedor de serviços de emergência necessitarão confirmar a validade do local verbalmente com o chamador antes de rotear a chamada para o PSAP (ponto de atendimento público seguro).
    
    <div>
    

    > [!NOTE]  
    > Os clientes do Lync de usuários que se conectam à rede da sua organização usando a VPN podem pegar informações de endereço IP interno, mas como esses endereços não podem ser usados para identificar o local real do usuário, é essencial que sub-redes VPN sejam excluídas do Serviço de informações de local.

    
    </div>

<!-- end list -->

  - **Você deseja fornecer roteamento de chamada de emergência para sites fora dos EUA?**  
    Talvez você queira fornecer roteamento de emergência para áreas de sua empresa que não são atendidas por um provedor de serviços de emergência (por exemplo, locais internacionais). Para fazer isso, crie um novo site e atribua políticas de voz aos sites que se referem a um uso do PSTN que roteia a chamada pelo gateway PSTN local.

</div>

<span> </span>

</div>

</div>

</div>

