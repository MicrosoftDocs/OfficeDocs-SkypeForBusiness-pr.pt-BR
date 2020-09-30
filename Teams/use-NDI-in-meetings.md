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
ms.openlocfilehash: a1b756cfdb56de533d4dd170f301dc38e4b3b529
ms.sourcegitcommit: 45064a0020a1231e17967c74f082106c68213ea0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2020
ms.locfileid: "48308164"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a>Usar a tecnologia® do NDI no Microsoft Teams

 NewTek NDI® a tecnologia de dispositivo de rede (Network Device Interface) é uma solução moderna para conexão de dispositivos de mídia (como uma câmera e mixer de estúdio). Em vez de usar conexões físicas, o NDI® tecnologia permite a conectividade em uma intranet local, incluindo em um computador local.

NDI® tecnologia tornou-se uma solução padrão do setor para a produção de conteúdo dinâmico para fluxos e ganhou conscientização significativa e adoção no mundo da transmissão profissional.

O Skype adicionou NDI a funcionalidade®-out ao Skype no fim do 2018. O Microsoft Teams usa essa funcionalidade para melhorar a experiência da reunião.

NDI® tecnologia está limitada a uma rede local e só deve ser considerada uma parte do fluxo de trabalho de produção, não uma solução de transmissão.

## <a name="turn-on-ndi-technology"></a>Ativar a tecnologia® do NDI

NDI® tecnologia exige que duas etapas sejam ativadas para um usuário.

1. O administrador de locatários deve habilitar a propriedade ' AllowNDIStreaming ' em CsTeamsMeetingPolicy.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. Depois que essa alteração tiver sido completada, o usuário final precisará ativar o NDI® tecnologia para o cliente específico nas permissões de **configurações**  >  **Permissions**.

Quando um usuário ingressa em uma reunião, ele vê uma mensagem que informa que a reunião está sendo transmitida. Se os usuários não quiserem ser incluídos na transmissão, eles precisarão ser descartados da reunião.

A imagem a seguir mostra a mensagem de faixa que o usuário vê em uma reunião do teams.

![Uma imagem da faixa de tecnologia® do NDI que é exibida em uma reunião do teams.](media/NDI-disclosure.png)

A faixa tem um link para a [política de privacidade da Microsoft](https://aka.ms/teamsprivacy).

## <a name="supported-locales-and-user-types"></a>Locais e tipos de usuários com suporte

NDI® tecnologia tem suporte em todas as localidades. Os seguintes usuários estão incluídos em um fluxo de tecnologia de® NDI, mas nem todos os usuários podem acessar o fluxo de tecnologia de® do NDI:

- In-locatário – suporte completo, entregue com base em anel/tenantid/userId (controlado por política de reuniões)
- Federado – sem acesso de fluxo (mesmo quando eles têm a tecnologia de® de NDI)<sup>1</sup>
- Freemium-sem acesso de fluxo
- Anônimo – sem acesso de fluxo
- Convidado – sem acesso de fluxo  

<sup>1</sup> dispositivos têm uma configuração de tecnologia NDI® que está ativada por padrão. Se um participante da reunião estiver usando um dispositivo com NDI® tecnologia desligada, ele precisará ativar o NDI® tecnologia.
