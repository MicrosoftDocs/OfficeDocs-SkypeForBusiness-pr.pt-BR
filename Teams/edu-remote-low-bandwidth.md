---
title: Diretrizes para baixa largura de banda do Microsoft Teams para EDU
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: jesegher
description: Artigo do Microsoft Teams para EDU para auxiliar com problemas de áudio e vídeo relacionados à baixa largura de banda. Se você for um dos pais, professor ou administrador de TI, terá opções para melhorar a experiência com o Teams.
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
ms.openlocfilehash: b254bfb89a96efed65e2c1fdba1c345825d81dc2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111077"
---
# <a name="help-for-low-bandwidth-situations-for-teams-for-edu"></a><span data-ttu-id="9ab1e-104">Ajuda para situações de baixa largura de banda para as Teams para EDU</span><span class="sxs-lookup"><span data-stu-id="9ab1e-104">Help for low bandwidth situations for Teams for EDU</span></span>

<span data-ttu-id="9ab1e-105">Há muitos elementos de rede, no que se refere a trabalhar com o Microsoft Teams, que podem afetar o desempenho, e a baixa largura de banda é uma das situações que podem dar a sensação de estar fora do seu controle.</span><span class="sxs-lookup"><span data-stu-id="9ab1e-105">There are a lot of network elements when it comes to working with Microsoft Teams that can affect performance, and low bandwidth is one of the situations that can feel entirely out of your control.</span></span> <span data-ttu-id="9ab1e-106">Considere o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9ab1e-106">Consider the following:</span></span>

- <span data-ttu-id="9ab1e-107">Uma conexão de internet de baixa velocidade para a escola.</span><span class="sxs-lookup"><span data-stu-id="9ab1e-107">A low-speed internet connection for the school.</span></span>
- <span data-ttu-id="9ab1e-108">Uma conexão de internet de baixa velocidade para um ou mais alunos.</span><span class="sxs-lookup"><span data-stu-id="9ab1e-108">A low-speed internet connection for one or more students.</span></span>
- <span data-ttu-id="9ab1e-109">Períodos do dia em que há baixa largura de banda devido ao uso da rede em uma região.</span><span class="sxs-lookup"><span data-stu-id="9ab1e-109">Times of the day when there is low bandwidth due to network usage in an area.</span></span>
- <span data-ttu-id="9ab1e-110">Períodos de baixa largura de banda devido a paralisações locais não relacionadas à escola ou alunos, mas que ainda assim impactam na performance.</span><span class="sxs-lookup"><span data-stu-id="9ab1e-110">Low bandwidth periods due to outages local to neither the school nor to students, but which impact performance nonetheless.</span></span>
- <span data-ttu-id="9ab1e-111">Problemas não relacionados à largura de banda (por exemplo, problemas com hardware) confundidos como problemas de baixa largura de banda.</span><span class="sxs-lookup"><span data-stu-id="9ab1e-111">Non-bandwidth issues (for example, issues with hardware) that masquerade as low bandwidth issues.</span></span>

<span data-ttu-id="9ab1e-112">Este artigo lhe oferece práticas recomendadas a seguir para diversas atividades do Teams quando você estiver enfrentando um problema de baixa largura de banda.</span><span class="sxs-lookup"><span data-stu-id="9ab1e-112">This article will give you best practices to follow for a variety of Teams activities when you're faced with a low-bandwidth issue.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9ab1e-113">Aqui tem informação sobre [Como o Microsoft Teams utiliza memória](teams-memory-usage-perf.md), porque além dos problemas de baixa largura de banda, você pode ter problemas com os recursos do seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9ab1e-113">There's information here on [How Microsoft Teams uses memory](teams-memory-usage-perf.md), because in addition to low bandwidth problems, you may be having resource issues on your device.</span></span> <span data-ttu-id="9ab1e-114">Se você estiver procurando por diretrizes de rede do Microsoft Teams, confira [Preparar a rede da sua organização para o Microsoft Teams](prepare-network.md).</span><span class="sxs-lookup"><span data-stu-id="9ab1e-114">If you're looking for network guidance for Microsoft Teams, review [Prepare your organization's network for Microsoft Teams](prepare-network.md).</span></span>

