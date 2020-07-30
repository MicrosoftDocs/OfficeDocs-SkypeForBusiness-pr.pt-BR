---
title: Usar o NDI no Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como usar o NDI no Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: d971a7c9e44e2fbf7c3d2500f237e3755c5f89d0
ms.sourcegitcommit: 824c79bd050b0abb576004f6209bb081d5090a8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522886"
---
# <a name="use-ndi-in-microsoft-teams"></a>Usar o NDI no Microsoft Teams

[!INCLUDE [template](includes/preview-feature.md)]

O NDI (Network Device Interface) é uma solução moderna para conexão de dispositivos de mídia (como uma câmera e mixer de estúdio). Em vez de usar conexões físicas, o NDI permite a conectividade em uma intranet local, incluindo em um computador local.

NewTek NDI® tornou-se uma solução padrão do setor para a produção de conteúdo ao vivo para fluxos e ganhou conhecimento e adoção significativos no mundo da transmissão profissional.

O Skype adicionou anteriormente a funcionalidade NDI ao Skype no fim de 2018. O Microsoft Teams aproveita essa funcionalidade para melhorar a experiência da reunião.

O NDI limita-se a uma rede local e só deve ser considerado parte do fluxo de trabalho de produção, não uma solução de transmissão.

## <a name="turn-on-ndi"></a>Ativar o NDI

O NDI exige que duas etapas sejam ativadas para um usuário.

1. O administrador de locatários deve habilitar o sinalizador de recursos enableStreamingCallsOverNdi.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. Depois que essa alteração tiver sido completada, o usuário final precisará ativar o NDI para o cliente específico das permissões de **configurações**  >  **Permissions**.

Quando um usuário ingressa em uma reunião, ele vê uma mensagem que informa que a reunião está sendo transmitida. Se os usuários não quiserem ser incluídos na transmissão, eles precisarão ser descartados da reunião.

A imagem a seguir mostra a mensagem de faixa que o usuário vê em uma reunião do teams.

![Uma imagem da faixa NDI exibida em uma reunião do teams.](media/NDI-disclosure.png)

A faixa tem um link para a [política de privacidade da Microsoft](https://support.skype.com/faq/FA34853/what-is-skype-for-content-creators?q=ndi).

## <a name="supported-locales-and-user-types"></a>Locais e tipos de usuários com suporte

NDI é compatível com todas as localidades. Os seguintes usuários têm suporte em uma reunião do NDI:

- In-locatário – suporte completo, entregue com base em Ring/tenantid/userId (controlado por política de reuniões + sinalizador de recursos)
- Federado – não (mesmo quando eles têm NDI)<sup>1</sup>
- Freemium-não (valor padrão)
- Anônimo – não (valor padrão)
- Convidado – não (valor padrão)

<sup>1</sup> dispositivos têm uma configuração NDI ativada por padrão. Se um participante da reunião estiver usando um dispositivo com o NDI desligado, ele precisará ativar o NDI.
