---
title: 'Lync Server 2013: políticas de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Voice policies
ms:assetid: b7433c62-9d8c-48af-89a0-19f0d34806ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412891(v=OCS.15)
ms:contentKeyID: 48185223
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a9df9b1caa42d3dc17d2f4f9e0908ed69d5660d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041280"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voice-policies-in-lync-server-2013"></a><span data-ttu-id="fec79-102">Políticas de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fec79-102">Voice policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fec79-103">_**Última modificação do tópico:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="fec79-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="fec79-104">*As políticas de voz* do Lync Server definem o seguinte para cada usuário, site ou organização ao qual a política é atribuída:</span><span class="sxs-lookup"><span data-stu-id="fec79-104">Lync Server *voice policies* define the following for each user, site, or organization that is assigned the policy:</span></span>

  - <span data-ttu-id="fec79-105">Um conjunto de recursos de chamada que podem ser habilitados ou desabilitados para determinar a funcionalidade do Enterprise Voice disponível para os usuários.</span><span class="sxs-lookup"><span data-stu-id="fec79-105">A set of calling features that can be enabled or disabled to determine the Enterprise Voice functionality available to users.</span></span>

  - <span data-ttu-id="fec79-106">Um conjunto de registros de uso de PSTN (Rede telefônica comutada pública) que define quais tipos de chamadas são autorizadas.</span><span class="sxs-lookup"><span data-stu-id="fec79-106">A set of public switched telephone network (PSTN) usage records that define what types of calls are authorized.</span></span>

<div>

## <a name="planning-for-voice-policies"></a><span data-ttu-id="fec79-107">Planejando as políticas de voz</span><span class="sxs-lookup"><span data-stu-id="fec79-107">Planning for Voice Policies</span></span>

<span data-ttu-id="fec79-108">As etapas a seguir o ajudarão a planejar as políticas de voz necessárias para a implantação do Enterprise Voice:</span><span class="sxs-lookup"><span data-stu-id="fec79-108">The following steps will help you plan the voice policies that you will need for your Enterprise Voice deployment:</span></span>

  - <span data-ttu-id="fec79-109">Determine como você configurará sua política de voz global (a política de voz padrão instalada com o produto).</span><span class="sxs-lookup"><span data-stu-id="fec79-109">Determine how you will configure your global voice policy (the default voice policy that is installed with the product).</span></span> <span data-ttu-id="fec79-110">Essa política será aplicada a todos os usuários do Enterprise Voice que não tenham atribuído explicitamente uma política de nível de site ou por usuário.</span><span class="sxs-lookup"><span data-stu-id="fec79-110">This policy will apply to all Enterprise Voice users who are not explicitly assigned a site-level or per-user policy.</span></span>

  - <span data-ttu-id="fec79-111">Identifique as políticas de voz de nível de local que você possa precisar.</span><span class="sxs-lookup"><span data-stu-id="fec79-111">Identify any site-level voice policies that you might need.</span></span>

  - <span data-ttu-id="fec79-112">Identifique as políticas de voz por usuário que você possa precisar.</span><span class="sxs-lookup"><span data-stu-id="fec79-112">Identify any per-user voice policies that you might need.</span></span>

  - <span data-ttu-id="fec79-113">Decida quais recursos de chamada serão habilitados para cada política de voz.</span><span class="sxs-lookup"><span data-stu-id="fec79-113">Decide which call features to enable for each voice policy.</span></span>

  - <span data-ttu-id="fec79-114">Determine quais registros de uso de PSTN configurar para cada política de voz.</span><span class="sxs-lookup"><span data-stu-id="fec79-114">Determine what PSTN usage records to configure for each voice policy.</span></span>

<div>

## <a name="voice-policy-scope"></a><span data-ttu-id="fec79-115">Escopo da política de voz</span><span class="sxs-lookup"><span data-stu-id="fec79-115">Voice Policy Scope</span></span>

