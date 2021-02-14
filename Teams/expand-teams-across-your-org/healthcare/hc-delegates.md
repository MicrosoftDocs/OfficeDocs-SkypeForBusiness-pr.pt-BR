---
title: Delegação de mensagem
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
description: Saiba como um usuário com o status Desalo ou Não Incomodar pode definir explicitamente outro usuário como representante em sua mensagem de status.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ac23afbea7f452967718a8c2d86fd4d36584492d
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790463"
---
# <a name="message-delegation"></a><span data-ttu-id="3852d-103">Delegação de mensagem</span><span class="sxs-lookup"><span data-stu-id="3852d-103">Message delegation</span></span>

<span data-ttu-id="3852d-104">Um usuário já pode definir explicitamente seu status como Distância ou Não Incomodar e fornecer texto personalizado.</span><span class="sxs-lookup"><span data-stu-id="3852d-104">A user can already explicitly set their status to Away or Do not Disturb, and provide custom text.</span></span> <span data-ttu-id="3852d-105">O recurso de delegação de mensagens funciona da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="3852d-105">The message delegation feature works as follows:</span></span>

1. <span data-ttu-id="3852d-106">Um usuário @username menciona outro usuário em parte de uma mensagem de status de texto, sugerindo que, embora não sejam pessoas indisponíveis que querem contatá-lo, entre em contato com o @username usuário mencionado.</span><span class="sxs-lookup"><span data-stu-id="3852d-106">A user @username mentions another user in part of a text status message, suggesting that while they are unavailable people who want to contact them instead contact the @username mentioned user.</span></span>
2. <span data-ttu-id="3852d-107">A pessoa que foi atribuída como representante será notificada de que ela foi nomeada como representante.</span><span class="sxs-lookup"><span data-stu-id="3852d-107">The person who has been assigned as a delegate is notified that they were nominated to be a delegate.</span></span>
3. <span data-ttu-id="3852d-108">Alguém que está tentando entrar em contato com o primeiro usuário pode passar o mouse sobre o representante nomeado e facilmente enviar uma mensagem ao representante.</span><span class="sxs-lookup"><span data-stu-id="3852d-108">Someone trying to contact the first user can then hover over the nominated delegate and easily message the delegate instead.</span></span>  

<span data-ttu-id="3852d-109">Esse é um processo iniciado pelo usuário no cliente, e nenhum envolvimento do Administrador é necessário para habilitar o recurso.</span><span class="sxs-lookup"><span data-stu-id="3852d-109">This is a user-initiated process in the client, and no Admin involvement is required to enable the feature.</span></span> 

## <a name="delegation-use-scenario-in-healthcare"></a><span data-ttu-id="3852d-110">Cenário de uso de delegação em Serviços de Saúde</span><span class="sxs-lookup"><span data-stu-id="3852d-110">Delegation use scenario in Healthcare</span></span>

<span data-ttu-id="3852d-111">*Exemplo de uso sem definir representantes:*  O Dr. Franco Piccio está de plantão no departamento de radiologia.</span><span class="sxs-lookup"><span data-stu-id="3852d-111">*Usage example without setting delegates:*  Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="3852d-112">Ele recebe uma chamada pessoal urgente e precisa se afastar pelas próximas horas.</span><span class="sxs-lookup"><span data-stu-id="3852d-112">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="3852d-113">Ele pede a um de seus colegas no departamento de radiologia, Dr. Melo Ehrle, que o cubra enquanto ele estiver fora.</span><span class="sxs-lookup"><span data-stu-id="3852d-113">He asks one of his peers in the radiology department, Dr. Lena Ehrle, to cover for him while he is gone.</span></span> <span data-ttu-id="3852d-114">Ele entrega informalmente o pager ao Dr. Ehrle, que está ouvindo mensagens urgentes e pings no pager e responde em nome do Dr. Piccio, além de suas responsabilidades atuais.</span><span class="sxs-lookup"><span data-stu-id="3852d-114">He informally hands over his pager to Dr. Ehrle, who is listening for urgent messages and pings on the pager and responds to them on behalf of Dr. Piccio in addition to her current responsibilities.</span></span> <span data-ttu-id="3852d-115">Outras pessoas da equipe podem não perceber que a delegação informal aconteceu e a confusão se dá com os cuidados de um paciente.</span><span class="sxs-lookup"><span data-stu-id="3852d-115">Others on the team may not realize the informal delegation happened, and confusion ensues with a patient's care.</span></span>

