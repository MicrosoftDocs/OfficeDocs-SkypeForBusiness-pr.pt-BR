---
title: Implantar telefones do Teams, exibições do Teams, painéis do Teams e Salas do Microsoft Teams no Android usando Intune
author: CarolynRowe
ms.author: crowe
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
description: Este artigo fornece uma visão geral dos recursos compatíveis com dispositivos Android do Microsoft Teams.
ms.openlocfilehash: 5522c29c74eb9679d26d13627dcb69b315dc33fd
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66790306"
---
# <a name="deploy-teams-phones-teams-displays-teams-panels-and-microsoft-teams-rooms-on-android-using-intune"></a>Implantar telefones do Teams, exibições do Teams, painéis do Teams e Salas do Microsoft Teams no Android usando Intune

Este artigo fornece uma visão geral de como implantar telefones do Teams, exibições do Teams, painéis do Teams e Salas do Microsoft Teams no Android usando Intune.

## <a name="conditional-access"></a>Acesso condicional

O Acesso Condicional é um recurso do Azure Active Directory (Azure AD) que ajuda você a garantir que os dispositivos que acessam seus recursos Office 365 sejam gerenciados corretamente e sejam seguros.  Se você aplicar políticas de Acesso Condicional ao serviço do Teams, dispositivos Android (incluindo telefones do Teams, exibições do Teams, painéis do Teams e Salas do Microsoft Teams no Android) que acessam o Teams precisam ser registrados no Intune e suas configurações precisam estar em conformidade com suas políticas.  Se o dispositivo não estiver registrado no Intune ou se ele estiver registrado, mas suas configurações não atenderem às suas políticas, o Acesso Condicional impedirá que um usuário entre ou use o aplicativo Teams no dispositivo.

Normalmente, as políticas de conformidade definidas Intune são atribuídas a grupos de usuários.  Isso significa que, se você atribuir uma política de conformidade do Android ao user@contoso.com, essa política será aplicada igualmente ao seu smartphone Android e a qualquer dispositivo Teams baseado em Android que user@contoso.com entrar.

Se você usar o Acesso Condicional, o que exige que o registro Intune seja imposto, em sua organização, há algumas coisas que você precisa configurar para permitir um registro Intune bem-sucedido:

- **Intune licença O** usuário que entra no dispositivo teams deve ser licenciado para Intune.  Desde que o dispositivo teams esteja conectado a uma conta de usuário que tenha uma licença de Intune válida, o dispositivo será registrado automaticamente no Microsoft Intune como parte do processo de entrada.
- **Configure Intune** você deve ter um locatário Intune configurado corretamente para o registro do Administrador de Dispositivos Android.

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>Configurar Intune para registrar dispositivos baseados em Android do Teams

Os dispositivos baseados em Android do Teams são gerenciados Intune gerenciamento do ADMINISTRADOR de Dispositivos Android (DA). Antes que os dispositivos possam ser registrados no Intune, há algumas etapas básicas a serem executadas.  Se você já está gerenciando dispositivos com Intune hoje, provavelmente já fez todas essas coisas.  Caso contrário, veja o que fazer:

> [!NOTE]
> - Se os administradores de locatários quiserem que os telefones de área comum sejam registrados no Intune, eles precisarão adicionar uma licença do Intune à conta e seguir as etapas para Intune registro.
> - Se a conta de usuário usada para entrar em um dispositivo teams não estiver licenciada para o Intune, as políticas de conformidade e as restrições de registro do Intune precisarão ser desabilitadas para a conta.



1. Defina Intune autoridade de MDM (gerenciamento de dispositivo móvel).  

   Se você nunca usou o Intune, precisará definir a autoridade de MDM antes de registrar dispositivos. Para obter mais informações, consulte [Definir a autoridade de gerenciamento de dispositivo móvel](/intune/fundamentals/mdm-authority-set).  Essa é uma etapa única que deve ser feita na criação de um novo locatário Intune locatário.
1. Habilitar o registro de administrador de dispositivo Android.
  
   Os dispositivos Teams baseados em Android são gerenciados como dispositivos de administrador de dispositivos com Intune.  O registro do administrador do dispositivo está desativado por padrão para locatários recém-criados. Consulte o [registro de administrador de dispositivo Android](/intune/enrollment/android-enroll-device-administrator).
1. Atribuir licenças aos usuários. 
 
   Os usuários de dispositivos do Teams que se registram Intune devem receber uma licença Intune válida. Para obter mais informações, [consulte Atribuir licenças aos usuários para que eles possam registrar dispositivos Intune](/intune/fundamentals/licenses-assign).
1. Atribuir políticas de conformidade do Administrador de Dispositivos.  

   1. Crie uma política de conformidade do Administrador de Dispositivos Android.

   1. Atribua-o ao grupo do Azure Active Directory que contém os usuários que entrarão nos dispositivos do Teams. Consulte [Usar políticas de conformidade para definir regras para dispositivos gerenciados com Intune](/mem/intune/protect/device-compliance-get-started).

## <a name="see-also"></a>Confira também

[Telefones para o Teams](phones-for-teams.md)

[Telefones IP certificados para o Microsoft Teams](teams-ip-phones.md)

[Exibições do Teams](teams-displays.md)

[Gerenciar seus dispositivos no Teams](device-management.md)

[Teams Marketplace](https://office.com/teamsdevices)
