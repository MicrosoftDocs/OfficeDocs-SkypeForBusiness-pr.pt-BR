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
localization_priority: Normal
search.appverid: MET150
description: Saiba mais sobre como registrar Salas do Microsoft Teams contas no Salas do Microsoft Teams Premium gerenciado.
f1keywords: ''
ms.openlocfilehash: 6ac3a9752fcb285c663e05939ae31b2e60a8a1e6
ms.sourcegitcommit: 3ebf9c5d27263b7e92163f1a61844a5367a4744f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/20/2021
ms.locfileid: "58449015"
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

Conclua as etapas a seguir para registrar um dispositivo no serviço Salas do Teams Premium gerenciado:

1. Faça logoff [no portal Salas do Teams Premium com](https://portal.rooms.microsoft.com/) um usuário que tenha sido atribuído a função Administrador de Serviço Gerenciado.
2. Selecione no **?** ícone no canto superior direito do portal para iniciar o menu de ajuda. O menu de ajuda inclui um [guia de instalação](https://portal.rooms.microsoft.com/docs/MMR%20Monitoring%20Software%20Installation%20Guide%20Feb%202021.pdf) contendo instruções detalhadas de registro:

    1. Revise a **seção Pré-requisitos** no guia Instalação. Confirme se as URLs listadas na **lista URLs Necessárias** para Comunicação são adicionadas à lista de autorizações de tráfego do firewall.
    2. Siga as instruções na seção **Habilitar** Configurações TPM para habilitar a funcionalidade TPM (Trusted Platform Module) em seu dispositivo.
    3. Siga as instruções na seção **Adicionando Configurações** proxy para configurar seu dispositivo para usar o gateway proxy, se você tiver um.
    4. Siga as instruções na seção **Processo para** instalar o software do agente de monitoramento e configurar a chave de auto-registro em seu dispositivo.

3. Depois que o agente de monitoramento e a chave XML exclusiva são configurados em seu dispositivo, navegue até **Salas** > nome da sala > **Status** e selecione **Registrar**.

    > [!NOTE]
    > O Salas do Teams permanecerá no estado **De** integração até que um Administrador de Serviços Gerenciados inscreva o dispositivo usando o portal.

## <a name="link-to-installation-guide"></a>Guia Link to Installation

O  menu Ajuda fornece um link para o guia [instalação](https://portal.rooms.microsoft.com/docs/MMR%20Monitoring%20Software%20Installation%20Guide%20Feb%202021.pdf) que, por sua vez, fornece as seguintes informações:

- Instruções sobre URLs que precisam ser listadas para servir para permitir que a telemetria de sala seja enviada para o serviço gerenciado.
- Instruções para aplicar o Salas do Microsoft Teams Premium de monitoramento e a chave XML exclusiva como parte do registro de um dispositivo no serviço gerenciado.
- Instruções de solução de problemas.
