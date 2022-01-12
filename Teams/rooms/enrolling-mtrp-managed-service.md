---
title: Registrar um Salas do Teams no serviço Salas do Microsoft Teams Premium gerenciado
author: v-smandalika
ms.author: v-smandalika
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
ms.openlocfilehash: 79dee52cc9c814338c6c5dc4c91245155ef2fd41
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2022
ms.locfileid: "61766964"
---
# <a name="enroll-a-device-in-the-microsoft-teams-rooms-premium-managed-service"></a>Registrar um dispositivo no serviço Salas do Microsoft Teams Premium gerenciado

Para registrar um Salas do Microsoft Teams no serviço gerenciado Salas do Teams Premium, você precisa atribuir mais um usuário ao Administrador de Serviços Gerenciados e, em seguida, concluir as etapas de registro usando esse usuário.

## <a name="assign-users-to-the-managed-service-administrator-role"></a>Atribuir usuários à função Administrador de Serviço Gerenciado

Conclua as etapas a seguir para atribuir usuários à função Administrador de Serviços Gerenciados:

1. Faça logoff no [portal Salas do Teams Premium com](https://portal.rooms.microsoft.com/) os mesmos privilégios de administrador que o usado para fazer logoff no Centro de administração do Microsoft 365.
2. Navegue **até Configurações**  >  **Configurações**  >  **Funções** e selecione Administrador de Serviço **Gerenciado.**
3. Em **Administrador de Serviço Gerenciado,** selecione a guia **Atribuições** e selecione **Adicionar**.
4. Siga o assistente para nomear a atribuição e selecione os usuários que devem ser adicionados a ela. A atribuição será aplicada a todas as salas e grupos de salas.
5. No final do assistente de atribuição, selecione **Adicionar atribuição**.

Os usuários que são atribuídos à função Administrador de Serviços Gerenciados são responsáveis pelo gerenciamento e monitoramento do portal de serviços gerenciados do Salas do Teams Premium do dia a dia.

Depois de ter atribuído usuários à função Administrador de [](#enroll-a-teams-rooms-device) Serviço Gerenciado, continue na seção Registrar um dispositivo para adicionar um dispositivo Salas do Teams ao portal de serviço gerenciado.

## <a name="enroll-a-teams-rooms-device"></a>Registrar um Salas do Teams de usuário

 Para registrar um dispositivo no serviço Salas do Teams Premium gerenciado, consulte [Monitoring device software installation](monitor-software-installation-guide.md).

<!--2. Select on the **?** icon at the top right-hand corner of the portal to launch the help menu. The help menu includes an [Installation guide](https://portal.rooms.microsoft.com/docs/MMR%20Monitoring%20Software%20Installation%20Guide%20Feb%202021.pdf) containing detailed enrollment instructions:

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
