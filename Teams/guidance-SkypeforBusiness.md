---
title: Habilitar o Microsoft Teams paralelamente ao Skype for Business
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: Um guia para usar o Skype for Business e o Microsoft Teams lado a lado.
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 8e4c93d3b33a6b1fa5322bd8a18ff193f8eaa93a
ms.sourcegitcommit: 9756856140ea56a94e986c134c5c04e53e5c0fa6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2017
---
<a name="enable-microsoft-teams-side-by-side-with-skype-for-business"></a><span data-ttu-id="f7a28-103">Habilitar o Microsoft Teams paralelamente ao Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f7a28-103">Enable Microsoft Teams side-by-side with Skype for Business</span></span> 
=============================================================

<span data-ttu-id="f7a28-104">Para organizações com implantações existentes do Skype for Business Online, a recente introdução do Microsoft Teams representa uma oportunidade de avaliar o potencial do Teams como uma solução única de comunicação e colaboração, um desafio para equilibrar a balança entre as duas soluções e como elas podem coexistir no seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="f7a28-104">For organizations with existing deployments of Skype for Business Online, the recent introduction of Microsoft Teams presents an opportunity to evaluate the potential of Teams as a sole, communications and collaboration solution, and a challenge to tip the scale between the two solutions and how they can coexist in your environment.</span></span>

<span data-ttu-id="f7a28-105">Se o Teams não conseguir atender suas exigências comerciais hoje, você pode começar a adotar o Teams para se tornar a solução única de comunicação e colaboração na sua organização.</span><span class="sxs-lookup"><span data-stu-id="f7a28-105">If Teams can meet your business requirements today, you can start adopting Teams to become your single communications and collaboration solution for your organization.</span></span>

<span data-ttu-id="f7a28-106">O Teams está habilitado por padrão em todos os locatários elegíveis.</span><span class="sxs-lookup"><span data-stu-id="f7a28-106">Teams is enabled by default, on all eligible tenants.</span></span> <span data-ttu-id="f7a28-107">Portanto, você precisa decidir como gerenciar o Teams lado a lado com o Skype for Business e continuar a atender às expectativas dos usuários.</span><span class="sxs-lookup"><span data-stu-id="f7a28-107">Therefore, you need to decide on how to manage Teams side-by-side with Skype for Business, and continue to meet user expectations.</span></span>

<span data-ttu-id="f7a28-108">De forma geral, existem duas grandes jornadas do cliente lado a lado.</span><span class="sxs-lookup"><span data-stu-id="f7a28-108">In general, there are two major side-by-side customer journeys.</span></span> <span data-ttu-id="f7a28-109">São elas:</span><span class="sxs-lookup"><span data-stu-id="f7a28-109">They are:</span></span>

-   <span data-ttu-id="f7a28-110">**Opção 1:** Jornada do cliente lado a lado não gerenciada.</span><span class="sxs-lookup"><span data-stu-id="f7a28-110">**Option 1:** Unmanaged side-by-side customer journey.</span></span>

    <span data-ttu-id="f7a28-111">A TI não controla ativamente a experiência lado a lado, e os usuários podem decidir pelo aplicativo de sua preferência.</span><span class="sxs-lookup"><span data-stu-id="f7a28-111">IT does not actively control the side-by-side experience, and users are empowered to make the choice of preferred app.</span></span>

-   <span data-ttu-id="f7a28-112">**Opção 2:** Jornada do cliente lado a lado gerenciada.</span><span class="sxs-lookup"><span data-stu-id="f7a28-112">**Option 2:** Managed side-by-side customer journey.</span></span>

    <span data-ttu-id="f7a28-113">A TI controla a experiência do lado a lado, levando os usuários por uma jornada de introdução gradual do Teams para primeiro, introduzir um novo espaço de trabalho de colaboração baseado em bate-papo com bate-papo privado, depois experiências de reunião e, por fim, as experiências de chamada do Teams.</span><span class="sxs-lookup"><span data-stu-id="f7a28-113">IT controls the side-by-side experience, taking users through a journey of gradually introducing Teams to first introduce a new chat-based collaboration workspace with private chat, then meeting experiences, and finally the calling experiences in Teams.</span></span>

![Diagrama de duas jornadas do cliente lado a lado: Gerenciada e não gerenciada.](media/guidance_SkypeforBusiness_image1.png)

<a name="side-by-side-benefits-and-considerations"></a><span data-ttu-id="f7a28-115">Benefícios e considerações do lado-a-lado</span><span class="sxs-lookup"><span data-stu-id="f7a28-115">Side-by-side benefits and considerations</span></span>
----------------------------------------

<span data-ttu-id="f7a28-116">Cada uma das jornadas tem benefícios e considerações a serem avaliados para determinar o caminho certo com base no perfil da sua organização.</span><span class="sxs-lookup"><span data-stu-id="f7a28-116">Each journey has benefits and considerations to evaluate when determining the right path forward based on your organization's profile.</span></span> <span data-ttu-id="f7a28-117">A tabela abaixo mostra a comparação entre as jornadas de cliente lado a lado gerenciadas e não gerenciadas.</span><span class="sxs-lookup"><span data-stu-id="f7a28-117">The table below provides the comparisons between managed and unmanaged side-by-side customer journeys.</span></span>


