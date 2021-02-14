---
title: Reter arquivos grandes anexados a uma reunião do Skype for Business
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
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: Você pode anexar arquivos a uma reunião do Skype for Business, que os participantes podem abrir e baixar. Os arquivos anexados às reuniões do Skype for Business são mantidos nas caixas de correio de qualquer participante cuja caixa de correio é colocada em Retenção de Litígio, tem uma política de retenção do Microsoft 365 ou do Office 365 aplicada ou é colocada em uma retenção associada a um caso de Descoberta Eletrônico no Centro de Conformidade do Microsoft 365. Esse conteúdo é salvo nas pastas Itens Recuperáveis dos participantes em suas caixas de correio.
ms.openlocfilehash: 23566272cec4f1afef2a0a067fdebdd2f497e312
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164070"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>Reter arquivos grandes anexados a uma reunião do Skype for Business

Você pode anexar arquivos a uma reunião do Skype for Business, que os participantes podem abrir e baixar. Os arquivos anexados às reuniões do Skype for Business são mantidos nas caixas de correio de qualquer participante cuja caixa de correio é colocada em Retenção de Litígio, tem uma política de retenção do Microsoft 365 ou do Office 365 aplicada ou é colocada em uma retenção associada a um caso de Descoberta Eletrônico no Centro de Conformidade do Microsoft 365. Esse conteúdo é salvo nas pastas Itens **Recuperáveis** dos participantes em suas caixas de correio.
  
Os arquivos mantidos em caixas de correio em espera são indexados e, portanto, podem ser pesquisados ao executar uma Pesquisa de Conteúdo no Centro de Conformidade de Segurança ao pesquisar a caixa de correio &amp; de um participante. No entanto, arquivos anexados com mais de 30 MB são divididos em dois ou mais arquivos menores e salvos como arquivos compactados (.zip). O  *conteúdo*  desses arquivos menores não é indexado para pesquisa e pode não ser retornado em uma Pesquisa de Conteúdo. No entanto, *os metadados*  desses arquivos (como o nome do arquivo e o autor) são indexados para pesquisa e podem ser retornados em uma Pesquisa de Conteúdo.
  
> [!IMPORTANT]
> As configurações MaxReceiveSize e MaxSendSize para uma caixa de correio do Exchange Online podem afetar a capacidade de reter arquivos grandes de reuniões do Skype for Business. As configurações padrão para MaxReceiveSize e MaxSendSize são de 36 MB e 35 MB, respectivamente. No entanto, essas configurações padrão são muito pequenas para manter qualquer arquivo de uma reunião do Skype for Business com mais de 30 MB. Isso porque o Exchange Online usa a codificação base64 de anexos de mensagens e outros dados binários. Quando uma mensagem é codificada, seu tamanho é aumentado em aproximadamente 33%. Portanto, para garantir que arquivos grandes de reuniões do Skype for Business sejam mantidos, recomendamos que você aumente o valor para MaxReceiveSize e MaxSendSize para 39 MB (que é aproximadamente 33% maior do que o limite de tamanho de 30 MB que foi explicado anteriormente) para usuários colocados em espera. Caso contrário, um arquivo grande anexado a uma reunião do Skype for Business pode não ser retido. Para saber mais sobre como usar os comandos **Set-Mailbox -MaxReceiveSize** e **Set-Mailbox -MaxSendSize** no PowerShell do Exchange Online, consulte [Set-Mailbox.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)
  
As caixas de correio que não estão em espera não terão os dados da reunião salvos. Por exemplo, em uma reunião de três pessoas na qual as caixas de correio de dois participantes estão marcadas para retenção, os dados da reunião são salvos nas caixas de correio desses dois participantes, mas não na caixa de correio do terceiro participante, cuja caixa de correio não está em espera.
  
## <a name="related-topics"></a>Tópicos relacionados
[Criar políticas personalizadas de acesso externo](create-custom-external-access-policies.md)

[Bloquear transferências de arquivo ponto a ponto](block-point-to-point-file-transfers.md)

[Configurar políticas de clientes para sua organização](set-up-client-policies-for-your-organization.md)

[Configurar políticas de conferência em sua organização](set-up-conferencing-policies-for-your-organization.md)
  
  
 
