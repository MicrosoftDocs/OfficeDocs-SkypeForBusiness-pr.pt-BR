---
title: Salas do Microsoft Teams versão do aplicativo
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
description: Saiba mais sobre o suporte ao ciclo de Salas do Microsoft Teams, incluindo a estrutura de suporte dinâmico e suas fases.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c0353dc1a52dbc16d42d7c7e2f974675bb5098aa
ms.sourcegitcommit: cd4464fe9bf0f38ed4c3ca058a51bcd29578eef9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2022
ms.locfileid: "65316507"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Salas do Microsoft Teams versão do aplicativo
 
O Salas do Microsoft Teams aplicativo obtém atualizações por meio da Windows armazenamento. Microsoft Teams aplicativo room usa um ciclo de vida de produto cada vez maior e somente a versão atual e a próxima mais recente do aplicativo têm suporte a qualquer momento. O Microsoft Teams Room agrupa uma versão específica do aplicativo Teams desktop que é modificado para uso na sala. O Teams da área de trabalho é atualizado a cada duas semanas. Saiba mais sobre o processo [Teams atualização.](../teams-client-update.md) Isso significa que Salas do Teams versão atual 1 do aplicativo pode ter até seis atualizações de aplicativos da área de trabalho do Teams para trás, portanto, é recomendável manter o aplicativo sala Teams atualizado para a versão mais recente do aplicativo Salas do Teams em todos os momentos. 

A estrutura de suporte para Salas do Teams é dinâmica e depende da disponibilidade da versão mais recente. Ao encontrar um defeito de código em uma versão do aplicativo que não seja a mais recente, você deve instalar a versão mais recente para receber uma correção.

Todas as versões são listadas nas notas [Salas do Microsoft Teams versão](rooms-release-note.md).

> [!IMPORTANT]
> Ao instalar um novo dispositivo que veio com uma versão mais antiga do aplicativo de sala Teams, é recomendável atualizar [manualmente](manual-update.md) o aplicativo após a configuração da conta, antes de baixar quaisquer atualizações Windows aplicativo. Isso garante que a versão correta do sistema operacional Windows as atualizações sejam instaladas em seu dispositivo.  

## <a name="windows-10-release-support"></a>Windows 10 de versão

Salas do Microsoft Teams requer o Windows 10 IoT Enterprise ou Windows 10 Enterprise SKUs em Semi-Annual de manutenção de canal. Essas outras Windows 10 edições não têm suporte:

- Windows 10 Enterprise LTSB (Branch de Manutenção de Longo Prazo) /LTSC (Canal de Manutenção de Longo Prazo)
- Windows 10 internet das coisas (IoT) Enterprise edições LTSB/LTSC
- qualquer outra edição de Windows como Windows 10 Pro ou Home Edition

As Windows 10 novas atualizações de recursos não são oferecidas em Salas do Microsoft Teams dispositivos imediatamente. Há um atraso intencional de até seis meses ou mais após a data de disponibilidade geral publicada na página de informações Windows 10 [versão](/windows/release-information/). Esse tempo é usado para validar Windows 10 versão do aplicativo Salas do Microsoft Teams, hardware do dispositivo e periféricos de vídeo de áudio certificados. A validação começa e continua durante o desenvolvimento ativo de cada versão principal do Windows 10. É necessário um tempo extra para validar se todos os fabricantes de dispositivos criaram imagens atualizadas para seus dispositivos e para a Microsoft certificar e testar essas imagens. Durante o período de validação, o aplicativo Microsoft Teams Room usa Windows Update [de](/windows/deployment/update/waas-manage-updates-wufb) grupo para Empresas para atrasar Windows 10 de recursos. Depois que quaisquer problemas de compatibilidade forem encontrados e resolvidos, o bloco será removido por meio da atualização de políticas de grupo por meio de uma nova versão de aplicativo Windows armazenamento. Os dispositivos que executam o aplicativo Salas do Microsoft Teams são atualizados automaticamente para uma versão Windows 10 apropriada durante a reinicialização da manutenção noturna. Uma versão do MSI é disponibilizada para clientes que precisam gerenciar atualizações manualmente.  

> [!IMPORTANT]
> Durante o período de validação, **Salas do Microsoft Teams dispositivos** não devem ser atualizados para a próxima versão do Windows 10 por qualquer meio. Isso inclui substituir as políticas de grupo em vigor ou usar System Center ou outros serviços de gerenciamento de dispositivos de terceiros. Qualquer um deles pode causar problemas para o aplicativo Microsoft Teams Room ou pode deixar os dispositivos inutilizáveis.  

A tabela a seguir mostra as versões recomendadas e compatíveis Windows 10 que são verificadas para dar suporte a Salas do Microsoft Teams. Todas as datas são listadas no formato ISO 8601: AAAA-MM-DD.

| Versão | Data de disponibilidade | Salas do Microsoft Teams de suporte                    | Salas do Microsoft Teams versão mínima do aplicativo | Build do sistema operacional recomendado |
|:--------|:------------------|:--------------------------------------------------------|:--------------------------------------------------|:---------------------|
| 21H2    | 2021-11-16        | Suportado<br>Recomendado                               | 4.12.126.0                                        | 19044.1288           |
| 21H1    | 2021-05-18        | Sem suporte                                           | &#x2014;                                          | &#x2014;             |
| 20H2    | 2020-10-20        | Com suporte                                               | 4.10.10.0                                         | 19042.631            |
| 2004    | 2020-05-27        | Ignorada <br/> Não recomendado &#x2780;                 | &#x2014;                                          | &#x2014;             |
| 1909    | 2019-11-12        | Com suporte                                               | 4.5.33.0                                          | 18363.418            |
| 1903    | 2019-05-21        | Sem suporte                                           | &#x2014;                                          | &#x2014;             |
| 1809    | 2019-03-28        | Sem suporte, <br/>Problemas de compatibilidade conhecidos &#x2781; | &#x2014;                                          | &#x2014;             |
| 1803    | 2018-07-10        | Sem suporte                                           | &#x2014;                                          | &#x2014;             |
| 1709    | 2018-01-18        | Incompatível                                           | &#x2014;                                          | &#x2014;             |
| 1703    | 2017-07-11        | Sem suporte                                           | &#x2014;                                          | &#x2014;             |

&#x2780; Windows 10 versão 2004 não é recomendada devido a problemas de compatibilidade encontrados com o Salas do Microsoft Teams aplicativo. Esse problema específico faz com que Salas do Microsoft Teams aplicativo não seja iniciado após a reinicialização noturna. 

&#x2781; Windows 10 versão 1809 não é recomendada devido a problemas de compatibilidade encontrados com o Salas do Microsoft Teams aplicativo. Esse problema específico faz com que Salas do Microsoft Teams aplicativo não seja iniciado após a reinicialização noturna. Esse problema foi resolvido Windows 10 versão 1903.  

Ao usar uma versão com suporte do Windows 10, você sempre obterá as atualizações de aplicativo mais recentes para o Salas do Microsoft Teams aplicativo.  


## <a name="related-topics"></a>Tópicos relacionados

[Suporte às Salas do Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Salas do Microsoft Teams de versão](rooms-release-note.md)

[Planejar as Salas do Microsoft Teams](rooms-plan.md)
