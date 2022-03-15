---
title: Salas do Microsoft Teams de versão do aplicativo
ms.author: czawideh
author: cazawideh
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
description: Saiba mais sobre o suporte ao ciclo de vida para Salas do Microsoft Teams, incluindo a estrutura de suporte dinâmico e suas fases.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b2f1ad2ce3be71667588288b82ca93646ff776a5
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503668"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Salas do Microsoft Teams de versão do aplicativo
 
O Salas do Microsoft Teams aplicativo recebe atualizações por meio do Windows store. Microsoft Teams aplicativo room usa um ciclo de vida do produto cada vez maior e somente a versão atual e a próxima mais recente do aplicativo são suportadas a qualquer momento. O Microsoft Teams room empacota uma versão específica do Teams da área de trabalho que é modificada para uso de sala. O Teams aplicativo da área de trabalho é atualizado a cada duas semanas. Saiba mais sobre o processo [Teams atualização](../teams-client-update.md). Isso significa que Salas do Teams versão atual do aplicativo 1 pode ter até seis atualizações de aplicativos de área de trabalho do Teams para trás, portanto, é recomendável manter o aplicativo do Teams Room atualizado para a versão mais recente do aplicativo Salas do Teams o tempo todo. 

A estrutura de suporte para Salas do Teams é dinâmica e depende da disponibilidade da versão mais recente. Quando você encontra um defeito de código em uma versão do aplicativo que não é a mais recente, você deve instalar a versão mais recente para receber uma correção.

Todas as versões estão listadas nas notas [Salas do Microsoft Teams versão.](rooms-release-note.md)

> [!IMPORTANT]
> Ao instalar um novo dispositivo que veio com uma versão mais antiga do aplicativo de sala Teams, é recomendável atualizar [manualmente](manual-update.md) o aplicativo após a configuração da conta, antes de baixar todas as atualizações Windows. Isso garante que a versão correta do sistema operacional e Windows as atualizações sejam instaladas em seu dispositivo.  

## <a name="windows-10-release-support"></a>Windows 10 de versão

Salas do Microsoft Teams requer o Windows 10 IoT Enterprise ou Windows 10 Enterprise SKUs em Semi-Annual opções de manutenção do Canal. Essas outras Windows 10 edições não são suportadas:

- Windows 10 Enterprise filial de manutenção a longo prazo (LTSB) / edições do Canal de Manutenção de Longo Prazo (LTSC)
- Windows 10 internet das coisas (IoT) Enterprise edições LTSB/LTSC
- qualquer outra edição de Windows, como Windows 10 Pro ou Home edition

As Windows 10 novas atualizações de recursos não são oferecidas em Salas do Microsoft Teams dispositivos imediatamente. Há um atraso intencional de até seis meses ou mais após a data de disponibilidade geral publicada na página Windows 10 [de lançamento](/windows/release-information/). Esse tempo é usado para validar Windows 10 versão do aplicativo Salas do Microsoft Teams, hardware de dispositivo e periféricos de vídeo de áudio certificados. A validação começa e continua durante o desenvolvimento ativo de cada versão principal do Windows 10. É necessário tempo extra para validar que todos os fabricantes de dispositivos tenham criado imagens atualizadas para seus dispositivos e que a Microsoft certifique e teste essas imagens. Durante o período de validação, o aplicativo Microsoft Teams Room usa [Windows de grupo Update for Business](/windows/deployment/update/waas-manage-updates-wufb) para atrasar Windows 10 de recursos. Depois que quaisquer problemas de compatibilidade são encontrados e resolvidos, o bloco é levantado por meio da atualização de políticas de grupo por meio de uma nova versão de aplicativo no Windows store. Dispositivos que executem o aplicativo Salas do Microsoft Teams atualizar automaticamente para uma versão Windows 10 apropriada durante a reinicialização de manutenção noturna. Uma versão MSI é disponibilizada para clientes que precisam gerenciar as atualizações manualmente.  

> [!IMPORTANT]
> Durante o período de validação, **Salas do Microsoft Teams dispositivos** não devem ser atualizados para a próxima versão Windows 10 por qualquer meio. Isso inclui a sobressução das políticas de grupo no local ou o uso System Center ou outros serviços de gerenciamento de dispositivos de terceiros. Qualquer um deles pode causar problemas para o aplicativo Microsoft Teams Room ou pode deixar os dispositivos inutilizáveis.  

A tabela a seguir mostra versões recomendadas e com suporte de Windows 10 que são verificadas para dar suporte a Salas do Microsoft Teams. Todas as datas são listadas no formato ISO 8601: YYYY-MM-DD.

|Versão  |Data de disponibilidade   |Salas do Microsoft Teams status de suporte   |Salas do Microsoft Teams versão mínima do aplicativo | Com build do sistema operacional recomendado  |
|:---  |:---       |:---                                  |:---     |:---     |
| 21H1 |2021-05-18 |Sem suporte                         |&#x2014; |&#x2014; |
| 20H2 |2020-10-20 |Com suporte, <br/>Recomendado|4.10.10.0 |19042.631 |
| 2004 |2020-05-27 |Ignorado, <br/> Não recomendado &#x2780;|&#x2014; |&#x2014; |
| 1909 |2019-11-12 |Com suporte |4.5.33.0 |18363.418  |
| 1903 |2019-05-21 |Sem suporte  |&#x2014; |&#x2014; |
| 1809 |2019-03-28 |Sem suporte, <br/>Problemas de compatibilidade conhecidos &#x2781;|&#x2014; |&#x2014; |
| 1803 |2018-07-10 |Sem suporte                             |&#x2014;  |&#x2014; |
| 1709 |2018-01-18 |Incompatível                         |&#x2014; |&#x2014; |
| 1703 |2017-07-11 |Sem suporte                         |&#x2014; |&#x2014; |

&#x2780; Windows 10 versão 2004 não é recomendada devido a problemas de compatibilidade encontrados com o Salas do Microsoft Teams aplicativo. Esse problema específico faz com que o aplicativo Salas do Microsoft Teams falha ao iniciar após a reinicialização noturna. 

&#x2781; Windows 10 versão 1809 não é recomendada devido a problemas de compatibilidade encontrados com o Salas do Microsoft Teams aplicativo. Esse problema específico faz com que o aplicativo Salas do Microsoft Teams falha ao iniciar após a reinicialização noturna. Esse problema foi abordado na Windows 10 versão 1903.  

Quando você usa uma versão com suporte do Windows 10, você sempre receberá as atualizações mais recentes do aplicativo Salas do Microsoft Teams aplicativo.  


## <a name="related-topics"></a>Tópicos relacionados

[Suporte às Salas do Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Salas do Microsoft Teams notas de versão](rooms-release-note.md)

[Planejar as Salas do Microsoft Teams](rooms-plan.md)
