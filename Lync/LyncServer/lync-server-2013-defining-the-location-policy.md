---
title: 'Lync Server 2013: definindo a política de local'
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
ms.openlocfilehash: 9842b5bec4b635566288998d6e8110fcc51463d7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048194"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-location-policy-for-lync-server-2013"></a><span data-ttu-id="10304-102">Definir a política de local para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10304-102">Defining the location policy for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10304-103">_**Última modificação do tópico:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="10304-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="10304-104">Cada política de local contém as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="10304-104">Each location policy contains the following information:</span></span>

  - <span data-ttu-id="10304-105">**Serviços de emergência habilitados**</span><span class="sxs-lookup"><span data-stu-id="10304-105">**Emergency Services Enabled**</span></span>  
    <span data-ttu-id="10304-106">Quando este valor é **Sim**, o cliente é habilitado para E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="10304-106">When this value is **Yes**, the client is enabled for E9-1-1.</span></span> <span data-ttu-id="10304-107">Quando um cliente se registra, ele tenta adquirir um local do serviço de informações de local e incluirá as informações de local como parte de uma chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="10304-107">When a client registers, it attempts to acquire a location from the Location Information service and will include the location information as part of an emergency call.</span></span>

<!-- end list -->

  - <span data-ttu-id="10304-108">**Local necessário**</span><span class="sxs-lookup"><span data-stu-id="10304-108">**Location Required**</span></span>  
    <span data-ttu-id="10304-109">Essa configuração é usada somente quando os **serviços de emergência habilitados** estão definidos como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="10304-109">This setting is used only when **Emergence Services Enabled** is set to **Yes**.</span></span>
    
    <span data-ttu-id="10304-p102">É possível definir a configuração **Local Necessário** para definir o comportamento do cliente. A definição do valor como **Não** significa que o usuário não receberá uma solicitação de local. A definição do valor como **Sim** significa que o usuário receberá uma solicitação por um local, mas poderá ignorar a solicitação. A definição do valor como **Aviso de isenção de responsabilidade** significa que o usuário receberá uma solicitação por um local e mostrará um aviso de isenção de responsabilidade caso ele tente ignorar a solicitação. Em todos os casos, o usuário pode continuar a usar o cliente.</span><span class="sxs-lookup"><span data-stu-id="10304-p102">You can configure the **Location Required** setting to define the client behavior. Setting the value to **No** means that the user will not be prompted for a location. Setting the value to **Yes** means that the user will be prompted for a location, but can dismiss the prompt. Setting the value to **Disclaimer** means that the user will be prompted for a location and also will be shown a disclaimer if they try to dismiss the prompt. In all cases, the user can continue to use the client.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="10304-p103">O texto do aviso de isenção de responsabilidade não aparecerá se um usuário inserir manualmente um local antes de ser habilitado para E9-1-1. As atualizações para o texto do aviso de isenção de responsabilidade não será visualizado pelos usuários que já visualizaram o aviso de isenção de responsabilidade.</span><span class="sxs-lookup"><span data-stu-id="10304-p103">The disclaimer text will not appear if a user manually entered a location before being enabled for E9-1-1. Updates to the disclaimer text will not be viewed by users that have already viewed the disclaimer.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="10304-117">**Isenção de Responsabilidade do Serviço de Emergência Avançado**</span><span class="sxs-lookup"><span data-stu-id="10304-117">**Enhanced Emergency Service Disclaimer**</span></span>  
    <span data-ttu-id="10304-118">Esta configuração especifica o aviso de isenção que o usuário ver se ignorar o aviso em um local.</span><span class="sxs-lookup"><span data-stu-id="10304-118">This setting specifies the disclaimer that users see if they dismiss the prompt for a location.</span></span> <span data-ttu-id="10304-119">No Lync Server 2013, você pode usar a política de local para definir avisos de isenção de responsabilidade diferentes para localidades diferentes ou diferentes conjuntos de usuários.</span><span class="sxs-lookup"><span data-stu-id="10304-119">In Lync Server 2013, you can use location policy to set different disclaimers for different locales or different sets of users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="10304-120">Essa configuração de política de local difere do Lync Server 2010, onde você usou o cmdlet <STRONG>set-CsEnhancedEmergencyServiceDisclaimer</STRONG> para definir um aviso global para toda a organização.</span><span class="sxs-lookup"><span data-stu-id="10304-120">This location policy setting differs from Lync Server 2010, where you used the <STRONG>Set-CsEnhancedEmergencyServiceDisclaimer</STRONG> cmdlet to set a global disclaimer for the entire organization.</span></span> <span data-ttu-id="10304-121">Se um aviso de isenção global já existir, você precisa especificar o aviso de isenção na política de local.</span><span class="sxs-lookup"><span data-stu-id="10304-121">If a global disclaimer already exists, you need to specify that disclaimer in location policy.</span></span> <span data-ttu-id="10304-122">Ou seja, o Lync Server 2013 usa apenas avisos de isenção de responsabilidade especificados na política de local.</span><span class="sxs-lookup"><span data-stu-id="10304-122">That is, Lync Server 2013 uses only disclaimers specified in location policy.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="10304-123">**Sequência de discagem de emergência**</span><span class="sxs-lookup"><span data-stu-id="10304-123">**Emergency Dial String**</span></span>  
    <span data-ttu-id="10304-p106">Esta  sequência de discagem (menos o “+” inicial, mas incluindo qualquer normalização realizada pelo Plano de discagem do usuário do Lync) que significa que uma chamada é uma chamada de emergência. A **Sequência de discagem de emergência** faz com que o cliente inclua na chamada informações sobre o local e sobre retorno de chamada.</span><span class="sxs-lookup"><span data-stu-id="10304-p106">This dial string (less the leading “+”, but including any normalization done by the Lync user’s Dial Plan) signifies that a call is an emergency call. The **Emergency Dial String** causes the client to include location and callback information with the call.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="10304-126">Se sua organização não usa um prefixo de acesso de linha externa, não será necessário criar uma regra de normalização do Plano de discagem correspondente que acrescenta um “+” à sequência 911 antes de enviar a chamada ao Roteamento de saída em um servidor de pool do Lync; o “+” será automaticamente pré-demarcado pelo cliente do Lync como resultado da política de local.</span><span class="sxs-lookup"><span data-stu-id="10304-126">If your organization does not use an external line access prefix, you do not need to create a corresponding Dial Plan normalization rule that adds a “+” to the 911 string prior to sending the call to Outbound Routing on a Lync pool server; the “+” will be automatically prepended by the Lync client as a result of the location policy.</span></span> <span data-ttu-id="10304-127">No entanto, se seu site usar um prefixo de acesso externo, é necessário adicionar uma regra de normalização à política de Plano de discagem aplicável que retira o prefixo de acesso externo e adiciona o “+”.</span><span class="sxs-lookup"><span data-stu-id="10304-127">However, if your site uses an external access prefix, you need to add a normalization rule to the applicable Dial Plan policy that strips the external access prefix and adds the “+”.</span></span> <span data-ttu-id="10304-128">Por exemplo, se seu local usar um prefixo de acesso externo 9 e um usuário discar 9&nbsp;911 para fazer uma chamada de emergência, o cliente usará sua política de plano de discagem para normalizar isso para + 911 antes que o número discado seja avaliado pelas rotas no perfil de local do chamador.</span><span class="sxs-lookup"><span data-stu-id="10304-128">For example, if your location uses an external access prefix of 9 and a user dials 9&nbsp;911 to place an emergency call, the client will use its Dial Plan policy to normalize this to +911 before the dialed number is evaluated by the routes in the caller’s location profile.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="10304-129">**Máscaras da sequência de discagem de emergência**</span><span class="sxs-lookup"><span data-stu-id="10304-129">**Emergency Dial String Masks**</span></span>  
    <span data-ttu-id="10304-p108">Uma lista separada por ponto e vírgula de sequências de discagem a serem traduzidas para a **Sequência de discagem de emergência**. Por exemplo, você pode querer adicionar 112, que é o número do serviço de emergência em grande parte da Europa. Talvez um usuário do Lync vindo da Europa não saiba que 911 é o número de emergência nos EUA, mas ele pode discar 112 e obter o mesmo resultado. Assim como ocorre com a Sequência de discagem de emergência, não inclua um “+” antes de cada número e se você usar os códigos de acesso de linha externa, certifique-se de que existam regras de normalização na política de Plano de discagem do usuário para retirar o dígito do código de acesso.</span><span class="sxs-lookup"><span data-stu-id="10304-p108">A semicolon-separated list of dial strings that is translated into the specified **Emergency Dial String**. For example, you may want to add 112, which is the emergency service number for most of Europe. A visiting Lync user from Europe may not know that 911 is the U.S. emergency number, but they can dial 112 and get the same result. As with the Emergency Dial String, do not include a “+” before each number, and if you use external line access codes, be sure there are normalization rules in the user’s Dial Plan policy to strip off the access code digit.</span></span>

