---
title: Salas do Microsoft Teams visão geral da licença no Centro de administração do Teams
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Licensing
- LIL_Placement
- seo-marvel-apr2020
description: Saiba mais sobre e compare Salas do Teams licenciamento e disponibilidade de recursos no Centro de administração do Teams.
ms.openlocfilehash: d88e7a0c0a6c17fb22f1cc94fcd4de65a3ff79a2
ms.sourcegitcommit: 732a7f3e120cfa221d42b4e8af2cf9ff623488a1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/08/2022
ms.locfileid: "67633631"
---
# <a name="microsoft-teams-rooms-license-overview-in-teams-admin-center"></a>Salas do Microsoft Teams visão geral da licença no Centro de administração do Teams

O Centro de administração do Teams permite que você exiba e gerencie Salas do Teams dispositivos e seus periféricos de um local central. Este artigo mostra quais [recursos](#comparison-of-teams-rooms-feature-availability-by-license) de gerenciamento você tem, dependendo se um dispositivo Salas do Teams é atribuído a uma licença Salas do Microsoft Teams Basic ou Salas do Microsoft Teams Pro.

Para obter mais informações sobre Salas do Microsoft Teams licenças, [consulte Salas do Microsoft Teams licenças](rooms-licensing.md).

## <a name="see-which-licenses-are-assigned-to-teams-rooms-devices"></a>Ver quais licenças são atribuídas a Salas do Teams dispositivos

Você pode ver qual licença seus dispositivos têm indo para dispositivos do Teams no centro de administração do Teams e, em seguida, selecionando a categoria de dispositivo (Salas do Teams no Windows, Salas do Teams no Android e Surface Hubs) que deseja ver. Por exemplo, se você selecionar dispositivos **Salas do Teams Teams** >  **no Windows**, verá algo semelhante à imagem a seguir. A **coluna** Licença mostra a Salas do Teams atribuída a cada dispositivo.

:::image type="content" source="../media/mtr-device-inventory-license-focus.png" alt-text="Salas do Teams lista de inventário com foco em licenças Standard, Pro e Pro (Avaliação).":::

Os dispositivos que têm **a licença Pro** podem acessar todos os recursos do Centro de administração do Teams. Dispositivos com outras licenças podem acessar um subconjunto desses recursos. Você pode ver quais recursos estão disponíveis para cada licença em Comparação Salas do Teams [disponibilidade de recursos por licença](#comparison-of-teams-rooms-feature-availability-by-license).

> [!IMPORTANT]
> Se você selecionar vários dispositivos que incluem licenças do Salas do Microsoft Teams Basic e do Salas do Microsoft Teams Pro, as ações que exigem uma licença do Salas do Microsoft Teams Pro serão executadas somente em dispositivos que tenham sido atribuídos a essa licença. A ação não será executada em dispositivos atribuídos à licença Salas do Microsoft Teams Basic.

## <a name="see-which-features-require-a-microsoft-teams-rooms-pro-license"></a>Ver quais recursos exigem uma licença Salas do Microsoft Teams Pro

Os recursos que exigem uma Salas do Microsoft Teams Pro :::image type="icon" source="../media/mtr-pro-icon.png" border="false"::: podem ser identificados procurando o ícone na página de detalhes de um dispositivo. Se o dispositivo selecionado no momento não tiver uma licença do Salas do Microsoft Teams Pro, você não poderá executar a ação e verá um prompt para atualizar.

:::image type="content" source="../media/mtr-restart-device-dialog.png" alt-text="Salas do Teams de reinicialização do dispositivo mostrando o ícone Pro.":::

## <a name="comparison-of-teams-rooms-feature-availability-by-license"></a>Comparação da disponibilidade Salas do Teams recursos por licença

A tabela a seguir mostra os recursos de gerenciamento disponíveis no Centro de administração do Teams para cada Salas do Microsoft Teams licença.

|                                               | Salas do Microsoft Teams Básico | Salas do Microsoft Teams Pro |
|:----------------------------------------------|:---------------------------:|:-------------------------:|
| **Atualizações automáticas de dispositivo**                  | &#x2714;                    | &#x2714;                  |
| **Análise básica de dispositivo**                    | &#x2714;                    | &#x2714;                  |
| **Integridade básica do dispositivo**                       | &#x2714;                    | &#x2714;                  |
| **Painel de qualidade de chamada**                    | &#x2714;                    | &#x2714;                  |
| **Criar e exibir workspaces**                | &#x2714;                    | &#x2714;                  |
| **Telemetria em tempo real**                       | &#x2714;                    | &#x2714;                  |
| **Atualizações regulares de recursos**                   | &#x2714;                    | &#x2714;                  |
| **Entrada e saída remotas**               | &#x2714;                    | &#x2714;                  |
| **Configurações de dispositivo Android**             |                             | &#x2714;                  |
| **Alertas de dispositivo**                             |                             | &#x2714;                  |
| **Análise de dispositivo – integridade e utilização** |                             | &#x2714;                  |
| **Exibição de detalhes do dispositivo**                        |                             | &#x2714;                  |
| **Detalhes de integridade do dispositivo**                     |                             | &#x2714;                  |
| **Marcas de dispositivo**                               |                             | &#x2714;                  |
| **Graph APIs**                                |                             | &#x2714;                  |
| **Atualizações manuais de dispositivo**                     |                             | &#x2714;                  |
| **Reinicialização remota**                            |                             | &#x2714;                  |
| **Gerenciamento de periféricos de dispositivo Windows**     |                             | &#x2714;                  |
| **Configurações do dispositivo Windows**                   |                             | &#x2714;                  |