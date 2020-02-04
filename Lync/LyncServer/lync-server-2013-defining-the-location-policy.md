---
title: 'Lync Server 2013: definindo a política de localização'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the location policy
ms:assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398962(v=OCS.15)
ms:contentKeyID: 48185553
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: feb7550412fa6cdcda3a8fc4dd9b7913912c34e1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728351"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-location-policy-for-lync-server-2013"></a><span data-ttu-id="90009-102">Definindo a política de localização do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90009-102">Defining the location policy for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90009-103">_**Tópico da última modificação:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="90009-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="90009-104">Cada política de local contém as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="90009-104">Each location policy contains the following information:</span></span>

  - <span data-ttu-id="90009-105">**Serviços de emergência habilitados**</span><span class="sxs-lookup"><span data-stu-id="90009-105">**Emergency Services Enabled**</span></span>  
    <span data-ttu-id="90009-106">Quando esse valor é **Sim**, o cliente está habilitado para E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="90009-106">When this value is **Yes**, the client is enabled for E9-1-1.</span></span> <span data-ttu-id="90009-107">Quando um cliente é registrado, ele tenta adquirir um local do serviço de informações de localização e inclui as informações de localização como parte de uma chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="90009-107">When a client registers, it attempts to acquire a location from the Location Information service and will include the location information as part of an emergency call.</span></span>

