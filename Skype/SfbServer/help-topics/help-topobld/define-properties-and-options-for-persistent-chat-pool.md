---
title: Definir Propriedades e Opções para Pool de Chat Persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 'Você configura as opções do seu servidor de chat persistente ou pool de servidores de chat persistente definindo as seguintes propriedades:'
ms.openlocfilehash: 39816bcc4c76a5be07e90c63dfa9064c4a0670d9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820183"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a><span data-ttu-id="a46e2-103">Definir Propriedades e Opções para Pool de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="a46e2-103">Define Properties and Options for Persistent Chat Pool</span></span>
 
<span data-ttu-id="a46e2-104">Você configura as opções do seu servidor de chat persistente ou pool de servidores de chat persistente definindo as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="a46e2-104">You configure options for your Persistent Chat Server or Persistent Chat Server pool by defining the following properties:</span></span>
  
 <span data-ttu-id="a46e2-105">**Exibir o nome do pool de chat persistente**: uma propriedade necessária que define um nome de usuário amigável que será exibido para este servidor de chat persistente ou pool de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="a46e2-105">**Display name of the Persistent Chat pool**: A required property that defines a user friendly name that will be displayed for this Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="a46e2-106">**Porta de chat persistente**: uma propriedade necessária que definirá o número da porta que esse servidor de chat persistente ou o pool de servidores de chat persistente escutará.</span><span class="sxs-lookup"><span data-stu-id="a46e2-106">**Persistent Chat port**: A required property that will define the port number that this Persistent Chat Server or Persistent Chat Server pool will listen on.</span></span>
  
 <span data-ttu-id="a46e2-107">**Habilitar a conformidade**: marque a caixa de seleção se você planeja implantar e implementar o recurso de conformidade de chat persistente opcional e o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a46e2-107">**Enable compliance**: Select the check box if you plan to deploy and implement the optional Persistent Chat compliance feature and database.</span></span>
  
 <span data-ttu-id="a46e2-108">**Use as lojas de backup do SQL Server para habilitar a recuperação de desastres**: Marque esta caixa de seleção se você planeja implantar e implementar a recuperação de desastres dos repositórios persistentes do SQL Server de um conjunto de backup configurado de armazenamentos em outro SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a46e2-108">**Use backup SQL Server stores to enable disaster recovery**: Select this check box if you plan to deploy and implement disaster recovery of the Persistent Chat SQL Server stores from a configured backup set of stores on another SQL Server.</span></span> <span data-ttu-id="a46e2-109">Para obter detalhes, consulte [Configurar alta disponibilidade e recuperação de desastre para servidor de chat persistente no Skype for Business server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="a46e2-109">For details, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a46e2-110">Essa opção está disponível somente para pools com vários servidores.</span><span class="sxs-lookup"><span data-stu-id="a46e2-110">This option is available only for pools with multiple servers.</span></span> 
  
 <span data-ttu-id="a46e2-111">**Use este pool como padrão para o site \<do site em\>que esse servidor ou pool está sendo configurado**: Marque esta caixa de seleção se este for o servidor de chat persistente ou o pool de servidores de chat persistentes padrão do site.</span><span class="sxs-lookup"><span data-stu-id="a46e2-111">**Use this pool as default for the site \<site that this server or pool is being configured in\>**: Select this check box if this will be the default Persistent Chat Server or Persistent Chat Server pool for the site.</span></span> <span data-ttu-id="a46e2-112">Você deve ter um servidor de chat persistente ou uma pol padrão por site.</span><span class="sxs-lookup"><span data-stu-id="a46e2-112">You must have one default Persistent Chat server or pol per site.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a46e2-113">Se sua topologia incluir vários sites, uma caixa de seleção para **Usar este pool como o padrão para todos os sites** também será exibida.</span><span class="sxs-lookup"><span data-stu-id="a46e2-113">If your topology includes multiple sites, a checkbox for **Use this pool as default for all sites** is also displayed.</span></span>
  
<span data-ttu-id="a46e2-114">Clique em  **Voltar** para voltar à caixa de diálogo de definição de pool anterior.</span><span class="sxs-lookup"><span data-stu-id="a46e2-114">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="a46e2-115">Clique em **Avançar** após terminar de inserir as opções desse pool para continuar com a definição do pool de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="a46e2-115">Click **Next** after you have finished entering the options for this pool to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="a46e2-116">Clique em **Cancelar** para descartar todas as alterações e encerrar o assistente **Definir Novo Pool de Chat Persistente**.</span><span class="sxs-lookup"><span data-stu-id="a46e2-116">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="a46e2-117">Clique em **Ajuda** para acessar a ajuda contextual, como esta página.</span><span class="sxs-lookup"><span data-stu-id="a46e2-117">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a46e2-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="a46e2-118">See also</span></span>

[<span data-ttu-id="a46e2-119">Planejar Servidor de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a46e2-119">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="a46e2-120">Adicionar um servidor de chat persistente à sua topologia do Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a46e2-120">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
