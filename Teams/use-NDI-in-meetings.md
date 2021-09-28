---
title: Transmitir conteúdo de reunião
author: CarolynRowe
ms.author: crowe
ms.reviewer: aalinne
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como usar NDI e SDI para transmitir conteúdo de reunião em Microsoft Teams.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 65e47ccfa1963e8e95e13a1c8b94e1e051ff709c
ms.sourcegitcommit: 84706d0b3b93c1bc72baac830fefd3f0a87c5ad1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2021
ms.locfileid: "59941876"
---
# <a name="broadcast-meeting-content"></a>Transmitir conteúdo de reunião 



Teams oferece duas opções para transmitir Teams de reunião: Interface de Dispositivo de Rede (NewTek NDI®) e Interface Digital Serial (SDI):

- A tecnologia newTek NDI® é uma solução moderna para conectar dispositivos de mídia (como uma câmera de estúdio e um mixer). Em vez de usar conexões físicas, a tecnologia ® NDI habilita a conectividade em uma intranet local, inclusive em uma máquina local.

  A tecnologia ® NDI se tornou uma solução padrão do setor para produzir conteúdo ao vivo para fluxos e ganhou uma conscientização significativa e adoção no mundo da transmissão profissional.

- O SDI é usado em produções de transmissão desde 1989 e tem suporte na maioria dos dispositivos de hardware de estúdio herdados. Dispositivos de hardware de Sistemas de Vídeo AJA e Design Blackmagic fornecem conectividade para dispositivos de transmissão herdados que usam SDI.

> [!NOTE]
> O recurso Saída de Hardware de Vídeo que oferece suporte ao SDI está atualmente na versão De visualização.

A ® NDI e a tecnologia SDI são suportadas em todas as localidades.

O acesso ao uso de NDI e SDI é determinado pela política de reunião do usuário que está tentando ativar o recurso. Para a solução mais segura, não a turn on the local streaming parameter as a global setting.


## <a name="enable-broadcast-features"></a>Habilitar recursos de transmissão

Para habilitar recursos de transmissão NDI® e SDI para um usuário:

1. O administrador do locatário deve permitir que o usuário final tenha o streaming local ativado para sua política de reunião. 

2. O usuário final deve ativar o streaming local para seu cliente específico.


Para habilitar o usuário final, você pode usar o centro de administração Teams ou Teams PowerShell da seguinte forma.

No centro de Teams de administração, acesse Políticas de reunião > **áudio & vídeo** e selecione Permitir Streaming de **NDI**.

Para usar o PowerShell, use o cmdlet Set-CsTeamsMeetingPolicy da seguinte forma:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

Depois que essa alteração for preenchida, o usuário final deverá ativar o streaming local para seu cliente específico Configurações  >  **Permissões**. Para obter mais informações, [consulte Transmissão de áudio e vídeo de Teams](https://support.microsoft.com/office/broadcasting-audio-and-video-from-teams-with-ndi-technology-e91a0adb-96b9-4dca-a2cd-07181276afa3).





