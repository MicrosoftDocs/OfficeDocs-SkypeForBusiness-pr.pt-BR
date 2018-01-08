---
title: "Adicionar o domínio SMTP ao Microsoft Teams como um domínio aceito no Exchange Online"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Saiba como adicionar o domínio SMTP ao Microsoft Teams como um domínio aceito no Exchange Online para enviar notificações aos membros da equipe."
ms.openlocfilehash: 70795d466059233f09bf1eeb61c9a977a311936e
ms.sourcegitcommit: 3faedb6057da8650b06b05f9c9bdd941d5ade175
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2017
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-accepted-domain-in-exchange-online"></a>Adicionar o domínio SMTP ao Microsoft Teams como um domínio aceito no Exchange Online 
=============================================================================

Se você cria um Grupo do Office 365 no console de administração ou usando o Outlook, o Exchange Online é usado para enviar notificações quando um membro da equipe é adicionado a um Grupo. Essas mensagens são geradas a partir do seu locatário, pois representam o seu FQDN SMTP de domínio padrão.

![Captura de tela de um exemplo de mensagem de e-mail do Outlook mostrando que um usuário foi adicionado a um grupo.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

O Teams usa o Microsoft Exchange Online também para envia notificações aos membros da equipe quando são adicionados. A diferença do domínio FQDN na mensagem SMTP é “@email.teams.microsoft.com” e poderia ser pego por um filtro de spam. Como você pode ver na imagem abaixo, o Outlook considera essa mensagem como um remetente externo, sujeito a recursos padrão de segurança, como o bloqueio de imagens e de certos conteúdos.

![Captura de tela de um exemplo de mensagem de e-mail do Outlook mostrando que um usuário foi adicionado a um grupo.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

Para uma operação simples e melhores resultados, considere acrescentar o domínio SMTP do Microsoft Teams na sua lista de “domínios aceitos” na configuração de spam do Exchange Online:

![Captura de tela da seção de listas de permissão das configurações de spam do Exchange Online.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
