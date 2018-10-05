---
title: Retenção de arquivos grandes anexados a um Skype para reunião de negócios
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: brendonb, markjjo
ms.topic: article
ms.assetid: 12203a1a-4a9f-4838-88c5-3740ea16ed8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: Você pode anexar arquivos a uma Skype para reunião de negócios, que os participantes, em seguida, podem abrir e baixar. Arquivos anexados a Skype para reuniões de negócios são mantidos nas caixas de correio de qualquer participante cuja caixa de correio for colocada em retenção de litígio, tem uma política de retenção do Office 365 aplicada ou é colocada em uma espera associada a um caso de eDiscovery de segurança do Office 365 &amp; Centro de conformidade. Este conteúdo é salvo pastas de itens recuperáveis dos participantes em suas caixas de correio.
ms.openlocfilehash: 103fa8b9602c4db1c5399a97a94613ac8e7b8621
ms.sourcegitcommit: 2e11749734ff26b18709a1442b2c417f33430144
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/05/2018
ms.locfileid: "25429377"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>Retenção de arquivos grandes anexados a um Skype para reunião de negócios

Você pode anexar arquivos a uma Skype para reunião de negócios, que os participantes, em seguida, podem abrir e baixar. Arquivos anexados a Skype para reuniões de negócios são mantidos nas caixas de correio de qualquer participante cuja caixa de correio for colocada em retenção de litígio, tem uma política de retenção do Office 365 aplicada ou é colocada em uma espera associada a um caso de eDiscovery de segurança do Office 365 &amp; Centro de conformidade. Este conteúdo é salvo pastas de **Itens recuperáveis** dos participantes em suas caixas de correio.
  
Arquivos que são mantidos em caixas de correio em espera são indexados e, portanto, podem ser pesquisados ao executar uma pesquisa de conteúdo na segurança &amp; Centro de conformidade durante a pesquisa de caixa de correio de um participante. No entanto, os arquivos anexados que são maiores do que 30 MB são divididos em dois ou mais arquivos menores e salvos como arquivos compactados (. zip). O *conteúdo* desses arquivos menores não é indexado para pesquisa e não pode ser retornados em uma pesquisa de conteúdo. No entanto, os *metadados* desses arquivos (por exemplo, o nome do arquivo e o autor) é indexado para pesquisa e podem ser retornados em uma pesquisa de conteúdo.
  
> [!NOTE]
> Se a caixa de correio está cheia ou o administrador de locatário tiver configurado MaxSendSize para ser menor do que 30 MB, os dados de arquivo carregado não serão mantidos nisso. O padrão MaxSendSize é 150 MB, mas os administradores de Inquilino podem configurar MaxSendSize para ser tão pequeno quanto 1 MB. 
  
Caixas de correio que não estiverem em espera não terão qualquer dados da reunião salvos. Por exemplo, em uma reunião de 3 pessoas em que as caixas de correio de dois participantes estão marcadas para retenção de, os dados de reunião são salvos às caixas de correio desses dois participantes, mas não à caixa de correio do terceiro participante, cuja caixa de correio não está em espera.
  
## <a name="related-topics"></a>Tópicos relacionados
[Criar políticas personalizadas de acesso externo](create-custom-external-access-policies.md)

[Transferências de arquivos ponto a ponto de bloqueio](block-point-to-point-file-transfers.md)

[Configurar políticas de clientes para sua organização](set-up-client-policies-for-your-organization.md)

[Configurar políticas de conferência na sua organização](set-up-conferencing-policies-for-your-organization.md)
  
  
 