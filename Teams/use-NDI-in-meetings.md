---
title: Usar a NDI no Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como usar a NDI no Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e26c6a7ad92353e083c67d0dad777e980a83fdfe
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598460"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a>Usar a tecnologia ® NDI no Microsoft Teams

 A tecnologia NewTek NDI® (Interface de Dispositivo de Rede) é uma solução moderna para conectar dispositivos de mídia (como uma câmera de estúdio e um mixer). Em vez de usar conexões físicas, a tecnologia ® NDI habilita a conectividade em uma intranet local, inclusive em uma máquina local.

A tecnologia ® NDI se tornou uma solução padrão do setor para produzir conteúdo ao vivo para fluxos e ganhou uma conscientização significativa e adoção no mundo da transmissão profissional.

O Skype adicionou anteriormente a funcionalidade ® NDI ao Skype no final de 2018. O Microsoft Teams usa essa funcionalidade para melhorar a experiência de reunião.

A ® NDI está limitada a uma rede local e deve ser considerada apenas uma parte do fluxo de trabalho de produção, não uma solução de transmissão.

## <a name="turn-on-ndi-technology"></a>Ativar a tecnologia NDI®

A tecnologia ® NDI requer duas etapas para ser 1 para um usuário.

1. O administrador do locatário deve habilitar a propriedade 'AllowNDIStreaming' em CsTeamsMeetingPolicy.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. Depois que essa alteração for preenchida, o usuário final deverá ativar a tecnologia NDI® para seu cliente específico a partir **de Permissões**  >  **de Configurações.**

Quando um usuário ingressar em uma reunião, ele verá uma mensagem que notifica que a reunião está sendo transmitida. Se os usuários não quiserem ser incluídos na transmissão, eles precisarão sair da reunião.

A imagem a seguir mostra a mensagem em faixa que um usuário vê em uma reunião do Teams.

![ele NDI® faixa de tecnologia que é exibida em uma reunião do Teams.](media/NDI-disclosure.png)

O banner tem um link para a [política de privacidade da Microsoft.](https://aka.ms/teamsprivacy)

> [!NOTE]
> NDI® é ativado somente por sessão. No próximo logon, o usuário deve ativá-lo antes de usar o NDI®.

## <a name="supported-locales-and-user-types"></a>Localidades e tipos de usuário com suporte

A ® NDI é suportada em todas as localidades. Os usuários a seguir estão incluídos em um fluxo de tecnologia NDI®, mas nem todos os usuários podem acessar o fluxo de tecnologia NDI®:

- In-tenant – suporte completo, fornecido com base em ring/tenantId/userId (controlado pela Política de Reuniões)
- Federado – sem acesso a fluxo (mesmo quando eles têm a tecnologia ® NDI)<sup>1</sup>
- Premium - sem acesso a fluxo
- Anônimo – sem acesso a fluxo
- Convidado – sem acesso a fluxo  

<sup>1</sup> Os dispositivos têm uma configuração de tecnologia ® NDI que está em uso por padrão. Se um participante da reunião estiver usando um dispositivo com a tecnologia ® NDI desligada, ele precisará ativar a tecnologia ® NDI.