<span data-ttu-id="3852d-116">*Exemplo de uso com a configuração de representantes:* O Dr. Franco Piccio está de plantão no departamento de radiologia.</span><span class="sxs-lookup"><span data-stu-id="3852d-116">*Usage example with setting delegates:* Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="3852d-117">Ele recebe uma chamada pessoal urgente e precisa se afastar pelas próximas horas.</span><span class="sxs-lookup"><span data-stu-id="3852d-117">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="3852d-118">Ele pede a um de seus colegas no departamento de radiologia, Dr. Melo Ehrle para cobrir por ele enquanto ele estiver fora.</span><span class="sxs-lookup"><span data-stu-id="3852d-118">He asks one of his peers in the radiology department, Dr. Lena Ehrle to cover for him while he is gone.</span></span> <span data-ttu-id="3852d-119">Ele altera sua mensagem de status personalizada para dizer algo semelhante a "Estou indisponível nas próximas horas.</span><span class="sxs-lookup"><span data-stu-id="3852d-119">He changes his custom status message to say something similar to "I am unavailable for the next few hours.</span></span> <span data-ttu-id="3852d-120">Entre em contato @DrEhrle qualquer emergência".</span><span class="sxs-lookup"><span data-stu-id="3852d-120">Please contact @DrEhrle for any emergencies."</span></span>  <span data-ttu-id="3852d-121">Outras pessoas da equipe percebem que a delegação aconteceu enquanto eles tentam entrar em contato com o Dr. Piccio, então agora eles sabem como entrar em contato com o Dr. Ehrle enquanto isso.</span><span class="sxs-lookup"><span data-stu-id="3852d-121">Others on the team realize the delegation happened as they're attempting to contact Dr. Piccio, so they now know to contact Dr. Ehrle in the meantime.</span></span> <span data-ttu-id="3852d-122">Há pouca ou nenhuma confusão com os cuidados de um paciente.</span><span class="sxs-lookup"><span data-stu-id="3852d-122">Little to no confusion ensues with a patient's care.</span></span>

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a><span data-ttu-id="3852d-123">Impacto dos modos de co-existência no status do usuário no cliente do Teams</span><span class="sxs-lookup"><span data-stu-id="3852d-123">Impact of co-existence modes on user status in the Teams client</span></span>

<span data-ttu-id="3852d-124">Os administradores devem estar cientes de que as anotações de status e os comportamentos de menção de delegação dependerão parcialmente do modo de co-existência de um usuário.</span><span class="sxs-lookup"><span data-stu-id="3852d-124">Admins should be aware that status notes and delegation mention behaviors will depend partly on a user's co-existence mode.</span></span> <span data-ttu-id="3852d-125">Esta matriz mostra as possibilidades:</span><span class="sxs-lookup"><span data-stu-id="3852d-125">This matrix shows the possibilities:</span></span>

