---
title: Suporte de versão
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: Saiba mais sobre o suporte ao ciclo de vida das Salas do Microsoft Teams, incluindo a estrutura de suporte dinâmico e suas fases.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 584f4661a39d21f916b2097c242f71b996c568e6
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662446"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Suporte à versão do aplicativo Salas do Microsoft Teams
 
O aplicativo Salas do Microsoft Teams recebe atualizações algumas vezes por ano. Cada atualização tem suporte para doze (12) meses a partir da data de lançamento de disponibilidade geral (GA). O suporte técnico é fornecido para os doze (12) meses inteiros. No entanto, a estrutura de suporte é dinâmica, com duas fases distintas que dependem da disponibilidade da versão mais recente:

- **Fase de manutenção e atualizações críticas** \- Ao executar a versão mais recente do aplicativo Salas do  Microsoft Teams, você recebe atualizações regulares que contêm atualizações de Segurança e Manutenção.

- **Fase somente de atualizações de segurança** \- Quando uma nova versão do aplicativo Salas do Microsoft Teams é lançado,  as versões mais antigas do aplicativo têm um nível de suporte reduzido com atualizações de segurança apenas para o restante do ciclo de vida de doze (12) meses.

> [!NOTE]
> A versão mais recente está sempre na fase de Manutenção e Atualizações Críticas. Quando você encontra uma falha de código que garante uma atualização crítica, você também deve ter a versão mais recente instalada para receber uma correção. Todas as outras versões com suporte só estarão qualificadas para receber atualizações de segurança.

Todo o suporte termina após o ciclo de vida de doze (12) meses de uma versão ter expirado ou se mais de duas atualizações foram lançadas desde então. Em seguida, os clientes devem atualizar para uma versão com suporte.

Todas as versões são listadas nas notas de versão das [Salas do Microsoft Teams.](rooms-release-note.md)

## <a name="windows-10-release-support"></a>Suporte para versão do Windows 10

As Salas do Microsoft Teams exigem as SKUs do Windows 10 Enterprise ou do Windows 10 Enterprise sob Semi-Annual de manutenção de canal. Não há suporte para essas outras edições do Windows 10:

- Edições do Canal de Manutenção a Longo Prazo do Windows 10 Enterprise (LTSB) / Canal de Manutenção de Longo Prazo (LTSC)
- Windows 10 Internet of Things (IoT) Enterprise LTSB/LTSC edições
- qualquer outra edição do Windows, como o Windows 10 Pro ou Home Edition

Uma atualização de recursos do Windows 10 não é oferecida ou atualizada em dispositivos Microsoft Teams Rooms imediatamente. Um atraso intencional de até seis meses após a data de disponibilidade geral publicada na página de informações de versão do [Windows 10.](https://docs.microsoft.com/windows/release-information/) O tempo de atraso é usado para validar a compatibilidade de versão do Windows 10 para o aplicativo Salas do Microsoft Teams, hardware do dispositivo e periféricos de vídeo de áudio certificados. A validação começa e continua durante o desenvolvimento ativo de cada versão principal do Windows 10. É necessário tempo extra para validar que todos os fabricantes de dispositivos tenham criado imagens atualizadas para seus dispositivos e que o Microsoft Teams certifique e teste essas imagens. Durante o período de validação, o aplicativo Sala do Microsoft Teams usa políticas de grupo do  [Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) para atrasar as atualizações de recursos do Windows 10. Depois que quaisquer problemas de compatibilidade são encontrados e resolvidos, o bloqueio é suspenso por meio da atualização de políticas de grupo por meio de uma nova versão de aplicativo na Windows Store. Os dispositivos que executarem o aplicativo Salas do Microsoft Teams são atualizados automaticamente para uma versão apropriada do Windows 10 durante a reinicialização de manutenção noturna. Uma versão MSI é disponibilizada para clientes que desejam gerenciar as atualizações manualmente.  

> [!IMPORTANT]
> Durante o período de validação, os dispositivos do Microsoft Teams Rooms **não** devem ser atualizados para a próxima versão do Windows 10 por qualquer meio. Isso inclui a sobrecarro das políticas de grupo no local ou o uso do System Center ou outros serviços de gerenciamento de dispositivo de terceiros. Qualquer um desses problemas pode causar problemas para o aplicativo Sala do Microsoft Teams ou pode deixar dispositivos inutilizáveis.  

A tabela a seguir mostra as versões recomendadas e com suporte do Windows 10 que são verificadas para dar suporte às Salas do Microsoft Teams. Todas as datas são listadas no formato ISO 8601: YYYYY-MM-DD.

|Versão  |Data de disponibilidade   |Status de suporte das Salas do Microsoft Teams   |Versão mínima do aplicativo Salas do Microsoft Teams | Com build do sistema operacional recomendado  |
|:---  |:---       |:---                                  |:---     |:---     |
| 20H2 |2020-10-20 |Em validação, <br/>Ainda não há suporte|&#x2014; |19042.572 |
| 2004 |2020-05-27 |Ignorada <br/> Não recomendado|&#x2014; |19041.264 |
| 1909 |2019-11-12 |Suportado <br/>Recomendado |4.5.33.0 |18363.418  |
| 1903 |2019-05-21 |Com suporte  |4.2.4.0 |18362.356 |
| 1809 |2019-03-28 |Sem suporte, <br/>Problemas de compatibilidade conhecidos &#x2780;|&#x2014; |&#x2014; |
| 1803 |2018-07-10 |Sem suporte                             |&#x2014;  |&#x2014; |
| 1709 |2018-01-18 |Incompatível                         |&#x2014; |&#x2014; |
| 1703 |2017-07-11 |Sem suporte                         |&#x2014; |&#x2014; |

&#x2780; windows 10 versão 1809 não é recomendável devido a problemas de compatibilidade encontrados com o aplicativo Salas do Microsoft Teams. Esse problema específico faz com que o aplicativo Salas do Microsoft Teams falhe ao iniciar após a reinicialização noturna. Esse problema foi resolvido na versão 1903 do Windows 10.  

&#x2781; Windows 10 versão 2004 não é recomendável devido a problemas de compatibilidade encontrados com o aplicativo Salas do Microsoft Teams. Esse problema específico faz com que o aplicativo Salas do Microsoft Teams falhe ao iniciar após a reinicialização noturna. 

Ao usar uma versão com suporte do Windows 10, você sempre receberá as atualizações mais recentes do aplicativo Salas do Microsoft Teams.  

## <a name="related-topics"></a>Tópicos relacionados

[Suporte às Salas do Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Notas de versão do Microsoft Teams Rooms](rooms-release-note.md)

[Planejar as Salas do Microsoft Teams](rooms-plan.md)
