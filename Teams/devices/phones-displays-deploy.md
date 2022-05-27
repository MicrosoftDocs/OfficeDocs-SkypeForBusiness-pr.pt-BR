---
title: Implantar Teams, Teams telas, painéis Teams e Salas do Microsoft Teams em Android usando Intune
ms.author: serdars
author: SerdarSoysal
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
description: Este artigo fornece uma visão geral dos recursos compatíveis com Microsoft Teams Android dispositivos.
ms.openlocfilehash: 17f5e537b44d3aacd967ff5e8ffaa84df9da3f9b
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674853"
---
# <a name="deploy-teams-phones-teams-displays-teams-panels-and-microsoft-teams-rooms-on-android-using-intune"></a>Implantar Teams, Teams telas, painéis Teams e Salas do Microsoft Teams em Android usando Intune

Este artigo fornece uma visão geral de como implantar telefones Teams, telas do Teams, painéis Teams e Salas do Microsoft Teams no Android usando Intune.

## <a name="conditional-access"></a>Acesso condicional

O Acesso Condicional é um recurso Azure Active Directory (Azure AD) que ajuda você a garantir que os dispositivos que acessam seus recursos Office 365 sejam gerenciados corretamente e sejam seguros.  Se você aplicar políticas de Acesso Condicional ao serviço Teams, os dispositivos Android (incluindo telefones Teams, telas do Teams, painéis Teams e Salas do Microsoft Teams no Android) em que o Teams de acesso precisarão ser registrados Intune e suas configurações precisam estar em conformidade com suas políticas.  Se o dispositivo não estiver registrado no Intune ou se ele estiver registrado, mas suas configurações não atenderem às suas políticas, o Acesso Condicional impedirá que um usuário entre ou use o aplicativo Teams no dispositivo.

Normalmente, as políticas de conformidade definidas Intune são atribuídas a grupos de usuários.  Isso significa que, se você atribuir uma política de conformidade do Android ao user@contoso.com, essa política será aplicada igualmente ao smartphone Android e a qualquer dispositivo Teams baseado em Android que user@contoso.com se conecte.

Se você usar o Acesso Condicional, o que exige que o registro Intune seja imposto, em sua organização, há algumas coisas que você precisa configurar para permitir um registro Intune bem-sucedido:

- **Intune licença O** usuário que entra no dispositivo Teams deve ser licenciado para Intune.  Desde que o dispositivo Teams esteja conectado a uma conta de usuário que tenha uma licença de Intune válida, o dispositivo será registrado automaticamente no Microsoft Intune como parte do processo de entrada.
- **Configurar Intune** você deve ter um locatário Intune configurado corretamente para Android de Dispositivos.

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>Configurar Intune para registrar Teams Android baseados em Teams Android dispositivos

Teams Android baseados em dispositivos são gerenciados por Intune por meio Android gerenciamento do DA (Administrador de Dispositivos). Antes que os dispositivos possam ser registrados no Intune, há algumas etapas básicas a serem executadas.  Se você já está gerenciando dispositivos com Intune hoje, provavelmente já fez todas essas coisas.  Caso contrário, veja o que fazer:

> [!NOTE]
> - Se os administradores de locatários quiserem que os telefones de área comum sejam registrados no Intune, eles precisarão adicionar uma licença do Intune à conta e seguir as etapas para Intune registro.
> - Se a conta de usuário usada para entrar em um dispositivo Teams não estiver licenciada para o Intune, as políticas de conformidade do Intune e as restrições de registro precisarão ser desabilitadas para a conta.



1. Defina Intune autoridade de MDM (gerenciamento de dispositivo móvel).  

   Se você nunca usou o Intune, precisará definir a autoridade de MDM antes de registrar dispositivos. Para obter mais informações, consulte [Definir a autoridade de gerenciamento de dispositivo móvel](/intune/fundamentals/mdm-authority-set).  Essa é uma etapa única que deve ser feita na criação de um novo locatário Intune locatário.
1. Habilite Android de administrador do dispositivo.
  
   Android com base em Teams dispositivos são gerenciados como dispositivos de administrador de dispositivos com Intune.  O registro do administrador do dispositivo está desativado por padrão para locatários recém-criados. Consulte [Android de administrador do dispositivo](/intune/enrollment/android-enroll-device-administrator).
1. Atribuir licenças aos usuários. 
 
   Os usuários Teams dispositivos registrados no Intune devem receber uma licença Intune válida. Para obter mais informações, [consulte Atribuir licenças aos usuários para que eles possam registrar dispositivos Intune](/intune/fundamentals/licenses-assign).
1. Atribuir políticas de conformidade do Administrador de Dispositivos.  

   1. Crie uma política Android de conformidade do Administrador de Dispositivos.

   1. Atribua-o ao Azure Active Directory que contém os usuários que entrarão nos Teams dispositivos. Consulte [Usar políticas de conformidade para definir regras para dispositivos gerenciados com Intune](/mem/intune/protect/device-compliance-get-started).

## <a name="see-also"></a>Confira também

[Telefones para o Teams](phones-for-teams.md)

[Telefones IP certificados para Microsoft Teams](teams-ip-phones.md)

[Teams exibições](teams-displays.md)

[Gerenciar seus dispositivos no Teams](device-management.md)

[Teams Marketplace](https://office.com/teamsdevices)
