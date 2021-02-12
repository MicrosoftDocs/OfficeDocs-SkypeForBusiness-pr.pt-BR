---
title: Implantar telefones do Teams e exibições do Teams usando o Intune
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
description: Este artigo fornece uma visão geral dos recursos com suporte no Microsoft Teams.
ms.openlocfilehash: 4d955db2f260af0eff3d0c1f059461703cf23d79
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825411"
---
# <a name="deploy-teams-phones-and-teams-displays-using-intune"></a>Implantar telefones do Teams e exibições do Teams usando o Intune

Este artigo apresenta uma visão geral de como implantar telefones do Teams e as exibições do Teams usando o Intune.

## <a name="conditional-access"></a>Acesso condicional

O Acesso Condicional é um recurso do Azure Active Directory (Azure AD) que ajuda você a garantir que os dispositivos que acessam seus recursos do Office 365 sejam gerenciados corretamente e sejam seguros.  Se você aplicar políticas de Acesso Condicional ao serviço do Teams, dispositivos Android (incluindo telefones do Teams e exibições do Teams) que acessam o Teams precisam ser inscritos no Intune e suas configurações precisam estar em conformidade com suas políticas.  Se o dispositivo não estiver inscrito no Intune ou se estiver inscrito, mas suas configurações não atenderem às suas políticas, o Acesso Condicional impedirá que um usuário entre ou use o aplicativo teams no dispositivo.

Normalmente, as políticas de conformidade definidas no Intune são atribuídas a grupos de usuários.  Isso significa que, se você atribuir uma política de conformidade do Android ao user@contoso.com, essa política será aplicada igualmente ao smartphone Android e a qualquer dispositivo do Teams baseado no Android que user@contoso.com entrar.

Se você usa o Acesso Condicional, que exige que o registro do Intune seja imposto, em sua organização, há algumas coisas que você precisa configurar para permitir um registro bem-sucedido do Intune:

- **Licença do Intune** O usuário que entrar no dispositivo teams deve ser licenciado para o Intune.  Desde que o dispositivo do Teams seja conectado a uma conta de usuário que tenha uma licença válida do Intune, o dispositivo será automaticamente inscrito no Microsoft Intune como parte do processo de entrada.
- **Configurar o Intune** Você deve ter um locatário do Intune configurado corretamente configurado para o registro do Administrador de Dispositivos Android.

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>Configurar o Intune para registrar dispositivos baseados no Teams para Android

Os dispositivos baseados em Android do Teams são gerenciados pelo Intune por meio do gerenciamento de Administradores de Dispositivos Android (DA). Antes que os dispositivos possam ser inscritos no Intune, há algumas etapas básicas a serem executar.  Se você já estiver gerenciando dispositivos com o Intune hoje, provavelmente já fez todas essas coisas.  Caso não, veja o que fazer:

1. Defina a Autoridade de MDM do Intune (gerenciamento de dispositivo móvel).  Se você nunca usou o Intune antes, é necessário definir a autoridade MDM antes de registrar os dispositivos. Para obter mais informações, consulte [Definir a autoridade de gerenciamento de dispositivo móvel.](https://docs.microsoft.com/intune/fundamentals/mdm-authority-set)  Essa é uma etapa única que precisa ser feita ao criar um novo locatário do Intune.
2. Habilitar o registro de administrador de dispositivos Android. Dispositivos do Teams baseados no Android são gerenciados como dispositivos de administrador de dispositivo com o Intune.  O registro do administrador do dispositivo está desabilitado por padrão para locatários recém-criados.  Para obter mais informações, consulte o [registro do administrador do dispositivo Android.](https://docs.microsoft.com/intune/enrollment/android-enroll-device-administrator)
3. Atribuir licenças aos usuários. Os usuários de dispositivos teams que se inscrevem no Intune devem ter uma licença válida do Intune. Para obter mais informações, consulte [Atribuir licenças aos usuários para que eles possam registrar dispositivos no Intune.](https://docs.microsoft.com/intune/fundamentals/licenses-assign)
4. Atribuir políticas de conformidade de Administrador de Dispositivo.  Crie uma política de conformidade do Administrador de Dispositivos Android e atribua-a ao grupo do Azure Active Directory que contém os usuários que entrarão nos dispositivos do Teams. Para obter mais informações, [consulte Usar políticas de conformidade para definir regras para dispositivos que você gerencia com o Intune.](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started)

## <a name="see-also"></a>Confira também

[Telefones para o Teams](phones-for-teams.md)

[Telefones IP certificados para o Microsoft Teams](teams-ip-phones.md)

[O Teams é exibido](teams-displays.md)

[Gerenciar seus dispositivos no Teams](device-management.md)

[Teams Marketplace](https://office.com/teamsdevices)
