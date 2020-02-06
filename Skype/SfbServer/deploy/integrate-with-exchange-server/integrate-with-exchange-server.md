---
title: Integrar o Skype for Business Server com o Exchange Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 795dc1c6-524f-4012-8b66-103b55198044
description: 'Resumo: revise as etapas de integração do Exchange Server 2016 ou do Exchange Server 2013 e do Skype for Business Server.'
ms.openlocfilehash: ad8921c9c4c5c54809aa8323f60314dfc0826061
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41791649"
---
# <a name="integrate-skype-for-business-server-with-exchange-server"></a><span data-ttu-id="eaeb7-103">Integrar o Skype for Business Server com o Exchange Server</span><span class="sxs-lookup"><span data-stu-id="eaeb7-103">Integrate Skype for Business Server with Exchange Server</span></span>

<span data-ttu-id="eaeb7-104">**Resumo:** Examine as etapas de integração do Exchange Server 2013 ou posterior e do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="eaeb7-104">**Summary:** Review integration steps for Exchange Server 2013 or later and Skype for Business Server.</span></span>

<span data-ttu-id="eaeb7-105">O Exchange Server 2013 ou posterior e o Skype for Business Server são compatíveis e integram-se perfeitamente.</span><span class="sxs-lookup"><span data-stu-id="eaeb7-105">Exchange Server 2013 or later and Skype for Business Server are compatible and integrate well.</span></span> <span data-ttu-id="eaeb7-106">Por exemplo, as informações de presença do usuário do Skype for Business podem ser reportadas no Microsoft Outlook; da mesma forma, o Skype for Business pode acessar o calendário do Outlook de um usuário, observar que o usuário tem uma reunião agendada e mostrar a presença do usuário como ocupada durante a reunião.</span><span class="sxs-lookup"><span data-stu-id="eaeb7-106">For example, Skype for Business user presence information can be reported in Microsoft Outlook; likewise, Skype for Business can access a user's Outlook calendar, notice the user has a meeting scheduled, and show the user's presence as Busy during the meeting.</span></span> <span data-ttu-id="eaeb7-107">Embora você não precise executar o Exchange Server para executar o Skype for Business Server (ou vice-versa), os dois produtos aprimoram a experiência do usuário deles.</span><span class="sxs-lookup"><span data-stu-id="eaeb7-107">Although you do not have to run Exchange Server in order to run Skype for Business Server (or vice-versa) the two products together enhance each other's user experience.</span></span>

<span data-ttu-id="eaeb7-108">Esta documentação fornece informações sobre a integração do Skype for Business Server e do Exchange Server 2016 ou do Exchange Server 2013, mas presume que a configuração inicial e a configuração desses dois produtos já aconteceram.</span><span class="sxs-lookup"><span data-stu-id="eaeb7-108">This documentation provides information on integrating Skype for Business Server and Exchange Server 2016 or Exchange Server 2013, but it assumes the initial setup and configuration of these two products has already happened.</span></span> <span data-ttu-id="eaeb7-109">Para obter detalhes sobre a implantação do Skype for Business Server, consulte o [Skype for Business Server Tech Center](https://go.microsoft.com/fwlink/p/?LinkId=246127).</span><span class="sxs-lookup"><span data-stu-id="eaeb7-109">For details about deploying Skype for Business Server see the [Skype for Business Server Tech Center](https://go.microsoft.com/fwlink/p/?LinkId=246127).</span></span> <span data-ttu-id="eaeb7-110">Para obter detalhes sobre a implantação do Exchange Server, consulte a documentação de implantação para a sua versão do Exchange.</span><span class="sxs-lookup"><span data-stu-id="eaeb7-110">For details about deploying Exchange Server see the deployment documentation for your version of Exchange.</span></span>

<span data-ttu-id="eaeb7-111">Se você estiver integrando uma instalação local do Skype for Business Server com o Microsoft Exchange Online, consulte [Configurar a integração entre o Skype for Business Server local e o Outlook Web App](outlook-web-app.md).</span><span class="sxs-lookup"><span data-stu-id="eaeb7-111">If you are integrating an on premises installation of Skype for Business Server with Microsoft Exchange Online, see [Configure integration between on-premises Skype for Business Server and Outlook Web App](outlook-web-app.md).</span></span>

<span data-ttu-id="eaeb7-112">Se você estiver integrando o Skype for Business online com o Exchange Server no local, consulte [Configurar o OAuth entre o Skype for Business Online e o Exchange no local](oauth-with-online-and-on-premises.md).</span><span class="sxs-lookup"><span data-stu-id="eaeb7-112">If you are integrating Skype for Business Online with Exchange Server on premises, see [Configure OAuth between Skype for Business Online and Exchange on premises](oauth-with-online-and-on-premises.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="eaeb7-113">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="eaeb7-113">In this section</span></span>

[<span data-ttu-id="eaeb7-114">Configurar aplicativos de parceiros no Skype for Business Server e no Exchange Server</span><span class="sxs-lookup"><span data-stu-id="eaeb7-114">Configure partner applications in Skype for Business Server and Exchange Server</span></span>](configure-partner-applications.md)

[<span data-ttu-id="eaeb7-115">Configurar o Skype for Business Server para usar o arquivamento do Exchange Server</span><span class="sxs-lookup"><span data-stu-id="eaeb7-115">Configure Skype for Business Server to use Exchange Server archiving</span></span>](use-exchange-archiving.md)

[<span data-ttu-id="eaeb7-116">Configurar o SharePoint Server para pesquisar dados arquivados do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="eaeb7-116">Configure SharePoint Server to search for archived Skype for Business data</span></span>](sharepoint-to-search-for-archived-data.md)

[<span data-ttu-id="eaeb7-117">Configurar o Skype for Business Server para usar o repositório unificado de contatos</span><span class="sxs-lookup"><span data-stu-id="eaeb7-117">Configure Skype for Business Server to use the unified contact store</span></span>](use-the-unified-contact-store.md)

[<span data-ttu-id="eaeb7-118">Configurar o uso de fotos de alta resolução no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="eaeb7-118">Configure the use of high-resolution photos in Skype for Business Server</span></span>](high-resolution-photos.md)

[<span data-ttu-id="eaeb7-119">Configurar a Unificação de mensagens do Exchange Server para a caixa postal do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="eaeb7-119">Configure Exchange Server Unified Messaging for Skype for Business Server voice mail</span></span>](exchangeunified-messaging-for-voice-mail.md)

[<span data-ttu-id="eaeb7-120">Integrando o Skype for Business Server e o Microsoft Outlook Web App 2013</span><span class="sxs-lookup"><span data-stu-id="eaeb7-120">Integrating Skype for Business Server and Microsoft Outlook Web App 2013</span></span>](https://technet.microsoft.com/library/513d4cc7-aa87-4f68-b99d-d58b63bdf242.aspx)

[<span data-ttu-id="eaeb7-121">Configurar o repositório de contatos pessoais em computadores cliente para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="eaeb7-121">Configure the personal contacts store on client computers for Skype for Business Server</span></span>](personal-contacts-store.md)

## <a name="see-also"></a><span data-ttu-id="eaeb7-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="eaeb7-122">See also</span></span>

[<span data-ttu-id="eaeb7-123">Plano para integrar o Skype for Business e o Exchange</span><span class="sxs-lookup"><span data-stu-id="eaeb7-123">Plan to integrate Skype for Business and Exchange</span></span>](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)
