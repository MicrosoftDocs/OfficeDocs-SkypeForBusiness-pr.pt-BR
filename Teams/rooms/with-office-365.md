---
title: Criar contas de recursos para salas e dispositivos compartilhados do Teams
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Leia este artigo para obter informações sobre como criar contas de recursos para salas e dispositivos compartilhados, incluindo Salas do Microsoft Teams, Salas do Teams no Surface Hub e hot-desking em exibições do Teams.
ms.openlocfilehash: 1448496137088ce04dc087825e67f7d8b31afd80
ms.sourcegitcommit: 3ad7b46e31890fba7abe739138cd49527d5ca6b7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/05/2022
ms.locfileid: "68475493"
---
# <a name="create-and-configure-resource-accounts-for-rooms-and-shared-teams-devices"></a>Criar e configurar contas de recursos para salas e dispositivos compartilhados do Teams

Este artigo fornece etapas para criar contas de recursos para espaços compartilhados e dispositivos, e inclui etapas para configurar contas de recursos para o Salas do Microsoft Teams no Windows, Salas do Teams no Android, Salas do Teams no Surface Hub e hot desking em exibições do Teams.

As contas de recursos do Microsoft 365 são contas de caixa de correio e do Teams que são dedicadas a recursos específicos, como uma sala ou projetor. Essas contas de recursos podem responder automaticamente a convites de reunião usando regras que você define quando são criadas. Por exemplo, se você tiver um recurso comum, como uma sala de conferência, poderá configurar uma conta de recurso para essa sala de conferência que aceitará ou recusará automaticamente convites de reunião, dependendo da disponibilidade do calendário. 

Cada conta de recurso é exclusiva para uma única instalação Salas do Microsoft Teams ou o Teams exibe a implementação de mesa quente.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

> [!NOTE]
> Se estiver usando painéis do Microsoft Teams, Salas do Teams conta de recurso do Salas do Teams e dos painéis do Teams associados.

> [!NOTE]
> **Skype for Business** <br><br>
> Se você precisar habilitar sua conta de recurso para trabalhar com Skype for Business, consulte [Implantar Salas do Microsoft Teams com Skype for Business Server](with-skype-for-business-server-2015.md)

## <a name="before-you-begin"></a>Antes de você começar

### <a name="requirements"></a>Requisitos

Dependendo do seu ambiente, você precisa de uma ou mais funções para criar contas de recursos.

|**Ambiente**|**Funções necessárias**|
|-----|-----|
|Azure Active Directory  <br/> |Administrador Global ou Administrador de Usuários  <br/> |
|Active Directory  <br/> |Administradores corporativos do Active Directory, administradores de domínio ou têm direitos delegados para criar usuários. Direitos de Sincronização do Azure Active Directory Connect.  <br/> |
|Exchange Online  <br/> |Administrador Global ou Administrador do Exchange   <br/> |
|Exchange Server  <br/> |Gerenciamento da Organização do Exchange ou Gerenciamento de Destinatários   <br/> |

Se você estiver criando contas de recursos para Salas do Teams, o UPN deverá corresponder ao endereço SMTP da conta de recurso. Consulte [Salas do Microsoft Teams requisitos antes](requirements.md) de implantar Salas do Teams.

### <a name="what-license-do-you-need"></a>De que licença você precisa?

[!INCLUDE [mtr-device-config-license-include](../includes/mtr-device-config-license-include.md)]

## <a name="create-a-resource-account"></a>Criar uma conta de recurso

[!INCLUDE [mtr-device-config-account-include](../includes/mtr-device-config-account-include.md)]

## <a name="configure-mailbox-properties"></a>Configurar propriedades da caixa de correio

[!INCLUDE [mtr-device-config-mailbox-include](../includes/mtr-device-config-mailbox-include.md)]

## <a name="turn-off-password-expiration"></a>Desativar a expiração da senha

[!INCLUDE [mtr-device-config-password-include](../includes/mtr-device-config-password-include.md)]

## <a name="assign-a-meeting-room-license"></a>Atribuir uma licença de sala de reunião

[!INCLUDE [mtr-device-config-assign-include](../includes/mtr-device-config-assign-include.md)]

## <a name="next-steps"></a>Próximas etapas

### <a name="meeting-policies"></a>Políticas de reunião

[!INCLUDE [mtr-device-config-policies-include](../includes/mtr-device-config-policies-include.md)]

### <a name="calling"></a>Chamadas

Não há requisitos exclusivos para habilitar a chamada com contas de recursos. Você habilita a conta de recurso para chamada da mesma maneira que habilita um usuário normal.

> [!NOTE]
> Recomendamos desativar a caixa postal para dispositivos compartilhados atribuindo uma política de chamada às contas de recursos do dispositivo. Consulte [Chamadas e encaminhamento de chamadas no Teams](../teams-calling-policy.md) para obter mais informações.

[!INCLUDE [mtr-device-config-calendar-include](../includes/mtr-device-config-calendar-include.md)]

## <a name="related-articles"></a>Artigos relacionados

[Configurar contas para Salas do Microsoft Teams](rooms-configure-accounts.md)

[Planejar as Salas do Microsoft Teams](rooms-plan.md)

[Implantar Salas do Microsoft Teams](rooms-deploy.md)

[Gerenciar Salas do Microsoft Teams](rooms-manage.md)

[Salas do Microsoft Teams licenciamento](rooms-licensing.md)
