---
title: Delegação de mensagem
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: acolonna
description: Um usuário pode definir explicitamente outro usuário como um representante na mensagem de status.
ms.openlocfilehash: 56c0e9bd5394e738170130bab15803e5cb4d741c
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570353"
---
# <a name="message-delegation"></a><span data-ttu-id="524d8-103">Delegação de mensagem</span><span class="sxs-lookup"><span data-stu-id="524d8-103">Message delegation</span></span>

<span data-ttu-id="524d8-104">Um usuário já pode definir explicitamente seu status como ausente ou não incomodar e fornecer texto personalizado.</span><span class="sxs-lookup"><span data-stu-id="524d8-104">A user can already explicitly set their status to Away or Do not Disturb, and provide custom text.</span></span> <span data-ttu-id="524d8-105">O recurso de delegação de mensagens funciona da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="524d8-105">The message delegation feature works as follows:</span></span>

1. <span data-ttu-id="524d8-106">Um usuário @username mencionar outro usuário em parte de uma mensagem de status de texto, sugerindo que, enquanto eles não estiverem disponíveis, entrarem em contato com o usuário @username mencionado.</span><span class="sxs-lookup"><span data-stu-id="524d8-106">A user @username mentions another user in part of a text status message, suggesting that while they are unavailable people who want to contact them instead contact the @username mentioned user.</span></span>
2. <span data-ttu-id="524d8-107">A pessoa que foi atribuída como representante é notificada de que foram nomeadas como um representante.</span><span class="sxs-lookup"><span data-stu-id="524d8-107">The person who has been assigned as a delegate is notified that they were nominated to be a delegate.</span></span>
3. <span data-ttu-id="524d8-108">Alguém que está tentando entrar em contato com o primeiro usuário pode passar o mouse sobre o representante indicado e enviar facilmente o representante para a mensagem.</span><span class="sxs-lookup"><span data-stu-id="524d8-108">Someone trying to contact the first user can then hover over the nominated delegate and easily message the delegate instead.</span></span>  

<span data-ttu-id="524d8-109">Esse é um processo iniciado pelo usuário no cliente e não é necessário ter um envolvimento do administrador para habilitar o recurso.</span><span class="sxs-lookup"><span data-stu-id="524d8-109">This is a user-initiated process in the client, and no Admin involvement is required to enable the feature.</span></span> 

## <a name="delegation-use-scenario-in-healthcare"></a><span data-ttu-id="524d8-110">Cenário de uso de delegação na área de saúde</span><span class="sxs-lookup"><span data-stu-id="524d8-110">Delegation use scenario in Healthcare</span></span>

<span data-ttu-id="524d8-111">*Exemplo de uso sem configuração de representantes:*  O Dr. Franco Piccio está on-Call no departamento da radiologia.</span><span class="sxs-lookup"><span data-stu-id="524d8-111">*Usage example without setting delegates:*  Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="524d8-112">Ele recebe uma chamada pessoal urgente e tem que deixar de entrar nas próximas horas.</span><span class="sxs-lookup"><span data-stu-id="524d8-112">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="524d8-113">Ele pergunta a um de seus colegas no departamento de Radiologia, o Dr. Lena Ehrle, a cobrir para ele enquanto ele está fora.</span><span class="sxs-lookup"><span data-stu-id="524d8-113">He asks one of his peers in the radiology department, Dr. Lena Ehrle, to cover for him while he is gone.</span></span> <span data-ttu-id="524d8-114">Ele, informalmente, passa pelo seu pager para o Dr. Ehrle, que está ouvindo mensagens urgentes e pings no pager e responde a ele em nome do Dr. Piccio, além de suas responsabilidades atuais.</span><span class="sxs-lookup"><span data-stu-id="524d8-114">He informally hands over his pager to Dr. Ehrle, who is listening for urgent messages and pings on the pager and responds to them on behalf of Dr. Piccio in addition to her current responsibilities.</span></span> <span data-ttu-id="524d8-115">Outras pessoas na equipe podem não perceber que a delegação informal ocorreu, e confusão de Ensues com o cuidado de um paciente.</span><span class="sxs-lookup"><span data-stu-id="524d8-115">Others on the team may not realize the informal delegation happened, and confusion ensues with a patient's care.</span></span>

<span data-ttu-id="524d8-116">*Exemplo de uso com a configuração de representantes:* O Dr. Franco Piccio está on-Call no departamento da radiologia.</span><span class="sxs-lookup"><span data-stu-id="524d8-116">*Usage example with setting delegates:* Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="524d8-117">Ele recebe uma chamada pessoal urgente e tem que deixar de entrar nas próximas horas.</span><span class="sxs-lookup"><span data-stu-id="524d8-117">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="524d8-118">Ele pede um de seus colegas no departamento da radiologia, o Dr. Lena Ehrle para falar com ele enquanto ele está fora.</span><span class="sxs-lookup"><span data-stu-id="524d8-118">He asks one of his peers in the radiology department, Dr. Lena Ehrle to cover for him while he is gone.</span></span> <span data-ttu-id="524d8-119">Ele altera sua mensagem de status personalizado para dizer algo semelhante a "não estou disponível pelas próximas horas.</span><span class="sxs-lookup"><span data-stu-id="524d8-119">He changes his custom status message to say something similar to "I am unavailable for the next few hours.</span></span> <span data-ttu-id="524d8-120">Entre em contato com a @DrEhrle para qualquer emergência. "</span><span class="sxs-lookup"><span data-stu-id="524d8-120">Please contact @DrEhrle for any emergencies."</span></span>  <span data-ttu-id="524d8-121">Outras pessoas na equipe percebem que a delegação aconteceu enquanto tentavam entrar em contato com o Dr. Piccio, portanto, agora ele sabe entrar em contato com o Dr. Ehrle enquanto isso.</span><span class="sxs-lookup"><span data-stu-id="524d8-121">Others on the team realize the delegation happened as they're attempting to contact Dr. Piccio, so they now know to contact Dr. Ehrle in the meantime.</span></span> <span data-ttu-id="524d8-122">Pouca ou nenhuma confusão Ensues com o cuidado de um paciente.</span><span class="sxs-lookup"><span data-stu-id="524d8-122">Little to no confusion ensues with a patient's care.</span></span>

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a><span data-ttu-id="524d8-123">Impacto dos modos de coexistência no status do usuário no cliente da equipe</span><span class="sxs-lookup"><span data-stu-id="524d8-123">Impact of co-existence modes on user status in the Teams client</span></span>