<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f7a28-118">Caminhos de migração</span><span class="sxs-lookup"><span data-stu-id="f7a28-118">Migration Paths</span></span></th>
<th align="left"><span data-ttu-id="f7a28-119">Lado a lado sem gerenciamento</span><span class="sxs-lookup"><span data-stu-id="f7a28-119">Unmanaged Side-by-Side</span></span></th>
<th align="left"><span data-ttu-id="f7a28-120">Lado a lado com gerenciamento</span><span class="sxs-lookup"><span data-stu-id="f7a28-120">Managed Side-by-Side</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="f7a28-121"><strong>Perfil da organização</strong></span><span class="sxs-lookup"><span data-stu-id="f7a28-121"><strong>Organization profile</strong></span></span></td>
<td align="left"><ul>
<li><span data-ttu-id="f7a28-122">Normalmente, empresas menores sem recursos exclusivos de TI</span><span class="sxs-lookup"><span data-stu-id="f7a28-122">Typically, smaller organizations with no dedicated IT resources</span></span></li>
<li><span data-ttu-id="f7a28-123">A TI permite que o usuário escolha as ferramentas corretas para o seu trabalho a seu exclusivo critério</span><span class="sxs-lookup"><span data-stu-id="f7a28-123">IT allows user discretion in selecting right tools for their work</span></span></li>
<li><span data-ttu-id="f7a28-124">O uso primário do Skype for Business é IM/P e reuniões</span><span class="sxs-lookup"><span data-stu-id="f7a28-124">Primary Skype for Business usage is IM/P and meetings</span></span></li>
</ul></td>
<td align="left"><ul><li><span data-ttu-id="f7a28-125">Normalmente, empresas maiores, de porte médio</span><span class="sxs-lookup"><span data-stu-id="f7a28-125">Typically, mid-size to larger organizations</span></span></li>
<li><span data-ttu-id="f7a28-126">A TI deseja controlar mais rigorosamente a distribuição de novas ferramentas</span><span class="sxs-lookup"><span data-stu-id="f7a28-126">IT wants to control roll out of new tools more rigorously</span></span></li>
<li><span data-ttu-id="f7a28-127">Adoção mais profunda do Skype for Business hoje</span><span class="sxs-lookup"><span data-stu-id="f7a28-127">Deeper adoption of Skype for Business today</span></span></li>
<li><span data-ttu-id="f7a28-128">Maior complexidade de rede e infraestrutura</span><span class="sxs-lookup"><span data-stu-id="f7a28-128">Increased complexity in network and infrastructure</span></span></li>
<li><span data-ttu-id="f7a28-129">Várias localidades</span><span class="sxs-lookup"><span data-stu-id="f7a28-129">Multiple locations</span></span></p>
<li><span data-ttu-id="f7a28-130">Preferência por um aplicativo único, com recursos exclusivos de UC</span><span class="sxs-lookup"><span data-stu-id="f7a28-130">Preference for single app with unique UC capabilities</span></span></li></ul></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="f7a28-131"><strong>Benefícios</strong></span><span class="sxs-lookup"><span data-stu-id="f7a28-131"><strong>Benefits</strong></span></span></td>
<td align="left"><ul>
<li><span data-ttu-id="f7a28-132">Aproveitar os recursos do Teams que não estão disponíveis no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f7a28-132">Leverage capabilities in Teams that are not available in Skype for Business</span></span></li>
<li><span data-ttu-id="f7a28-133">Local de trabalho moderno e aprimorado no Office 365</span><span class="sxs-lookup"><span data-stu-id="f7a28-133">Enhanced modern workplace within Office 365</span></span></li>
<li><span data-ttu-id="f7a28-134">Mais flexibilidade para o usuário</span><span class="sxs-lookup"><span data-stu-id="f7a28-134">Increased user flexibility</span></span></li>
<li><span data-ttu-id="f7a28-135">Ativação de todos os recursos ao mesmo tempo</span><span class="sxs-lookup"><span data-stu-id="f7a28-135">Enable all capabilities at once</span></span></li>
</ul></td>
<td align="left"><ul><li><span data-ttu-id="f7a28-136">Aproveitar os recursos do Teams que não estão disponíveis no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f7a28-136">Leverage capabilities in Teams that are not available in Skype for Business</span></span></li>
<li><span data-ttu-id="f7a28-137">Local de trabalho moderno e aprimorado no Office 365</span><span class="sxs-lookup"><span data-stu-id="f7a28-137">Enhanced modern workplace within Office 365</span></span></li>
<li><span data-ttu-id="f7a28-138">Minimizar o impacto de produtividade do usuário</span><span class="sxs-lookup"><span data-stu-id="f7a28-138">Minimize user productivity impact</span></span></li>
<li><span data-ttu-id="f7a28-139">Reduzir a sobreposição de recursos</span><span class="sxs-lookup"><span data-stu-id="f7a28-139">Reduce capability overlap</span></span></li>
<li><span data-ttu-id="f7a28-140">Racionalizar a escolha da ferramenta para cenários UC</span><span class="sxs-lookup"><span data-stu-id="f7a28-140">Streamline tool choice for UC scenarios</span></span></li>
<li><span data-ttu-id="f7a28-141">Capacitar TI e a empresa para habilitar recursos conforme for apropriado na organização</span><span class="sxs-lookup"><span data-stu-id="f7a28-141">Empower IT and business to enable capabilities as appropriate in organization</span></span></li>
<li><span data-ttu-id="f7a28-142">Controlar o ritmo de mudança para os usuários</span><span class="sxs-lookup"><span data-stu-id="f7a28-142">Control the pace of change for users</span></span></li></ul></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="f7a28-143"><strong>Considerações</strong></span><span class="sxs-lookup"><span data-stu-id="f7a28-143"><strong>Considerations</strong></span></span></td>
<td align="left"><ul>
<li><span data-ttu-id="f7a28-144">Vários aplicativos com recursos semelhantes que se sobrepõem</span><span class="sxs-lookup"><span data-stu-id="f7a28-144">Multiple apps with similar, overlapping capabilities</span></span></li>
<li><span data-ttu-id="f7a28-145">Maior probabilidade de confusão para os usuários, o que pode aumentar os chamados de suporte, prejudicar a TI, impactar a produtividade</span><span class="sxs-lookup"><span data-stu-id="f7a28-145">Increased potential for user confusion which can lead to increased support calls, shadow IT, impacted productivity</span></span></li>
<li><span data-ttu-id="f7a28-146">O planejamento e monitoramento de rede devem levar em consideração o uso de dois serviços</span><span class="sxs-lookup"><span data-stu-id="f7a28-146">Network planning and monitoring must take usage of two services into consideration</span></span></li>
<li><span data-ttu-id="f7a28-147">Necessidade de um empenho maior e imediato de gerenciamento de mudanças: conscientização, treinamento e suporte</span><span class="sxs-lookup"><span data-stu-id="f7a28-147">Increased and immediate change management efforts required: awareness, training, and support</span></span></li>
<li><span data-ttu-id="f7a28-148">Os usuários podem se defrontar com limitações de interoperabilidade entre os aplicativos</span><span class="sxs-lookup"><span data-stu-id="f7a28-148">Users may experience interoperability limitations between apps</span></span></li>
</ul></td>
<td align="left"><ul><li><span data-ttu-id="f7a28-149">A TI tem um controle mais detalhado, desde as licenças até a experiência dos usuários, exigindo ciclos adicionais de planejamento e implementação</span><span class="sxs-lookup"><span data-stu-id="f7a28-149">IT has granular control, from licensing to user experiences, requiring additional cycles of planning and implementation</span></span></li>
<li><span data-ttu-id="f7a28-150">Necessidade de formação e ação do usuário para desativar os recursos selecionados no Teams</span><span class="sxs-lookup"><span data-stu-id="f7a28-150">User education and action required to disable select capabilities in Teams</span></span></li>
<li><span data-ttu-id="f7a28-151">Necessidade de esforços de gerenciamento mudanças para desativar os recursos selecionados no Teams</span><span class="sxs-lookup"><span data-stu-id="f7a28-151">Change management efforts required to disable select capabilities in Teams</span></span></li>
<li><span data-ttu-id="f7a28-152">O planejamento e monitoramento de rede devem levar em consideração o uso de dois serviços</span><span class="sxs-lookup"><span data-stu-id="f7a28-152">Network planning and monitoring must take usage of two services into consideration</span></span></li>
<li><span data-ttu-id="f7a28-153">Os usuários podem se defrontar com limitações de interoperabilidade entre os aplicativos</span><span class="sxs-lookup"><span data-stu-id="f7a28-153">Users may experience interoperability limitations between apps</span></span></li></ul></td>
</tr>
</tbody>
</table>


