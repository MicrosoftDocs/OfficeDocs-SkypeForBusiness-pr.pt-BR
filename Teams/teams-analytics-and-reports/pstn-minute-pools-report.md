---
title: Relatório de grupos de minutos PSTN do Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
MS.collection:
- M365-voice
description: Como usar o relatório de grupos de minutos PSTN do teams no centro de administração do Microsoft Teams para exibir os minutos consumidos na sua organização durante o mês atual.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5f44d8a48dc01b8d2cdbce9dd164d5b2440c24d8
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43140662"
---
# <a name="microsoft-teams-pstn-minute-pools-report"></a>Relatório de grupos de minutos PSTN do Microsoft Teams

O relatório de grupos de minutos de tempo PSTN do teams no centro de administração do Microsoft Teams oferece uma visão geral das atividades de conferência e de chamada de áudio em sua organização mostrando o número de minutos consumidos durante o mês atual. Você pode ver um detalhamento da atividade, incluindo a licença usada para chamadas, o total de minutos disponíveis, os minutos usados e o uso da licença por local.

## <a name="view-the-report"></a>Exibir o relatório

Na navegação à esquerda do centro de administração do Microsoft Teams, clique em **análises &** > relatórios de**uso**dos relatórios. Na guia **exibir relatórios** , em **relatório**, selecione **pools de minutos PSTN**e clique em **executar relatório**.

![Captura de tela do relatório de grupos de minutos PSTN do teams no centro de administração](../media/teams-reports-pstn-minute-pools-with-callouts.png "Captura de tela do relatório de grupos de minutos PSTN do teams no centro de administração do Microsoft Teams com textos explicativos numerados")

## <a name="interpret-the-report"></a>Interpretar relatório

|Texto Explicativo |Descrição  |
|--------|-------------|
|**1**   |Cada relatório tem uma data para o momento em que foi gerado. O relatório geralmente reflete um período de latência de atividade de 24 a 48 horas. |
|**2**   |Clique em uma funcionalidade (licença) para exibir atividades para essa funcionalidade. |
|**3**   |O eixo X é país ou região. O eixo Y é o número de minutos. <br>Passe o mouse sobre uma barra no gráfico para ver a atividade desse local de uso.  |
|**4**   |Você pode filtrar o que se vê no gráfico clicando em um item na legenda. Por exemplo, clique em não **usado**, **usuários domésticos**, **nenhum dado**ou **internacional usado** para ver apenas as informações relacionadas a cada um. |
|**5**   |A tabela oferece uma divisão de pools de minutos por funcionalidade e localização de uso. <ul><li>**País ou região** é o local de uso. </li><li>**Descrição da funcionalidade** é a descrição da licença usada para a chamada.  As descrições de recursos que podem ser exibidas neste relatório incluem: <ul><li>Plano de chamadas domésticas e internacionais (1200 minutos nacionais)</li><li>Plano de chamadas domésticas e internacionais (3000 minutos nacionais)</li><li>Plano de chamadas domésticas e internacionais (minutos internacionais de 600)</li></ul></li><br><li>**Total de minutos** é o número total de minutos disponíveis para o mês.</li><li>**Minutos usados** é o número de minutos usados a cada mês</li> <li>**Minutos disponíveis** é o número de minutos restantes para o mês.</li><li>**Recurso** é a licença usada para a chamada. As licenças que você pode ver incluem:<ul><li>**MCOPSTNPP** -créditos de comunicações</li><li>**MCOPSTN1** -plano de chamadas domésticas (3000 min-US/1200 min) planos da UE)</li><li>**MCOPSTN2** -plano de chamadas internacionais</li><li>**MCOPSTN5** -plano de chamadas domésticas (120 min – plano de chamadas)</li><li>**MCOPSTN6** -plano de chamadas domésticas (240 min – plano de chamadas)</li><li>**MCOMEETADD** -audioconferência</li><li>**MCOMEETACPEA** -conferência de áudio de pagamento por minuto</li></ul></li> </ul> Para ver as informações desejadas na tabela, certifique-se de adicionar as colunas à tabela.|
|**6**   |Selecione **Editar colunas** para adicionar ou remover colunas na tabela.|
|**7**   |Selecione **tela inteira** para exibir o relatório em modo de tela inteira.|

## <a name="related-topics"></a>Tópicos relacionados

- [Análises e relatórios do Teams](teams-reporting-reference.md)