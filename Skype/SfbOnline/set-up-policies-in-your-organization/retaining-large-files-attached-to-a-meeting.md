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
ms.openlocfilehash: f9a18aaf556427ccc1fad2700b40f40ff057be6a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32237514"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>Retenção de arquivos grandes anexados a um Skype para reunião de negócios

Você pode anexar arquivos a uma Skype para reunião de negócios, que os participantes, em seguida, podem abrir e baixar. Arquivos anexados a Skype para reuniões de negócios são mantidos nas caixas de correio de qualquer participante cuja caixa de correio for colocada em retenção de litígio, tem uma política de retenção do Office 365 aplicada ou é colocada em uma espera associada a um caso de eDiscovery de segurança do Office 365 &amp; Centro de conformidade. Este conteúdo é salvo pastas de **Itens recuperáveis** dos participantes em suas caixas de correio.
  
Arquivos que são mantidos em caixas de correio em espera são indexados e, portanto, podem ser pesquisados ao executar uma pesquisa de conteúdo na segurança &amp; Centro de conformidade durante a pesquisa de caixa de correio de um participante. No entanto, os arquivos anexados que são maiores do que 30 MB são divididos em dois ou mais arquivos menores e salvos como arquivos compactados (. zip). O *conteúdo* desses arquivos menores não é indexado para pesquisa e não pode ser retornados em uma pesquisa de conteúdo. No entanto, os *metadados* desses arquivos (por exemplo, o nome do arquivo e o autor) é indexado para pesquisa e podem ser retornados em uma pesquisa de conteúdo.
  
> [!IMPORTANT]
> As configurações MaxReceiveSize e MaxSendSize para uma caixa de correio do Exchange Online podem afetar a capacidade de reter arquivos grandes do Skype para reuniões de negócios. As configurações padrão de MaxReceiveSize e MaxSendSize são 36 MB e 35 MB, respectivamente. No entanto, essas configurações padrão são muito pequenas para reter qualquer arquivo de um Skype para reunião de negócios que for maior do que 30 MB. Isso ocorre porque o Exchange Online usa a codificação Base64 de anexos de mensagens e outros dados binários. Quando uma mensagem é codificada, seu tamanho será aumentado em aproximadamente 33%. Portanto, para garantir que os arquivos grandes do Skype para reuniões de negócios são mantidos, recomendamos que você aumente o valor para MaxReceiveSize e MaxSendSize para 39 MB (que é de aproximadamente 33% maior do que o limite de tamanho de 30 MB foi explicado anteriormente) para usuários que forem colocados em espera. Caso contrário, um grande arquivo anexado a uma Skype para reunião de negócios pode não ser retido. Para obter mais informações sobre como usar o **MaxReceiveSize de Set-Mailbox** e **Set-Mailbox-MaxSendSize** comandos no PowerShell do Exchange Online, consulte [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox).
  
Caixas de correio que não estiverem em espera não terão qualquer dados da reunião salvos. Por exemplo, em uma reunião de 3 pessoas em que as caixas de correio de dois participantes estão marcadas para retenção de, os dados de reunião são salvos às caixas de correio desses dois participantes, mas não à caixa de correio do terceiro participante, cuja caixa de correio não está em espera.
  
## <a name="related-topics"></a>Tópicos relacionados
[Criar políticas personalizadas de acesso externo](create-custom-external-access-policies.md)

[Transferências de arquivos ponto a ponto de bloqueio](block-point-to-point-file-transfers.md)

[Configurar políticas de clientes para sua organização](set-up-client-policies-for-your-organization.md)

[Configurar políticas de conferência na sua organização](set-up-conferencing-policies-for-your-organization.md)
  
  
 