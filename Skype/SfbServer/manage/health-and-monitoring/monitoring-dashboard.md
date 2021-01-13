---
title: Usando o Painel de Monitoramento no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e00e5783-116f-481f-ad17-3af847d6769a
description: 'Resumo: saiba mais sobre o Painel de Monitoramento no Skype for Business Server.'
ms.openlocfilehash: 98a96b8a513bad485a25aff76a69d787fb3079b0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827781"
---
# <a name="using-the-monitoring-dashboard-in-skype-for-business-server"></a>Usando o Painel de Monitoramento no Skype for Business Server
 
**Resumo:** Saiba mais sobre o Painel de Monitoramento no Skype for Business Server.
  
O Painel de Monitoramento fornece aos administradores uma visão geral rápida da saúde e do uso do sistema do Skype for Business Server. O Painel foi projetado para mostrar uma visão agregada das principais métricas do sistema e para fazer isso exibindo:
  
- Totais do dia atual. Observe que os valores mostrados para o dia atual representam dados que foram gravados da meia-noite até a hora atual (com base na hora local do servidor de relatórios). Isso significa que você geralmente exibirá dados para um dia parcial e não para um período de 24 horas. Por exemplo, se a hora local do servidor for 8:00, você verá oito horas de dados porque há oito horas entre meia-noite e a hora atual de 8:00 AM.
    
- Totais da semana e totais de tendência das últimas seis semanas.
    
- Totais do mês e totais de tendência dos últimos seis meses (somente para uso do sistema).
    
Observe que você pode usar o cmdlet [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csreportingconfiguration?view=skype-ps) para retornar a URL usada para acessar os Relatórios de Monitoramento do Skype for Business Server:
  
```PowerShell
Get-CsReportingConfiguration
```

Por padrão, o Painel de Monitoramento mostra dados para as seguintes métricas da semana atual (e os totais de tendência das seis semanas anteriores):
  
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
    
- Avg. minutos de sessão de áudio
    
  **Conferência**
  
- Total de conferências
    
- Conferências de IM
    
- Conferências A/V
    
- Conferências de compartilhamento de aplicativos
    
- Webconferência
    
- Total de organizadores
    
- Total de minutos da conferência A/V
    
- Avg. Minutos de conferência A/V
    
- Total de conferências PSTN
    
- Total de participantes PSTN
    
- Total de minutos de participantes PSTN
    
Além das métricas de Uso do Sistema, as métricas a seguir exibem o total do dia atual e dos seis dias anteriores (se você selecionar Exibição **Semanal)** ou para a semana atual e as últimas seis semanas se você selecionar Exibição Mensal **.**
  
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
    
- Taxa de falha de A/V
    
- Taxa de falha de compartilhamento de aplicativos
    
Cinco principais servidores por sessões com falha
  
## <a name="media-quality-diagnostics"></a>Diagnóstico de Qualidade de Mídia

Ponto a ponto
  
- Total de chamadas de baixa qualidade
    
- Percentual de chamada de baixa qualidade
    
- Chamadas PSTN com qualidade ruim
    
Conferência
  
- Total de chamadas de baixa qualidade
    
- Percentual de chamada de baixa qualidade
    
- Chamadas PSTN com qualidade ruim
    
Principais servidores por percentual de chamada de baixa qualidade
  
## <a name="working-with-the-monitoring-dashboard"></a>Trabalhando com o Painel de Monitoramento

Conforme indicado, os totais padrão são mostrados para a semana atual e os valores de tendência são mostrados nas últimas seis semanas. Se você preferir ver os totais do mês atual (bem como os valores de tendência dos últimos seis meses), clique no **link** Exibição Mensal no canto superior direito do painel. Se você decidir exibir totais mensais, o texto do link mudará para **Exibição Semanal.** Você pode voltar para a exibição semanal clicando nesse link.
  
> [!TIP]
> O Painel de Monitoramento restringe a análise dos totais da semana (ou mês) atual e dos valores de tendência das últimas seis semanas (ou meses). Você não pode alterar essas datas e horas. Por exemplo, você não pode usar o Painel para exibir os totais de relatório para o período de tempo que começa há nove meses. 
  
