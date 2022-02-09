---
title: Usando o Painel de Monitoramento no Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: e00e5783-116f-481f-ad17-3af847d6769a
description: 'Resumo: saiba mais sobre o Painel de Monitoramento no Skype for Business Server.'
ms.openlocfilehash: 58a847ce5e63ad70477f1e43518464760e95d742
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399675"
---
# <a name="using-the-monitoring-dashboard-in-skype-for-business-server"></a>Usando o Painel de Monitoramento no Skype for Business Server
 
**Resumo:** Saiba mais sobre o Painel de Monitoramento Skype for Business Server.
  
O Painel de Monitoramento fornece aos administradores uma visão geral rápida de sua Skype for Business Server do sistema e do uso do sistema. O Painel foi projetado para mostrar uma exibição agregada das principais métricas do sistema e fazer isso exibindo:
  
- Totais do dia atual. Observe que os valores mostrados para o dia atual representam dados que foram registrados da meia-noite até a hora atual (com base no horário local do servidor de relatório). Isso significa que você normalmente exibirá dados por um dia parcial e não por um período de 24 horas. Por exemplo, se a hora local do servidor for 8:00, você verá oito horas de dados, pois há oito horas entre meia-noite e a hora atual de 8:00 AM.
    
- Totais da semana e totais de tendência das últimas seis semanas.
    
- Totais do mês e totais de tendência dos últimos seis meses (somente para uso do sistema).
    
Observe que você pode usar o cmdlet [Get-CsReportingConfiguration](/powershell/module/skype/get-csreportingconfiguration?view=skype-ps) para retornar a URL usada para acessar Skype for Business Server Relatórios de Monitoramento:
  
```PowerShell
Get-CsReportingConfiguration
```

Por padrão, o Painel de Monitoramento mostra dados para as seguintes métricas para a semana atual (e totais de tendência para as seis semanas anteriores):
  
## <a name="system-usage-metrics"></a>Métricas de Uso do Sistema

 **Registro**
  
- Logons de usuário exclusivos
    
  **Ponto a ponto**
  
- Total de sessões
    
- Sessões de IM
    
- Sessões de áudio
    
- Sessões de vídeo
    
- Compartilhamento de aplicativos
    
- Total de minutos de sessão de áudio
    
- Avg. minutos de sessão de áudio
    
  **Conferência**
  
- Total de conferências
    
- Conferências de IM
    
- Conferências A/V
    
- Conferências de compartilhamento de aplicativos
    
- Web conferences
    
- Total de organizadores
    
- Total de minutos da conferência A/V
    
- Avg. Minutos de conferência A/V
    
- Total de conferências PSTN
    
- Total de participantes PSTN
    
- Total de minutos de participantes PSTN
    
Além das métricas de Uso do Sistema, as métricas a seguir exibem o total do dia atual e dos seis dias anteriores (se você selecionar Exibição **Semanal) ou** para a semana atual e as últimas seis semanas se você selecionar **Exibir Mensalmente**.
  
## <a name="per-user-call-diagnostics"></a>Per-User Diagnóstico de Chamada

 **Usuários com falhas de chamada**
  
- Total de usuários com falhas de chamada
    
- Organizadores de conferência com falhas de chamada
    
  **Usuários com chamadas de baixa qualidade**
  
- Total de usuários com chamadas de baixa qualidade
    
## <a name="call-diagnostics"></a>Diagnóstico de Chamada

Ponto a ponto
  
- Total de falhas
    
- Taxa de falha geral
    
- Taxa de falha de IM
    
- Taxa de falha de áudio
    
- Taxa de falha de compartilhamento de aplicativos
    
Conferência
  
- Total de falhas
    
- Taxa de falha geral
    
- Taxa de falha de IM
    
- Taxa de falha A/V
    
- Taxa de falha de compartilhamento de aplicativos
    
Cinco servidores principais por sessões com falha
  
## <a name="media-quality-diagnostics"></a>Diagnóstico de Qualidade de Mídia

Ponto a ponto
  
- Total de chamadas de baixa qualidade
    
- Porcentagem de chamada de baixa qualidade
    
- Chamadas PSTN com baixa qualidade
    
Conferência
  
- Total de chamadas de baixa qualidade
    
- Porcentagem de chamada de baixa qualidade
    
- Chamadas PSTN com baixa qualidade
    
Principais servidores de pior qualidade por porcentagem de chamada de baixa qualidade
  
## <a name="working-with-the-monitoring-dashboard"></a>Trabalhando com o Painel de Monitoramento

