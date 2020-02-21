---
title: 'Lync Server 2013: modelos de usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 user models
ms:assetid: c551371c-d740-4372-bada-f0d713ec0d33
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398811(v=OCS.15)
ms:contentKeyID: 49733811
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 389d545c18edb4a3c14fc2f0abdf5fb185fcd0ae
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213047"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-models-in-lync-server-2013"></a><span data-ttu-id="c39c6-102">Modelos de usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c39c6-102">User models in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c39c6-103">_**Última modificação do tópico:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="c39c6-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="c39c6-104">Os modelos de usuário descritos aqui fornecem a base para as medições de planejamento de capacidade e recomendações descritas no [planejamento de capacidade do Lync Server 2013 usando os modelos de usuário](lync-server-2013-capacity-planning-using-the-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="c39c6-104">The user models described here provide the basis for the capacity planning measurements and recommendations described in [Capacity planning for Lync Server 2013 using the user models](lync-server-2013-capacity-planning-using-the-user-models.md).</span></span>

<div>

## <a name="lync-server-2013-user-models"></a><span data-ttu-id="c39c6-105">Modelos de usuário do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c39c6-105">Lync Server 2013 User Models</span></span>

<span data-ttu-id="c39c6-106">A tabela a seguir descreve o modelo de usuário para registro, contatos, mensagens instantâneas (IM) e presença para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c39c6-106">The following table describes the user model for registration, contacts, instant messaging (IM), and presence for Lync Server 2013.</span></span>