<a name="unmanaged-side-by-side-customer-journey"></a><span data-ttu-id="f7a28-154">Jornada do cliente lado a lado não gerenciada</span><span class="sxs-lookup"><span data-stu-id="f7a28-154">Unmanaged side-by-side customer journey</span></span>
---------------------------------------


![Diagrama da jornada do cliente lado a lado não gerenciada.](media/guidance_SkypeforBusiness_image4.png)

<span data-ttu-id="f7a28-156">Em uma jornada do cliente lado a lado não gerenciada, o Teams é introduzido como uma solução de colaboração (espaço de trabalho baseado em bate-papo, canais, aplicativos, integração com outras cargas de trabalho do Office 365, etc.) que envolve software cliente e cliente web em computadores desktop (PC ou Mac) e em dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="f7a28-156">In an unmanaged side-by-side customer journey, Teams is introduced as a collaboration solution (chat-based workspace, channels, apps, integration with other Office 365 workloads, etc.) that involves client software and web client on desktop computers (PC or Mac) and mobile devices.</span></span>


<span data-ttu-id="f7a28-157">Por padrão, o Teams também apresenta recursos que se sobrepõem com o Skype for Business, como bate-papo e chamadas privadas e reuniões agendadas.</span><span class="sxs-lookup"><span data-stu-id="f7a28-157">By default, Teams also presents overlapping capabilities with Skype for Business, these include private chat and calling, and scheduled meetings.</span></span> <span data-ttu-id="f7a28-158">Isso significa que o Teams acaba oferecendo comunicação e colaboração completa para a organização, enquanto, ao mesmo tempo, o Skype for Business oferece recursos semelhantes.</span><span class="sxs-lookup"><span data-stu-id="f7a28-158">This means Teams ends up providing complete communications and collaboration for the organization, while at the same time Skype for Business provides similar capabilities.</span></span>

<span data-ttu-id="f7a28-159">O Teams suporta interoperabilidade com os usuários do Skype for Business Online e os usuários terão a oportunidade de escolher o aplicativo de bate-papo e chamada de sua preferência quando o Teams for lançado.</span><span class="sxs-lookup"><span data-stu-id="f7a28-159">Teams supports interoperability with Skype for Business Online users, and users will be given an opportunity to choose their preferred chat and calling app when they launch Teams.</span></span> <span data-ttu-id="f7a28-160">Se um usuário escolher o Teams como o aplicativo de sua preferência e outro usuário não tiver instalado o Teams ou tiver escolhido o Skype for Business como o aplicativo de bate-papo e chamada de sua preferência, eles podem continuar conversando e fazendo chamadas entre si através dos recursos de interoperabilidade que fazem parte do Teams.</span><span class="sxs-lookup"><span data-stu-id="f7a28-160">If one user picks Teams as the preferred app, and another user hasn’t installed Teams or picked Skype for Business as the preferred chat and calling app, they can continue to chat and call each other through the interop capabilities that are part of Teams.</span></span>

<span data-ttu-id="f7a28-161">A Microsoft está aprimorando continuamente as experiências de interoperabilidade.</span><span class="sxs-lookup"><span data-stu-id="f7a28-161">Microsoft is continuously improving the interop experiences.</span></span> <span data-ttu-id="f7a28-162">No início, poderá haver alguns casos em que as experiências de interoperabilidade não atendam às expectativas dos usuários.</span><span class="sxs-lookup"><span data-stu-id="f7a28-162">In the beginning, there may be some cases whereby the interop experiences are not meeting user expectations.</span></span> <span data-ttu-id="f7a28-163">Como o Skype for Business ainda está disponível para os usuários, eles podem mudar para o Skype for Business para os recursos que no momento não podem ser atendidos pelo Teams.</span><span class="sxs-lookup"><span data-stu-id="f7a28-163">Since Skype for Business is still available to users, they can switch to Skype for Business for the capabilities that currently cannot be served by Teams.</span></span>

<span data-ttu-id="f7a28-164">A reuniões agendadas do Teams é outro recurso de sobreposição que permite que os usuários agendem reuniões via Teams ou Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="f7a28-164">Scheduled meetings in Teams is another overlapping capability that lets users schedule Teams meetings, or Skype for Business meetings.</span></span> <span data-ttu-id="f7a28-165">Cada um tem suas próprias vantagens e, com o passar do tempo, quando a experiência de reunião do Teams atender aos requisitos da empresa ou superar as funcionalidades das reuniões Skype for Business, é esperado que os usuários troquem naturalmente para reuniões Teams.</span><span class="sxs-lookup"><span data-stu-id="f7a28-165">Each has its own advantages, and over time, when Teams meeting experience meets business requirements or surpasses the functionalities of Skype for Business meetings, we expect users to naturally switch to Teams meetings.</span></span>