<span data-ttu-id="524d8-124">Os administradores devem estar cientes de que as anotações de status e os comportamentos de referência de delegação dependerão parcialmente do modo de coexistência de um usuário.</span><span class="sxs-lookup"><span data-stu-id="524d8-124">Admins should be aware that status notes and delegation mention behaviors will depend partly on a user’s co-existence mode.</span></span> <span data-ttu-id="524d8-125">Esta matriz mostra as possibilidades:</span><span class="sxs-lookup"><span data-stu-id="524d8-125">This matrix shows the possibilities:</span></span>

|<span data-ttu-id="524d8-126">Modo de co-existência</span><span class="sxs-lookup"><span data-stu-id="524d8-126">Co-Existence Mode</span></span> | <span data-ttu-id="524d8-127">Comportamento esperado</span><span class="sxs-lookup"><span data-stu-id="524d8-127">Expected Behavior</span></span>|
|---|---|
|<span data-ttu-id="524d8-128">TeamsOnly</span><span class="sxs-lookup"><span data-stu-id="524d8-128">TeamsOnly</span></span> |<span data-ttu-id="524d8-129">Os usuários podem definir uma anotação apenas do teams.</span><span class="sxs-lookup"><span data-stu-id="524d8-129">Users can set a note only from Teams.</span></span> <br> <span data-ttu-id="524d8-130">A nota de equipes do usuário é visível no Teams & SfB.</span><span class="sxs-lookup"><span data-stu-id="524d8-130">User’s Teams note is visible in Teams & SfB.</span></span> |
|<span data-ttu-id="524d8-131">McDonald</span><span class="sxs-lookup"><span data-stu-id="524d8-131">Islands</span></span> | <span data-ttu-id="524d8-132">Anotação do usuário definida em equipes visíveis somente no Teams.</span><span class="sxs-lookup"><span data-stu-id="524d8-132">User’s note set in Teams visible only in Teams.</span></span> <br> <span data-ttu-id="524d8-133">Nota do usuário definida no SfB visível apenas em SfB</span><span class="sxs-lookup"><span data-stu-id="524d8-133">User’s note set in SfB visible only in SfB</span></span> |
|<span data-ttu-id="524d8-134">SfB \* Modes</span><span class="sxs-lookup"><span data-stu-id="524d8-134">SfB\* modes</span></span> | <span data-ttu-id="524d8-135">Os usuários podem definir uma anotação apenas a partir do SfB.</span><span class="sxs-lookup"><span data-stu-id="524d8-135">Users can set a note only from SfB.</span></span> <br> <span data-ttu-id="524d8-136">A anotação SfB do usuário fica visível no SfB & Teams.</span><span class="sxs-lookup"><span data-stu-id="524d8-136">User’s SfB note is visible in SfB & Teams.</span></span>  |
|||

<span data-ttu-id="524d8-137">Um usuário só poderá definir uma anotação no Microsoft Teams se seu modo for TeamsOnly ou ilhas.</span><span class="sxs-lookup"><span data-stu-id="524d8-137">A user can only set a note in Teams if their mode is TeamsOnly or Islands.</span></span>  

### <a name="displaying-notes-set-in-skype-for-business"></a><span data-ttu-id="524d8-138">Exibir anotações definidas no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="524d8-138">Displaying notes set in Skype for Business</span></span>
  
<span data-ttu-id="524d8-139">Não há indicação visual de que uma anotação foi definida no Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="524d8-139">There is no visual indication that a note was set from Skype for Business.</span></span>

<span data-ttu-id="524d8-140">O Skype for Business não impõe um limite de caracteres nas anotações de status.</span><span class="sxs-lookup"><span data-stu-id="524d8-140">Skype for Business doesn’t enforce a character limit on status notes.</span></span> <span data-ttu-id="524d8-141">O Microsoft Teams só exibirá os primeiros 280 caracteres de uma anotação definida no Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="524d8-141">Microsoft Teams will only display the first 280 characters of a note set from Skype for Business.</span></span> <span data-ttu-id="524d8-142">Uma elipse (...) no final de uma nota indica truncamento.</span><span class="sxs-lookup"><span data-stu-id="524d8-142">An ellipse (…) at the end of a note indicates truncation.</span></span>
  
<span data-ttu-id="524d8-143">O Skype for Business não dá suporte a tempos de expiração de anotações.</span><span class="sxs-lookup"><span data-stu-id="524d8-143">Skype for Business doesn’t support expiry times for notes.</span></span>

<span data-ttu-id="524d8-144">Não há suporte para a migração de anotações do Skype for Business para o Teams quando um usuário é atualizado para o modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="524d8-144">Migration of notes from Skype for Business to Teams is not supported when a user is upgraded to TeamsOnly mode.</span></span>

## <a name="related-topics"></a><span data-ttu-id="524d8-145">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="524d8-145">Related topics</span></span>

[<span data-ttu-id="524d8-146">Coexistência com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="524d8-146">Coexistence with Skype for Business</span></span>](../../coexistence-chat-calls-presence.md)
