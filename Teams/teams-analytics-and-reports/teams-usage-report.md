---
title: Relatório de uso do Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kojika
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Saiba como usar o relatório de uso do Teams no centro de administração do Microsoft Teams para obter uma visão geral das atividades to Teams na sua organização.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3e280a32c765c989ef5d6081388ad76701be6ab1
ms.sourcegitcommit: b2692b3f6c60d8df5ba0677c68ff9c90a75a0d72
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68033789"
---
# <a name="microsoft-teams-usage-report"></a>Relatório de uso do Microsoft Teams

O relatório de uso do Teams no centro de administração do Microsoft Teams apresenta uma visão geral da atividade de uso no Teams, incluindo o número de usuários e canais ativos, para que você possa ver rapidamente quantos usuários na sua organização estão usando o Teams para se comunicar e colaborar. Você pode visualizar as informações de uso de equipes, incluindo o número de usuários e canais ativos, convidados e mensagens em cada equipe.

Com mais informações adicionais sobre usuários internos e externos, agora você pode medir a colaboração dentro de canais compartilhados internos e externos [em uma](/Teams/shared-channels.md) equipe. Por exemplo, métricas como canais compartilhados ativos e usuários ativos externos em uma equipe ajudarão o administrador a medir a colaboração entre canais compartilhados dentro de uma equipe.

## <a name="view-the-usage-report"></a>Exibir o relatório de uso

Você deve ser um administrador global, um leitor global ou um administrador de serviços do Teams para exibir os relatórios no Centro de administração do Teams. Veja [ Use funções de administrador Teams para gerenciar o Teams](../using-admin-roles.md) para ler sobre como obter funções e permissões de administrador.

1. No painel de navegação esquerdo do Centro de administração do Microsoft Teams, clique **em Análise & relatórios** > **de uso**. Na guia **Exibir relatórios** , em **Relatório**, selecione **Uso do Teams**.
2. Em **Intervalo de dados**, selecione intervalo e em seguida clique em **Executar relatório**.

    ![Captura de tela do relatório de uso do Teams no Centro de administração do Teams com textos explicativo.](../media/teams-reports-teams-usage-with-callouts2.png "Captura de tela do relatório de uso do Teams no Centro de administração do Teams com textos explicativo")

## <a name="interpret-the-report"></a>Interpretar relatório

