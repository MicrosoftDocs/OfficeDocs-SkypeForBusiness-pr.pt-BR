---
title: Adicionar e atualizar rótulos de relatório
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
- Teams_ITAdmin_Help
- M365-collaboration
description: Saiba como carregar um arquivo de texto que contém uma lista de locais físicos e sub-redes associadas para usar como rótulos de relatório para relatórios de análise de chamada e de painel de qualidade de chamada.
ms.custom:
- NewAdminCenter_Update
f1keywords:
- ms.teamsadmincenter.locations.reportinglabels.overview
- ms.teamsadmincenter.voice.phonenumbers.searchacquire.tooltip.location
- ms.teamsadmincenter.locations.overview
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6a876e6b007674aba9e0132005a57913c38f3297
ms.sourcegitcommit: 8fb89d6226b02ba8b1f8396eb4d1a37da4608b7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2019
ms.locfileid: "37396427"
---
<a name="add-and-update-reporting-labels"></a>Adicionar e atualizar rótulos de relatório
============================

Os rótulos de relatório são usados em sua organização para indicar os locais físicos de escritórios, prédios ou sites organizacionais. A página de etiquetas de relatório no centro de administração do Microsoft Teams permite que você forneça um arquivo de texto (. csv ou. tsv) que contém uma lista de locais físicos e suas sub-redes de rede associadas. Esse arquivo é usado pelo painel de análise de chamadas e de qualidade de chamada para gerar relatórios. Quando você carregar o mapeamento de sub-rede, os relatórios fornecidos por esses serviços também conterão os nomes de localização, facilitando a compreensão e o uso dos relatórios para corrigir problemas em potencial.

Os dados de rótulos e locais de relatório que você fornece são uma estrutura de dados única – atualmente, não há uma interface disponível para fazer edições individuais nos dados.

**Para editar a tabela de sub-redes e locais**

1. Na navegação à esquerda do centro de administração do Microsoft Teams, clique em **locais** > **relatório de rótulos**.
2. Clique em **substituir dados de localização**.
3. No painel **substituir dados de local** , clique em **selecionar um arquivo**e, em seguida, navegue até o arquivo. csv ou. tsv editado e carregue-o.
4. Clique em **carregar**.

Você pode baixar um modelo de exemplo [aqui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true).

Use o exemplo a seguir para ajudar a criar seu arquivo de dados.

> [!IMPORTANT]
> Seu arquivo de dados não deve conter cabeçalhos de coluna (como rede, nome de rede, etc.). Eles são usados aqui apenas para fins informativos. <br>

|Rede|Nome da rede|Intervalo de rede|Nome do edifício|Tipo de propriedade|Tipo de edifício|Tipo de edifício de escritório|Cidade|Código Postal|País|Estado|Região|Inside Corp|Rota expressa|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0 |SVC-1|32|USCAMTV001|A contoso concedeu&F|Office|RE&F|Exibição de Mountain|94043|Junte|CA|Junte|1|1|
|10.0.130.0 |SVC-1|32|USCAMTV001|A contoso concedeu&F|Office|RE&F|Exibição de Mountain|94043|Junte|CA|Junte|1|1|
|10.0.131.0 |SVC-1|32|USCAMTV001|A contoso concedeu&F|Office|RE&F|Exibição de Mountain|94043|Junte|CA|Junte|1|1|
|10.0.132.0 |SVC-1|32|USCAMTV001|A contoso concedeu&F|Office|RE&F|Exibição de Mountain|94043|Junte|CA|Junte|1|1|

Para obter mais informações sobre como formatar seu arquivo de dados, consulte [formato de arquivo de dados do locatário e estrutura do arquivo de dados de construção](turning-on-and-using-call-quality-dashboard.md#tenant-data-file-format-and-structure).

## <a name="related-topics"></a>Tópicos relacionados

[Configurar Análise de Chamada](set-up-call-analytics.md)
