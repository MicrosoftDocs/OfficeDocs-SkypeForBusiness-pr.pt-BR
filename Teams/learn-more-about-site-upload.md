---
title: Adicionar e atualizar dados locais
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
description: Saiba como carregar em um site.
ms.custom:
- NewAdminCenter_Update
f1keywords:
- ms.teamsadmincenter.locations.reportinglabels.overview
- ms.teamsadmincenter.voice.phonenumbers.searchacquire.tooltip.location
- ms.teamsadmincenter.locations.overview
appliesto:
- Microsoft Teams
ms.openlocfilehash: bed4487a944bafb8092f63fb4582b165375a1e83
ms.sourcegitcommit: d4e69d46de564c445feb855cbee55954a7063bba
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/21/2019
ms.locfileid: "36484017"
---
<a name="adding-and-updating-locations-data"></a>Adicionar e atualizar dados locais
============================

Os locais são usados em sua organização para indicar os locais físicos de escritórios, prédios ou sites organizacionais. A página locais fornece aos administradores a capacidade de fornecer um arquivo de texto (. csv ou. tsv) que contém uma lista de locais físicos e suas sub-redes de rede associadas. Esse arquivo é usado pelo painel de análise de chamadas e de qualidade de chamada para gerar relatórios. Quando os clientes carregam o mapeamento de sub-rede, os relatórios fornecidos por esses serviços também contêm os nomes de localização, facilitando a compreensão e o uso dos relatórios para corrigir problemas em potencial.

Os dados de locais que você fornece são uma estrutura de dados única – atualmente, não há uma interface disponível para fazer edições individuais nos dados de localização. 

**Para editar a tabela de sub-redes e locais**

1. Clique em **substituir dados de localização**.
2. No painel **substituir dados de local** , clique em **selecionar um arquivo**e, em seguida, navegue até o arquivo. csv ou. tsv editado e carregue-o. 
3. Clique em **carregar**. 


Você pode baixar um modelo de exemplo [aqui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true).

Você pode usar o exemplo a seguir para ajudar a criar seu arquivo de dados. 

> [!IMPORTANT]
> Seu arquivo de dados não deve conter cabeçalhos de coluna (como rede, nome de rede, etc.). Eles são usados aqui apenas para fins informativos. </br>

|Rede|Nome da rede|Intervalo de rede|Nome do edifício|Tipo de propriedade|Tipo de edifício|Tipo de edifício de escritório|Cidade|Código Postal|País|Estado|Região|Inside Corp|Rota expressa|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0 |SVC-1|32|USCAMTV001|A contoso concedeu&F|Office|RE&F|Exibição de Mountain|94043|Junte|CA|Junte|1|1|
|10.0.130.0 |SVC-1|32|USCAMTV001|A contoso concedeu&F|Office|RE&F|Exibição de Mountain|94043|Junte|CA|Junte|1|1|
|10.0.131.0 |SVC-1|32|USCAMTV001|A contoso concedeu&F|Office|RE&F|Exibição de Mountain|94043|Junte|CA|Junte|1|1|
|10.0.132.0 |SVC-1|32|USCAMTV001|A contoso concedeu&F|Office|RE&F|Exibição de Mountain|94043|Junte|CA|Junte|1|1|


Para obter mais informações sobre como formatar seu arquivo de dados, consulte [formato de arquivo de dados do locatário e estrutura do arquivo de dados de construção](turning-on-and-using-call-quality-dashboard.md#tenant-data-file-format-and-structure).


## <a name="related-topics"></a>Tópicos relacionados

[Configurar Análise de Chamada](set-up-call-analytics.md)
