---
title: Adicionar e atualizar rótulos de relatórios
author: tonysmit
ms.author: tonysmit
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Saiba como adicionar e atualizar rótulos de relatórios carregando um arquivo de texto que contém uma lista de locais físicos e sub-redes associadas.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- ms.teamsadmincenter.locations.reportinglabels.overview
- ms.teamsadmincenter.voice.phonenumbers.searchacquire.tooltip.location
- ms.teamsadmincenter.locations.overview
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 189b821e7238911190c4c72c07b863fc961f3074
ms.sourcegitcommit: ab9d27d7ddd1494539ae9424de200c9d0e76a9ec
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2021
ms.locfileid: "59984606"
---
# <a name="add-and-update-reporting-labels"></a>Adicionar e atualizar rótulos de relatórios

Os rótulos de relatório são usados em sua organização para indicar os locais físicos de escritórios, edifícios ou sites organizacionais. A página Rótulos de relatório no centro de administração Microsoft Teams permite fornecer um arquivo de texto (.csv ou .tsv) contendo uma lista de locais físicos e suas sub-redes de rede associadas. Esse arquivo é usado pelo Call Analytics para gerar relatórios. Ao carregar o mapeamento de sub-rede, os relatórios fornecidos por esses serviços também conterão os nomes de local, facilitando a compreensão e o uso dos relatórios para a correção de possíveis problemas.

> [!IMPORTANT]
> Os rótulos de relatórios  carregados serão tratados como Dados de Suporte em seu contrato para Office 365, incluindo quaisquer informações que de outra forma seriam consideradas Dados do Cliente *ou* *Dados Pessoais.* Não inclua dados que você não deseja fornecer à Microsoft como Dados de *Suporte,* pois essas informações estarão visíveis para os Engenheiros da Microsoft para fins de suporte.

Os rótulos de relatório e os dados de localização que você fornece são uma única estrutura de dados – no momento, não há nenhuma interface disponível para fazer edições individuais para os dados.

**Para editar a tabela de sub-redes e locais**

1. Na navegação à esquerda do centro de administração Microsoft Teams, clique em **Análise & relatórios**  >  **Rótulos de relatório.**
2. Clique **Upload dados**.
3. No painel **Upload** de dados, clique em Selecionar um arquivo **e** navegue até e carregue seu arquivo .csv ou .tsv editado.
4. Clique **Upload**.

Você pode baixar um modelo de exemplo [aqui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true).

Use o exemplo a seguir para ajudar a criar seu arquivo de dados.

> [!IMPORTANT]
> Seu arquivo de dados não deve conter os headers de coluna (como Rede, Nome da Rede, etc.). Eles são usados aqui apenas para fins informacionais. <br>

|Rede|Nome da rede|Intervalo de rede|Nome da construção|Tipo de propriedade|Tipo de construção|Criar Office Tipo|Cidade|Código Postal|País|Estado|Região|Inside Corp|Rota Expressa|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|Mountain View|94043|EUA|CA|EUA|1|1|
|10.0.130.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|Mountain View|94043|EUA|CA|EUA|1|1|
|10.0.131.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|Mountain View|94043|EUA|CA|EUA|1|1|
|10.0.132.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|Mountain View|94043|EUA|CA|EUA|1|1|

Para obter mais informações sobre como formatar seu arquivo de dados, consulte Formato de arquivo de dados de [locatário e Estrutura de arquivo de dados de criação.](CQD-upload-tenant-building-data.md#upload-building-data-file)

## <a name="related-topics"></a>Tópicos relacionados

[Configurar Análise de Chamada](set-up-call-analytics.md)

[Usar a análise de chamada para solucionar problemas de baixa qualidade de chamada](use-call-analytics-to-troubleshoot-poor-call-quality.md)
