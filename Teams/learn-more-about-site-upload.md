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
description: Saiba como adicionar e atualizar rótulos de relatório carregando um arquivo de texto que contém uma lista de locais físicos e sub-redes associadas.
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
ms.openlocfilehash: 4a1af7f14695d1f933a9c3902b373eb668044e24
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918637"
---
<a name="add-and-update-reporting-labels"></a>Adicionar e atualizar rótulos de relatórios
============================

Os rótulos de relatório são usados em sua organização para indicar os locais físicos de escritórios, prédios ou sites organizacionais. A página de etiquetas de relatório no centro de administração do Microsoft Teams permite que você forneça um arquivo de texto (. csv ou. tsv) que contém uma lista de locais físicos e suas sub-redes de rede associadas. Esse arquivo é usado pela análise de chamadas para gerar relatórios. Quando você carregar o mapeamento de sub-rede, os relatórios fornecidos por esses serviços também conterão os nomes de localização, facilitando a compreensão e o uso dos relatórios para corrigir problemas em potencial.

> [!IMPORTANT]
> Os rótulos de relatório que você carrega serão tratados como *dados de suporte* em seu contrato do Office 365, incluindo qualquer informação que, de outra forma, seria considerada dados do *cliente* ou *dados pessoais*. Não inclua os dados que não deseja fornecer à Microsoft como dados de *suporte*, pois essas informações ficarão visíveis para os engenheiros da Microsoft para fins de suporte.

Os dados de rótulos e locais de relatório que você fornece são uma estrutura de dados única – atualmente, não há uma interface disponível para fazer edições individuais nos dados.

**Para editar a tabela de sub-redes e locais**

1. Na navegação à esquerda do centro de administração do Microsoft Teams, clique em **locais**  >  **relatório de rótulos**.
2. Clique em **substituir dados de localização**.
3. No painel **substituir dados de locais** , clique em **selecionar um arquivo** e, em seguida, navegue até o arquivo. csv ou. tsv editado e carregue-o.
4. Clique em **carregar**.

Você pode baixar um modelo de exemplo [aqui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true).

Use o exemplo a seguir para ajudar a criar seu arquivo de dados.

> [!IMPORTANT]
> Seu arquivo de dados não deve conter cabeçalhos de coluna (como rede, nome de rede, etc.). Eles são usados aqui apenas para fins informativos. <br>

|Rede|Nome da rede|Intervalo de rede|Nome do edifício|Tipo de propriedade|Tipo de edifício|Tipo de edifício de escritório|Cidade|Código Postal|País|Estado|Região|Inside Corp|Rota expressa|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0    |SVC-1|32|USCAMTV001|A contoso concedeu&F|Office|RE&F|Exibição de Mountain|94043|Junte|CA|Junte|1|1|
|10.0.130.0    |SVC-1|32|USCAMTV001|A contoso concedeu&F|Office|RE&F|Exibição de Mountain|94043|Junte|CA|Junte|1|1|
|10.0.131.0    |SVC-1|32|USCAMTV001|A contoso concedeu&F|Office|RE&F|Exibição de Mountain|94043|Junte|CA|Junte|1|1|
|10.0.132.0    |SVC-1|32|USCAMTV001|A contoso concedeu&F|Office|RE&F|Exibição de Mountain|94043|Junte|CA|Junte|1|1|

Para obter mais informações sobre como formatar seu arquivo de dados, consulte [formato de arquivo de dados do locatário e estrutura do arquivo de dados de construção](CQD-upload-tenant-building-data.md#upload-building-data-file).

## <a name="related-topics"></a>Tópicos relacionados

[Configurar Análise de Chamada](set-up-call-analytics.md)

[Usar a análise de chamadas para solucionar problemas de qualidade de chamadas ruins](use-call-analytics-to-troubleshoot-poor-call-quality.md)
