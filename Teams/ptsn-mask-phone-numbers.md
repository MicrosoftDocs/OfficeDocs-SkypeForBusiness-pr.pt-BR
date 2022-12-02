---
title: Mascarar números de telefone em reuniões do Microsoft Teams
author: heidip
ms.author: heidip
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
ms.openlocfilehash: 7072d1853a49d9e7ebc59e360c971874ed6549a3
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2022
ms.locfileid: "69242265"
---
# <a name="mask-phone-numbers-in-microsoft-teams-meetings"></a>Mascarar números de telefone em reuniões do Microsoft Teams

Para adicionar privacidade, os números de telefone dos participantes que discam para uma reunião do Teams usando a conferência de áudio são totalmente exibidos para os participantes internos. Os números são mascarados dos participantes fora de sua organização. Essa configuração é o padrão para todas as organizações. O número mascarado é exibido conforme mostrado na imagem a seguir:

![um exemplo de um número de telefone mascarado.](media/hiddenPhoneNum.png)

Para casos específicos de uso do setor, os administradores têm a capacidade de escolher como os números de telefone dos participantes de conferência de áudio aparecem em reuniões organizadas em seu locatário. Os administradores podem escolher entre três opções:

- Os números de telefone são mascarados apenas de participantes externos. Os participantes que pertencem ao locatário do organizador da reunião ainda veem o número de telefone completo.
- Os números de telefone são mascarados de todos na reunião, exceto do organizador.
- Os números de telefone são desmascarados, o que os torna visíveis para todos na reunião.

Essa configuração é aplicada a todas as superfícies da reunião em que os números de telefone são expostos.

## <a name="use-teams-admin-center-to-set-phone-number-masking"></a>Usar o centro de administração do Teams para definir mascaramento de número de telefone

Para alterar a configuração de mascaramento PSTN (Rede Telefônica Comutada Pública) no centro de administração do Teams, faça logon no centro de administração do Teams como administrador, selecione **Reuniões Pontes** >  de **Conferência** no painel de navegação à esquerda e selecione **Configurações de Ponte**. **Exibir IDs de chamador mascaradas** é uma lista suspensa na parte inferior do painel Configurações da Ponte e permitirá que você escolha o seguinte:

- Para participantes fora de sua organização
- Para todos os participantes da reunião
- Desabilitado

## <a name="use-microsoft-powershell-to-set-phone-number-masking"></a>Usar Microsoft PowerShell para definir mascaramento de número de telefone

Para alterar a configuração de mascaramento PSTN no PowerShell, defina o **`MaskPstnNumbersType`** parâmetro do cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings) como uma das opções disponíveis.

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
