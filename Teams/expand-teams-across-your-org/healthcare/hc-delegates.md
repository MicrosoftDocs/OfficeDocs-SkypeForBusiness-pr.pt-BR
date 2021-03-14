---
title: Delegação de mensagens
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: acolonna
description: Saiba como um usuário com status Ausente ou Não Perturbe, pode definir de maneira explícita outro usuário como um delegado na sua mensagem de status.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ac23afbea7f452967718a8c2d86fd4d36584492d
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790463"
---
# <a name="message-delegation"></a><span data-ttu-id="60cfa-103">Delegação de mensagens</span><span class="sxs-lookup"><span data-stu-id="60cfa-103">Message delegation</span></span>

<span data-ttu-id="60cfa-104">Um usuário já pode definir explicitamente seu status como Ausente ou Não Incomode e fornecer textos personalizados.</span><span class="sxs-lookup"><span data-stu-id="60cfa-104">A user can already explicitly set their status to Away or Do not Disturb, and provide custom text.</span></span> <span data-ttu-id="60cfa-105">A função da delegação de mensagens funciona da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="60cfa-105">The message delegation feature works as follows:</span></span>

1. <span data-ttu-id="60cfa-106">Um usuário @nomedeusuário menciona outro usuário em parte de uma mensagem de status de texto, sugerindo que enquanto eles não estiverem disponíveis, pessoas que queiram contatá-los, em vez disso, contatem o usuário @nomedeusuário mencionado.</span><span class="sxs-lookup"><span data-stu-id="60cfa-106">A user @username mentions another user in part of a text status message, suggesting that while they are unavailable people who want to contact them instead contact the @username mentioned user.</span></span>
2. <span data-ttu-id="60cfa-107">A pessoa que foi atribuída como representante será notificada de que foi indicada para ser a representante.</span><span class="sxs-lookup"><span data-stu-id="60cfa-107">The person who has been assigned as a delegate is notified that they were nominated to be a delegate.</span></span>
3. <span data-ttu-id="60cfa-108">Alguém que tentar entrar em contato com o primeiro usuário pode passar o mouse sobre o representante indicado e facilmente enviar uma mensagem ao representante.</span><span class="sxs-lookup"><span data-stu-id="60cfa-108">Someone trying to contact the first user can then hover over the nominated delegate and easily message the delegate instead.</span></span>  

<span data-ttu-id="60cfa-109">Trata-se de um processo iniciado pelo usuário no cliente, e nenhum envolvimento administrativo é necessário para habilitar o recurso.</span><span class="sxs-lookup"><span data-stu-id="60cfa-109">This is a user-initiated process in the client, and no Admin involvement is required to enable the feature.</span></span> 

## <a name="delegation-use-scenario-in-healthcare"></a><span data-ttu-id="60cfa-110">Cenário de uso da delegação na área da saúde</span><span class="sxs-lookup"><span data-stu-id="60cfa-110">Delegation use scenario in Healthcare</span></span>

<span data-ttu-id="60cfa-111">*Exemplo de uso sem definir os representantes:* O Dr. Franco Piccio está de plantão no departamento de radiologia.</span><span class="sxs-lookup"><span data-stu-id="60cfa-111">*Usage example without setting delegates:*  Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="60cfa-112">Ele recebe uma chamada pessoal urgente e tem que se afastar pelas próximas horas.</span><span class="sxs-lookup"><span data-stu-id="60cfa-112">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="60cfa-113">Ele pede a uma de suas colegas do departamento de radiologia, Dra. Lena Ehrle, que o substitua enquanto ele estiver fora.</span><span class="sxs-lookup"><span data-stu-id="60cfa-113">He asks one of his peers in the radiology department, Dr. Lena Ehrle, to cover for him while he is gone.</span></span> <span data-ttu-id="60cfa-114">Informalmente, ele entrega seu pager à Dra. Ehrle, que está ouvindo as mensagens urgentes e os pings no pager e responde-os em nome do Dr. Piccio, além das suas responsabilidades atuais.</span><span class="sxs-lookup"><span data-stu-id="60cfa-114">He informally hands over his pager to Dr. Ehrle, who is listening for urgent messages and pings on the pager and responds to them on behalf of Dr. Piccio in addition to her current responsibilities.</span></span> <span data-ttu-id="60cfa-115">É possível que outros membros da equipe não percebam que a delegação informal aconteceu, e a confusão se instala com o cuidado de um paciente.</span><span class="sxs-lookup"><span data-stu-id="60cfa-115">Others on the team may not realize the informal delegation happened, and confusion ensues with a patient's care.</span></span>