## <a name="resolving-low-bandwidth-issues-for-itadmins"></a><span data-ttu-id="9ab1e-115">Solucionar problemas de baixa largura de banda para Administradores de TI</span><span class="sxs-lookup"><span data-stu-id="9ab1e-115">Resolving low bandwidth issues for ITAdmins</span></span>

<span data-ttu-id="9ab1e-116">O importante a ser lembrado, como um Administrador de TI, é que, embora você tenha soluções para problemas de baixa largura de banda amplos que possam ser solucionados rapidamente, isso deve ser analisado cuidadosamente, pois alguns problemas podem ser resolvidos com um foco mais estreito no professor ou até mesmo no nível de aluno/pais.</span><span class="sxs-lookup"><span data-stu-id="9ab1e-116">The important thing to remember, as an ITAdmin, is that while you have solutions for low bandwidth issues that are wide-spread that will resolve problems quickly, this should be considered carefully, as some issues may be able to resolved with a more narrow focus taken at the educator or even the student/parent level.</span></span>

<span data-ttu-id="9ab1e-117">Resumindo, se o problema de baixa largura de banda ocorrer em um grande grupo de alunos, executar uma ação como um Administrador de TI faz sentido, e também faz sentido se as ações executadas no nível aluno/professor ainda não tiveram sucesso.</span><span class="sxs-lookup"><span data-stu-id="9ab1e-117">In short, if the low bandwidth issue occurs for a wide group of students, taking action as an ITAdmin makes sense, and it also makes sense if the actions taken at the student/educator level haven't been helpful.</span></span>

> [!NOTE]
> <span data-ttu-id="9ab1e-118">Se você tem a oportunidade de investir, o [Guia de Revisão de Qualidade da Experiência](quality-of-experience-review-guide.md) é uma leitura válida (não é específica de EDU, mas ainda assim terá informações valiosas).</span><span class="sxs-lookup"><span data-stu-id="9ab1e-118">If you've got the time to invest, the [Quality of Experience Review Guide](quality-of-experience-review-guide.md) is a worthwhile read (this is not EDU-specific, but it will still have valuable information).</span></span> <span data-ttu-id="9ab1e-119">Isso permitirá que Administradores de TI experientes se aprofundem na experiência dos professores e alunos.</span><span class="sxs-lookup"><span data-stu-id="9ab1e-119">This will allow experienced ITAdmins to go in-depth on the experience for their educators and students.</span></span>

### <a name="meetings-and-video"></a><span data-ttu-id="9ab1e-120">Reuniões e vídeo</span><span class="sxs-lookup"><span data-stu-id="9ab1e-120">Meetings and video</span></span>

<span data-ttu-id="9ab1e-121">Um foco principal para problemas de baixa largura de banda são reuniões e vídeos em reuniões.</span><span class="sxs-lookup"><span data-stu-id="9ab1e-121">A primary focus for low bandwidth issues are meetings, and specifically video in meetings.</span></span> <span data-ttu-id="9ab1e-122">A seguir, listamos algumas das ações que uma Administrador de TI deve considerar ao lidar com problemas relatados por alunos ou professores no que se refere a ter uma melhor experiência de reunião em um ambiente escolar.</span><span class="sxs-lookup"><span data-stu-id="9ab1e-122">We have some of the actions below that an ITAdmin should consider when dealing with issues reported by students or educators in regard to having the best meeting experience in an educational setting.</span></span>

#### <a name="meeting-policies"></a><span data-ttu-id="9ab1e-123">Políticas de reunião</span><span class="sxs-lookup"><span data-stu-id="9ab1e-123">Meeting policies</span></span>

<span data-ttu-id="9ab1e-124">Em relação às reuniões, uma das áreas de maior preocupação para as situações de baixa largura de banda tem a ver com os vídeos.</span><span class="sxs-lookup"><span data-stu-id="9ab1e-124">In regards to meetings, one of the most concerning areas for low bandwidth situations has to do with videos.</span></span> <span data-ttu-id="9ab1e-125">Felizmente, além do Teams ser capaz de dimensionar automaticamente a largura de banda detectada, você como um Administrador de TI tem opções à política que podem ser definidas conforme o organizador e/ou usuário para oferecer a todos a melhor experiência, à luz da largura de banda com a qual precisam trabalhar em um determinado período.</span><span class="sxs-lookup"><span data-stu-id="9ab1e-125">Fortunately, in addition to Teams being able to scale to detected bandwidth automatically, you as an ITAdmin have policy options you can set at the per-organizer and/or per-user level to give everyone the best experience in light of the bandwidth they have to work with at a given time.</span></span>

