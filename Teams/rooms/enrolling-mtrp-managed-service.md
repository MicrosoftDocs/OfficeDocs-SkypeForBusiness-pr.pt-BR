---
title: Registrar um Salas do Teams no serviço Salas do Microsoft Teams Premium gerenciado
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba mais sobre como registrar Salas do Microsoft Teams contas no Salas do Microsoft Teams Premium gerenciado.
f1keywords: ''
ms.openlocfilehash: c64fcaf6e817eb57be2915f4f7b6d8684f2ae49b
ms.sourcegitcommit: d425748a50964ebc78e5d38fce564a444a449f43
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2022
ms.locfileid: "65635449"
---
# <a name="enroll-a-device-in-the-microsoft-teams-rooms-premium-managed-service"></a>Registrar um dispositivo no serviço Salas do Microsoft Teams Premium gerenciado

Para registrar um Salas do Microsoft Teams no serviço gerenciado do Salas do Teams Premium, você precisa atribuir um ou mais usuários ao Administrador de Serviços Gerenciados e concluir as etapas de registro usando esse usuário.

## <a name="assign-users-to-the-managed-service-administrator-role"></a>Atribuir usuários à função administrador de serviços gerenciados

Conclua as seguintes etapas para atribuir usuários à função de Administrador de Serviços Gerenciados:

1. Faça logon [no portal Salas do Teams Premium com](https://portal.rooms.microsoft.com/) os mesmos privilégios de administrador usados para fazer logon no Centro de administração do Microsoft 365.
2. Navegue **até Configurações** >  **Configurações** >  **Roles e** selecione **Administrador de Serviços Gerenciados**.
3. Em **Administrador de Serviços Gerenciados**, selecione a guia **Atribuições** e, em seguida, **selecione Adicionar**.
4. Siga o assistente para nomear a atribuição e selecione os usuários que devem ser adicionados a ela. A atribuição será aplicada a todas as salas e grupos de salas.
5. No final do assistente de atribuição, selecione **Adicionar atribuição**.

Os usuários que recebem a função administrador de serviços gerenciados são responsáveis pelo gerenciamento e monitoramento diários do portal Salas do Teams Premium de serviços gerenciados.

Depois de ter atribuído usuários à função administrador de serviços gerenciados, continue para Registrar um dispositivo [Salas do Teams](enroll-a-device.md) para adicionar um dispositivo Salas do Teams ao portal de serviço gerenciado.

<!-- ## Enroll a Teams Rooms device

 To enroll a device in the Teams Rooms Premium managed service, see [Monitoring device software installation](monitor-software-installation-guide.md).

2. Select on the **?** icon at the top right-hand corner of the portal to launch the help menu. The help menu includes an [Installation guide](https://portal.rooms.microsoft.com/docs/MMR%20Monitoring%20Software%20Installation%20Guide%20Feb%202021.pdf) containing detailed enrollment instructions:

    1. Review the **Pre-requisites** section in the Installation guide. Confirm that the URLs listed in the **URLs Required for Communication** list are added to your firewall's traffic allow list.
    2. Follow the instructions in the **Enabling TPM Settings** section to enable the Trusted Platform Module (TPM) functionality on your device.
    3. Follow the instructions in the **Adding Proxy Settings** section to configure your device to use your proxy gateway, if you have one.
    4. Follow the instructions in the **Process** section to install the monitoring agent software and configure the self enrollment key on your device.

3. After the monitoring agent and unique XML key are configured on your device, navigate to **Rooms** > room name > **Status**, and then select **Enroll**.

    > [!NOTE]
    > The Teams Rooms device will remain in the **Onboarding** state until a Managed Service Administrator enrolls the device using the portal.

    See [Monitoring device software installation](monitoring-software-installation-guide.md).

<!--## Link to Installation guide

The **Help** menu provides a link to the [Installation guide](https://portal.rooms.microsoft.com/docs/MMR%20Monitoring%20Software%20Installation%20Guide%20Feb%202021.pdf) which in turn provides the following information:

- Instructions on URLs that need to be allow-listed to serve to enable room telemetry to be sent to the managed service.
- Instructions for applying the Microsoft Teams Rooms Premium monitoring agent and unique XML key as part of enrolling a device in the managed service.
- Troubleshooting instructions.-->
