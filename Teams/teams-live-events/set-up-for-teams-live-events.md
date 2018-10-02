---
title: Configurar para live eventos no Microsoft Teams
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: tonysmit
search.appverid: MET150
description: Conheça as etapas para configurar ao vivo para eventos no Microsoft Teams, incluindo Otimize sua rede, como atribuir licenças, habilitando o agendamento para usuários e configurando um provedor de eCDN de evento ao vivo.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a6fa8e2bc277bbece7dcbd94fca397e219cdf278
ms.sourcegitcommit: 6447a3aa060452c8d6879524cd6a56aecf33b152
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2018
ms.locfileid: "25354360"
---
# <a name="set-up-for-live-events-in-microsoft-teams"></a><span data-ttu-id="c4230-103">Configurar para live eventos no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c4230-103">Set up for live events in Microsoft Teams</span></span>
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

<span data-ttu-id="c4230-104">Quando você estiver configurando para eventos ao vivo, há diversas etapas que devem ser executadas:</span><span class="sxs-lookup"><span data-stu-id="c4230-104">When you are setting up for live events, there are several steps that you must take:</span></span>

## <a name="step-1-set-up-your-network-for-live-events-in-microsoft-teams"></a><span data-ttu-id="c4230-105">Etapa 1: Configurar sua rede para live eventos no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c4230-105">Step 1: Set up your network for live events in Microsoft Teams</span></span>
<span data-ttu-id="c4230-106">Os eventos de início rápido ao vivo exigem que você preparar [a rede da sua organização para equipes da Microsoft](https://docs.microsoft.com/microsoftteams/prepare-network).</span><span class="sxs-lookup"><span data-stu-id="c4230-106">The quick start live events require you to [prepare your organization's network for Microsoft Teams](https://docs.microsoft.com/microsoftteams/prepare-network).</span></span>  

## <a name="step-2-get-and-assign-licenses"></a><span data-ttu-id="c4230-107">Etapa 2: Comprar e atribuir licenças</span><span class="sxs-lookup"><span data-stu-id="c4230-107">Step 2: Get and assign licenses</span></span>
<span data-ttu-id="c4230-108">Verifique se você tem as atribuições de licença correta para [quem pode criar e agendar eventos ao vivo?](#who-can-create-and-schedule-live-events) e [quem pode assistir eventos ao vivo?](#who-can-watch-live-events).</span><span class="sxs-lookup"><span data-stu-id="c4230-108">Ensure you have correct license assignments for [Who can create and schedule live events?](#who-can-create-and-schedule-live-events) and [Who can watch live events?](#who-can-watch-live-events).</span></span>

## <a name="step-3-enable-live-event-scheduling-for-users"></a><span data-ttu-id="c4230-109">Etapa 3: Habilitar o agendamento de evento ao vivo para usuários</span><span class="sxs-lookup"><span data-stu-id="c4230-109">Step 3: Enable live event scheduling for users</span></span>
<span data-ttu-id="c4230-110">Evento ao vivo agendamento é habilitado por padrão para os usuários de equipes, mas se você estiver buscando os usuários agendem eventos externos codificador há etapas adicionais que você deve fazer.</span><span class="sxs-lookup"><span data-stu-id="c4230-110">Live event scheduling is enabled by default for Teams users but if you are wanting users to schedule external encoder events there are additional steps that you must do.</span></span>

### <a name="for-quick-start-events"></a><span data-ttu-id="c4230-111">Eventos de início rápido</span><span class="sxs-lookup"><span data-stu-id="c4230-111">For quick start events</span></span>
<span data-ttu-id="c4230-112">Use a configuração *AllowBroadcastScheduling* no **TeamsMeetingBroadcastPolicy** no PowerShell equipes para controlar se o usuário pode criar eventos ao vivo em equipes ou não.</span><span class="sxs-lookup"><span data-stu-id="c4230-112">Use the setting *AllowBroadcastScheduling* in **TeamsMeetingBroadcastPolicy** in Teams PowerShell to control whether the user can create live events in Teams or not.</span></span> <span data-ttu-id="c4230-113">Saiba mais sobre como gerenciar TeamsMeetingBroadcastPolicy [aqui](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="c4230-113">You can learn more about managing TeamsMeetingBroadcastPolicy [here](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

 <span data-ttu-id="c4230-114">Se você ainda não atribuída uma política personalizada atribuída aos usuários, os usuários receberá a política *Global* , que tem a gravação habilitada por padrão.</span><span class="sxs-lookup"><span data-stu-id="c4230-114">If you haven't assigned a custom policy assigned to the users, the users will get the *Global* policy, which has recording enabled by default.</span></span>

<span data-ttu-id="c4230-115">Verifique se o parâmetro *AllowBroadcastScheduling* estiver definido como *True*:</span><span class="sxs-lookup"><span data-stu-id="c4230-115">Verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="c4230-116">Atribua o usuário para a política *Global* , execute:</span><span class="sxs-lookup"><span data-stu-id="c4230-116">Then assign the user to the *Global* policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

#### <a name="user-scenarios"></a><span data-ttu-id="c4230-117">Cenários de usuário</span><span class="sxs-lookup"><span data-stu-id="c4230-117">User scenarios</span></span>
<span data-ttu-id="c4230-118">**Você deseja todos os usuários da sua empresa, possam criar eventos ao vivo.**</span><span class="sxs-lookup"><span data-stu-id="c4230-118">**You want all users in your company to be able to create live events.**</span></span>

<span data-ttu-id="c4230-119">Se os usuários são atribuídos a política *Glocal* , execute e confirme que *AllowBroadcastScheduling* \* estiver definida como *True*:</span><span class="sxs-lookup"><span data-stu-id="c4230-119">If users are assigned the *Glocal* policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="c4230-120">Se os usuários recebem uma política que não seja a política *Global* , execute o seguinte e verificar se a opção *-AllowBroadcastScheduling* está definida como *True*:</span><span class="sxs-lookup"><span data-stu-id="c4230-120">If the users are assigned a policy other than the *Global* policy, run the following and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```

<span data-ttu-id="c4230-121">**Você desejar que o evento ao vivo planejamento ser desabilitado de 100% em sua organização.**</span><span class="sxs-lookup"><span data-stu-id="c4230-121">**You want live event scheduling to be 100% disabled across your organization.**</span></span>

<span data-ttu-id="c4230-122">Desabilitar o agendamento de transmissão, execute:</span><span class="sxs-lookup"><span data-stu-id="c4230-122">Disable broadcast scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="c4230-123">Atribua a todos os usuários em sua organização para a política *Global* , execute:</span><span class="sxs-lookup"><span data-stu-id="c4230-123">Assign all users in your organization to the *Global* policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="c4230-124">**Você deseja que um grande número de usuários possam criar eventos ao vivo, mas deseja impedir que um conjunto de usuários criá-los.**</span><span class="sxs-lookup"><span data-stu-id="c4230-124">**You want a large number of users to be able to create live events, but want to prevent a set of users from creating them.**</span></span>

<span data-ttu-id="c4230-125">Atribuir a política *Global* usando o **Grant-CsTeamsMeetingBroadcastPolicy** para alguns dos usuários (que você deseja enabled), mas primeiro execute o seguinte e verificar se *AllowBroadcastScheduling* está definida como *True*:</span><span class="sxs-lookup"><span data-stu-id="c4230-125">Assign the *Global* policy using the **Grant-CsTeamsMeetingBroadcastPolicy** for some of the users (that you want enabled) but first run the following and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="c4230-126">Atribua um ou mais usuários à política *Global* , execute:</span><span class="sxs-lookup"><span data-stu-id="c4230-126">Then assign a user or users to the *Global* policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="c4230-127">Crie e atribua uma diretiva para desabilitar o agendamento usando o cmdlet **Grant-CsTeamsMeetingBroadcastPolicy** para os outros usuários (serem desabilitadas).</span><span class="sxs-lookup"><span data-stu-id="c4230-127">Create and assign a policy for disabling scheduling using the  **Grant-CsTeamsMeetingBroadcastPolicy** cmdlet to the other users (you want disabled).</span></span> 

<span data-ttu-id="c4230-128">Criar a nova diretiva com ele desabilitada, execute:</span><span class="sxs-lookup"><span data-stu-id="c4230-128">Create the new policy with it disabled, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -identity DisabledBroadcastSchedulingpolicy
```
<span data-ttu-id="c4230-129">Desabilitar o agendamento, execute:</span><span class="sxs-lookup"><span data-stu-id="c4230-129">Disable scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity DisabledBroadcastSchedulingpolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="c4230-130">Atribua usuários a essa diretiva, execute:</span><span class="sxs-lookup"><span data-stu-id="c4230-130">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingpolicy -Verbose
```
<span data-ttu-id="c4230-131">**Você deseja eventos ao vivo devem ser desabilitados para um grande número de usuários, mas deseja permitir que um conjunto de usuários para criá-los.**</span><span class="sxs-lookup"><span data-stu-id="c4230-131">**You want live events to be disabled for a large number of the users, but want to allow a set of users to create them.**</span></span>

<span data-ttu-id="c4230-132">Desabilitar o agendamento de transmissão, execute:</span><span class="sxs-lookup"><span data-stu-id="c4230-132">Disable broadcast scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="c4230-133">Em seguida, atribua esses usuários para a política *Global* , execute:</span><span class="sxs-lookup"><span data-stu-id="c4230-133">Then assign those users to the *Global* policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="c4230-134">Criar e atribuir uma política para habilitar o agendamento, execute:</span><span class="sxs-lookup"><span data-stu-id="c4230-134">Create and assign a policy for enabling scheduling, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="c4230-135">Habilite o agendamento, execute:</span><span class="sxs-lookup"><span data-stu-id="c4230-135">Enable scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="c4230-136">Atribua usuários a essa diretiva, execute:</span><span class="sxs-lookup"><span data-stu-id="c4230-136">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```

### <a name="for-external-encoder-events"></a><span data-ttu-id="c4230-137">Para eventos externos codificador</span><span class="sxs-lookup"><span data-stu-id="c4230-137">For external encoder events</span></span>
<span data-ttu-id="c4230-138">Você deve fazer o seguinte procedimento para habilitar o agendamento para os usuários de evento ao vivo.</span><span class="sxs-lookup"><span data-stu-id="c4230-138">You must do the following to enable live event scheduling for those users.</span></span>

#### <a name="step-1-enable-microsoft-stream-for-users-in-your-organization"></a><span data-ttu-id="c4230-139">Etapa 1: Habilitar o Microsoft Stream para usuários em sua organização \* \*</span><span class="sxs-lookup"><span data-stu-id="c4230-139">Step 1: Enable Microsoft Stream for users in your organization\*\*</span></span>
<span data-ttu-id="c4230-140">Microsoft Stream está disponível como parte das assinaturas do Office 365 elegíveis ou como um serviço autônomo.</span><span class="sxs-lookup"><span data-stu-id="c4230-140">Microsoft Stream is available as part of eligible Office 365 subscriptions or as a standalone service.</span></span> <span data-ttu-id="c4230-141">Para obter mais detalhes, consulte [Visão geral do licenciamento de Stream](https://docs.microsoft.com/stream/license-overview) .</span><span class="sxs-lookup"><span data-stu-id="c4230-141">See [Stream licensing overview](https://docs.microsoft.com/stream/license-overview) for more details.</span></span>

> <span data-ttu-id="c4230-142">! [NOTA] Microsoft Stream não está incluído nos planos Business Essentials ou Business Premium.</span><span class="sxs-lookup"><span data-stu-id="c4230-142">![NOTE] Microsoft Stream is not included in Business Essentials or Business Premium plans.</span></span>  

<span data-ttu-id="c4230-143">Saiba mais sobre como você pode [Atribuir licenças aos usuários no Office 365](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) para que os usuários podem acessar o Microsoft Stream.</span><span class="sxs-lookup"><span data-stu-id="c4230-143">Learn more about how you can [assign licenses to users in Office 365](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) so that users can access Microsoft Stream.</span></span> <span data-ttu-id="c4230-144">Certifique-se de que Microsoft Stream não é bloqueado para os usuários conforme definido [neste](https://docs.microsoft.com/stream/disable-user-organization)artigo.</span><span class="sxs-lookup"><span data-stu-id="c4230-144">Ensure Microsoft Stream is not blocked for the users as defined in [this article](https://docs.microsoft.com/stream/disable-user-organization).</span></span>

#### <a name="step-2-ensure-users-have-live-event-creation-permission-in-microsoft-stream"></a><span data-ttu-id="c4230-145">Etapa 2: Verifique se os usuários têm permissão de criação de evento ao vivo na Microsoft Stream \* \*</span><span class="sxs-lookup"><span data-stu-id="c4230-145">Step 2: Ensure users have live event creation permission in Microsoft Stream\*\*</span></span>
<span data-ttu-id="c4230-146">Por padrão, os administradores podem criar codificador externa a eventos ao vivo.</span><span class="sxs-lookup"><span data-stu-id="c4230-146">By default, administrators can create external encoder live events.</span></span> <span data-ttu-id="c4230-147">Administrador do Microsoft Stream pode [Permitir que usuários adicionais para criação de evento ao vivo](https://docs.microsoft.com/stream/live-event-administration#enabling-and-restricting-users-to-creating) no fluxo.</span><span class="sxs-lookup"><span data-stu-id="c4230-147">Microsoft Stream administrator can [enable additional users for live event creation](https://docs.microsoft.com/stream/live-event-administration#enabling-and-restricting-users-to-creating) in Stream.</span></span>  

#### <a name="step-3-ensure-live-event-organizers-have-consented-to-the-company-policy-set-by-stream-admin"></a><span data-ttu-id="c4230-148">Etapa 3: Verifique se o evento ao vivo organizadores tem consentiu a política da empresa definida pelo fluxo admin \* \*</span><span class="sxs-lookup"><span data-stu-id="c4230-148">Step 3: Ensure live event organizers have consented to the company policy set by Stream admin\*\*</span></span>
<span data-ttu-id="c4230-149">Se um administrador do Microsoft Stream [definir uma política de diretrizes da empresa](https://docs.microsoft.com/stream/company-policy-and-consent) e requer funcionários aceitar essa política antes de salvar conteúdo, em seguida, os usuários devem fazer isso antes de criar um evento ao vivo (com a produção de codificador externo) em equipes.</span><span class="sxs-lookup"><span data-stu-id="c4230-149">If a Microsoft Stream administrator has [set up a company guidelines policy](https://docs.microsoft.com/stream/company-policy-and-consent) and requires employees to accept this policy before saving content, then users must do so before creating a live event (with External Encoder production) in Teams.</span></span> <span data-ttu-id="c4230-150">Antes da distribuição o recurso de eventos ao vivo na organização, certifique-se de tem consentiu usuários que criarão esses eventos ao vivo a política.</span><span class="sxs-lookup"><span data-stu-id="c4230-150">Before you rollout the live events feature in the organization, make sure users who will be creating these live events have consented to the policy.</span></span> 

## <a name="step-4-set-up-ecdn-provider-for-live-events-in-microsoft-teams"></a><span data-ttu-id="c4230-151">Etapa 4: Configurar o provedor de eCDN para live eventos no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c4230-151">Step 4: Set up eCDN provider for live events in Microsoft Teams</span></span> 
<span data-ttu-id="c4230-152">Reprodução de vídeos do evento ao vivo usa a taxa de bits adaptável streaming (ABR), mas é um fluxo de unicast, que significa que cada visualizador está recebendo o seu próprio fluxo de vídeo da internet.</span><span class="sxs-lookup"><span data-stu-id="c4230-152">Playback of live event videos uses adaptive bitrate streaming (ABR) but it is a unicast stream, meaning every viewer is getting their own video stream from the internet.</span></span> <span data-ttu-id="c4230-153">Para eventos ao vivo ou vídeos enviados para grandes partes da sua organização, pode haver uma quantidade significativa de largura de banda de internet consumida por visualizadores.</span><span class="sxs-lookup"><span data-stu-id="c4230-153">For live events or videos sent out to large portions of your organization, there could be a significant amount of internet bandwidth consumed by viewers.</span></span> <span data-ttu-id="c4230-154">Para organizações que desejam reduzir esse tráfego da internet para eventos ao vivo, eventos ao vivo soluções integradas da Microsoft confiam definidos de parceiros de entrega de vídeo oferecem software redes (SDNs) ou redes de fornecimento de conteúdo corporativo (eCDNs).</span><span class="sxs-lookup"><span data-stu-id="c4230-154">For organizations that want to reduce this internet traffic for live events, live events solutions are integrated with Microsoft's trusted video delivery partners offering software defined networks (SDNs) or enterprise content delivery networks (eCDNs).</span></span> <span data-ttu-id="c4230-155">Esses SDN eCDN plataformas permitem que as organizações a otimizar a largura de banda de rede sem prejudicar o usuário final experiências de exibição.</span><span class="sxs-lookup"><span data-stu-id="c4230-155">These SDN / eCDN platforms enable organizations to optimize network bandwidth without sacrificing end user viewing experiences.</span></span> <span data-ttu-id="c4230-156">Nossos parceiros podem ajudar a habilitar uma distribuição mais flexível e eficiente de vídeo em sua rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="c4230-156">Our partners can help enable a more scalable and efficient video distribution across your enterprise network.</span></span>

<span data-ttu-id="c4230-157">**Compra & instalação sua solução fora do Microsoft Teams** Obtenha ajuda especializada com o dimensionamento de entrega de vídeo aproveitando parceiros de entrega confiável de vídeo da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c4230-157">**Purchase & setup your solution outside of Microsoft Teams** Get expert help with scaling video delivery by leveraging Microsoft’s trusted video delivery partners.</span></span> <span data-ttu-id="c4230-158">Para poder habilitar um provedor de entrega de vídeo ser usado com equipes, você deve adquirir e a solução SDN/eCDN externamente e separada das equipes de instalação.</span><span class="sxs-lookup"><span data-stu-id="c4230-158">Before you can enable a video delivery provider to be used with Teams you must purchase and setup the SDN/eCDN solution outside and separate from Teams.</span></span>

<span data-ttu-id="c4230-159">As seguintes soluções SDN/eCDN previamente são integradas e podem ser configurado para ser usado com o Microsoft Stream.</span><span class="sxs-lookup"><span data-stu-id="c4230-159">The following SDN/eCDN solutions are pre-integrated and can be setup to be used with Microsoft Stream.</span></span>

- <span data-ttu-id="c4230-160">**Hive Streaming** fornece uma solução simple e eficiente para distribuição de vídeo da empresa ao vivo e sob demanda.</span><span class="sxs-lookup"><span data-stu-id="c4230-160">**Hive Streaming** provides a simple and powerful solution for live and on-demand enterprise video distribution.</span></span> <span data-ttu-id="c4230-161">Hive é uma solução baseada em software que não exige nenhum hardware adicional ou a largura de banda e fornece uma maneira segura para habilitar milhares de visualizadores de vídeos simultâneos sem afetar a sua rede.</span><span class="sxs-lookup"><span data-stu-id="c4230-161">Hive is a software-based solution that requires no additional hardware or bandwidth and provides a secure way to enable thousands of simultaneous video viewers without impact to your network.</span></span> <span data-ttu-id="c4230-162">Para clientes que desejem para entender que o vídeo do impacto está tendo em sua rede antes da compra de uma solução SDN/eCDN, Hive Streaming também fornece uma solução de análise baseada em navegador para os clientes da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c4230-162">For customers looking to understand the impact video is having on their network prior to purchasing an SDN/eCDN solution, Hive Streaming also provides a browser-based analytics solution for Microsoft customers.</span></span> <span data-ttu-id="c4230-163">[Saiba mais](https://www.hivestreaming.com/partners/integration-partners/microsoft/).</span><span class="sxs-lookup"><span data-stu-id="c4230-163">[Learn more](https://www.hivestreaming.com/partners/integration-partners/microsoft/).</span></span>
 
- <span data-ttu-id="c4230-164">**Kollective** é uma baseada na nuvem inteligente aos distribuição plataforma, que aproveita a infra-estrutura de rede existente para entregar conteúdo, em vários formulários, (live streaming de vídeo, vídeo sob demanda, atualizações de software, patches de segurança, etc.) com mais rapidamente e confiável e com menos largura de banda.</span><span class="sxs-lookup"><span data-stu-id="c4230-164">**Kollective** is a cloud-based, smart peering distribution platform that leverages your existing network infrastructure to deliver content, in many forms, (live streaming video, on-demand video, software updates, security patches, etc.) faster, more reliably and with less bandwidth.</span></span> <span data-ttu-id="c4230-165">Nossa plataforma segura é confiável por maiores instituições financeiras de todo o mundo e sem hardware adicional, são fáceis de instalação e manutenção.</span><span class="sxs-lookup"><span data-stu-id="c4230-165">Our secure platform is trusted by the world’s largest financial institutions and with no additional hardware, setup and maintenance are easy.</span></span> <span data-ttu-id="c4230-166">[Saiba mais](http://www.kollective.com).</span><span class="sxs-lookup"><span data-stu-id="c4230-166">[Learn more](http://www.kollective.com).</span></span>
 
- <span data-ttu-id="c4230-167">**Conheça OmniCache** fornece a distribuição de rede de última geração e garante perfeito fornecimento de conteúdo de vídeo entre WANs globais, ajudando produtores de evento otimizar a largura de banda de rede e suporte difusões bem-sucedida evento ao vivo e sob demanda Streaming.</span><span class="sxs-lookup"><span data-stu-id="c4230-167">**Ramp OmniCache** provides next-generation network distribution and ensures seamless delivery of video content across global WANs, helping event producers optimize network bandwidth and support successful live event broadcasts and on-demand streaming.</span></span> <span data-ttu-id="c4230-168">O suporte para OmniCache conheça para eventos ao vivo do início rápido estarão disponíveis em breve.</span><span class="sxs-lookup"><span data-stu-id="c4230-168">The support for Ramp OmniCache for quick start live events is coming soon.</span></span>  <span data-ttu-id="c4230-169">[Saiba mais](http://www.ramp.com).</span><span class="sxs-lookup"><span data-stu-id="c4230-169">[Learn more](http://www.ramp.com).</span></span> 
 
> [!NOTE] 
> <span data-ttu-id="c4230-170">Sua solução eCDN escolhida está sujeito selecionado de **termos do provedor de terceiros 3º da política de privacidade e de serviço**, quais rege o uso da solução do provedor eCDN.</span><span class="sxs-lookup"><span data-stu-id="c4230-170">Your chosen eCDN solution is subject to the selected **3rd party provider’s terms of service and privacy policy**, which will governs your use of the eCDN provider’s solution.</span></span> <span data-ttu-id="c4230-171">O uso da solução do provedor eCDN não estará sujeito a termos de licenciamento de volume do Microsoft ou termos de serviços Online.</span><span class="sxs-lookup"><span data-stu-id="c4230-171">Your use of the eCDN provider’s solution will not be subject to the Microsoft volume licensing terms or Online Services Terms.</span></span> <span data-ttu-id="c4230-172">Se não concordar com os **termos do provedor de terceiros 3º**, não habilite a solução eCDN em equipes.</span><span class="sxs-lookup"><span data-stu-id="c4230-172">If you do not agree to the **3rd party provider’s terms**, then don't enable the eCDN solution in Teams.</span></span> 

<span data-ttu-id="c4230-173">**Configurar um eCDN para "Quick start" eventos ao vivo** Você pode configurar o provedor de eCDN para eventos ao vivo em equipes usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c4230-173">**Set up an eCDN for "Quick start" live events** You can configure eCDN provider for live events in Teams using PowerShell.</span></span> 

> [!NOTE] 
> <span data-ttu-id="c4230-174">Um provedor de eCDN único pode ser configurado para sua organização.</span><span class="sxs-lookup"><span data-stu-id="c4230-174">A single eCDN provider can be configured for your organization.</span></span> 

<span data-ttu-id="c4230-175">***Hive*** Você pode usar o cmdlet [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) do PowerShell para configurar o provedor de eCDN.</span><span class="sxs-lookup"><span data-stu-id="c4230-175">***Hive*** You can use [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) PowerShell cmdlet to configure eCDN provider.</span></span> <span data-ttu-id="c4230-176">Primeiro, obtenha a URL do modelo ID e a API de licença de seu contato Hive, em seguida, execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c4230-176">First obtain the license ID and API template URL from your Hive contact then run the following:</span></span>
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
<span data-ttu-id="c4230-177">***Kollective*** Você pode usar o cmdlet [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) do PowerShell para configurar o provedor de eCDN.</span><span class="sxs-lookup"><span data-stu-id="c4230-177">***Kollective*** You can use [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) PowerShell cmdlet to configure eCDN provider.</span></span> <span data-ttu-id="c4230-178">Primeiro obter o token de API e a URL do modelo de API do seu contato Kollective, depois, execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c4230-178">First obtain the API token and the API template URL from your Kollective contact, then run the following:</span></span>
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
<span data-ttu-id="c4230-179">**Configurar um eCDN para eventos de "Codificador externo" ao vivo**</span><span class="sxs-lookup"><span data-stu-id="c4230-179">**Set up an eCDN for "External encoder" live events**</span></span> 

<span data-ttu-id="c4230-180">Se você planeja criar eventos ao vivo que usam codificadores externos, você precisará [configurar seu provedor de eCDN com Microsoft Stream](https://docs.microsoft.com/stream/network-caching) também.</span><span class="sxs-lookup"><span data-stu-id="c4230-180">If you plan to create live events that use external encoders, you will need to [configure your eCDN provider with Microsoft Stream](https://docs.microsoft.com/stream/network-caching) as well.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="c4230-181">Próximos passos</span><span class="sxs-lookup"><span data-stu-id="c4230-181">Next steps</span></span>
<span data-ttu-id="c4230-182">Vá para [equipes Confgure live eventos](configure-teams-live-events.md).</span><span class="sxs-lookup"><span data-stu-id="c4230-182">Go to [Confgure Teams live events](configure-teams-live-events.md).</span></span>
