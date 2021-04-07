---
title: Orientação do Microsoft Teams sobre largura de banda baixa para EDU
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: jesegher
description: Artigo do Microsoft Teams para EDU para ajudar com problemas de vídeo e reuniões relacionados à baixa largura de banda. Quer você seja um pai, um educador ou um administrador de TI, você tem opções para melhorar a experiência com o Teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 17520645f23500550c6bc991c9d25ad2f72b2b6e
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598420"
---
# <a name="help-for-low-bandwidth-situations-for-teams-for-edu"></a><span data-ttu-id="e6a95-104">Ajuda para situações de baixa largura de banda para Teams para EDU</span><span class="sxs-lookup"><span data-stu-id="e6a95-104">Help for low-bandwidth situations for Teams for EDU</span></span>

<span data-ttu-id="e6a95-105">Existem vários elementos de rede quando se trata de trabalhar com o Microsoft Teams que podem afetar o desempenho.</span><span class="sxs-lookup"><span data-stu-id="e6a95-105">There are numerous network elements when it comes to working with Microsoft Teams that can affect performance.</span></span> <span data-ttu-id="e6a95-106">A largura de banda baixa é uma das situações que pode parecer totalmente fora de seu controle.</span><span class="sxs-lookup"><span data-stu-id="e6a95-106">Low bandwidth is one of the situations that can feel entirely out of your control.</span></span> <span data-ttu-id="e6a95-107">Considere as seguintes situações:</span><span class="sxs-lookup"><span data-stu-id="e6a95-107">Consider the following situations:</span></span>

- <span data-ttu-id="e6a95-108">Uma conexão de internet de baixa velocidade para a escola.</span><span class="sxs-lookup"><span data-stu-id="e6a95-108">A low-speed internet connection for the school.</span></span>
- <span data-ttu-id="e6a95-109">Uma conexão de internet de baixa velocidade para um ou mais alunos.</span><span class="sxs-lookup"><span data-stu-id="e6a95-109">A low-speed internet connection for one or more students.</span></span>
- <span data-ttu-id="e6a95-110">Horários do dia em que há pouca largura de banda devido ao uso da rede em uma área.</span><span class="sxs-lookup"><span data-stu-id="e6a95-110">Times of the day when there's low bandwidth because of network usage in an area.</span></span>
- <span data-ttu-id="e6a95-111">Períodos de baixa largura de banda devido a interrupções locais nem para a escola nem para os alunos, mas que afetam o desempenho.</span><span class="sxs-lookup"><span data-stu-id="e6a95-111">Low-bandwidth periods because of outages local to neither the school nor to students, but, which affect performance nonetheless.</span></span>
- <span data-ttu-id="e6a95-112">Problemas sem largura de banda (por exemplo, problemas com hardware) que se disfarçam como problemas de largura de banda baixa.</span><span class="sxs-lookup"><span data-stu-id="e6a95-112">Non-bandwidth issues (for example, issues with hardware) that masquerade as low-bandwidth issues.</span></span>

<span data-ttu-id="e6a95-113">Este artigo fornecerá as melhores práticas a serem seguidas para várias atividades do Teams quando você se deparar com um problema de largura de banda baixa.</span><span class="sxs-lookup"><span data-stu-id="e6a95-113">This article will give you best practices to follow for various Teams activities when you're faced with a low-bandwidth issue.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e6a95-114">Aqui tem informação sobre [Como o Microsoft Teams utiliza memória](teams-memory-usage-perf.md), porque além dos problemas de baixa largura de banda, você pode ter problemas com os recursos do seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e6a95-114">There's information here on [How Microsoft Teams uses memory](teams-memory-usage-perf.md), because in addition to low bandwidth problems, you may be having resource issues on your device.</span></span> <span data-ttu-id="e6a95-115">Se você estiver procurando por diretrizes de rede do Microsoft Teams, confira [Preparar a rede da sua organização para o Microsoft Teams](prepare-network.md).</span><span class="sxs-lookup"><span data-stu-id="e6a95-115">If you're looking for network guidance for Microsoft Teams, review [Prepare your organization's network for Microsoft Teams](prepare-network.md).</span></span>

