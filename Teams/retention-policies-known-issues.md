---
title: Problemas conhecidos com políticas de retenção no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anach
description: Lista atual de problemas conhecidos para políticas de retenção do Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5565409ea2f3dbb83754ced08a78e12283b1601c
ms.sourcegitcommit: 4a22bf77f529cfc2e68a6498a0c4aa9030ee2168
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2019
ms.locfileid: "37968332"
---
# <a name="known-issues-for-retention-policies-in-microsoft-teams"></a>Problemas conhecidos com políticas de retenção no Microsoft Teams

> [!NOTE]
> Ainda não damos suporte à configuração para a retenção de mensagens de canal privado. A retenção de arquivos compartilhados em canais privados tem suporte.

Veja a seguir problemas conhecidos de políticas de retenção no Teams que estão sendo controladas e investigadas.

- Em escolher equipes na linha de localização de mensagens de canal do Teams, você pode ver os grupos do Office 365 que não são equipes também. Isso será abordado no futuro.

- Em escolher usuários na linha de local do chat do Teams, você pode ver convidados e usuários que não são usuários da caixa de correio. As políticas de retenção não devem ser definidas para convidados e estamos trabalhando para removê-las da lista.

- O assistente de ciclo de vida do Exchange (ELC) é executado diariamente, mas tem um SLA de 7 dias. Como resultado, é possível que, se você tiver uma política de retenção do teams para excluir itens com mais de 60 dias, esses itens possam persistir por até 67 dias. Essa não é uma nova situação-ela segue o modelo do Exchange. É claro que, na maioria dos casos, não há atraso.


| | | |
|---------|---------|---------|
|![Um ícone representando um ponto de decisão](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |Ponto de decisão         |Quais são os recursos de segurança e conformidade exigidos pela sua organização? A sua organização tem as licenças necessárias para atender aos requisitos empresariais de segurança e conformidade?         |
|![Um ícone que representa as próximas etapas](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |Próximas etapas         |Documente seus recursos obrigatórios de segurança e conformidade.         |