<span data-ttu-id="9ab1e-126">Algumas das coisas que você pode definir por meio da política incluem:</span><span class="sxs-lookup"><span data-stu-id="9ab1e-126">Some of the things you can set via policy include:</span></span>

- <span data-ttu-id="9ab1e-127">Desabilitar o vídeo completamente, para que ninguém possa habilitá-lo.</span><span class="sxs-lookup"><span data-stu-id="9ab1e-127">Disabling video altogether, so no one could enable it.</span></span>
- <span data-ttu-id="9ab1e-128">Taxa de bits de mídia (definida por usuário).</span><span class="sxs-lookup"><span data-stu-id="9ab1e-128">Media bit rate (this is set per-user).</span></span>

<span data-ttu-id="9ab1e-129">Para saber mais sobre suas opções e para um resumo das especificações de quais políticas você precisaria definir para reuniões e vídeos, confira [Configurações de política de reunião no Teams: Áudio e vídeo](./meeting-policies-in-teams.md#meeting-policy-settings---audio--video) para obter informações detalhadas.</span><span class="sxs-lookup"><span data-stu-id="9ab1e-129">To learn more about your options, and to walk through the specifics of what policies you'd need to set for meetings and video, check out [Meeting policy settings in Teams: Audio and video](./meeting-policies-in-teams.md#meeting-policy-settings---audio--video) for detailed walk-through information.</span></span>

#### <a name="screen-sharing-policies"></a><span data-ttu-id="9ab1e-130">Políticas de compartilhamento de tela</span><span class="sxs-lookup"><span data-stu-id="9ab1e-130">Screen sharing policies</span></span>

<span data-ttu-id="9ab1e-131">Em outros casos, professores podem estar compartilhando toda a tela com os alunos, quando o compartilhamento deve ser limitado a um aplicativo relevante à lição que está sendo ensinada.</span><span class="sxs-lookup"><span data-stu-id="9ab1e-131">In other cases, educators may be sharing their entire screen to students, when sharing should be limited to an application relevant to the lesson being taught.</span></span> <span data-ttu-id="9ab1e-132">Isso também pode ser definido pela política, se essa opção for mais interessante do que fazer com que os professores façam essa escolha individualmente.</span><span class="sxs-lookup"><span data-stu-id="9ab1e-132">This can also be set via policy, if that's a more desirable way to do it than to have educators making that choice individually.</span></span>

<span data-ttu-id="9ab1e-133">Para ter uma boa ideia do que você pode fazer para limitar o compartilhamento de tela por meio das configurações de política, confira [Configurações de política de reunião no Teams: Compartilhamento de tela](./meeting-policies-in-teams.md#meeting-policy-settings---audio--video).</span><span class="sxs-lookup"><span data-stu-id="9ab1e-133">For a good idea of what you can do about limiting screen sharing via policy settings, check out [Meeting policy settings in Teams: Screen sharing](./meeting-policies-in-teams.md#meeting-policy-settings---audio--video).</span></span>

#### <a name="dial-in-number-for-meetings"></a><span data-ttu-id="9ab1e-134">Números de discagem para reuniões</span><span class="sxs-lookup"><span data-stu-id="9ab1e-134">Dial-in number for meetings</span></span>

<span data-ttu-id="9ab1e-135">Pode ser mais fácil para os alunos tentarem discagem para algumas sessões da sala de aula.</span><span class="sxs-lookup"><span data-stu-id="9ab1e-135">It may be easier for some students to attempt to dial in to some classroom sessions.</span></span> <span data-ttu-id="9ab1e-136">Você pode fornecer um número de discagem para reuniões no Teams, para que os alunos com dificuldades possam telefonar como uma alternativa para participar de uma reunião de vídeo.</span><span class="sxs-lookup"><span data-stu-id="9ab1e-136">You can provide a dial-in number for Teams meetings, so students with issues can phone in as an alternative to attending a video meeting.</span></span>

<span data-ttu-id="9ab1e-137">Para saber mais sobre isso, você pode ler [Definir os números de telefone incluídos em convites no Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="9ab1e-137">For more information on this, you can read [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>

## <a name="low-bandwidth-scenarios-as-an-educator"></a><span data-ttu-id="9ab1e-138">Cenários de baixa largura de banda como um professor</span><span class="sxs-lookup"><span data-stu-id="9ab1e-138">Low bandwidth scenarios as an educator</span></span>

<span data-ttu-id="9ab1e-139">Os professores devem ter uma capacidade de resolver problemas de baixa largura de banda e podem ser uma melhor opção às ações de Administradores de TI nas seguintes situações:</span><span class="sxs-lookup"><span data-stu-id="9ab1e-139">Educators should feel empowered to take steps to resolve low bandwidth issues, and may be a superior choice to ITAdmin action in the following situations:</span></span>

- <span data-ttu-id="9ab1e-140">Se o problema for intermitente ou relativamente passageiro.</span><span class="sxs-lookup"><span data-stu-id="9ab1e-140">If the problem is intermittent, or relatively transitory.</span></span>
- <span data-ttu-id="9ab1e-141">Se houver um horário específico do dia em que você pode antecipar a existência de um problema ou se o período de baixa largura de banda tiver alguma previsibilidade.</span><span class="sxs-lookup"><span data-stu-id="9ab1e-141">If there is a specific time of the day you can anticipate there being an issue, or the low bandwidth period has some predictability to it.</span></span>

<span data-ttu-id="9ab1e-142">Nesses casos, você pode executar algumas ações.</span><span class="sxs-lookup"><span data-stu-id="9ab1e-142">In these situations, you can take some actions.</span></span>

<span data-ttu-id="9ab1e-143">Para obter mais informações, confira [Usar o Teams para a trabalhos escolares quando a largura de banda estiver baixa](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262).</span><span class="sxs-lookup"><span data-stu-id="9ab1e-143">For more information, check out [Use Teams for schoolwork when bandwidth is low](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262).</span></span>

## <a name="low-bandwidth-scenarios-as-a-parent-or-student"></a><span data-ttu-id="9ab1e-144">Cenários de baixa largura de banda como pai ou aluno</span><span class="sxs-lookup"><span data-stu-id="9ab1e-144">Low bandwidth scenarios as a parent or student</span></span>

<span data-ttu-id="9ab1e-145">Há situações também, e você deve discuti-las proativamente com seus professores, onde o problema de largura de banda pode estar no lado do aluno (por exemplo, um grande número de alunos pode assistir as lições de vídeo sem problemas, mas um pequeno número de alunos pode ter dificuldades).</span><span class="sxs-lookup"><span data-stu-id="9ab1e-145">There are also situations, and you should proactively discuss them with your educators, where the bandwidth problem may be on the student's side (for example, a large number of students are able to watch the video lessons without issue, but a small number of students have difficulties).</span></span>

<span data-ttu-id="9ab1e-146">Não é razoável esperar que muitos pais possam solucionar esses problemas, e problemas de baixa largura de banda podem estar fora do controle de um aluno ou pai (sua casa pode não ter acesso à alta largura de banda, pode ter uma grande quantidade de pessoas em sua vizinhança consumindo banda e afetando o que elas podem fazer, pode haver instabilidade na Internet e assim por diante).</span><span class="sxs-lookup"><span data-stu-id="9ab1e-146">It's not reasonable to expect many parents to be able to troubleshoot these issues, and low bandwidth issues may be out of a student or parent's control (their home may not have access to high bandwidth, they may have a lot of people in their immediate area consuming bandwidth and affecting what they can do, there may be internet instability, and so on).</span></span>

<span data-ttu-id="9ab1e-147">Reunimos as diretrizes em nosso artigo [Usar o Teams para dever de casa quando a largura de banda estiver baixa](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262) para pais e alunos, e, além disso, você pode revisar e testar essas recomendações se estiver tendo problemas.</span><span class="sxs-lookup"><span data-stu-id="9ab1e-147">We've put together guidance in our [Use Teams for schoolwork when bandwidth is low](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262) article for parents and students as well, you can review and try these recommendations if you're having any problems.</span></span>