## <a name="resolving-low-bandwidth-issues-for-admins"></a><span data-ttu-id="e6a95-116">Resolvendo problemas de baixa largura de banda para administradores</span><span class="sxs-lookup"><span data-stu-id="e6a95-116">Resolving low-bandwidth issues for Admins</span></span>

<span data-ttu-id="e6a95-117">O importante a se lembrar, como administrador de TI, é que, embora você tenha soluções para problemas de baixa largura de banda amplamente difundidos que resolverão os problemas rapidamente, as soluções devem ser consideradas com cuidado.</span><span class="sxs-lookup"><span data-stu-id="e6a95-117">The important thing to remember, as an IT Admin, is that while you have solutions for low-bandwidth issues that are wide-spread that will resolve problems quickly, solutions should be considered carefully.</span></span> <span data-ttu-id="e6a95-118">Alguns problemas podem ser resolvidos com um enfoque mais restrito ao educador ou mesmo ao nível do aluno/pai.</span><span class="sxs-lookup"><span data-stu-id="e6a95-118">Some issues may be able to resolve with a more narrow focus taken at the educator or even the student/parent level.</span></span>

<span data-ttu-id="e6a95-119">Resumindo, se o problema de largura de banda baixa ocorre para um grande grupo de alunos, agir como um administrador de TI faz sentido, e também faz sentido se as ações realizadas no nível do aluno/educador não foram úteis.</span><span class="sxs-lookup"><span data-stu-id="e6a95-119">In short, if the low-bandwidth issue occurs for a wide group of students, taking action as an IT Admin makes sense, and it also makes sense if the actions taken at the student/educator level haven't been helpful.</span></span>

> [!NOTE]
> <span data-ttu-id="e6a95-120">Se você tem a oportunidade de investir, o [Guia de Revisão de Qualidade da Experiência](quality-of-experience-review-guide.md) é uma leitura válida (não é específica de EDU, mas ainda assim terá informações valiosas).</span><span class="sxs-lookup"><span data-stu-id="e6a95-120">If you've got the time to invest, the [Quality of Experience Review Guide](quality-of-experience-review-guide.md) is a worthwhile read (this is not EDU-specific, but it will still have valuable information).</span></span> <span data-ttu-id="e6a95-121">Isso permitirá que Administradores de TI experientes se aprofundem na experiência dos professores e alunos.</span><span class="sxs-lookup"><span data-stu-id="e6a95-121">This guide will allow experienced IT Admins to go in-depth on the experience for their educators and students.</span></span>

### <a name="meetings-and-video"></a><span data-ttu-id="e6a95-122">Reuniões e vídeo</span><span class="sxs-lookup"><span data-stu-id="e6a95-122">Meetings and video</span></span>

<span data-ttu-id="e6a95-123">Um foco principal para problemas de baixa largura de banda são as reuniões; especificamente, vídeo em reuniões.</span><span class="sxs-lookup"><span data-stu-id="e6a95-123">A primary focus for low-bandwidth issues is meetings; specifically, video in meetings.</span></span> <span data-ttu-id="e6a95-124">Um administrador de TI deve considerar as ações abaixo ao lidar com problemas relatados por alunos ou educadores em relação a ter a melhor experiência de reunião em um ambiente educacional.</span><span class="sxs-lookup"><span data-stu-id="e6a95-124">An IT Admin should consider the actions below when dealing with issues reported by students or educators in regard to having the best meeting experience in an educational setting.</span></span>

#### <a name="meeting-policies"></a><span data-ttu-id="e6a95-125">Políticas de reunião</span><span class="sxs-lookup"><span data-stu-id="e6a95-125">Meeting policies</span></span>

<span data-ttu-id="e6a95-126">Em relação às reuniões, uma das áreas mais preocupantes para situações de baixa largura de banda tem a ver com os vídeos.</span><span class="sxs-lookup"><span data-stu-id="e6a95-126">Regarding meetings, one of the most concerning areas for low-bandwidth situations has to do with videos.</span></span> <span data-ttu-id="e6a95-127">Além do Teams serem capazes de escalar para a largura de banda detectada automaticamente, você, como administrador de TI, tem opções de política que pode definir no nível por organizador e/ou por usuário.</span><span class="sxs-lookup"><span data-stu-id="e6a95-127">In addition to Teams being able to scale to detected bandwidth automatically, you as an IT Admin have policy options you can set at the per-organizer and/or per-user level.</span></span> <span data-ttu-id="e6a95-128">Essas opções permitem que você dê a todos a melhor experiência em relação à largura de banda com a qual precisam trabalhar em um determinado momento.</span><span class="sxs-lookup"><span data-stu-id="e6a95-128">These options allow you to give everyone the best experience in light of the bandwidth they have to work with at a given time.</span></span>

