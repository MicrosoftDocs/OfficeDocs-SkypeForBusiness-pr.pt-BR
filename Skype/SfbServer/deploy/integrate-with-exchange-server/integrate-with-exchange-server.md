---
title: Integrar Skype para Business Server com o Exchange Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 795dc1c6-524f-4012-8b66-103b55198044
description: 'Resumo: Revise as etapas de integração para Exchange Server 2016 ou Exchange Server 2013 e Skype para Business Server.'
ms.openlocfilehash: d08bf95894febb224e88cc1c40dce1f693b99704
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873531"
---
# <a name="integrate-skype-for-business-server-with-exchange-server"></a><span data-ttu-id="4945d-103">Integrar Skype para Business Server com o Exchange Server</span><span class="sxs-lookup"><span data-stu-id="4945d-103">Integrate Skype for Business Server with Exchange Server</span></span>

<span data-ttu-id="4945d-104">**Resumo:** Revisar as etapas de integração do Exchange Server 2013 ou posterior e Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="4945d-104">**Summary:** Review integration steps for Exchange Server 2013 or later and Skype for Business Server.</span></span>

<span data-ttu-id="4945d-105">Exchange Server 2013 ou posterior e Skype para Business Server são compatíveis e bem integram.</span><span class="sxs-lookup"><span data-stu-id="4945d-105">Exchange Server 2013 or later and Skype for Business Server are compatible and integrate well.</span></span> <span data-ttu-id="4945d-106">Por exemplo, Skype para informações de presença do usuário de negócios pode ser informado no Microsoft Outlook; da mesma forma, Skype para negócios pode acessar o calendário do Outlook do usuário, observe que o usuário tem uma reunião agendada e mostrar a presença do usuário como ocupado durante a reunião.</span><span class="sxs-lookup"><span data-stu-id="4945d-106">For example, Skype for Business user presence information can be reported in Microsoft Outlook; likewise, Skype for Business can access a user's Outlook calendar, notice the user has a meeting scheduled, and show the user's presence as Busy during the meeting.</span></span> <span data-ttu-id="4945d-107">Embora você não precisa executar o Exchange Server para poder executar Skype para Business Server (ou vice-versa) os dois produtos juntos Aprimore a experiência do usuário uns dos outros.</span><span class="sxs-lookup"><span data-stu-id="4945d-107">Although you do not have to run Exchange Server in order to run Skype for Business Server (or vice-versa) the two products together enhance each other's user experience.</span></span>

<span data-ttu-id="4945d-108">Esta documentação fornece informações sobre a integração do Skype para Business Server e o Exchange Server 2016 ou o Exchange Server 2013, mas supõe que a configuração inicial e a configuração desses dois produtos já tiver acontecido.</span><span class="sxs-lookup"><span data-stu-id="4945d-108">This documentation provides information on integrating Skype for Business Server and Exchange Server 2016 or Exchange Server 2013, but it assumes the initial setup and configuration of these two products has already happened.</span></span> <span data-ttu-id="4945d-109">Para obter detalhes sobre como implantar o Skype para Business Server, consulte o [Skype para Business Server Tech Center](https://go.microsoft.com/fwlink/p/?LinkId=246127).</span><span class="sxs-lookup"><span data-stu-id="4945d-109">For details about deploying Skype for Business Server see the [Skype for Business Server Tech Center](https://go.microsoft.com/fwlink/p/?LinkId=246127).</span></span> <span data-ttu-id="4945d-110">Para obter detalhes sobre como implantar o Exchange Server, consulte a documentação de implantação para a sua versão do Exchange.</span><span class="sxs-lookup"><span data-stu-id="4945d-110">For details about deploying Exchange Server see the deployment documentation for your version of Exchange.</span></span>

<span data-ttu-id="4945d-111">Se você estiver integrando uma instalação local diante do Skype para Business Server com o Microsoft Exchange Online, consulte [Configure de integração entre o local Skype para Business Server e o Outlook Web App](outlook-web-app.md).</span><span class="sxs-lookup"><span data-stu-id="4945d-111">If you are integrating an on premises installation of Skype for Business Server with Microsoft Exchange Online, see [Configure integration between on-premises Skype for Business Server and Outlook Web App](outlook-web-app.md).</span></span>

<span data-ttu-id="4945d-112">Se você estiver integrando Skype para negócios Online com o Exchange Server no local, consulte [Configure OAuth entre Skype para Business Online e do Exchange no local](oauth-with-online-and-on-premises.md).</span><span class="sxs-lookup"><span data-stu-id="4945d-112">If you are integrating Skype for Business Online with Exchange Server on premises, see [Configure OAuth between Skype for Business Online and Exchange on premises](oauth-with-online-and-on-premises.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="4945d-113">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="4945d-113">In this section</span></span>

[<span data-ttu-id="4945d-114">Configurar aplicativos de parceiros no Skype para Business Server e o Exchange Server</span><span class="sxs-lookup"><span data-stu-id="4945d-114">Configure partner applications in Skype for Business Server and Exchange Server</span></span>](configure-partner-applications.md)

[<span data-ttu-id="4945d-115">Configurar Skype para Business Server usar o arquivamento do Exchange Server</span><span class="sxs-lookup"><span data-stu-id="4945d-115">Configure Skype for Business Server to use Exchange Server archiving</span></span>](use-exchange-archiving.md)

[<span data-ttu-id="4945d-116">Configurar o SharePoint Server para pesquisar dados arquivados do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="4945d-116">Configure SharePoint Server to search for archived Skype for Business data</span></span>](sharepoint-to-search-for-archived-data.md)

[<span data-ttu-id="4945d-117">Configurar o Skype for Business Server para usar o repositório unificado de contatos</span><span class="sxs-lookup"><span data-stu-id="4945d-117">Configure Skype for Business Server to use the unified contact store</span></span>](use-the-unified-contact-store.md)

[<span data-ttu-id="4945d-118">Configurar o uso de fotos de alta resolução no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="4945d-118">Configure the use of high-resolution photos in Skype for Business Server</span></span>](high-resolution-photos.md)

[<span data-ttu-id="4945d-119">Configurar Unificação de mensagens do Exchange Server para Skype para caixa postal Business Server</span><span class="sxs-lookup"><span data-stu-id="4945d-119">Configure Exchange Server Unified Messaging for Skype for Business Server voice mail</span></span>](exchangeunified-messaging-for-voice-mail.md)

[<span data-ttu-id="4945d-120">Integração do Skype para Business Server e o Microsoft Outlook Web App 2013</span><span class="sxs-lookup"><span data-stu-id="4945d-120">Integrating Skype for Business Server and Microsoft Outlook Web App 2013</span></span>](https://technet.microsoft.com/library/513d4cc7-aa87-4f68-b99d-d58b63bdf242.aspx)

[<span data-ttu-id="4945d-121">Configurar o repositório de contatos pessoais nos computadores cliente para Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="4945d-121">Configure the personal contacts store on client computers for Skype for Business Server</span></span>](personal-contacts-store.md)

## <a name="see-also"></a><span data-ttu-id="4945d-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4945d-122">See also</span></span>

[<span data-ttu-id="4945d-123">Plano para integrar o Skype for Business e o Exchange</span><span class="sxs-lookup"><span data-stu-id="4945d-123">Plan to integrate Skype for Business and Exchange</span></span>](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)
