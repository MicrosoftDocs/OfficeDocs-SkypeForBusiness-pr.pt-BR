---
title: Acessando o portal de Gerenciamento Pro
author: altsou
ms.author: altsou
manager: serdars
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba mais sobre como acessar o portal Salas do Microsoft Teams Pro Management.
f1keywords: ''
ms.openlocfilehash: 64d2613b586a5c87f42b6a376a6c3a0d9ad3a799
ms.sourcegitcommit: 43db97b84ca70b1e6accfa7214d4106e4177a642
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68218075"
---
# <a name="accessing-the-pro-management-portal"></a>Acessando o portal de Gerenciamento Pro

Para acessar o portal Salas do Teams Pro Management, você precisa atribuir um ou mais usuários ao Administrador de Serviços Gerenciados e concluir as etapas de registro usando esse usuário.

## <a name="assign-users-to-the-managed-service-administrator-role"></a>Atribuir usuários à função administrador de serviços gerenciados

Conclua as seguintes etapas para atribuir usuários à função de Administrador de Serviços Gerenciados:

1. Faça logon no [portal Salas do Teams Pro Management](https://portal.rooms.microsoft.com/) com os mesmos privilégios de administrador usados para fazer logon no Centro de administração do Microsoft 365.
2. Navegue **até Funções de** > **Configurações e** >  selecione Administrador **de Serviços Gerenciados**.
3. Em **Administrador de Serviços Gerenciados**, selecione a guia **Atribuições** e, em seguida, **selecione Adicionar**.
4. Siga o assistente para nomear a atribuição e selecione os usuários que devem ser adicionados a ela. A atribuição será aplicada a todas as salas e grupos de salas.
5. No final do assistente de atribuição, selecione **Adicionar atribuição**.

Os usuários que recebem a função de Administrador de Serviços Gerenciados são responsáveis pelo gerenciamento diário e pelo monitoramento de Salas do Teams.

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