<!-- end list -->

  - <span data-ttu-id="10304-134">**Uso de PSTN**</span><span class="sxs-lookup"><span data-stu-id="10304-134">**PSTN Usage**</span></span>  
    <span data-ttu-id="10304-135">O nome do Uso de PSTN que contém os caminhos de roteamento que determinam para qual tronco SIP, gateway PSTN ou gateway ELIN as chamadas serão encaminhadas.</span><span class="sxs-lookup"><span data-stu-id="10304-135">The name of the PSTN Usage that contains the routing paths that determine which SIP trunk, PSTN gateway, or ELIN gateway emergency calls will go to.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="10304-p109">É possível atribuir apenas um Uso a uma política de local. Esse Uso de PSTN substitui os Usos de PSTN atribuídos à política de voz do usuário, mas se aplica somente às chamadas feitas para a Sequência de discagem de emergência ou uma das Máscaras de sequência de chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="10304-p109">Only one usage can be assigned to a location policy. This PSTN Usage overrides the PSTN Usages assigned to the user’s voice policy, but applies only to calls placed to the Emergency Dial String or to one of the Emergency Dial String Masks.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="10304-138">**URI de notificação**</span><span class="sxs-lookup"><span data-stu-id="10304-138">**Notification URI**</span></span>  
    <span data-ttu-id="10304-p110">Especifica um ou mais URIs SIP do pessoal de segurança que receberá uma notificação de mensagem instantânea (IM) quando uma chamada de emergência for realizada. Os grupos de distribuição são suportados.</span><span class="sxs-lookup"><span data-stu-id="10304-p110">Specifies one or more SIP URIs of the security personnel who receive an instant messaging (IM) notification when an emergency call is placed. Distribution groups are supported.</span></span>

