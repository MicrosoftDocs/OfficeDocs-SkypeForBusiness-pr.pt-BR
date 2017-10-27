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
<a name="add-the-microsoft-teams-smtp-domain-as-an-accepted-domain-in-exchange-online"></a>Adicionar o domínio SMTP ao Microsoft Teams como um domínio aceito no Exchange Online 
=============================================================================

Se você cria um Grupo do Office 365 no console de administração ou usando o Outlook, o Exchange Online é usado para enviar notificações quando um membro da equipe é adicionado a um Grupo. Essas mensagens são geradas a partir do seu locatário, pois representam o seu FQDN SMTP de domínio padrão.

![](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

O Teams usa o Microsoft Exchange Online também para envia notificações aos membros da equipe quando são adicionados. A diferença do domínio FQDN na mensagem SMTP é “@email.teams.microsoft.com” e poderia ser pego por um filtro de spam. Como você pode ver na imagem abaixo, o Outlook considera essa mensagem como um remetente externo, sujeito a recursos padrão de segurança, como o bloqueio de imagens e de certos conteúdos.

![](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

Para uma operação simples e melhores resultados, considere acrescentar o domínio SMTP do Microsoft Teams na sua lista de “domínios aceitos” na configuração de spam do Exchange Online:

![](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