Conforme indicado, por padrão, os totais são mostrados para a semana atual e os valores de tendência são mostrados nas últimas seis semanas. Se você preferir ver totais do mês atual (bem como os valores de tendência dos últimos seis meses), clique **no link** Exibição Mensal no canto superior direito do painel. Se você decidir exibir totais mensais, o texto do link será alterado para **Exibição Semanal**. Você pode alternar de volta para a exibição semanal clicando nesse link.
  
> [!TIP]
> O Painel de Monitoramento restringe você a olhar os totais da semana atual (ou mês) e os valores de tendência das últimas seis semanas (ou meses). Não é possível alterar essas datas e horas. Por exemplo, você não pode usar o Painel para exibir os totais do relatório do período que começa há nove meses. 
  
Os valores mostrados **nas colunas Esta semana**, **Este mês** ou **Hoje** vinculam você a informações mais detalhadas sobre o item. Lembre-se de que o nome da coluna e os valores exibidos nessa coluna geralmente diferem dependendo da métrica escolhida e dependendo se você selecionou a exibição semanal ou a exibição mensal. Por exemplo, se você clicar nos totais mostrados para a métrica de **logons** do usuário exclusivo, você verá o **Relatório** de Registro do Usuário para o período de tempo especificado. Você pode retornar ao Painel de Monitoramento a qualquer momento clicando em **Painel**.
  
> [!TIP]
> Você também pode acessar a home page Relatórios do Servidor de Monitoramento clicando **no link Relatórios** no canto superior direito do Painel.
  
A **coluna Tendência** exibe um gráfico de linha simples que mostra totais das últimas seis semanas (ou, dependendo da métrica e do intervalo de tempo, dos últimos seis dias ou dos últimos seis meses). Esses gráficos de linha simples exibem um ponto de dados não rotulado para cada período de tempo (por exemplo, um ponto de dados não rotulado para cada uma das últimas seis semanas). No entanto, você pode recuperar valores reais para esses gráficos segurando o ponteiro do mouse sobre o gráfico. Nesse caso, uma dica de ferramenta mostra os valores máximos e mínimos no gráfico.
  
## <a name="exporting-data-from-the-monitoring-dashboard"></a>Exportando dados do Painel de Monitoramento

O Painel de Monitoramento fornece várias maneiras de exportar o modo de exibição do painel atual. Na barra de ferramentas Painel, você verá um ícone que se parece com um disco flexível com uma seta verde anexada a ele. Se você clicar nesse ícone, uma listada aparecerá dando a você os seguintes formatos de exportação de dados:
  
- Arquivo XML com dados de relatório
    
- CSV (delimitado por vírgula)
    
- PDF
    
- MHTML (arquivo da web)
    
- Excel
    
- Arquivo TIFF
    
- Word
    
Para exportar a exibição atual do painel (e seus valores), clique na opção de exportação desejada. Skype for Business Server gera um relatório no formato especificado e, em seguida, dá a opção de abrir esse relatório ou salvá-lo. Observe que, por padrão, Skype for Business Server títulos do Painel de **Monitoramento** do relatório e salva-o na pasta Downloads. Para dar ao relatório um nome diferente ou para armazená-lo em uma pasta diferente, clique na seta  ao lado do botão Salvar e clique em **Salvar como**. Se você estiver bem com o nome **Painel de** Monitoramento e com o relatório salvo na pasta Downloads, basta clicar no **botão Salvar** .
  
É possível que, ao tentar exportar dados do painel, uma caixa de diálogo Alerta de Segurança apareça junto **com a mensagem** "Suas configurações atuais não permitem que esse arquivo seja baixado". Se isso ocorrer, faça o seguinte:
  
- No Internet Explorer, selecione **Opções da Internet**.
    
- Na caixa **de diálogo Opções da Internet** , na guia **Segurança** , clique em **Sites** confiáveis e clique em **Sites**.
    
- Na caixa **de diálogo Sites confiáveis**, clique em **Adicionar** para adicionar o Skype for Business Server que está executando Skype for Business Server Relatórios às coleções de sites confiáveis.
    
- Clique **em Fechar** e clique em **OK**.
    
Em seguida, você precisará atualizar o Painel de Monitoramento antes que as alterações entre em vigor. Para fazer isso, pressione F5 ou clique no ícone **Atualizar** na barra de ferramentas painel. (O **ícone Atualizar** é um círculo com um par de setas verdes nele.)
  
Você também pode criar uma planilha Excel que inclui feeds de dados ao vivo, que inclui links para os dados mais recentes do Painel de Monitoramento. Para criar um arquivo de feed de dados ao vivo, clique no ícone **laranja Exportar para Feed** de Dados na barra de ferramentas.
  
Se você preferir imprimir o Painel atual, clique no ícone da impressora na barra de ferramentas.
