---
title: "Adicionar o domínio SMTP ao Microsoft Teams como um domínio aceito no Exchange Online | Suporte da Microsoft"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Saiba como adicionar o domínio SMTP ao Microsoft Teams como um domínio aceito no Exchange Online para enviar notificações aos membros da equipe."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: c33cba163d3395be7214caf5df4e87eaa164e020
ms.sourcegitcommit: 2e557e90b4e30fe99ff9df3897b8e54f38ea2f2e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2017
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-accepted-domain-in-exchange-online"></a><span data-ttu-id="2ed88-103">Adicionar o domínio SMTP ao Microsoft Teams como um domínio aceito no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2ed88-103">Add the Microsoft Teams SMTP domain as an accepted domain in Exchange Online</span></span> 
=============================================================================

<span data-ttu-id="2ed88-104">Se você cria um Grupo do Office 365 no console de administração ou usando o Outlook, o Exchange Online é usado para enviar notificações quando um membro da equipe é adicionado a um Grupo.</span><span class="sxs-lookup"><span data-stu-id="2ed88-104">Whether you create an Office 365 Group in the admin console or by using Outlook, Exchange Online is used to send notifications of a team member being added to a Group.</span></span> <span data-ttu-id="2ed88-105">Essas mensagens são geradas a partir do seu locatário, pois representam o seu FQDN SMTP de domínio padrão.</span><span class="sxs-lookup"><span data-stu-id="2ed88-105">These messages are generated from your tenant as they represent your default domain SMTP FQDN.</span></span>

![](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

<span data-ttu-id="2ed88-106">O Teams usa o Microsoft Exchange Online também para envia notificações aos membros da equipe quando são adicionados.</span><span class="sxs-lookup"><span data-stu-id="2ed88-106">Teams uses Microsoft Exchange Online as well to send notifications to team members when they’ve been added.</span></span> <span data-ttu-id="2ed88-107">A diferença do domínio FQDN na mensagem SMTP é “@email.teams.microsoft.com” e poderia ser pego por um filtro de spam.</span><span class="sxs-lookup"><span data-stu-id="2ed88-107">The difference being the domain FQDN of the SMTP message is “@email.teams.microsoft.com” and could be caught by spam filtering.</span></span> <span data-ttu-id="2ed88-108">Como você pode ver na imagem abaixo, o Outlook considera essa mensagem como um remetente externo, sujeito a recursos padrão de segurança, como o bloqueio de imagens e de certos conteúdos.</span><span class="sxs-lookup"><span data-stu-id="2ed88-108">As you can see from the image below, Outlook considers this message as an external sender which is subject to standard security features such as blocking images and certain content.</span></span>

![](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

<span data-ttu-id="2ed88-109">Para uma operação simples e melhores resultados, considere acrescentar o domínio SMTP do Microsoft Teams na sua lista de “domínios aceitos” na configuração de spam do Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="2ed88-109">For best result and seamless operation, consider adding the Microsoft Teams SMTP domain to your “accepted domains” list in your Exchange Online spam configuration:</span></span>

![](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