<!-- end list -->

  - <span data-ttu-id="90009-108">**Local obrigatório**</span><span class="sxs-lookup"><span data-stu-id="90009-108">**Location Required**</span></span>  
    <span data-ttu-id="90009-109">Essa configuração é usada somente quando os **serviços de emergência habilitados** são definidos como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="90009-109">This setting is used only when **Emergence Services Enabled** is set to **Yes**.</span></span>
    
    <span data-ttu-id="90009-110">Você pode configurar a configuração de **localização necessária** para definir o comportamento do cliente.</span><span class="sxs-lookup"><span data-stu-id="90009-110">You can configure the **Location Required** setting to define the client behavior.</span></span> <span data-ttu-id="90009-111">Definir o valor como **Não** significa que o usuário não receberá uma solicitação de local.</span><span class="sxs-lookup"><span data-stu-id="90009-111">Setting the value to **No** means that the user will not be prompted for a location.</span></span> <span data-ttu-id="90009-112">Definir o valor como **Sim** significa que o usuário receberá uma solicitação de local, mas poderá ignorá-la.</span><span class="sxs-lookup"><span data-stu-id="90009-112">Setting the value to **Yes** means that the user will be prompted for a location, but can dismiss the prompt.</span></span> <span data-ttu-id="90009-113">Definir o valor como **Aviso de isenção de responsabilidade** significa que o usuário receberá uma solicitação de local e um aviso de isenção de responsabilidade caso tente ignorar a solicitação.</span><span class="sxs-lookup"><span data-stu-id="90009-113">Setting the value to **Disclaimer** means that the user will be prompted for a location and also will be shown a disclaimer if they try to dismiss the prompt.</span></span> <span data-ttu-id="90009-114">De qualquer forma, o usuário pode continuar utilizando o cliente.</span><span class="sxs-lookup"><span data-stu-id="90009-114">In all cases, the user can continue to use the client.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="90009-p103">O texto do aviso de isenção de responsabilidade não aparecerá se um usuário inserir manualmente um local antes de ser habilitado para E9-1-1. As atualizações para o texto do aviso de isenção de responsabilidade não será visualizado pelos usuários que já visualizaram o aviso de isenção de responsabilidade. </span><span class="sxs-lookup"><span data-stu-id="90009-p103">The disclaimer text will not appear if a user manually entered a location before being enabled for E9-1-1. Updates to the disclaimer text will not be viewed by users that have already viewed the disclaimer.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="90009-117">**Aviso de Isenção de Responsabilidade do Serviço de Emergência Avançado**</span><span class="sxs-lookup"><span data-stu-id="90009-117">**Enhanced Emergency Service Disclaimer**</span></span>  
    <span data-ttu-id="90009-118">Esta configuração especifica o aviso de isenção de responsabilidade que o usuário verá caso ignore a solicitação de local.</span><span class="sxs-lookup"><span data-stu-id="90009-118">This setting specifies the disclaimer that users see if they dismiss the prompt for a location.</span></span> <span data-ttu-id="90009-119">No Lync Server 2013, você pode usar a política de localização para definir avisos de isenção de responsabilidade diferentes para locais diferentes ou conjuntos de usuários diferentes.</span><span class="sxs-lookup"><span data-stu-id="90009-119">In Lync Server 2013, you can use location policy to set different disclaimers for different locales or different sets of users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="90009-120">Essa configuração de política de localização é diferente do Lync Server 2010, no qual você usou o cmdlet <STRONG>set-CsEnhancedEmergencyServiceDisclaimer</STRONG> para definir um aviso global para a organização inteira.</span><span class="sxs-lookup"><span data-stu-id="90009-120">This location policy setting differs from Lync Server 2010, where you used the <STRONG>Set-CsEnhancedEmergencyServiceDisclaimer</STRONG> cmdlet to set a global disclaimer for the entire organization.</span></span> <span data-ttu-id="90009-121">Se já existir uma isenção global, você precisará especificar essa isenção de responsabilidade na política de localização.</span><span class="sxs-lookup"><span data-stu-id="90009-121">If a global disclaimer already exists, you need to specify that disclaimer in location policy.</span></span> <span data-ttu-id="90009-122">Ou seja, o Lync Server 2013 usa apenas avisos de isenção especificados na política de localização.</span><span class="sxs-lookup"><span data-stu-id="90009-122">That is, Lync Server 2013 uses only disclaimers specified in location policy.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="90009-123">**Cadeia de discagem de emergência**</span><span class="sxs-lookup"><span data-stu-id="90009-123">**Emergency Dial String**</span></span>  
    <span data-ttu-id="90009-124">Esta cadeia de caracteres de discagem (menos a "+" à esquerda, mas incluindo qualquer normalização feita pelo plano de discagem do usuário do Lync) significa que uma chamada é uma chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="90009-124">This dial string (less the leading “+”, but including any normalization done by the Lync user’s Dial Plan) signifies that a call is an emergency call.</span></span> <span data-ttu-id="90009-125">A **Sequência de discagem de emergência** faz com que o cliente inclua na chamada informações sobre o local e sobre retorno de chamada.</span><span class="sxs-lookup"><span data-stu-id="90009-125">The **Emergency Dial String** causes the client to include location and callback information with the call.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="90009-126">Se a sua organização não usar um prefixo de acesso de linha externa, você não precisará criar uma regra de normalização de plano de discagem correspondente que adiciona "+" à cadeia de caracteres 911 antes de enviar a chamada para o roteamento de saída em um servidor de pool do Lync; o "+" será automaticamente retomado pelo cliente do Lync como resultado da política de localização.</span><span class="sxs-lookup"><span data-stu-id="90009-126">If your organization does not use an external line access prefix, you do not need to create a corresponding Dial Plan normalization rule that adds a “+” to the 911 string prior to sending the call to Outbound Routing on a Lync pool server; the “+” will be automatically prepended by the Lync client as a result of the location policy.</span></span> <span data-ttu-id="90009-127">No entanto, se seu site usar um prefixo de acesso externo, será necessário adicionar uma regra de normalização à política de Plano de Discagem aplicável que remove o prefixo de acesso externo e adiciona “+”.</span><span class="sxs-lookup"><span data-stu-id="90009-127">However, if your site uses an external access prefix, you need to add a normalization rule to the applicable Dial Plan policy that strips the external access prefix and adds the “+”.</span></span> <span data-ttu-id="90009-128">Por exemplo, se a sua localização usa um prefixo de acesso externo de 9 e um usuário discar 9&nbsp;911 para fazer uma chamada de emergência, o cliente usará sua política de plano de discagem para normalizar isso para + 911 antes que o número discado seja avaliado por rotas no perfil de localização do chamador.</span><span class="sxs-lookup"><span data-stu-id="90009-128">For example, if your location uses an external access prefix of 9 and a user dials 9&nbsp;911 to place an emergency call, the client will use its Dial Plan policy to normalize this to +911 before the dialed number is evaluated by the routes in the caller’s location profile.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="90009-129">**Máscaras de cadeias de discagem de emergência**</span><span class="sxs-lookup"><span data-stu-id="90009-129">**Emergency Dial String Masks**</span></span>  
    <span data-ttu-id="90009-130">Uma lista separada por ponto-e-vírgula de cadeias de discagem que é traduzida para a **cadeia de discagem de emergência**especificada</span><span class="sxs-lookup"><span data-stu-id="90009-130">A semicolon-separated list of dial strings that is translated into the specified **Emergency Dial String**.</span></span> <span data-ttu-id="90009-131">Por exemplo, talvez você queira adicionar 112, que é o número do serviço de emergência para a maioria da Europa.</span><span class="sxs-lookup"><span data-stu-id="90009-131">For example, you may want to add 112, which is the emergency service number for most of Europe.</span></span> <span data-ttu-id="90009-132">Um usuário visitante do Lync da Europa talvez não saiba que 911 é o número de emergência dos EUA, mas pode discar o 112 e obter o mesmo resultado.</span><span class="sxs-lookup"><span data-stu-id="90009-132">A visiting Lync user from Europe may not know that 911 is the U.S. emergency number, but they can dial 112 and get the same result.</span></span> <span data-ttu-id="90009-133">Assim como na cadeia de caracteres de discagem de emergência, não inclua um "+" antes de cada número e, se você usar códigos de acesso de linha externos, certifique-se de que haja regras de normalização na política de plano de discagem do usuário para retirar o dígito de código de acesso.</span><span class="sxs-lookup"><span data-stu-id="90009-133">As with the Emergency Dial String, do not include a “+” before each number, and if you use external line access codes, be sure there are normalization rules in the user’s Dial Plan policy to strip off the access code digit.</span></span>