<!-- end list -->

  - <span data-ttu-id="10304-141">**URI de conferência**</span><span class="sxs-lookup"><span data-stu-id="10304-141">**Conference URI**</span></span>  
    <span data-ttu-id="10304-142">Especifica um número DID (discagem direta interna) (normalmente um número do suporte de segurança) que deve ser verificado quando uma chamada de emergência é feita.</span><span class="sxs-lookup"><span data-stu-id="10304-142">Specifies a direct inward dialing (DID) number (typically, a security desk number) that should be conferenced in when an emergency call is placed.</span></span>

<!-- end list -->

  - <span data-ttu-id="10304-143">**Modo de conferência**</span><span class="sxs-lookup"><span data-stu-id="10304-143">**Conference Mode**</span></span>  
    <span data-ttu-id="10304-144">Especifica se o URI de conferência será inserido na chamada de emergência usando comunicação de uma ou duas vias.</span><span class="sxs-lookup"><span data-stu-id="10304-144">Specifies if the conference URI will be conferenced into the emergency call by using one-way or two-way communication.</span></span>

<!-- end list -->

  - <span data-ttu-id="10304-145">**Intervalo de atualização de local**</span><span class="sxs-lookup"><span data-stu-id="10304-145">**Location Refresh Interval**</span></span>  
    <span data-ttu-id="10304-146">Especifica a quantidade de tempo (em horas) entre as solicitações de cliente para uma atualização de local do serviço de informações de local.</span><span class="sxs-lookup"><span data-stu-id="10304-146">Specifies the amount of time (in hours) between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="10304-147">O valor pode ser definido para qualquer valor entre 1 e 12.</span><span class="sxs-lookup"><span data-stu-id="10304-147">The value can be set to any value between 1 and 12.</span></span> <span data-ttu-id="10304-148">O valor padrão é 4.</span><span class="sxs-lookup"><span data-stu-id="10304-148">The default value is 4.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

