---
title: Definir a experiência do usuário para aquisição manual de um local
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the user experience for manually acquiring a location
ms:assetid: d37f67d3-e248-483b-b64c-3986559ef357
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398912(v=OCS.15)
ms:contentKeyID: 48185435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fa9c7242351417c4ea82ed7ce6183963bc9730e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504468"
---
# <a name="defining-the-user-experience-for-manually-acquiring-a-location-in-lync-server-2013"></a><span data-ttu-id="d70b8-102">Definir a experiência do usuário para adquirir manualmente um local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d70b8-102">Defining the user experience for manually acquiring a location in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d70b8-103">_**Última modificação do tópico:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="d70b8-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="d70b8-p101">Se um cliente estiver localizado fora da rede ou em uma subrede indefinida, o usuário poderá inserir manualmente um local. Mas durante uma chamada de emergência, a chamada será roteada primeiro para o ECRC (Centro de resposta de chamada de emergência) de E9-1-1 nacional/regional antes de ser roteada para um PSAP (Ponto de atendimento público seguro). O ECRC consultará verbalmente o chamador por um local e encaminhará a chamada para o PSAP adequado, com base nas informações fornecidas.</span><span class="sxs-lookup"><span data-stu-id="d70b8-p101">If a client is located outside the network, or in an undefined subnet, the user can manually enter a location. But during an emergency call, the call will first be routed to a national/regional E9-1-1 Emergency Call Response Center (ECRC) dispatcher before being routed to a Public Safety Answering Point (PSAP). The ECRC will verbally query the caller for a location and then forward the call to the appropriate PSAP, based on the information provided.</span></span>

  - <span data-ttu-id="d70b8-107">**Os usuários devem ser solicitados a inserir um local quando um não é fornecido automaticamente pelo serviço de informações de local?**</span><span class="sxs-lookup"><span data-stu-id="d70b8-107">**Should users be prompted to enter a location when one is not automatically provided by the Location Information service?**</span></span>  
    <span data-ttu-id="d70b8-108">Por exemplo, se um cliente estiver localizado em uma sub-rede indefinida, em casa, em um hotel ou em qualquer outro lugar fora da rede, o usuário deverá inserir um local?</span><span class="sxs-lookup"><span data-stu-id="d70b8-108">For example, if a client is located in an undefined subnet, at home, in a hotel, or anywhere else outside the network, should the user be required to enter a location?</span></span>
    
    <span data-ttu-id="d70b8-p102">É possível definir a configuração **Local obrigatório** na política de local para definir o comportamento do cliente. Configurar este valor para Não significa que o usuário não será solicitado por um local. Configurar este valor para Sim significa que o usuário será solicitado por um local, mas pode ignorar a solicitação. A configuração deste valor para Isenção de responsabilidade significa que o usuário será solicitado por um local e exibirá uma isenção de responsabilidade se tentar ignorar a solicitação. De qualquer forma, o usuário pode contribuir com o uso do cliente, como sempre.</span><span class="sxs-lookup"><span data-stu-id="d70b8-p102">You can configure the **Location Required** setting in the location policy to define the client behavior. Setting this value to No means that the user will not be prompted for a location. Setting this value to Yes means that the user will be prompted for a location, but can dismiss the prompt. Setting this value to Disclaimer means that the user will be prompted for a location, and will be shown a disclaimer if they try to dismiss the prompt. In all cases, the user can continue to use the client as usual.</span></span>

<span data-ttu-id="d70b8-p103">Quando um usuário insere manualmente um local, o local é mapeado para o endereço MAC do gateway padrão da rede do cliente, e é armazenado em uma tabela por usuário localizada no cliente. Quando o usuário retorna a qualquer local armazenado anteriormente, o cliente Lync se define automaticamente para esse local.</span><span class="sxs-lookup"><span data-stu-id="d70b8-p103">When a user manually enters a location, the location is mapped to the MAC address of the default gateway of the client’s network, and is stored in a per-user table located on the client. When the user returns to any previously stored location, the Lync client automatically sets itself to that location.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="d70b8-116">É possível modificar somente o local atual de seu cliente, mas você também pode excluir qualquer local armazenado na tabela dos usuários locais.</span><span class="sxs-lookup"><span data-stu-id="d70b8-116">You can modify only the current location of your client, but you can also delete any location stored in the local user’s table.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

