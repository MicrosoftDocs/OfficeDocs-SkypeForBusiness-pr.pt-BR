---
title: 'Lync Server 2013: usando o painel de monitoramento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Monitoring Dashboard
ms:assetid: e00e5783-116f-481f-ad17-3af847d6769a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721905(v=OCS.15)
ms:contentKeyID: 49733839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91efa1e0431c86fa1918473d01021f68e4dc16b1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503738"
---
# <a name="using-the-monitoring-dashboard-in-lync-server-2013"></a>Usando o painel de monitoramento no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-02-05_

O painel de monitoramento fornece aos administradores uma visão geral rápida da integridade do sistema do Microsoft Lync Server 2013 e do uso do sistema. O painel é projetado para mostrar um modo de exibição de agregação de métricas de sistema principal e fazer isso, exibindo:

  - Totais para o dia atual. Observe que os valores mostrados para o dia atual representam os dados gravados da meia-noite até a hora atual (com base na hora local do servidor de relatórios). Isso significa que você normalmente estará exibindo dados por um dia parcial e não por um período de 24 horas. Por exemplo, se a hora local do servidor for 8:00 AM, você verá oito horas de dados, pois há oito horas entre meia-noite e a hora atual de 8:00 AM.

  - Totais para a semana e totais de tendência das últimas seis semanas.

  - Totais para o mês e os totais de tendência dos últimos seis meses (apenas para uso do sistema).

Observe que você pode usar o cmdlet [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration) para retornar a URL usada para acessar os relatórios de monitoramento do Lync Server 2013:

    Get-CsReportingConfiguration

Por padrão, o painel de monitoramento mostra dados para as seguintes métricas da semana atual (e os totais de tendência das seis semanas anteriores):

<div>

## <a name="system-usage-metrics"></a>Métricas de uso do sistema

**Registro**

  - Logons de usuário exclusivos

**Ponto a ponto**

  - Total de sessões

  - Sessões de IM

  - Sessões de áudio

  - Sessões de vídeo

  - Compartilhamento de aplicativos

  - Total de minutos de sessão de áudio

  - Média de minutos de sessão de áudio

**Conferência**

  - Total de conferências

  - Conferências de IM

  - Conferências A/V

  - Conferências de compartilhamento de aplicativos

  - Webconferências

  - Total de organizadores

  - Total de minutos da conferência A/V

  - Contadores. Minutos de conferência A/V

  - Total de conferências PSTN

  - Total de participantes PSTN

  - Total de minutos de participantes PSTN

Além das métricas de uso do sistema, as métricas a seguir exibem o total do dia atual e dos seis dias anteriores (se você selecionar **exibição Semanal**) ou para a semana atual e as últimas seis semanas se você selecionar **exibição mensal**.

</div>

<div>

## <a name="per-user-call-diagnostics"></a>Per-User diagnóstico de chamadas

**Usuários com falhas de chamada**

  - Total de usuários com falhas de chamada

  - Organizadores de conferência com falhas de chamada

**Usuários com chamadas de baixa qualidade**

  - Total de usuários com chamadas de baixa qualidade

</div>

<div>

## <a name="call-diagnostics"></a>Diagnóstico de chamada

Ponto a ponto

  - Total de falhas

  - Taxa de falha geral

  - Taxa de falha de IM

  - Taxa de falha de áudio

  - Taxa de falha de compartilhamento de aplicativo

Conferência

  - Total de falhas

  - Taxa de falha geral

  - Taxa de falha de IM

  - Taxa de falha de A/V

  - Taxa de falha de compartilhamento de aplicativo

Principais cinco servidores por sessões com falha

</div>

<div>

## <a name="media-quality-diagnostics"></a>Diagnóstico de qualidade de mídia

Ponto a ponto

  - Total de chamadas de baixa qualidade

  - Porcentagem de chamada de baixa qualidade

  - Chamadas PSTN com baixa qualidade

Conferência

  - Total de chamadas de baixa qualidade

  - Porcentagem de chamada de baixa qualidade

  - Chamadas PSTN com baixa qualidade

Principais servidores por porcentagem de chamadas de baixa qualidade

</div>

<div>

## <a name="working-with-the-monitoring-dashboard"></a>Trabalhar com o painel de monitoramento

Como observado, os totais padrão são mostrados para a semana atual e os valores de tendência são mostrados nas últimas seis semanas. Se você preferir ver os totais para o mês atual (bem como os valores de tendência dos últimos seis meses), clique no link de **exibição mensal** no canto superior direito do painel. Se você optar por exibir os totais mensais, o texto do link será alterado para **modo de exibição Semanal**. Você pode alternar de volta para o modo de exibição Semanal clicando nesse link.

