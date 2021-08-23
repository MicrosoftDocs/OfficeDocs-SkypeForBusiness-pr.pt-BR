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
description: Saiba como usar a NDI em Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2a9eed33ba105584379f207697c27e8d6bd6cde5
ms.sourcegitcommit: 85017cf88789c750836780dad2ef707c1c6c39b4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/16/2021
ms.locfileid: "58359178"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a>Usar a tecnologia NDI® em Microsoft Teams

 A tecnologia NewTek NDI® (Interface de Dispositivo de Rede) é uma solução moderna para conectar dispositivos de mídia (como uma câmera de estúdio e um mixer). Em vez de usar conexões físicas, a tecnologia ® NDI habilita a conectividade em uma intranet local, inclusive em uma máquina local.

A tecnologia ® NDI se tornou uma solução padrão do setor para produzir conteúdo ao vivo para fluxos e ganhou uma conscientização significativa e adoção no mundo da transmissão profissional.

Skype a funcionalidade de ® NDI foi adicionada Skype final de 2018. Microsoft Teams usa essa funcionalidade para melhorar a experiência de reunião.

A ® NDI está limitada a uma rede local e deve ser considerada apenas uma parte do fluxo de trabalho de produção, não uma solução de transmissão.

## <a name="turn-on-ndi-technology"></a>Ativar a tecnologia NDI®

A tecnologia ® NDI requer duas etapas para ser 1 para um usuário.

1. O administrador do locatário deve permitir que o usuário final tenha a NDI ativada para sua política de reunião. Isso pode ser feito individualmente no portal de administração Teams ou por meio do Teams PowerShell pela propriedade _AllowNDIStreaming_ em CsTeamsMeetingPolicy.

    ```PowerShell
    Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
    ```

2. Depois que essa alteração for preenchida, o usuário final deverá ativar a tecnologia NDI® para seu cliente específico Configurações  >  **Permissões**.

Depois de ser ligado para um usuário e seu cliente específico, o usuário pode ativar a NDI por meio do menu de estouro e selecionar "Transmitir sobre NDI".

Depois de iniciar a NDI e ter um ponto de extremidade inscrito em um feed de NDI, eles verão uma mensagem que os notifica de que a reunião está sendo transmitida. Se os usuários não quiserem ser incluídos na transmissão, eles precisarão sair da reunião.

A imagem a seguir mostra a mensagem em faixa que um usuário vê em uma Teams reunião.

![ele NDI® faixa de tecnologia que é exibida em uma Teams reunião.](media/NDI-disclosure.png)

O banner tem um link para a [política de privacidade da Microsoft.](https://aka.ms/teamsprivacy)

> [!NOTE]
> NDI® é ativado somente por sessão. Na próxima reunião, o usuário deve ativá-lo antes de usar o NDI®.

## <a name="supported-locales-and-user-types"></a>Localidades e tipos de usuário com suporte

A ® NDI é suportada em todas as localidades.

O acesso ao uso da NDI é determinado pela política de reunião para o usuário que está tentando ativar o recurso. Para a solução mais segura, não apronte a política de NDI como uma configuração global.
