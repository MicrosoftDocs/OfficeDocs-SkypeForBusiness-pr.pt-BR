---
title: Retendo arquivos grandes anexados a uma reunião do Skype for Business
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: Você pode anexar arquivos a uma reunião do Skype for Business, que os participantes podem abrir e baixar. Os arquivos anexados a reuniões do Skype for Business são mantidos nas caixas de correio de qualquer participante cuja caixa de correio é colocada em retenção de litígio, tem uma política de retenção do Office 365 aplicada ou é colocada em um Hold associado a um caso de descoberta eletrônica no Office 365 Security &amp; Centro de conformidade. Este conteúdo é salvo nas pastas de itens recuperáveis dos participantes nas suas caixas de correio.
ms.openlocfilehash: 4a8022b522f933ff8897586f632764eda77c6a67
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297755"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>Retendo arquivos grandes anexados a uma reunião do Skype for Business

Você pode anexar arquivos a uma reunião do Skype for Business, que os participantes podem abrir e baixar. Os arquivos anexados a reuniões do Skype for Business são mantidos nas caixas de correio de qualquer participante cuja caixa de correio é colocada em retenção de litígio, tem uma política de retenção do Office 365 aplicada ou é colocada em um Hold associado a um caso de descoberta eletrônica no Office 365 Security &amp; Centro de conformidade. Este conteúdo é salvo nas pastas de **itens recuperáveis** dos participantes nas suas caixas de correio.
  
Os arquivos que são mantidos nas caixas de correio em espera são indexados e, portanto, podem ser pesquisados ao executar uma &amp; pesquisa de conteúdo no centro de conformidade de segurança ao pesquisar a caixa de correio de um participante. No entanto, os arquivos anexados com mais de 30 MB são divididos em dois ou mais arquivos menores e salvos como arquivos compactados (. zip). O *conteúdo* desses arquivos menores não é indexado para pesquisa e não pode ser retornado em uma pesquisa de conteúdo. No entanto, os *metadados* desses arquivos (como o nome do arquivo e o autor) são indexados para pesquisa e podem ser retornados em uma pesquisa de conteúdo.
  
> [!IMPORTANT]
> As configurações de MaxReceiveSize e MaxSendSize para uma caixa de correio do Exchange Online podem afetar a capacidade de reter arquivos grandes das reuniões do Skype for Business. As configurações padrão para MaxReceiveSize e MaxSendSize são 36 MB e 35 MB, respectivamente. No entanto, essas configurações padrão são muito pequenas para reter qualquer arquivo de uma reunião do Skype for Business maior do que 30 MB. Isso ocorre porque o Exchange Online usa a codificação Base64 de anexos de mensagens e outros dados binários. Quando uma mensagem é codificada, seu tamanho é aumentado cerca de 33%. Portanto, para garantir que arquivos grandes das reuniões do Skype for Business sejam mantidos, recomendamos que você aumente o valor de MaxReceiveSize e MaxSendSize para 39 MB (que é aproximadamente 33% maior do que o limite de tamanho de 30 MB descrito anteriormente) para os usuários colocados em espera. Caso contrário, um arquivo grande anexado a uma reunião do Skype for Business pode não ser mantido. Para obter mais informações sobre como usar os comandos **Set-Mailbox-MaxReceiveSize** e **Set-Mailbox-MaxSendSize** no Exchange Online PowerShell, consulte [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox).
  
As caixas de correio que não estão em espera não terão dados de reunião salvos. Por exemplo, em uma reunião de três pessoas na qual as caixas de correio de dois participantes são marcadas para retenção, os dados da reunião são salvos nas caixas de correio desses dois participantes, mas não à caixa de correio do terceiro participante, cuja caixa de correio não está em espera.
  
## <a name="related-topics"></a>Tópicos relacionados
[Criar políticas personalizadas de acesso externo](create-custom-external-access-policies.md)

[Bloquear transferências de arquivo ponto a ponto](block-point-to-point-file-transfers.md)

[Configurar políticas de clientes para sua organização](set-up-client-policies-for-your-organization.md)

[Configurar políticas de conferência em sua organização](set-up-conferencing-policies-for-your-organization.md)
  
  
 