|Texto Explicativo |Descrição  |
|--------|-------------|
|**1**   |O relatório de atividades de uso do Teams pode ser exibido para ver tendências nos últimos 7, 30, 90 e 180 dias. |
|**2**   |Cada relatório tem uma data de geração. Os relatórios geralmente refletem uma latência de 24 a 48 horas do tempo de atividade. |
|**3**   |<ul><li>O eixo X no gráfico representa o intervalo selecionado de datas para o relatório.</li> <li> O eixo Y representa a contagem dos itens ativos ou atividade.</li> </ul>Passe o mouse sobre o ponto que representa um item ou atividade em uma determinada data para ver o número de instâncias de tal item ou atividade na data determinada.|
|**4**   |Você pode filtrar o que se vê no gráfico clicando em um item na legenda. Por exemplo, clique **em Usuários ativos internos****, Convidados** ativos, Canais **ativos**, **Postagens** e muito mais para ver apenas as informações relacionadas a cada um deles. Ao alterar esta seleção, as informações da tabela não são alteradas. |
|**5**   |A tabela oferece um detalhamento do uso por equipe. <ul><li>**O nome da** equipe é o nome de exibição da equipe. Você pode clicar no nome da equipe para ir para a página de configurações da equipe no Centro de administração do Microsoft Teams. </li> <li>**A ID da** equipe é o identificador exclusivo da equipe. </li> <li>**O** tipo refere-se a se a equipe é uma equipe privada ou pública.</li> <li>**Usuários ativos** internos são o número de usuários ativos, incluindo convidados que executam uma ação nessa equipe no período de tempo especificado. <br/>Usuários e convidados internos residem no mesmo locatário, mas não são os mesmos.</li><li>**Os convidados** ativos são o número de convidados que executam uma ação nessa equipe no período de tempo especificado.</li> <li>**Usuários ativos** externos (novo) é o número de usuários ativos de organizações externas que executam uma ação nessa equipe em um recurso, como um canal compartilhado em uma equipe. <br/> Os usuários externos têm suas próprias identidades em locatários diferentes e não são iguais a uma conta de convidado.</li><li>**Canais ativos** é o número de canais na equipe que tem pelo menos um usuário ativo no período de tempo especificado. Isso inclui canais privados, públicos e compartilhados. </li><li>**Canais compartilhados** ativos (novo) é o número de canais compartilhados em uma equipe que tem pelo menos um usuário interno ou externo ativo no período de tempo especificado. </li> <li>**O total de reuniões organizadas** é a soma de reuniões agendadas, recorrentes, não planejadas e não classificadas que um usuário organizou durante o período de tempo especificado. </li><li>**Postagens** é o número de todas as mensagens de postagem em canais no período de tempo especificado.</li> <li>**Respostas é o** número de todas as mensagens de resposta nos canais no período de tempo especificado.</li> <li>**Menções** é o número de todas as menções usadas em mensagens no período de tempo especificado.</li><li>**Reações** é o número de todas as reações a mensagens no período de tempo especificado.</li><li>**Mensagens urgentes** é o número de todas as mensagens urgentes no período de tempo especificado.</li><li>**Mensagens de** canal é o número de mensagens exclusivas que os usuários da equipe postam em chats de equipe durante o período de tempo especificado.</li> </li> </ul>Observe que, se uma equipe não existir mais, o nome será exibido como "--" na tabela. <br><br>Para ver as informações desejadas na tabela, certifique-se de adicionar as colunas à tabela. |
|**6**   |Selecione **Editar colunas** para adicionar ou remover colunas na tabela.|
|**7**   |Exporte o relatório para um arquivo CSV para análise offline. Selecione o **ícone Exportar para o Excel** e o relatório será baixado no navegador.|
|**8** |Os dados de série temporal representados no gráfico superior mostram métricas de uso diferentes agregadas para todo o locatário|
|**9** |Os dados tabulares representados na metade inferior mostram diferentes métricas de uso agregadas por equipe|

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]


## <a name="make-the-user-specific-data-anonymous"></a>Tornar os dados específicos do usuário anônimos

Para tornar os dados no relatório de atividades do usuário do Teams anônimos, você precisa ser um administrador global. O administrador global pode ocultar informações identificáveis (usando hashes MD5), como nome de exibição, nome do grupo, email e ID do AAD no relatório e sua exportação.

1. No Centro de administração do Microsoft 365, vá para **Configurações** >  da **Organização e,** na guia **Serviços**, escolha **Relatórios**.
    
2. Selecione **Relatórios** e, em seguida, **escolha Exibir nomes de usuário, grupo e site ocultos em todos os relatórios**. Essa configuração é aplicada aos relatórios de uso no Centro de administração do Microsoft 365, bem como ao Centro de administração do Teams.
  
3. Selecione **Salvar alterações**.

> [!NOTE]
> Habilitar essa configuração desidentirá informações de nome de usuário, grupo e site no relatório de atividades do usuário do [Teams](user-activity-report.md), relatório de uso de dispositivos do [Teams](device-usage-report.md) e relatório [de uso do Teams](teams-usage-report.md). A partir de 1º de setembro de 2021, essa configuração é habilitada por padrão para todos como parte do nosso compromisso contínuo de ajudar a proteger informações importantes e permitir que as empresas deem suporte às leis de privacidade locais. 
>
>Essa configuração também se aplica aos relatórios de uso do Microsoft 365 Centro de administração do Microsoft 365, Microsoft Graph e Power BI.

## <a name="related-topics"></a>Tópicos relacionados

- [Análises e relatórios do Teams](teams-reporting-reference.md)
