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
ms.openlocfilehash: 11a16026bf8d844b4d533316e8680b8aa409b5b2
ms.sourcegitcommit: b2692b3f6c60d8df5ba0677c68ff9c90a75a0d72
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68033799"
---
# <a name="microsoft-teams-device-usage-report"></a>Relatório de uso de dispositivos do Microsoft Teams

O relatório de uso de dispositivos do Teams no centro de administração do Microsoft Teams fornece informações sobre como os usuários se conectam ao Teams. Você pode usar o relatório para ver os dispositivos usados em toda a sua organização, incluindo quantos usam o Teams de seus dispositivos móveis em qualquer lugar.  

## <a name="view-the-device-usage-report"></a>Exibir o relatório de uso do dispositivo


Você deve ser um administrador global, um leitor global ou um administrador de serviços do Teams para exibir relatórios no Centro de administração do Teams. Veja [ Use funções de administrador Teams para gerenciar o Teams](../using-admin-roles.md) para ler sobre como obter funções e permissões de administrador.


1. No painel de navegação esquerdo do Centro de administração do Microsoft Teams, clique **em Análise & relatórios** > **de uso**. Na guia **Exibir relatórios** , em **Relatório**, selecione **Uso de dispositivos do Teams**.
2. Em **Intervalo de dados**, selecione intervalo e em seguida clique em **Executar relatório**.

    ![Captura de tela do relatório de uso de dispositivos do Teams no Centro de administração do Teams com textos explicativo.](../media/teams-reports-device-usage-with-callouts.png "Captura de tela do relatório de uso de dispositivos do Teams no Centro de administração do Teams com textos explicativo")

## <a name="interpret-the-report"></a>Interpretar relatório

|Texto Explicativo |Descrição  |
|--------|-------------|
|**1**   |O relatório de uso de dispositivos do Teams pode ser exibido para ver tendências nos últimos 7, 30, 90 e 180 dias.  |
|**2**   |Cada relatório tem uma data para quando o relatório foi gerado. Os relatórios geralmente refletem uma latência de 24 a 48 horas do momento da atividade. |
|**3**   |<ul><li>O eixo X no gráfico representa os diferentes dispositivos (**Windows**, **Mac**, **Linux**, **iOS**, **Android Phone**, **Web**) usados para se conectar ao Teams. </li><li>O eixo Y é o número de usuários que usam o dispositivo durante o período de tempo selecionado.</li> </ul>Passe o mouse sobre a barra que representa um dispositivo para ver o número de usuários que usam o dispositivo para se conectar ao Teams.|
|**4**   |A tabela fornece uma divisão do uso do dispositivo pelo usuário. <ul><li>**Nome de** usuário é o nome de exibição do usuário. Você pode clicar no nome de exibição para ir para a página de configuração do usuário no Centro de administração do Microsoft Teams. </li><li>**O Windows** é selecionado se o usuário estava ativo no cliente da área de trabalho do Teams em um computador baseado no Windows.</li><li>**Mac** estará selecionado se o usuário estiver ativo no cliente de desktop do Teams em um computador com macOS. </li> <li>**O Linux** será selecionado se o usuário estiver ativo no cliente da área de trabalho do Teams em um computador Linux. </li> <li>**iOS** estará selecionado se o usuário estiver ativo no cliente do Mobile Teams para iOS.</li><li>**O telefone Android** será selecionado se o usuário estiver ativo no cliente móvel do Teams para Android.</li><li>**O sistema operacional Chrome** é selecionado se o usuário estava ativo no cliente da área de trabalho do Teams em um computador ChromeOS.</li><li>**Web** estará selecionado se o usuário estiver ativo no cliente Web do Teams. <li>**A última** atividade é a última data (UTC) em que o usuário participou de uma atividade do Teams.</li> </ul> Observe que, se uma conta de usuário não existir mais no Azure AD, o nome de usuário será exibido como "--" na tabela. <br><br>Para ver as informações desejadas na tabela, certifique-se de adicionar as colunas à tabela. |
|**5**   |Selecione **Editar colunas** para adicionar ou remover colunas na tabela. |
|**6**   |Exporte o relatório para um arquivo CSV para análise offline. Selecione o **ícone Exportar para Excel** e o relatório será baixado no navegador.|
|**7** |Os dados de série temporal representados no gráfico superior mostram métricas de uso diferentes agregadas para todo o locatário|
|**8** |Os dados tabulares representados na metade do botton mostram métricas de uso diferentes agregadas por usuário|


## <a name="make-the-user-specific-data-anonymous"></a>Tornar os dados específicos do usuário anônimos

Para tornar os dados no relatório de atividades do usuário do Teams anônimos, você precisa ser um administrador global. O administrador global pode ocultar informações identificáveis (usando hashes MD5), como nome de exibição, nome do grupo, email e ID do AAD no relatório e sua exportação.

1. No Centro de administração do Microsoft 365, vá para **As Configurações** \> da **Organização e,** na **guia Serviços**, escolha **Relatórios**.
    
2. Selecione **Relatórios** e, em seguida, **escolha Exibir nomes de usuário, grupo e site ocultos em todos os relatórios**. Essa configuração é aplicada aos relatórios de uso no Centro de administração do Microsoft 365, bem como ao Centro de administração do Teams.
  
3. Selecione **Salvar alterações**.

> [!NOTE]
> Habilitar essa configuração desidentirá as informações de nome de usuário, grupo e site no relatório de atividades do usuário do [Teams](user-activity-report.md), no relatório de uso de dispositivos do [Teams](device-usage-report.md) e [no relatório de uso do Teams](teams-usage-report.md). A partir de 1º de setembro de 2021, essa configuração é habilitada por padrão para todos como parte do nosso compromisso contínuo de ajudar a proteger informações importantes e permitir que as empresas deem suporte às leis de privacidade locais. 
>
>Essa configuração também se aplica aos relatórios de uso do Microsoft 365 Centro de administração do Microsoft 365, Microsoft Graph e Power BI.

## <a name="related-topics"></a>Tópicos relacionados

- [Análises e relatórios do Teams](teams-reporting-reference.md)
