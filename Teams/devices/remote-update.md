---
title: Atualizar Microsoft Teams dispositivos remotamente
ms.author: dstrome
author: dstrome
ms.reviewer: rahulmi
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Atualizar Microsoft Teams telefones, Teams painéis e barras de colaboração remotamente usando o Teams de administração
ms.openlocfilehash: c35fc24be2456c4ee1583e7a073a7c4dcf8e7214
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727460"
---
# <a name="update-microsoft-teams-devices-remotely"></a>Atualizar Microsoft Teams dispositivos remotamente

Usando o centro de administração do Microsoft Teams, você pode atualizar seus dispositivos Teams, como telefones Teams, painéis Teams e barras de colaboração, remotamente, e você pode escolher o comportamento de atualização automática do firmware do dispositivo. Você pode atualizar o seguinte em seus dispositivos usando o Teams de administração:

- Teams administrador de aplicativos e equipes
- Aplicativo do portal da empresa
- Aplicativo de agente OEM
- Firmware do dispositivo

As atualizações de firmware do dispositivo podem ser aplicadas automaticamente ou agendadas para uma data e hora futuras. Outras atualizações de dispositivo disponíveis não são aplicadas automaticamente, mas podem ser aplicadas manualmente ou agendadas para uma data e hora futuras.

> [!NOTE]
> Embora as atualizações de firmware do dispositivo possam ser agendadas, se a data e a hora agendadas cairem após o atraso máximo de 30 ou 90 dias configurado, a atualização de firmware será aplicada quando o atraso máximo for atingido. A data e a hora agendadas são ignoradas. Além disso, atualizar Microsoft Teams dispositivos remotamente é um recurso que ainda não está disponível nos locatários da Nuvem governamental dos EUA (GCC-High).

Para gerenciar dispositivos, você precisa ser um administrador global, Teams de serviço ou Teams de dispositivo. Para obter mais informações sobre funções de administrador, consulte [Use Microsoft Teams de administrador para gerenciar Teams](../using-admin-roles.md).

## <a name="choose-automatic-device-firmware-update-behavior"></a>Escolher o comportamento de atualização automática do firmware do dispositivo

As atualizações de firmware do dispositivo são aplicadas automaticamente. Você pode decidir se deve aplicar atualizações assim que uma for lançada (se você escolher essa opção, as atualizações serão aplicadas no primeiro fim de semana após a atualização ser lançada), ou 30 ou 90 dias após a atualização ser lançada. Por padrão, as atualizações de firmware do dispositivo são aplicadas 30 dias um lançamento.

> [!IMPORTANT]
> A versão mais recente da atualização de firmware não é aplicada ao seu Teams dispositivo. Em vez disso, a atualização que é aplicada automaticamente em seu dispositivo é adiada por uma versão. Por exemplo, suponha que seu dispositivo tenha a versão "10" aplicada e a versão "11" seja lançada. A versão "11" ainda não será aplicada. Em vez disso, seu dispositivo só será atualizado para a versão "11" após a versão "12" ser lançada.

> [!NOTE]
> Alguns dispositivos ainda não suportam a atualização automática de firmware. A aplicação de configurações automáticas de atualização de firmware em dispositivos que não suportam atualizações automáticas não terá qualquer efeito nesses dispositivos. Para saber se o dispositivo dará suporte a atualizações automáticas de firmware, entre em contato com o fabricante do dispositivo.

Para escolher o comportamento de atualização automática para seus dispositivos, faça o seguinte:

1. Entre no centro de Microsoft Teams de administração visitando https://admin.teams.microsoft.com .
2. Navegar **dispositivos**  >  **telefones IP** ou **barras** de colaboração ou **Teams painéis**.
3. Selecione um ou mais dispositivos e selecione **Atualizar**.
4. Em **Atualização automática do firmware,** selecione um dos seguintes:
    - **Assim que disponível** A segunda atualização de firmware de dispositivo mais recente é aplicada no primeiro fim de semana após o lançamento da atualização mais recente.
    - **Adiar 30 dias** A segunda atualização de firmware de dispositivo mais recente é aplicada 30 dias após o lançamento da atualização mais recente.
    - **Adiar 90 dias** A segunda atualização de firmware de dispositivo mais recente é aplicada 90 dias após o lançamento da atualização mais recente.
5. Selecione **Atualizar**.

Se, por qualquer motivo, você precisar reverter uma atualização de firmware de dispositivo, será necessário redefinir seu dispositivo para suas configurações de fábrica. Redefinir o dispositivo usando as instruções de seu fabricante.  

## <a name="manually-update-remote-devices"></a>Atualizar manualmente dispositivos remotos

Quando você atualiza um ou mais dispositivos usando o centro de administração, você pode decidir se deve atualizar os dispositivos imediatamente ou agendar uma atualização para uma data e hora futuras.

Para atualizar manualmente dispositivos remotos, faça o seguinte:

1. Entre no centro de Microsoft Teams de administração visitando https://admin.teams.microsoft.com .
2. Navegar **dispositivos**  >  **telefones IP** ou **barras** de colaboração ou **Teams painéis**.
3. Selecione um ou mais dispositivos e selecione **Atualizar**.
4. Em **Atualizações manuais,** selecione **Agendar** se quiser agendar a atualização para uma data e hora futuras. As atualizações são aplicadas na data e hora no timezone selecionado em **Timezone**.

O que você verá dependerá se você tiver um ou vários dispositivos selecionados. A imagem à esquerda abaixo mostra vários dispositivos selecionados enquanto a imagem à direita mostra um único dispositivo selecionado.

:::image type="content" source="../media/device-update-status.png" alt-text="Exibições de dispositivo único e múltiplos no painel de status de atualização do dispositivo.":::

Ao selecionar vários dispositivos, você pode escolher quais tipos de atualização serão aplicados a cada dispositivo selecionado. Selecione os tipos de atualização que você deseja aplicar e selecione **Atualizar**.

Quando você seleciona um único dispositivo, as atualizações disponíveis para o dispositivo são mostradas. Se vários tipos de atualização estão disponíveis para o dispositivo, selecione cada tipo de atualização a ser aplicado. Você pode exibir a **versão atual** aplicada no dispositivo e a **nova versão** que será aplicada. Selecione as atualizações que você deseja aplicar e selecione **Atualizar**.

Depois de selecionar **Atualizar,** as atualizações serão aplicadas aos seus dispositivos na data e hora selecionadas se você tiver agendado uma atualização. Se você não tiver selecionado uma data e hora futuras, as atualizações serão aplicadas aos dispositivos em alguns minutos.
