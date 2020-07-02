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
f1.keywords:
- NOCSH
localization_priority: Normal
description: Atualizar os telefones e as barras de colaboração do Microsoft Teams remotamente usando o centro de administração do teams
ms.openlocfilehash: 7e47c9394eddfa73b8b55279b68ae59ff7b6de3d
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2020
ms.locfileid: "44944075"
---
# <a name="update-microsoft-teams-devices-remotely"></a>Atualizar dispositivos do Microsoft Teams remotamente

Usando o centro de administração do Microsoft Teams, você pode atualizar seus dispositivos de equipe, como telefones e barras de colaboração, remotamente, e pode escolher o comportamento de atualização automática do firmware do dispositivo. Você pode atualizar o seguinte em seus dispositivos usando o centro de administração do teams:

- Agente de administração do Teams e aplicativos do teams
- Aplicativo do portal da empresa
- Aplicativo de agente OEM
- Firmware do dispositivo

As atualizações de firmware de dispositivo podem ser aplicadas automaticamente ou agendadas para uma data e hora futuras. Outras atualizações de dispositivo disponíveis não são aplicadas automaticamente, mas podem ser aplicadas manualmente ou agendadas para uma data e hora futuras.

> [!NOTE]
> Enquanto as atualizações de firmware do dispositivo podem ser agendadas, se a data e a hora programadas ficarão após o máximo de 30 ou 90, a atualização do firmware será aplicada quando o atraso máximo for atingido. A data e a hora programadas são ignoradas.

## <a name="choose-automatic-device-firmware-update-behavior"></a>Escolher o comportamento de atualização automática do firmware do dispositivo

As atualizações do firmware do dispositivo são aplicadas automaticamente. Você pode decidir se deseja aplicar as atualizações assim que uma for liberada ou 30 ou 90 dias após o lançamento de uma atualização. Por padrão, as atualizações do firmware do dispositivo são aplicadas 30 dias, uma lançada.

> [!IMPORTANT]
> A versão mais recente da atualização do firmware não é aplicada ao seu dispositivo de equipe. Em vez disso, a atualização aplicada automaticamente ao seu dispositivo é atrasada em uma versão. Por exemplo, suponha que o dispositivo tenha a versão "10" aplicada e a versão "11" seja lançada. A versão "11" ainda não será aplicada. Em vez disso, seu dispositivo só será atualizado para a versão "11" após a versão "12" ser liberada.

Para escolher o comportamento de atualização automática para seus dispositivos, faça o seguinte:

1. Acesse o centro de administração do Microsoft Teams visitandohttps://admin.teams.microsoft.com
2. Navegar pelos **dispositivos**  >  **telefones** ou **barras de colaboração**
3. Selecione um ou mais dispositivos e, em seguida, selecione **Atualizar** .
4. Em **atualização automática de firmware**, selecione uma das seguintes opções:
    - Assim **que disponível** O segundo-atualização do firmware do dispositivo mais recente é aplicada o mais rápido possível depois que a atualização mais recente é lançada.
    - **Adiar 30 dias** Segundo-a atualização mais recente do firmware do dispositivo é aplicada 30 dias após o lançamento da atualização mais recente.
    - **Adiar 90 dias** O segundo-atualização do firmware do dispositivo mais recente é aplicada 90 dias após o lançamento da atualização mais recente.
5. Selecionar **atualização**

Se, por qualquer motivo, você precisar reverter uma atualização de firmware do dispositivo, será necessário redefinir o dispositivo para as configurações de fábrica. Redefina o dispositivo usando as instruções do fabricante.  

## <a name="manually-update-remote-devices"></a>Atualizar manualmente dispositivos remotos

Ao atualizar um ou mais dispositivos usando o centro de administração, você pode decidir se deseja atualizar os dispositivos imediatamente ou agendar uma atualização para uma data e hora futuras.

Para atualizar manualmente dispositivos remotos, faça o seguinte:

1. Acesse o centro de administração do Microsoft Teams visitandohttps://admin.teams.microsoft.com
2. Navegar pelos **dispositivos**  >  **telefones** ou **barras de colaboração**
3. Selecione um ou mais dispositivos e, em seguida, selecione **Atualizar** .
4. Em **Atualizações manuais**, selecione **agendar** se desejar agendar a atualização para uma data e hora futuras. As atualizações são aplicadas na data e na hora no fuso horário selecionado no **fuso horário**.

O que você verá depende se você tem um ou vários dispositivos selecionados. A imagem à esquerda abaixo mostra vários dispositivos selecionados enquanto a imagem à direita mostra um único dispositivo selecionado.

:::image type="content" source="../media/device-update-status.png" alt-text="Modos de exibição de um e vários dispositivos no painel de status de atualização do dispositivo":::

Ao selecionar vários dispositivos, você pode escolher quais tipos de atualização aplicar a cada dispositivo selecionado. Selecione os tipos de atualização que você deseja aplicar e selecione **Atualizar**.

Quando você seleciona um único dispositivo, as atualizações disponíveis para o dispositivo são mostradas. Se vários tipos de atualização estiverem disponíveis para o dispositivo, selecione cada tipo de atualização para aplicar. Você pode exibir a **versão atual** aplicada ao dispositivo e a **nova versão** que será aplicada. Selecione a (s) atualização (ções) que você deseja aplicar e selecione **Atualizar**.

Depois de selecionar **Atualizar**, as atualizações são aplicadas aos seus dispositivos na data e hora que você selecionou se agendou uma atualização. Se você não selecionou uma data e hora futuras, as atualizações são aplicadas aos seus dispositivos dentro de alguns minutos.
