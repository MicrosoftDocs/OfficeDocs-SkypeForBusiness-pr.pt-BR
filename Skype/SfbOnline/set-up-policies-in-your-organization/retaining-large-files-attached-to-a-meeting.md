---
title: "Retenção de arquivos grandes anexados a um Skype para reunião de negócios"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: brendonb, markjjo
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 12203a1a-4a9f-4838-88c5-3740ea16ed8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: "Você pode anexar arquivos a uma Skype para reunião de negócios, que os participantes, em seguida, podem abrir e baixar. Arquivos anexados a Skype para reuniões de negócios são mantidos nas caixas de correio de qualquer participante cuja caixa de correio for colocada em retenção de litígio, tem uma política de retenção do Office 365 aplicada ou é colocada em uma espera associada a um caso de eDiscovery de segurança do Office 365 &amp; Centro de conformidade. Este conteúdo é salvo pastas de itens recuperáveis dos participantes em suas caixas de correio."
ms.openlocfilehash: fb20055106362143b5c4573115e095637d873599
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/27/2018
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a><span data-ttu-id="8901f-105">Retenção de arquivos grandes anexados a um Skype para reunião de negócios</span><span class="sxs-lookup"><span data-stu-id="8901f-105">Retaining large files attached to a Skype for Business meeting</span></span>

<span data-ttu-id="8901f-106">Você pode anexar arquivos a uma Skype para reunião de negócios, que os participantes, em seguida, podem abrir e baixar.</span><span class="sxs-lookup"><span data-stu-id="8901f-106">You can attach files to a Skype for Business meeting, which participants can then open and download.</span></span> <span data-ttu-id="8901f-107">Arquivos anexados a Skype para reuniões de negócios são mantidos nas caixas de correio de qualquer participante cuja caixa de correio for colocada em retenção de litígio, tem uma política de retenção do Office 365 aplicada ou é colocada em uma espera associada a um caso de eDiscovery de segurança do Office 365 &amp; Centro de conformidade.</span><span class="sxs-lookup"><span data-stu-id="8901f-107">Files attached to Skype for Business meetings are retained in the mailboxes of any participant whose mailbox is placed on Litigation Hold, has an Office 365 retention policy applied, or is placed on a hold associated with an eDiscovery case in the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="8901f-108">Este conteúdo é salvo pastas de **Itens recuperáveis** dos participantes em suas caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="8901f-108">This content is saved to participants' **Recoverable Items** folders in their mailboxes.</span></span>
  
<span data-ttu-id="8901f-109">Arquivos que são mantidos em caixas de correio em espera são indexados e, portanto, podem ser pesquisados ao executar uma pesquisa de conteúdo na segurança &amp; Centro de conformidade durante a pesquisa de caixa de correio de um participante.</span><span class="sxs-lookup"><span data-stu-id="8901f-109">Files that are retained in mailboxes on hold are indexed and can therefore be searched when running a Content Search in the Security &amp; Compliance Center when searching a participant's mailbox.</span></span> <span data-ttu-id="8901f-110">No entanto, os arquivos anexos maiores que 39 MB são divididos em dois ou mais arquivos menores e salvos como arquivos compactados (. zip).</span><span class="sxs-lookup"><span data-stu-id="8901f-110">However, attached files that are larger than 39 MB are split into two or more smaller files and saved as compressed (.zip) files.</span></span> <span data-ttu-id="8901f-111">O *conteúdo* desses arquivos menores não é indexado para pesquisa e não pode ser retornados em uma pesquisa de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="8901f-111">The  *content*  of these smaller files is not indexed for search, and might not be returned in a Content Search.</span></span> <span data-ttu-id="8901f-112">No entanto, os *metadados* desses arquivos (por exemplo, o nome do arquivo e o autor) é indexado para pesquisa e podem ser retornados em uma pesquisa de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="8901f-112">However, the *metadata*  of these files (such as the file name and author) is indexed for search, and might be returned in a Content Search.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8901f-113">Se a caixa de correio está cheia ou o administrador de locatário tiver configurado MaxSendSize para ser menor do que 39 MB, carregado o arquivo de dados não serão mantidos em todas as.</span><span class="sxs-lookup"><span data-stu-id="8901f-113">If the mailbox is full or the tenant admin has configured MaxSendSize to be smaller than 39 MB, uploaded file data will not be retained at all.</span></span> <span data-ttu-id="8901f-114">O padrão MaxSendSize é 150 MB, mas os administradores de Inquilino podem configurar MaxSendSize para ser tão pequeno quanto 1 MB.</span><span class="sxs-lookup"><span data-stu-id="8901f-114">The default MaxSendSize is 150 MB, but tenant admins can configure MaxSendSize to be as small as 1 MB.</span></span> 
  
<span data-ttu-id="8901f-115">Caixas de correio que não estiverem em espera não terão qualquer dados da reunião salvos.</span><span class="sxs-lookup"><span data-stu-id="8901f-115">Mailboxes that are not on hold will not have any meeting data saved.</span></span> <span data-ttu-id="8901f-116">Por exemplo, em uma reunião de 3 pessoas em que as caixas de correio de dois participantes estão marcadas para retenção de, os dados de reunião são salvos às caixas de correio desses dois participantes, mas não à caixa de correio do terceiro participante, cuja caixa de correio não está em espera.</span><span class="sxs-lookup"><span data-stu-id="8901f-116">For example, in a three-person meeting in which the mailboxes of two participants are marked for retention, the meeting data is saved to the mailboxes of those two participants, but not to the mailbox of the third participant, whose mailbox is not on hold.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="8901f-117">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="8901f-117">Related topics</span></span>
[<span data-ttu-id="8901f-118">Criar políticas personalizadas de acesso externo</span><span class="sxs-lookup"><span data-stu-id="8901f-118">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="8901f-119">Transferências de arquivos ponto a ponto de bloqueio</span><span class="sxs-lookup"><span data-stu-id="8901f-119">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="8901f-120">Configurar políticas de clientes para sua organização</span><span class="sxs-lookup"><span data-stu-id="8901f-120">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="8901f-121">Configurar políticas de conferência na sua organização</span><span class="sxs-lookup"><span data-stu-id="8901f-121">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)
  
## <a name="feedback"></a><span data-ttu-id="8901f-122">Comentários?</span><span class="sxs-lookup"><span data-stu-id="8901f-122">Feedback?</span></span>
<span data-ttu-id="8901f-123">Para fornecer comentários sobre o produto ou para saber como estamos indo, consulte [Skype para comentários de negócios](https://www.skypefeedback.com).</span><span class="sxs-lookup"><span data-stu-id="8901f-123">To provide product feedback or to let us know how we're doing, see [Skype for Business Feedback](https://www.skypefeedback.com).</span></span>