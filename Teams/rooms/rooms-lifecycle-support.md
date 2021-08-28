---
title: Salas do Microsoft Teams de versão do aplicativo
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
ms.localizationpriority: medium
description: Saiba mais sobre o suporte ao ciclo de vida Salas do Microsoft Teams, incluindo a estrutura de suporte dinâmico e suas fases.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7ecfd878b5d8aa22a19b4b2831c04a73e0d8911e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58607024"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Salas do Microsoft Teams de versão do aplicativo
 
O Salas do Microsoft Teams aplicativo recebe atualizações algumas vezes por ano. Cada atualização é suportada por doze (12) meses a partir de sua data de lançamento de disponibilidade geral (GA). O suporte técnico é fornecido para os doze (12) meses inteiros. No entanto, a estrutura de suporte é dinâmica, com duas fases distintas que dependem da disponibilidade da versão mais recente:

- **Fase de Manutenção** e Atualizações Críticas - Quando você executar a versão mais  recente do aplicativo Salas do Microsoft Teams, receberá atualizações regulares que contêm atualizações de Segurança e Manutenção.

- Fase Somente Atualizações de Segurança **-** Quando uma nova versão do aplicativo Salas do Microsoft Teams versões,  as versões mais antigas do aplicativo têm um nível de suporte reduzido com atualizações de segurança apenas para o restante do ciclo de vida de doze (12) meses.

> [!NOTE]
> A versão mais recente está sempre na fase Manutenção e Atualizações Críticas. Quando você encontra um defeito de código que garante uma atualização crítica, você também deve ter a versão mais recente instalada para receber uma correção. Todas as outras versões com suporte só serão qualificadas para receber atualizações de segurança.

Todo o suporte termina após o ciclo de vida de doze (12) meses de uma versão ter expirado ou se mais de duas atualizações foram lançadas desde então. Em seguida, os clientes devem atualizar para uma versão com suporte.

Todas as versões estão listadas nas [notas Salas do Microsoft Teams de versão](rooms-release-note.md).

## <a name="windows-10-release-support"></a>Windows 10 de versão

Salas do Microsoft Teams requer o Windows 10 IoT Enterprise ou Windows 10 Enterprise SKUs em Semi-Annual de manutenção do Canal. Essas outras Windows 10 edições não são suportadas:

- Windows 10 Enterprise Ramificação de Manutenção de Longo Prazo (LTSB) / Edições do Canal de Manutenção de Longo Prazo (LTSC)
- Windows 10 Internet das Coisas (IoT) Enterprise edições LTSB/LTSC
- qualquer outra edição de Windows, como Windows 10 Pro ou Home edition

As novas Windows 10 de recursos não são oferecidas em Salas do Microsoft Teams dispositivos imediatamente. Um atraso intencional de até seis meses após a data de disponibilidade geral publicada na página Windows 10 [de lançamento.](/windows/release-information/) O tempo de atraso é usado para validar Windows 10 versão do Salas do Microsoft Teams aplicativo, hardware do dispositivo e periféricos de vídeo de áudio certificados. A validação começa e continua durante o desenvolvimento ativo de cada versão principal do Windows 10. É necessário tempo extra para validar que todos os fabricantes de dispositivos tenham criado imagens atualizadas para seus dispositivos e para que Microsoft Teams certificar e testar essas imagens. Durante o período de validação, o aplicativo Microsoft Teams Room usa Windows de grupo [Update for Business](/windows/deployment/update/waas-manage-updates-wufb) para atrasar Windows 10 de recursos. Depois que quaisquer problemas de compatibilidade são encontrados e resolvidos, o bloco é levantado por meio da atualização de políticas de grupo por meio de uma nova versão de aplicativo no Windows store. Dispositivos que executem o aplicativo Salas do Microsoft Teams atualizar automaticamente para uma versão Windows 10 apropriada durante a reinicialização de manutenção noturna. Uma versão MSI é disponibilizada para clientes que desejam gerenciar as atualizações manualmente.  

> [!IMPORTANT]
> Durante o período de validação, Salas do Microsoft Teams **dispositivos** não devem ser atualizados para a próxima versão Windows 10 por qualquer meio. Isso inclui a substituição das políticas de grupo no local ou o uso de System Center ou outros serviços de gerenciamento de dispositivos de terceiros. Qualquer um deles pode causar problemas para o aplicativo Microsoft Teams Room ou pode deixar os dispositivos inutilizáveis.  

A tabela a seguir mostra versões recomendadas e com suporte de Windows 10 que são verificadas para dar suporte a Salas do Microsoft Teams. Todas as datas são listadas no formato ISO 8601: YYYY-MM-DD.

|Versão  |Data de disponibilidade   |Salas do Microsoft Teams status de suporte   |Salas do Microsoft Teams Versão mínima do aplicativo | Com build do sistema operacional recomendado  |
|:---  |:---       |:---                                  |:---     |:---     |
| 20H2 |2020-10-20 |Com suporte, <br/>Recomendado|4.8.31.0 |19042.631 |
| 2004 |2020-05-27 |Ignorado, <br/> Não recomendado &#x2780;|&#x2014; |&#x2014; |
| 1909 |2019-11-12 |Com suporte |4.5.33.0 |18363.418  |
| 1903 |2019-05-21 |Sem suporte  |&#x2014; |&#x2014; |
| 1809 |2019-03-28 |Sem suporte, <br/>Problemas de compatibilidade conhecidos &#x2781;|&#x2014; |&#x2014; |
| 1803 |2018-07-10 |Sem suporte                             |&#x2014;  |&#x2014; |
| 1709 |2018-01-18 |Incompatível                         |&#x2014; |&#x2014; |
| 1703 |2017-07-11 |Sem suporte                         |&#x2014; |&#x2014; |

&#x2780; Windows 10 versão 2004 não é recomendada devido a problemas de compatibilidade encontrados com o Salas do Microsoft Teams aplicativo. Esse problema específico faz com que o aplicativo Salas do Microsoft Teams falha ao iniciar após a reinicialização noturna. 

&#x2781; Windows 10 versão 1809 não é recomendada devido a problemas de compatibilidade encontrados com o Salas do Microsoft Teams aplicativo. Esse problema específico faz com que o aplicativo Salas do Microsoft Teams falha ao iniciar após a reinicialização noturna. Esse problema foi abordado na Windows 10 versão 1903.  

Quando você usa uma versão com suporte do Windows 10, você sempre receberá as atualizações mais recentes de aplicativos para o Salas do Microsoft Teams app.  

> [!IMPORTANT]
> A Windows 10 atualização do 20H2 ainda não está disponível para os seguintes dispositivos Salas do Teams devido a problemas de compatibilidade. Os OEMs de dispositivo estão trabalhando para resolver esses problemas assim que possível. Windows 10 20H2 não serão oferecidos nesses dispositivos. Não atualize manualmente esses dispositivos para o 20H2 substituindo os GPOs (objetos de política de grupo) ou o gerenciamento de dispositivo móvel (MDM). 
> 
> Os dispositivos com problemas de compatiablidade são:
> 
> - Crestron UC-Engine (versão/data do BIOS contém "KYSKLI" - indicando um BIOS do Skull Canyon) 

## <a name="related-topics"></a>Tópicos relacionados

[Suporte às Salas do Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Salas do Microsoft Teams notas de versão](rooms-release-note.md)

[Planejar as Salas do Microsoft Teams](rooms-plan.md)
