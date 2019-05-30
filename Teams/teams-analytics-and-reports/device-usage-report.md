---
title: Relatório de uso de dispositivos do Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 04/24/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Saiba como usar o relatório de uso de dispositivos do teams no centro de administração do Microsoft Teams para ver como os usuários em sua organização se conectam ao Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4d1e1137903dbda86a7ec3beedae32f13d1f27eb
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548721"
---
# <a name="microsoft-teams-device-usage-report"></a>Relatório de uso de dispositivos do Microsoft Teams

O relatório de uso de dispositivos do teams no centro de administração do Microsoft Teams fornece informações sobre como os usuários se conectam ao Teams. Você pode usar o relatório para ver os dispositivos que são usados em toda a sua organização, incluindo quantas usar equipes de seus dispositivos móveis quando estiverem em trânsito.  

![Captura de tela do relatório de uso de dispositivos do teams no centro de administração] (../media/teams-reports-device-usage.png "Captura de tela do relatório de uso de dispositivos do teams no centro de administração do Microsoft Teams")

## <a name="view-the-report"></a>Exibir o relatório

1. Vá para o centro de administração do Microsoft Teams, no painel de navegação esquerdo, clique em **relatórios do Analytics &** e, em seguida, em **relatório**, selecione **uso do dispositivo**do teams. 
2. Em **Intervalo de dados**, selecione intervalo e em seguida clique em **Executar relatório**. 

## <a name="interpret-the-report"></a>Interpretar relatório

![Captura de tela do relatório de uso de dispositivos do teams no centro de administração] (../media/teams-reports-device-usage-with-callouts.png "Captura de tela do relatório de uso de dispositivos do teams no centro de administração do Microsoft Teams com textos explicativos numerados")

|Texto explicativo |Descrição  |
|--------|-------------|
|**1**   |O relatório de uso de dispositivos do teams pode ser exibido para obter tendências nos últimos sete dias ou 28 dias.  |
|**2**   |Cada relatório tem uma data para quando o relatório foi gerado. O relatório geralmente reflete um período de latência de atividade de 24 a 48 horas. |
|**3**   |<ul><li>O eixo X no gráfico representa os diferentes dispositivos (**Windows**, **Mac**, **Ios**, **telefone Android**) usados para conexão com o Microsoft Teams. </li><li>O eixo Y é o número de usuários que usam o dispositivo durante o período de tempo selecionado.</li> </ul>Passe o mouse sobre a barra que representa um dispositivo para ver o número de usuários que estão usando o dispositivo para se conectar ao Microsoft Teams.|
|**4**   |A tabela oferece uma divisão do uso do dispositivo pelo usuário. <ul><li>**Nome para exibição** é o nome de exibição do usuário. Você pode clicar no nome para exibição para acessar a página de configuração do usuário no centro de administração do Microsoft Teams. </li><li>O **Windows** estará selecionado se o usuário estava ativo no cliente da área de trabalho do teams em um computador com Windows.</li><li>**Mac** estará selecionado se o usuário estava ativo no cliente da área de trabalho do teams em um computador MacOS. </li> <li>**Ios** estará selecionado se o usuário estava ativo no cliente móvel do teams para Ios.</li><li>**Telefone Android** estará selecionado se o usuário estava ativo no cliente do teams Mobile para Android. <li>**Última atividade** é a última data (UTC) que o usuário participou em uma atividade do teams.</li> </ul> Para ver as informações desejadas na tabela, certifique-se de adicionar as colunas à tabela. |
|**5**   |Selecione **Editar colunas** para adicionar ou remover colunas na tabela. |
|**6**   |Você pode exportar o relatório para um arquivo CSV para análise offline. Clique em **exportar para o Excel**e, na guia **downloads** , clique em **baixar** para baixar o relatório quando ele estiver pronto.<br>![Captura de tela da guia downloads mostrando relatórios exportados](../media/teams-reports-export-to-csv.png)|

## <a name="related-topics"></a>Tópicos relacionados
- [Análises e relatórios do Teams](teams-reporting-reference.md)
- [Relatório de uso do Teams](teams-usage-report.md)
- [Relatório de atividades do usuário do Teams](user-activity-report.md)