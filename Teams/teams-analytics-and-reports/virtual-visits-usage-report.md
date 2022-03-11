---
title: Microsoft Teams relatório de uso de Visitas Virtuais
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
description: Saiba como usar o relatório de uso de Visitas Virtuais no centro de administração Microsoft Teams para obter uma visão geral da atividade de Visitas Virtuais em sua organização.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2b3432ea92ad89c5304d81b266fce61fb9b95d5b
ms.sourcegitcommit: ff975c21725e1812e6db8fc9fe37de1362f168c3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/11/2022
ms.locfileid: "63435845"
---
# <a name="microsoft-teams-virtual-visits-usage-report"></a>Microsoft Teams relatório de uso de Visitas Virtuais

O relatório de uso de Visitas Virtuais no centro de administração Microsoft Teams oferece uma visão geral Teams atividade de Visitas Virtuais em sua organização. Você pode exibir atividades detalhadas para compromissos virtuais agendados por meio do aplicativo [Bookings](../expand-teams-across-your-org/bookings-virtual-visits.md) e do [conector EHR (Registro](../expand-teams-across-your-org/healthcare/teams-in-hc.md#virtual-visits-and-electronic-healthcare-record-ehr-integration) Eletrônico de Saúde) do Microsoft Teams.

Para exibir o relatório, você deve ser um administrador global ou Teams administrador.

O relatório contém as guias a seguir. As informações que você verá no relatório dependem se você tem uma licença para o aplicativo Bookings, o conector Teams EHR ou ambos.

|Guia |Descrição  |
|---------|---------|
|**[Visitas virtuais](#virtual-visits)**     |Mostra o número total de Visitas Virtuais, com uma divisão do número de visitas agendadas usando o aplicativo Bookings e Teams reuniões integradas ao EHR conduzidas a partir do seu sistema EHR.         |
|**[Duração](#duration)**     |Mostra a duração média das visitas e o tempo médio de espera do lobby dos participantes.         |
|**[Bookings](#bookings)**     |Mostra o número de visitas agendadas por meio do aplicativo Bookings.         |
|**[EHR](#ehr)**     |Mostra o número de Teams de visitas integradas ao EHR conduzidas a partir do sistema EHR.         |  

Use este relatório para obter informações sobre as atividades e tendências de Visitas Virtuais em sua organização. As informações podem ajudá-lo a otimizar as Visitas Virtuais para oferecer melhores resultados comerciais.

## <a name="view-the-virtual-visits-usage-report"></a>Exibir o relatório de uso de Visitas Virtuais

1. Na navegação à esquerda do centro de administração Microsoft Teams, escolha **Análise & relatóriosusuário** > . Na guia **Exibir relatórios** , em **Relatório**, selecione **Uso de Visitas Virtuais**.
2. Em **Intervalo de datas**, selecione um intervalo de 7 dias, 30 ou 90 dias. Em seguida, escolha **Executar relatório**.

> [!NOTE]
> Por padrão, a análise de Visitas Virtuais está em e o relatório está disponível. Ao usar este relatório, você dá permissão à Microsoft para coletar dados sobre Visitas Virtuais em sua organização. Para obter informações sobre nossas políticas de retenção de dados, consulte [Retenção, exclusão](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview) e destruição de dados Microsoft 365.
>
>Se você quiser desativar o relatório para sua organização, você pode fazer isso Configurações no canto  superior direito da página. Essa configuração pode levar entre 0 (zero) e 2 horas para ter efeito depois de alterá-la.

## <a name="interpret-the-report"></a>Interpretar relatório

### <a name="virtual-visits"></a>Visitas virtuais

Os gráficos que você verá aqui dependem se você tem uma licença para o aplicativo Bookings, o conector Teams EHR ou ambos. Para saber mais, consulte [Manage the Bookings app](../bookings-app-admin.md), and [Integration into Cerner EHR](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md) or [Integration into Épico EHR](../expand-teams-across-your-org/healthcare/ehr-admin.md).

:::image type="content" source="../media/virtual-visits-usage-report-virtual-visits.png" alt-text="Captura de tela da guia Visitas Virtuais do relatório de uso de Visitas Virtuais mostrando explicações numeradas." lightbox="../media/virtual-visits-usage-report-virtual-visits.png":::

|Texto Explicativo |Descrição  |
|--------|-------------|
|**1**   |Cada relatório tem uma data para quando o relatório foi gerado. Os relatórios geralmente refletem uma latência de 24 a 48 horas do tempo de atividade. |
|**2**   |O eixo X é o intervalo de datas selecionado para o relatório. O eixo Y é o número de visitas.<br>Passe o mouse sobre o ponto em uma determinada data para ver o número de visitas nessa data.|
|**3**   |Você pode filtrar o que você vê no gráfico selecionando um item na legenda. Por exemplo, selecione **Total de Visitas Virtuais** de Reservas ou **Total de Visitas Virtuais do EHR** para ver apenas as informações relacionadas a cada uma delas. Ao alterar esta seleção, as informações da tabela não são alteradas. |
|**4**   |A tabela fornece informações detalhadas sobre cada visita que ocorreu durante o intervalo de datas selecionado. <ul><li>**A hora de início (UTC)** é a data e a hora em que um membro da equipe e um participante estão na reunião ou quando a primeira atividade ocorreu na reunião.  </li> <li>**A ID da** reunião é a ID exclusiva da reunião.</li> <li>**O tempo de espera** do lobby é o tempo entre quando um participante entra pela primeira vez no lobby quando esse mesmo participante ou um participante diferente é admitido na reunião por um membro da equipe.</li><li>**Duração** é a diferença de tempo entre a hora de início e quando a última pessoa sai da reunião. Se um membro da equipe e um participante não ingressarem na reunião, a duração será 0 (zero).</li> <li>**Status** mostra o status da reunião. <ul><li>**Concluído**: se um ou mais membros da equipe e participantes ingressarem na reunião e a reunião for encerrada. Ou, se um ou mais participantes ingressarem na reunião e a reunião tiver terminado.</li> <li> **Nenhum show**: se um membro da equipe ingressar na reunião, mas nenhuma outra pessoa participar, e a reunião tiver terminado. </li></ul> </li> <li>**O tipo de** reunião indica se o compromisso virtual foi agendado por meio do aplicativo Bookings ou do conector Teams EHR.</li> <li>**Os participantes são** o número total de membros e participantes da reunião.</li> <li>**O SMS** enviado indica se uma notificação de SMS foi enviada aos participantes. </li> </li> </ul> |
|**5**   |Selecione **Configurações** abrir o painel de análise **de Visitas** Virtuais. A partir daqui, você pode desativar ou ativar o relatório de Visitas Virtuais para sua organização e adicionar ou remover colunas na tabela. Para ver as informações desejadas na tabela, certifique-se de adicionar as colunas à tabela.|
|**6**   |Você pode exportar o relatório para um arquivo CSV para análise offline. Selecione **Exportar para Excel** e, na guia **Downloads**, escolha **Baixar** para baixar o relatório quando estiver pronto.|

### <a name="duration"></a>Duração

:::image type="content" source="../media/virtual-visits-usage-report-duration.png" alt-text="Captura de tela da guia Duração do relatório de uso de Visitas Virtuais mostrando explicações numeradas." lightbox="../media/virtual-visits-usage-report-duration.png":::

|Texto Explicativo |Descrição  |
|--------|-------------|
|**1**   |Cada relatório tem uma data para quando o relatório foi gerado. Os relatórios geralmente refletem uma latência de 24 a 48 horas do tempo de atividade. |
|**2**   |O eixo X é o intervalo de datas selecionado para o relatório. O eixo Y é o número de minutos.<br>Passe o mouse sobre o ponto em uma determinada data para ver a duração média da visita ou o tempo médio de espera do lobby para uma determinada data.  |
|**3**   |Você pode filtrar o que você vê no gráfico selecionando um item na legenda. Por exemplo, selecione **Duração média da Visita Virtual** ou Tempo médio de espera do **lobby** para ver apenas as informações relacionadas a cada uma delas. Ao alterar esta seleção, as informações da tabela não são alteradas. |
|**4**   |A tabela fornece informações detalhadas sobre cada visita que ocorreu durante o intervalo de datas selecionado. <ul><li>**A hora de início (UTC)** é a data e a hora em que um membro da equipe e um participante estão na reunião ou quando a primeira atividade ocorreu na reunião.  </li> <li>**A ID da** reunião é a ID exclusiva da reunião.</li> <li>**O tempo de espera** do lobby é o tempo entre quando um participante entra pela primeira vez no lobby quando esse mesmo participante ou um participante diferente é admitido na reunião por um membro da equipe.</li><li>**Duração** é a diferença de tempo entre a hora de início e quando a última pessoa sai da reunião. Se um membro da equipe e um participante não ingressarem na reunião, a duração será 0 (zero).</li> <li>**Status** mostra o status da reunião. <ul><li>**Concluído**: se um ou mais membros da equipe e participantes ingressarem na reunião e a reunião for encerrada. Ou, se um ou mais participantes ingressarem na reunião e a reunião tiver terminado.</li> <li> **Nenhum show**: se um membro da equipe ingressar na reunião, mas nenhuma outra pessoa participar, e a reunião tiver terminado. </li></ul> </li> <li>**O tipo de** reunião indica se o compromisso virtual foi agendado por meio do aplicativo Bookings ou do conector Teams EHR.</li> <li>**Os participantes são** o número total de membros e participantes da reunião.</li> <li>**O SMS** enviado indica se uma notificação de SMS foi enviada aos participantes. </li> </li> </ul>|
|**5**   |Selecione **Configurações** abrir o painel de análise **de Visitas** Virtuais. A partir daqui, você pode desativar ou ativar o relatório de Visitas Virtuais para sua organização e adicionar ou remover colunas na tabela. Para ver as informações desejadas na tabela, certifique-se de adicionar as colunas à tabela.|
|**6**   |Você pode exportar o relatório para um arquivo CSV para análise offline. Selecione **Exportar para Excel** e, na guia **Downloads**, escolha **Baixar** para baixar o relatório quando estiver pronto.|
### <a name="bookings"></a>Bookings

Você verá essa guia se tiver uma licença que inclua o aplicativo Bookings. Para saber mais, confira [Gerenciar o aplicativo Bookings](../bookings-app-admin.md).

:::image type="content" source="../media/virtual-visits-usage-report-bookings.png" alt-text="Captura de tela da guia Reservas do relatório de uso de Visitas Virtuais mostrando explicações numeradas." lightbox="../media/virtual-visits-usage-report-bookings.png":::

|Texto Explicativo |Descrição  |
|--------|-------------|
|**1**   |Cada relatório tem uma data para quando o relatório foi gerado. Os relatórios geralmente refletem uma latência de 24 a 48 horas do tempo de atividade. |
|**2**   |O eixo X é o intervalo de datas selecionado para o relatório. O eixo Y é o número de visitas do Bookings.<br>Passe o mouse sobre o ponto em uma determinada data para ver o número de visitas do Bookings que ocorreram nessa data.|
|**3**   |A tabela fornece informações detalhadas sobre cada visita que ocorreu durante o intervalo de datas selecionado. <ul><li>**A hora de início (UTC)** é a data e a hora em que um membro da equipe e um participante estão na reunião ou quando a primeira atividade ocorreu na reunião.  </li> <li>**A ID da** reunião é a ID exclusiva da reunião.</li> <li>**O tempo de espera** do lobby é o tempo entre quando um participante entra pela primeira vez no lobby quando esse mesmo participante ou um participante diferente é admitido na reunião por um membro da equipe.</li><li>**Duração** é a diferença de tempo entre a hora de início e quando a última pessoa sai da reunião. Se um membro da equipe e um participante não ingressarem na reunião, a duração será 0 (zero).</li> <li>**Status** mostra o status da reunião. <ul><li>**Concluído**: se um ou mais membros da equipe e participantes ingressarem na reunião e a reunião for encerrada. Ou, se um ou mais participantes ingressarem na reunião e a reunião tiver terminado.</li> <li> **Nenhum show**: se um membro da equipe ingressar na reunião, mas nenhuma outra pessoa participar, e a reunião tiver terminado. </li></ul> </li> <li>**O tipo de** reunião indica se o compromisso virtual foi agendado por meio do aplicativo Bookings ou do conector Teams EHR.</li> <li>**Os participantes são** o número total de membros e participantes da reunião.</li> <li>**O SMS** enviado indica se uma notificação de SMS foi enviada aos participantes. </li> </li> </ul>|
|**4**   |Selecione **Configurações** abrir o painel de análise **de Visitas** Virtuais. A partir daqui, você pode desativar ou ativar o relatório de Visitas Virtuais para sua organização e adicionar ou remover colunas na tabela. Para ver as informações desejadas na tabela, certifique-se de adicionar as colunas à tabela.|
|**5**   |Você pode exportar o relatório para um arquivo CSV para análise offline. Selecione **Exportar para Excel** e, na guia **Downloads**, escolha **Baixar** para baixar o relatório quando estiver pronto.|
### <a name="ehr"></a>EHR

Você verá essa guia se tiver uma licença que inclua o conector Teams EHR. Para saber mais, consulte [Integration into Cerner EHR](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md) or [Integration into Épico EHR](../expand-teams-across-your-org/healthcare/ehr-admin.md).

:::image type="content" source="../media/virtual-visits-usage-report-ehr.png" alt-text="Captura de tela da guia EHR do relatório de uso de Visitas Virtuais mostrando explicações numeradas." lightbox="../media/virtual-visits-usage-report-ehr.png":::

|Texto Explicativo |Descrição  |
|--------|-------------|
|**1**   |Cada relatório tem uma data para quando o relatório foi gerado. Os relatórios geralmente refletem uma latência de 24 a 48 horas do tempo de atividade. |
|**2**   |O eixo X é o intervalo de datas selecionado para o relatório. O eixo Y é o número de visitas de EHR.<br>Passe o mouse sobre o ponto em uma determinada data para ver o número de visitas do EHR nessa data.|
|**3**   |A tabela fornece informações detalhadas sobre cada visita que ocorreu durante o intervalo de datas selecionado. <ul><li>**A hora de início (UTC)** é a data e a hora em que um membro da equipe e um participante estão na reunião ou quando a primeira atividade ocorreu na reunião.  </li> <li>**A ID da** reunião é a ID exclusiva da reunião.</li> <li>**O tempo de espera** do lobby é o tempo entre quando um participante entra pela primeira vez no lobby quando esse mesmo participante ou um participante diferente é admitido na reunião por um membro da equipe.</li><li>**Duração** é a diferença de tempo entre a hora de início e quando a última pessoa sai da reunião. Se um membro da equipe e um participante não ingressarem na reunião, a duração será 0 (zero).</li> <li>**Status** mostra o status da reunião. <ul><li>**Concluído**: se um ou mais membros da equipe e participantes ingressarem na reunião e a reunião for encerrada. Ou, se um ou mais participantes ingressarem na reunião e a reunião tiver terminado.</li> <li> **Nenhum show**: se um membro da equipe ingressar na reunião, mas nenhuma outra pessoa participar, e a reunião tiver terminado. </li></ul> </li> <li>**O tipo de** reunião indica se o compromisso virtual foi agendado por meio do aplicativo Bookings ou do conector Teams EHR.</li> <li>**Os participantes são** o número total de membros e participantes da reunião.</li> <li>**O SMS** enviado indica se uma notificação de SMS foi enviada aos participantes. </li> </li> </ul>|
|**4**   |Selecione **Configurações** abrir o painel de análise **de Visitas** Virtuais. A partir daqui, você pode desativar ou ativar o relatório de Visitas Virtuais para sua organização e adicionar ou remover colunas na tabela. Para ver as informações desejadas na tabela, certifique-se de adicionar as colunas à tabela.|
|**5**   |Você pode exportar o relatório para um arquivo CSV para análise offline. Selecione **Exportar para Excel** e, na guia **Downloads**, escolha **Baixar** para baixar o relatório quando estiver pronto.|

> [!NOTE]
> Se sua organização quiser participar da visualização privada para usuários que não são administradores, como os tomadores de decisão de negócios, tenham acesso e visualizem esse relatório, entre em [contato conosco](mailto:tapmwtanalytics@microsoft.com).

## <a name="related-articles"></a>Artigos relacionados

- [Análises e relatórios do Teams](teams-reporting-reference.md)
- [Visitas virtuais com Teams e o aplicativo Bookings](../expand-teams-across-your-org/bookings-virtual-visits.md)
- [Visitas virtuais com Teams - Integração ao EHR Épico](../expand-teams-across-your-org/healthcare/ehr-admin.md)
- [Visitas virtuais com Teams - Integração ao Cerner EHR](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md)
