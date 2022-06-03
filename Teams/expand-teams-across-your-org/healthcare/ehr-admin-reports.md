---
title: Relatório de Compromissos Virtuais do conector EHR do Microsoft Teams
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Saiba como usar o relatório compromissos virtuais do conector EHR do Teams no centro de administração do Microsoft Teams para obter uma visão geral do uso de compromissos virtuais integrados ao EHR em sua organização.
ms.openlocfilehash: 0e78b89c934eac101b863bd7b5ba9957939f994b
ms.sourcegitcommit: cf2f2d23e6dcda0c03f22a5800a210a1c88e583f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "65883534"
---
# <a name="microsoft-teams-ehr-connector-virtual-appointments-report"></a>Relatório de Compromissos Virtuais do conector EHR do Microsoft Teams

O relatório de Compromissos Virtuais do conector EHR (Registro Eletrônico de Integridade) do Microsoft Teams no Centro de administração do Microsoft Teams oferece uma maneira rápida e fácil de exibir o uso de compromissos virtuais integrados ao EHR do Teams em sua organização.

Para exibir o relatório, você deve ser um administrador global, administrador do Teams, leitor global ou leitor de relatórios.

## <a name="view-the-report"></a>Exibir o relatório

Há duas maneiras de acessar e exibir o relatório no centro de administração do Teams.

- Por meio [do cartão de uso do conector EHR](#the-ehr-connector-usage-card) no painel
- Diretamente escolhendo [**compromissos virtuais do conector EHR**](#the-teams-ehr-connector-virtual-appointments-report) no **Analytics & relatórios** > **de uso**

### <a name="the-ehr-connector-usage-card"></a>O cartão de uso do conector EHR

No painel de navegação esquerdo do Centro de administração do Microsoft Teams, escolha **Painel** e, em seguida, vá para o cartão **compromissos virtuais do conector EHR** .

Aqui, você obtém uma visão geral da atividade de compromisso virtual integrada ao Teams EHR por mês, incluindo compromissos concluídos, alocação restante e se você excedeu o limite mensal (dependendo da licença que você tem).

:::image type="content" source="../../media/ehr-connector-report-card.png" alt-text="Captura de tela do cartão de uso do conector EHR no painel do Centro de administração do Teams." lightbox="../../media/ehr-connector-report-card.png":::

Escolha **Exibir detalhes para** ver os detalhes do relatório. Para comprar mais licenças, escolha **Comprar mais**.

### <a name="the-teams-ehr-connector-virtual-appointments-report"></a>O relatório compromissos virtuais do conector do EHR do Teams

1. No painel de navegação esquerdo do Centro de administração do Teams, vá para **Análise & relatórios** > **de uso**.
1. Na guia **Exibir relatórios** , escolha **Compromissos Virtuais do conector EHR** e um intervalo de datas. Em seguida, selecione **Executar relatório**.

    :::image type="content" source="../../media/ehr-connector-report.png" alt-text="Captura de tela do relatório compromissos virtuais do conector EHR do Teams no centro de administração do Teams." lightbox="../../media/ehr-connector-report.png":::

#### <a name="interpret-the-report"></a>Interpretar relatório

|Texto Explicativo |Descrição  |
|--------|-------------|
|**1**   |Cada relatório mostra a data de quando o relatório foi gerado e o intervalo de datas escolhido.|
|**2**   |A tabela fornece informações detalhadas sobre cada compromisso que ocorreu durante o intervalo de datas selecionado. Lembre-se de que você não verá entradas para compromissos nos quais um membro da equipe ou um paciente não ingressou. <ul><li>**A hora de início (UTC)** é a data e a hora em que um membro da equipe e um participante estão no compromisso.  </li> <li>**Duração** é a diferença de tempo entre a hora de início e quando a última pessoa sai do compromisso.</li> <li>**O** principal é o nome do organizador da reunião. <li>**O email principal é** o endereço de email do organizador da reunião.</li> <li> **Departamento** é a informação do departamento para o compromisso. Se as informações não são exibidas corretamente, entre em contato com a equipe de suporte do EHR. Para integração com a Epic, certifique-se ```&departmentId=%PERFDEPID;;; ; ;;NONE;%``` de fazer parte do registro de integração do provedor. </li></li> <li>**Atendedores** é o número total de membros e participantes da equipe no compromisso.</li> <li>**Dentro do** limite indica se o compromisso está dentro do limite de alocação. </li> </ul> |
|**3**   |Você pode exportar o relatório para um arquivo CSV para análise offline. Selecione **Exportar para Excel** para baixar o relatório. |
|**4**   |Selecione **Filtrar** para filtrar a exibição de detalhes do relatório. |
|**5**   |Selecione **Tela inteira** para exibir o relatório no modo de tela inteira. |
|**6**   |Selecione **Editar colunas** para adicionar ou remover colunas na tabela |

> [!NOTE]
> Para obter mais análises sobre compromissos virtuais integrados ao Teams EHR, consulte [o relatório de uso de Visitas Virtuais](../../teams-analytics-and-reports/virtual-visits-usage-report.md). Com o relatório de uso de Visitas Virtuais, você pode exibir as principais métricas, como total de compromissos, tempo de espera do lobby, duração do compromisso e nenhum evento. Use essas informações para obter informações sobre tendências de uso para ajudá-lo a otimizar compromissos virtuais para fornecer melhores resultados de negócios.

## <a name="related-articles"></a>Artigos relacionados

- [Compromissos virtuais com o Teams – Integração ao Cerner EHR](ehr-admin-cerner.md)
- [Compromissos virtuais com o Teams – Integração ao Epic EHR](ehr-admin.md) 