<span data-ttu-id="f7a28-166">Nesta jornada do cliente lado a lado não gerenciada, prepare sua equipe de assistência técnica para lidar com chamados de suporte dos usuários quando estiverem enfrentando problemas com os recursos de interoperabilidade.</span><span class="sxs-lookup"><span data-stu-id="f7a28-166">In this unmanaged side-by-side customer journey, prepare your helpdesk team to handle support calls from users when facing issues with interop capabilities.</span></span> <span data-ttu-id="f7a28-167">Ou aconselhe os usuários a escolherem as reuniões Teams em vez de reuniões Skype for Business e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="f7a28-167">Or advise users when to choose Teams meetings over Skype for Business meetings, and vice versa.</span></span>

<span data-ttu-id="f7a28-168">Esta jornada do cliente lado a lado pode ser aplicável à sua organização se os usuários estiverem mais receptivos à natureza da experiência lado a lado sem gerenciamento, e a organização permitir abertamente que os usuários escolham as melhores ferramentas de comunicação e colaboração para atender aos seus requisitos.</span><span class="sxs-lookup"><span data-stu-id="f7a28-168">This side-by-side customer journey may be applicable to your organization, whereby the users are more receptive to the nature of the unmanaged side-by-side experience, and the organization openly allows the users to pick the best communications and collaboration tools that suit their requirements.</span></span>

<a name="managed-side-by-side-customer-journey"></a><span data-ttu-id="f7a28-169">Jornada do cliente lado a lado gerenciada</span><span class="sxs-lookup"><span data-stu-id="f7a28-169">Managed side-by-side customer journey</span></span>
-------------------------------------

![Diagrama da jornada do cliente lado a lado gerenciada.](media/guidance_SkypeforBusiness_image2.png)

<span data-ttu-id="f7a28-171">Uma jornada do cliente lado a lado gerenciada começa quando a organização deseja ter mais controle de como o Teams será introduzido.</span><span class="sxs-lookup"><span data-stu-id="f7a28-171">A managed side-by-side customer journey starts with organization wanting more control over how Teams is introduced.</span></span>

-   <span data-ttu-id="f7a28-172">O **primeiro passo** dessa jornada é um piloto limitado do Teams com o escopo em exigências modernas de colaboração (espaço de trabalho baseado em bate-papo, canais, aplicativos, integração com outras cargas de trabalho do Office 365, etc.).</span><span class="sxs-lookup"><span data-stu-id="f7a28-172">The **first step** of this journey is a limited pilot of Teams scoped to modern collaboration requirements (chat-based workspace, channels, apps, integration with other Office 365 workloads, etc.).</span></span> <span data-ttu-id="f7a28-173">As reuniões de canais ad hoc e o bate-papo privado no Teams também estão habilitados para dar uma oportunidade aos usuários pilotos avaliarem a experiência de reuniões Teams e as experiências de bate-papo privado.</span><span class="sxs-lookup"><span data-stu-id="f7a28-173">Ad-hoc channel meetings and private chat in Teams is also enabled to provide a chance for pilot users to evaluate the Teams meetings experience and private chat experiences.</span></span> <span data-ttu-id="f7a28-174">Os recursos de reuniões agendadas e chamadas privadas do Teams estão desativados nesta fase.</span><span class="sxs-lookup"><span data-stu-id="f7a28-174">Scheduled meetings and private calling capabilities in Teams are disabled at this stage.</span></span> <span data-ttu-id="f7a28-175">Para iniciar um piloto, vá para [Piloto do Teams com o Skype for Business](pilot-essentials.md).</span><span class="sxs-lookup"><span data-stu-id="f7a28-175">To get started with a pilot, go to [Pilot Teams with Skype for Business](pilot-essentials.md).</span></span>
    
-   <span data-ttu-id="f7a28-176">O **segundo passo** dessa jornada é ampliar a distribuição do Teams para uma colaboração moderna com o bate-papo privado por toda a organização.</span><span class="sxs-lookup"><span data-stu-id="f7a28-176">The **second step** of this journey is extending the rollout of Teams for modern collaboration with private chat throughout the organization.</span></span> <span data-ttu-id="f7a28-177">As reuniões agendadas e as chamadas privadas permanecem desativadas no Teams para reduzir o tempo de sobreposição com os recursos do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="f7a28-177">Scheduled meetings, and private calling continue to be disabled in Teams to reduce the overlap  with with Skype for Business capabilities.</span></span>

    <span data-ttu-id="f7a28-178">Nessa fase, talvez seja necessário considerar se o aplicativo de bate-papo de preferência deve ser definido como o do Teams ou do Skype for Business para toda a organização.</span><span class="sxs-lookup"><span data-stu-id="f7a28-178">At this stage, you may need to consider whether preferred chat application should be set to Teams or Skype for Business for the entire organization.</span></span>

    - <span data-ttu-id="f7a28-179">Se for definido para o Teams, prepare seus usuários para lidar com os primeiros desafios de interoperabilidade quando se comunicarem com outras pessoas dentro de toda a organização.</span><span class="sxs-lookup"><span data-stu-id="f7a28-179">If set to Teams, prepare your users to handle early interoperability challenges when communicating with other parties within and across the organization.</span></span>
    
    - <span data-ttu-id="f7a28-180">Se for definido para o Skype for Business, os bate-papos privados dentro do Teams permanecerão no Teams e os usuários finais poderão tirar proveito imediato da natureza persistente da plataforma cruzada dos recursos de bate-papo do Teams e continuarão a usar o Skype for Business para bate-papos privados no Skype for Business dentro de toda a organização.</span><span class="sxs-lookup"><span data-stu-id="f7a28-180">If set to Skype for Business, private chats within Teams will remain in Teams, and end users can immediately take advantage of the cross-platform persistent nature of chat capabilities within Teams, and they will continue to use Skype for Business for private chats among Skype for Business users, within the organization and across the organization.</span></span>