<div>


> [!TIP]  
> O painel de monitoramento restringe você a observar os totais da semana atual (ou mês) e os valores de tendência das últimas seis semanas (ou meses). Não é possível alterar essas datas e horas. Por exemplo, você não pode usar o painel para exibir totais de relatório para o período de tempo que começa nove meses atrás.



</div>

Os valores mostrados nas colunas **esta semana**, **este mês**ou **hoje** o vinculam a informações mais detalhadas sobre o item. Lembre-se de que o nome da coluna e os valores exibidos nessa coluna geralmente diferem dependendo da métrica escolhida e dependendo se você selecionou o modo de exibição semanal ou mensal. Por exemplo, se você clicar nos totais mostrados para a métrica de **logons de usuário exclusivo** , verá o **relatório de registro de usuário** para o período de tempo especificado. Você pode retornar ao painel de monitoramento a qualquer momento clicando em **painel**.

<div>


> [!TIP]  
> Você também pode acessar a página inicial de relatórios do Monitoring Server clicando no link <STRONG>relatórios</STRONG> no canto superior direito do painel.



</div>

A coluna **tendência** exibe um gráfico de linhas simples que mostra os totais das últimas seis semanas (ou, dependendo da métrica e do intervalo de tempo, dos últimos seis dias ou dos últimos seis meses). Esses gráficos de linhas simples exibem um ponto de dados não rotulado para cada período de tempo (por exemplo, um ponto de dados não rotulado para cada uma das últimas seis semanas). No entanto, você pode recuperar os valores reais desses gráficos segurando o ponteiro do mouse sobre o gráfico. Nesse caso, uma dica de ferramenta mostra os valores máximo e mínimo no gráfico.

</div>

<div>

## <a name="exporting-data-from-the-monitoring-dashboard"></a>Exportando dados do painel de monitoramento

O painel de monitoramento oferece várias maneiras de exportar o modo de exibição atual do painel. Na barra de ferramentas painel, você verá um ícone parecido com um disquete com uma seta verde anexada. Se você clicar nesse ícone, uma lista suspensa aparecerá oferecendo os seguintes formatos de exportação de dados:

  - Arquivo XML com dados de relatório

  - CSV (delimitado por vírgula)

  - PDF

  - MHTML (arquivo da web)

  - Excel

  - Arquivo TIFF

  - Word

Para exportar o modo de exibição atual do painel (e seus valores), clique na opção Exportar desejado. O Lync Server 2013 gera um relatório no formato especificado e, em seguida, oferece a opção de abrir esse relatório ou salvá-lo. Observe que, por padrão, o Lync Server títulos o **painel de monitoramento** de relatórios e o salva na pasta downloads. Para dar um nome diferente ao relatório ou para armazená-lo em uma pasta diferente, clique na seta ao lado do botão **salvar** e clique em **salvar como**. Se você estiver bem no **painel de monitoramento** de nome e com o relatório salvo na pasta downloads, basta clicar no botão **salvar** .

É possível que, quando você tentar exportar os dados do painel, uma caixa de diálogo de **alerta de segurança** seja exibida junto com a mensagem "as configurações atuais não permitem o download desse arquivo." Se isso ocorrer, faça o seguinte:

  - No Internet Explorer, selecione **Opções da Internet**.

  - Na caixa de diálogo **Opções da Internet** , na guia **segurança** , clique em **sites confiáveis** e em **sites**.

  - Na caixa de diálogo **sites confiáveis** , clique em **Adicionar** para adicionar o Lync Server 2013 que está executando o Lync Server 2013 Reports para as coleções de sites confiáveis.

  - Clique em **fechar** e em **OK**.

Em seguida, será necessário atualizar o painel de monitoramento antes que as alterações entrem em vigor. Para fazer isso, pressione F5 ou clique no ícone **Atualizar** na barra de ferramentas do painel. (O ícone de **atualização** é um círculo com um par de setas verdes.)

Você também pode criar uma planilha do Excel que inclui o Live Data feeds, que inclui links para os dados mais recentes do painel de monitoramento. Para criar um arquivo de feed de dados dinâmicos, clique no ícone de **exportação laranja para alimentação de dados** na barra de ferramentas.

Se preferir imprimir o painel atual, clique no ícone da impressora na barra de ferramentas.

</div>

</div>

<span> </span>

</div>

</div>

</div>

