---
title: Implantar as equipes de telefones e equipes do teams usando o Intune
ms.author: v-lanac
author: lanachin
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
description: Este artigo fornece uma visão geral e os recursos suportados pelo Microsoft Teams é exibido.
ms.openlocfilehash: acebf619d76cd6df2f0da305deedec9dd3b79aa0
ms.sourcegitcommit: e07b2d7470b93e52b9e85207db0d6fa3a136efd9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2020
ms.locfileid: "48787599"
---
# <a name="deploy-teams-phones-and-teams-displays-using-intune"></a>Implantar as equipes de telefones e equipes do teams usando o Intune

Este artigo oferece uma visão geral de como implantar o Microsoft Teams e o Microsoft Teams usando o Intune.

## <a name="conditional-access"></a>Acesso condicional

O acesso condicional é um recurso do Azure Active Directory (Azure AD) que ajuda você a garantir que os dispositivos que acessam seus recursos do Office 365 sejam gerenciados corretamente e são seguros.  Se você aplicar políticas de acesso condicional ao serviço do Teams, dispositivos Android (incluindo telefones e equipes de equipe) que acessam as equipes do Access devem ser registrados no Intune e suas configurações precisam estar em conformidade com as políticas.  Se o dispositivo não estiver registrado no Intune ou se estiver registrado, mas suas configurações não atenderem às suas políticas, o acesso condicional impedirá um usuário de entrar ou usar o aplicativo Teams no dispositivo.

Geralmente, as políticas de conformidade definidas no Intune são atribuídas a grupos de usuários.  Isso significa que, se você atribuir uma política de conformidade Android ao user@contoso.com, essa política será aplicada igualmente ao smartphone Android e a qualquer dispositivo de equipe baseado em Android que o user@contoso.com entrar.

Se você usar o acesso condicional, o que requer que o registro do Intune seja imposto, em sua organização, há algumas coisas que você precisa configurar para ter uma inscrição bem-sucedida do Intune:

- **Licença do Intune** O usuário que está entrando no dispositivo do teams deve ser licenciado para o Intune.  Desde que o dispositivo do teams esteja conectado a uma conta de usuário que tenha uma licença válida do Intune, o dispositivo será registrado automaticamente no Microsoft Intune como parte do processo de entrada.
- **Configurar o Intune** Você deve ter uma configuração de locatário do Intune configurada corretamente para o registro do administrador do dispositivo Android.

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>Configurar o Intune para registrar dispositivos baseados em Android do teams

Os dispositivos baseados em Android do teams são gerenciados pelo Intune via gerenciamento de administrador de dispositivo Android (DA). Para que os dispositivos possam ser registrados no Intune, há algumas etapas básicas a serem realizadas.  Se você já estiver gerenciando dispositivos com o Intune hoje, provavelmente já fez todas essas coisas.  Caso contrário, veja o que fazer:

1. Defina a autoridade MDM (gerenciamento de dispositivo móvel) do Intune.  Se você nunca usou o Intune antes, é preciso definir a autoridade de MDM antes de poder inscrever dispositivos. Para obter mais informações, consulte [definir a autoridade de gerenciamento de dispositivos móveis](https://docs.microsoft.com/intune/fundamentals/mdm-authority-set).  Esta é uma etapa única que deve ser realizada durante a criação de um novo locatário do Intune.
2. Habilite o registro do administrador do dispositivo Android. O dispositivo de equipes baseado em Android é gerenciado como dispositivos de administrador de dispositivos com o Intune.  O registro do administrador do dispositivo está desativado por padrão para locatários recém-criados.  Para obter mais informações, consulte [registro do administrador do dispositivo Android](https://docs.microsoft.com/intune/enrollment/android-enroll-device-administrator).
3. Atribuir licenças a usuários. Os usuários de dispositivos do teams que estão sendo registrados no Intune devem receber uma licença válida do Intune. Para obter mais informações, consulte [atribuir licenças aos usuários para que eles possam registrar dispositivos no Intune](https://docs.microsoft.com/intune/fundamentals/licenses-assign).
4. Atribuir políticas de conformidade do administrador do dispositivo.  Crie uma política de conformidade do administrador de dispositivo Android e atribua-a ao grupo do Azure Active Directory que contém os usuários que entrarão nos dispositivos do teams. Para obter mais informações, consulte [usar políticas de conformidade para definir regras para os dispositivos que você gerencia com o Intune](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started).

## <a name="see-also"></a>Confira também

[Telefones para o Teams](phones-for-teams.md)

[Telefones IP certificados para o Microsoft Teams](teams-ip-phones.md)

[Teams exibe](teams-displays.md)

[Gerenciar seus dispositivos no Teams](device-management.md)

[Marketplace do teams](https://office.com/teamsdevices)
