---
title: Implantar Teams telefones e Teams displays usando o Intune
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: weizxue
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
search.appverid: MET150
localization_priority: Normal
description: Este artigo fornece uma visão geral dos recursos e com suporte Microsoft Teams exibições.
ms.openlocfilehash: 178f8c594f8953c56a2d354806e86f4a19de028f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120773"
---
# <a name="deploy-teams-phones-and-teams-displays-using-intune"></a>Implantar Teams telefones e Teams displays usando o Intune

Este artigo fornece uma visão geral de como implantar telefones Teams e Teams usando o Intune.

## <a name="conditional-access"></a>Acesso condicional

O Acesso Condicional é um recurso Azure Active Directory (Azure AD) que ajuda você a garantir que os dispositivos que acessam seus recursos Office 365 sejam gerenciados corretamente e sejam seguros.  Se você aplicar políticas de Acesso Condicional ao serviço Teams, dispositivos Android (incluindo telefones Teams e displays Teams) que o acesso Teams precisam ser inscritos no Intune e suas configurações precisam estar em conformidade com suas políticas.  Se o dispositivo não estiver inscrito no Intune ou se estiver inscrito, mas suas configurações não estão em conformidade com suas políticas, o Acesso Condicional impedirá que um usuário entre ou use o aplicativo Teams no dispositivo.

Normalmente, as políticas de conformidade definidas no Intune são atribuídas a grupos de usuários.  Isso significa que, se você atribuir uma política de conformidade do Android ao user@contoso.com, essa política se aplicará igualmente ao seu smartphone Android e a qualquer dispositivo Teams android no user@contoso.com conectado.

Se você usar o Acesso Condicional, que exige que o registro do Intune seja imposto, em sua organização, há algumas coisas que você precisa configurar para permitir um registro bem-sucedido do Intune:

- **Licença do Intune** O usuário que entra no dispositivo Teams deve ser licenciado para o Intune.  Desde que o dispositivo Teams seja conectado a uma conta de usuário que tenha uma licença válida do Intune, o dispositivo será automaticamente inscrito no Microsoft Intune como parte do processo de entrada.
- **Configurar o Intune** Você deve ter um locatário do Intune configurado corretamente para o registro do Administrador de Dispositivos Android.

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>Configurar o Intune para registrar Teams dispositivos baseados no Android

Teams Os dispositivos baseados em Android são gerenciados pelo Intune por meio do gerenciamento do Administrador de Dispositivos Android (DA). Antes que os dispositivos possam ser inscritos no Intune, há algumas etapas básicas a serem tomadas.  Se você já está gerenciando dispositivos com o Intune hoje, provavelmente já fez todas essas coisas.  Caso não seja, veja o que fazer:

1. Definir a Autoridade do MDM do Intune (gerenciamento de dispositivo móvel).  Se você nunca tiver usado o Intune antes, precisará definir a autoridade MDM antes de poder registrar dispositivos. Para obter mais informações, consulte [Definir a autoridade de gerenciamento de dispositivo móvel](/intune/fundamentals/mdm-authority-set).  Esta é uma etapa única que precisa ser feita ao criar um novo locatário do Intune.
2. Habilitar o registro do administrador de dispositivos Android. O dispositivo Teams android é gerenciado como dispositivos de administrador de dispositivos com o Intune.  O registro do administrador de dispositivos está desabilitado por padrão para locatários recém-criados.  Para obter mais informações, consulte [Registro do administrador de dispositivos Android](/intune/enrollment/android-enroll-device-administrator).
3. Atribuir licenças aos usuários. Os usuários Teams dispositivos que se registram no Intune devem ter uma licença válida do Intune. Para obter mais informações, consulte Atribuir licenças aos usuários para [que eles possam registrar dispositivos no Intune](/intune/fundamentals/licenses-assign).
4. Atribuir políticas de conformidade do Administrador de Dispositivos.  Crie uma política de conformidade do Administrador de Dispositivos Android e atribua-a ao grupo Azure Active Directory que contém os usuários que entrarão nos dispositivos Teams de segurança. Para obter mais informações, [consulte Use policies compliance to set rules for devices you manage with Intune](/mem/intune/protect/device-compliance-get-started).

## <a name="see-also"></a>Confira também

[Telefones para o Teams](phones-for-teams.md)

[Telefones IP certificados para Microsoft Teams](teams-ip-phones.md)

[Teams exibe](teams-displays.md)

[Gerenciar seus dispositivos no Teams](device-management.md)

[Teams Marketplace](https://office.com/teamsdevices)