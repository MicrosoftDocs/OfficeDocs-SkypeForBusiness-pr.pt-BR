---
title: Opções de conectividade PSTN
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 07/08/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
- seo-marvel-may2020
search.appverid: MET150
description: Saiba mais sobre Teams opções de chamada (conectividade PSTN) e as decisões que você tomará para sua organização.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5b1b06178b269529b1d0227ff02d529c91ba1480
ms.sourcegitcommit: 5720fa12bdabdfc2988bf835c8cf95e4d64fa54e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2021
ms.locfileid: "53354510"
---
# <a name="pstn-connectivity-options"></a><span data-ttu-id="c1587-103">Opções de conectividade PSTN</span><span class="sxs-lookup"><span data-stu-id="c1587-103">PSTN connectivity options</span></span>

<span data-ttu-id="c1587-104">A Microsoft fornece recursos completos de Exchange (PBX) para sua organização por meio Sistema de Telefonia.</span><span class="sxs-lookup"><span data-stu-id="c1587-104">Microsoft provides complete Private Branch Exchange (PBX) capabilities for your organization through Phone System.</span></span> <span data-ttu-id="c1587-105">No entanto, para permitir que os usuários façam chamadas fora da sua organização, você precisa se conectar Sistema de Telefonia a Rede Telefônica Pública Comutado (PSTN).</span><span class="sxs-lookup"><span data-stu-id="c1587-105">However, to enable users to make calls outside your organization, you need to connect Phone System to the Public Switched Telephone Network (PSTN).</span></span>

