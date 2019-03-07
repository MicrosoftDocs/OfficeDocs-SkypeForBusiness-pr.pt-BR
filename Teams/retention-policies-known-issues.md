---
title: Problemas conhecidos para políticas de retenção no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: article
ms.service: msteams
ms.reviewer: anach
description: Lista atual de problemas conhecidos para políticas de retenção Teams da Microsoft.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 411ef4bf12d55af0b913443219a00f3f56c7eba2
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30461184"
---
# <a name="known-issues-for-retention-policies-in-microsoft-teams"></a>Problemas conhecidos para políticas de retenção no Microsoft Teams

Os seguintes problemas conhecidos para políticas de retenção em equipes que estão sendo rastreados e investigados.

- Em Escolha equipes na linha local de mensagens do canal de equipes, talvez você veja os grupos do Office 365 que são não também às equipes. Isto será abordado no futuro.

- Em Escolha usuários na linha local equipes de bate-papo, talvez você veja convidados e os usuários não-mailbox. Políticas de retenção não devem ser definidos para convidados e estamos trabalhando para removê-los da lista.

- Assistente de ciclo de vida do Exchange (ELC) executado diariamente, mas ele tem um SLA de 7 dias. Como resultado, é possível que, se você tiver uma política de retenção de equipes para excluir itens mais antigos do que 60 dias, esses itens poderiam persistem até 67 dias. Isso não é uma nova situação - vier o modelo do Exchange. Obviamente, na maioria dos casos, não há nenhum atraso.


| | | |
|---------|---------|---------|
|![Ícone de ponto de decisão.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |Ponto de decisão         |Quais são os recursos de segurança e conformidade exigidos pela sua organização? A sua organização tem as licenças necessárias para atender aos requisitos empresariais de segurança e conformidade?         |
|![Ícone de próximos passos.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |Próximos passos         |Documente seus recursos de segurança e conformidade necessários.         |
