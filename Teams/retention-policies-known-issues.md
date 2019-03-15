---
title: Problemas conhecidos com políticas de retenção no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: reference
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
ms.openlocfilehash: e64bcb2959060b8237f06a1986f15a093eb321a2
ms.sourcegitcommit: 3014331fff89a0842c4db0b9adf0ef32f9728ade
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2019
ms.locfileid: "30641148"
---
# <a name="known-issues-for-retention-policies-in-microsoft-teams"></a>Problemas conhecidos com políticas de retenção no Microsoft Teams

Os seguintes problemas conhecidos para políticas de retenção em equipes que estão sendo rastreados e investigados.

- Em Escolha equipes na linha local de mensagens do canal de equipes, talvez você veja os grupos do Office 365 que são não também às equipes. Isto será abordado no futuro.

- Em Escolha usuários na linha local equipes de bate-papo, talvez você veja convidados e os usuários não-mailbox. Políticas de retenção não devem ser definidos para convidados e estamos trabalhando para removê-los da lista.

- Assistente de ciclo de vida do Exchange (ELC) executado diariamente, mas ele tem um SLA de 7 dias. Como resultado, é possível que, se você tiver uma política de retenção de equipes para excluir itens mais antigos do que 60 dias, esses itens poderiam persistem até 67 dias. Isso não é uma nova situação - vier o modelo do Exchange. Obviamente, na maioria dos casos, não há nenhum atraso.


| | | |
|---------|---------|---------|
|![Ícone de ponto de decisão.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |Ponto de decisão         |Quais são os recursos de segurança e conformidade exigidos pela sua organização? A sua organização tem as licenças necessárias para atender aos requisitos empresariais de segurança e conformidade?         |
|![Ícone de próximos passos.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |Próximos passos         |Documente seus recursos de segurança e conformidade necessários.         |
