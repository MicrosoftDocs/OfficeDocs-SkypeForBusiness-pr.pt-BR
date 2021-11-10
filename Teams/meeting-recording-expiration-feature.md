---
title: Recurso de expiração de gravação de reunião
author: cichur
ms.author: v-cichur
ms.reviewer: ''
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Saiba mais sobre o recurso de expiração de gravação de reunião Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cfbbc8602044c0429de414b94b88d0e0e5aa8b19
ms.sourcegitcommit: 11a803d569a57410e7e648f53b28df80a53337b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2021
ms.locfileid: "60889518"
---
# <a name="meeting-recording-expiration-feature---frequently-asked-questions"></a>Recurso de expiração de gravação de reunião - Perguntas frequentes

**Qual é a mudança?**

Estamos introduzindo uma configuração de expiração padrão de 60 dias para todas as TMRs (gravações de reunião) recém-criadas Teams reunião.  Isso está em uso por padrão para todos os locatários e você deve a desativar se não quiser esse recurso. O OneDrive e o SharePoint monitorarão a data de expiração definida em todas as TMRs e moverão automaticamente as TMRs para a lixeira na data de expiração.

**Por que estamos introduzindo essa alteração?**

Respondemos às suas solicitações para o recurso de expiração de gravação de reunião. Este é um mecanismo de limpeza leve para reduzir a desordem de armazenamento criada a partir de TMR a frio. Em média, 99% das TMRs nunca são re amostradas após 60 dias.

**Por que isso está sendo ativado por padrão?**

Acreditamos que quase todos os clientes se beneficiarão da carga de armazenamento reduzida em seu locatário removendo gravações que provavelmente nunca serão re-assistidas após 60 dias. Nosso objetivo é fornecer uma experiência o mais limpa possível para todos os clientes por padrão.

**Como a data de expiração é calculada?**

A data de expiração é calculada como o dia em que é criada, mais o número padrão de dias definidos na política de Teams pelo administrador.

**Como um administrador pode alterar a data de expiração?**

Os administradores podem editar a configuração de expiração padrão no console Teams política. Essa alteração afetará apenas as TMRs recém-criadas desse ponto em diante. Não afetará nenhuma gravação antes dessa data.

Os administradores não podem alterar a data de expiração em TMRs existentes. Isso é feito para proteger a decisão do usuário proprietário da TMR.

**Quem causa esse impacto?**

Qualquer pessoa que armazenar TMRs em OneDrive ou SharePoint.

**Por que devo usar esse recurso?**

Esse recurso está sendo ligado por padrão. Para desabilitá-lo, altere a configuração de expiração padrão no console Teams de política para **Sem expiração**.
Você deve usá-lo para limitar o OneDrive ou o Sharepoint para consumo de armazenamento em nuvem impulsionado por Teams de reunião. Uma gravação típica de reunião consome cerca de 400 MB por hora de gravação.

**Devo contar com esse recurso para uma rigorosa adesão à segurança e à conformidade?**

Não, você não deve depender disso para proteção legal, pois os usuários finais podem modificar a data de expiração de todas as gravações que eles controlam.

**Será que uma política de retenção & e/ou exclusão que eu defini no Centro de Conformidade e Segurança substituirá a configuração de Teams de expiração de gravação de reunião?**

Sim, todas as políticas definidas no centro de conformidade terão precedência total.

Por exemplo:

- Se você tiver uma política que diga que todos os arquivos em um site devem ser mantidos por 100 dias, e a configuração de expiração para uma gravação de reunião do Teams for de 30 dias, a gravação será mantida pelos 100 dias completos.
- Se você tiver uma política de exclusão que diga que todas as gravações de reunião Teams serão excluída Teams s após cinco dias e você tiver uma configuração de expiração para uma gravação de reunião de 30 dias, a gravação será excluída após cinco dias.

**O que acontece quando uma TMR expira?**

Na data de expiração, a gravação é movida para a lixeira e o campo de data de expiração é limpo. Se você recuperar a gravação da lixeira, ela não será excluída por esse recurso novamente porque a data de expiração foi limpa.

**Como eu vou ser notificado sobre a expiração de um arquivo?**

- Todos verão uma notificação sobre a data de expiração na lista de verificação de gravação na Teams de chat.
- Todos com acesso de visualização verão um ícone vermelho ao lado do arquivo na pasta do OneDrive ou do SharePoint 14 dias antes que o arquivo expire.
- O proprietário do arquivo receberá uma notificação por email quando a gravação expirar e será direcionado para a lixeira para recuperar a gravação.

**Quais SKUs são necessários para esse recurso?**

- Todas as SKUs terão esse recurso por padrão.

- Todos os usuários serão padrão para um período de expiração de 30 dias e não poderão modificar a data de expiração.

**O arquivo expirar é um evento auditado e eu posso vê-lo em meus logs de auditoria?**

Sim, eles aparecerão como eventos de exclusão do sistema no log de auditoria.

**E se eu quiser que o administrador tenha controle total sobre o ciclo de vida das gravações de reunião e não quiser dar aos usuários finais a capacidade de substituir a data de expiração?**

Recomendamos usar as políticas de retenção e/ou exclusão de segurança e/ou exclusão disponíveis como parte da SKU de conformidade do E5. Essa oferta é destinada a resolver questões legais administrativas e políticas complexas orientadas por SLA.

Esse recurso é destinado apenas como um mecanismo de limpeza leve para reduzir a desordem de armazenamento criada a partir de gravações de reuniões Teams a frio.

**Quando o arquivo será excluído?**

O arquivo será excluído dentro de cinco dias após a data de expiração, embora essa não seja uma garantia estrita.
