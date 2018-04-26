---
title: Integrar o Skype for Business Server 2015 com o Exchange Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 795dc1c6-524f-4012-8b66-103b55198044
description: 'Summary: Review integration steps for Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server 2015.'
ms.openlocfilehash: c8cbecd6b78e3dc14ad2133a93d9fc2d1f6bb3d6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="integrate-skype-for-business-server-2015-with-exchange-server"></a><span data-ttu-id="7b534-103">Integrar o Skype for Business Server 2015 com o Exchange Server</span><span class="sxs-lookup"><span data-stu-id="7b534-103">Integrate Skype for Business Server 2015 with Exchange Server</span></span>
 
<span data-ttu-id="7b534-104">**Summary:** Review integration steps for Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7b534-104">**Summary:** Review integration steps for Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="7b534-105">Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server 2015 are compatible and integrate well.</span><span class="sxs-lookup"><span data-stu-id="7b534-105">Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server 2015 are compatible and integrate well.</span></span> <span data-ttu-id="7b534-106">As informações de presença do usuário do , por exemplo, podem ser relatadas no Microsoft Outlook; da mesma forma, o  pode acessar um calendário do Outlook do usuário, verificar que o usuário tem uma reunião agendada e mostrar a presença do usuário como Ocupado durante a reunião.</span><span class="sxs-lookup"><span data-stu-id="7b534-106">For example,  user presence information can be reported in Microsoft Outlook; likewise,  can access a user's Outlook calendar, notice the user has a meeting scheduled, and show the user's presence as Busy during the meeting.</span></span> <span data-ttu-id="7b534-107">Apesar de não ser necessário executar o  para poder executar o  (ou vice-versa), os dois produtos juntos aprimoram a experiência do usuário de cada um.</span><span class="sxs-lookup"><span data-stu-id="7b534-107">Although you do not have to run  in order to run  (or vice-versa) the two products together enhance each other's user experience.</span></span>
  
<span data-ttu-id="7b534-108">This documentation provides information on integrating Skype for Business Server 2015 and Exchange Server 2016 or Exchange Server 2013, but it assumes the initial setup and configuration of these two products has already happened.</span><span class="sxs-lookup"><span data-stu-id="7b534-108">This documentation provides information on integrating Skype for Business Server 2015 and Exchange Server 2016 or Exchange Server 2013, but it assumes the initial setup and configuration of these two products has already happened.</span></span> <span data-ttu-id="7b534-109">For details about deploying Skype for Business Server 2015 see the [Skype for Business Server 2015 Tech Center](https://go.microsoft.com/fwlink/p/?LinkId=246127).</span><span class="sxs-lookup"><span data-stu-id="7b534-109">For details about deploying Skype for Business Server 2015 see the [Skype for Business Server 2015 Tech Center](https://go.microsoft.com/fwlink/p/?LinkId=246127).</span></span> <span data-ttu-id="7b534-110">For details about deploying Exchange Server see the deployment documentation for your version of Exchange.</span><span class="sxs-lookup"><span data-stu-id="7b534-110">For details about deploying Exchange Server see the deployment documentation for your version of Exchange.</span></span>
  
<span data-ttu-id="7b534-111">If you are integrating an on premises installation of Skype for Business Server 2015 with Microsoft Exchange Online, see [Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App](outlook-web-app.md).</span><span class="sxs-lookup"><span data-stu-id="7b534-111">If you are integrating an on premises installation of Skype for Business Server 2015 with Microsoft Exchange Online, see [Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App](outlook-web-app.md).</span></span>
  
<span data-ttu-id="7b534-112">If you are integrating Skype for Business Online with Exchange Server on premises, see [Configure OAuth between Skype for Business Online and Exchange on premises](oauth-with-online-and-on-premises.md).</span><span class="sxs-lookup"><span data-stu-id="7b534-112">If you are integrating Skype for Business Online with Exchange Server on premises, see [Configure OAuth between Skype for Business Online and Exchange on premises](oauth-with-online-and-on-premises.md).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="7b534-113">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="7b534-113">In this section</span></span>

[<span data-ttu-id="7b534-114">Configurar aplicativos de parceiros no Skype for Business Server 2015 e Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="7b534-114">Configure partner applications in Skype for Business Server 2015 and Microsoft Exchange Server</span></span>](configure-partner-applications.md)
  
[<span data-ttu-id="7b534-115">Configurar o Skype for Business Server 2015 para usar o arquivamento do Exchange Server</span><span class="sxs-lookup"><span data-stu-id="7b534-115">Configure Skype for Business Server 2015  to use Exchange Server archiving</span></span>](use-exchange-archiving.md)
  
[<span data-ttu-id="7b534-116">Configurar o SharePoint Server para pesquisar dados arquivados do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="7b534-116">Configure SharePoint Server to search for archived Skype for Business data</span></span>](sharepoint-to-search-for-archived-data.md)
  
[<span data-ttu-id="7b534-117">Configurar o Skype for Business Server 2015 para usar o repositório unificado de contatos</span><span class="sxs-lookup"><span data-stu-id="7b534-117">Configure Skype for Business Server 2015  to use the unified contact store</span></span>](use-the-unified-contact-store.md)
  
[<span data-ttu-id="7b534-118">Configurar o uso de fotos de alta resolução no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7b534-118">Configure the use of high-resolution photos in Skype for Business Server 2015</span></span>](high-resolution-photos.md)
  
[<span data-ttu-id="7b534-119">Configurar a Unificação de Mensagens do Exchange Server para a caixa postal do Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7b534-119">Configure Exchange Server Unified Messaging for Skype for Business Server 2015 voice mail</span></span>](exchangeunified-messaging-for-voice-mail.md)
  
[<span data-ttu-id="7b534-120">Integrar o Skype for Business Server 2015 e o Microsoft Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="7b534-120">Integrate Skype for Business Server 2015 and Microsoft Outlook Web App</span></span>](http://technet.microsoft.com/library/513d4cc7-aa87-4f68-b99d-d58b63bdf242.aspx)
  
[<span data-ttu-id="7b534-121">Configurar o repositório de contatos pessoais em computadores cliente para o Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7b534-121">Configure the personal contacts store on client computers for Skype for Business Server 2015</span></span>](personal-contacts-store.md)
  
## <a name="see-also"></a><span data-ttu-id="7b534-122">Consulte também</span><span class="sxs-lookup"><span data-stu-id="7b534-122">See also</span></span>

#### 

[<span data-ttu-id="7b534-123">Plano para integrar o Skype for Business e o Exchange</span><span class="sxs-lookup"><span data-stu-id="7b534-123">Plan to integrate Skype for Business and Exchange</span></span>](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)

