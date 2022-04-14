---
title: Microsoft Teams de uso de Visitas Virtuais
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Saiba como usar o relatório de uso de Visitas Virtuais no centro de administração do Microsoft Teams para obter uma visão geral da atividade de compromisso virtual em sua organização.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 91f1aa8ff25b591305c8d5ca41485f7ceec9faca
ms.sourcegitcommit: 68162a8c9dee9a27af596353baabeda9b8fa64f3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2022
ms.locfileid: "64853212"
---
# <a name="microsoft-teams-virtual-visits-usage-report"></a>Microsoft Teams de uso de Visitas Virtuais

O relatório de uso de Visitas Virtuais no centro de administração Microsoft Teams oferece uma visão geral Teams atividade de compromisso virtual em sua organização. Você pode exibir a atividade detalhada para compromissos virtuais agendados por meio do aplicativo [Bookings](../expand-teams-across-your-org/bookings-virtual-visits.md) e do conector [Microsoft Teams EHR (Registro eletrônico de integridade](../expand-teams-across-your-org/healthcare/teams-in-hc.md#virtual-appointments-and-electronic-healthcare-record-ehr-integration)).

Para exibir o relatório, você deve ser um administrador global ou Teams administrador.

O relatório contém as guias a seguir. As informações que você verá no relatório dependem se você tem uma licença para o aplicativo Bookings, o conector Teams EHR ou ambos.

|Guia |Descrição  |
|---------|---------|
|**[Visitas virtuais](#virtual-visits)**     |Mostra o número total de compromissos virtuais, com um detalhamento do número de compromissos agendados usando o aplicativo Bookings e Teams reuniões integradas ao EHR realizadas do seu sistema EHR.         |
|**[Duração](#duration)**     |Mostra a duração média dos compromissos e o tempo médio de espera do lobby dos participantes.         |
|**[Bookings](#bookings)**     |Mostra o número de compromissos agendados por meio do Bookings aplicativo.         |
|**[EHR](#ehr)**     |Mostra o número de Teams compromissos integrados ao EHR realizados do sistema EHR.         |  

Use este relatório para obter informações sobre a atividade de compromisso virtual e as tendências em sua organização. As informações podem ajudá-lo a otimizar compromissos virtuais para fornecer melhores resultados de negócios.

## <a name="view-the-virtual-visits-usage-report"></a>Exibir o relatório de uso de Visitas Virtuais

1. Na navegação à esquerda do centro de administração Microsoft Teams, escolha **Relatórios & reportsUsage** >  **do Analytics**. Na guia **Exibir relatórios** , em **Relatório**, selecione **Uso de Visitas Virtuais**.
2. Em **Intervalo de datas**, selecione um intervalo de datas de 7 dias, 30 ou 90 dias. Em seguida, escolha **Executar relatório**.

> [!NOTE]
> Por padrão, a análise de Visitas Virtuais está ativada e o relatório está disponível. Ao usar esse relatório, você concede à Microsoft permissão para coletar dados sobre compromissos virtuais em sua organização. Para obter informações sobre nossas políticas de retenção de dados, consulte [Retenção, exclusão](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview) e destruição de dados Microsoft 365.
>
>Se você quiser desativar o relatório para sua organização, poderá fazer isso Configurações no canto superior  direito da página. Essa configuração pode levar entre 0 (zero) e 2 horas para entrar em vigor depois que você alterá-la.

## <a name="interpret-the-report"></a>Interpretar relatório

### <a name="virtual-visits"></a>Visitas virtuais

Os grafos que você verá aqui dependem se você tem uma licença para o aplicativo Bookings, o conector Teams EHR ou ambos. Para saber mais, confira [Gerenciar o aplicativo Bookings e](../bookings-app-admin.md) a integração com [o Cerner EHR](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md) ou [a Integração com o Epic EHR](../expand-teams-across-your-org/healthcare/ehr-admin.md).

:::image type="content" source="../media/virtual-visits-usage-report-virtual-visits.png" alt-text="Captura de tela da guia Visitas Virtuais do relatório de uso de Visitas Virtuais mostrando textos explicativo numerados." lightbox="../media/virtual-visits-usage-report-virtual-visits.png":::

|Texto Explicativo |Descrição  |
|--------|-------------|
|**1**   |Cada relatório tem uma data para quando o relatório foi gerado. Os relatórios geralmente refletem uma latência de 24 a 48 horas do tempo de atividade. |
|**2**   |O eixo X é o intervalo de datas selecionado para o relatório. O eixo Y é o número de compromissos.<br>Passe o mouse sobre o ponto em uma determinada data para ver o número de compromissos nessa data.|
|**3**   |Você pode filtrar o que vê no gráfico selecionando um item na legenda. Por exemplo, selecione **Total Bookings Virtual Visits** ou **Total EHR Virtual Visits** para ver apenas as informações relacionadas a cada uma. Ao alterar esta seleção, as informações da tabela não são alteradas. |
|**4**   |A tabela fornece informações detalhadas sobre cada compromisso que ocorreu durante o intervalo de datas selecionado. <ul><li>**A hora de início (UTC)** é a data e a hora em que um membro da equipe e um participante estão na reunião ou quando a primeira atividade ocorreu na reunião.  </li> <li>**A ID da** reunião é a ID exclusiva da reunião.</li> <li>**O tempo de espera** do lobby é o tempo entre quando um participante ingressa pela primeira vez no lobby quando esse mesmo participante ou um participante diferente é admitido na reunião por um membro da equipe.</li><li>**A** duração é a diferença de tempo entre a hora de início e quando a última pessoa sai da reunião. Se um membro da equipe e um participante não ingressaram na reunião, a duração será exibida como 0 (zero).</li> <li>**O status** mostra o status da reunião. <ul><li>**Concluído**: se um ou mais membros da equipe e participantes ingressarem na reunião e a reunião tiver terminado. Ou, se um ou mais participantes ingressarem na reunião e a reunião tiver terminado.</li> <li> **Não mostrar**: se um membro da equipe ingressar na reunião, mas nenhuma outra pessoa ingressar, e a reunião tiver terminado. </li></ul> </li> <li>**O tipo** de reunião indica se o compromisso virtual foi agendado por meio do aplicativo Bookings ou do Teams EHR.</li> <li>**Os participantes são** o número total de membros da equipe e participantes da reunião.</li> <li>**O SMS** enviado indica se uma notificação por SMS foi enviada aos participantes. </li> </li> </ul> |
|**5**   |Selecione **Configurações** para abrir o **painel de análise de Visitas** Virtuais. A partir daqui, você pode desativar ou ativar relatórios de Visitas Virtuais para sua organização e adicionar ou remover colunas na tabela. Para ver as informações desejadas na tabela, certifique-se de adicionar as colunas à tabela.|
|**6**   |Você pode exportar o relatório para um arquivo CSV para análise offline. Selecione **Exportar para Excel** e, na guia **Downloads**, escolha **Baixar** para baixar o relatório quando ele estiver pronto.|

### <a name="duration"></a>Duração

:::image type="content" source="../media/virtual-visits-usage-report-duration.png" alt-text="Captura de tela da guia Duração do relatório de uso de Visitas Virtuais mostrando textos explicativo numerados." lightbox="../media/virtual-visits-usage-report-duration.png":::

|Texto Explicativo |Descrição  |
|--------|-------------|
|**1**   |Cada relatório tem uma data para quando o relatório foi gerado. Os relatórios geralmente refletem uma latência de 24 a 48 horas do tempo de atividade. |
|**2**   |O eixo X é o intervalo de datas selecionado para o relatório. O eixo Y é o número de minutos.<br>Passe o mouse sobre o ponto em uma determinada data para ver a duração média do compromisso ou o tempo médio de espera do lobby para uma determinada data.  |
|**3**   |Você pode filtrar o que vê no gráfico selecionando um item na legenda. Por exemplo, selecione **Duração Média da Visita Virtual** ou **Tempo médio** de espera do lobby para ver apenas as informações relacionadas a cada uma delas. Ao alterar esta seleção, as informações da tabela não são alteradas. |
|**4**   |A tabela fornece informações detalhadas sobre cada compromisso que ocorreu durante o intervalo de datas selecionado. <ul><li>**A hora de início (UTC)** é a data e a hora em que um membro da equipe e um participante estão na reunião ou quando a primeira atividade ocorreu na reunião.  </li> <li>**A ID da** reunião é a ID exclusiva da reunião.</li> <li>**O tempo de espera** do lobby é o tempo entre quando um participante ingressa pela primeira vez no lobby quando esse mesmo participante ou um participante diferente é admitido na reunião por um membro da equipe.</li><li>**A** duração é a diferença de tempo entre a hora de início e quando a última pessoa sai da reunião. Se um membro da equipe e um participante não ingressaram na reunião, a duração será exibida como 0 (zero).</li> <li>**O status** mostra o status da reunião. <ul><li>**Concluído**: se um ou mais membros da equipe e participantes ingressarem na reunião e a reunião tiver terminado. Ou, se um ou mais participantes ingressarem na reunião e a reunião tiver terminado.</li> <li> **Não mostrar**: se um membro da equipe ingressar na reunião, mas nenhuma outra pessoa ingressar, e a reunião tiver terminado. </li></ul> </li> <li>**O tipo** de reunião indica se o compromisso virtual foi agendado por meio do aplicativo Bookings ou do Teams EHR.</li> <li>**Os participantes são** o número total de membros da equipe e participantes da reunião.</li> <li>**O SMS** enviado indica se uma notificação por SMS foi enviada aos participantes. </li> </li> </ul>|
|**5**   |Selecione **Configurações** para abrir o **painel de análise de Visitas** Virtuais. A partir daqui, você pode desativar ou ativar relatórios de Visitas Virtuais para sua organização e adicionar ou remover colunas na tabela. Para ver as informações desejadas na tabela, certifique-se de adicionar as colunas à tabela.|
|**6**   |Você pode exportar o relatório para um arquivo CSV para análise offline. Selecione **Exportar para Excel** e, na guia **Downloads**, escolha **Baixar** para baixar o relatório quando ele estiver pronto.|
### <a name="bookings"></a>Bookings

Você verá essa guia se tiver uma licença que inclua o Bookings aplicativo. Para saber mais, confira [Gerenciar o Bookings aplicativo](../bookings-app-admin.md).

:::image type="content" source="../media/virtual-visits-usage-report-bookings.png" alt-text="Captura de tela da Bookings do relatório de uso de Visitas Virtuais mostrando textos explicativo numerados." lightbox="../media/virtual-visits-usage-report-bookings.png":::

|Texto Explicativo |Descrição  |
|--------|-------------|
|**1**   |Cada relatório tem uma data para quando o relatório foi gerado. Os relatórios geralmente refletem uma latência de 24 a 48 horas do tempo de atividade. |
|**2**   |O eixo X é o intervalo de datas selecionado para o relatório. O eixo Y é o número de Bookings compromissos.<br>Passe o mouse sobre o ponto em uma determinada data para ver o número Bookings compromissos que ocorreram nessa data.|
|**3**   |A tabela fornece informações detalhadas sobre cada compromisso que ocorreu durante o intervalo de datas selecionado. <ul><li>**A hora de início (UTC)** é a data e a hora em que um membro da equipe e um participante estão na reunião ou quando a primeira atividade ocorreu na reunião.  </li> <li>**A ID da** reunião é a ID exclusiva da reunião.</li> <li>**O tempo de espera** do lobby é o tempo entre quando um participante ingressa pela primeira vez no lobby quando esse mesmo participante ou um participante diferente é admitido na reunião por um membro da equipe.</li><li>**A** duração é a diferença de tempo entre a hora de início e quando a última pessoa sai da reunião. Se um membro da equipe e um participante não ingressaram na reunião, a duração será exibida como 0 (zero).</li> <li>**O status** mostra o status da reunião. <ul><li>**Concluído**: se um ou mais membros da equipe e participantes ingressarem na reunião e a reunião tiver terminado. Ou, se um ou mais participantes ingressarem na reunião e a reunião tiver terminado.</li> <li> **Não mostrar**: se um membro da equipe ingressar na reunião, mas nenhuma outra pessoa ingressar, e a reunião tiver terminado. </li></ul> </li> <li>**O tipo** de reunião indica se o compromisso virtual foi agendado por meio do aplicativo Bookings ou do Teams EHR.</li> <li>**Os participantes são** o número total de membros da equipe e participantes da reunião.</li> <li>**O SMS** enviado indica se uma notificação por SMS foi enviada aos participantes. </li> </li> </ul>|
|**4**   |Selecione **Configurações** para abrir o **painel de análise de Visitas** Virtuais. A partir daqui, você pode desativar ou ativar relatórios de Visitas Virtuais para sua organização e adicionar ou remover colunas na tabela. Para ver as informações desejadas na tabela, certifique-se de adicionar as colunas à tabela.|
|**5**   |Você pode exportar o relatório para um arquivo CSV para análise offline. Selecione **Exportar para Excel** e, na guia **Downloads**, escolha **Baixar** para baixar o relatório quando ele estiver pronto.|
### <a name="ehr"></a>EHR

Você verá essa guia se tiver uma licença que inclua o conector Teams EHR. Para saber mais, confira [Integração com o Cerner EHR ou](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md) [a Integração com o Epic EHR](../expand-teams-across-your-org/healthcare/ehr-admin.md).

:::image type="content" source="../media/virtual-visits-usage-report-ehr.png" alt-text="Captura de tela da guia EHR do relatório de uso de Visitas Virtuais mostrando textos explicativo numerados." lightbox="../media/virtual-visits-usage-report-ehr.png":::

|Texto Explicativo |Descrição  |
|--------|-------------|
|**1**   |Cada relatório tem uma data para quando o relatório foi gerado. Os relatórios geralmente refletem uma latência de 24 a 48 horas do tempo de atividade. |
|**2**   |O eixo X é o intervalo de datas selecionado para o relatório. O eixo Y é o número de compromissos EHR.<br>Passe o mouse sobre o ponto em uma determinada data para ver o número de compromissos EHR nessa data.|
|**3**   |A tabela fornece informações detalhadas sobre cada compromisso que ocorreu durante o intervalo de datas selecionado. <ul><li>**A hora de início (UTC)** é a data e a hora em que um membro da equipe e um participante estão na reunião ou quando a primeira atividade ocorreu na reunião.  </li> <li>**A ID da** reunião é a ID exclusiva da reunião.</li> <li>**O tempo de espera** do lobby é o tempo entre quando um participante ingressa pela primeira vez no lobby quando esse mesmo participante ou um participante diferente é admitido na reunião por um membro da equipe.</li><li>**A** duração é a diferença de tempo entre a hora de início e quando a última pessoa sai da reunião. Se um membro da equipe e um participante não ingressaram na reunião, a duração será exibida como 0 (zero).</li> <li>**O status** mostra o status da reunião. <ul><li>**Concluído**: se um ou mais membros da equipe e participantes ingressarem na reunião e a reunião tiver terminado. Ou, se um ou mais participantes ingressarem na reunião e a reunião tiver terminado.</li> <li> **Não mostrar**: se um membro da equipe ingressar na reunião, mas nenhuma outra pessoa ingressar, e a reunião tiver terminado. </li></ul> </li> <li>**O tipo** de reunião indica se o compromisso virtual foi agendado por meio do aplicativo Bookings ou do Teams EHR.</li> <li>**Os participantes são** o número total de membros da equipe e participantes da reunião.</li> <li>**O SMS** enviado indica se uma notificação por SMS foi enviada aos participantes. </li> </li> </ul>|
|**4**   |Selecione **Configurações** para abrir o **painel de análise de Visitas** Virtuais. A partir daqui, você pode desativar ou ativar relatórios de Visitas Virtuais para sua organização e adicionar ou remover colunas na tabela. Para ver as informações desejadas na tabela, certifique-se de adicionar as colunas à tabela.|
|**5**   |Você pode exportar o relatório para um arquivo CSV para análise offline. Selecione **Exportar para Excel** e, na guia **Downloads**, escolha **Baixar** para baixar o relatório quando ele estiver pronto.|

> [!NOTE]
> Se sua organização quiser participar de uma visualização privada para que usuários não administradores, como tomadores de decisão de negócios, tenham acesso e exibam esse relatório, [entre em contato conosco](mailto:tapmwtanalytics@microsoft.com).

## <a name="related-articles"></a>Artigos relacionados

- [Análises e relatórios do Teams](teams-reporting-reference.md)
- [Compromissos virtuais com Teams e o Bookings aplicativo](../expand-teams-across-your-org/bookings-virtual-visits.md)
- [Compromissos virtuais com o Teams – Integração ao Epic EHR](../expand-teams-across-your-org/healthcare/ehr-admin.md)
- [Compromissos virtuais com o Teams – Integração ao Cerner EHR](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md)
