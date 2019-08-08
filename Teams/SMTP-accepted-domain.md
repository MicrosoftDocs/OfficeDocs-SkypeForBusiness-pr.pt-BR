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
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: anprakas
search.appverid: MET150
description: Saiba como adicionar o domínio SMTP do Microsoft Teams como um domínio de remetente permitido no Exchange Online para enviar notificações para os membros da equipe.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5dc4b72e973bf6763b817c9bc4f133961cd000f7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245757"
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-allowed-sender-domain-in-exchange-online"></a>Adicionar o domínio SMTP do Microsoft Teams como um domínio de remetente permitido no Exchange Online 
=============================================================================

Se você cria um Grupo do Office 365 no console de administração ou usando o Outlook, o Exchange Online é usado para enviar notificações quando um membro da equipe é adicionado a um Grupo. Essas mensagens são geradas a partir do seu locatário, pois representam o seu FQDN SMTP de domínio padrão.

![Captura de tela de um cabeçalho de mensagem mostrando um usuário adicionado a um grupo.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

O Teams usa o Microsoft Exchange Online também para envia notificações aos membros da equipe quando são adicionados. A diferença é o FQDN do domínio da mensagem SMTP é "@email. teams.microsoft.com" para locatários comerciais/comerciais e "@GCC-email.teams.com" para locatários governamentais e pode ser detectada pela filtragem de spam.

![Captura de tela de um cabeçalho de mensagem mostrando um usuário adicionado a um grupo.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

Para obter o melhor resultado e a operação contínua, considere adicionar o domínio SMTP do Microsoft Teams à sua lista de "domínios remetente permitidos" na sua configuração de spam do Exchange Online:

![Captura de tela da seção permitir listas de definições de configuração de spam](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
