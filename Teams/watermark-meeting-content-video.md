---
title: Exigir uma marca d'água para reuniões confidenciais do Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
description: Saiba como habilitar ou exigir marcas d'água no vídeo do participante e conteúdo compartilhado em reuniões confidenciais do Teams.
ms.openlocfilehash: 6037bc6e9dbe79d9ecee10666f4c34e4e778216a
ms.sourcegitcommit: 5e0900ed7a21ed4e854cc00dbfb4ae4ff2372262
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2023
ms.locfileid: "69950498"
---
# <a name="require-a-watermark-for-sensitive-teams-meetings"></a>Exigir uma marca d'água para reuniões confidenciais do Teams

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

Você pode permitir que uma marca d'água seja exibida em reuniões do Teams tanto para conteúdo compartilhado na tela quanto para vídeo do participante. A marca d'água exibe o endereço de email do participante da reunião. Os participantes da reunião não podem desativar a marca d'água.

Há suporte para marcas d'água na área de trabalho e no celular do Teams. Pessoas ingressar em reuniões de plataformas sem suporte terá uma experiência somente áudio.

Os participantes que ingressarem no [Cloud Video Interop (CVI)](cloud-video-interop.md)poderão ver conteúdo sem marcas d'água.

Os participantes a seguir têm uma experiência somente áudio quando uma marca d'água está em uso:

- Participantes usando o cliente Web do Teams
- participantes do Virtual Desktop Infrastructure (VDI)
- Participantes anônimos
- Participantes de estouro
- Salas do Microsoft Teams no Windows e Salas do Microsoft Teams no Surface Hub
- Salas do Microsoft Teams no Android
- Clientes mais antigos do Teams
- [Ingresso direto em dispositivos Salas do Microsoft Teams](/microsoftteams/rooms/third-party-join)

> [!Note]
> As configurações de reunião em rótulos de confidencialidade, modelos de reunião personalizados e marcas d'água exigem Teams Premium.

As marcas d'água de reunião estão habilitadas no centro de administração do Teams. Em seguida, eles podem ser adicionados pelo organizador da reunião ou imposto por um modelo ou rótulo de confidencialidade.

A tabela a seguir mostra onde as marcas d'água estão configuradas:

|Configuração|Administração política|Rótulo de confidencialidade|Modelo|Organizador da reunião|
|:------|:----------:|:---------------:|:------:|:---------------:|
|Aplicar uma marca d'água ao conteúdo compartilhado|Sim|Sim|Sim|Sim|
|Aplicar uma marca d'água ao feed de vídeo de todos|Sim|Sim|Sim|Sim|

Quando uma marca d'água está sendo usada em uma reunião, os seguintes recursos são desativados:

- Gravação de reunião, incluindo gravação automática

- Galeria grande

- Modo conferência

- PowerPoint Live

- Quadro de comunicações

- Conteúdo da câmera

## <a name="watermarks-for-sensitive-and-highly-sensitive-meetings"></a>Marcas d'água para reuniões confidenciais e altamente sensíveis

As marcas d'água podem ser úteis para proteger informações confidenciais compartilhadas em reuniões. Isso é mais útil ao compartilhar informações com pessoas que normalmente não têm acesso às informações. Por exemplo, um membro da organização financeira pode usar marcas d'água ao compartilhar estimativas trimestrais com gerentes de diferentes divisões.

Como as marcas d'água são projetadas para reduzir as chances de que as informações confidenciais sejam exfiltradas, usá-las em reuniões em que todos os participantes têm acesso direto ao conteúdo que está sendo compartilhado, talvez não adicione à segurança.

Para obter informações sobre como usar marcas d'água com outros recursos de reunião para ajudar a proteger informações confidenciais em reuniões, consulte [Configurar reuniões do Teams com proteção para dados altamente confidenciais](/microsoftteams/configure-meetings-highly-sensitive-protection).

## <a name="enable-watermarks"></a>Habilitar marcas d'água

Para que as marcas d'água estejam disponíveis em modelos e rótulos de confidencialidade e para o organizador da reunião, elas devem estar habilitadas no centro de administração do Teams.

Para habilitar a marca d'água para reuniões

1. No centro de administração do Teams, expanda **Reuniões** e selecione **Políticas de reunião**.

1. Selecione a política que você deseja atualizar.

1. Para habilitar a marca d'água no vídeo do participante, defina **vídeos da marca d'água** como **Ativado**.

1. Para habilitar a marca d'água no conteúdo compartilhado na tela em uma reunião, defina **o conteúdo compartilhado da Marca d'água** como **Ativado**.

    ![Captura de tela da política de administrador do Teams para marcas d'água](media/watermark-admin-policy.png)

1. Para ver como a marca d'água será exibida em dispositivos móveis e de área de trabalho, **selecione Visualizar**.

1. Selecione **Salvar**.

Você também pode habilitar ou desabilitar marcas d'água usando o PowerShell. Use o cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) com os `-AllowWatermarkForCameraVideo` parâmetros e `-AllowWatermarkForScreenSharing` .

Por exemplo:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowWatermarkForCameraVideo $True 

Set-CsTeamsMeetingPolicy -Identity Global -AllowWatermarkForScreenSharing $True 
```

## <a name="related-topics"></a>Tópicos relacionados

[Configurar reuniões do Teams com três camadas de proteção](configure-meetings-three-tiers-protection.md)

[Use modelos de reunião do Teams, rótulos de confidencialidade e políticas de administrador juntos para reuniões confidenciais](meeting-templates-sensitivity-labels-policies.md)