|<span data-ttu-id="3852d-126">Co-Existence modo</span><span class="sxs-lookup"><span data-stu-id="3852d-126">Co-Existence Mode</span></span> | <span data-ttu-id="3852d-127">Comportamento esperado</span><span class="sxs-lookup"><span data-stu-id="3852d-127">Expected Behavior</span></span>|
|---|---|
|<span data-ttu-id="3852d-128">TeamsOnly</span><span class="sxs-lookup"><span data-stu-id="3852d-128">TeamsOnly</span></span> |<span data-ttu-id="3852d-129">Os usuários podem definir uma anotação somente no Teams.</span><span class="sxs-lookup"><span data-stu-id="3852d-129">Users can set a note only from Teams.</span></span> <br> <span data-ttu-id="3852d-130">A anotação do Teams do usuário está visível no Teams & SfB.</span><span class="sxs-lookup"><span data-stu-id="3852d-130">User's Teams note is visible in Teams & SfB.</span></span> |
|<span data-ttu-id="3852d-131">Ilhas</span><span class="sxs-lookup"><span data-stu-id="3852d-131">Islands</span></span> | <span data-ttu-id="3852d-132">A anotação do usuário definida no Teams visível apenas no Teams.</span><span class="sxs-lookup"><span data-stu-id="3852d-132">User's note set in Teams visible only in Teams.</span></span> <br> <span data-ttu-id="3852d-133">Anotações do usuário definidas em SfB visíveis somente em SfB</span><span class="sxs-lookup"><span data-stu-id="3852d-133">User's note set in SfB visible only in SfB</span></span> |
|<span data-ttu-id="3852d-134">Modos SfB\*</span><span class="sxs-lookup"><span data-stu-id="3852d-134">SfB\* modes</span></span> | <span data-ttu-id="3852d-135">Os usuários podem definir uma anotação somente a partir do SfB.</span><span class="sxs-lookup"><span data-stu-id="3852d-135">Users can set a note only from SfB.</span></span> <br> <span data-ttu-id="3852d-136">A nota SfB do usuário está visível no SfB & Teams.</span><span class="sxs-lookup"><span data-stu-id="3852d-136">User's SfB note is visible in SfB & Teams.</span></span>  |
|||

<span data-ttu-id="3852d-137">Um usuário só pode definir uma anotação no Teams se seu modo for TeamsOnly ou Islands.</span><span class="sxs-lookup"><span data-stu-id="3852d-137">A user can only set a note in Teams if their mode is TeamsOnly or Islands.</span></span>  

### <a name="displaying-notes-set-in-skype-for-business"></a><span data-ttu-id="3852d-138">Exibindo anotações definidas no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="3852d-138">Displaying notes set in Skype for Business</span></span>
  
<span data-ttu-id="3852d-139">Não há nenhuma indicação visual de que uma anotação foi definida do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="3852d-139">There is no visual indication that a note was set from Skype for Business.</span></span>

<span data-ttu-id="3852d-140">O Skype for Business não impõe um limite de caracteres nas anotações de status.</span><span class="sxs-lookup"><span data-stu-id="3852d-140">Skype for Business doesn't enforce a character limit on status notes.</span></span> <span data-ttu-id="3852d-141">O Microsoft Teams exibirá apenas os primeiros 280 caracteres de uma anotação definida pelo Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="3852d-141">Microsoft Teams will only display the first 280 characters of a note set from Skype for Business.</span></span> <span data-ttu-id="3852d-142">Uma elipse (...) no final de uma anotação indica truncamento.</span><span class="sxs-lookup"><span data-stu-id="3852d-142">An ellipse (…) at the end of a note indicates truncation.</span></span>
  
<span data-ttu-id="3852d-143">O Skype for Business não dá suporte a prazos para anotações.</span><span class="sxs-lookup"><span data-stu-id="3852d-143">Skype for Business doesn't support expiry times for notes.</span></span>

<span data-ttu-id="3852d-144">A migração de anotações do Skype for Business para o Teams não é suportada quando um usuário é atualizado para o modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="3852d-144">Migration of notes from Skype for Business to Teams is not supported when a user is upgraded to TeamsOnly mode.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3852d-145">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="3852d-145">Related topics</span></span>

[<span data-ttu-id="3852d-146">Coexistência com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="3852d-146">Coexistence with Skype for Business</span></span>](../../coexistence-chat-calls-presence.md)
