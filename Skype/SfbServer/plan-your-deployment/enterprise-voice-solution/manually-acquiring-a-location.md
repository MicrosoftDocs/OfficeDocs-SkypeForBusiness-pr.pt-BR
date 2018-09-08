---
title: Definir a experiência do usuário para adquirir manualmente um local no Skype para Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d37f67d3-e248-483b-b64c-3986559ef357
description: Planejamento de usuários em uma implantação do E9-1-1 usando provedores de tronco SIP, em Skype para Business Server Enterprise Voice móveis.
ms.openlocfilehash: 921724b2dc93b852cebe6a34acbd8d4d66a594f8
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23881808"
---
# <a name="define-the-user-experience-for-manually-acquiring-a-location-in-skype-for-business-server"></a><span data-ttu-id="1f0de-103">Definir a experiência do usuário para adquirir manualmente um local no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="1f0de-103">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>
 
<span data-ttu-id="1f0de-104">Planejamento de usuários em uma implantação do E9-1-1 usando provedores de tronco SIP, em Skype para Business Server Enterprise Voice móveis.</span><span class="sxs-lookup"><span data-stu-id="1f0de-104">Planning for roaming users in an E9-1-1 deployment using SIP trunking providers, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="1f0de-p101">Se um cliente estiver localizado fora da rede ou em uma subrede indefinida, o usuário poderá inserir manualmente um local. Mas durante uma chamada de emergência, a chamada será roteada primeiro para o ECRC (Centro de resposta de chamada de emergência) de E9-1-1 nacional/regional antes de ser roteada para um PSAP (Ponto de atendimento público seguro). O ECRC consultará verbalmente o chamador por um local e encaminhará a chamada para o PSAP adequado, com base nas informações fornecidas.</span><span class="sxs-lookup"><span data-stu-id="1f0de-p101">If a client is located outside the network, or in an undefined subnet, the user can manually enter a location. But during an emergency call, the call will first be routed to a national/regional E9-1-1 Emergency Call Response Center (ECRC) dispatcher before being routed to a Public Safety Answering Point (PSAP). The ECRC will verbally query the caller for a location and then forward the call to the appropriate PSAP, based on the information provided.</span></span> 
  
<span data-ttu-id="1f0de-108">**Os usuários devem ser solicitados para inserir um local quando um não for obtido automaticamente pelo serviço de informações de local?**</span><span class="sxs-lookup"><span data-stu-id="1f0de-108">**Should users be prompted to enter a location when one is not automatically provided by the Location Information service?**</span></span>
  
<span data-ttu-id="1f0de-109">Por exemplo, se um cliente estiver localizado em uma sub-rede indefinida, em casa, em um hotel ou em qualquer outro lugar fora da rede, o usuário deverá inserir um local?</span><span class="sxs-lookup"><span data-stu-id="1f0de-109">For example, if a client is located in an undefined subnet, at home, in a hotel, or anywhere else outside the network, should the user be required to enter a location?</span></span>
    
<span data-ttu-id="1f0de-p102">É possível definir a configuração **Local obrigatório** na política de local para definir o comportamento do cliente. Configurar este valor para Não significa que o usuário não será solicitado por um local. Configurar este valor para Sim significa que o usuário será solicitado por um local, mas pode ignorar a solicitação. A configuração deste valor para Isenção de responsabilidade significa que o usuário será solicitado por um local e exibirá uma isenção de responsabilidade se tentar ignorar a solicitação. De qualquer forma, o usuário pode contribuir com o uso do cliente, como sempre.</span><span class="sxs-lookup"><span data-stu-id="1f0de-p102">You can configure the **Location Required** setting in the location policy to define the client behavior. Setting this value to No means that the user will not be prompted for a location. Setting this value to Yes means that the user will be prompted for a location, but can dismiss the prompt. Setting this value to Disclaimer means that the user will be prompted for a location, and will be shown a disclaimer if they try to dismiss the prompt. In all cases, the user can continue to use the client as usual.</span></span>
    
<span data-ttu-id="1f0de-115">Quando um usuário insere manualmente um local, o local é mapeado para o endereço MAC do gateway padrão da rede do cliente e é armazenado em uma tabela por usuário localizada no cliente.</span><span class="sxs-lookup"><span data-stu-id="1f0de-115">When a user manually enters a location, the location is mapped to the MAC address of the default gateway of the client's network, and is stored in a per-user table located on the client.</span></span> <span data-ttu-id="1f0de-116">Quando o usuário retorna para qualquer local armazenado anteriormente, o Skype para o cliente de negócios definirá automaticamente próprio para esse local.</span><span class="sxs-lookup"><span data-stu-id="1f0de-116">When the user returns to any previously stored location, the Skype for Business client automatically sets itself to that location.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1f0de-117">Você pode modificar somente o local atual de seu cliente, mas você também pode excluir qualquer local armazenado na tabela do usuário local.</span><span class="sxs-lookup"><span data-stu-id="1f0de-117">You can modify only the current location of your client, but you can also delete any location stored in the local user's table.</span></span> 
  