### <a name="environment-and-registration-user-model"></a><span data-ttu-id="c39c6-107">Modelo de usuário de ambiente e registro</span><span class="sxs-lookup"><span data-stu-id="c39c6-107">Environment and Registration User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c39c6-108">Categoria</span><span class="sxs-lookup"><span data-stu-id="c39c6-108">Category</span></span></th>
<th><span data-ttu-id="c39c6-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="c39c6-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c39c6-110">Tamanho da implantação e distribuição</span><span class="sxs-lookup"><span data-stu-id="c39c6-110">Deployment size and distribution</span></span></p></td>
<td><p><span data-ttu-id="c39c6-111">Modelamos uma grande implantação com três locais centrais, com um pool de Front-end por local.</span><span class="sxs-lookup"><span data-stu-id="c39c6-111">We model a large deployment with three central sites, with one Front End pool per site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c39c6-112">Porcentagem de usuários do Active Directory</span><span class="sxs-lookup"><span data-stu-id="c39c6-112">Percentage of Active Directory users</span></span></p></td>
<td><p><span data-ttu-id="c39c6-113">Supomos que 70% de todos os usuários do Active Directory na organização estão habilitados para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c39c6-113">We assume that 70% of all Active Directory users in the organization are enabled for Lync Server.</span></span> <span data-ttu-id="c39c6-114">80% dos usuários habilitados estão conectados ao Lync Server por dia (80% de simultaneidade).</span><span class="sxs-lookup"><span data-stu-id="c39c6-114">80% of those enabled users are logged on to Lync Server each day (80% concurrency).</span></span> <span data-ttu-id="c39c6-115">Os usuários simultâneos são a base para os números no restante desta seção.</span><span class="sxs-lookup"><span data-stu-id="c39c6-115">The concurrent users are the basis for the numbers in the rest of this section.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c39c6-116">Mudanças do Active Directory</span><span class="sxs-lookup"><span data-stu-id="c39c6-116">Active Directory changes</span></span></p></td>
<td><p><span data-ttu-id="c39c6-117">Presumimos que 0,5% do total de usuários são criados e habilitados para o Lync no Active Directory por semana, e que 0,5% do total de usuários estão desabilitados do Active Directory e do Lync por semana.</span><span class="sxs-lookup"><span data-stu-id="c39c6-117">We assume that 0.5% of total users are created and enabled for Lync in Active Directory each week, and that 0.5% of total users are disabled from Active Directory and from Lync each week.</span></span> <span data-ttu-id="c39c6-118">5% dos usuários possuem pelo menos um atributo do Active Directory alterado cada semana.</span><span class="sxs-lookup"><span data-stu-id="c39c6-118">5% of users have at least one Active Directory attribute changed each week.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c39c6-119">Grupos de distribuição do Active Directory</span><span class="sxs-lookup"><span data-stu-id="c39c6-119">Active Directory distribution groups</span></span></p></td>
<td><p><span data-ttu-id="c39c6-p103">Supomos que o número de grupos de distribuição do Active Directory na organização seja igual a três vezes o número de todos os usuários no Active Directory. Os grupos de distribuição têm os seguintes tamanhos:</span><span class="sxs-lookup"><span data-stu-id="c39c6-p103">We assume that the number of Active Directory distribution groups in the organization is equal to three times the number of all users in Active Directory. The distribution groups have the following sizes:</span></span></p>
<ul>
<li><p><span data-ttu-id="c39c6-122">64% têm de 2 a 30 usuários</span><span class="sxs-lookup"><span data-stu-id="c39c6-122">64% have 2-30 users</span></span></p></li>
<li><p><span data-ttu-id="c39c6-123">13% têm de 31 a 50 usuários</span><span class="sxs-lookup"><span data-stu-id="c39c6-123">13% have 31-50 users</span></span></p></li>
<li><p><span data-ttu-id="c39c6-124">10% têm de 51 a 100 usuários</span><span class="sxs-lookup"><span data-stu-id="c39c6-124">10% have 51-100 users</span></span></p></li>
<li><p><span data-ttu-id="c39c6-125">13% têm de 101 a 500 usuários</span><span class="sxs-lookup"><span data-stu-id="c39c6-125">13% have 101-500 users</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c39c6-126">Usuários de VoIP (Voz sobre IP)</span><span class="sxs-lookup"><span data-stu-id="c39c6-126">Voice over IP (VoIP) users</span></span></p></td>
<td><p><span data-ttu-id="c39c6-127">60% dos usuários do Lync Server estão habilitados para comunicações unificadas (UC) (ou seja, seus números de telefone são proprietários do Lync Server).</span><span class="sxs-lookup"><span data-stu-id="c39c6-127">60% of Lync Server users are enabled for unified communications (UC) (that is, their phone numbers are owned by Lync Server).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c39c6-128">Distribuição dos cliente registrados</span><span class="sxs-lookup"><span data-stu-id="c39c6-128">Registered client distribution</span></span></p></td>
<td><p><span data-ttu-id="c39c6-129">65% dos clientes executam o software Lync 2013, incluindo o Lync e o Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="c39c6-129">65% of clients run Lync 2013 software, including Lync and Lync Phone Edition.</span></span></p>
<p><span data-ttu-id="c39c6-130">30% dos clientes que executam software cliente de uma versão anterior do Lync.</span><span class="sxs-lookup"><span data-stu-id="c39c6-130">30% of clients running client software from a previous version of Lync.</span></span></p>
<p><span data-ttu-id="c39c6-131">5% dos clientes usando o Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="c39c6-131">5% of clients using Lync Web App.</span></span></p>
<p><span data-ttu-id="c39c6-132">Se a mobilidade estiver habilitada, presumimos que 40% dos usuários estejam usando a mobilidade simultaneamente com as outras opções de cliente registradas anteriormente citadas.</span><span class="sxs-lookup"><span data-stu-id="c39c6-132">If mobility is enabled, we assume that 40% of users are using mobility concurrently with the other previously cited registered client options.</span></span> <span data-ttu-id="c39c6-133">Nesse caso, a taxa de MPOP (ponto de presença) de vários clientes é 1:1.9.</span><span class="sxs-lookup"><span data-stu-id="c39c6-133">In this case the client multiple point of presence (MPOP) ratio is 1:1.9.</span></span> <span data-ttu-id="c39c6-134">Se a mobilidade está desabilitada, a taxa MPOP é de 1:1.5.</span><span class="sxs-lookup"><span data-stu-id="c39c6-134">If mobility is disabled, the MPOP ratio is 1:1.5.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c39c6-135">Distribuição dos usuários remotos</span><span class="sxs-lookup"><span data-stu-id="c39c6-135">Remote user distribution</span></span></p></td>
<td><p><span data-ttu-id="c39c6-136">70% os usuários se conectam internamente.</span><span class="sxs-lookup"><span data-stu-id="c39c6-136">70% of users connecting internally.</span></span></p>
<p><span data-ttu-id="c39c6-137">30% dos usuários se conectam por meio de um Servidor de Borda e um Diretor.</span><span class="sxs-lookup"><span data-stu-id="c39c6-137">30% of users connecting through an Edge Server and a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c39c6-138">Distribuição dos contatos</span><span class="sxs-lookup"><span data-stu-id="c39c6-138">Contact distribution</span></span></p></td>
<td><p><span data-ttu-id="c39c6-p105">O número máximo de contatos de um usuário é 1.000. Menos de um 1% dos usuários tem 1.000 contatos. Menos de 25% dos usuários têm 100 ou mais contatos.</span><span class="sxs-lookup"><span data-stu-id="c39c6-p105">The maximum number of contacts a user has is 1,000. Less than 1% of users have 1,000 contacts. Less than 25% of users have 100 or more contacts.</span></span></p>
<p><span data-ttu-id="c39c6-p106">Média de 80 contatos para usuários com conectividade pública na nuvem. Desses usuários:</span><span class="sxs-lookup"><span data-stu-id="c39c6-p106">Average of 80 contacts for users with public cloud connectivity. Of these users:</span></span></p>
<ul>
<li><p><span data-ttu-id="c39c6-p107">50% dos contatos estão dentro da organização. 10% desses usuários são usuários remotos, se conectando de fora do firewall.</span><span class="sxs-lookup"><span data-stu-id="c39c6-p107">50% of the contacts are within the organization. 10% of those users are remote users, connecting from outside the firewall.</span></span></p></li>
<li><p><span data-ttu-id="c39c6-146">40% dos contatos são usuários públicos na nuvem (como usuários do AOL, Yahoo!, MSN ou Google Talk).</span><span class="sxs-lookup"><span data-stu-id="c39c6-146">40% of the contacts are public cloud users (such as users of AOL, Yahoo!, MSN, or Google Talk).</span></span></p></li>
<li><p><span data-ttu-id="c39c6-147">10% dos contatos são de parceiros federados.</span><span class="sxs-lookup"><span data-stu-id="c39c6-147">10% of the contacts are from federated partners.</span></span></p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="c39c6-148">A partir de 1º de setembro de 2012, a licença de assinatura de usuário da conectividade de IM pública do Microsoft Lync ("PIC USL") não está mais disponível para compra de contratos novos ou de renovação.</span><span class="sxs-lookup"><span data-stu-id="c39c6-148">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="c39c6-149">Os clientes com licenças ativas poderão continuar a se federar com o Yahoo!</span><span class="sxs-lookup"><span data-stu-id="c39c6-149">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="c39c6-150">Messenger até a data de encerramento do serviço.</span><span class="sxs-lookup"><span data-stu-id="c39c6-150">Messenger until the service shut down date.</span></span> <span data-ttu-id="c39c6-151">Uma data de fim de vida de junho de 2014 para AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="c39c6-151">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="c39c6-152">foi anunciado.</span><span class="sxs-lookup"><span data-stu-id="c39c6-152">has been announced.</span></span> <span data-ttu-id="c39c6-153">Para obter detalhes, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">support for Public Instant Messenger Connectivity in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c39c6-153">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="c39c6-154">O PIC USL é uma licença de assinatura por usuário por mês, necessária para o Lync Server ou o Office Communications Server federar-se com o Yahoo!</span><span class="sxs-lookup"><span data-stu-id="c39c6-154">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="c39c6-155">Instantânea.</span><span class="sxs-lookup"><span data-stu-id="c39c6-155">Messenger.</span></span> <span data-ttu-id="c39c6-156">A capacidade da Microsoft de fornecer esse serviço tem sido contingente o suporte da Yahoo!, o contrato subjacente para o qual está se enrolando para baixo.</span><span class="sxs-lookup"><span data-stu-id="c39c6-156">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="c39c6-157">Mais do que nunca, o Lync é uma poderosa ferramenta para a conexão entre organizações e pessoas em todo o mundo.</span><span class="sxs-lookup"><span data-stu-id="c39c6-157">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="c39c6-158">A Federação com o Windows Live Messenger não requer licenças de usuário/dispositivo adicionais além da CAL padrão do Lync.</span><span class="sxs-lookup"><span data-stu-id="c39c6-158">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="c39c6-159">A Federação do Skype será adicionada à lista, permitindo que os usuários do Lync atinjam centenas de milhões de pessoas com IM e voz.</span><span class="sxs-lookup"><span data-stu-id="c39c6-159">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


