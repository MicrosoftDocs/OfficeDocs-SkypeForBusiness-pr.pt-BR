---
title: Adicionar e atualizar rótulos de relatórios
author: tonysmit
ms.author: tonysmit
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
localization_priority: Normal
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
ms.openlocfilehash: 481e087a6cfe2b641f6b81fcfc893d50f27cbf47
ms.sourcegitcommit: 75ccb8cda9e6dd900df93a2d856ff5f7682ac623
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2021
ms.locfileid: "50237481"
---
<a name="add-and-update-reporting-labels"></a>Adicionar e atualizar rótulos de relatórios
============================

Os rótulos de relatório são usados em sua organização para indicar os locais físicos de escritórios, edifícios ou sites organizacionais. A página Rótulos de relatório no Centro de administração do Microsoft Teams permite que você forneça um arquivo de texto (.csv ou .tsv) contendo uma lista de locais físicos e suas sub-redes de rede associadas. Esse arquivo é usado pelo Recurso de Análise de Chamada para gerar relatórios. Ao carregar o mapeamento da sub-rede, os relatórios fornecidos por esses serviços também conterão os nomes de localização, facilitando o entendimento e o uso dos relatórios para a correção de possíveis problemas.

> [!IMPORTANT]
> Os Rótulos de Relatório  carregados serão tratados como Dados de Suporte de acordo  com seu contrato para o Office 365, incluindo qualquer informação que, de outra forma, seria considerada Dados do Cliente ou *Dados Pessoais.* Não inclua os dados que você não deseja fornecer à Microsoft como Dados de *Suporte,* pois essas informações estarão visíveis aos Engenheiros da Microsoft para fins de suporte.

Os rótulos de relatório e os dados de locais que você fornece são uma única estrutura de dados. No momento, não há nenhuma interface disponível para fazer edições individuais para os dados.

**Para editar a tabela de sub-redes e locais**

1. Na navegação à esquerda do Centro de administração do Microsoft Teams, clique em **Locais**  >  **relatórios de rótulos.**
2. Clique **em Carregar dados.**
3. No painel **Carregar dados,** clique em Selecionar um arquivo **e,** em seguida, navegue até e carregue seu arquivo .csv ou .tsv editado.
4. Clique **em Carregar.**

Você pode baixar um modelo de exemplo [aqui.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)

Use o exemplo a seguir para ajudar a criar seu arquivo de dados.

> [!IMPORTANT]
> Seu arquivo de dados não deve conter os headers de coluna (como Rede, Nome da Rede, etc.). Elas são usadas aqui apenas para fins informacionais. <br>

|Rede|Nome da Rede|Intervalo de Rede|Nome do Prédio|Tipo de Propriedade|Tipo de Construção|Building Office Type|Cidade|Código Postal|País|Estado|Região|Inside Corp|Rota Expressa|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|Mountain View|94043|Nos|CA|Nos|1|1|
|10.0.130.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|Mountain View|94043|Nos|CA|Nos|1|1|
|10.0.131.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|Mountain View|94043|Nos|CA|Nos|1|1|
|10.0.132.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|Mountain View|94043|Nos|CA|Nos|1|1|

Para obter mais informações sobre como formatar seu arquivo de dados, consulte o formato de arquivo de dados [do locatário e a estrutura de arquivos de dados de Criação.](CQD-upload-tenant-building-data.md#upload-building-data-file)

## <a name="related-topics"></a>Tópicos relacionados

[Configurar Análise de Chamada](set-up-call-analytics.md)

[Usar a análise de chamada para solucionar problemas de baixa qualidade da chamada](use-call-analytics-to-troubleshoot-poor-call-quality.md)
