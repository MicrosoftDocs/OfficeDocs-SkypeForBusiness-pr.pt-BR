---
title: Adicionar o domínio SMTP do teams como um domínio de remetente permitido no Exchange Online
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: anprakas
search.appverid: MET150
f1.keywords:
- NOCSH
description: Saiba como adicionar o domínio SMTP do Microsoft Teams como um domínio de remetente permitido no Exchange Online para enviar notificações para os membros da equipe.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 33605a8250c9cd2bdcec90ade7b3fcea536f8977
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582048"
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-allowed-sender-domain-in-exchange-online"></a><span data-ttu-id="4d510-103">Adicionar o domínio SMTP do Microsoft Teams como um domínio de remetente permitido no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="4d510-103">Add the Microsoft Teams SMTP domain as an allowed sender domain in Exchange Online</span></span> 
=============================================================================

<span data-ttu-id="4d510-104">Não importa se você cria um grupo do Microsoft 365 no console de administração ou usando o Outlook, o Exchange Online é usado para enviar notificações de um membro da equipe que está sendo adicionado a um grupo.</span><span class="sxs-lookup"><span data-stu-id="4d510-104">Whether you create a Microsoft 365 group in the admin console or by using Outlook, Exchange Online is used to send notifications of a team member being added to a group.</span></span> <span data-ttu-id="4d510-105">Essas mensagens são geradas a partir do seu locatário, pois representam o seu FQDN SMTP de domínio padrão.</span><span class="sxs-lookup"><span data-stu-id="4d510-105">These messages are generated from your tenant as they represent your default domain SMTP FQDN.</span></span>

![Captura de tela de um cabeçalho de mensagem mostrando um usuário adicionado a um grupo.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

<span data-ttu-id="4d510-107">O Microsoft Teams usa o Microsoft Exchange Online, além de enviar notificações para os membros da equipe quando eles forem adicionados.</span><span class="sxs-lookup"><span data-stu-id="4d510-107">Teams uses Microsoft Exchange Online as well to send notifications to team members when they've been added.</span></span> <span data-ttu-id="4d510-108">A diferença é o FQDN do domínio da mensagem SMTP é "@email. teams.microsoft.com" para locatários comerciais/comerciais e "@GCC-email.teams.microsoft.com" para locatários governamentais e pode ser detectada pela filtragem de spam.</span><span class="sxs-lookup"><span data-stu-id="4d510-108">The difference being the domain FQDN of the SMTP message is "@email.teams.microsoft.com" for Commercial/Business tenants and "@GCC-email.teams.microsoft.com" for Government tenants and could be caught by spam filtering.</span></span>

![Captura de tela de um cabeçalho de mensagem mostrando um usuário adicionado a um grupo.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

<span data-ttu-id="4d510-110">Para obter o melhor resultado e a operação contínua, considere adicionar o domínio SMTP do Microsoft Teams à sua lista de "domínios remetente permitidos" na sua configuração de spam do Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="4d510-110">For best result and seamless operation, consider adding the Microsoft Teams SMTP domain to your "allowed sender domains" list in your Exchange Online spam configuration:</span></span>

![Captura de tela da seção permitir listas de definições de configuração de spam](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
