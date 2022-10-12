---
title: Relatório de atividades do usuário do Microsoft Teams
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
description: Saiba como usar o relatório de atividades do usuário do Teams no centro de administração do Microsoft Teams para ver como os usuários em sua organização estão usando o Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3bd00dd9cf05adea6d37ad07c1a22c3000d78e94
ms.sourcegitcommit: 8dd36e1e30a47316c15c99e964d0464715bcd742
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2022
ms.locfileid: "68532381"
---
# <a name="microsoft-teams-user-activity-report"></a>Relatório de atividades do usuário do Microsoft Teams

O relatório de atividades do usuário do Teams fornece informações sobre os tipos de atividades que os usuários em sua organização fazem no Teams. Você pode ver quantos usuários se comunicam de forma não planejada por meio de reuniões não agendadas (1:1 e chamadas de grupo). Veja quantas reuniões um usuário do Teams organizou e as reuniões em que um usuário do Teams participou. Veja detalhes sobre minutos de tela, vídeo e áudio e estatísticas de comunicação de chat, como quantos usuários respondem e postam mensagens de canal e quantos usuários se envolvem em mensagens de chat em grupo ou 1:1.

Com mais informações sobre usuários internos e externos, agora você pode medir a interação dos usuários em canais compartilhados internos e externos [, por](/Teams/shared-channels.md) exemplo, métricas como o nome do locatário ao qual o usuário pertence, nomes de locatário externos em que o usuário está interagindo e se o usuário é externo ao locatário ajudará os administradores a medir a interação dos usuários por meio de recursos de canal compartilhado. 

> [!NOTE]
> A capacidade de agendar um relatório de atividades do usuário não está disponível no momento.

## <a name="view-the-user-activity-report"></a>Exibir o relatório de atividades do usuário

Você deve ser um administrador global, um leitor global ou um administrador de serviços do Teams para exibir o relatório no centro de administração do Microsoft Teams. Veja [ Use funções de administrador Teams para gerenciar o Teams](../using-admin-roles.md) para ler sobre como obter funções e permissões de administrador.

1. No painel de navegação esquerdo do Centro de administração do Microsoft Teams, selecione **Relatórios de uso** >  &**análise.** Na guia **Exibir relatórios** , em **Relatório**, selecione **Atividade de usuário do Teams**.
2. Em **Intervalo de datas**, selecione um intervalo e, em seguida, **selecione Executar relatório**.

    ![Captura de tela do relatório de atividades do usuário do Teams no Centro de administração do Teams com textos explicativo.](../media/teams-reports-user-activity-with-callouts2.png "Captura de tela do relatório de atividades do usuário do Teams no Centro de administração do Teams com textos explicativo")

## <a name="interpret-the-report"></a>Interpretar relatório