<span data-ttu-id="60cfa-116">*Exemplo de uso definindo os representantes:* O Dr. Franco Piccio está de plantão no departamento de radiologia.</span><span class="sxs-lookup"><span data-stu-id="60cfa-116">*Usage example with setting delegates:* Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="60cfa-117">Ele recebe uma chamada pessoal urgente e tem que se afastar pelas próximas horas.</span><span class="sxs-lookup"><span data-stu-id="60cfa-117">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="60cfa-118">Ele pede a uma de suas colegas do departamento de radiologia, Dra. Lena Ehrle, que o substitua enquanto ele estiver fora.</span><span class="sxs-lookup"><span data-stu-id="60cfa-118">He asks one of his peers in the radiology department, Dr. Lena Ehrle to cover for him while he is gone.</span></span> <span data-ttu-id="60cfa-119">Ele altera sua mensagem de status personalizada para dizer algo semelhante a "Estou indisponível durante as próximas horas.</span><span class="sxs-lookup"><span data-stu-id="60cfa-119">He changes his custom status message to say something similar to "I am unavailable for the next few hours.</span></span> <span data-ttu-id="60cfa-120">Contatar @DraEhrle para quaisquer emergências".</span><span class="sxs-lookup"><span data-stu-id="60cfa-120">Please contact @DrEhrle for any emergencies."</span></span>  <span data-ttu-id="60cfa-121">Outros membros da equipe perceberam que a delegação aconteceu enquanto tentavam contatar o Dr. Piccio, e agora sabem que devem contatar a Dra. Ehrle nesse meio tempo.</span><span class="sxs-lookup"><span data-stu-id="60cfa-121">Others on the team realize the delegation happened as they're attempting to contact Dr. Piccio, so they now know to contact Dr. Ehrle in the meantime.</span></span> <span data-ttu-id="60cfa-122">Pouca ou nenhuma confusão ocorre com o atendimento do paciente.</span><span class="sxs-lookup"><span data-stu-id="60cfa-122">Little to no confusion ensues with a patient's care.</span></span>

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a><span data-ttu-id="60cfa-123">Impacto dos modos de coexistência no status do usuário no cliente do Teams</span><span class="sxs-lookup"><span data-stu-id="60cfa-123">Impact of co-existence modes on user status in the Teams client</span></span>

<span data-ttu-id="60cfa-124">Os administradores devem estar cientes de que as notas de status e as delegações mencionam comportamentos que dependerão em parte do modo de coexistência de um usuário.</span><span class="sxs-lookup"><span data-stu-id="60cfa-124">Admins should be aware that status notes and delegation mention behaviors will depend partly on a user's co-existence mode.</span></span> <span data-ttu-id="60cfa-125">Esta matriz mostra as possibilidades:</span><span class="sxs-lookup"><span data-stu-id="60cfa-125">This matrix shows the possibilities:</span></span>

