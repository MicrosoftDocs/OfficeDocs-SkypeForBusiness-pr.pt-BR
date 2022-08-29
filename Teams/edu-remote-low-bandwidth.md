---
title: Solucionar problemas de cenários de baixa largura de banda para o Teams
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: jesegher
description: Obtenha ajuda com problemas de reunião e vídeo relacionados a problemas de baixa largura de banda no Teams. Seja você um pai, um educador ou um Administração ti, você tem opções para melhorar a experiência com o Teams.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7f60095f20d62ed14b19d7c23493553efc39b872
ms.sourcegitcommit: c19ac3be42cc4b8409c8d512bbe3156736af0309
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/24/2022
ms.locfileid: "67426808"
---
# <a name="troubleshoot-low-bandwidth-scenarios-for-teams"></a>Solucionar problemas de cenários de baixa largura de banda para o Teams

Este artigo fornecerá aos administradores de TI as práticas recomendadas ao lidar com problemas de baixa largura de banda no Teams.

Vários elementos de rede podem afetar o desempenho ao trabalhar com o Microsoft Teams.

- Conexão com a Internet de baixa velocidade para a escola.
- Conexão com a Internet de baixa velocidade para um ou mais alunos.
- Horários do dia em que há pouca largura de banda devido ao uso da rede em uma área.
- Interrupções não locais para a escola ou alunos, mas afetam o desempenho.
- Problemas com hardware que causam problemas de baixa largura de banda.

> [!IMPORTANT]
> Leia [como o Microsoft Teams usa memória para](teams-memory-usage-perf.md) limitações de recursos em dispositivos.
>
>Para obter diretrizes de rede do Teams, [consulte Preparar a rede da sua organização para o Microsoft Teams](prepare-network.md).

## <a name="resolving-low-bandwidth-issues-for-it-admins"></a>Resolução de problemas de baixa largura de banda para administradores de TI

Alguns problemas só podem ser resolvidos com um foco estreito no nível do usuário individual.

Se ocorrerem problemas de largura de banda para muitos usuários ou se as ações executadas no nível do usuário não tiverem sido úteis, a ação em toda a escola será a próxima etapa.

> [!NOTE]
> Você também pode ler o Guia [de Revisão de Qualidade da Experiência](quality-of-experience-review-guide.md). Não é específico do EDU, mas tem informações valiosas.

### <a name="meetings-and-video"></a>Reuniões e vídeo

Considere as ações abaixo ao lidar com problemas de reunião relacionados à baixa largura de banda de rede.

#### <a name="meeting-video-policies"></a>Políticas de vídeo de reunião

O Teams dimensiona automaticamente a qualidade da reunião para a largura de banda detectada pelo usuário. No entanto, você pode definir restrições adicionais para preservar a largura de banda.

Algumas restrições que você pode definir por meio da política incluem:

- Desativando completamente o vídeo para que ninguém possa usar o vídeo.
- Limitando a taxa de bits de mídia, que é definida por usuário.

Para obter mais políticas que você deve definir para reuniões e vídeo, leia as [configurações da política de reunião no Teams: Áudio e vídeo](meeting-policies-audio-and-video.md).

#### <a name="screen-sharing-policies"></a>Políticas de compartilhamento de tela

No Teams, os usuários podem compartilhar toda a tela ou janelas individuais.

O compartilhamento de uma tela inteira usa mais largura de banda do que apenas compartilhar uma janela.

- Impedir que os usuários compartilhem toda a tela por meio da política.
- Instrua os educadores a compartilharem apenas aplicativos, não toda a tela.

Saiba mais sobre as políticas de compartilhamento de tela [nas configurações de política de reunião no Teams: Áudio e vídeo](meeting-policies-audio-and-video.md).

#### <a name="dial-in-number-for-meetings"></a>Números de discagem para reuniões

Pode ser mais fácil para alguns alunos discar para sessões de sala de aula.

- Forneça um número de discagem para reuniões do Teams como uma alternativa para participar de uma reunião em vídeo.

Para obter mais informações, leia [Definir os números de telefone incluídos em convites no Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).

## <a name="low-bandwidth-scenarios-as-an-educator"></a>Cenários de baixa largura de banda como educador

Ter educadores para solucionar problemas de largura de banda pode ser uma opção melhor do que a ação de TI nas seguintes situações:

- O problema é intermitente.
- Há uma hora específica do dia que você pode prever que há um problema.

Para obter as etapas que um educador pode seguir para resolver problemas de largura de banda, [leia Usar o Teams para o trabalho escolar quando a largura de banda estiver baixa](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262).

## <a name="low-bandwidth-scenarios-as-a-parent-or-student"></a>Cenários de baixa largura de banda como pai ou aluno

Às vezes, o problema de largura de banda está do lado de um aluno.

- Sua casa pode não ter acesso à alta largura de banda.
- Eles podem ter muitas pessoas em sua área imediata também consumindo largura de banda.
- Pode haver instabilidade na Internet.

Criamos orientações em nosso Use Teams para o trabalho escolar quando a largura de banda [é um](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262) artigo baixo para pais e alunos.
