---
title: Transmitir conteúdo da reunião
author: CarolynRowe
ms.author: crowe
ms.reviewer: aalinne
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como usar NDI e SDI para transmitir conteúdo de reunião no Microsoft Teams.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5d048063f7b8efa6b853aa7273e0bcefaeb41b1f
ms.sourcegitcommit: 9175c6d542dd825ce965d0cb7c67264f22315202
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2022
ms.locfileid: "66687817"
---
# <a name="broadcast-meeting-content"></a>Transmitir conteúdo da reunião 



O Teams fornece duas opções para transmitir conteúdo de reunião do Teams: Interface de Dispositivo de Rede (NewTek NDI®) e SDI (Interface Digital Serial):

- A tecnologia NewTek NDI® é uma solução moderna para conectar dispositivos de mídia (como uma câmera de estúdio e um mixer). Em vez de usar conexões físicas, a tecnologia NDI® permite a conectividade em uma intranet local, incluindo em um computador local.

  A tecnologia NDI® tornou-se uma solução padrão do setor para produzir conteúdo ao vivo para fluxos e ganhou reconhecimento e adoção significativos no mundo da difusão profissional.

- O SDI foi usado em produção de difusão desde 1989 e tem suporte na maioria dos dispositivos de hardware de estúdio herdados. Os dispositivos de hardware dos Sistemas de Vídeo do AJA e do Blackmagic Design fornecem conectividade a dispositivos de difusão herdados que usam SDI.

> [!NOTE]
> O recurso hardware out de vídeo que dá suporte a SDI está atualmente em versão prévia.

Há suporte para a tecnologia NDI® e SDI em todas as localidades.

O acesso ao uso de NDI e SDI é determinado pela política de reunião para o usuário que está tentando ativar o recurso. Para a solução mais segura, não ative o parâmetro de streaming local como uma configuração global.


## <a name="enable-broadcast-features"></a>Habilitar recursos de difusão

Para habilitar recursos de difusão NDI® e SDI para um usuário:

1. O administrador de locatários deve permitir que o usuário final tenha o streaming local ativado para sua política de reunião. 

2. O usuário final deve ativar o streaming local para seu cliente específico.


Para habilitar o usuário final, você pode usar o Teams Administração central ou o PowerShell do Teams da seguinte maneira.

No centro de administração do Teams, acesse Políticas de reunião > **áudio & vídeo** e selecione **Difusão Local**.

Para usar o PowerShell, use o Set-CsTeamsMeetingPolicy cmdlet da seguinte maneira:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

Depois que essa alteração for preenchida, o usuário final deverá ativar o streaming local para seu cliente específico nas **Permissões de** > **Configurações**. Para obter mais informações, consulte [Transmissão de áudio e vídeo do Teams](https://support.microsoft.com/office/broadcasting-audio-and-video-from-teams-with-ndi-technology-e91a0adb-96b9-4dca-a2cd-07181276afa3).