<span data-ttu-id="e6a95-129">Algumas das coisas que você pode definir por meio da política incluem:</span><span class="sxs-lookup"><span data-stu-id="e6a95-129">Some of the things you can set via policy include:</span></span>

- <span data-ttu-id="e6a95-130">Desabilitar o vídeo completamente, para que ninguém possa habilitá-lo.</span><span class="sxs-lookup"><span data-stu-id="e6a95-130">Disabling video altogether, so no one could enable it.</span></span>
- <span data-ttu-id="e6a95-131">Taxa de bits de mídia (esta configuração é definida por usuário).</span><span class="sxs-lookup"><span data-stu-id="e6a95-131">Media bit rate (this setting is set per-user).</span></span>

<span data-ttu-id="e6a95-132">Para saber mais sobre suas opções e para percorrer os detalhes de quais políticas você precisa definir para reuniões e vídeo, verifique as [configurações de política de reunião no Teams: áudio e vídeo](meeting-policies-audio-and-video.md).</span><span class="sxs-lookup"><span data-stu-id="e6a95-132">To learn more about your options, and to walk through the specifics of what policies you'd need to set for meetings and video, check out [Meeting policy settings in Teams: Audio and video](meeting-policies-audio-and-video.md).</span></span>

#### <a name="screen-sharing-policies"></a><span data-ttu-id="e6a95-133">Políticas de compartilhamento de tela</span><span class="sxs-lookup"><span data-stu-id="e6a95-133">Screen sharing policies</span></span>

<span data-ttu-id="e6a95-134">Em outros casos, professores podem estar compartilhando toda a tela com os alunos, quando o compartilhamento deve ser limitado a um aplicativo relevante à lição que está sendo ensinada.</span><span class="sxs-lookup"><span data-stu-id="e6a95-134">In other cases, educators may be sharing their entire screen to students, when sharing should be limited to an application relevant to the lesson being taught.</span></span> <span data-ttu-id="e6a95-135">Essa configuração também pode ser definida por meio de política, se essa for uma maneira mais desejável de fazer isso do que ter educadores fazendo essa escolha individualmente.</span><span class="sxs-lookup"><span data-stu-id="e6a95-135">This setting can also be set via policy, if that's a more desirable way to do it than to have educators making that choice individually.</span></span>

<span data-ttu-id="e6a95-136">Para ter uma boa ideia do que você pode fazer para limitar o compartilhamento de tela por meio de configurações de política, verifique as [configurações de política de Reunião no Teams: áudio e vídeo](meeting-policies-audio-and-video.md).</span><span class="sxs-lookup"><span data-stu-id="e6a95-136">For a good idea of what you can do about limiting screen sharing via policy settings, check out [Meeting policy settings in Teams: Audio and video](meeting-policies-audio-and-video.md).</span></span>

#### <a name="dial-in-number-for-meetings"></a><span data-ttu-id="e6a95-137">Números de discagem para reuniões</span><span class="sxs-lookup"><span data-stu-id="e6a95-137">Dial-in number for meetings</span></span>

<span data-ttu-id="e6a95-138">Pode ser mais fácil para os alunos tentarem discagem para algumas sessões da sala de aula.</span><span class="sxs-lookup"><span data-stu-id="e6a95-138">It may be easier for some students to attempt to dial in to some classroom sessions.</span></span> <span data-ttu-id="e6a95-139">Você pode fornecer um número de discagem para reuniões no Teams, para que os alunos com dificuldades possam telefonar como uma alternativa para participar de uma reunião de vídeo.</span><span class="sxs-lookup"><span data-stu-id="e6a95-139">You can provide a dial-in number for Teams meetings, so students with issues can phone in as an alternative to attending a video meeting.</span></span>

