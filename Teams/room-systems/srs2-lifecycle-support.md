---
title: Suporte de versão
ms.author: v-lanac
author: lanachin
ms.reviewer: davgroom
manager: serdars
ms.date: 4/17/2018
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection: M365-voice
localization_priority: Normal
description: Este artigo discute o suporte do ciclo de vida para salas do Microsoft Teams.
ms.openlocfilehash: dc4f8c0997ee64f4011aed6056be506738012639
ms.sourcegitcommit: 1401ee484a2bc8e72d96649b0571bb59198f9dab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/15/2019
ms.locfileid: "36427682"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Suporte à versão do aplicativo salas do Microsoft Teams
 
A Microsoft planeja liberar atualizações para as salas do Microsoft Teams algumas vezes por ano, com cada atualização compatível com doze (12) meses a partir da data de lançamento do GA (disponibilidade geral). O suporte técnico é oferecido para os doze (12) meses inteiros. No entanto, a estrutura de suporte agora é dinâmica, evoluindo para duas fases de manutenção distintas que dependem da disponibilidade da versão mais recente.

**Fase de manutenção de serviços e atualizações críticas** \- Ao executar a versão mais recente dos salas do Microsoft Teams, você recebe atualizações regulares, que contêm atualizações de segurança e manutenção.

**Fase de manutenção de atualizações de segurança (apenas)** \- Depois que uma nova versão for liberada, o suporte para ramificações mais antigas será reduzido para atualizações de segurança apenas para o restante das doze (12) meses de ciclo de vida de suporte.

> [!NOTE]
> A versão mais recente está sempre na fase manutenção e manutenção de atualizações críticas. Isso significa que, caso você encontre um defeito de código que garanta uma atualização crítica, você deve ter a versão mais recente instalada para receber uma correção. Todas as outras versões com suporte só serão elegíveis para receber atualizações de segurança.

O suporte será encerrado depois que o ciclo de vida de doze (12) meses tiver expirado ou se mais de duas atualizações tiverem sido lançadas desde então. Em seguida, os clientes devem atualizar para uma versão com suporte.

Todas as versões estão listadas nas [notas de versão das salas do Microsoft Teams](srs2-release-note.md).

# <a name="os-version-support"></a>Suporte para versão do sistema operacional
As atualizações de recursos do Windows 10 para dispositivos que executam salas do Microsoft Teams não são oferecidas por seis meses a partir do momento em que o Windows faz uma atualização de versão. Isso é realizado colocando um bloco especial para dispositivos de salas do Microsoft Teams no canal do Windows Update para empresas (ou seja, canal semestral) e por meio das configurações do aplicativo. Durante este período bloqueado, a Microsoft executa vários testes internos e por meio dos nossos parceiros OEM para garantir que a nova versão do Windows 10 Feature funcione em harmonia com o aplicativo salas do Microsoft Teams e periféricos conectados a ele. Isso é importante para garantir a segurança do dispositivo, a experiência do usuário consistente e garantir a qualidade das experiências oferecidas pelo aplicativo salas do Microsoft Teams. 

No bloco de tempo é levantado (ou seja, a atualização de recursos do Window 10 é oferecida para download nesses dispositivos), as salas do Microsoft Teams dão suporte ao lançamento do recurso específico do Windows 10 para o período de 12 meses, em uma política de suporte do aplicativo. Como as atualizações de recursos do Windows 10 são oferecidas a cada seis meses, isso também significa que o Microsoft Teams tem duas versões adicionais para testar no momento em que o suporte para a versão atual é encerrado. Isso também significa que uma versão do Windows 10 é desbloqueada a cada seis meses para todos os clientes de salas do Microsoft Teams. O aplicativo é alterado continuamente e desenvolvido com base na última versão do Windows desbloqueada. Para garantir que você tenha a correção do aplicativo para um problema que você encontra em seu dispositivo de salas do Microsoft Teams, recomendamos que todos os clientes atualizem esses dispositivos para a atualização de recursos mais recente do Windows 10 oferecida para manter-se atualizado com as diretrizes de versão do Windows.

Assim, os dispositivos de salas do Microsoft Teams exigem o Windows 10 versão 1709 como a versão mínima com suporte a 2019 de maio de. Não são oferecidas novas versões do aplicativo para sistemas nas versões 1703 ou anteriores do Windows 10.

> [!NOTE]
> Quando um dispositivo de salas do Microsoft Teams é compatível com a próxima versão do Windows 10 OS, o dispositivo é atualizado automaticamente para a próxima versão por meio do Windows Update. Os dispositivos de salas do Microsoft Teams não devem ser atualizados manualmente para o próximo lançamento do Windows 10 ou por meio da habilitação das políticas de grupo do Windows Update for Business (WUFB) usando o "selecionar o nível de preparação do Windows para as atualizações que você deseja receber" e "selecionar quando Versões prévias e atualizações de recursos são recebidas "opções por meio de um GPO. Habilitar essas diretivas de grupo é conhecido por levar a problemas entre a atualização do Windows 10 OS e o aplicativo salas do Microsoft Teams. 
 
<a name="See"> </a> 
## <a name="see-also"></a>Confira também

[Suporte às Salas do Microsoft Teams](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Salas de lançamento das salas do Microsoft Teams](srs2-release-note.md)

[Plano para salas do Microsoft Teams](skype-room-systems-v2-0.md)
