---
title: Mascarar números de telefone em Microsoft Teams reuniões
author: cichur
ms.author: v-mahoffman
manager: serdars
ms.reviewer: moakram
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba como mascarar números de telefone em reuniões Microsoft Teams reuniões
ms.openlocfilehash: d34d2f38a3a1fe2219816184a5f127312cd0475e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60758263"
---
# <a name="mask-phone-numbers-in-microsoft-teams-meetings"></a>Mascarar números de telefone em Microsoft Teams reuniões

Para privacidade adicional, os números de telefone dos participantes que discam em uma reunião Teams usando audioconferência são totalmente exibidos para os participantes internos. Os números são mascarados dos participantes de fora da sua organização. Essa configuração é o padrão para todas as organizações. O número mascarado é exibido conforme mostrado na imagem a seguir:

![um exemplo de um número de telefone mascarado.](media/hiddenPhoneNum.png)

Para casos específicos de uso do setor, os administradores têm a capacidade de escolher como os números de telefone dos participantes da audioconferência aparecem em reuniões organizadas em seu locatário. Os administradores podem escolher entre três opções:

- Telefone números são mascarados somente de participantes externos. Os participantes que pertencem ao locatário do organizador da reunião ainda veem o número de telefone completo.
- Telefone números são mascarados de todos na reunião, exceto o organizador.
- Telefone números são não máscaras, o que os torna visíveis para todos na reunião.

Essa configuração é aplicada a todas as superfícies na reunião em que os números de telefone são expostos.

## <a name="use-microsoft-powershell-to-set-phone-number-masking"></a>Usar o Microsoft PowerShell para definir o mascaramento de número de telefone

Para alterar a configuração de mascaramento rede telefônica pública comutado (PSTN), defina o parâmetro do **`MaskPstnNumbersType`** cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) como uma das opções disponíveis.

Para mascarar números de telefone somente de participantes externos, execute o seguinte comando:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForExternalUsers"
```

Para mascarar números de telefone de todos os participantes da reunião (exceto o organizador), execute o seguinte comando:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForAllUsers"
```

Para desabilitar o mascaramento de número de telefone, execute o seguinte comando:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "NoMasking"
```