</div></li>
</ul>
<p><span data-ttu-id="c39c6-p111">Média de 50 contatos para usuários sem conectividade pública na nuvem. Desses usuários:</span><span class="sxs-lookup"><span data-stu-id="c39c6-p111">Average of 50 contacts for users without public cloud connectivity. Of these users:</span></span></p>
<ul>
<li><p><span data-ttu-id="c39c6-p112">80% dos contatos estão dentro da organização. 10% desses usuários são usuários remotos, se conectando de fora do firewall.</span><span class="sxs-lookup"><span data-stu-id="c39c6-p112">80% of the contacts are within the organization. 10% of those users are remote users, connecting from outside the firewall.</span></span></p></li>
<li><p><span data-ttu-id="c39c6-164">20% dos contatos são de parceiros federados.</span><span class="sxs-lookup"><span data-stu-id="c39c6-164">20% of the contacts are from federated partners.</span></span></p>
<p><span data-ttu-id="c39c6-p113">Cada usuário possui 1 grupo de distribuição em sua lista de contatos. Para testar o desempenho, assumimos que os grupos de distribuição são sempre expandidos.</span><span class="sxs-lookup"><span data-stu-id="c39c6-p113">Each user has 1 distribution group in their contact list. For performance testing, we assume that distribution groups are always expanded.</span></span></p></li>
</ul>
<p><span data-ttu-id="c39c6-167">25% dos contatos do usuário utilizam XMPP.</span><span class="sxs-lookup"><span data-stu-id="c39c6-167">25% of a user’s contacts use XMPP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c39c6-168">Tempo de sessão</span><span class="sxs-lookup"><span data-stu-id="c39c6-168">Session time</span></span></p></td>
<td><p><span data-ttu-id="c39c6-p114">A sessão média de logon do usuário dura 12 horas. Todos os usuários fazem logon em até 120 minutos após o início da sessão.</span><span class="sxs-lookup"><span data-stu-id="c39c6-p114">The average user logon session lasts 12 hours. All users log on within 120 minutes of the start of the session.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="im-and-presence-user-model"></a><span data-ttu-id="c39c6-171">Modelo de usuário de IM e presença</span><span class="sxs-lookup"><span data-stu-id="c39c6-171">IM and Presence User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c39c6-172">Categoria</span><span class="sxs-lookup"><span data-stu-id="c39c6-172">Category</span></span></th>
<th><span data-ttu-id="c39c6-173">Descrição</span><span class="sxs-lookup"><span data-stu-id="c39c6-173">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c39c6-174">Sessões de IM ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="c39c6-174">Peer-to-peer IM sessions</span></span></p></td>
<td><p><span data-ttu-id="c39c6-175">Cada usuário tem em média seis sessões de IM ponto a ponto por dia.</span><span class="sxs-lookup"><span data-stu-id="c39c6-175">Each user averages six peer-to-peer IM sessions per day.</span></span></p>
<p><span data-ttu-id="c39c6-176">10 mensagens instantâneas por sessão.</span><span class="sxs-lookup"><span data-stu-id="c39c6-176">10 instant messages per session.</span></span></p>
<p><span data-ttu-id="c39c6-177">Cada mensagem é correspondida com duas mensagens de INFO SIP e 2 mensagens de SIP 200 (para os indicadores de status como&lt;"&gt; nome está digitando")</span><span class="sxs-lookup"><span data-stu-id="c39c6-177">Each message is matched by two SIP INFO messages and 2 SIP 200 OK messages (for the status indicators such as “&lt;Name&gt; is Typing”)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c39c6-178">Sondagem de presença</span><span class="sxs-lookup"><span data-stu-id="c39c6-178">Presence polling</span></span></p></td>
<td><p><span data-ttu-id="c39c6-p115">Em geral, supomos o pool de presença com uma média de 60 pools por usuário, por hora. Para cada usuário, suponha uma média de:</span><span class="sxs-lookup"><span data-stu-id="c39c6-p115">Overall, we assume presence polling at an average of 60 polls per user per hour. For each user, assume an average of:</span></span></p>
<ul>
<li><p><span data-ttu-id="c39c6-p116">Um pool por dia de presença de usuários na guia organização do usuário (mas não na Lista de contatos). O número médio de não contatos na guia organização do usuário é de 15 usuários. Dois cartões de visita visualizando operações por dia.</span><span class="sxs-lookup"><span data-stu-id="c39c6-p116">One poll per day of the presence of users in the user’s organization tab (but not Contacts list). Average number of non-contacts in the user’s organization tab is 15 users. Two contact card viewing operations per day.</span></span></p></li>
<li><p><span data-ttu-id="c39c6-184">Um pool de presença sempre que o usuário clica em outro usuário para começar uma conversa, estimativa de uma vez por hora.</span><span class="sxs-lookup"><span data-stu-id="c39c6-184">One presence poll every time the user clicks another user to start a conversation, estimated at once per hour.</span></span></p></li>
<li><p><span data-ttu-id="c39c6-p117">Seis pesquisas do usuário por hora. Cada vez que uma pesquisa é realizada, um pool de lote é enviado para todos na lista de resultados da pesquisa. Suponha que o tamanho médio dos resultados da pesquisa é 20. Se os resultados da pesquisa permanecem na tela, o pool de lote é atualizado a cada 5 minutos; assumimos que haverá duas atualizações por hora.</span><span class="sxs-lookup"><span data-stu-id="c39c6-p117">Six user searches per hour. Every time a search is performed, a batch poll is sent for everyone in the search result list. We assume the average size of search results is 20. If the search results stay on screen, the batch poll is refreshed every 5 minutes; we assume that there will be two such refreshes per hour.</span></span></p></li>
<li><p><span data-ttu-id="c39c6-189">Quando o usuário abre ou visualiza um email no Outlook, um pool de presença de usuários nos campos Para: e Cc: do email, com estimativa de cinco emails por hora e quatro usuários por email.</span><span class="sxs-lookup"><span data-stu-id="c39c6-189">When the user opens or previews an email in Outlook, a poll of the presence of users in the To: and CC: fields of the email, estimated at five emails per hour and four users per email.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c39c6-190">Assinaturas de presença</span><span class="sxs-lookup"><span data-stu-id="c39c6-190">Presence subscriptions</span></span></p></td>
<td><p><span data-ttu-id="c39c6-p118">Quando um usuário adiciona outro como contato, o primeiro usuário está se <em>inscrevendo</em> em cinco categorias de informação sobre o segundo usuário. As atualizações dessas categorias de informação são automaticamente enviadas ao primeiro usuário.</span><span class="sxs-lookup"><span data-stu-id="c39c6-p118">When one user adds another as a contact, the first user is <em>subscribing</em> to five categories of information about the second user. Updates of these categories of information are automatically sent to the first user.</span></span></p>
<p><span data-ttu-id="c39c6-193">Para cada cliente, uma única solicitação de inscrição em lote é enviada para obter o estado de presença em uma média de 40 contatos, com 40 diálogos adicionais para obter presença de contatos federados.</span><span class="sxs-lookup"><span data-stu-id="c39c6-193">For each client, a single batch subscription request is sent to obtain the presence state of an average of 40 contacts, with an additional 40 dialogs to obtain presence for federated contacts.</span></span></p>
<p><span data-ttu-id="c39c6-194">A presença de membros de um grupo de distribuição expandido é encontrada através de inscrições de presença persistente, não pool, e é modelada como 1 expansão por usuário para cada 2 horas.</span><span class="sxs-lookup"><span data-stu-id="c39c6-194">Presence for members of an expanded distribution group is found through persistent presence subscriptions, not polling, and is modeled as 1 expansion per user for each 2 hours.</span></span></p>
<p><span data-ttu-id="c39c6-p119"><em>Descrições curtas</em> ocorrem quando um usuário faz o login, há uma inscrição de lote para todos os contatos do usuário e o usuário faz o logoff logo. Assumimos 6 inscrições curtas por usuário, por hora, onde cada inscrição dura 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="c39c6-p119"><em>Short subscriptions</em> happen when a user logs in, there is a batch subscription for all the user’s contacts, and then the user soon logs off. We assume 6 short subscriptions per user per hour, where each subscription lasts 10 minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c39c6-197">Publicação de Presença</span><span class="sxs-lookup"><span data-stu-id="c39c6-197">Presence Publication</span></span></p></td>
<td><p><span data-ttu-id="c39c6-198">O estado de presença é publicado em uma média de 4 publicações por usuário, por hora, com um máximo de 6 por usuário, por hora.</span><span class="sxs-lookup"><span data-stu-id="c39c6-198">Presence state is published at an average of 4 publications per user per hour, with a maximum 6 per user per hour.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c39c6-199">Tamanho do Documento de Presença</span><span class="sxs-lookup"><span data-stu-id="c39c6-199">Presence Document Size</span></span></p></td>
<td><p><span data-ttu-id="c39c6-200">O tamanho médio de um documento de presença completo é assumido como 4K, com um máximo de 25K.</span><span class="sxs-lookup"><span data-stu-id="c39c6-200">The average size of a complete presence document is assumed to be 4K, with a maximum of 25K.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c39c6-201">A tabela a seguir descreve o modelo de usuário para uso do catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="c39c6-201">The following table describes the user model for address book use.</span></span>

