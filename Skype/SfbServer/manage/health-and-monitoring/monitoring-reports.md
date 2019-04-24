---
title: Usando relatórios de monitoramento no Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 733577d0-c70f-4c70-ab7b-59b89fb495a8
description: 'Resumo: Saiba sobre o monitoramento de relatórios no Skype para Business Server.'
ms.openlocfilehash: 11eb398d45102cb73fa02e61f63e0eda56e70200
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199674"
---
# <a name="using-monitoring-reports-in-skype-for-business-server"></a>Usando relatórios de monitoramento no Skype para Business Server 
 
**Resumo:** Saiba mais sobre o monitoramento de relatórios no Skype para Business Server.
  
Skype para Business Server inclui um conjunto de relatórios padrão publicados pelo serviço de relatório do Microsoft SQL Server. Esses relatórios, que podem ser acessados por meio de navegadores, fornecem informações de uso, diagnóstico de chamada e qualidade de mídia, com base em registros de detalhes das chamadas (CDR) e qualidade da experiência (QoE) armazenados nos bancos de dados de CDR e QoE.
  
Para usar esses relatórios, você deve instalar os relatórios do Monitoring em um computador que esteja executando uma instância do SQL Server.
  
## <a name="in-this-section"></a>Nesta seção

- [Usando o painel de monitoramento no Skype para Business Server](monitoring-dashboard.md) Fornece aos administradores uma visão geral rápida da integridade e uso do sistema.
    
- [Relatórios de uso do sistema na Skype para Business Server](system-usage-reports.md) Fornece informações de uso do sistema com base nos dados de CDR coletados pelo Skype para Business Server.
    
- [Chamada relatórios de diagnóstico (por usuário) no Skype para Business Server](call-diagnostic-reports-per-user.md) Fornece informações por usuário sobre sessões ponto a ponto e conferências com falha.
    
- [Relatórios de diagnóstico no Skype para Business Server de chamada](call-diagnostic-reports.md) Fornece informações de resumo e dados de diagnóstico para sessões de conferência e ponto a ponto com falha.
    
- [Relatórios de diagnóstico de qualidade de mídia no Skype para Business Server](media-quality-diagnostic-reports.md) Fornece informações sobre a qualidade da chamada, bem como informações de diagnóstico e solução de problemas para chamadas com falha.
    
## <a name="locating-records"></a>Localizar registros

Os relatórios de monitoramento mostram apenas um número limitado de registros na tela a qualquer momento. O número real de registros exibidos em uma tela varia de acordo com o relatório. Para exibir os registros que não estão atualmente exibidos na tela, você pode usar o frente e para trás controle padrão (encontrado na barra de ferramentas do cada relatório) que permitem que você percorrer os dados. Você pode saltar rapidamente para a primeira página ou a última página do conjunto de dados.
  
Além disso, usando os controles para ir para frente e para trás, você pode também saltar para qualquer página no conjunto de dados simplesmente digitando o número da página na caixa **Página Atual** e pressionando ENTER.
  
Além de fornecer a capacidade de percorrer os dados, cada relatório também inclui a capacidade limitada para localizar registros. Para localizar registros com base em um determinado valor, digite esse valor na caixa **Localizar** e clique em **Localizar**. O relatório procura nos dados e para na primeira ocorrência do valor inserido na caixa **Localizar**. Para localizar o próximo registro que satisfaça os critérios de pesquisa, clique em **Avançar**.
  
Como observado, os relatórios de monitoramento fornecem apenas as funções mais básicas de pesquisa. Por exemplo, você não pode especificar em qual campo o valor deve ser encontrado. O mecanismo de pesquisa automaticamente procura valores correspondentes em cada campo de cada registro. Você não pode usar caracteres curinga em pesquisas e todas as pesquisas procura valores parciais. Isso significa que se você procurar 111 a pesquisa retorna o valor 111 junto com os valores 11100, 811, 3112, 611A5B e outros campos que incluam o valor 111 em qualquer lugar dentro desse campo.
  
Cada relatório é configurado para exibir um conjunto de registros padrão. Por exemplo, por padrão o Relatório de Registro de Usuário exibe as atividades de registro de usuário da semana passada. Em alguns casos, isso pode resultar em um relatório que não retorna registros. Nesse caso, significa que nenhum registro de usuário ocorreu na semana passada. Se você vir a mensagem "nenhum resultado coincidirem com os filtros de relatório", tente alterando os valores de filtro (por exemplo, alterar o período de tempo no último mês ao invés da semana anterior) e execute novamente a consulta. Para obter detalhes, consulte "Filtragem de dados", seção que está mais adiante neste tópico.
  
## <a name="filtering-data"></a>Filtragem de dados

Provavelmente haverá momentos nos quais você deseje examinar apenas um subconjunto de registros. Por exemplo, somente sessões ponto a ponto, em vez de duas sessões ponto a ponto e sessões de conferência. Da mesma forma, haverá momentos nos quais você precise reduzir o número de registros retornados. Por padrão, um relatório só pode exibir os primeiros 1.000 registros em um conjunto de dados. Para resolver esses problemas, a maioria dos relatórios incluem um número de opções de filtragem. Por exemplo, se você quiser exibir apenas os registros para o período de 1 de janeiro de 2011 até 15 de janeiro de 2011, poderá inserir 1 de janeiro de 2011 na caixa **De** e 15 de janeiro de 2011 na caixa **Para**. Se você clicar em **Exibir relatório**, os dados retornados estarão limitados às atividades realizadas entre 1 de janeiro de 2011 e 15 de janeiro de 2011.
  
Os filtros disponíveis variam dependendo do relatório exibido. Para obter detalhes sobre um relatório específico, consulte o tópico Ajuda para esse relatório.
  
## <a name="exporting-data"></a>Exportação de dados

Os relatórios de monitoramento fornecem pelo menos duas maneiras diferentes de exportar os dados incluídos em um relatório. Você pode usar a opção **Exportar** na barra de ferramentas exibida na parte superior de cada relatório. Para usar essa opção, selecione o formato de exportação desejado na lista suspensa **Selecione um formato**. Os seguintes formatos estão disponíveis:
  
- Arquivo XML com dados de relatório
    
- CSV (delimitado por vírgula)
    
- Arquivo Acrobat (PDF)
    
- MHTML (arquivo da web)
    
- Excel
    
- Arquivo TIFF
    
- Word
    
Após selecionar um formato, clique em **Exportar**. Quando a caixa de diálogo **Download de arquivo** for exibida, clique em **Salvar**. Na caixa de diálogo **Salvar como**, selecione uma pasta de destino, insira um nome de arquivo e clique em **Salvar**.
  
Se o Microsoft OneNote estiver instalado, você também pode copiar os dados do relatório para o OneNote. Para fazer isso, clique com o botão direito no botão **Exibir Relatório** da barra de ferramentas. Na caixa de diálogo **Selecionar Local no OneNote**, selecione a seção do OneNote onde você deseja copiar os dados e clique em **OK**.
  

