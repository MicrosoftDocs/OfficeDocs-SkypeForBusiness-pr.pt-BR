---
title: Usando relatórios de monitoramento no Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 733577d0-c70f-4c70-ab7b-59b89fb495a8
description: 'Resumo: Saiba mais sobre Relatórios de Monitoramento no Skype for Business Server.'
ms.openlocfilehash: 0088bb5a83de7f1f22e14461bb841a6011810444
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60862278"
---
# <a name="using-monitoring-reports-in-skype-for-business-server"></a>Usando relatórios de monitoramento no Skype for Business Server 
 
**Resumo:** Saiba mais sobre Relatórios de Monitoramento Skype for Business Server.
  
Skype for Business Server inclui um conjunto de relatórios padrão publicados pelo Microsoft SQL Server Reporting Service. Esses relatórios, que podem ser acessados com um navegador da Web, oferecem informações sobre utilização, diagnóstico de chamadas e qualidade de mídia, todas baseadas nos registros de detalhes das chamadas (CDR) e de Qualidade da Experiência (QoE) armazenados nos bancos de dados de CDR e QoE.
  
Para usar esses relatórios, você deve instalar Relatórios de Monitoramento em um computador que está executando uma instância do SQL Server.
  
## <a name="in-this-section"></a>Nesta seção

- [Usando o Painel de Monitoramento no Skype for Business Server](monitoring-dashboard.md) Fornece aos administradores uma visão geral rápida da saúde do sistema e do uso do sistema.
    
- [Relatórios de uso do sistema em Skype for Business Server](system-usage-reports.md) Fornece informações de uso do sistema com base nos dados de CDR coletados por Skype for Business Server.
    
- [Chamar Relatórios de Diagnóstico (por usuário) Skype for Business Server](call-diagnostic-reports-per-user.md) Fornece informações por usuário sobre sessões ponto a ponto com falha e conferência.
    
- [Chamar Relatórios de Diagnóstico no Skype for Business Server](call-diagnostic-reports.md) Fornece informações resumidas e dados de diagnóstico para sessões ponto a ponto com falha e conferência.
    
- [Relatórios de diagnóstico de qualidade de mídia em Skype for Business Server](media-quality-diagnostic-reports.md) Fornece informações sobre a qualidade da chamada, bem como informações de diagnóstico e solução de problemas para chamadas com falha.
    
## <a name="locating-records"></a>Localizar registros

Os relatórios de monitoramento mostram apenas um número limitado de registros na tela a qualquer momento. O número real de registros exibidos em uma tela varia de acordo com o relatório. Para exibir os registros que não são mostrados atualmente na tela, você pode usar o controle padrão para frente e para trás (encontrado na barra de ferramentas de cada relatório) que permite que você page pelos dados. Você pode saltar rapidamente para a primeira página ou a última página do conjunto de dados.
  
Além disso, usando os controles para ir para frente e para trás, você pode também saltar para qualquer página no conjunto de dados simplesmente digitando o número da página na caixa **Página Atual** e pressionando ENTER.
  
Além de fornecer a capacidade de percorrer os dados, cada relatório também inclui a capacidade limitada para localizar registros. Para localizar registros com base em um determinado valor, digite esse valor na caixa **Localizar** e clique em **Localizar**. O relatório procura nos dados e para na primeira ocorrência do valor inserido na caixa **Localizar**. Para localizar o próximo registro que satisfaça os critérios de pesquisa, clique em **Avançar**.
  
Como observado, os relatórios de monitoramento fornecem apenas as funções mais básicas de pesquisa. Por exemplo, você não pode especificar em qual campo o valor deve ser encontrado. O mecanismo de pesquisa automaticamente procura valores correspondentes em cada campo de cada registro. Você não pode usar caracteres curinga em pesquisas e todas as pesquisas procura valores parciais. Isso significa que se você procurar 111 a pesquisa retorna o valor 111 junto com os valores 11100, 811, 3112, 611A5B e outros campos que incluam o valor 111 em qualquer lugar dentro desse campo.
  
Cada relatório é configurado para exibir um conjunto de registros padrão. Por exemplo, por padrão o Relatório de Registro de Usuário exibe as atividades de registro de usuário da semana passada. Em alguns casos, isso pode resultar em um relatório que não retorna registros. Nesse caso, significa que nenhum registro de usuário ocorreu na semana passada. Se você vir a mensagem "Sem resultados que corresponderem aos filtros de relatório", tente alterar os valores do filtro (por exemplo, altere o período de tempo para o mês anterior, em vez da semana passada) e reexame a consulta. Para obter detalhes, consulte "Filtragem de dados", seção que está mais adiante neste tópico.
  
## <a name="filtering-data"></a>Filtragem de dados

Provavelmente haverá momentos nos quais você deseje examinar apenas um subconjunto de registros. Por exemplo, somente sessões ponto a ponto, em vez de duas sessões ponto a ponto e sessões de conferência. Da mesma forma, haverá momentos nos quais você precise reduzir o número de registros retornados. Por padrão, um relatório só pode exibir os primeiros 1.000 registros em um conjunto de dados. Para resolver esses problemas, a maioria dos relatórios incluem um número de opções de filtragem. Por exemplo, se você quiser exibir apenas os registros para o período de 1 de janeiro de 2011 até 15 de janeiro de 2011, poderá inserir 1 de janeiro de 2011 na caixa **De** e 15 de janeiro de 2011 na caixa **Para**. Se você clicar em **Exibir relatório**, os dados retornados estarão limitados às atividades realizadas entre 1 de janeiro de 2011 e 15 de janeiro de 2011.
  
Os filtros disponíveis variam dependendo do relatório exibido. Para obter detalhes sobre um relatório específico, consulte o tópico Ajuda para esse relatório.
  
## <a name="exporting-data"></a>Exportação de dados

Os relatórios de monitoramento fornecem pelo menos duas maneiras diferentes de exportar os dados incluídos em um relatório. Você pode usar a opção **Exportar** na barra de ferramentas exibida na parte superior de cada relatório. Para usar esta opção, selecione o formato de exportação desejado na lista suspensa **Selecione um formato**. Os seguintes formatos estão disponíveis:
  
- Arquivo XML com dados de relatório
    
- CSV (delimitado por vírgula)
    
- Arquivo Acrobat (PDF)
    
- MHTML (arquivo da web)
    
- Excel
    
- Arquivo TIFF
    
- Word
    
Após selecionar um formato, clique em **Exportar**. Quando a caixa de diálogo **Download de arquivo** for exibida, clique em **Salvar**. Na caixa de diálogo **Salvar como**, selecione uma pasta de destino, insira um nome de arquivo e clique em **Salvar**.
  
Se o Microsoft OneNote estiver instalado, você também pode copiar os dados do relatório para o OneNote. Para fazer isso, clique com o botão direito no botão **Exibir Relatório** da barra de ferramentas. Na caixa de diálogo **Selecionar Local no OneNote**, selecione a seção do OneNote onde você deseja copiar os dados e clique em **OK**.
  