<span data-ttu-id="c1587-106">Este artigo se concentra nas opções de conectividade PSTN.</span><span class="sxs-lookup"><span data-stu-id="c1587-106">This article focuses on PSTN connectivity options.</span></span> <span data-ttu-id="c1587-107">Para obter mais informações sobre soluções de voz da Microsoft, detalhando detalhes sobre Sistema de Telefonia recursos, consulte [Plan your Teams voice solution](cloud-voice-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="c1587-107">For more information about Microsoft voice solutions, incuding details about Phone System features, see [Plan your Teams voice solution](cloud-voice-landing-page.md).</span></span>

<span data-ttu-id="c1587-108">Para conectar Sistema de Telefonia ao PSTN, você pode escolher entre as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="c1587-108">To connect Phone System to the PSTN, you can choose from the following options:</span></span>

- <span data-ttu-id="c1587-109">[**Plano de Chamada**](#phone-system-with-calling-plan).</span><span class="sxs-lookup"><span data-stu-id="c1587-109">[**Calling Plan**](#phone-system-with-calling-plan).</span></span> <span data-ttu-id="c1587-110">Uma solução completa na nuvem com a Microsoft como operadora PSTN.</span><span class="sxs-lookup"><span data-stu-id="c1587-110">An all-in-the-cloud solution with Microsoft as your PSTN carrier.</span></span>

- <span data-ttu-id="c1587-111">[**Roteamento**](#phone-system-with-direct-routing)Direto , que permite que você use sua própria operadora PSTN conectando seus Controladores de Borda de Sessão (SBC) a Sistema de Telefonia.</span><span class="sxs-lookup"><span data-stu-id="c1587-111">[**Direct Routing**](#phone-system-with-direct-routing), which enables you to use your own PSTN carrier by connecting your Session Border Controller(s) (SBC) to Phone System.</span></span>

- <span data-ttu-id="c1587-112">[**Operador Conexão**](#phone-system-with-operator-connect), que está disponível atualmente apenas na **visualização pública.**</span><span class="sxs-lookup"><span data-stu-id="c1587-112">[**Operator Connect**](#phone-system-with-operator-connect), which is currently available only in **public preview.**</span></span>  <span data-ttu-id="c1587-113">Com o Conexão operador, se sua operadora existente for participante do programa Conexão microsoft operator, eles poderão gerenciar a chamada PSTN e os Controladores de Borda de Sessão (SBCs).</span><span class="sxs-lookup"><span data-stu-id="c1587-113">With Operator Connect, if your existing carrier is a participant in the Microsoft Operator Connect program, they can manage PSTN calling and Session Border Controllers (SBCs).</span></span> 

<span data-ttu-id="c1587-114">Você também pode escolher uma combinação de opções, que permite projetar uma solução para um ambiente complexo ou gerenciar uma migração em várias etapas.</span><span class="sxs-lookup"><span data-stu-id="c1587-114">You can also choose a combination of options, which enables you to design a solution for a complex environment, or manage a multi-step migration.</span></span>

<span data-ttu-id="c1587-115">Saiba que a opção ou as opções escolhidas afetam como alguns recursos Sistema de Telefonia estão configurados.</span><span class="sxs-lookup"><span data-stu-id="c1587-115">Be aware that the option or options you choose affect how some Phone System features are configured.</span></span> <span data-ttu-id="c1587-116">Para obter mais informações, consulte [Considerações de](#configuration-considerations) configuração posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="c1587-116">For more information, see [Configuration considerations](#configuration-considerations) later in this article.</span></span>


## <a name="phone-system-with-calling-plan"></a><span data-ttu-id="c1587-117">Sistema de Telefonia com Plano de Chamada</span><span class="sxs-lookup"><span data-stu-id="c1587-117">Phone System with Calling Plan</span></span> 

<span data-ttu-id="c1587-118">Sistema de Telefonia com o Plano de Chamadas é a solução de voz all-in-the-cloud da Microsoft para Teams usuários.</span><span class="sxs-lookup"><span data-stu-id="c1587-118">Phone System with Calling Plan is Microsoft's all-in-the-cloud voice solution for Teams users.</span></span> <span data-ttu-id="c1587-119">Essa é a opção mais simples que conecta Sistema de Telefonia ao PSTN.</span><span class="sxs-lookup"><span data-stu-id="c1587-119">This is the simplest option that connects Phone System to the PSTN.</span></span> <span data-ttu-id="c1587-120">Com essa opção, a Microsoft atua como sua operadora PSTN, conforme mostrado no diagrama a seguir:</span><span class="sxs-lookup"><span data-stu-id="c1587-120">With this option, Microsoft acts as your PSTN carrier, as shown in the following diagram:</span></span>

![O Diagrama 1 mostra Sistema de Telefonia com Plano de Chamada](media/voice-solutions-simple.png)

<span data-ttu-id="c1587-122">Se você responder sim ao seguinte, Sistema de Telefonia com Plano de Chamada é a solução certa para você:</span><span class="sxs-lookup"><span data-stu-id="c1587-122">If you answer yes to the following, then Phone System with Calling Plan is the right solution for you:</span></span>

- <span data-ttu-id="c1587-123">O Plano de Chamada está disponível em sua região.</span><span class="sxs-lookup"><span data-stu-id="c1587-123">Calling Plan is available in your region.</span></span>
- <span data-ttu-id="c1587-124">Você não precisa manter sua operadora PSTN atual.</span><span class="sxs-lookup"><span data-stu-id="c1587-124">You do not need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="c1587-125">Você deseja usar o acesso gerenciado pela Microsoft à PSTN.</span><span class="sxs-lookup"><span data-stu-id="c1587-125">You want to use Microsoft-managed access to the PSTN.</span></span>

<span data-ttu-id="c1587-126">Com esta opção:</span><span class="sxs-lookup"><span data-stu-id="c1587-126">With this option:</span></span> 

- <span data-ttu-id="c1587-127">Você Telefone Microsoft sistema com planos de chamada domésticos ou internacionais que permitem a chamada para telefones em todo o mundo (dependendo do nível de serviço que está sendo licenciado).</span><span class="sxs-lookup"><span data-stu-id="c1587-127">You get Microsoft Phone System with added Domestic or International Calling Plans that enable calling to phones around the world (depending on the level of service being licensed).</span></span>

- <span data-ttu-id="c1587-128">Você não exige implantação ou manutenção de uma implantação local porque o Plano de Chamada &mdash; opera fora do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c1587-128">You do not require deployment or maintenance of an on-premises deployment&mdash;because Calling Plan operates out of Microsoft 365.</span></span>

- <span data-ttu-id="c1587-129">Observação: se necessário, você pode optar por conectar um Controlador de Borda de Sessão (SBC) com suporte por meio de Roteamento Direto para interoperabilidade com PBXs de terceiros, dispositivos analógicos e outros equipamentos de telefonia de terceiros suportados pelo SBC.</span><span class="sxs-lookup"><span data-stu-id="c1587-129">Note: If necessary, you can choose to connect a supported Session Border Controller (SBC) through Direct Routing for interoperability with third-party PBXs, analog devices, and other third-party telephony equipment supported by the SBC.</span></span>

<span data-ttu-id="c1587-130">Essa opção requer conexão ininterrupta com Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c1587-130">This option requires uninterrupted connection to Microsoft 365.</span></span>

<span data-ttu-id="c1587-131">Para obter mais informações sobre o Plano de Chamada, consulte os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="c1587-131">For more information about Calling Plan, see the following articles:</span></span>

- [<span data-ttu-id="c1587-132">Qual plano de chamadas é ideal para você?</span><span class="sxs-lookup"><span data-stu-id="c1587-132">Which Calling Plan is right for you?</span></span>](calling-plan-landing-page.md)
- [<span data-ttu-id="c1587-133">Como comprar um plano de chamadas</span><span class="sxs-lookup"><span data-stu-id="c1587-133">How to buy a Calling Plan</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="c1587-134">Disponibilidade de país e região do Plano de chamadas</span><span class="sxs-lookup"><span data-stu-id="c1587-134">Country and region availability for Calling Plan</span></span>](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [<span data-ttu-id="c1587-135">Configurar Plano de Chamada</span><span class="sxs-lookup"><span data-stu-id="c1587-135">Set up Calling Plan</span></span>](set-up-calling-plans.md)


## <a name="phone-system-with-direct-routing"></a><span data-ttu-id="c1587-136">Sistema de Telefonia com Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="c1587-136">Phone System with Direct Routing</span></span>

<span data-ttu-id="c1587-137">Essa opção conecta Sistema de Telefonia à sua rede de telefonia usando Roteamento Direto, conforme mostrado no diagrama a seguir:</span><span class="sxs-lookup"><span data-stu-id="c1587-137">This option connects Phone System to your telephony network by using Direct Routing, as shown in the following diagram:</span></span> 

![O Diagrama 5 mostra Sistema de Telefonia roteamento direto](media/voice-solution-with-direct-routing.png)

<span data-ttu-id="c1587-139">Se você responder sim às seguintes perguntas, Sistema de Telefonia com Roteamento Direto é a solução certa para você:</span><span class="sxs-lookup"><span data-stu-id="c1587-139">If you answer yes to the following questions, then Phone System with Direct Routing is the right solution for you:</span></span>

- <span data-ttu-id="c1587-140">Você deseja usar Teams com Sistema de Telefonia.</span><span class="sxs-lookup"><span data-stu-id="c1587-140">You want to use Teams with Phone System.</span></span>
- <span data-ttu-id="c1587-141">Você precisa manter sua operadora PSTN atual.</span><span class="sxs-lookup"><span data-stu-id="c1587-141">You need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="c1587-142">Você deseja misturar roteamento, com algumas chamadas passando pelo Plano de Chamadas, algumas por meio da sua operadora.</span><span class="sxs-lookup"><span data-stu-id="c1587-142">You want to mix routing, with some calls going through Calling Plan, some through your carrier.</span></span>
- <span data-ttu-id="c1587-143">Você precisa interoperar com PBXs e/ou equipamentos de terceiros, como pagers de sobrecarga, dispositivos analógicos e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="c1587-143">You need to interoperate with third-party PBXs and/or equipment such us overhead pagers, analog devices, and so on.</span></span>

<span data-ttu-id="c1587-144">Com esta opção:</span><span class="sxs-lookup"><span data-stu-id="c1587-144">With this option:</span></span>

- <span data-ttu-id="c1587-145">Você conecta seu próprio Controlador de Borda de Sessão (SBC) com suporte Sistema de Telefonia sem a necessidade de software local adicional.</span><span class="sxs-lookup"><span data-stu-id="c1587-145">You connect your own supported Session Border Controller (SBC) to Phone System without the need for additional on-premises software.</span></span>

- <span data-ttu-id="c1587-146">Você pode usar praticamente qualquer operadora de telefonia com Sistema de Telefonia.</span><span class="sxs-lookup"><span data-stu-id="c1587-146">You can use virtually any telephony carrier with Phone System.</span></span>

- <span data-ttu-id="c1587-147">Você pode optar por configurar e gerenciar essa opção, ou ela pode ser configurada e gerenciada por sua operadora ou parceiro (pergunte se sua operadora ou parceiro fornece essa opção).</span><span class="sxs-lookup"><span data-stu-id="c1587-147">You can choose to configure and manage this option, or it can be configured and managed by your carrier or partner (ask if your carrier or partner provides this option).</span></span>

- <span data-ttu-id="c1587-148">Você pode configurar a interoperabilidade entre seu equipamento de telefonia, como um PBX de terceiros e &mdash; dispositivos analógicos &mdash; e Sistema de Telefonia.</span><span class="sxs-lookup"><span data-stu-id="c1587-148">You can configure interoperability between your telephony equipment&mdash;such as a third-party PBX and analog devices&mdash;and Phone System.</span></span>

<span data-ttu-id="c1587-149">Esta opção requer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c1587-149">This option requires the following:</span></span>

- <span data-ttu-id="c1587-150">Conexão ininterrupta com Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c1587-150">Uninterrupted connection to Microsoft 365.</span></span>

- <span data-ttu-id="c1587-151">Implantando e mantendo um SBC com suporte.</span><span class="sxs-lookup"><span data-stu-id="c1587-151">Deploying and maintaining a supported SBC.</span></span>

- <span data-ttu-id="c1587-152">Um contrato com uma operadora de terceiros.</span><span class="sxs-lookup"><span data-stu-id="c1587-152">A contract with a third-party carrier.</span></span>
  <span data-ttu-id="c1587-153">(A menos que implantado como uma opção para fornecer conexão com PBX de terceiros, dispositivos analógicos ou outros equipamentos de telefonia para usuários que estão em Sistema de Telefonia com Plano de Chamada.)</span><span class="sxs-lookup"><span data-stu-id="c1587-153">(Unless deployed as an option to provide connection to third-party PBX, analog devices, or other telephony equipment for users who are on Phone System with Calling Plan.)</span></span>

<span data-ttu-id="c1587-154">Para obter mais informações sobre Roteamento Direto, consulte os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="c1587-154">For more information about Direct Routing, see the following articles:</span></span>

- [<span data-ttu-id="c1587-155">Planejar o Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="c1587-155">Plan Direct Routing</span></span>](direct-routing-plan.md)
- [<span data-ttu-id="c1587-156">Configurar o Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="c1587-156">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="c1587-157">Gerenciar políticas de roteamento de voz para uso com Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="c1587-157">Manage voice routing policies for use with Direct Routing</span></span>](manage-voice-routing-policies.md)
- [<span data-ttu-id="c1587-158">Planejar o Roteamento baseado na localização para o Roteamento direto</span><span class="sxs-lookup"><span data-stu-id="c1587-158">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="c1587-159">Lista de controladores de borda da sessão certificados para Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="c1587-159">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)


## <a name="phone-system-with-operator-connect"></a><span data-ttu-id="c1587-160">Sistema de Telefonia com operador Conexão</span><span class="sxs-lookup"><span data-stu-id="c1587-160">Phone System with Operator Connect</span></span>

<span data-ttu-id="c1587-161">Com o Conexão operador, atualmente em visualização pública, se sua operadora existente for participante do programa de Conexão do Microsoft Operator, eles poderão gerenciar o serviço para trazer a chamada PSTN para Teams.</span><span class="sxs-lookup"><span data-stu-id="c1587-161">With Operator Connect, currently in public preview, if your existing carrier is a participant in the Microsoft Operator Connect program, they can manage the service for bringing PSTN calling to Teams.</span></span> <span data-ttu-id="c1587-162">Sua operadora gerencia os serviços de chamada PSTN e controladores de borda de sessão (SBCs), permitindo que você salve na compra e gerenciamento de hardware.</span><span class="sxs-lookup"><span data-stu-id="c1587-162">Your carrier manages the PSTN calling services and Session Border Controllers (SBCs), allowing you to save on hardware purchase and management.</span></span>

<span data-ttu-id="c1587-163">O Conexão operador pode ser a solução certa para sua organização se:</span><span class="sxs-lookup"><span data-stu-id="c1587-163">Operator Connect might be the right solution for your organization if:</span></span>

- <span data-ttu-id="c1587-164">O Plano de Chamada da Microsoft não está disponível em sua localização geográfica.</span><span class="sxs-lookup"><span data-stu-id="c1587-164">Microsoft Calling Plan isn't available in your geographic location.</span></span>
- <span data-ttu-id="c1587-165">Sua operadora preferencial é participante do programa Conexão Microsoft Operator.</span><span class="sxs-lookup"><span data-stu-id="c1587-165">Your preferred carrier is a participant in the Microsoft Operator Connect program.</span></span>
- <span data-ttu-id="c1587-166">Você deseja encontrar uma nova operadora para habilitar a chamada no Teams.</span><span class="sxs-lookup"><span data-stu-id="c1587-166">You want to find a new carrier to enable calling in Teams.</span></span>

<span data-ttu-id="c1587-167">Para obter informações sobre os benefícios e requisitos do Operador Conexão e para obter uma lista de operadoras participantes deste programa, consulte [Plan Operator Conexão](operator-connect-plan.md).</span><span class="sxs-lookup"><span data-stu-id="c1587-167">For information on the benefits and requirements of Operator Connect, and for a list of carriers participating in this program, see [Plan Operator Connect](operator-connect-plan.md).</span></span> <span data-ttu-id="c1587-168">Para obter informações sobre como configurar o operador Conexão, consulte [Configure Operator Conexão](operator-connect-configure.md).</span><span class="sxs-lookup"><span data-stu-id="c1587-168">For information on how to configure Operator Connect, see [Configure Operator Connect](operator-connect-configure.md).</span></span>

## <a name="configuration-considerations"></a><span data-ttu-id="c1587-169">Considerações sobre configuração</span><span class="sxs-lookup"><span data-stu-id="c1587-169">Configuration considerations</span></span>

<span data-ttu-id="c1587-170">A maioria Sistema de Telefonia recursos são os mesmos, independentemente da opção de conectividade PSTN escolhida.</span><span class="sxs-lookup"><span data-stu-id="c1587-170">Most Phone System features are the same regardless of the PSTN connectivity option you choose.</span></span> <span data-ttu-id="c1587-171">Por exemplo, as configurações de chamada sem resposta e encaminhamento, transferência de chamada, música personalizada em espera, estacionamento de chamadas, linha compartilhada e aplicativos de voz estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="c1587-171">For example, call unanswered and forwarding settings, call transfer, custom music on hold, call park, shared line, and voice apps are all available.</span></span> <span data-ttu-id="c1587-172">Para obter uma lista completa de Sistema de Telefonia recursos, consulte Aqui está [o que você obter com Sistema de Telefonia](here-s-what-you-get-with-phone-system.md).</span><span class="sxs-lookup"><span data-stu-id="c1587-172">For a complete list of Phone System features, see [Here's what you get with Phone System](here-s-what-you-get-with-phone-system.md).</span></span>

<span data-ttu-id="c1587-173">No entanto, há algumas diferenças na funcionalidade que afetam a forma como você configura determinados Sistema de Telefonia recursos.</span><span class="sxs-lookup"><span data-stu-id="c1587-173">There are some differences in functionality, however, that affect how you configure certain Phone System features.</span></span> <span data-ttu-id="c1587-174">Por exemplo, o Roteamento Direto exige etapas adicionais para configurar o roteamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="c1587-174">For example, Direct Routing requires additional steps to configure call routing.</span></span> <span data-ttu-id="c1587-175">Como outro exemplo, o Roteamento Direto fornece o Roteamento Baseado em Local (LBR), para que você possa restringir o desvio de chamada de chamada em determinados locais geográficos onde ele não é permitido.</span><span class="sxs-lookup"><span data-stu-id="c1587-175">As another example, Direct Routing provides Location-Based-Routing (LBR)--so that you can restrict toll bypass in certain geographic locations where it is not allowed.</span></span> 


### <a name="phone-number-management"></a><span data-ttu-id="c1587-176">Telefone gerenciamento de números</span><span class="sxs-lookup"><span data-stu-id="c1587-176">Phone number management</span></span>

<span data-ttu-id="c1587-177">A Microsoft tem dois tipos de números de telefone disponíveis: números de assinante (usuário), que podem ser atribuídos aos usuários em sua organização, e números de serviço, disponíveis como números de serviço de chamada e chamada gratuita.</span><span class="sxs-lookup"><span data-stu-id="c1587-177">Microsoft has two types of telephone numbers available: subscriber (user) numbers, which can be assigned to users in your organization, and service numbers, available as toll and toll-free service numbers.</span></span> <span data-ttu-id="c1587-178">Os números de serviço têm maior capacidade de chamada simultânea do que números de assinantes e podem ser atribuídos a serviços como Audioconferência, Atendimento Automático ou Filas de Chamada.</span><span class="sxs-lookup"><span data-stu-id="c1587-178">Service numbers have higher concurrent call capacity than subscriber numbers and can be assigned to services such as Audio Conferencing, Auto Attendants, or Call Queues.</span></span>

<span data-ttu-id="c1587-179">Você precisará decidir:</span><span class="sxs-lookup"><span data-stu-id="c1587-179">You will need to decide:</span></span>

- <span data-ttu-id="c1587-180">Quais locais de usuários precisam de novos números de telefone da Microsoft?</span><span class="sxs-lookup"><span data-stu-id="c1587-180">Which user locations need new phone numbers from Microsoft?</span></span>
- <span data-ttu-id="c1587-181">De que tipo de número de telefone (assinante ou serviço) preciso?</span><span class="sxs-lookup"><span data-stu-id="c1587-181">Which type of telephone number (subscriber or service) do I need?</span></span>
- <span data-ttu-id="c1587-182">Como posso portar números de telefone existentes para Teams?</span><span class="sxs-lookup"><span data-stu-id="c1587-182">How do I port existing phone numbers to Teams?</span></span>

<span data-ttu-id="c1587-183">A forma como você adquire e gerencia números de telefone difere dependendo da sua opção de conectividade PSTN.</span><span class="sxs-lookup"><span data-stu-id="c1587-183">How you acquire and manage phone numbers differs depending on your PSTN connectivity option.</span></span>

- <span data-ttu-id="c1587-184">Para obter informações sobre como gerenciar números de telefone para o Plano de Chamadas, consulte [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="c1587-184">For information about managing phone numbers for Calling Plan, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>

- <span data-ttu-id="c1587-185">Para obter informações sobre como gerenciar números de telefone para Roteamento Direto, consulte [Configure the phone number and enable enterprise voice and voicemail](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online).</span><span class="sxs-lookup"><span data-stu-id="c1587-185">For information about managing phone numbers for Direct Routing, see [Configure the phone number and enable enterprise voice and voicemail](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online).</span></span>

- <span data-ttu-id="c1587-186">Para obter informações sobre como gerenciar números de telefone com operador Conexão, consulte Configurar números de telefone [com operador Conexão](operator-connect-configure.md#set-up-phone-numbers).</span><span class="sxs-lookup"><span data-stu-id="c1587-186">For information about managing phone numbers with Operator Connect, see [Set up phone numbers with Operator Connect](operator-connect-configure.md#set-up-phone-numbers).</span></span>


### <a name="call-routing-and-dial-plans"></a><span data-ttu-id="c1587-187">Roteamento de chamadas e planos de discagem</span><span class="sxs-lookup"><span data-stu-id="c1587-187">Call routing and dial plans</span></span>

<span data-ttu-id="c1587-188">A forma como você configura o roteamento de chamadas difere dependendo da sua opção de conectividade PSTN.</span><span class="sxs-lookup"><span data-stu-id="c1587-188">How you configure call routing differs depending on your PSTN connectivity option.</span></span>  

- <span data-ttu-id="c1587-189">Para Planos de Chamadas, a maior parte do roteamento de chamadas é manipulada pela infraestrutura do Plano de Chamadas da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c1587-189">For Calling Plans, most of call routing is handled by the Microsoft Calling Plan infrastructure.</span></span> <span data-ttu-id="c1587-190">Configure os planos de discagem do usuário para fins de conversão de número para autorização de chamada e roteamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="c1587-190">You configure user dial plans for purposes of number translation for call authorization and call routing.</span></span> <span data-ttu-id="c1587-191">Para obter mais informações, consulte [O que são planos de discagem?](what-are-dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="c1587-191">For more information, see [What are dial plans?](what-are-dial-plans.md).</span></span>

- <span data-ttu-id="c1587-192">Para Roteamento Direto, você deve configurar o roteamento de chamadas especificando as rotas de voz e atribuindo políticas de roteamento de voz aos usuários.</span><span class="sxs-lookup"><span data-stu-id="c1587-192">For Direct Routing, you must configure call routing by specifying the voice routes and assigning voice routing policies to users.</span></span> <span data-ttu-id="c1587-193">Você pode configurar planos de discagem para conversão de número no nível do tronco para garantir a interoperabilidade com controladores de borda de sessão (SBCs).</span><span class="sxs-lookup"><span data-stu-id="c1587-193">You can configure dial plans for number translation at the trunk level to ensure interoperability with Session Border Controllers (SBCs).</span></span> <span data-ttu-id="c1587-194">Para obter mais informações, consulte [Configure voice routing for Direct Routing](direct-routing-voice-routing.md), Manage voice routing [policies](manage-voice-routing-policies.md) and Translate [phone numbers](direct-routing-translate-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="c1587-194">For more information, see [Configure voice routing for Direct Routing](direct-routing-voice-routing.md), [Manage voice routing policies](manage-voice-routing-policies.md) and [Translate phone numbers](direct-routing-translate-numbers.md).</span></span> 

- <span data-ttu-id="c1587-195">Para operador Conexão, a maior parte do roteamento de chamadas é gerenciada pela operadora.</span><span class="sxs-lookup"><span data-stu-id="c1587-195">For Operator Connect, most of call routing is managed by the carrier.</span></span>  <span data-ttu-id="c1587-196">Configure os planos de discagem do usuário para fins de conversão de número para autorização de chamada e roteamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="c1587-196">You configure user dial plans for purposes of number translation for call authorization and call routing.</span></span> <span data-ttu-id="c1587-197">Para obter mais informações, consulte [O que são planos de discagem?](what-are-dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="c1587-197">For more information, see [What are dial plans?](what-are-dial-plans.md).</span></span>


### <a name="location-based-routing-for-direct-routing"></a><span data-ttu-id="c1587-198">Location-Based roteamento para roteamento direto</span><span class="sxs-lookup"><span data-stu-id="c1587-198">Location-Based Routing for Direct Routing</span></span>

<span data-ttu-id="c1587-199">Em alguns países e regiões, é ilegal ignorar a operadora PSTN para diminuir os custos de chamada de longa distância.</span><span class="sxs-lookup"><span data-stu-id="c1587-199">In some countries and regions, it's illegal to bypass the PSTN carrier to decrease long-distance calling costs.</span></span> <span data-ttu-id="c1587-200">Location-Based (LBR) para Roteamento Direto permite restringir o desvio de chamada para usuários Teams com base em sua localização geográfica.</span><span class="sxs-lookup"><span data-stu-id="c1587-200">Location-Based Routing (LBR) for Direct Routing enables you to restrict toll bypass for Teams users based on their geographic location.</span></span> <span data-ttu-id="c1587-201">Para obter mais informações sobre como planejar e configurar a LBR, consulte os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="c1587-201">For more information about how to plan and configure LBR, see the following articles:</span></span>

- [<span data-ttu-id="c1587-202">Planejar o Roteamento baseado na localização para o Roteamento direto</span><span class="sxs-lookup"><span data-stu-id="c1587-202">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="c1587-203">Configurar definições de rede para o Roteamento baseado na localização</span><span class="sxs-lookup"><span data-stu-id="c1587-203">Configure network settings for Location-Based Routing</span></span>](location-based-routing-configure-network-settings.md)
- [<span data-ttu-id="c1587-204">Habilitar o Roteamento baseado na localização para o Roteamento direto</span><span class="sxs-lookup"><span data-stu-id="c1587-204">Enable Location-Based Routing for Direct Routing</span></span>](location-based-routing-enable.md)
- [<span data-ttu-id="c1587-205">Estudo de caso contoso: Location-Based routing</span><span class="sxs-lookup"><span data-stu-id="c1587-205">Contoso case study: Location-Based Routing</span></span>](voice-case-study-location-based-routing.md)<br>
  <span data-ttu-id="c1587-206">Descreve como uma corporação multi-nacional fictícia, Contoso, implementou Location-Based roteamento para sua organização.</span><span class="sxs-lookup"><span data-stu-id="c1587-206">Describes how a fictional multi-national corporation, Contoso, implemented Location-Based Routing for their organization.</span></span>


### <a name="emergency-calling"></a><span data-ttu-id="c1587-207">Chamada de emergência</span><span class="sxs-lookup"><span data-stu-id="c1587-207">Emergency calling</span></span>

<span data-ttu-id="c1587-208">A forma como você configura a chamada de emergência difere dependendo da sua opção de conectividade PSTN.</span><span class="sxs-lookup"><span data-stu-id="c1587-208">How you configure emergency calling differs depending on your PSTN connectivity option.</span></span>

- <span data-ttu-id="c1587-209">Para o Plano de Chamadas, cada usuário é automaticamente habilitado para chamadas de emergência e é necessário ter um endereço de emergência registrado associado ao número de telefone atribuído.</span><span class="sxs-lookup"><span data-stu-id="c1587-209">For Calling Plan, each user is automatically enabled for emergency calling and is required to have a registered emergency address associated with their assigned telephone number.</span></span> <span data-ttu-id="c1587-210">A chamada de emergência dinâmica (com base no local do Teams cliente) é suportada.</span><span class="sxs-lookup"><span data-stu-id="c1587-210">Dynamic emergency calling (based on the location of the Teams client) is supported.</span></span>  

- <span data-ttu-id="c1587-211">Para Roteamento Direto Teams, você deve definir políticas de chamadas de emergência para usuários usando uma política de roteamento de chamadas de emergência (TeamsEmergencyCallRoutingPolicy) para definir números de emergência e seu destino de roteamento associado.</span><span class="sxs-lookup"><span data-stu-id="c1587-211">For Direct Routing, you must define emergency calling policies for users by using a Teams emergency call routing policy (TeamsEmergencyCallRoutingPolicy) to define emergency numbers and their associated routing destination.</span></span> <span data-ttu-id="c1587-212">Locais de emergência registrados não são suportados para usuários de Roteamento Direto.</span><span class="sxs-lookup"><span data-stu-id="c1587-212">Registered emergency locations are not supported for Direct Routing users.</span></span> <span data-ttu-id="c1587-213">Para chamadas de emergência dinâmicas, a configuração adicional é necessária para roteamento de chamadas de emergência e, possivelmente, para conectividade do parceiro.</span><span class="sxs-lookup"><span data-stu-id="c1587-213">For dynamic emergency calling, additional configuration is required for routing emergency calls and possibly for partner connectivity.</span></span>

- <span data-ttu-id="c1587-214">Para operador Conexão, cada usuário é automaticamente habilitado para chamadas de emergência e é necessário ter um endereço de emergência registrado associado ao número de telefone atribuído, mas só pode ser definido pelo parceiro de operadora.</span><span class="sxs-lookup"><span data-stu-id="c1587-214">For Operator Connect, each user is automatically enabled for emergency calling and is required to have a registered emergency address associated with their assigned telephone number but can only be set by the carrier partner.</span></span> <span data-ttu-id="c1587-215">A chamada de emergência dinâmica (com base no local do Teams cliente) é suportada.</span><span class="sxs-lookup"><span data-stu-id="c1587-215">Dynamic emergency calling (based on the location of the Teams client) is supported.</span></span>

<span data-ttu-id="c1587-216">Para obter mais informações sobre conceitos e terminologia de chamada de emergência e como configurar a chamada de emergência e a chamada de emergência dinâmica, consulte os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="c1587-216">For more information about emergency calling concepts and terminology, and how to configure emergency calling and dynamic emergency calling, see the following articles:</span></span>

- [<span data-ttu-id="c1587-217">Gerenciar chamada de emergência</span><span class="sxs-lookup"><span data-stu-id="c1587-217">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="c1587-218">Planejar e configurar chamadas de emergência dinâmicas</span><span class="sxs-lookup"><span data-stu-id="c1587-218">Plan and configure dynamic emergency calling</span></span>](configure-dynamic-emergency-calling.md)
- [<span data-ttu-id="c1587-219">Gerenciar políticas de chamadas de emergência</span><span class="sxs-lookup"><span data-stu-id="c1587-219">Manage emergency calling policies</span></span>](manage-emergency-calling-policies.md)
- [<span data-ttu-id="c1587-220">Gerenciar políticas de roteamento de chamadas de emergência para Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="c1587-220">Manage emergency call routing policies for Direct Routing</span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="c1587-221">Estudo de caso contoso: Chamada de emergência</span><span class="sxs-lookup"><span data-stu-id="c1587-221">Contoso case study: Emergency calling</span></span>](voice-case-study-emergency-calling.md)<br>
  <span data-ttu-id="c1587-222">Descreve como uma corporação multi-nacional fictícia, Contoso, implementou a chamada de emergência para sua organização.</span><span class="sxs-lookup"><span data-stu-id="c1587-222">Describes how a fictional multi-national corporation, Contoso, implemented emergency calling for their organization.</span></span>


### <a name="network-topology-for-voice-features"></a><span data-ttu-id="c1587-223">Topologia de rede para recursos de voz</span><span class="sxs-lookup"><span data-stu-id="c1587-223">Network topology for voice features</span></span>

<span data-ttu-id="c1587-224">Se você estiver implantando chamadas de emergência dinâmicas ou Location-Based roteamento para Roteamento Direto, você deve configurar configurações de rede para uso com esses recursos em Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c1587-224">If you are deploying dynamic emergency calling or Location-Based Routing for Direct Routing, you must configure network settings for use with these features in Microsoft Teams.</span></span> <span data-ttu-id="c1587-225">Para saber como configurar configurações de rede para regiões de rede, sites de rede, sub-redes de rede e endereços IP confiáveis, consulte os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="c1587-225">To learn how to configure network settings for network regions, network sites, network subnets, and trusted IP addresses, see the following articles:</span></span>

- [<span data-ttu-id="c1587-226">Configurações de rede para recursos de voz na nuvem Microsoft Teams - Conceitos e terminologia</span><span class="sxs-lookup"><span data-stu-id="c1587-226">Network settings for cloud voice features in Microsoft Teams - Concepts and terminology</span></span>](cloud-voice-network-settings.md)
- [<span data-ttu-id="c1587-227">Gerenciar sua topologia de rede para recursos de voz na nuvem Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c1587-227">Manage your network topology for cloud voice features in Microsoft Teams</span></span>](manage-your-network-topology.md)



