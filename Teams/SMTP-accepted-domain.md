---
title: Adicionar o domínio SMTP de equipes da Microsoft como um domínio do remetente permitidos no Exchange Online
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: anprakas
search.appverid: MET150
description: Saiba como adicionar o domínio SMTP de equipes da Microsoft como um domínio do remetente permitidos no Exchange Online para enviar notificações aos membros da equipe.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f94b18994e277b90f96bc4fdbdefaa0b1f7a72e8
ms.sourcegitcommit: 0458232441d3aed8dd578f41a13078aa379c9b00
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/10/2019
ms.locfileid: "27789046"
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-allowed-sender-domain-in-exchange-online"></a>Adicionar o domínio SMTP de equipes da Microsoft como um domínio do remetente permitidos no Exchange Online 
=============================================================================

Se você cria um Grupo do Office 365 no console de administração ou usando o Outlook, o Exchange Online é usado para enviar notificações quando um membro da equipe é adicionado a um Grupo. Essas mensagens são geradas a partir do seu locatário, pois representam o seu FQDN SMTP de domínio padrão.

![Captura de tela de um exemplo de mensagem de e-mail do Outlook mostrando que um usuário foi adicionado a um grupo.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

O Teams usa o Microsoft Exchange Online também para envia notificações aos membros da equipe quando são adicionados. A diferença é o FQDN da mensagem SMTP do domínio é para os locatários comercial/Business "@email.teams.microsoft.com" e "@GCC-email.teams.com" para os locatários governamentais e poderia ser detectada pela filtragem de spam.

![Captura de tela de um exemplo de mensagem de e-mail do Outlook mostrando que um usuário foi adicionado a um grupo.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

Para obter melhores resultados e operação simplificada, considere a adição de domínio SMTP de equipes da Microsoft à sua lista de "domínios de remetente de permitidos" na configuração de spam do Exchange Online:

![Captura de tela da seção de listas de permissão das configurações de spam do Exchange Online.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
