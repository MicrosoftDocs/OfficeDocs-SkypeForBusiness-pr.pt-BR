---
title: Mascarar números de telefone em reuniões do Microsoft Teams
author: heidip
ms.author: MicrosoftHeidi
manager: serdars
ms.reviewer: moakram
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba como mascarar números de telefone em reuniões do Microsoft Teams
ms.openlocfilehash: e1ef25f12bdf92bc58739284af2a624257169403
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270816"
---
# <a name="mask-phone-numbers-in-microsoft-teams-meetings"></a>Mascarar números de telefone em reuniões do Microsoft Teams

Para maior privacidade, os números de telefone dos participantes que discam para uma reunião do Teams usando audioconferência são totalmente exibidos para os participantes internos. Os números são mascarados dos participantes de fora da sua organização. Essa configuração é o padrão para todas as organizações. O número mascarado é exibido conforme mostrado na imagem a seguir:

![um exemplo de um número de telefone mascarado.](media/hiddenPhoneNum.png)

Para casos de uso específicos do setor, os administradores têm a capacidade de escolher como os números de telefone dos participantes da audioconferência aparecem em reuniões organizadas em seu locatário. Os administradores podem escolher entre três opções:

- Os números de telefone são mascarados somente de participantes externos. Os participantes que pertencem ao locatário do organizador da reunião ainda veem o número de telefone completo.
- Os números de telefone são mascarados de todos na reunião, exceto o organizador.
- Os números de telefone não são máscaras, o que os torna visíveis para todos na reunião.

Essa configuração é aplicada a todas as superfícies na reunião em que os números de telefone são expostos.

## <a name="use-microsoft-powershell-to-set-phone-number-masking"></a>Usar o Microsoft PowerShell para definir o mascaramento de número de telefone

Para alterar a configuração de mascaramento PSTN (Rede Telefônica Pública Comutada), **`MaskPstnNumbersType`** defina o parâmetro do cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) como uma das opções disponíveis.

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
