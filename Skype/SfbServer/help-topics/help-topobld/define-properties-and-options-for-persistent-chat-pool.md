---
title: Definir Propriedades e Opções para Pool de Chat Persistente
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 'Você pode configurar opções para o servidor de Chat persistente ou o pool de servidor de Chat persistente definindo as seguintes propriedades:'
ms.openlocfilehash: 380a1e34e041368d4520cd5c8ecea5b18284ef51
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32226918"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a><span data-ttu-id="ff03f-103">Definir Propriedades e Opções para Pool de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="ff03f-103">Define Properties and Options for Persistent Chat Pool</span></span>
 
<span data-ttu-id="ff03f-104">Você pode configurar opções para o servidor de Chat persistente ou o pool de servidor de Chat persistente definindo as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="ff03f-104">You configure options for your Persistent Chat Server or Persistent Chat Server pool by defining the following properties:</span></span>
  
 <span data-ttu-id="ff03f-105">**Nome para exibição do pool de Chat persistente**: uma propriedade necessária que define um nome amigável para o usuário que será exibido para esse servidor de Chat persistente ou o pool do servidor de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="ff03f-105">**Display name of the Persistent Chat pool**: A required property that defines a user friendly name that will be displayed for this Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="ff03f-106">**Porta de Chat persistente**: uma propriedade necessária que definirá a porta de número em que este servidor de Chat persistente ou servidor de Chat persistente pool escutará.</span><span class="sxs-lookup"><span data-stu-id="ff03f-106">**Persistent Chat port**: A required property that will define the port number that this Persistent Chat Server or Persistent Chat Server pool will listen on.</span></span>
  
 <span data-ttu-id="ff03f-107">**Habilitar a conformidade**: marque a caixa de seleção se você planeja implantar e implementar o recurso de conformidade de Chat persistente opcional e um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ff03f-107">**Enable compliance**: Select the check box if you plan to deploy and implement the optional Persistent Chat compliance feature and database.</span></span>
  
 <span data-ttu-id="ff03f-108">**Use o backup SQL Server armazena para habilitar a recuperação de desastres**: marque essa caixa de seleção se você planeja implantar e implementar a recuperação de desastre do SQL Server de Chat persistente armazena a partir de um conjunto de backup configurado dos repositórios em outro SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ff03f-108">**Use backup SQL Server stores to enable disaster recovery**: Select this check box if you plan to deploy and implement disaster recovery of the Persistent Chat SQL Server stores from a configured backup set of stores on another SQL Server.</span></span> <span data-ttu-id="ff03f-109">Para obter detalhes, consulte [Configure alta disponibilidade e recuperação de desastres para o servidor de Chat persistente no Skype para Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="ff03f-109">For details, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ff03f-110">Essa opção está disponível somente para pools com vários servidores.</span><span class="sxs-lookup"><span data-stu-id="ff03f-110">This option is available only for pools with multiple servers.</span></span> 
  
 <span data-ttu-id="ff03f-111">**Usar este pool como padrão para o site \<sites nesse servidor ou pool que está sendo configurado no\>**: marque essa caixa de seleção se esse será o padrão de servidor de Chat persistente ou o pool de servidor de Chat persistente para o site.</span><span class="sxs-lookup"><span data-stu-id="ff03f-111">**Use this pool as default for the site \<site that this server or pool is being configured in\>**: Select this check box if this will be the default Persistent Chat Server or Persistent Chat Server pool for the site.</span></span> <span data-ttu-id="ff03f-112">Você deve ter um servidor de Chat persistente padrão ou pol por site.</span><span class="sxs-lookup"><span data-stu-id="ff03f-112">You must have one default Persistent Chat server or pol per site.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ff03f-113">Se sua topologia incluir vários sites, uma caixa de seleção para **Usar este pool como o padrão para todos os sites** também será exibida.</span><span class="sxs-lookup"><span data-stu-id="ff03f-113">If your topology includes multiple sites, a checkbox for **Use this pool as default for all sites** is also displayed.</span></span>
  
<span data-ttu-id="ff03f-114">Clique em  **Voltar** para voltar à caixa de diálogo de definição de pool anterior.</span><span class="sxs-lookup"><span data-stu-id="ff03f-114">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="ff03f-115">Clique em **Avançar** depois de concluir a inserção das opções para essa pool a fim de continuar com a definição do pool de servidor de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="ff03f-115">Click **Next** after you have finished entering the options for this pool to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="ff03f-116">Clique em **Cancelar** para descartar todas as alterações e encerrar o assistente **Definir Novo Pool de Chat Persistente**.</span><span class="sxs-lookup"><span data-stu-id="ff03f-116">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="ff03f-117">Clique em **Ajuda** para acessar a ajuda contextual, como esta página.</span><span class="sxs-lookup"><span data-stu-id="ff03f-117">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ff03f-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="ff03f-118">See also</span></span>

[<span data-ttu-id="ff03f-119">Planejar Servidor de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="ff03f-119">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="ff03f-120">Adicionar servidor de Chat persistente à sua Skype para a topologia de negócios Server 2015</span><span class="sxs-lookup"><span data-stu-id="ff03f-120">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
