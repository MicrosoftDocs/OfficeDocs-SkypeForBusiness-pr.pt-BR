---
title: Usar o painel de monitoramento no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e00e5783-116f-481f-ad17-3af847d6769a
description: 'Resumo: Saiba mais sobre o painel de monitoramento no Skype for Business Server.'
ms.openlocfilehash: 0ca85bff7cfcad7f3b64a4b0f5b92a22299e5719
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279925"
---
# <a name="using-the-monitoring-dashboard-in-skype-for-business-server"></a>Usar o painel de monitoramento no Skype for Business Server
 
**Resumo:** Saiba mais sobre o painel de monitoramento no Skype for Business Server.
  
O painel Monitoramento fornece aos administradores uma rápida visão geral da integridade do sistema e do uso do sistema do Skype for Business Server. O Painel foi projetado para fornecer uma exibição agregada das principais métricas do sistema e para fazer isso exibindo:
  
- Os totais para o dia atual. Observe que os valores mostrados para o dia atual representam dados que foram gravados da meia-noite até a hora atual (com base na hora local do servidor de relatório). Isso significa que você geralmente estará vendo dados referentes a um dia parcial, não a um período de 24 horas. Por exemplo, se a hora local do servidor for 8:00 AM, você verá a importância de oito horas de dados porque há oito horas entre a meia-noite e a hora atual do 8:00 AM.
    
- Totais para a semana e totais de tendência das últimas seis semanas.
    
- Totais para o mês e os totais de tendência dos últimos seis meses (apenas para uso do sistema).
    
Observe que você pode usar o cmdlet [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csreportingconfiguration?view=skype-ps) para retornar a URL usada para acessar os relatórios de monitoramento do Skype for Business Server:
  
```
Get-CsReportingConfiguration
```

Por padrão, o Painel de Monitoramento mostra dados para as seguintes métricas da semana atual (e os totais de tendência das seis semanas anteriores):
  
## <a name="system-usage-metrics"></a>Métricas de uso do sistema

 **Registro**
  
- Logons de usuário exclusivos
    
  **Ponto a ponto**
  
- Total de sessões
    
- Sessões de mensagens instantâneas
    
- Sessões de áudio
    
- Sessões de vídeo
    
- Compartilhamento de aplicativos
    
- Total de minutos da sessão de áudio
    
- Média de minutos da sessão de áudio
    
  **Conferência**
  
- Total de conferências
    
- Conferências de mensagens instantâneas
    
- Conferências A/V
    
- Conferências de compartilhamento de aplicativos
    
- Webconferências
    
- Total de organizadores
    
- Total de minutos da conferência A/V
    
- Média de minutos da conferência A/V
    
- Total de conferências PSTN
    
- Total de participantes PSTN
    
- Total de minutos dos participantes PSTN
    
Além das métricas de Uso do Sistema, as seguintes métricas exibem o total para o dia atual e os seis dias anteriores (se você selecionar **Exibição Semanal**) ou para a semana atual e as últimas seis semanas se você selecionar **Exibição Mensal**.
  
## <a name="per-user-call-diagnostics"></a>Diagnóstico de chamada por usuário

 **Usuários com falhas na chamada**
  
- Total de usuários com falhas de chamada
    
- Organizadores de conferência com falhas de chamada
    
  **Usuários com chamadas com qualidade ruim**
  
- Total de usuários com chamadas de baixa qualidade
    
## <a name="call-diagnostics"></a>Diagnóstico de Chamadas

Ponto a ponto
  
- Total de falhas
    
- Taxa de falha geral
    
- Taxa de falha de mensagens instantâneas
    
- Taxa de falha de áudio
    
- Taxa de falha de compartilhamento de aplicativos
    
Conferência
  
- Total de falhas
    
- Taxa de falha geral
    
- Taxa de falha de mensagens instantâneas
    
- Taxa de falha de A/V
    
- Taxa de falha de compartilhamento de aplicativos
    
Principais cinco servidores por sessões de falha
  
## <a name="media-quality-diagnostics"></a>Diagnóstico de Qualidade de Mídia

Ponto a ponto
  
- Total de chamadas com qualidade ruim
    
- Percentual de chamadas com qualidade ruim
    
- Chamadas PSTN com qualidade ruim
    
Conferência
  
- Total de chamadas com qualidade ruim
    
- Percentual de chamadas com qualidade ruim
    
- Chamadas PSTN com qualidade ruim
    
Piores servidores por percentual de chamadas com qualidade ruim
  
## <a name="working-with-the-monitoring-dashboard"></a>Trabalhando com o Painel de Monitoramento

