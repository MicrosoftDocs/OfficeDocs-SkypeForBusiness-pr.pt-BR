---
title: Visão geral dos modelos de reunião personalizados no Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ralphmaamari
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365initiative-meetings
appliesto:
- Microsoft Teams
description: Saiba mais sobre modelos de reunião personalizados no Microsoft Teams Premium.
ms.openlocfilehash: 0ed766141e09b9c26d8e8c6f5e8fdd12195ddb78
ms.sourcegitcommit: 4fdbd93aacb52a4fca68e31eb04d0495d4e27a10
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/27/2022
ms.locfileid: "69672911"
---
# <a name="overview-of-custom-meeting-templates-in-microsoft-teams"></a>Visão geral dos modelos de reunião personalizados no Microsoft Teams

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

Microsoft o Teams Premium inclui a capacidade de criar modelos de reunião personalizados. Os modelos de reunião podem ser usados para controlar as configurações de reunião que o organizador da reunião normalmente controla. Com modelos, você pode criar experiências de reunião consistentes em sua organização e ajudar a impor requisitos de conformidade e regras de negócios.

Os modelos de reunião podem ser usados para impor configurações ou para definir padrões. Cada configuração de modelo pode ser bloqueada para que o organizador da reunião não possa alterá-la ou pode ser deixada desbloqueada para que o organizador da reunião altere, se necessário.

As seguintes configurações de reunião podem ser controladas usando um modelo de reunião:

|Configuração|Descrição|
|:------|:----------|
|Chat|Especifica se o chat da reunião está disponível. Também pode ser usado para impedir o chat antes e depois da reunião.|
|Criptografia de ponta a ponta|Especifica se a reunião é criptografada.|
|Lobby|Especifica quem pode ignorar o lobby e ingressar diretamente na reunião.|
|Gerenciar o que os participantes veem|Especifica se os organizadores da reunião podem visualizar e aprovar o conteúdo que está sendo compartilhado na tela antes que outros participantes da reunião possam vê-lo.|
|Microfone e câmera para participantes|Especifica se os participantes podem desmutar e usar a câmera.|
|Notificar quando os chamadores ingressarem e saírem|Especifica se um som é reproduzido quando as pessoas que ligam por telefone se juntam ou saem da reunião.|
|Q&A|Especifica se os participantes podem usar o recurso Q&A para fazer perguntas durante a reunião.|
|Reações|Especifica se os participantes podem usar reações ou levantar a mão na reunião.|
|Gravando|Especifica quem pode gravar e se a reunião é gravada automaticamente.|
|Rótulo de confidencialidade|Especifica o rótulo de confidencialidade a ser usado para a reunião.|
|Marcas d' água|Especifica se as marcas d'água são usadas para feeds de câmera e conteúdo compartilhados na tela na reunião.|

Alguns exemplos de quando um modelo pode ser útil são:

- Impor a gravação automática de reunião para determinados tipos de reuniões.
- Restringir o chat e a câmera e o áudio do participante e usar o recurso Q&A para reuniões no estilo de apresentação.
- Usando um padrão mais rigoroso para quem pode ignorar o lobby, mas permitindo que o organizador da reunião altere a configuração, se necessário.

Para saber como criar modelos de reunião, consulte [Criar um modelo de reunião personalizado no Microsoft Teams](create-custom-meeting-template.md).

## <a name="templates-with-sensitivity-labels"></a>Modelos com rótulos de confidencialidade

Os modelos têm a opção de especificar um rótulo de confidencialidade. Os rótulos também podem ser aplicados diretamente às reuniões, independentemente dos modelos. Os rótulos de confidencialidade podem controlar algumas das mesmas configurações que os modelos:

- Criptografia de ponta a ponta
- Chat de reunião
- Gravar automaticamente
- Quem pode ignorar o lobby
- Quem pode apresentar
- Quem pode gravar
- Marcas d' água

Se alguma dessas configurações estiver configurada no rótulo, elas substituirão essas configurações no modelo.

## <a name="templates-included-with-teams"></a>Modelos incluídos no Teams

O Teams Premium inclui vários modelos de reunião padrão que você pode disponibilizar aos seus usuários:

- Reunião Grande
- Reunião protegida
- Prefeitura
- [Compromisso virtual](virtual-appointment-meeting-template.md)
- Webinar

Além disso, esses modelos estão disponíveis no Teams para Educação:

- Classe
- Grupo de discussão
- Palestra
- Conferência de professores pai

Você pode atualizar as configurações nesses modelos se precisar.

## <a name="related-topics"></a>Tópicos relacionados

[Configurar reuniões do Teams com três camadas de proteção](configure-meetings-three-tiers-protection.md)

[Use modelos de reunião do Teams, rótulos de confidencialidade e políticas de administrador juntos](meeting-templates-sensitivity-labels-policies.md)
