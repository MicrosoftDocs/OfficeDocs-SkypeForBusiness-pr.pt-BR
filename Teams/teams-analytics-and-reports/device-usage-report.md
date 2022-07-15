---
title: Relatório de uso de dispositivos do Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Saiba como usar o relatório de uso de dispositivos do Teams no centro de administração do Microsoft Teams para ver como os usuários em sua organização se conectam ao Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 949ad172425f5e02da2fa67078193b198cb987d1
ms.sourcegitcommit: 4c4f2f220832cae3efb3f6f3c74795300d661295
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2022
ms.locfileid: "66825505"
---
# <a name="microsoft-teams-device-usage-report"></a>Relatório de uso de dispositivos do Microsoft Teams

O relatório de uso de dispositivos do Teams no centro de administração do Microsoft Teams fornece informações sobre como os usuários se conectam ao Teams. Você pode usar o relatório para ver os dispositivos usados em toda a sua organização, incluindo quantos usam o Teams de seus dispositivos móveis em qualquer lugar.  

## <a name="view-the-device-usage-report"></a>Exibir o relatório de uso do dispositivo

1. No painel de navegação esquerdo do Centro de administração do Microsoft Teams, clique **em Análise & relatórios** > **de uso**. Na guia **Exibir relatórios** , em **Relatório**, selecione **Uso de dispositivos do Teams**.
2. Em **Intervalo de dados**, selecione intervalo e em seguida clique em **Executar relatório**.

    ![Captura de tela do relatório de uso de dispositivos do Teams no Centro de administração do Teams com textos explicativo.](../media/teams-reports-device-usage-with-callouts.png "Captura de tela do relatório de uso de dispositivos do Teams no Centro de administração do Teams com textos explicativo")

## <a name="interpret-the-report"></a>Interpretar relatório

|Texto Explicativo |Descrição  |
|--------|-------------|
|**1**   |O relatório de uso de dispositivos do Teams pode ser exibido para ver tendências nos últimos 7 ou 30 dias.  |
|**2**   |Cada relatório tem uma data para quando o relatório foi gerado. Os relatórios geralmente refletem uma latência de 24 horas do tempo de atividade. |
|**3**   |<ul><li>O eixo X no gráfico representa os diferentes dispositivos (**Windows**, **Mac**, **Linux**, **iOS**, **Android Phone**, **Web**) usados para se conectar ao Teams. </li><li>O eixo Y é o número de usuários que usam o dispositivo durante o período de tempo selecionado.</li> </ul>Passe o mouse sobre a barra que representa um dispositivo para ver o número de usuários que usam o dispositivo para se conectar ao Teams.|
|**4**   |A tabela fornece uma divisão do uso do dispositivo pelo usuário. <ul><li>**Nome de** usuário é o nome de exibição do usuário. Você pode clicar no nome de exibição para ir para a página de configuração do usuário no Centro de administração do Microsoft Teams. </li><li>**O Windows** é selecionado se o usuário estava ativo no cliente da área de trabalho do Teams em um computador baseado no Windows.</li><li>**Mac** estará selecionado se o usuário estiver ativo no cliente de desktop do Teams em um computador com macOS. </li> <li>**O Linux** será selecionado se o usuário estiver ativo no cliente da área de trabalho do Teams em um computador Linux. </li> <li>**iOS** estará selecionado se o usuário estiver ativo no cliente do Mobile Teams para iOS.</li><li>**O telefone Android** será selecionado se o usuário estiver ativo no cliente móvel do Teams para Android. <li><li>**Web** estará selecionado se o usuário estiver ativo no cliente Web do Teams. <li>**A última** atividade é a última data (UTC) em que o usuário participou de uma atividade do Teams.</li> </ul> Observe que, se uma conta de usuário não existir mais no Azure AD, o nome de usuário será exibido como "--" na tabela. <br><br>Para ver as informações desejadas na tabela, certifique-se de adicionar as colunas à tabela. |
|**5**   |Selecione **Editar colunas** para adicionar ou remover colunas na tabela. |
|**6**   |Você pode exportar o relatório para um arquivo CSV para análise offline. Clique **em Exportar para Excel** e, na **guia Downloads**, clique em  Baixar para baixar o relatório quando ele estiver pronto.<br><br>![Captura de tela da guia Downloads mostrando relatórios exportados.](../media/teams-reports-export-to-csv.png)|


## <a name="make-the-user-specific-data-anonymous"></a>Tornar os dados específicos do usuário anônimos

Para tornar os dados no relatório de uso de dispositivos do Teams anônimos, você precisa ser um administrador global. Isso ocultará informações identificáveis, como nome de exibição, email e ID do AAD no relatório e sua exportação.

1. No Centro de administração do Microsoft 365, vá para **As Configurações** \> da **Organização e,** na **guia Serviços**, escolha **Relatórios**.
    
2. Selecione **Relatórios** e escolha Exibir **identificadores anônimos**. Essa configuração é aplicada aos relatórios de uso no Centro de administração do Microsoft 365, bem como ao Centro de administração do Teams.
  
3. Selecione **Salvar alterações**.

## <a name="related-topics"></a>Tópicos relacionados

- [Análises e relatórios do Teams](teams-reporting-reference.md)