<span data-ttu-id="fec79-116">*Escopo da política de voz* determina o nível hierárquico no qual a política pode ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="fec79-116">*Voice policy scope* determines the hierarchical level at which the policy can be applied.</span></span> <span data-ttu-id="fec79-117">No Lync Server, você pode configurar políticas de voz com os seguintes níveis de escopo (listados do mais específico para o mais geral).</span><span class="sxs-lookup"><span data-stu-id="fec79-117">In Lync Server, you can configure voice policies with the following scope levels (listed from the most specific to the most general).</span></span>

  - <span data-ttu-id="fec79-p103">A **Política de voz de usuário** pode ser atribuída a usuários individuais, grupos ou objetos de contato. Essa á política de nível mais baixo. As políticas de voz de usuário podem ser implantadas a fim de habilitar recursos para determinados usuários ou grupos em um site, mas não para outros no mesmo site. Por exemplo, talvez você queira desabilitar a discagem de longa distância para alguns funcionários. Para o objetivo de atribuir uma política de voz, um objeto de contato é tratado como um usuário individual.</span><span class="sxs-lookup"><span data-stu-id="fec79-p103">**User voice policy** can be assigned to individual users, groups, or contact objects. This is the lowest level policy. User voice policies can be deployed to enable features for certain users or groups at a site, but not for others in the same site. For example, you may want to disable long distance dialing for some employees. For the purpose of assigning a voice policy, a contact object is treated as an individual user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fec79-123">Recomendamos que você implante uma política de voz de usuário para usuários do Enterprise Voice do site de filial registrados com a implantação do site central ou usuários registrados em um aparelho de filial persistente.</span><span class="sxs-lookup"><span data-stu-id="fec79-123">We recommend that you deploy a user voice policy for branch site Enterprise Voice users who are registered with the central site deployment, or users who are registered on a Survivable Branch Appliance.</span></span>

    
    </div>

  - <span data-ttu-id="fec79-p104">**Política de voz de site** se aplica a todo um site, exceto para quaisquer usuários, grupos ou objetos de contato que recebam uma política de voz de usuário. Para definir uma política de voz de site, você precisa especificar o site ao qual a política será aplicada. Se uma política de voz de usuário não tiver sido atribuída, a política de voz de site será usada.</span><span class="sxs-lookup"><span data-stu-id="fec79-p104">**Site voice policy** applies to an entire site, except for any users, groups, or contact objects that are assigned a user voice policy. To define a site voice policy, you must specify the site to which the policy applies. If a user voice policy is not assigned, the site voice policy is used.</span></span>

  - <span data-ttu-id="fec79-127">**Política de voz global** é a política de voz padrão, instalada com o produto.</span><span class="sxs-lookup"><span data-stu-id="fec79-127">**Global voice policy** is the default voice policy that is installed with the product.</span></span> <span data-ttu-id="fec79-128">É possível editar a política de voz global a fim de atender às necessidades específicas de sua organização, mas não é possível renomear ou excluí-la.</span><span class="sxs-lookup"><span data-stu-id="fec79-128">You can edit the global voice policy to meet the specific needs of your organization, but you cannot rename or delete it.</span></span> <span data-ttu-id="fec79-129">Esta política de voz aplica-se a todos os usuários, grupos e objetos de contato do Enterprise Voice em sua implantação, a menos que você configure e atribua uma política de voz com um escopo mais específico.</span><span class="sxs-lookup"><span data-stu-id="fec79-129">This voice policy applies to all Enterprise Voice users, groups, and contact objects in your deployment unless you configure and assign a voice policy with more specific scope.</span></span> <span data-ttu-id="fec79-130">Se você quiser desabilitar totalmente essa política, certifique-se de que todos os sites e usuários tenham políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="fec79-130">If you want to disable this policy entirely, be sure that all sites and users have custom policies assigned to them.</span></span>

</div>

<div>

## <a name="call-features"></a><span data-ttu-id="fec79-131">Recursos de chamada</span><span class="sxs-lookup"><span data-stu-id="fec79-131">Call Features</span></span>

