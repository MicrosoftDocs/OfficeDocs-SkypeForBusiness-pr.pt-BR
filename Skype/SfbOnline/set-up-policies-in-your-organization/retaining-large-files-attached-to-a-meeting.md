---
title: Reter arquivos grandes anexados a uma Skype for Business reunião
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
description: Você pode anexar arquivos a uma reunião Skype for Business, que os participantes podem abrir e baixar. Os arquivos anexados às reuniões do Skype for Business são mantidos nas caixas de correio de qualquer participante cuja caixa de correio é colocada em Retenção de Litígio, tem uma política de retenção Microsoft 365 ou Office 365 aplicada ou é colocada em uma retenção associada a um caso de Descoberta Eletrônico no Centro de Conformidade Microsoft 365. Esse conteúdo é salvo nas pastas Itens Recuperáveis dos participantes em suas caixas de correio.
ms.openlocfilehash: 10d793afce0485de749a5609b77f2c769c55fa9d5305a4a815351ef62ff9a8b3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54316487"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>Reter arquivos grandes anexados a uma Skype for Business reunião

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Você pode anexar arquivos a uma reunião Skype for Business, que os participantes podem abrir e baixar. Os arquivos anexados às reuniões do Skype for Business são mantidos nas caixas de correio de qualquer participante cuja caixa de correio é colocada em Retenção de Litígio, tem uma política de retenção Microsoft 365 ou Office 365 aplicada ou é colocada em uma retenção associada a um caso de Descoberta Eletrônico no Centro de Conformidade Microsoft 365. Esse conteúdo é salvo nas pastas **Itens Recuperáveis** dos participantes em suas caixas de correio.
  
Os arquivos mantidos em caixas de correio em espera são indexados e, portanto, podem ser pesquisados ao executar uma Pesquisa de Conteúdo no Centro de Conformidade de Segurança ao pesquisar a caixa de correio &amp; de um participante. No entanto, arquivos anexados com mais de 30 MB são divididos em dois ou mais arquivos menores e salvos como arquivos compactados (.zip). O  *conteúdo*  desses arquivos menores não é indexado para pesquisa e pode não ser retornado em uma Pesquisa de Conteúdo. No entanto, *os metadados*  desses arquivos (como o nome do arquivo e o autor) são indexados para pesquisa e podem ser retornados em uma Pesquisa de Conteúdo.
  
> [!IMPORTANT]
> As configurações MaxReceiveSize e MaxSendSize para uma caixa de correio Exchange Online podem afetar a capacidade de reter arquivos grandes de reuniões Skype for Business reuniões. As configurações padrão para MaxReceiveSize e MaxSendSize são 36 MB e 35 MB, respectivamente. No entanto, essas configurações padrão são muito pequenas para manter qualquer arquivo de uma reunião Skype for Business que seja maior do que 30 MB. Isso se deve Exchange Online codificação Base64 de anexos de mensagens e outros dados binários. Quando uma mensagem é codificada, seu tamanho é aumentado em aproximadamente 33%. Portanto, para garantir que os arquivos grandes de reuniões de Skype for Business sejam mantidos, recomendamos que você aumente o valor para MaxReceiveSize e MaxSendSize para 39 MB (que é aproximadamente 33% maior do que o limite de tamanho de 30 MB que foi explicado anteriormente) para usuários colocados em espera. Caso contrário, um arquivo grande anexado a uma reunião Skype for Business pode não ser mantido. Para obter mais informações sobre como usar os comandos **Set-Mailbox -MaxReceiveSize** e **Set-Mailbox -MaxSendSize** no Exchange Online PowerShell, consulte [Set-Mailbox](/powershell/module/exchange/mailboxes/Set-Mailbox).
  
Caixas de correio que não estão em espera não terão nenhum dado de reunião salvo. Por exemplo, em uma reunião de três pessoas na qual as caixas de correio de dois participantes são marcadas para retenção, os dados da reunião são salvos nas caixas de correio desses dois participantes, mas não na caixa de correio do terceiro participante, cuja caixa de correio não está em espera.
  
## <a name="related-topics"></a>Tópicos relacionados
[Criar políticas personalizadas de acesso externo](create-custom-external-access-policies.md)

[Bloquear transferências de arquivo ponto a ponto](block-point-to-point-file-transfers.md)

[Configurar políticas de clientes para sua organização](set-up-client-policies-for-your-organization.md)

[Configurar políticas de conferência em sua organização](set-up-conferencing-policies-for-your-organization.md)
  
  