### <a name="address-book-usage-user-model"></a><span data-ttu-id="c39c6-202">Modelo de usuário para uso do catálogo de endereços</span><span class="sxs-lookup"><span data-stu-id="c39c6-202">Address Book Usage User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c39c6-203">Modo de pesquisa do Catálogo de endereços</span><span class="sxs-lookup"><span data-stu-id="c39c6-203">Address Book search mode</span></span></th>
<th><span data-ttu-id="c39c6-204">Uso</span><span class="sxs-lookup"><span data-stu-id="c39c6-204">Usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c39c6-205">Consulta da web do Catálogo de endereços somente (todas as consultas realizadas pelo serviço Consulta da web do Catálogo de endereços)</span><span class="sxs-lookup"><span data-stu-id="c39c6-205">Address Book Web Query only (all queries performed by Address Book Web Query service)</span></span></p></td>
<td><p><span data-ttu-id="c39c6-206">Quatro consultas de prefixo por usuário, por dia.</span><span class="sxs-lookup"><span data-stu-id="c39c6-206">Four prefix queries per user per day.</span></span></p>
<p><span data-ttu-id="c39c6-p120">60 consultas de pesquisa exatas por usuário, por dia. 40% delas são em lote, com uma média de 20 contatos por consulta. Os outros 60% das consultas servem para um único contato.</span><span class="sxs-lookup"><span data-stu-id="c39c6-p120">60 exact search queries per user per day. 40% of those are batched, with an average of 20 contacts per query. The other 60% of the queries are for a single contact.</span></span></p>
<p><span data-ttu-id="c39c6-p121">25 consultas de foto por usuário, por dia. 24 para uma única foto, o restante é uma consulta em lote com uma média de 20 contatos.</span><span class="sxs-lookup"><span data-stu-id="c39c6-p121">25 photo queries per user per day. 24 are for a single photo, the other is a batch query with an average of 20 contacts.</span></span></p>
<p><span data-ttu-id="c39c6-212">Uma consulta de pesquisa de organização por usuário, por dia.</span><span class="sxs-lookup"><span data-stu-id="c39c6-212">One total organization search query per user per day.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c39c6-p122">Modo misto, arquivo do catálogo de endereços e consultas da web usadas. Esse é o modo padrão.</span><span class="sxs-lookup"><span data-stu-id="c39c6-p122">Mixed mode, both address book file and web queries used. This is the default mode.</span></span></p></td>
<td><p><span data-ttu-id="c39c6-215">Somente dois tipos de consulta vão para a rede, as consultas de pesquisa de foto e organizacional total.</span><span class="sxs-lookup"><span data-stu-id="c39c6-215">Only two types of queries go to the network, the photo and total organizational search queries.</span></span></p>
<p><span data-ttu-id="c39c6-p123">25 consultas de foto por usuário, por dia. 24 para uma única foto, o restante é uma consulta em lote com uma média de 20 contatos.</span><span class="sxs-lookup"><span data-stu-id="c39c6-p123">25 photo queries per user per day. 24 are for a single photo, the other is a batch query with an average of 20 contacts.</span></span></p>
<p><span data-ttu-id="c39c6-218">Uma consulta de pesquisa de organização por usuário, por dia.</span><span class="sxs-lookup"><span data-stu-id="c39c6-218">One total organization search query per user per day.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c39c6-219">A tabela a seguir descreve o modelo de conferência.</span><span class="sxs-lookup"><span data-stu-id="c39c6-219">The following table describes the conferencing model.</span></span>

