---
title: Adicionar o domínio SMTP de equipes da Microsoft como um domínio do remetente permitidos no Exchange Online
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: anprakas
search.appverid: MET150
description: Saiba como adicionar o domínio SMTP de equipes da Microsoft como um domínio do remetente permitidos no Exchange Online para enviar notificações aos membros da equipe.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7f0b20f84484d4b0998a11653fe7f9d2bb1e9899
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23861581"
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-allowed-sender-domain-in-exchange-online"></a><span data-ttu-id="f5cb5-103">Adicionar o domínio SMTP de equipes da Microsoft como um domínio do remetente permitidos no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="f5cb5-103">Add the Microsoft Teams SMTP domain as an allowed sender domain in Exchange Online</span></span> 
=============================================================================

<span data-ttu-id="f5cb5-104">Se você cria um Grupo do Office 365 no console de administração ou usando o Outlook, o Exchange Online é usado para enviar notificações quando um membro da equipe é adicionado a um Grupo.</span><span class="sxs-lookup"><span data-stu-id="f5cb5-104">Whether you create an Office 365 Group in the admin console or by using Outlook, Exchange Online is used to send notifications of a team member being added to a Group.</span></span> <span data-ttu-id="f5cb5-105">Essas mensagens são geradas a partir do seu locatário, pois representam o seu FQDN SMTP de domínio padrão.</span><span class="sxs-lookup"><span data-stu-id="f5cb5-105">These messages are generated from your tenant as they represent your default domain SMTP FQDN.</span></span>

![Captura de tela de um exemplo de mensagem de e-mail do Outlook mostrando que um usuário foi adicionado a um grupo.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

<span data-ttu-id="f5cb5-107">O Teams usa o Microsoft Exchange Online também para envia notificações aos membros da equipe quando são adicionados.</span><span class="sxs-lookup"><span data-stu-id="f5cb5-107">Teams uses Microsoft Exchange Online as well to send notifications to team members when they’ve been added.</span></span> <span data-ttu-id="f5cb5-108">A diferença do domínio FQDN na mensagem SMTP é “@email.teams.microsoft.com” e poderia ser pego por um filtro de spam.</span><span class="sxs-lookup"><span data-stu-id="f5cb5-108">The difference being the domain FQDN of the SMTP message is “@email.teams.microsoft.com” and could be caught by spam filtering.</span></span>

![Captura de tela de um exemplo de mensagem de e-mail do Outlook mostrando que um usuário foi adicionado a um grupo.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

<span data-ttu-id="f5cb5-110">Para obter melhores resultados e operação simplificada, considere a adição de domínio SMTP de equipes da Microsoft à sua lista de "domínios de remetente de permitidos" na configuração de spam do Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="f5cb5-110">For best result and seamless operation, consider adding the Microsoft Teams SMTP domain to your “allowed sender domains” list in your Exchange Online spam configuration:</span></span>

![Captura de tela da seção de listas de permissão das configurações de spam do Exchange Online.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
