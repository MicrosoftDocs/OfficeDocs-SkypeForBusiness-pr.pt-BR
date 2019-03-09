---
title: Adicionar e atualizar dados de locais
author: tonysmit
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Aprenda a carregar a um site.
ms.custom:
- NewAdminCenter_Update
f1keywords: ms.teamsadmincenter.locations.overview
appliesto:
- Microsoft Teams
ms.openlocfilehash: a84b022c7b5553a15ff8862a175ba5f856cdd149
ms.sourcegitcommit: f3b41e7abafc84571bd9e8267d41decc0fe78e4a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/08/2019
ms.locfileid: "30494073"
---
<a name="adding-and-updating-locations-data"></a>Adicionar e atualizar dados de locais
============================

Locais são usados em sua organização para indicar os locais físicos dos escritórios, prédios ou sites organizacionais. A página locais oferece os administradores a capacidade de fornecer um arquivo de texto (. csv ou. tsv) contendo uma lista de locais físicos e seus subredes associadas. Este arquivo é usado pelo análise de chamada e o painel de controle de qualidade de chamada para geração de relatórios. Quando os clientes carregar sua mapeamento de sub-rede, os relatórios fornecidos por esses serviços irá conter os nomes de local também, tornando os relatórios mais fácil de entender e usar para a correção de quaisquer problemas potenciais.

Os dados de locais fornecidos serão uma estrutura de dados único – no momento, não há nenhuma interface disponível faça edições individuais em dados de local. 

**Editar a tabela de locais e sub-redes**

1. Clique em **Substituir os dados de locais**.
2. No painel de **Substituir os dados de local** , clique em **Selecionar um arquivo**e, em seguida, navegue até e carregar seu. csv editadas ou o arquivo. tsv. 
3. Clique em **carregar**. 


Você pode baixar um modelo de exemplo [aqui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true).

Você pode usar o exemplo a seguir para ajudar a criar seu arquivo de dados. 

> [!IMPORTANT]
> O arquivo de dados não deve conter cabeçalhos de coluna (por exemplo, rede, o nome de rede, etc.). Eles são usados aqui apenas para fins informativos. </br>

|Rede|Nome da rede|Intervalo de rede|Nome do edifício|Tipo de propriedade|Tipo de construção|Tipo de construção do Office|Cidade|Código Postal|País|Estado|Região|Interior Corp|Rota Express|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0 |SVC-1|32|USCAMTV001|Contoso concessão RE&F|Office|RE&F|Modo de exibição das Montanhas|94043 e.u.a.|CONOSCO|CA|CONOSCO|1|1|
|10.0.130.0 |SVC-1|32|USCAMTV001|Contoso concessão RE&F|Office|RE&F|Modo de exibição das Montanhas|94043 e.u.a.|CONOSCO|CA|CONOSCO|1|1|
|10.0.131.0 |SVC-1|32|USCAMTV001|Contoso concessão RE&F|Office|RE&F|Modo de exibição das Montanhas|94043 e.u.a.|CONOSCO|CA|CONOSCO|1|1|
|10.0.132.0 |SVC-1|32|USCAMTV001|Contoso concessão RE&F|Office|RE&F|Modo de exibição das Montanhas|94043 e.u.a.|CONOSCO|CA|CONOSCO|1|1|


Para obter mais informações sobre a formatação de seu arquivo de dados, consulte o [formato e a estrutura do arquivo de dados de criação do arquivo de dados de Inquilino](turning-on-and-using-call-quality-dashboard.md#tenant-data-file-format-and-building-data-file-structure).


## <a name="related-topics"></a>Tópicos relacionados

[Configurar Análise de Chamada](set-up-call-analytics.md)