<span data-ttu-id="fec79-132">É possível habilitar ou desabilitar os recursos de chamada a seguir para cada política de voz:</span><span class="sxs-lookup"><span data-stu-id="fec79-132">You can enable or disable the following call features for each voice policy:</span></span>

  - <span data-ttu-id="fec79-p106">**Encaminhamento de chamada** permite que os usuários encaminhem chamadas a outros telefones e dispositivos clientes. Habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="fec79-p106">**Call forwarding** enables users to forward calls to other phones and client devices. Enabled by default.</span></span>

  - <span data-ttu-id="fec79-p107">**Delegação** permite que o usuário especifique outros usuários para enviar e receber chamadas em seu nome. Habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="fec79-p107">**Delegation** enables users to specify other users to send and receive calls on their behalf. Enabled by default.</span></span>

  - <span data-ttu-id="fec79-p108">**Transferência de chamada** permite a transferência de chamadas para outros usuários. Habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="fec79-p108">**Call transfer** enables users to transfer calls to other users. Enabled by default.</span></span>

  - <span data-ttu-id="fec79-p109">**Estacionamento de chamada** permite que os usuários estacionem chamadas e atendam à chamada de um telefone ou cliente diferente. Desabilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="fec79-p109">**Call park** enables users to park calls and then pick up the call from a different phone or client. Disabled by default.</span></span>

  - <span data-ttu-id="fec79-p110">**Toque simultâneo** permite que as chamadas recebidas toquem em um telefone adicional (por exemplo, um celular) ou outros dispositivos. Habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="fec79-p110">**Simultaneous ringing** enables incoming calls to ring on an additional phone (for example, a mobile phone) or other endpoint devices. Enabled by default.</span></span>

  - <span data-ttu-id="fec79-p111">**Chamada de equipe** permite que os usuários de uma equipe definida respondam às chamadas de outros membros da equipe. Habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="fec79-p111">**Team call** enables users on a defined team to answer calls for other members of the team. Enabled by default.</span></span>

  - <span data-ttu-id="fec79-p112">**Redirecionamento de PSTN** permite que as chamadas realizadas por usuários que receberam essa política para outros usuários empresariais sejam redirecionadas na PSTN (Rede Telefônica Pública Comutada) se a WAN estiver congestionada ou indisponível. Habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="fec79-p112">**PSTN reroute** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the public switched telephone network (PSTN) if the WAN is congested or unavailable. Enabled by default.</span></span>

  - <span data-ttu-id="fec79-p113">**Substituição da política de largura de banda** permite que os administradores substituam as decisões da política de controle de admissão de chamada para um usuário específico. Desabilitada por padrão.</span><span class="sxs-lookup"><span data-stu-id="fec79-p113">**Bandwidth policy override** enables administrators to override call admission control policy decisions for a particular user. Disabled by default.</span></span>

  - <span data-ttu-id="fec79-149">O **rastreamento de chamada mal-intencionada** permite que os usuários reportem chamadas mal intencionadas usando o cliente Lync e, em seguida, sinalizam essas chamadas nos registros de detalhes da chamada.</span><span class="sxs-lookup"><span data-stu-id="fec79-149">**Malicious call tracing** enables users to report malicious calls by using the Lync client, and then flags such calls in the call detail records.</span></span> <span data-ttu-id="fec79-150">Desabilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="fec79-150">Disabled by default.</span></span>

  - <span data-ttu-id="fec79-151">O **Escape do correio de voz** impede que as chamadas sejam roteadas imediatamente para o sistema de correio de voz do telefone móvel do usuário quando a chamada simultânea está configurada e o telefone está desligado, sem bateria ou fora de área, tendo por base um valor de temporizador.</span><span class="sxs-lookup"><span data-stu-id="fec79-151">**Voicemail escape** prevents calls from being immediately routed to the user’s mobile phone voicemail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range, and is based on a timer value.</span></span> <span data-ttu-id="fec79-152">Esta configuração habilita e desabilita o temporizador e define o valor dele.</span><span class="sxs-lookup"><span data-stu-id="fec79-152">This setting enables and disables the timer and sets the value of the timer.</span></span> <span data-ttu-id="fec79-153">Ela pode ser configurada apenas usando o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fec79-153">It can be configured only by using the Lync Server Management Shell.</span></span> <span data-ttu-id="fec79-154">Desabilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="fec79-154">Disabled by default.</span></span>

  - <span data-ttu-id="fec79-p116">**Usos de PSTN de encaminhamento de chamadas e toque simultâneo** permite que os administradores especifiquem o mesmo uso de PSTN que a política de voz para encaminhamento de chamadas e toque simultâneo, restrinjam o encaminhamento de chamadas e o toque simultâneo somente a usuários internos do Lync ou especificar um uso personalizado de PSTN diferente do uso de PSTN da política de voz. O padrão é usar o mesmo uso de PSTN que a política de voz para encaminhamento de chamadas e toque simultâneo.</span><span class="sxs-lookup"><span data-stu-id="fec79-p116">**Call forwarding and simultaneous ringing PSTN usages** enables administrators to specify the same PSTN usage as the voice policy for call forwarding and simultaneous ringing, restrict call forwarding and simultaneous ringing to internal Lync users only, or specify a custom PSTN usage that is different from the voice policy’s PSTN usage. The default is to use the same PSTN usage as the voice policy for call forwarding and simultaneous ringing.</span></span>

</div>

<div>

## <a name="pstn-usage-records"></a><span data-ttu-id="fec79-157">Registros de uso de PSTN</span><span class="sxs-lookup"><span data-stu-id="fec79-157">PSTN Usage Records</span></span>

<span data-ttu-id="fec79-158">Cada política de voz deve ter um ou mais registros de uso de PSTN associados.</span><span class="sxs-lookup"><span data-stu-id="fec79-158">Each voice policy should have one or more associated PSTN usage records.</span></span> <span data-ttu-id="fec79-159">Os usos de PSTN podem ser associados a uma política de voz somente para toque simultâneo e encaminhamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="fec79-159">PSTN usages can be associated with a voice policy for the purpose of simultaneous ringing and call forwarding only.</span></span> <span data-ttu-id="fec79-160">Para obter detalhes sobre o planejamento de registros de uso de PSTN, consulte [PSTN Usage Records in Lync Server 2013](lync-server-2013-pstn-usage-records.md).</span><span class="sxs-lookup"><span data-stu-id="fec79-160">For details about planning PSTN usage records, see [PSTN usage records in Lync Server 2013](lync-server-2013-pstn-usage-records.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fec79-p118">A ordem de uso de PSTN é fundamental, pois ao se comparar usuários a rotas, a funcionalidade de roteamento de saída compara as utilizações de PSTN do início ao fim. Se o primeiro uso corresponder à rota da chamada, essa rota será usada. Caso contrário, a funcionalidade de roteamento de saída analisa o próximo uso de PSTN na lista e continua até que uma correspondência seja encontrada. De fato, os usos de PSTN subsequentes fornecem um backup se o primeiro da lista não estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="fec79-p118">PSTN usage order is critical because in matching users to routes, the outbound routing functionality compares PSTN usages from top to bottom. If the first usage matches the call route, that route is used. If not, the outbound routing functionality looks at the next PSTN usage on the list and continues until a match is found. In effect, the subsequent PSTN usages provide backup if the first one on the list is unavailable.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

