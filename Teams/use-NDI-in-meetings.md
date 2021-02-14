---
title: Usar NDI no Microsoft Teams
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
ms.openlocfilehash: d1ad11000de2ae0dac7563d785dfaea8c34978ed
ms.sourcegitcommit: fd7d5ba09ef30cf4594e352c36f62b950e0e41a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2020
ms.locfileid: "48337010"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a>Usar a tecnologia ® NDI no Microsoft Teams

 A tecnologia NewTek NDI® (Interface de Dispositivo de Rede) é uma solução moderna para conectar dispositivos de mídia (como uma câmera de estúdio e um mixer). Em vez de usar conexões físicas, ® NDI habilita a conectividade em uma intranet local, inclusive em um computador local.

A tecnologia NDI® tornou-se uma solução padrão do setor para a produção de conteúdo ao vivo para fluxos e ganhou reconhecimento e adoção significativas no mundo da transmissão profissional.

O Skype adicionou anteriormente ® NDI ao Skype no final de 2018. O Microsoft Teams usa essa funcionalidade para melhorar a experiência da reunião.

O NDI® a tecnologia é limitada a uma rede local e só deve ser considerada parte do fluxo de trabalho de produção, não uma solução de transmissão.

## <a name="turn-on-ndi-technology"></a>Ativar a tecnologia NDI® NDI

A tecnologia NDI® requer duas etapas para ser responsabilidade do usuário.

1. O administrador do locatário deve habilitar a propriedade 'AllowNDIStreaming' no CsTeamsMeetingPolicy.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. Depois que essa alteração for preenchida, o usuário final deverá ativar a tecnologia NDI® para seu cliente específico a partir de  >  **Permissões de Configurações.**

Quando um usuário ingressar em uma reunião, ele verá uma mensagem que o notifica de que a reunião está sendo transmitida. Se os usuários não quiserem ser incluídos na transmissão, eles precisarão sair da reunião.

A imagem a seguir mostra a mensagem de faixa que um usuário vê em uma reunião do Teams.

![NDI® faixa de tecnologia que é exibida em uma reunião do Teams.](media/NDI-disclosure.png)

A faixa tem um link para a [política de privacidade da Microsoft.](https://aka.ms/teamsprivacy)

## <a name="supported-locales-and-user-types"></a>Localidades e tipos de usuário com suporte

A tecnologia ® NDI é suportada em todas as localidades. Os seguintes usuários estão incluídos em um fluxo de tecnologia NDI®, mas nem todos os usuários podem acessar o fluxo de tecnologia NDI®:

- No locatário – suporte total, fornecido com base no ring/tenantId/userId (controlado pela Política de Reuniões)
- Federado – sem acesso de fluxo (mesmo quando eles têm NDI® tecnologia em)<sup>1</sup>
- Premium – sem acesso de fluxo
- Anônimo – sem acesso de fluxo
- Convidado – sem acesso de fluxo  

<sup>1</sup> Os dispositivos têm uma configuração de ® NDI que está on por padrão. Se um participante da reunião estiver usando um dispositivo com ® NDI desligado, ele precisará ativar a tecnologia NDI® NDI.