Conforme observado, os totais padrões são mostrados para a semana atual e os valores de tendência são mostrados para as últimas seis semanas. Se você prefere ver os totais para o mês atual (assim como os valores de tendência para os últimos seis meses), clique no link **Exibição Mensal** no canto superior direito do painel. Se você decidir exibir os totais mensais, o texto do link irá mudar para **Exibição Semanal**. É possível voltar para a exibição semanal clicando neste link.
  
> [!TIP]
> O Painel de Monitoramento restringe a exibição dos totais para a semana (ou mês) atual e os valores de tendência das últimas seis semanas (ou meses). Não é possível alterar essas datas e horas. Por exemplo, não é possível usar o Painel para ver os totais do relatório para o período que inicia nove meses atrás. 
  
Os valores mostrados nas colunas **Esta semana**, **Este mês** ou **Hoje** vinculam você às informações mais detalhadas sobre o item. Lembre-se de que o nome da coluna e os valores exibidos nesta coluna frequentemente são diferentes dependendo da métrica escolhida e dependendo se você selecionou exibição semanal ou mensal. Por exemplo, se você clicar nos totais exibidos para a métrica **Logons de usuário exclusivos**, você verá o **Relatório de Registro do Usuário** para o período especificado. É possível retornar para o Painel de Monitoramento a qualquer momento clicando em **Painel**.
  
> [!TIP]
> Você também pode acessar a Home Page de relatórios do Monitoring Server clicando no link **relatórios** no canto superior direito do painel.
  
A coluna **Tendência** exibe um gráfico de linha simples que mostra os totais das últimas seis semanas (ou, dependendo da métrica e do intervalo de tempo, os últimos seis dias ou últimos seis meses). Esses gráficos de linha simples mostram um ponto de dados não rotulado para cada período (por exemplo, um ponto de dados não rotulado para cada uma das últimas seis semanas). No entanto, é possível recuperar os valores reais desses gráficos mantendo o ponteiro do mouse sobre o gráfico. Nesse caso, uma dica de tela mostra os valores máximos e mínimo no gráfico.
  
## <a name="exporting-data-from-the-monitoring-dashboard"></a>Exportando dados do Painel de Monitoramento

O Painel de Monitoramento oferece várias formas de exportar a exibição do painel atual. Na barra de ferramentas do Painel, você verá um ícone semelhante a um disquete com uma seta verde anexada. Se você clicar nesse ícone, uma lista suspensa aparecerá oferecendo os seguintes formatos de exportação de dados:
  
- Arquivo XML com dados do relatório
    
- CSV (delimitado por vírgula)
    
- PDF
    
- MHTML (arquivo Web)
    
- Excel
    
- Arquivo TIFF
    
- Word
    
Para exportar a exibição do painel atual (e seus valores), clique na opção de exportação desejada. O Skype for Business Server gera um relatório no formato especificado e oferece a opção de abrir esse relatório ou salvá-lo. Observe que, por padrão, o Skype for Business Server títulos o **painel Monitoramento** de relatório e salva-o na pasta downloads. Para dar um nome diferente ou armazená-lo em uma pasta diferente, clique na seta ao lado do botão **Salvar** e clique em **Salvar Como**. Se você concorda com o nome **Painel de Monitoramento** e em salvar na pasta Downloads, basta clicar no botão **Salvar**.
  
É possível que, ao tentar exportar os dados do painel, uma caixa de diálogo **Alerta de Segurança** seja exibida junto com a mensagem "Suas configurações atuais não permitem que este arquivo seja baixado". Se isso ocorrer, faça o seguinte:
  
- No Internet Explorer, selecione **Opções de Internet**.
    
- Na caixa de diálogo **Opções de Internet**, na guia **Segurança**, clique em **Sites confiáveis** e em **Sites**.
    
- Na caixa de diálogo **sites confiáveis** , clique em **Adicionar** para adicionar o Skype for Business Server que está executando os relatórios do Skype for Business Server às coleções de sites confiáveis.
    
- Clique em **Fechar** e em **OK**.
    
Você precisará atualizar o Painel de Monitoramento para que as alterações tenham efeito. Para fazer isso, pressione F5 ou clique no ícone **Atualizar** na barra de ferramentas do Painel. (O ícone **Atualizar** é um círculo com um par de setas verdes.)
  
Também é possível criar uma planilha do Excel que inclui feeds de dados ao vivo, incluindo links para os dados do Painel de Monitoramento. Para criar um arquivo de feed de dados ao vivo, clique no ícone laranja **Exportar para Feed de Dados** na barra de ferramentas.
  
Se você prefere imprimir o Painel atual, clique no ícone da impressora na barra de ferramentas.
  

