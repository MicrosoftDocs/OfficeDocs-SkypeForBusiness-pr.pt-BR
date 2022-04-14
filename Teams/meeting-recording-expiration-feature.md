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
ms.openlocfilehash: 67cbef7e6fad2c9620de17f89b8b3a4fe641368e
ms.sourcegitcommit: 68162a8c9dee9a27af596353baabeda9b8fa64f3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2022
ms.locfileid: "64853222"
---
# <a name="meeting-recording-expiration-feature---frequently-asked-questions"></a>Recurso de expiração de gravação de reunião – Perguntas frequentes

**Qual é a mudança?**

Estamos introduzindo uma configuração de expiração padrão de 120  dias para todas as TMRs (Teams de reunião) recém-criadas. Isso está ativado por padrão para todos os locatários e você deve desativá-lo se não quiser esse recurso. O OneDrive e SharePoint monitorarão a data de validade definida em todas as TMRs e moverão automaticamente as TMRs para a lixeira na data de validade.

**Por que estamos introduzindo essa alteração?**

Respondemos às suas solicitações para o recurso de expiração de gravação de reunião. Esse é um mecanismo leve de manutenção para reduzir a desordem de armazenamento criada a partir de TMR frio. Em média, 99% das TMRs nunca são re amostradas após 120 dias.

**Por que isso está sendo ativado por padrão?**

Acreditamos que quase todos os clientes se beneficiarão da carga de armazenamento reduzida em seu locatário removendo gravações que provavelmente nunca serão novamente exibidas após 120 dias. Nossa meta é fornecer uma experiência o mais limpa possível para todos os clientes por padrão.

**Como a data de expiração é calculada?**

A data de expiração é calculada como o dia em que ela é criada mais o número padrão de dias definido na política de Teams pelo administrador.

**Como um administrador pode alterar a data de validade?**

Os administradores podem editar a configuração de expiração padrão no console Teams política. Essa alteração afetará apenas as TMRs recém-criadas desse ponto em diante. Não afetará nenhuma gravação antes dessa data.

Os administradores não podem alterar a data de validade em TMRs existentes. Isso é feito para proteger a decisão do usuário que possui a TMR.

**Quem afeta isso?**

Qualquer pessoa que armazene TMRs OneDrive ou SharePoint.

**Por que devo usar esse recurso?**

Esse recurso está sendo ativado por padrão. Para desabilitá-lo, altere a configuração de expiração padrão no console Teams política para **Sem expiração**.
Você deve usar isso para limitar o OneDrive do Sharepoint para o consumo de armazenamento em nuvem orientado por Teams de reunião. Uma gravação típica de reunião consome cerca de 400 MB por hora de gravação.

**Devo contar com esse recurso para uma conformidade estrita de segurança e conformidade?**

Não, você não deve confiar nisso para proteção legal, pois os usuários finais podem modificar a data de validade de todas as gravações que eles controlam.

**Uma política de retenção e/ou exclusão que eu defini no Centro de conformidade de segurança & substituirá a configuração Teams de expiração da gravação da reunião?**

Sim, todas as políticas definidas no centro de conformidade terão precedência total.

Por exemplo:

- Se você tiver uma política que diz que todos os arquivos em um site devem ser retidos por 100 dias e a configuração de expiração para uma gravação de reunião do Teams for de 30 dias, a gravação será mantida por 100 dias completos.
- Se você tiver uma política de exclusão que diz que todas as gravações de reunião do Teams serão excluídas após cinco dias e você tiver uma configuração de expiração para uma gravação de reunião do Teams de 30 dias, a gravação será excluída após cinco dias.

**O que acontece quando uma TMR expira?**

Na data de validade, a gravação é movida para a lixeira e o campo de data de validade é limpo. Se você recuperar a gravação da lixeira, ela não será excluída por esse recurso novamente porque a data de validade foi desmarcada.

**Como eu vou ser notificado sobre a expiração de um arquivo?**

- Todos verão uma notificação sobre a data de validade na lista de verificação de gravação na Teams de chat.
- Todos com acesso de visualização verão um ícone vermelho ao lado do arquivo na pasta do OneDrive ou do SharePoint 14 dias antes que o arquivo expire.
- O proprietário do arquivo receberá uma notificação por email quando a gravação expirar e será direcionado para a lixeira para recuperar a gravação.

**Quais SKUs são necessários para esse recurso?**

- Todas as SKUs terão esse recurso por padrão.

- Os usuários A1 terão o padrão de um período de expiração de 30 dias e não poderão modificar a data de validade.

**O arquivo expirar é um evento auditado e eu posso vê-lo em meus logs de auditoria?**

Sim, eles aparecerão como eventos de exclusão do sistema no log de auditoria.

**E se eu quiser que o administrador tenha controle total sobre o ciclo de vida das gravações de reunião e não quiser dar aos usuários finais a capacidade de substituir a data de validade?**

É recomendável usar as políticas de retenção e/ou exclusão de segurança e/ou exclusão disponíveis como parte do SKU de conformidade do E5. Essa oferta é destinada a resolver questões legais administrativas e políticas complexas orientadas por SLA.

Esse recurso destina-se exclusivamente a um mecanismo leve de manutenção para reduzir a desordem de armazenamento criada a partir de gravações Teams reuniões a frio.

**Quando o arquivo será excluído?**

O arquivo será excluído dentro de cinco dias a partir da data de validade, embora essa não seja uma garantia estrita.

**A expiração padrão é de 120 dias, mas quando eu Teams o centro de administração é de 60 dias. Porque?**

A maneira como as Teams políticas de segurança funcionam é se qualquer política no centro for definida pelo administrador, um instantâneo armazenado em cache será tirado de todas as configurações. Se o administrador definir qualquer atributo na política quando tivemos temporariamente um padrão de 60 dias, ele precisará alterá-lo manualmente para 120 dias. Se eles não tinham uma configuração personalizada antes de definirmos o padrão de 120 dias, eles receberão os 120 dias.
