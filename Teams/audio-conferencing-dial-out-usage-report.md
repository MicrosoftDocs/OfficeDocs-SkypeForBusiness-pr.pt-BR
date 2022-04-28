---
title: Relatório de uso de discagem de audioconferência
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: fafan
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- LIL_Placement
description: Saiba quais países e regiões têm números de conferência discada e como eles são atribuídos automaticamente.
ms.openlocfilehash: 16cdae3a377d5ce87c218affc4944051f14f2631
ms.sourcegitcommit: 0967f725aad0a7b9c430b2e30a37ea333007558a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2022
ms.locfileid: "65106436"
---
# <a name="audio-conferencing-dial-out-usage-report"></a>Relatório de uso de discagem de audioconferência

O relatório de uso de discagem de Audioconferência no centro de administração do Teams fornece uma visão geral do uso e dos dólares gastos para o serviço de discagem de audioconferência. Esse relatório permite que os administradores consumam dados no nível do usuário em termos de créditos de comunicação gastos e minutos de discagem usados. Ele ajudará os administradores a determinar os créditos de comunicação futuros necessários a partir de qualquer ponto no tempo.

## <a name="view-the-audio-conferencing-dial-out-usage-report"></a>Exibir o relatório de uso de discagem de Audioconferência

No painel de navegação à esquerda do Microsoft Teams de administração,  **selecioneAnalytics &**  **reportsUsage** >. No  **reportstab doView** , em  **Relatório**, selecione o relatório de uso de **discagem de Audioconferência**.

No  **intervalo UnderDate**, você pode selecionar um intervalo predefinido de 7 ou 28 dias ou definir um intervalo personalizado.

 **UnderCountry Previsioned**, selecione um país preferencial ou selecione todos e, em seguida, selecione  **Executar relatório**.

## <a name="report-details"></a>Detalhes do relatório

O relatório de uso de discagem de Audioconferência tem três guias principais que exibirão informações em um formato de gráfico com base no intervalo selecionado nas listas suspensas acima dele:

- A **guia** Custo mostra os créditos de comunicação gastos durante o período selecionado e a tabela abaixo fornece detalhes de nível de usuário.
- A **guia Minutos de uso** mostra o total de minutos de discagem durante o período selecionado e a tabela abaixo forneceu detalhes de nível de usuário.
- A **guia Chamadas discada** mostra o número total de chamadas discada durante o período selecionado e a tabela abaixo fornece detalhes no nível do usuário.

Cada relatório tem uma data para quando ele foi gerado. Os relatórios geralmente refletem uma latência de 24 a 48 horas do tempo de atividade.

> [!NOTE]
> Todos os minutos de discagem/chamadas/crédito gastos serão contados no organizador da reunião. Não é necessariamente a mesma pessoa que ligou.

### <a name="cost-tab"></a>Guia Custo

Na parte superior desta seção de guia, há um gráfico exibindo uma linha que mostra informações de custo sobre o intervalo de datas e para o país ou países selecionados.

Há uma seção **Custo abaixo do** gráfico mostrando um preço, que é o custo total por minutos de chamadas dentro do intervalo de tempo selecionado.

### <a name="minutes-of-use-tab"></a>Guia Minutos de uso

Na parte superior desta seção de guia, há um gráfico exibindo uma linha que mostra minutos de uso no intervalo de datas e para o país ou países selecionados.

Há uma seção **Minutos de uso** abaixo do gráfico mostrando o total de minutos de chamadas usadas dentro do intervalo de tempo selecionado.

### <a name="dial-out-calls"></a>Chamadas discada

Na parte superior desta seção de guia está um gráfico exibindo uma linha que mostra chamadas discada sobre o intervalo de datas e para o país ou países selecionados.

Há uma seção **chamadas discada abaixo** do gráfico mostrando o número total de chamadas discada dentro do intervalo de tempo selecionado.

## <a name="using-the-report"></a>Usando o relatório

Na parte inferior da página está uma tabela, que mostra os detalhamentos no nível do usuário com os seguintes títulos:

- Organizador da reunião
- Username
- Minutos do usuário
- Crédito gasto
- Moeda

Se você precisar pesquisar o uso de um usuário específico, há uma barra de pesquisa à direita acima do relatório. Os nomes dos organizadores da reunião são todos hiperlinks selecionáveis que levarão você a um relatório de uso mais detalhado para o usuário. Essa exibição de usuário tem as mesmas três guias que o relatório principal, no entanto, o gráfico na parte superior da página mostrará detalhes para esse usuário específico.

Você pode exportar qualquer relatório mostrado nesta tabela para um arquivo CSV para análise offline. Selecione **Exportar para Excel** e, na guia **Downloads**, selecione **Baixar** para baixar o relatório quando ele estiver pronto.