<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p><span data-ttu-id="f7a28-181">Nota</span><span class="sxs-lookup"><span data-stu-id="f7a28-181">Note</span></span></p></td>
<td align="left"><br><br><span data-ttu-id="f7a28-182">No momento, a definição do aplicativo de bate-papo de preferência está disponível apenas no nível de cliente.</span><span class="sxs-lookup"><span data-stu-id="f7a28-182">Currently the preferred chat application setting is available only at the client level.</span></span> <span data-ttu-id="f7a28-183">O treinamento de usuários e a campanha de adoção serão necessários para conduzir a configuração pretendida em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="f7a28-183">User training and adoption campaign will be required to drive the intended organization-wide configuration.</span></span></td>
</tr>
</thead>
<tbody>
</tbody>
</table>

<span data-ttu-id="f7a28-184">O **terceiro passo** da jornada do cliente lado a lado gerenciada começa quando a organização decidir que os recursos e a experiência de reunião do Teams atende aos requisitos da empresa.</span><span class="sxs-lookup"><span data-stu-id="f7a28-184">The **third step** of the managed side-by-side customer journey starts when the organization decides that Teams meeting experience and capabilities meet their business requirements.</span></span> <span data-ttu-id="f7a28-185">Ao habilitar as reuniões privadas e reuniões de canal no Teams, os usuários recebem opções para agendar as reuniões Teams e as reuniões Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="f7a28-185">By enabling private and channel meetings in Teams, users are presented with options to schedule both Teams meetings and Skype for Business meetings.</span></span> <span data-ttu-id="f7a28-186">Portanto, espera-se que, ao longo do tempo, os usuários mudem naturalmente para reuniões Teams, tendo em vista as constantes inovações do Teams.</span><span class="sxs-lookup"><span data-stu-id="f7a28-186">Therefore, it is expected that over time users will naturally switch to Teams meetings given the continued innovations in Teams.</span></span> <span data-ttu-id="f7a28-187">Para ter sucesso ao direcionar o uso do Skype for Business para o Teams, implemente um programa robusto de gerenciamento de mudanças, incluindo treinamentos, suporte e comunicações que expliquem o valor agregado que o Teams oferece aos usuários, com uma orientação clara de como começar com o Teams.</span><span class="sxs-lookup"><span data-stu-id="f7a28-187">To be successful in steering usage from Skype for Business to Teams, implement a robust change management program inclusive of training, support and communications that explains the value-add that Teams offers to the user, with clear guidance on how to get started with Teams.</span></span> <span data-ttu-id="f7a28-188">Aproveite nossos recursos de [Prontidão do usuário](http://aka.ms/UserReadiness) para ajudar a projetar sua campanha de conscientização.</span><span class="sxs-lookup"><span data-stu-id="f7a28-188">Leverage our [User Readiness](http://aka.ms/UserReadiness) resources to help design your awareness campaign.</span></span>


<span data-ttu-id="f7a28-189">O **quarto passo** da jornada do cliente lado a lado gerenciada começa com a habilitação de chamadas no Teams.</span><span class="sxs-lookup"><span data-stu-id="f7a28-189">The **fourth step** of the managed side-by-side customer journey begins with enabling calling in Teams.</span></span> <span data-ttu-id="f7a28-190">Os recursos de interoperabilidade do Teams serão bem característicos nesta etapa para garantir uma experiência lado a lado descomplicada.</span><span class="sxs-lookup"><span data-stu-id="f7a28-190">Teams interoperability capabilities will feature heavily in this step to ensure a seamless side-by-side experience.</span></span> <span data-ttu-id="f7a28-191">De forma ideal, para aplicar o uso do Teams para chamadas privadas, o Teams deve ser definido como o aplicativo de chamada padrão.</span><span class="sxs-lookup"><span data-stu-id="f7a28-191">Ideally, to enforce the use of Teams for private calling, Teams is set as the default calling app.</span></span> 

<span data-ttu-id="f7a28-192">Com o passar do tempo, a organização toda pode utilizar somente o Teams para atender às exigências de comunicação e colaboração, e então partir para o **quinto passo**.</span><span class="sxs-lookup"><span data-stu-id="f7a28-192">Over time, potentially the whole organization can rely solely on Teams to meet communications and collaboration requirements and take the **fifth step**.</span></span> <span data-ttu-id="f7a28-193">Para ver quando novos recursos serão implementados no Teams, consulte o [Mapa do Office 365](http://aka.ms/TeamsRoadmap).</span><span class="sxs-lookup"><span data-stu-id="f7a28-193">To see when new features are coming in Teams, see the [Office 365 Roadmap](http://aka.ms/TeamsRoadmap).</span></span> 

<a name="managing-side-by-side-experience"></a><span data-ttu-id="f7a28-194">Gerenciamento da experiência lado a lado</span><span class="sxs-lookup"><span data-stu-id="f7a28-194">Managing side-by-side experience</span></span>
--------------------------------

<span data-ttu-id="f7a28-195">Por padrão, o Microsoft Teams está habilitado para organizações com assinaturas elegíveis do Office 365.</span><span class="sxs-lookup"><span data-stu-id="f7a28-195">By default, for organizations with eligible Office 365 subscriptions, Microsoft Teams is enabled.</span></span> <span data-ttu-id="f7a28-196">Se a sua organização se encaixa no perfil para a jornada do cliente lado a lado não gerenciada, recomendamos fortemente que você mantenha tudo como está para promover uma adoção orgânica do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f7a28-196">If your organization fits the profile for unmanaged side-by-side customer journey, we highly recommend you keep it as-is to foster organic adoption of Microsoft Teams.</span></span>

<span data-ttu-id="f7a28-197">O Teams pode ser acessado por clientes móveis e por clientes desktop de navegador da web modernos que não precisem de privilégios administrativos de TI (para instalação, aplicável atualmente somente ara PC).</span><span class="sxs-lookup"><span data-stu-id="f7a28-197">Teams is accessible via modern Web browser desktop clients which require no IT administrative privilege (for installation, currently applicable to PC only) and mobile clients.</span></span>

<span data-ttu-id="f7a28-198">Todos os recursos do Teams, de bate-papo e chamada privada, reuniões ad-hoc e agendadas e até mesmo aplicativos estão habilitados por padrão, permitindo que os usuários experimentem e utilizem os recursos que atendam às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="f7a28-198">All capabilities in Teams, from private chat and calling, ad-hoc and scheduled meetings, and apps are enabled by default, allowing users to experiment and use the capabilities that suit their needs.</span></span> <span data-ttu-id="f7a28-199">A experiência de primeira execução do Teams orienta os usuários a escolher o seu aplicativo de bate-papo e chamada de preferência (Microsoft Teams ou Skype for Business).</span><span class="sxs-lookup"><span data-stu-id="f7a28-199">A first-run experience in Teams guides users to pick their preferred chat and calling application (Microsoft Teams or Skype for Business).</span></span>

<span data-ttu-id="f7a28-200">Se a sua organização exigir uma liberação mais controlada de novas ferramentas como o Teams, as opções a seguir podem ser consideradas para a sua jornada do cliente lado a lado gerenciada. São elas:</span><span class="sxs-lookup"><span data-stu-id="f7a28-200">Should your organization require a more controlled release of new tools such as Teams, the following options can be considered for your managed side-by-side customer journey, they are:</span></span>

-   <span data-ttu-id="f7a28-201">Piloto e lançamento do Teams para colaboração.</span><span class="sxs-lookup"><span data-stu-id="f7a28-201">Pilot and rollout of Teams for collaboration.</span></span> <span data-ttu-id="f7a28-202">Veja [Piloto do Teams paralelamente ao Skype for Business](pilot-essentials.md).</span><span class="sxs-lookup"><span data-stu-id="f7a28-202">See [Pilot Teams with Skype for Business](pilot-essentials.md).</span></span>

-   <span data-ttu-id="f7a28-203">Lançamento do Teams para reuniões</span><span class="sxs-lookup"><span data-stu-id="f7a28-203">Rollout of Teams for meetings</span></span>

-   <span data-ttu-id="f7a28-204">Lançamento do Teams para chamadas</span><span class="sxs-lookup"><span data-stu-id="f7a28-204">Rollout of Teams for calling</span></span>

### <a name="teams-pilot-and-rollout-for-collaboration"></a><span data-ttu-id="f7a28-205">Piloto e lançamento do Teams para colaboração</span><span class="sxs-lookup"><span data-stu-id="f7a28-205">Teams pilot and rollout for collaboration</span></span>

<span data-ttu-id="f7a28-206">Na essência, o Microsoft Teams foi construído em torno do bate-papo persistente e da integração com o Office 365 ao aprimorar os Grupos do Office 365.</span><span class="sxs-lookup"><span data-stu-id="f7a28-206">At its core, Microsoft Teams was built around persistent chat and integration with Office 365 by enhancing Office 365 Groups.</span></span>

<span data-ttu-id="f7a28-207">Uma vez que, por padrão, os usuários da sua organização com uma licença de assinatura elegível do Office 365 estão habilitados para o Teams, um piloto limitado do Teams envolverá desabilitar a licença do Teams para todos os usuários que estejam fora do grupo piloto.</span><span class="sxs-lookup"><span data-stu-id="f7a28-207">Since by default users in your organization with an eligible Office 365 subscription license are enabled for Teams, a limited Teams pilot will involve disabling the Teams license for all users who are outside of the pilot group.</span></span>

<span data-ttu-id="f7a28-208">Para focar o lançamento do Teams como uma solução de colaboração e bate-papo privado, além de reduzir a confusão do usuário devido à sobreposição de recursos do Skype for Business, você pode alterar as configurações a seguir do Office 365, em nível de locatário.</span><span class="sxs-lookup"><span data-stu-id="f7a28-208">To focus the Teams release as a collaboration and private chat solution, and to reduce user confusion due to overlapping capabilities with Skype for Business, you can change the following settings at the Office 365 tenant level.</span></span> <span data-ttu-id="f7a28-209">Para alterar essas configurações do Office 365, consulte [Configurar o Microsoft Teams na sua organização do Office 365](Office-365-set-up.md).</span><span class="sxs-lookup"><span data-stu-id="f7a28-209">To change these Office 365 settings, see [Set up Microsoft Teams in your Office 365 organization](Office-365-set-up.md).</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f7a28-210">Seção</span><span class="sxs-lookup"><span data-stu-id="f7a28-210">Section</span></span></th>
<th align="left"><span data-ttu-id="f7a28-211">Configuração</span><span class="sxs-lookup"><span data-stu-id="f7a28-211">Setting</span></span></th>
<th align="left"><span data-ttu-id="f7a28-212">Descrição</span><span class="sxs-lookup"><span data-stu-id="f7a28-212">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong><br><span data-ttu-id="f7a28-213">Chamadas e reuniões</strong></span><span class="sxs-lookup"><span data-stu-id="f7a28-213">Calls and meetings</strong></span></span></td>
<td align="left"><p><span data-ttu-id="f7a28-214">Permitir agendamento de reuniões privadas: <strong>Desativado</strong></span><span class="sxs-lookup"><span data-stu-id="f7a28-214">Allow scheduling for private meetings: <strong>Off</strong></span></span></p><p><span data-ttu-id="f7a28-215">Permitir agendamento de reuniões de canais: <strong>Desativado</strong></span><span class="sxs-lookup"><span data-stu-id="f7a28-215">Allow scheduling for channel meetings: <strong>Off</strong></span></span></p><p><span data-ttu-id="f7a28-216">Permitir chamadas privadas: <strong>Desativado</strong></span><span class="sxs-lookup"><span data-stu-id="f7a28-216">Allow private calling: <strong>Off</strong></span></span></p></td>
<td align="left"><p><span data-ttu-id="f7a28-217">Desabilitar essa configuração impede que os usuários agendem reuniões privadas</span><span class="sxs-lookup"><span data-stu-id="f7a28-217">Disabling this setting prevents users from scheduling private meetings</span></span></p><p><span data-ttu-id="f7a28-218">Desabilitar essa configuração impede que os usuários agendem reuniões em canais</span><span class="sxs-lookup"><span data-stu-id="f7a28-218">Disabling this setting prevents users from scheduling channel meetings</span></span></p><p><span data-ttu-id="f7a28-219">Desabilitar essa configuração impede que os usuários façam chamadas privadas (áudio e vídeo)</span><span class="sxs-lookup"><span data-stu-id="f7a28-219">Disabling this setting prevents users from making private calls (audio and video)</span></span></p></td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p><span data-ttu-id="f7a28-220">Nota</span><span class="sxs-lookup"><span data-stu-id="f7a28-220">Note</span></span></p></td>
<td align="left"><br><br><span data-ttu-id="f7a28-221">Você precisa desabilitar a Chamada Privada dos usuários Business e Enterprise e os usuários Convidados (se o aceso a convidados se aplicar na sua organização).</span><span class="sxs-lookup"><span data-stu-id="f7a28-221">You must disable Private Calling to both Business and Enterprise users, and Guest users (if Guest Access is applicable to your organization).</span></span></td>
</tr>
</thead>
<tbody>
</tbody>
</table>



<span data-ttu-id="f7a28-222">Com essa configuração, pode ser apresentado aos usuários podem como as reuniões funcionam no Teams, defendendo o uso de meetup de canais ad-hoc, permitindo o uso de voz, vídeo e compartilhamento de tela como parte da experiência de colaboração moderna.</span><span class="sxs-lookup"><span data-stu-id="f7a28-222">With this configuration, users can be introduced to how meetings work in Teams by advocating the use of ad-hoc channel meetup, enabling the use of voice, video, and screen sharing as part of the modern collaboration experience.</span></span> <span data-ttu-id="f7a28-223">Os usuários finais também podem se beneficiar dos recursos de bate-papo privado persistente em plataforma cruzada do Teams.</span><span class="sxs-lookup"><span data-stu-id="f7a28-223">End users can also benefit from Teams persistent, cross-platform, private chat capabilities.</span></span>

<span data-ttu-id="f7a28-224">Um piloto bem-sucedido do Teams para colaboração e bate-papo privado pode ser acompanhado com uma ampla distribuição através da empresa ao habilitar a licença do Teams para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="f7a28-224">A successful Teams pilot for collaboration and private chat can be followed up with broad rollout throughout the organization by enabling Teams license for all users.</span></span>

<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p><span data-ttu-id="f7a28-225">Nota</span><span class="sxs-lookup"><span data-stu-id="f7a28-225">Note</span></span></p></td>
<td align="left"><span data-ttu-id="f7a28-226">Durante o piloto, e também na fase dois, quando o bate-papo privado estiver habilitado, um bate-papo entre o usuário do Teams e o usuário do Skype for Business, o usuário não poderá fazer o que segue:</span><span class="sxs-lookup"><span data-stu-id="f7a28-226">During the pilot, and in phase two when private chat is enabled, a Teams user chatting with a Skype for Business user will not be able to do the following:</span></span><br><span data-ttu-id="f7a28-227">
- Iniciar um vídeo a partir de uma sessão de bate-papo</span><span class="sxs-lookup"><span data-stu-id="f7a28-227">
- Start video call from a chat session</span></span><br><span data-ttu-id="f7a28-228">
- Transferir arquivos</span><span class="sxs-lookup"><span data-stu-id="f7a28-228">
- Transfers files</span></span> <br><span data-ttu-id="f7a28-229">
- Iniciar uma chamada com várias pessoas a partir da sessão de bate-papo</span><span class="sxs-lookup"><span data-stu-id="f7a28-229">
- Initiate a multiparty call from the chat session</span></span><br><span data-ttu-id="f7a28-230">
- Os usuários não poderão iniciar uma sessão de compartilhamento de desktop</span><span class="sxs-lookup"><span data-stu-id="f7a28-230">
- Users will not be able to start a desktop sharing session</span></span><br>

</td>
</tr>
</thead>
<tbody>
</tbody>
</table>


### <a name="rollout-of-teams-for-meetings"></a><span data-ttu-id="f7a28-231">Lançamento do Teams para reuniões</span><span class="sxs-lookup"><span data-stu-id="f7a28-231">Rollout of Teams for meetings</span></span>

<span data-ttu-id="f7a28-232">Conforme os usuários forem se acostumando a colaborar usando o Microsoft Teams, as reunião agendadas poderão ser consideradas como o próximo recurso a ser habilitado na organização.</span><span class="sxs-lookup"><span data-stu-id="f7a28-232">As users are getting accustomed to collaborating using Microsoft Teams, scheduled meetings can be considered as the next capability to enable in the organization.</span></span>

<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p><span data-ttu-id="f7a28-233">Nota</span><span class="sxs-lookup"><span data-stu-id="f7a28-233">Note</span></span></p></td>
<td align="left"><br><br><span data-ttu-id="f7a28-234">Os organizadores das reuniões agendadas precisam ter suas caixas de correio no Exchange Online multilocatário (ou Exchange Online Dedicated vNext).</span><span class="sxs-lookup"><span data-stu-id="f7a28-234">The organizers of scheduled meetings must have their mailboxes in Exchange Online multi-tenant (or Exchange Online Dedicated vNext).</span></span></td>
</tr>
</thead>
<tbody>
</tbody>
</table>

<span data-ttu-id="f7a28-235">As configurações a seguir podem ser configuradas em nível de locatário para habilitar reuniões agendadas no Teams, e as configurações são aplicáveis somente para usuários Business e Enterprise.</span><span class="sxs-lookup"><span data-stu-id="f7a28-235">The following settings can be configured at the tenant level to enable scheduled meetings in Teams, and the settings are applicable to Business and Enterprise users only.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f7a28-236">Seção</span><span class="sxs-lookup"><span data-stu-id="f7a28-236">Section</span></span></th>
<th align="left"><span data-ttu-id="f7a28-237">Configuração</span><span class="sxs-lookup"><span data-stu-id="f7a28-237">Setting</span></span></th>
<th align="left"><span data-ttu-id="f7a28-238">Descrição</span><span class="sxs-lookup"><span data-stu-id="f7a28-238">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong><br><span data-ttu-id="f7a28-239">Chamadas e reuniões</strong></span><span class="sxs-lookup"><span data-stu-id="f7a28-239">Calls and meetings</strong></span></span></td>
<td align="left"><p><span data-ttu-id="f7a28-240">Permitir agendamento de reuniões privadas: <strong>Ativado</strong></span><span class="sxs-lookup"><span data-stu-id="f7a28-240">Allow scheduling for private meetings: <strong>On</strong></span></span></p><p><span data-ttu-id="f7a28-241">Permitir agendamento de reuniões de canais: <strong>Ativado</strong></span><span class="sxs-lookup"><span data-stu-id="f7a28-241">Allow scheduling for channel meetings: <strong>On</strong></span></span></p></td>
<td align="left"><p><span data-ttu-id="f7a28-242">Habilitar essa configuração permite que os usuários agendem reuniões privadas</span><span class="sxs-lookup"><span data-stu-id="f7a28-242">Enabling this setting allows users to schedule private meetings</span></span></p><p><span data-ttu-id="f7a28-243">Habilitar essa configuração permite que os usuários agendem reuniões em canais</span><span class="sxs-lookup"><span data-stu-id="f7a28-243">Enabling this setting allows users to schedule channel meetings</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f7a28-244">As reuniões agendadas podem ser organizadas através do cliente desktop do Teams, de um navegador ou do Microsoft Outlook, usando o complemento da reunião para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f7a28-244">Scheduled meetings can be organized via the Teams desktop client, a browser, or via Microsoft Outlook using the meeting add-in for Microsoft Teams.</span></span> <span data-ttu-id="f7a28-245">Depois que as reuniões agendadas do Teams estiverem habilitadas, recomendamos que você comece a instruir os usuários para criar novas reuniões no Teams ou atualizar as reuniões Skype for Business existentes para reuniões Teams.</span><span class="sxs-lookup"><span data-stu-id="f7a28-245">Once scheduled meetings in Teams is enabled, we recommend you start educating users to create new Teams meetings or update existing Skype for Business meetings to Teams meetings.</span></span>

### <a name="rollout-of-teams-for-calling"></a><span data-ttu-id="f7a28-246">Lançamento do Teams para chamadas</span><span class="sxs-lookup"><span data-stu-id="f7a28-246">Rollout of Teams for calling</span></span>

<span data-ttu-id="f7a28-247">A chamada privada é o recurso do Teams que será desenvolvido continuamente e, ao longo do tempo, oferecerá uma substituição atraente para o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="f7a28-247">Private calling is the Teams capability that will be continuously developed, and over time provide a compelling replacement to Skype for Business.</span></span> <span data-ttu-id="f7a28-248">Quando a sua organização considerar que os recursos de chamadas privadas do Teams atendem aos principais requisitos da empresa, as configurações a seguir podem ser configuradas em nível de locatário para habilitar a chamada privada no Teams.</span><span class="sxs-lookup"><span data-stu-id="f7a28-248">When your organization considers that Teams private calling capabilities meet key business requirements, the following settings can be configured at the tenant level to enable private calling in Teams.</span></span> 

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f7a28-249">Seção</span><span class="sxs-lookup"><span data-stu-id="f7a28-249">Section</span></span></th>
<th align="left"><span data-ttu-id="f7a28-250">Configuração</span><span class="sxs-lookup"><span data-stu-id="f7a28-250">Setting</span></span></th>
<th align="left"><span data-ttu-id="f7a28-251">Descrição</span><span class="sxs-lookup"><span data-stu-id="f7a28-251">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong><br><span data-ttu-id="f7a28-252">Chamadas e reuniões</strong></span><span class="sxs-lookup"><span data-stu-id="f7a28-252">Calls and meetings</strong></span></span></td>
<td align="left"><p><span data-ttu-id="f7a28-253">Permitir chamadas privadas: <strong>Ativado</strong></span><span class="sxs-lookup"><span data-stu-id="f7a28-253">Allow private calling: <strong>On</strong></span></span></p></td>
<td align="left"><p><span data-ttu-id="f7a28-254">Habilitar essa configuração permite que os usuários façam chamadas privadas (áudio e vídeo)</span><span class="sxs-lookup"><span data-stu-id="f7a28-254">Enabling this setting allows users to place private calls (audio and video)</span></span></p></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p><span data-ttu-id="f7a28-255">Nota</span><span class="sxs-lookup"><span data-stu-id="f7a28-255">Note</span></span></p></td>
<td align="left"><br><br><span data-ttu-id="f7a28-256">Permitir que os usuários batam papo de forma privada: Habilitar essa configuração permite que os usuários tenham bate-papos privados com outros usuários.</span><span class="sxs-lookup"><span data-stu-id="f7a28-256">Allow users to chat privately: Enabling this setting allows users to chat with other users privately.</span></span></td>
</tr>
</thead>
<tbody>
</tbody>
</table>


<span data-ttu-id="f7a28-257">Nessa fase, todos os usuários devem ser instruídos para escolher o Teams como o aplicativo de chamada de preferência.</span><span class="sxs-lookup"><span data-stu-id="f7a28-257">At this stage, all users must be instructed to choose Teams as the preferred calling app.</span></span>

<span data-ttu-id="f7a28-258">Com a habilitação das chamadas privadas, o Teams oferecerá todos os recursos atualmente oferecidos pelo Skype for Business, e os usuários poderão começar a usar o Teams para satisfazer suas necessidades de comunicação e colaboração.</span><span class="sxs-lookup"><span data-stu-id="f7a28-258">With the enablement of private calling, Teams will deliver all capabilities currently provided by Skype for Business, and users can start using Teams to fulfill their communications and collaboration requirements.</span></span>


<table>
<thead>
<tr class="header">
<td align="left"><p><img src="media/pilot_essentials_image2.png" /></p></td>
<td align="left">
<p><span data-ttu-id="f7a28-259"><strong>Próxima ação:</strong> Depois que o Teams estiver estabelecido e sendo executado lado a lado com o Skype for Business, [Gere valor com a adoção do Teams pelos usuários](continue-journey.md), enquanto continua sua jornada de migração do Skype for Business para o Teams.</span><span class="sxs-lookup"><span data-stu-id="f7a28-259"><strong>Next Action:</strong> Once Teams is up and running side-by-side with Skype for Business, [Drive Value through user adoption of Teams](continue-journey.md), while continuing your journey from Skype for Business to Teams.</span></span></td>
</tr>
</thead>
<tbody>
</tbody>
</table>