---
title: Relatório de uso de dispositivos do Microsoft Teams
author: cichur
ms.author: v-cichur
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
description: Saiba como usar o relatório de uso de dispositivos do Teams no Centro de administração do Microsoft Teams para ver como os usuários em sua organização se conectam ao Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 292632972396f5d4300fa2526f01e69a5555ff45
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815641"
---
# <a name="microsoft-teams-device-usage-report"></a>Relatório de uso de dispositivos do Microsoft Teams

O relatório de uso de dispositivos do Teams no Centro de administração do Microsoft Teams fornece informações sobre como os usuários se conectam ao Teams. Você pode usar o relatório para ver os dispositivos usados em sua organização, incluindo quantos usam o Teams em seus dispositivos móveis quando estiver em qualquer lugar.  

## <a name="view-the-device-usage-report"></a>Exibir o relatório de uso do dispositivo

1. Na navegação à esquerda do Centro de administração do Microsoft Teams, clique em **Análise & relatórios**  >  **uso.** Na guia **Exibir relatórios,** em **Relatório,** selecione **Uso de dispositivo do Teams.**
2. Em **Intervalo de dados**, selecione intervalo e em seguida clique em **Executar relatório**.

    ![Captura de tela do relatório de uso de dispositivos do Teams no Centro de administração do Teams com os recursos de chamada](../media/teams-reports-device-usage-with-callouts.png "Captura de tela do relatório de uso de dispositivos do Teams no Centro de administração do Teams com os recursos de chamada")

## <a name="interpret-the-report"></a>Interpretar relatório

|Texto Explicativo |Descrição  |
|--------|-------------|
|**1**   |O relatório de uso de dispositivos do Teams pode ser consultado sobre tendências dos últimos 7 ou 30 dias.  |
|**2**   |Cada relatório tem uma data para quando o relatório foi gerado. Os relatórios geralmente refletem uma latência de 24 horas do tempo de atividade. |
|**3**   |<ul><li>O eixo X no gráfico representa os diferentes dispositivos **(Windows,** **Mac,** **Linux,** **iOS,** **Telefone Android,** **Web)** usados para se conectar ao Teams. </li><li>O eixo Y é o número de usuários que usam o dispositivo durante o período de tempo selecionado.</li> </ul>Passe o mouse sobre a barra que representa um dispositivo para ver o número de usuários que usam o dispositivo para se conectar ao Teams.|
|**4**   |A tabela fornece uma divisão do uso do dispositivo pelo usuário. <ul><li>**Nome de** usuário é o nome de exibição do usuário. Você pode clicar no nome de exibição para ir para a página de configuração do usuário no Centro de administração do Microsoft Teams. </li><li>**O Windows** é selecionado se o usuário estava ativo no cliente de área de trabalho do Teams em um computador baseado no Windows.</li><li>**Mac** estará selecionado se o usuário estiver ativo no cliente de desktop do Teams em um computador com macOS. </li> <li>**O Linux** é selecionado se o usuário estava ativo no cliente de área de trabalho do Teams em um computador Linux. </li> <li>**iOS** estará selecionado se o usuário estiver ativo no cliente do Mobile Teams para iOS.</li><li>**O telefone Android** é selecionado se o usuário estava ativo no cliente móvel do Teams para Android. <li><li>**Web** estará selecionado se o usuário estiver ativo no cliente Web do Teams. <li>**A última** atividade é a última data (UTC) em que o usuário participou de uma atividade do Teams.</li> </ul> Observe que se uma conta de usuário não existir mais no Azure AD, o nome de usuário será exibido como "--" na tabela. <br><br>Para ver as informações desejadas na tabela, certifique-se de adicionar as colunas à tabela. |
|**5**   |Selecione **Editar colunas** para adicionar ou remover colunas na tabela. |
|**6**   |Você pode exportar o relatório para um arquivo CSV para análise offline. Clique **em Exportar para o Excel** e, na guia **Downloads,** clique em **Baixar** para baixar o relatório quando estiver pronto.<br><br>![Captura de tela da guia Downloads mostrando relatórios exportados](../media/teams-reports-export-to-csv.png)|

## <a name="related-topics"></a>Tópicos relacionados

- [Análises e relatórios do Teams](teams-reporting-reference.md)
