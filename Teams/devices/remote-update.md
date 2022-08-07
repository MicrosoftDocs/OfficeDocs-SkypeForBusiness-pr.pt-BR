---
title: Atualizar dispositivos do Microsoft Teams remotamente
ms.author: dstrome
author: dstrome
ms.reviewer: rahulmi
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Devices
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Atualizar telefones, painéis do Teams e barras de colaboração do Microsoft Teams remotamente usando o centro de administração do Teams
ms.openlocfilehash: 36f84025feec5b88b2cbf28a52fcb89cb76aeaa5
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269456"
---
# <a name="update-microsoft-teams-devices-remotely"></a>Atualizar dispositivos do Microsoft Teams remotamente

Usando o centro de administração do Microsoft Teams, você pode atualizar seus dispositivos do Teams, como telefones do Teams, painéis do Teams e barras de colaboração, remotamente, e pode escolher o comportamento de atualização automática do firmware do dispositivo. Você pode atualizar o seguinte em seus dispositivos usando o Centro de administração do Teams:

- Aplicativo do Teams e agente de administração do Teams
- Aplicativo do portal da empresa
- Aplicativo do agente OEM
- Firmware do dispositivo

As atualizações de firmware do dispositivo podem ser aplicadas automaticamente ou agendadas para uma data e hora futuras. Outras atualizações de dispositivo disponíveis não são aplicadas automaticamente, mas podem ser aplicadas manualmente ou agendadas para uma data e hora futuras.

> [!NOTE]
> Embora as atualizações de firmware do dispositivo possam ser agendadas, se a data e hora agendadas cair após o atraso máximo de 30 ou 90 dias configurado, a atualização de firmware será aplicada quando o atraso máximo for atingido. A data e a hora agendadas são ignoradas. Além disso, atualizar dispositivos do Microsoft Teams remotamente é um recurso que ainda não está disponível em locatários da Nuvem do Governo dos EUA (GCC-High).

Para gerenciar dispositivos, você precisa ser um administrador global, administrador do Serviço do Teams ou administrador de dispositivos do Teams. Para obter mais informações sobre funções de administrador, [consulte Usar funções de administrador do Microsoft Teams para gerenciar o Teams](../using-admin-roles.md).

## <a name="choose-automatic-device-firmware-update-behavior"></a>Escolher o comportamento de atualização automática de firmware do dispositivo

As atualizações de firmware do dispositivo são aplicadas automaticamente. Você pode decidir se deseja aplicar atualizações assim que uma for lançada (se você escolher essa opção, as atualizações serão aplicadas no primeiro fim de semana após o lançamento de uma atualização) ou 30 ou 90 dias após o lançamento de uma atualização. Por padrão, as atualizações de firmware do dispositivo são aplicadas 30 dias um lançamento.

> [!IMPORTANT]
> A versão mais recente da atualização de firmware não é aplicada ao seu dispositivo Teams. Em vez disso, a atualização aplicada automaticamente em seu dispositivo é atrasada por uma versão. Por exemplo, suponha que seu dispositivo tenha a versão "10" aplicada e a versão "11" seja lançada. A versão "11" ainda não será aplicada. Em vez disso, seu dispositivo só será atualizado para a versão "11" após o lançamento da versão "12".

> [!NOTE]
> Alguns dispositivos ainda não dão suporte à atualização automática de firmware. Aplicar configurações de atualização automática de firmware em dispositivos que não dão suporte a atualizações automáticas não terá nenhum efeito nesses dispositivos. Para perguntas sobre se o dispositivo oferecerá suporte a atualizações automáticas de firmware, entre em contato com o fabricante do dispositivo.

Para escolher o comportamento de atualização automática para seus dispositivos, faça o seguinte:

1. Entre no Centro de administração do Microsoft Teams visitando https://admin.teams.microsoft.com.
2. Navegue pelos **telefones IP dos Dispositivos do** **Teams** > , **barras de colaboração** **ou painéis do Teams**.
3. Selecione um ou mais dispositivos e, em seguida, selecione **Atualizar**.
4. Em **Atualização Automática de Firmware**, selecione um dos seguintes:
    - **Assim que disponível** A segunda atualização de firmware do dispositivo mais recente é aplicada no primeiro fim de semana após o lançamento da atualização mais recente.
    - **Adiar 30 dias** A segunda atualização de firmware do dispositivo mais recente é aplicada 30 dias após o lançamento da atualização mais recente.
    - **Adiar 90 dias** A segunda atualização de firmware do dispositivo mais recente é aplicada 90 dias após o lançamento da atualização mais recente.
5. Selecione **Atualizar**.

Se, por qualquer motivo, você precisar reverter uma atualização de firmware do dispositivo, precisará redefinir seu dispositivo para suas configurações de fábrica. Redefina seu dispositivo usando as instruções de seu fabricante.  

## <a name="manually-update-remote-devices"></a>Atualizar manualmente dispositivos remotos

Ao atualizar um ou mais dispositivos usando o centro de administração, você pode decidir se deseja atualizar os dispositivos imediatamente ou agendar uma atualização para uma data e hora futuras.

Para atualizar manualmente os dispositivos remotos, faça o seguinte:

1. Entre no Centro de administração do Microsoft Teams visitando https://admin.teams.microsoft.com.
2. Navegue pelos **telefones IP dos Dispositivos do** **Teams** > , **barras de colaboração** **ou painéis do Teams**.
3. Selecione um ou mais dispositivos e, em seguida, selecione **Atualizar**.
4. Em **Atualizações manuais**, selecione **Agendar** se quiser agendar a atualização para uma data e hora futuras. As atualizações são aplicadas na data e hora no fuso horário selecionado no **fuso horário**.

O que você verá dependerá se você tiver um ou vários dispositivos selecionados. A imagem à esquerda abaixo mostra vários dispositivos selecionados enquanto a imagem à direita mostra um único dispositivo selecionado.

:::image type="content" source="../media/device-update-status.png" alt-text="Exibições de dispositivo único e múltiplo no painel de status de atualização do dispositivo.":::

Ao selecionar vários dispositivos, você pode escolher quais tipos de atualização aplicar a cada dispositivo selecionado. Selecione os tipos de atualização que você deseja aplicar e selecione **Atualizar**.

Quando você seleciona um único dispositivo, as atualizações disponíveis para o dispositivo são mostradas. Se vários tipos de atualização estão disponíveis para o dispositivo, selecione cada tipo de atualização a ser aplicado. Você pode exibir **a versão atual** aplicada no dispositivo e a **nova** versão que será aplicada. Selecione as atualizações que você deseja aplicar e selecione **Atualizar**.

Depois de selecionar **Atualizar**, as atualizações serão aplicadas aos seus dispositivos na data e hora selecionadas se você tiver agendado uma atualização. Se você não tiver selecionado uma data e hora futuras, as atualizações serão aplicadas aos seus dispositivos em alguns minutos.