### <a name="conferencing-model"></a><span data-ttu-id="c39c6-220">Modelo de conferência</span><span class="sxs-lookup"><span data-stu-id="c39c6-220">Conferencing Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c39c6-221">Categoria</span><span class="sxs-lookup"><span data-stu-id="c39c6-221">Category</span></span></th>
<th><span data-ttu-id="c39c6-222">Descrição</span><span class="sxs-lookup"><span data-stu-id="c39c6-222">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c39c6-223">Reuniões agendadas &quot;versus reuniões&quot; de reunião agora</span><span class="sxs-lookup"><span data-stu-id="c39c6-223">Scheduled meetings versus &quot;Meet now&quot; meetings</span></span></p></td>
<td><p><span data-ttu-id="c39c6-224">60% agendadas, 40% não agendadas.</span><span class="sxs-lookup"><span data-stu-id="c39c6-224">60% scheduled, 40% unscheduled.</span></span></p>
<p><span data-ttu-id="c39c6-225">Das reuniões programadas, assumimos que 80% são conferências atribuídas, que são ocorrências de conferências recorrentes; 10% são reuniões abertas uma vez; 8% são reuniões anônimas únicas, e 2% são reuniões fechadas uma vez.</span><span class="sxs-lookup"><span data-stu-id="c39c6-225">Of the scheduled meetings, we assume that 80% are assigned conferences, which are occurences of recurring conferences; 10% are one-time open meetings; 8% are one-time anonymous meetings, and 2% are one-time closed meetings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c39c6-226">Distribuição de cliente de conferência</span><span class="sxs-lookup"><span data-stu-id="c39c6-226">Conferencing client distribution</span></span></p></td>
<td><p><span data-ttu-id="c39c6-227">Para reuniões agendadas:</span><span class="sxs-lookup"><span data-stu-id="c39c6-227">For scheduled meetings:</span></span></p>
<ul>
<li><p><span data-ttu-id="c39c6-228">65% dos usuários de conferência usam o Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="c39c6-228">65% of conferencing users use Lync 2013.</span></span></p></li>
<li><p><span data-ttu-id="c39c6-229">5% dos usuários de conferência usam o Microsoft Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="c39c6-229">5% of conferencing users use Microsoft Lync Web App.</span></span></p></li>
<li><p><span data-ttu-id="c39c6-230">30% dos usuários de conferência utilizam clientes anteriores, incluindo o Microsoft Lync 2010, o Office Communicator 2007 R2, o Office Communicator 2007 e o Microsoft Office Communicator Web Access (versão 2007).</span><span class="sxs-lookup"><span data-stu-id="c39c6-230">30% of conferencing users use earlier clients, including Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007, and Microsoft Office Communicator Web Access (2007 release).</span></span></p></li>
</ul>
<p><span data-ttu-id="c39c6-231">Para reuniões não agendadas:</span><span class="sxs-lookup"><span data-stu-id="c39c6-231">For unscheduled meetings:</span></span></p>
<ul>
<li><p><span data-ttu-id="c39c6-232">70% dos usuários de conferência usam o Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="c39c6-232">70% of conferencing users use Lync 2013.</span></span></p></li>
<li><p><span data-ttu-id="c39c6-233">30% dos usuários de conferência utilizam clientes anteriores, incluindo o Microsoft Lync 2010, o Office Communicator 2007 R2, o Office Communicator 2007 e o Microsoft Office Communicator Web Access (versão 2007).</span><span class="sxs-lookup"><span data-stu-id="c39c6-233">30% of conferencing users use earlier clients, including Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007, and Microsoft Office Communicator Web Access (2007 release).</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c39c6-234">Simultaneidade de reunião</span><span class="sxs-lookup"><span data-stu-id="c39c6-234">Meeting concurrency</span></span></p></td>
<td><p><span data-ttu-id="c39c6-p124">5% dos usuários estarão em conferências durante as horas de trabalho. Dessa forma, em um pool de 80.000 usuários, 4.000 usuários poderão estar em conferências a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="c39c6-p124">5% of users will be in conferences during working hours. Thus, in an 80,000-user pool, as many as 4,000 users might be in conferences at any one time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c39c6-237">Distribuição do áudio de reunião</span><span class="sxs-lookup"><span data-stu-id="c39c6-237">Meeting audio distribution</span></span></p></td>
<td><p><span data-ttu-id="c39c6-238">40% de combinação entre conferência de áudio VoIP e discada, com uma proporção de 3:1 de usuários VoIP para usuários discados.</span><span class="sxs-lookup"><span data-stu-id="c39c6-238">40% mixed VoIP audio and dial-in conferencing, with a 3:1 ratio of VoIP users to dial-in users.</span></span></p>
<p><span data-ttu-id="c39c6-239">35% somente de áudio VoIP.</span><span class="sxs-lookup"><span data-stu-id="c39c6-239">35% VoIP audio only.</span></span></p>
<p><span data-ttu-id="c39c6-240">15% somente de áudio de conferência discada.</span><span class="sxs-lookup"><span data-stu-id="c39c6-240">15% dial-in conferencing audio only.</span></span></p>
<p><span data-ttu-id="c39c6-241">10% sem áudio (conferências somente de IM, com uma média de cinco mensagens enviadas por usuário).</span><span class="sxs-lookup"><span data-stu-id="c39c6-241">10% no audio (IM-only conferences, with an average of five messages sent per user).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c39c6-242">Combinação de mídias para conferências</span><span class="sxs-lookup"><span data-stu-id="c39c6-242">Media mix for conferences</span></span></p></td>
<td><p><span data-ttu-id="c39c6-243">75% das conferências são conferências da Web, com áudio mais alguma outra modalidade de colaboração.</span><span class="sxs-lookup"><span data-stu-id="c39c6-243">75% of conferences are web conferences, which include audio plus some other collaboration modalities.</span></span></p>
<p><span data-ttu-id="c39c6-244">Para essas conferências, os outros métodos de colaboração são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="c39c6-244">For these conferences, the other collaboration methods are as follows:</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="c39c6-245">Esses números somam mais de 100%, pois uma conferência pode ter vários métodos de colaboração.</span><span class="sxs-lookup"><span data-stu-id="c39c6-245">These numbers add up to more than 100% because one conference can have multiple collaboration methods.</span></span>


