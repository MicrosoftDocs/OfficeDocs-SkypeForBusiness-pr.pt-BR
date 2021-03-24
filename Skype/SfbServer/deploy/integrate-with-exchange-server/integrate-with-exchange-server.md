---
title: Integrar o Skype for Business Server com Exchange Server
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
description: 'Resumo: revise as etapas de integração Exchange Server 2016 ou Exchange Server 2013 e Skype for Business Server.'
ms.openlocfilehash: b19aa73e62b12674551690b716144fb67b4cd715
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104847"
---
# <a name="integrate-skype-for-business-server-with-exchange-server"></a><span data-ttu-id="7c328-103">Integrar o Skype for Business Server com Exchange Server</span><span class="sxs-lookup"><span data-stu-id="7c328-103">Integrate Skype for Business Server with Exchange Server</span></span>

<span data-ttu-id="7c328-104">**Resumo:** Revise as etapas de integração Exchange Server 2013 ou posterior e Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="7c328-104">**Summary:** Review integration steps for Exchange Server 2013 or later and Skype for Business Server.</span></span>

<span data-ttu-id="7c328-105">Exchange Server 2013 ou posterior e o Skype for Business Server são compatíveis e se integram bem.</span><span class="sxs-lookup"><span data-stu-id="7c328-105">Exchange Server 2013 or later and Skype for Business Server are compatible and integrate well.</span></span> <span data-ttu-id="7c328-106">Por exemplo, informações de presença do usuário do Skype for Business podem ser relatadas no Microsoft Outlook; Da mesma forma, o Skype for Business pode acessar o calendário do Outlook de um usuário, perceber que o usuário tem uma reunião agendada e mostrar a presença do usuário como Ocupado durante a reunião.</span><span class="sxs-lookup"><span data-stu-id="7c328-106">For example, Skype for Business user presence information can be reported in Microsoft Outlook; likewise, Skype for Business can access a user's Outlook calendar, notice the user has a meeting scheduled, and show the user's presence as Busy during the meeting.</span></span> <span data-ttu-id="7c328-107">Embora você não tenha que executar Exchange Server para executar o Skype for Business Server (ou vice-versa), os dois produtos juntos aprimoram a experiência do usuário uns dos outros.</span><span class="sxs-lookup"><span data-stu-id="7c328-107">Although you do not have to run Exchange Server in order to run Skype for Business Server (or vice-versa) the two products together enhance each other's user experience.</span></span>

<span data-ttu-id="7c328-108">Esta documentação fornece informações sobre como integrar o Skype for Business Server e o Exchange Server 2016 ou Exchange Server 2013, mas supõe que a configuração inicial desses dois produtos já tenha ocorrido.</span><span class="sxs-lookup"><span data-stu-id="7c328-108">This documentation provides information on integrating Skype for Business Server and Exchange Server 2016 or Exchange Server 2013, but it assumes the initial setup and configuration of these two products has already happened.</span></span> <span data-ttu-id="7c328-109">Para obter detalhes sobre como implantar o Skype for Business Server, consulte o [Centro de Tecnologia do Skype for Business Server.](../../../Hub/index.yml)</span><span class="sxs-lookup"><span data-stu-id="7c328-109">For details about deploying Skype for Business Server see the [Skype for Business Server Tech Center](../../../Hub/index.yml).</span></span> <span data-ttu-id="7c328-110">Para obter detalhes sobre a implantação Exchange Server consulte a documentação de implantação da sua versão do Exchange.</span><span class="sxs-lookup"><span data-stu-id="7c328-110">For details about deploying Exchange Server see the deployment documentation for your version of Exchange.</span></span>

<span data-ttu-id="7c328-111">Se você estiver integrando uma instalação local do Skype for Business Server com o Microsoft Exchange Online, consulte Configure integration [between on-premises Skype for Business Server and Outlook Web App](outlook-web-app.md).</span><span class="sxs-lookup"><span data-stu-id="7c328-111">If you are integrating an on premises installation of Skype for Business Server with Microsoft Exchange Online, see [Configure integration between on-premises Skype for Business Server and Outlook Web App](outlook-web-app.md).</span></span>

<span data-ttu-id="7c328-112">Se você estiver integrando o Skype for Business Online com Exchange Server local, consulte [Configure OAuth between Skype for Business Online and Exchange on premises](oauth-with-online-and-on-premises.md).</span><span class="sxs-lookup"><span data-stu-id="7c328-112">If you are integrating Skype for Business Online with Exchange Server on premises, see [Configure OAuth between Skype for Business Online and Exchange on premises](oauth-with-online-and-on-premises.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="7c328-113">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="7c328-113">In this section</span></span>

[<span data-ttu-id="7c328-114">Configurar aplicativos parceiros no Skype for Business Server e Exchange Server</span><span class="sxs-lookup"><span data-stu-id="7c328-114">Configure partner applications in Skype for Business Server and Exchange Server</span></span>](configure-partner-applications.md)

[<span data-ttu-id="7c328-115">Configurar o Skype for Business Server para usar Exchange Server arquivamento</span><span class="sxs-lookup"><span data-stu-id="7c328-115">Configure Skype for Business Server to use Exchange Server archiving</span></span>](use-exchange-archiving.md)

[<span data-ttu-id="7c328-116">Configurar o SharePoint Server para pesquisar dados arquivados do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="7c328-116">Configure SharePoint Server to search for archived Skype for Business data</span></span>](sharepoint-to-search-for-archived-data.md)

[<span data-ttu-id="7c328-117">Configurar o Skype for Business Server para usar o armazenamento unificado de contatos</span><span class="sxs-lookup"><span data-stu-id="7c328-117">Configure Skype for Business Server to use the unified contact store</span></span>](use-the-unified-contact-store.md)

[<span data-ttu-id="7c328-118">Configurar o uso de fotos de alta resolução no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7c328-118">Configure the use of high-resolution photos in Skype for Business Server</span></span>](high-resolution-photos.md)

[<span data-ttu-id="7c328-119">Configurar Exchange Server Unificação de Mensagens para a caixa postal do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7c328-119">Configure Exchange Server Unified Messaging for Skype for Business Server voice mail</span></span>](exchangeunified-messaging-for-voice-mail.md)

<span data-ttu-id="7c328-120">[Integrando o Skype for Business Server e o Microsoft Outlook Web App 2013](/previous-versions/office/communications/jj688055(v=ocs.16))</span><span class="sxs-lookup"><span data-stu-id="7c328-120">[Integrating Skype for Business Server and Microsoft Outlook Web App 2013](/previous-versions/office/communications/jj688055(v=ocs.16))</span></span>

[<span data-ttu-id="7c328-121">Configurar o armazenamento de contatos pessoais em computadores cliente para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7c328-121">Configure the personal contacts store on client computers for Skype for Business Server</span></span>](personal-contacts-store.md)

## <a name="see-also"></a><span data-ttu-id="7c328-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="7c328-122">See also</span></span>

[<span data-ttu-id="7c328-123">Plano para integrar o Skype for Business e o Exchange</span><span class="sxs-lookup"><span data-stu-id="7c328-123">Plan to integrate Skype for Business and Exchange</span></span>](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)