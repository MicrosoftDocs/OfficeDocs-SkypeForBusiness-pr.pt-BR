---
title: Implantar Teams telefones, Teams e Salas do Microsoft Teams no Android usando o Intune
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.localizationpriority: medium
description: Este artigo fornece uma visão geral dos recursos e com suporte Microsoft Teams exibições.
ms.openlocfilehash: 96ffaef167fd40b320ff4c1b9b7a6dca0e9c3325
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60861958"
---
# <a name="deploy-teams-phones-teams-displays-and-microsoft-teams-rooms-on-android-using-intune"></a>Implantar Teams telefones, Teams e Salas do Microsoft Teams no Android usando o Intune

Este artigo fornece uma visão geral de como implantar telefones Teams, Teams e Salas do Microsoft Teams no Android usando o Intune.

## <a name="conditional-access"></a>Acesso condicional

O Acesso Condicional é um recurso Azure Active Directory (Azure AD) que ajuda você a garantir que os dispositivos que acessam seus recursos Office 365 sejam gerenciados corretamente e sejam seguros.  Se você aplicar políticas de Acesso Condicional ao serviço Teams, dispositivos Android (incluindo telefones Teams, exibições do Teams e Salas do Microsoft Teams no Android) que acessam o Teams precisam ser inscritos no Intune e suas configurações precisam estar em conformidade com suas políticas.  Se o dispositivo não estiver inscrito no Intune ou se estiver inscrito, mas suas configurações não estão em conformidade com suas políticas, o Acesso Condicional impedirá que um usuário entre ou use o aplicativo Teams no dispositivo.

Normalmente, as políticas de conformidade definidas no Intune são atribuídas a grupos de usuários.  Isso significa que, se você atribuir uma política de conformidade do Android ao user@contoso.com, essa política se aplicará igualmente ao seu smartphone Android e a qualquer dispositivo Teams android no user@contoso.com conectado.

Se você usar o Acesso Condicional, que exige que o registro do Intune seja imposto, em sua organização, há algumas coisas que você precisa configurar para permitir um registro bem-sucedido do Intune:

- **Licença do Intune** O usuário que entra no dispositivo Teams deve ser licenciado para o Intune.  Desde que o dispositivo Teams seja conectado a uma conta de usuário que tenha uma licença válida do Intune, o dispositivo será automaticamente inscrito no Microsoft Intune como parte do processo de entrada.
- **Configurar o Intune** Você deve ter um locatário do Intune configurado corretamente para o registro do Administrador de Dispositivos Android.

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>Configurar o Intune para registrar Teams dispositivos baseados no Android

Teams Os dispositivos baseados em Android são gerenciados pelo Intune por meio do gerenciamento do Administrador de Dispositivos Android (DA). Antes que os dispositivos possam ser inscritos no Intune, há algumas etapas básicas a serem tomadas.  Se você já está gerenciando dispositivos com o Intune hoje, provavelmente já fez todas essas coisas.  Caso não seja, veja o que fazer:

> [!NOTE]
> - Se os administradores de locatários quiserem que os telefones de área comum sejam inscritos no Intune, eles precisarão adicionar uma licença do Intune à conta e seguir as etapas para o registro do Intune.
> - Se a conta de usuário usada para entrar em um dispositivo Teams não estiver licenciada para o Intune, as políticas de conformidade e as restrições de registro do Intune precisarão ser desabilitadas para a conta.



1. Definir a Autoridade do MDM do Intune (gerenciamento de dispositivo móvel).  

   Se você nunca usou o Intune antes, precisa definir a autoridade MDM antes de registrar dispositivos. Para obter mais informações, consulte [Definir a autoridade de gerenciamento de dispositivo móvel](/intune/fundamentals/mdm-authority-set).  Esta é uma etapa única que precisa ser feita ao criar um novo locatário do Intune.
1. Habilitar o registro do administrador de dispositivos Android.
  
   Os dispositivos Teams baseados no Android são gerenciados como dispositivos administradores de dispositivos com o Intune.  O registro do administrador de dispositivos está desabilitado por padrão para locatários recém-criados. Consulte [Registro de administrador de dispositivo Android](/intune/enrollment/android-enroll-device-administrator).
1. Atribuir licenças aos usuários. 
 
   Os usuários Teams dispositivos que se registram no Intune devem ter uma licença válida do Intune. Para obter mais informações, consulte Atribuir licenças aos usuários para [que eles possam registrar dispositivos no Intune](/intune/fundamentals/licenses-assign).
1. Atribuir políticas de conformidade do Administrador de Dispositivos.  

   1. Crie uma política de conformidade do Administrador de Dispositivos Android.

   1. Atribua-o ao grupo Azure Active Directory que contém os usuários que entrarão no Teams dispositivos. Consulte [Usar políticas de conformidade para definir regras para dispositivos que você gerencia com o Intune](/mem/intune/protect/device-compliance-get-started).

## <a name="see-also"></a>Confira também

[Telefones para o Teams](phones-for-teams.md)

[Telefones IP certificados para Microsoft Teams](teams-ip-phones.md)

[Teams exibe](teams-displays.md)

[Gerenciar seus dispositivos no Teams](device-management.md)

[Teams Marketplace](https://office.com/teamsdevices)