</div>
<ul>
<li><p><span data-ttu-id="c39c6-p125">50% adiciona compartilhamento de aplicativos. Assumimos que um usuário envia dados a um pico de 1,1 MB por segundo.</span><span class="sxs-lookup"><span data-stu-id="c39c6-p125">50% add application sharing. We assume one users sends data at a peak of 1.1 MB per second.</span></span></p></li>
<li><p><span data-ttu-id="c39c6-248">50% adicionam mensagem instantânea (com média de 2 mensagens por usuário).</span><span class="sxs-lookup"><span data-stu-id="c39c6-248">50% add instant messaging (with an average of 2 messages per user).</span></span></p></li>
<li><p><span data-ttu-id="c39c6-p126">20% de colaboração de dados adicionados, incluindo PowerPoint ou quadro de anotações. Nestes, uma média de 2 arquivos 2 PowerPoint apresentados por conferência, com um tamanho de arquivo médio do PowerPoint de 10 MB (sem vídeo integrado) ou 30 MB (com vídeo integrado). Média de 20 anotações por quadro de anotações.</span><span class="sxs-lookup"><span data-stu-id="c39c6-p126">20% add data collaboration, including PowerPoint or whiteboard In these, an average of 2 PowerPoint files presented per conference, with an average PowerPoint file size of 10 MB (without embedded video) or 30 MB (with embedded video). Average of 20 annotations per whiteboard.</span></span></p></li>
<li><p><span data-ttu-id="c39c6-p127">20% de vídeo adicionado. Destes usuários, 70% estão em conferências habilitadas para vídeo multivisualização, onde cada usuário recebe 2-3 fluxos de vídeo.</span><span class="sxs-lookup"><span data-stu-id="c39c6-p127">20% add video. Of these users, 70% are in conferences enabled for multiview video, where each user receives 2-3 video streams.</span></span></p></li>
<li><p><span data-ttu-id="c39c6-253">15% notas compartilhadas adicionadas.</span><span class="sxs-lookup"><span data-stu-id="c39c6-253">15% add shared notes.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c39c6-254">Distribuição dos participantes da reunião</span><span class="sxs-lookup"><span data-stu-id="c39c6-254">Meeting participant distribution</span></span></p></td>
<td><p><span data-ttu-id="c39c6-255">50% de usuários internos autenticados.</span><span class="sxs-lookup"><span data-stu-id="c39c6-255">50% internal, authenticated users.</span></span></p>
<p><span data-ttu-id="c39c6-256">25% de usuários de acesso remoto autenticados.</span><span class="sxs-lookup"><span data-stu-id="c39c6-256">25% remote access, authenticated users.</span></span></p>
<p><span data-ttu-id="c39c6-257">15% de usuários anônimos.</span><span class="sxs-lookup"><span data-stu-id="c39c6-257">15% anonymous users.</span></span></p>
<p><span data-ttu-id="c39c6-258">10% de usuários federados.</span><span class="sxs-lookup"><span data-stu-id="c39c6-258">10% federated users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c39c6-259">Distribuição de ingresso na reunião</span><span class="sxs-lookup"><span data-stu-id="c39c6-259">Meeting join distribution</span></span></p></td>
<td><p><span data-ttu-id="c39c6-260">Os usuários são simulados como participação da reunião dentro dos primeiros 5 minutos.</span><span class="sxs-lookup"><span data-stu-id="c39c6-260">Users are simulated as joining the meeting within the first 5 minutes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c39c6-261">Em pools de front-ends regulares, o Lync Server 2013 tem um tamanho de reunião máximo com suporte de 250 usuários.</span><span class="sxs-lookup"><span data-stu-id="c39c6-261">In regular Front End pools, Lync Server 2013 has a maximum supported meeting size of 250 users.</span></span> <span data-ttu-id="c39c6-262">Cada pool pode hospedar uma reunião de 250 usuários por vez.</span><span class="sxs-lookup"><span data-stu-id="c39c6-262">Each pool can host one 250-user meeting at a time.</span></span> <span data-ttu-id="c39c6-263">Enquanto esta grande reunião está ocorrendo, o pool também pode hospedar outras conferências menores.</span><span class="sxs-lookup"><span data-stu-id="c39c6-263">While this large meeting is occurring, the pool can also host other smaller conferences.</span></span> <span data-ttu-id="c39c6-264">Além disso, é possível suportar reuniões de até 1000 usuários configurando um pool exclusivo para hospedar estas reuniões.</span><span class="sxs-lookup"><span data-stu-id="c39c6-264">Additionally, you can support meetings of up to 1000 users by setting up a dedicated pool to host these meetings.</span></span> <span data-ttu-id="c39c6-265">Para obter detalhes, consulte [suporte para grandes reuniões no Lync Server 2013](lync-server-2013-support-for-large-meetings.md).</span><span class="sxs-lookup"><span data-stu-id="c39c6-265">For details, see [Support for large meetings in Lync Server 2013](lync-server-2013-support-for-large-meetings.md).</span></span>

<span data-ttu-id="c39c6-266">Conferências foram simuladas como a seguir:</span><span class="sxs-lookup"><span data-stu-id="c39c6-266">Conferences were simulated as follows:</span></span>

  - <span data-ttu-id="c39c6-267">85% das conferências tinham quatro participantes.</span><span class="sxs-lookup"><span data-stu-id="c39c6-267">85% of conferences had four participants.</span></span>

  - <span data-ttu-id="c39c6-268">10% das conferências tinham seis participantes.</span><span class="sxs-lookup"><span data-stu-id="c39c6-268">10% of conferences had six participants.</span></span>

  - <span data-ttu-id="c39c6-269">5% das conferências tinham 11 participantes.</span><span class="sxs-lookup"><span data-stu-id="c39c6-269">5% of conferences had 11 participants.</span></span>

  - <span data-ttu-id="c39c6-270">Uma grande conferência de 250 usuários.</span><span class="sxs-lookup"><span data-stu-id="c39c6-270">One large conference of 250 users.</span></span>

<span data-ttu-id="c39c6-271">A tabela a seguir fornece detalhes sobre o modelo de usuário para conferências envolvendo usuários discados.</span><span class="sxs-lookup"><span data-stu-id="c39c6-271">The following table provides details about the user model for conferences involving dial-in users.</span></span>

