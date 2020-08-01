---
title: Relatório de uso de dispositivos do Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Saiba como usar o relatório de uso de dispositivos do teams no centro de administração do Microsoft Teams para ver como os usuários em sua organização se conectam ao Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dc36ccca5145bdfdd21e5b398954aec79cd12127
ms.sourcegitcommit: dc3e8ae454c42981f037f4de2e48005428b6078e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/31/2020
ms.locfileid: "46533858"
---
# <a name="microsoft-teams-device-usage-report"></a>Relatório de uso de dispositivos do Microsoft Teams

O relatório de uso de dispositivos do teams no centro de administração do Microsoft Teams fornece informações sobre como os usuários se conectam ao Teams. Você pode usar o relatório para ver os dispositivos que são usados em toda a sua organização, incluindo quantas usar equipes de seus dispositivos móveis quando estiverem em trânsito.  

## <a name="view-the-device-usage-report"></a>Exibir o relatório de uso do dispositivo

1. Na navegação à esquerda do centro de administração do Microsoft Teams, clique em **análises &** relatórios de  >  **uso**dos relatórios. Na guia **exibir relatórios** , em **relatório**, selecione **uso do dispositivo do teams**.
2. Em **Intervalo de dados**, selecione intervalo e em seguida clique em **Executar relatório**.

    ![Captura de tela do relatório de uso de dispositivos do teams no centro de administração do teams com textos explicativos](../media/teams-reports-device-usage-with-callouts.png "Captura de tela do relatório de uso de dispositivos do teams no centro de administração do teams com textos explicativos")

## <a name="interpret-the-report"></a>Interpretar relatório

|Texto Explicativo |Descrição  |
|--------|-------------|
|**1**   |O relatório de uso de dispositivos do teams pode ser exibido para obter tendências nos últimos sete dias ou 30 dias.  |
|**2**   |Cada relatório tem uma data para quando o relatório foi gerado. Os relatórios geralmente refletem uma latência de 24 horas do tempo de atividade. |
|**3**   |<ul><li>O eixo X no gráfico representa os diferentes dispositivos (**Windows**, **Mac**, **Linux**, **Ios**, **telefone Android**, **Web**) usados para se conectar ao Teams. </li><li>O eixo Y é o número de usuários que usam o dispositivo durante o período de tempo selecionado.</li> </ul>Passe o mouse sobre a barra que representa um dispositivo para ver o número de usuários que estão usando o dispositivo para se conectar ao Microsoft Teams.|
|**4**   |A tabela oferece uma divisão do uso do dispositivo pelo usuário. <ul><li>**Nome** de usuário é o nome de exibição do usuário. Você pode clicar no nome para exibição para acessar a página de configuração do usuário no centro de administração do Microsoft Teams. </li><li>O **Windows** estará selecionado se o usuário estava ativo no cliente da área de trabalho do teams em um computador com Windows.</li><li>**Mac** estará selecionado se o usuário estiver ativo no cliente de desktop do Teams em um computador com macOS. </li> <li>**Linux** estará selecionado se o usuário estava ativo no cliente da área de trabalho do teams em um computador Linux. </li> <li>**iOS** estará selecionado se o usuário estiver ativo no cliente do Mobile Teams para iOS.</li><li>**Telefone Android** estará selecionado se o usuário estava ativo no cliente do teams Mobile para Android. <li><li>**Web** estará selecionado se o usuário estiver ativo no cliente Web do Teams. <li>**Última atividade** é a última data (UTC) que o usuário participou em uma atividade do teams.</li> </ul> Observe que, se uma conta de usuário não existir mais no Azure AD, o nome de usuário será exibido como "--" na tabela. <br><br>Para ver as informações desejadas na tabela, certifique-se de adicionar as colunas à tabela. |
|**5**   |Selecione **Editar colunas** para adicionar ou remover colunas na tabela. |
|**6**   |Você pode exportar o relatório para um arquivo CSV para análise offline. Clique em **exportar para o Excel**e, na guia **downloads** , clique em **baixar** para baixar o relatório quando ele estiver pronto.<br><br>![Captura de tela da guia downloads mostrando relatórios exportados](../media/teams-reports-export-to-csv.png)|

## <a name="related-topics"></a>Tópicos relacionados

- [Análises e relatórios do Teams](teams-reporting-reference.md)