|<span data-ttu-id="60cfa-126">Modo de coexistência</span><span class="sxs-lookup"><span data-stu-id="60cfa-126">Co-Existence Mode</span></span> | <span data-ttu-id="60cfa-127">Comportamento esperado</span><span class="sxs-lookup"><span data-stu-id="60cfa-127">Expected Behavior</span></span>|
|---|---|
|<span data-ttu-id="60cfa-128">TeamsOnly</span><span class="sxs-lookup"><span data-stu-id="60cfa-128">TeamsOnly</span></span> |<span data-ttu-id="60cfa-129">Os usuários podem definir uma nota apenas no Teams.</span><span class="sxs-lookup"><span data-stu-id="60cfa-129">Users can set a note only from Teams.</span></span> <br> <span data-ttu-id="60cfa-130">A nota do Teams do usuário é visível no Teams e no SfB.</span><span class="sxs-lookup"><span data-stu-id="60cfa-130">User's Teams note is visible in Teams & SfB.</span></span> |
|<span data-ttu-id="60cfa-131">Ilhas</span><span class="sxs-lookup"><span data-stu-id="60cfa-131">Islands</span></span> | <span data-ttu-id="60cfa-132">O conjunto de notas do usuário no Teams é visível apenas no Teams.</span><span class="sxs-lookup"><span data-stu-id="60cfa-132">User's note set in Teams visible only in Teams.</span></span> <br> <span data-ttu-id="60cfa-133">A nota do usuário definida no SfB é visível apenas no SfB</span><span class="sxs-lookup"><span data-stu-id="60cfa-133">User's note set in SfB visible only in SfB</span></span> |
|<span data-ttu-id="60cfa-134">Modos SfB\*</span><span class="sxs-lookup"><span data-stu-id="60cfa-134">SfB\* modes</span></span> | <span data-ttu-id="60cfa-135">Os usuários podem definir uma nota apenas no SfB.</span><span class="sxs-lookup"><span data-stu-id="60cfa-135">Users can set a note only from SfB.</span></span> <br> <span data-ttu-id="60cfa-136">A nota SfB do usuário é visível no SfB e no Teams.</span><span class="sxs-lookup"><span data-stu-id="60cfa-136">User's SfB note is visible in SfB & Teams.</span></span>  |
|||

<span data-ttu-id="60cfa-137">Um usuário só pode definir uma nota no Teams se seu modo for TeamsOnly ou Islands.</span><span class="sxs-lookup"><span data-stu-id="60cfa-137">A user can only set a note in Teams if their mode is TeamsOnly or Islands.</span></span>  

### <a name="displaying-notes-set-in-skype-for-business"></a><span data-ttu-id="60cfa-138">Exibir notas definidas no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="60cfa-138">Displaying notes set in Skype for Business</span></span>
  
<span data-ttu-id="60cfa-139">Não há nenhuma indicação visual de que uma nota tenha sido enviada pelo Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="60cfa-139">There is no visual indication that a note was set from Skype for Business.</span></span>

<span data-ttu-id="60cfa-140">O Skype for Business não impõe um limite de caracteres às notas de status.</span><span class="sxs-lookup"><span data-stu-id="60cfa-140">Skype for Business doesn't enforce a character limit on status notes.</span></span> <span data-ttu-id="60cfa-141">O Microsoft Teams exibirá apenas os primeiros 280 caracteres de um conjunto de notas do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="60cfa-141">Microsoft Teams will only display the first 280 characters of a note set from Skype for Business.</span></span> <span data-ttu-id="60cfa-142">Uma elipse (...) no final de uma nota indica truncagem.</span><span class="sxs-lookup"><span data-stu-id="60cfa-142">An ellipse (…) at the end of a note indicates truncation.</span></span>
  
<span data-ttu-id="60cfa-143">O Skype for Business não oferece suporte a prazos de validade para notas.</span><span class="sxs-lookup"><span data-stu-id="60cfa-143">Skype for Business doesn't support expiry times for notes.</span></span>

<span data-ttu-id="60cfa-144">A migração de notas do Skype for Business para o Teams não possui suporte quando um usuário é atualizado para o modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="60cfa-144">Migration of notes from Skype for Business to Teams is not supported when a user is upgraded to TeamsOnly mode.</span></span>

## <a name="related-topics"></a><span data-ttu-id="60cfa-145">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="60cfa-145">Related topics</span></span>

[<span data-ttu-id="60cfa-146">Coexistência com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="60cfa-146">Coexistence with Skype for Business</span></span>](../../coexistence-chat-calls-presence.md)
