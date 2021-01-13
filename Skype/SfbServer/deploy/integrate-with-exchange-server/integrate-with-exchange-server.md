---
title: Integrar o Skype for Business Server ao Exchange Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 6b5c63c0ad6783c11fd8fde25d1b00dc84d7e15a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833731"
---
# <a name="integrate-skype-for-business-server-with-exchange-server"></a><span data-ttu-id="00e3a-103">Integrar o Skype for Business Server ao Exchange Server</span><span class="sxs-lookup"><span data-stu-id="00e3a-103">Integrate Skype for Business Server with Exchange Server</span></span>

<span data-ttu-id="00e3a-104">**Resumo:** Revise as etapas de integração do Exchange Server 2013 ou posterior e do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="00e3a-104">**Summary:** Review integration steps for Exchange Server 2013 or later and Skype for Business Server.</span></span>

<span data-ttu-id="00e3a-105">O Exchange Server 2013 ou posterior e o Skype for Business Server são compatíveis e se integram bem.</span><span class="sxs-lookup"><span data-stu-id="00e3a-105">Exchange Server 2013 or later and Skype for Business Server are compatible and integrate well.</span></span> <span data-ttu-id="00e3a-106">Por exemplo, as informações de presença do usuário do Skype for Business podem ser relatadas no Microsoft Outlook; Da mesma forma, o Skype for Business pode acessar o calendário do Outlook de um usuário, observar que o usuário tem uma reunião agendada e mostrar a presença do usuário como Ocupado durante a reunião.</span><span class="sxs-lookup"><span data-stu-id="00e3a-106">For example, Skype for Business user presence information can be reported in Microsoft Outlook; likewise, Skype for Business can access a user's Outlook calendar, notice the user has a meeting scheduled, and show the user's presence as Busy during the meeting.</span></span> <span data-ttu-id="00e3a-107">Embora você não tenha que executar o Exchange Server para executar o Skype for Business Server (ou vice-versa), os dois produtos juntos melhoram a experiência do usuário um do outro.</span><span class="sxs-lookup"><span data-stu-id="00e3a-107">Although you do not have to run Exchange Server in order to run Skype for Business Server (or vice-versa) the two products together enhance each other's user experience.</span></span>

<span data-ttu-id="00e3a-108">Esta documentação fornece informações sobre como integrar o Skype for Business Server e o Exchange Server 2016 ou o Exchange Server 2013, mas supõe que a configuração inicial desses dois produtos já tenha ocorrido.</span><span class="sxs-lookup"><span data-stu-id="00e3a-108">This documentation provides information on integrating Skype for Business Server and Exchange Server 2016 or Exchange Server 2013, but it assumes the initial setup and configuration of these two products has already happened.</span></span> <span data-ttu-id="00e3a-109">Para obter detalhes sobre como implantar o Skype for Business Server, consulte [o Tech Center do Skype for Business Server.](https://go.microsoft.com/fwlink/p/?LinkId=246127)</span><span class="sxs-lookup"><span data-stu-id="00e3a-109">For details about deploying Skype for Business Server see the [Skype for Business Server Tech Center](https://go.microsoft.com/fwlink/p/?LinkId=246127).</span></span> <span data-ttu-id="00e3a-110">Para obter detalhes sobre como implantar o Exchange Server, consulte a documentação de implantação para sua versão do Exchange.</span><span class="sxs-lookup"><span data-stu-id="00e3a-110">For details about deploying Exchange Server see the deployment documentation for your version of Exchange.</span></span>

<span data-ttu-id="00e3a-111">Se você estiver integrando uma instalação local do Skype for Business Server ao Microsoft Exchange Online, consulte Configurar a integração entre o Skype for Business Server local e o [Outlook Web App.](outlook-web-app.md)</span><span class="sxs-lookup"><span data-stu-id="00e3a-111">If you are integrating an on premises installation of Skype for Business Server with Microsoft Exchange Online, see [Configure integration between on-premises Skype for Business Server and Outlook Web App](outlook-web-app.md).</span></span>

<span data-ttu-id="00e3a-112">Se você estiver integrando o Skype for Business Online ao Exchange Server local, consulte [Configurar o OAuth](oauth-with-online-and-on-premises.md)entre o Skype for Business Online e o Exchange no local.</span><span class="sxs-lookup"><span data-stu-id="00e3a-112">If you are integrating Skype for Business Online with Exchange Server on premises, see [Configure OAuth between Skype for Business Online and Exchange on premises](oauth-with-online-and-on-premises.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="00e3a-113">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="00e3a-113">In this section</span></span>

[<span data-ttu-id="00e3a-114">Configurar aplicativos parceiros no Skype for Business Server e no Exchange Server</span><span class="sxs-lookup"><span data-stu-id="00e3a-114">Configure partner applications in Skype for Business Server and Exchange Server</span></span>](configure-partner-applications.md)

[<span data-ttu-id="00e3a-115">Configurar o Skype for Business Server para usar o arquivamento do Exchange Server</span><span class="sxs-lookup"><span data-stu-id="00e3a-115">Configure Skype for Business Server to use Exchange Server archiving</span></span>](use-exchange-archiving.md)

[<span data-ttu-id="00e3a-116">Configurar o SharePoint Server para pesquisar dados arquivados do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="00e3a-116">Configure SharePoint Server to search for archived Skype for Business data</span></span>](sharepoint-to-search-for-archived-data.md)

[<span data-ttu-id="00e3a-117">Configurar o Skype for Business Server para usar o armazenamento unificado de contatos</span><span class="sxs-lookup"><span data-stu-id="00e3a-117">Configure Skype for Business Server to use the unified contact store</span></span>](use-the-unified-contact-store.md)

[<span data-ttu-id="00e3a-118">Configurar o uso de fotos em alta resolução no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="00e3a-118">Configure the use of high-resolution photos in Skype for Business Server</span></span>](high-resolution-photos.md)

[<span data-ttu-id="00e3a-119">Configurar a Unificação de Mensagens do Exchange Server para a caixa postal do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="00e3a-119">Configure Exchange Server Unified Messaging for Skype for Business Server voice mail</span></span>](exchangeunified-messaging-for-voice-mail.md)

[<span data-ttu-id="00e3a-120">Integrando o Skype for Business Server e o Microsoft Outlook Web App 2013</span><span class="sxs-lookup"><span data-stu-id="00e3a-120">Integrating Skype for Business Server and Microsoft Outlook Web App 2013</span></span>](https://technet.microsoft.com/library/513d4cc7-aa87-4f68-b99d-d58b63bdf242.aspx)

[<span data-ttu-id="00e3a-121">Configurar o armazenamento de contatos pessoais em computadores cliente para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="00e3a-121">Configure the personal contacts store on client computers for Skype for Business Server</span></span>](personal-contacts-store.md)

## <a name="see-also"></a><span data-ttu-id="00e3a-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="00e3a-122">See also</span></span>

[<span data-ttu-id="00e3a-123">Plano para integrar o Skype for Business e o Exchange</span><span class="sxs-lookup"><span data-stu-id="00e3a-123">Plan to integrate Skype for Business and Exchange</span></span>](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)