Os valores mostrados nas **colunas Esta semana**, **Este mês** ou **Hoje** vinculam você a informações mais detalhadas sobre o item. Tenha em mente que o nome da coluna e os valores exibidos nessa coluna geralmente serão diferentes dependendo da métrica escolhida e dependendo se você selecionou a exibição semanal ou a exibição mensal. Por exemplo, se você clicar nos totais mostrados para  a métrica de **logons** de usuário exclusivos, você verá o Relatório de Registro de Usuário para o período de tempo especificado. Você pode retornar ao Painel de Monitoramento a qualquer momento clicando no **Painel.**
  
> [!TIP]
> Você também pode acessar a home page Relatórios do Monitoring Server clicando no link **Relatórios** no canto superior direito do Painel.
  
A **coluna Tendência** exibe um gráfico de linha simples que mostra os totais das últimas seis semanas (ou, dependendo da métrica e do intervalo de tempo, dos últimos seis dias ou dos últimos seis meses). Esses gráficos de linha simples exibem um ponto de dados sem rótulo para cada período de tempo (por exemplo, um ponto de dados sem rótulo para cada uma das últimas seis semanas). No entanto, você pode recuperar valores reais para esses gráficos segurando o ponteiro do mouse sobre o gráfico. Nesse caso, uma dica de ferramenta mostra os valores máximo e mínimo no gráfico.
  
## <a name="exporting-data-from-the-monitoring-dashboard"></a>Exportando dados do Painel de Monitoramento

O Painel de Monitoramento oferece várias maneiras de exportar o modo de exibição de painel atual. Na barra de ferramentas Painel, você verá um ícone que se parece com um disquete com uma seta verde anexada a ele. Se você clicar nesse ícone, uma listada será exibida, dando a você os seguintes formatos de exportação de dados:
  
- Arquivo XML com dados de relatório
    
- CSV (delimitado por vírgula)
    
- PDF
    
- MHTML (arquivo da web)
    
- Excel
    
- Arquivo TIFF
    
- Word
    
Para exportar a exibição do painel atual (e seus valores), clique na opção de exportação desejada. O Skype for Business Server gera um relatório no formato especificado e dá a você a opção de abrir ou salvar o relatório. Observe que, por padrão, o Skype  for Business Server chama o Painel de Monitoramento do relatório e o salva na pasta Downloads. Para dar ao relatório um nome diferente ou armazená-lo em  uma pasta diferente, clique na seta ao lado do botão Salvar e clique em **Salvar como**. Se você não tiver problemas com o nome **Painel** de Monitoramento e se o relatório for salvo na pasta Downloads, basta clicar no **botão** Salvar.
  
É possível que, ao tentar exportar dados do painel, uma caixa de diálogo Alerta de Segurança apareça junto com **a** mensagem "Suas configurações atuais não permitem que este arquivo seja baixado". Se isso ocorrer, faça o seguinte:
  
- No Internet Explorer, selecione **Opções da Internet.**
    
- Na caixa de diálogo Opções da **Internet,** **na** guia Segurança, clique em **Sites** Confiáveis e em **Sites.**
    
- Na caixa **de diálogo**  Sites confiáveis, clique em Adicionar para adicionar o Skype for Business Server que está executando os Relatórios do Skype for Business Server aos conjunto de sites confiáveis.
    
- Clique **em Fechar** e em **OK.**
    
Em seguida, você precisará atualizar o Painel de Monitoramento antes que as alterações entre em vigor. Para fazer isso, pressione F5 ou clique **no** ícone Atualizar na barra de ferramentas Painel. (O **ícone Atualizar** é um círculo com um par de setas verdes.)
  
Você também pode criar uma planilha do Excel que inclua feeds de dados ao vivo, que inclui links para os dados mais recentes do Painel de Monitoramento. Para criar um arquivo de feed de dados ao vivo, clique no ícone laranja Exportar para **Feed de** Dados na barra de ferramentas.
  
Se você preferir imprimir o Painel atual, clique no ícone da impressora na barra de ferramentas.
  

