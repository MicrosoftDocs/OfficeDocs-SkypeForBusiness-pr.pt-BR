---
title: Adicionar o domínio SMTP do Microsoft Teams como um domínio de remetente permitido no Exchange Online
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: anprakas
search.appverid: MET150
description: Saiba como adicionar o domínio SMTP do Microsoft Teams como um domínio de remetente permitido no Exchange Online para enviar notificações para os membros da equipe.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5ae8be5c4b596b8815b8677b6214163924cbb183
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37567124"
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-allowed-sender-domain-in-exchange-online"></a><span data-ttu-id="2dd45-103">Adicionar o domínio SMTP do Microsoft Teams como um domínio de remetente permitido no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2dd45-103">Add the Microsoft Teams SMTP domain as an allowed sender domain in Exchange Online</span></span> 
=============================================================================

<span data-ttu-id="2dd45-104">Se você cria um Grupo do Office 365 no console de administração ou usando o Outlook, o Exchange Online é usado para enviar notificações quando um membro da equipe é adicionado a um Grupo.</span><span class="sxs-lookup"><span data-stu-id="2dd45-104">Whether you create an Office 365 Group in the admin console or by using Outlook, Exchange Online is used to send notifications of a team member being added to a Group.</span></span> <span data-ttu-id="2dd45-105">Essas mensagens são geradas a partir do seu locatário, pois representam o seu FQDN SMTP de domínio padrão.</span><span class="sxs-lookup"><span data-stu-id="2dd45-105">These messages are generated from your tenant as they represent your default domain SMTP FQDN.</span></span>

![Captura de tela de um cabeçalho de mensagem mostrando um usuário adicionado a um grupo.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

<span data-ttu-id="2dd45-107">O Teams usa o Microsoft Exchange Online também para envia notificações aos membros da equipe quando são adicionados.</span><span class="sxs-lookup"><span data-stu-id="2dd45-107">Teams uses Microsoft Exchange Online as well to send notifications to team members when they’ve been added.</span></span> <span data-ttu-id="2dd45-108">A diferença é o FQDN do domínio da mensagem SMTP é "@email. teams.microsoft.com" para locatários comerciais/comerciais e "@GCC-email.teams.com" para locatários governamentais e pode ser detectada pela filtragem de spam.</span><span class="sxs-lookup"><span data-stu-id="2dd45-108">The difference being the domain FQDN of the SMTP message is “@email.teams.microsoft.com” for Commercial/Business tenants and "@GCC-email.teams.com" for Government tenants and could be caught by spam filtering.</span></span>

![Captura de tela de um cabeçalho de mensagem mostrando um usuário adicionado a um grupo.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

<span data-ttu-id="2dd45-110">Para obter o melhor resultado e a operação contínua, considere adicionar o domínio SMTP do Microsoft Teams à sua lista de "domínios remetente permitidos" na sua configuração de spam do Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="2dd45-110">For best result and seamless operation, consider adding the Microsoft Teams SMTP domain to your “allowed sender domains” list in your Exchange Online spam configuration:</span></span>

![Captura de tela da seção permitir listas de definições de configuração de spam](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