<!-- end list -->

  - <span data-ttu-id="90009-134">**Uso de PSTN**</span><span class="sxs-lookup"><span data-stu-id="90009-134">**PSTN Usage**</span></span>  
    <span data-ttu-id="90009-135">O nome do Uso de PSTN que contém os caminhos de roteamento que determinam para qual tronco SIP, gateway PSTN ou gateway ELIN as chamadas serão encaminhadas.</span><span class="sxs-lookup"><span data-stu-id="90009-135">The name of the PSTN Usage that contains the routing paths that determine which SIP trunk, PSTN gateway, or ELIN gateway emergency calls will go to.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="90009-p109">É possível atribuir apenas um Uso a uma política de local. Esse Uso de PSTN substitui os Usos de PSTN atribuídos à política de voz do usuário, mas se aplica somente às chamadas feitas para a Sequência de discagem de emergência ou uma das Máscaras de sequência de chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="90009-p109">Only one usage can be assigned to a location policy. This PSTN Usage overrides the PSTN Usages assigned to the user’s voice policy, but applies only to calls placed to the Emergency Dial String or to one of the Emergency Dial String Masks.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="90009-138">**URI de notificação**</span><span class="sxs-lookup"><span data-stu-id="90009-138">**Notification URI**</span></span>  
    <span data-ttu-id="90009-p110">Especifica um ou mais URIs SIP do pessoal de segurança que receberá uma notificação de IM (Sistema de Mensagens Instantâneas) quando uma chamada de emergência for realizada. Há suporte para grupos de distribuição.</span><span class="sxs-lookup"><span data-stu-id="90009-p110">Specifies one or more SIP URIs of the security personnel who receive an instant messaging (IM) notification when an emergency call is placed. Distribution groups are supported.</span></span>

<!-- end list -->

  - <span data-ttu-id="90009-141">**URI de Conferência**</span><span class="sxs-lookup"><span data-stu-id="90009-141">**Conference URI**</span></span>  
    <span data-ttu-id="90009-142">Especifica um número DID (discagem direta interna) (normalmente um número do suporte de segurança) que deve ser verificado quando uma chamada de emergência é feita.  </span><span class="sxs-lookup"><span data-stu-id="90009-142">Specifies a direct inward dialing (DID) number (typically, a security desk number) that should be conferenced in when an emergency call is placed.</span></span>

<!-- end list -->

  - <span data-ttu-id="90009-143">**Modo de Conferência**</span><span class="sxs-lookup"><span data-stu-id="90009-143">**Conference Mode**</span></span>  
    <span data-ttu-id="90009-144">Especifica se o URI de conferência será inserido na chamada de emergência usando comunicação de uma ou duas vias. </span><span class="sxs-lookup"><span data-stu-id="90009-144">Specifies if the conference URI will be conferenced into the emergency call by using one-way or two-way communication.</span></span>

<!-- end list -->

  - <span data-ttu-id="90009-145">**Intervalo de Atualização de Local**</span><span class="sxs-lookup"><span data-stu-id="90009-145">**Location Refresh Interval**</span></span>  
    <span data-ttu-id="90009-146">Especifica a quantidade de tempo (em horas) entre as solicitações do cliente para uma atualização de localização do serviço de informações de localização.</span><span class="sxs-lookup"><span data-stu-id="90009-146">Specifies the amount of time (in hours) between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="90009-147">O valor pode ser definido para qualquer valor entre 1 e 12.</span><span class="sxs-lookup"><span data-stu-id="90009-147">The value can be set to any value between 1 and 12.</span></span> <span data-ttu-id="90009-148">O valor padrão é 4.</span><span class="sxs-lookup"><span data-stu-id="90009-148">The default value is 4.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

