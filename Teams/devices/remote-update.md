---
title: Atualizar dispositivos microsoft teams remotamente
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
localization_priority: Normal
description: Atualizar telefones e barras de colaboração do Microsoft Teams remotamente usando o Centro de administração do Teams
ms.openlocfilehash: e57ca3f357deeb005f845d37a17c4b20db5d2035
ms.sourcegitcommit: b255db7ef816d1884c9c71af86a901bd83a1d9ab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962882"
---
# <a name="update-microsoft-teams-devices-remotely"></a>Atualizar dispositivos microsoft teams remotamente

Usando o Centro de administração do Microsoft Teams, você pode atualizar seus dispositivos do Teams, como telefones e barras de colaboração, remotamente, e pode escolher o comportamento de atualização automática do firmware do dispositivo. Você pode atualizar o seguinte em seus dispositivos usando o Centro de administração do Teams:

- Agente de administração do aplicativo Teams e equipes
- Aplicativo do portal da empresa
- Aplicativo de agente OEM
- Firmware do dispositivo

As atualizações de firmware do dispositivo podem ser aplicadas automaticamente ou agendadas para uma data e hora futuras. Outras atualizações de dispositivo disponíveis não são aplicadas automaticamente, mas podem ser aplicadas manualmente ou agendadas para uma data e hora futuras.

> [!NOTE]
> Embora as atualizações de firmware do dispositivo possam ser agendadas, se a data e a hora agendadas ocorrerem após o atraso máximo de 30 ou 90 dias configurado, a atualização de firmware será aplicada quando o atraso máximo for atingido. A data e a hora agendadas são ignoradas. Além disso, a atualização remota de dispositivos do Microsoft Teams é um recurso que ainda não está disponível em locatários do Government Cloud (GCC-High) dos EUA.

Para gerenciar dispositivos, você precisa ser um administrador global, administrador do Serviço do Teams ou administrador de Dispositivo do Teams. Para obter mais informações sobre funções de administrador, [consulte Usar funções de administrador do Microsoft Teams para gerenciar o Teams.](../using-admin-roles.md)

## <a name="choose-automatic-device-firmware-update-behavior"></a>Escolha o comportamento de atualização automática do firmware do dispositivo

As atualizações de firmware do dispositivo são aplicadas automaticamente. Você pode decidir se deve aplicar atualizações assim que uma for lançada (se você escolher essa opção, as atualizações serão aplicadas no primeiro fim de semana após o lançamento de uma atualização) ou 30 ou 90 dias após o lançamento de uma atualização. Por padrão, as atualizações de firmware do dispositivo são aplicadas 30 dias após o lançamento.

> [!IMPORTANT]
> A versão mais recente da atualização de firmware não é aplicada ao seu dispositivo Teams. Em vez disso, a atualização que é aplicada automaticamente em seu dispositivo é atrasada em uma versão. Por exemplo, suponha que seu dispositivo tenha a versão "10" aplicada e a versão "11" seja lançada. A versão "11" ainda não será aplicada. Em vez disso, seu dispositivo só será atualizado para a versão "11" após o lançamento da versão "12".

> [!NOTE]
> Alguns dispositivos ainda não são compatíveis com a atualização automática de firmware. A aplicação de configurações automáticas de atualização de firmware em dispositivos que não são compatíveis com atualizações automáticas não terá nenhum efeito nesses dispositivos. Para perguntas sobre se seu dispositivo dará suporte a atualizações automáticas de firmware, entre em contato com o fabricante do dispositivo.

Para escolher o comportamento de atualização automática para seus dispositivos, faça o seguinte:

1. Entre no Centro de administração do Microsoft Teams visitando https://admin.teams.microsoft.com
2. Navegar **em Telefones de**  >  **Dispositivos** ou Barras de **Colaboração**
3. Selecione um ou mais dispositivos e, em seguida, selecione **Atualizar**
4. Em **Atualização Automática de Firmware,** selecione um dos seguintes:
    - **Assim que disponível** A segunda atualização mais recente de firmware de dispositivo é aplicada no primeiro fim de semana após o lançamento da atualização mais recente.
    - **Adiar 30 dias** A segunda atualização mais recente de firmware de dispositivo é aplicada 30 dias após o lançamento da atualização mais recente.
    - **Adiar 90 dias** A segunda atualização mais recente de firmware de dispositivo é aplicada 90 dias após o lançamento da atualização mais recente.
5. Selecionar **Atualizar**

Se, por qualquer motivo, você precisar reverter uma atualização de firmware do dispositivo, será necessário redefinir seu dispositivo para suas configurações de fábrica. Redefinir seu dispositivo usando as instruções do fabricante.  

## <a name="manually-update-remote-devices"></a>Atualizar manualmente dispositivos remotos

Ao atualizar um ou mais dispositivos usando o centro de administração, você pode decidir se atualiza os dispositivos imediatamente ou agendar uma atualização para uma data e hora futuras.

Para atualizar manualmente dispositivos remotos, faça o seguinte:

1. Entre no Centro de administração do Microsoft Teams visitando https://admin.teams.microsoft.com
2. Navegar **em Telefones de**  >  **Dispositivos** ou Barras de **Colaboração**
3. Selecione um ou mais dispositivos e, em seguida, selecione **Atualizar**
4. Em **Atualizações manuais,** selecione **Agendar** se quiser agendar a atualização para uma data e hora futuras. As atualizações são aplicadas na data e na hora no zona de tempo selecionada no **Timezone.**

O que você verá depende se você tiver um ou vários dispositivos selecionados. A imagem à esquerda abaixo mostra vários dispositivos selecionados enquanto a imagem à direita mostra um único dispositivo selecionado.

:::image type="content" source="../media/device-update-status.png" alt-text="Exibições individuais e múltiplas do dispositivo no painel de status de atualização do dispositivo":::

Ao selecionar vários dispositivos, você pode escolher quais tipos de atualização serão aplicados a cada dispositivo selecionado. Selecione os tipos de atualização que você deseja aplicar e selecione **Atualizar.**

Quando você seleciona um único dispositivo, as atualizações disponíveis para o dispositivo são mostradas. Se vários tipos de atualização estão disponíveis para o dispositivo, selecione cada tipo de atualização para aplicar. Você pode exibir **a versão Atual** aplicada no dispositivo e a **nova** versão que será aplicada. Selecione as atualizações que você deseja aplicar e selecione **Atualizar.**

Depois de selecionar **Atualizar,** as atualizações serão aplicadas aos seus dispositivos na data e na hora selecionadas se você tiver agendado uma atualização. Se você não selecionar uma data e hora futuras, as atualizações serão aplicadas aos seus dispositivos em poucos minutos.