<span data-ttu-id="e6a95-140">Para saber mais sobre isso, você pode ler [Definir os números de telefone incluídos em convites no Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="e6a95-140">For more information on this, you can read [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>

## <a name="low-bandwidth-scenarios-as-an-educator"></a><span data-ttu-id="e6a95-141">Cenários de baixa largura de banda como educador</span><span class="sxs-lookup"><span data-stu-id="e6a95-141">Low-bandwidth scenarios as an educator</span></span>

<span data-ttu-id="e6a95-142">Os educadores devem se sentir capacitados para tomar medidas para resolver problemas de baixa largura de banda e podem ser uma escolha superior à ação do Administrador de TI nas seguintes situações:</span><span class="sxs-lookup"><span data-stu-id="e6a95-142">Educators should feel empowered to take steps to resolve low-bandwidth issues, and may be a superior choice to IT Admin action in the following situations:</span></span>

- <span data-ttu-id="e6a95-143">Se o problema for intermitente ou relativamente passageiro.</span><span class="sxs-lookup"><span data-stu-id="e6a95-143">If the problem is intermittent, or relatively transitory.</span></span>
- <span data-ttu-id="e6a95-144">Se houver um horário específico do dia em que você pode antecipar a existência de um problema ou se o período de baixa largura de banda tiver alguma previsibilidade.</span><span class="sxs-lookup"><span data-stu-id="e6a95-144">If there is a specific time of the day you can anticipate there being an issue, or the low bandwidth period has some predictability to it.</span></span>

<span data-ttu-id="e6a95-145">Nesses casos, você pode executar algumas ações.</span><span class="sxs-lookup"><span data-stu-id="e6a95-145">In these situations, you can take some actions.</span></span>

<span data-ttu-id="e6a95-146">Para obter mais informações, confira [Usar o Teams para a trabalhos escolares quando a largura de banda estiver baixa](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262).</span><span class="sxs-lookup"><span data-stu-id="e6a95-146">For more information, check out [Use Teams for schoolwork when bandwidth is low](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262).</span></span>

## <a name="low-bandwidth-scenarios-as-a-parent-or-student"></a><span data-ttu-id="e6a95-147">Cenários de baixa largura de banda como pai ou aluno</span><span class="sxs-lookup"><span data-stu-id="e6a95-147">Low-bandwidth scenarios as a parent or student</span></span>

<span data-ttu-id="e6a95-148">Há situações também, e você deve discuti-las proativamente com seus professores, onde o problema de largura de banda pode estar no lado do aluno (por exemplo, um grande número de alunos pode assistir as lições de vídeo sem problemas, mas um pequeno número de alunos pode ter dificuldades).</span><span class="sxs-lookup"><span data-stu-id="e6a95-148">There are also situations, and you should proactively discuss them with your educators, where the bandwidth problem may be on the student's side (for example, a large number of students are able to watch the video lessons without issue, but a small number of students have difficulties).</span></span>

<span data-ttu-id="e6a95-149">Não é razoável esperar que muitos pais consigam solucionar esses problemas.</span><span class="sxs-lookup"><span data-stu-id="e6a95-149">It's not reasonable to expect many parents to be able to troubleshoot these issues.</span></span> <span data-ttu-id="e6a95-150">Problemas de baixa largura de banda podem estar fora do controle do aluno ou dos pais (a casa pode não ter acesso a alta largura de banda, pode haver várias pessoas em sua área imediata consumindo largura de banda e afetando o que podem fazer, pode haver instabilidade da Internet e assim em).</span><span class="sxs-lookup"><span data-stu-id="e6a95-150">Low-bandwidth issues may be out of a student or parent's control (their home may not have access to high bandwidth, they may have numerous people in their immediate area consuming bandwidth and affecting what they can do, there may be internet instability, and so on).</span></span>

<span data-ttu-id="e6a95-151">Reunimos as diretrizes em nosso artigo [Usar o Teams para dever de casa quando a largura de banda estiver baixa](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262) para pais e alunos, e, além disso, você pode revisar e testar essas recomendações se estiver tendo problemas.</span><span class="sxs-lookup"><span data-stu-id="e6a95-151">We've put together guidance in our [Use Teams for schoolwork when bandwidth is low](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262) article for parents and students as well, you can review and try these recommendations if you're having any problems.</span></span>