| **Texto Explicativo** |**Descrição**  |
|--------|-------------|
|**1**   |O relatório de atividades do usuário do Teams pode ser exibido para ver tendências nos últimos 7, 30, 90 ou 180 dias. |
|**2**   |Cada relatório tem uma data de geração. Os relatórios geralmente refletem uma latência de 24 a 48 horas do momento da atividade. |
|**3**   |Os dados de série temporal representados no grafo superior mostram diferentes métricas de uso agregadas para todo o locatário. |
|**4**   |Os dados tabulares representados na metade inferior mostram diferentes métricas de uso agregadas por usuário. |
|**5**   |<ul><li>O eixo X no gráfico representa o intervalo selecionado de datas para o relatório.</li> <li> O eixo Y representa a contagem dos itens ativos ou atividade.</li> </ul>Passe o mouse sobre o ponto que representa um item ou atividade em uma determinada data para ver o número de instâncias de tal item ou atividade na data determinada.|
|**6**   | Cada uma das métricas é representada no grafo no nível do locatário. Filtre o que você vê no gráfico selecionando um item na legenda. Selecione **Mensagens de canal**, **mensagens de resposta**,  **mensagens de chat** ou **Reuniões** Organizadas e muito mais para ver informações relacionadas a cada uma delas. Ao alterar esta seleção, as informações da tabela não são alteradas. |
|**7**   |A tabela fornece um detalhamento do uso por usuário.   <ul><li>**O nome de** usuário é o endereço de email do usuário. Consulte [a seção a seguir](#make-the-user-specific-data-anonymous) para obter diretrizes sobre como anonimizá-la.  Selecione o nome de usuário para ir para a página de detalhes do usuário.</li><li>**O nome** do locatário (novo) é o nome de um locatário interno ou externo ao qual um usuário pertence. Se um usuário pertencer a um locatário externo, diferentes métricas de uso (por exemplo, mensagens de postagem, mensagens de resposta e muito mais) serão calculadas com base em suas interações em um ou mais canais compartilhados do locatário do administrador. As interações feitas por um usuário externo em seu próprio locatário não são consideradas para o relatório de uso do administrador de um determinado locatário.  </li><li>**Nomes de locatários** de canal compartilhado (novo) são os nomes de locatários internos ou externos em que o usuário participou como parte de um canal compartilhado.</li><li>**Mensagens de** canal é o número de mensagens exclusivas que o usuário postou em um canal de equipe durante o período de tempo especificado.</li><li>**Respostas é o** número de mensagens de resposta exclusivas que o usuário postou em um canal de equipe durante o período de tempo especificado.</li> <li>**Postagens** é o número de mensagens de postagem exclusivas que o usuário postou em um canal de equipe durante o período de tempo especificado.</li><li>**Mensagens de chat** é o número de mensagens exclusivas que o usuário publicou em um chat particular durante o período de tempo especificado.</li><li>**Mensagens urgentes** é o número de mensagens urgentes que o usuário postou em um chat durante o período de tempo especificado.</li><li>**O total de reuniões** organizadas é a soma de reuniões agendadas, recorrentes, não planejadas e não classificadas que um usuário organizou durante o período de tempo especificado.</li><li>**Reuniões organizadas únicamente agendadas** é o número de reuniões agendadas única que um usuário organizou durante o período de tempo especificado.</li><li>**Reuniões organizadas recorrentes agendadas** é o número de reuniões recorrentes que um usuário organizou durante o período de tempo especificado.</li><li>**Reuniões organizadas ad hoc** é o número de reuniões não planejadas que um usuário organizou durante o período de tempo especificado.</li><li>**O total de reuniões** participadas é a soma das reuniões agendadas, recorrentes, não planejadas e não classificadas em que um usuário participou durante o período de tempo especificado.</li><li>**As reuniões que participaram de uma** única vez agendadas são o número de reuniões agendadas que um usuário participou durante o período de tempo especificado.</li><li>**Reuniões participadas recorrentes agendadas** é o número de reuniões recorrentes das que um usuário participou durante o período de tempo especificado.</li><li>**Reuniões participadas ad hoc** é o número de reuniões não planejadas das que um usuário participou durante o período de tempo especificado.</li><li>**Chamadas 1:1** é o número de chamadas 1:1 das qual o usuário participou durante o período de tempo especificado.</li><li>**O tempo de** áudio é o tempo total de áudio (em minutos) do qual o usuário participou durante o período de tempo especificado.</li><li>**Tempo de** vídeo é o tempo total de vídeo (em minutos) do qual o usuário participou durante o período de tempo especificado.</li><li>**O tempo de** compartilhamento de tela é o tempo total de compartilhamento de tela (minutos) do qual o usuário participou durante o período de tempo especificado.</li>  <li>**A última** atividade é a última data (UTC) em que o usuário participou de uma atividade do Teams.</li><li>**Outras atividades** acompanham quando o usuário é considerado ativo, mas tem um valor igual a zero para mensagens de chat, chamadas 1:1, mensagens de canal, total de reuniões e reuniões organizadas. Exemplos de ações são quando um usuário altera o status do Teams ou a mensagem de status do Teams, quando um usuário abre uma postagem de mensagem de canal, mas não responde a ela, ou quando um usuário recebe uma mensagem privada e a lê, mas não responde a ela.</li> </ul> **As reuniões não classificadas** são aquelas que não podem ser identificadas como agendadas, recorrentes ou não planejadas. Eles são poucos em número e geralmente não podem ser identificados devido a informações de telemetria imperfeitas.<br><br>**As chamadas** em grupo foram substituídas por **Reuniões organizadas ad hoc** e Reuniões **participaram ad hoc**. A soma desses dois valores é igual ao que foi medido por chamadas **de grupo**. <br/><br/>Observe que, se um usuário não existir mais, o nome será exibido como "--" na tabela.
|**8**   |Selecione **Editar colunas** para adicionar ou remover colunas na tabela. |
**9**   |Exporte o relatório para um arquivo CSV para análise offline. Selecione **Exportar para o Excel** e o relatório será baixado no navegador. <br>Ao exibir o relatório no Excel, você também verá uma coluna **de ID de** usuário, que representa a ID de usuário. Uma ID de usuário normalmente é uma cadeia de caracteres alfanumérica. |


[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>Tornar os dados específicos do usuário anônimos

Para tornar os dados no relatório de atividades do usuário do Teams anônimos, você precisa ser um administrador global. O Administrador global pode ocultar informações identificáveis (usando hashes MD5), como nome de exibição, nome do grupo, email e ID do AAD em relatórios e sua exportação.

1. No Centro de administração do Microsoft 365, vá para **As Configurações** \> da **Organização e,** na **guia Serviços**, escolha **Relatórios**.
    
2. Selecione **Relatórios** e, em seguida, escolha **Exibir nomes de usuário, grupo e site ocultos em todos os relatórios**. Essa configuração é aplicada aos relatórios de uso no Centro de administração do Microsoft 365 e no Centro de administração do Teams.
  
3. Selecione **Salvar alterações**.


> [!NOTE]
> Habilitar essa configuração desidentirá as informações de nome de usuário, grupo e site no relatório de atividades do usuário do [Teams](user-activity-report.md), relatório de uso de dispositivos do [Teams](device-usage-report.md) e relatório [de uso do Teams](teams-usage-report.md) . A partir de 1º de setembro de 2021, essa configuração está habilitada por padrão para todos como parte do nosso compromisso contínuo de ajudar a proteger informações importantes e permitir que as empresas deem suporte às leis de privacidade locais. Essa configuração também se aplica aos relatórios de uso do Microsoft 365 no Centro de administração do Microsoft 365, no Microsoft Graph e no Power BI.
## <a name="related-topics"></a>Tópicos relacionados

- [Análises e relatórios do Teams](teams-reporting-reference.md)