### <a name="dial-in-conferencing-user-model"></a><span data-ttu-id="c39c6-272">Modelo de usuário de conferência discada</span><span class="sxs-lookup"><span data-stu-id="c39c6-272">Dial-In Conferencing User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c39c6-273">Categoria</span><span class="sxs-lookup"><span data-stu-id="c39c6-273">Category</span></span></th>
<th><span data-ttu-id="c39c6-274">Descrição</span><span class="sxs-lookup"><span data-stu-id="c39c6-274">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c39c6-275">Autenticado/anônimo</span><span class="sxs-lookup"><span data-stu-id="c39c6-275">Authenticated/anonymous</span></span></p></td>
<td><p><span data-ttu-id="c39c6-p129">70% de chamadores participaram como anônimos e foram solicitados por um nome de registro. 30% participaram como usuários autenticados.</span><span class="sxs-lookup"><span data-stu-id="c39c6-p129">70% of callers join as anonymous and are prompted for a recorded name. 30% join as authenticated users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c39c6-278">Duração da chamada e música em espera</span><span class="sxs-lookup"><span data-stu-id="c39c6-278">Call duration and music on hold</span></span></p></td>
<td><p><span data-ttu-id="c39c6-279">A duração média da chamada sem música em espera: 50 segundos.</span><span class="sxs-lookup"><span data-stu-id="c39c6-279">Average call duration without music on hold: 50 seconds.</span></span></p>
<p><span data-ttu-id="c39c6-280">50% dos usuários de chamada recebida ouvem música em espera, durante uma média de 5 minutos.</span><span class="sxs-lookup"><span data-stu-id="c39c6-280">50% of call-in users hear music on hold, for an average of 5 minutes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c39c6-281">DTMF (Dual-tone multifrequency)</span><span class="sxs-lookup"><span data-stu-id="c39c6-281">Dual-tone multifrequency (DTMF)</span></span></p></td>
<td><p><span data-ttu-id="c39c6-p130">15% das conferências somente discadas têm líderes de telefone. 10% das conferências mistas que incluem usuários discados também têm líderes de telefone.</span><span class="sxs-lookup"><span data-stu-id="c39c6-p130">15% of conferences that are dial-in only have phone leaders. 10% of mixed conferences that include dial-in users also have phone leaders.</span></span></p>
<p><span data-ttu-id="c39c6-284">20% dos líderes de telefone usam 2 comandos DTMF por conferência.</span><span class="sxs-lookup"><span data-stu-id="c39c6-284">20% of phone leaders use 2 DTMF commands per conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c39c6-285">Idiomas do anúncio</span><span class="sxs-lookup"><span data-stu-id="c39c6-285">Announcement languages</span></span></p></td>
<td><p><span data-ttu-id="c39c6-286">As simulações usam Inglês como o idioma de anúncio.</span><span class="sxs-lookup"><span data-stu-id="c39c6-286">Simulations use English as the announcement language.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c39c6-287">A tabela a seguir fornece detalhes sobre o modelo de usuário para lobbies de conferência.</span><span class="sxs-lookup"><span data-stu-id="c39c6-287">The following table provides details about the user model for conference lobbies.</span></span>

### <a name="conference-lobby-user-model"></a><span data-ttu-id="c39c6-288">Modelo de usuário de lobby de conferência</span><span class="sxs-lookup"><span data-stu-id="c39c6-288">Conference Lobby User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c39c6-289">Categoria</span><span class="sxs-lookup"><span data-stu-id="c39c6-289">Category</span></span></th>
<th><span data-ttu-id="c39c6-290">Descrição</span><span class="sxs-lookup"><span data-stu-id="c39c6-290">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c39c6-291">Número de usuários no lobby</span><span class="sxs-lookup"><span data-stu-id="c39c6-291">Number of users in lobby</span></span></p></td>
<td><p><span data-ttu-id="c39c6-292">5% dos usuários discados passam pelo lobby e 25% dos outros usuários passam pelo lobby</span><span class="sxs-lookup"><span data-stu-id="c39c6-292">5% of dial-in users go through the lobby, and 25% of other users go through the lobby</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c39c6-293">Admissão a partir do lobby</span><span class="sxs-lookup"><span data-stu-id="c39c6-293">Admitting from lobby</span></span></p></td>
<td><p><span data-ttu-id="c39c6-294">Em simulações, todos os usuários foram admitidos pelo apresentador antes do tempo limite do cliente.</span><span class="sxs-lookup"><span data-stu-id="c39c6-294">In simulations, all users were admitted by the presenter before client timeout.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c39c6-295">A tabela a seguir descreve o modelo de usuário para outras sessões ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="c39c6-295">The following table describes the user model for other peer-to-peer sessions.</span></span>

### <a name="peer-to-peer-sessions-user-model"></a><span data-ttu-id="c39c6-296">Modelo de usuário de sessões ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="c39c6-296">Peer-to-Peer Sessions User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c39c6-297">Categoria</span><span class="sxs-lookup"><span data-stu-id="c39c6-297">Category</span></span></th>
<th><span data-ttu-id="c39c6-298">Descrição</span><span class="sxs-lookup"><span data-stu-id="c39c6-298">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c39c6-299">Compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="c39c6-299">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="c39c6-300">Cada usuário participa de 5 sessões de compartilhamento de aplicativo ponto a ponto por mês, uma média de 0,25 sessões por dia.</span><span class="sxs-lookup"><span data-stu-id="c39c6-300">Each user participates in 5 peer-to-peer application sharing sessions per month, for an average of 0.25 sessions per day.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c39c6-301">Transferência de arquivo</span><span class="sxs-lookup"><span data-stu-id="c39c6-301">File transfer</span></span></p></td>
<td><p><span data-ttu-id="c39c6-p131">Cada usuário participa de uma sessão de transferência de arquivo ponto a ponto por mês (como parte de uma sessão de IM), para uma média de 0,05 sessões por dia. O tamanho de arquivo médio da sessão transferido é de 1 MB.</span><span class="sxs-lookup"><span data-stu-id="c39c6-p131">Each user participates in 1 peer-to-peer file transfer session per month (as part of an IM session), for an average of 0.05 sessions per day. The average session file size transferred is 1 MB.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c39c6-304">A tabela a seguir descreve o modelo de usuário para políticas.</span><span class="sxs-lookup"><span data-stu-id="c39c6-304">The following table describes the user model for policies.</span></span>

### <a name="policies-user-model"></a><span data-ttu-id="c39c6-305">Políticas de Modelo do Usuário</span><span class="sxs-lookup"><span data-stu-id="c39c6-305">Policies User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c39c6-306">Categoria</span><span class="sxs-lookup"><span data-stu-id="c39c6-306">Category</span></span></th>
<th><span data-ttu-id="c39c6-307">Descrição</span><span class="sxs-lookup"><span data-stu-id="c39c6-307">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c39c6-308">Políticas de Arquiamento, Presença e Conferência</span><span class="sxs-lookup"><span data-stu-id="c39c6-308">Conferencing, Presence, and Archiving Policies</span></span></p></td>
<td><p><span data-ttu-id="c39c6-309">Assumimos que há uma política global, 10 políticas de conferência de marcação, 4 políticas de Arquivamento e 10 políticas de presença de tag.</span><span class="sxs-lookup"><span data-stu-id="c39c6-309">We assume that there is one global policy, 10 tag conferencing policies, 4 Archiving policies, and 10 tag presence policies.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c39c6-310">Política de voz</span><span class="sxs-lookup"><span data-stu-id="c39c6-310">Voice Policy</span></span></p></td>
<td><p><span data-ttu-id="c39c6-311">Assumimos que há uma política global e 2 políticas de tag por local.</span><span class="sxs-lookup"><span data-stu-id="c39c6-311">We assume that there is one global policy and 2 tag policies per site.</span></span> <span data-ttu-id="c39c6-312">100% dos locais possuem uma política local e 30% dos usuários possuem uma política por usuário atribuída.</span><span class="sxs-lookup"><span data-stu-id="c39c6-312">100% of sites have a site policy, and 30% of users have a per-user policy assigned.</span></span> <span data-ttu-id="c39c6-313">Assumimos um plano de discagem por local e duas rotas por local.</span><span class="sxs-lookup"><span data-stu-id="c39c6-313">We assume one dial plan per site and two routes per site.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="busy-hour"></a><span data-ttu-id="c39c6-314">Horário de pico</span><span class="sxs-lookup"><span data-stu-id="c39c6-314">Busy Hour</span></span>

