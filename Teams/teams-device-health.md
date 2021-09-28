---
title: Gerenciando a saúde dos Teams dispositivos
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: snchatur
search.appverid: MET150
f1.keywords:
- NOCSH
description: Este artigo orientará você no gerenciamento da saúde de dispositivos Teams, dispositivos que Microsoft Teams instalados neles.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: d5e98e65c35b8319a7e4f8675b68d530fa382c31
ms.sourcegitcommit: ab9d27d7ddd1494539ae9424de200c9d0e76a9ec
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2021
ms.locfileid: "59984766"
---
# <a name="manage-the-health-of-teams-devices"></a>Gerenciar a saúde dos Teams dispositivos

Os administradores podem monitorar a saúde dos dispositivos instalados com Microsoft Teams usando o status de saúde, o que indica a gravidade dos problemas. Para verificar a saúde de um dispositivo, você pode  ir para a lista de dispositivos presente na seção dispositivos Teams do centro de administração Teams. A coluna status de saúde nesta lista indica o status de saúde atual do dispositivo. Selecionar esse status abre o painel **Status de** saúde , que fornece mais detalhes sobre problemas de saúde.

Muitos tipos de problemas podem contribuir para o status de saúde do dispositivo, e o sistema Teams centro de administração avalia a gravidade desses problemas à medida que ocorrem.

O administrador que gerencia os dispositivos Teams para sua organização pode decidir que a gravidade dos problemas para eles não é a mesma que a configuração padrão Teams fornece. Há uma maneira dos administradores personalizarem a gravidade e o impacto na saúde de seus dispositivos para corresponder às prioridades da organização.

Salas do Teams dispositivos têm periféricos anexados para fornecer uma experiência de reunião completa, como Alto-falante, Microfone, Exibição, Câmera. Os detalhes sobre eles estão disponíveis na página do dispositivo nas guias Periféricos e De saúde. A conectividade desses periféricos afeta a saúde do dispositivo pai.

## <a name="feature-details"></a>Detalhes do recurso

Ao exibir detalhes periféricos em uma página de dispositivo, agora você verá uma **opção Gerenciar impacto na saúde.** Além disso, os administradores também podem exibir o impacto que cada periférico tem na saúde do dispositivo.

Por padrão, todos os periféricos são definidos para **ter impacto crítico** na saúde do dispositivo. Se um periférico for desconectado, a saúde do dispositivo pai se  tornará **Crítica** e esse problema será abordado em Problemas críticos no painel de status de saúde.

> [!NOTE]
> As categorias **periféricos HDMI ingest** e **Compute** não estão disponíveis para personalização, pois são cruciais para o funcionamento do dispositivo pai.

## <a name="how-does-this-work"></a>Como isso funciona?

1. Um administrador pode selecionar os periféricos para os que deseja alterar o impacto de saúde. Em seguida, eles podem selecionar **Gerenciar impacto na saúde.** Como alternativa, eles também podem encontrar a **opção Gerenciar impacto na saúde** na guia **Periféricos** em cada cartão periférico.
1. O **painel de impacto** saúde será aberto e o administrador poderá selecionar o nível de impacto desejado para os periféricos selecionados e salvá-lo.

| Configurações Opções | Descrição |
|------------------|-------------|
| **Não urgente** | Quando definido para uma categoria periférica (como uma exibição ou um alto-falante) e o periférico é desconectado, o status de saúde do dispositivo Salas do Teams se tornará não urgente **(em** vez de **Crítico**). Novos problemas serão categorizados na seção **Não urgente** do painel de status de saúde.|
| **Sem impacto** | Quando definido para uma categoria periférica e o periférico é desconectado, o status de saúde do dispositivo Salas do Teams permanecerá **Saudável** (em vez de **Crítico**). Esse problema de saúde não aparece no painel de status de saúde.|
| **Crítico** | Quando definido para uma categoria periférica e o periférico é desconectado, o status de saúde do dispositivo Salas do Teams se tornará **Crítico**. Novos problemas serão categorizados na seção **Crítico** do painel de status de saúde.|
| **Redefinir para padrão** | Quando definido para uma categoria periférica, o impacto na saúde dessa categoria será redefinido para **Crítico**. Depois que essa opção for salva, as alterações serão aplicadas e o impacto na saúde refletirá essas alterações em diante.|

## <a name="applicable-device-categories"></a>Categorias de dispositivo aplicáveis

Atualmente, esse recurso está disponível para gerenciar o impacto na saúde dos periféricos associados aos dispositivos Salas do Microsoft Teams (Windows).

## <a name="impact-on-other-workflows"></a>Impacto em outros fluxos de trabalho

Se o impacto de saúde dos periféricos for reduzido na gravidade, os administradores poderão não notar problemas quando eles acontecerem. Você deve estar atento aos dispositivos de alta prioridade que precisam de monitoramento próximo.

Por exemplo, se um alerta for configurado para ser acionado para ConfRoom1 se sua saúde se tornar **Crítica**. O administrador reduziu o impacto de saúde da exibição e do alto-falante para essa sala de reunião do padrão, **Critical**, para **Não urgente**. Agora, se a exibição for desconectada, a saúde de ConfRoom1 se tornará **não urgente**. Nesse caso, o alerta não será disparado.