<span data-ttu-id="c39c6-p133">Para sessões ponto a ponto, a carga durante o pico é calculada usando tentativas de chamada no horário de pico (BHCA). Esse termo do setor de voz supõe que 50% de todas as chamadas para esse dia serão completadas em 20% do tempo. Isso é calculado usando a seguinte fórmula:</span><span class="sxs-lookup"><span data-stu-id="c39c6-p133">For peer-to-peer sessions, peak load is calculated using busy hour call attempts (BHCA). This voice industry term assumes that 50% of all calls for the day will be completed in 20% of the time. It is calculated using the following formula:</span></span>

`BHCA=(total calls * 0.5) / 1.6`

<span data-ttu-id="c39c6-318">O teste de desempenho simulou o horário de pico executando sessões VoIP e outras sessões ponto a ponto com uma carga de hora de pico durante pelo menos 1,6 hora por dia.</span><span class="sxs-lookup"><span data-stu-id="c39c6-318">Performance testing simulated busy hour by running VoIP and other peer-to-peer sessions at a busy hour load for at least 1.6 hours per day.</span></span>

<span data-ttu-id="c39c6-p134">A carga de pico de conferência supõe que 75% de todas as conferências para um dia de oito horas ocorre em 4 horários de pico. Esses horários de pico têm 1,5 vezes a carga média de conferência.</span><span class="sxs-lookup"><span data-stu-id="c39c6-p134">Conferencing peak load assumes that 75% of all conferences for an eight-hour day happen in 4 peak time hours. Those peak hours have 1.5 times the average conferencing load.</span></span>

</div>

<div>

## <a name="enterprise-voice-to-pstn-calls"></a><span data-ttu-id="c39c6-321">Chamadas do Enterprise Voice para PSTN</span><span class="sxs-lookup"><span data-stu-id="c39c6-321">Enterprise Voice to PSTN Calls</span></span>

<span data-ttu-id="c39c6-322">As seguintes pressuposições se aplicam às chamadas do Enterprise Voice:</span><span class="sxs-lookup"><span data-stu-id="c39c6-322">The following assumptions apply to Enterprise Voice calls:</span></span>

  - <span data-ttu-id="c39c6-323">50% dos usuários estão habilitados para o Enterprise Voice e 60% desses usuários estão habilitados para chamada PSTN.</span><span class="sxs-lookup"><span data-stu-id="c39c6-323">50% of users are enabled for Enterprise Voice, and 60% of these users are enabled for PSTN calling.</span></span>

  - <span data-ttu-id="c39c6-p135">Cada um destes usuários habilitados para chamada PSTN faz 4 chamadas PSTN durante a hora ocupada. Cada duração de chamada é de 3 minutos.</span><span class="sxs-lookup"><span data-stu-id="c39c6-p135">Each of these users enabled for PSTN calling makes 4 PSTN calls during the busy hour. Each call duration is 3 minutes.</span></span>

  - <span data-ttu-id="c39c6-326">65% destas chamadas de voz PSTN usam bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="c39c6-326">65% of these PSTN voice calls use media bypass.</span></span>

</div>

<div>

## <a name="mobility"></a><span data-ttu-id="c39c6-327">Movimentação</span><span class="sxs-lookup"><span data-stu-id="c39c6-327">Mobility</span></span>

<span data-ttu-id="c39c6-p136">40% dos usuários registrados são assumidos como habilitados para Mobilidade. Para cada usuário que possui habilidade habilitado, assumimos que a atividade do cliente móvel é aditivo àquelas de outras instâncias MPOP deste usuário, com exceção das interações de conferência, para as quais o cliente de mobilidade é apenas outro tipo de cliente que pode ser usado para participar de conferências.</span><span class="sxs-lookup"><span data-stu-id="c39c6-p136">40% of registered users are assumed to be enabled for Mobility. For each user that has mobility enabled, we assume that the activity of the mobile client is additive to that of the other MPOP instances for that user, with the exception of conferencing interactions, for which the mobility client is just another client type that can be used to participate in conferences.</span></span>

</div>

<div>

## <a name="persistent-chat"></a><span data-ttu-id="c39c6-330">Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="c39c6-330">Persistent Chat</span></span>

<span data-ttu-id="c39c6-331">Assumimos que 25% dos usuários registrados sejam envolvidos em sessões de chat Persistente, com as seguintes características:</span><span class="sxs-lookup"><span data-stu-id="c39c6-331">We assume that 25% of registered users will be involved in Persistent chat sessions, with the following characteristics:</span></span>

  - <span data-ttu-id="c39c6-332">Uma média de 1,5 salas de bate-papo por usuário</span><span class="sxs-lookup"><span data-stu-id="c39c6-332">An average of 1.5 chat rooms per user</span></span>

  - <span data-ttu-id="c39c6-333">Cada sala de bate-papo resulta em 12 solicitações de pool por hora, indicando uma média de 10 usuários cada</span><span class="sxs-lookup"><span data-stu-id="c39c6-333">Each chat room results in 12 polling requests per hour, targeting an average of 10 users each</span></span>

</div>

<div>

## <a name="response-group-and-call-park"></a><span data-ttu-id="c39c6-334">Grupo de Resposta e Estacionamento de Chamadas</span><span class="sxs-lookup"><span data-stu-id="c39c6-334">Response Group and Call Park</span></span>

<span data-ttu-id="c39c6-p137">Assumimos que 0,15% dos usuários registrados pertencem aos grupos de resposta. Assumimos que 0,02% dos usuários registrados possuem chamadas estacionadas em um determinado ponto do tempo.</span><span class="sxs-lookup"><span data-stu-id="c39c6-p137">We assume that 0.15% of registered users belong to response groups. We assume that 0.02% of registered users have parked calls at any given point of time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

