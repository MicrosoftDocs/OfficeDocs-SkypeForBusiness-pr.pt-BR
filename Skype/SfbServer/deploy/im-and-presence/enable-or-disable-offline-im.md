---
title: Habilitar ou desabilitar Offline mensagens instantâneas (IM) no Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: Aprenda a habilitar ou desabilitar Offline as mensagens Instantâneas no Skype para Business Server.
ms.openlocfilehash: fe3ce34fed4890c494fc987a4fc82ad5faf62764
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894413"
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a><span data-ttu-id="241ad-103">Habilitar ou desabilitar Offline mensagens instantâneas (IM) no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="241ad-103">Enable or Disable Offline Instant Messaging (IM) in Skype for Business Server</span></span>
 
<span data-ttu-id="241ad-104">Aprenda a habilitar ou desabilitar Offline as mensagens Instantâneas no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="241ad-104">Learn to enable or disable Offline Instant Messaging (IM) in Skype for Business Server.</span></span>
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a><span data-ttu-id="241ad-105">Habilitar Offline mensagens instantâneas (IM) no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="241ad-105">Enable Offline Instant Messaging (IM) in Skype for Business Server</span></span>

<span data-ttu-id="241ad-106">Mensagens Instantâneas offline são um recurso do lado cliente incorporado ao Skype para o cliente de negócios (2016 C2R build 16.0.6701.1000 ou superior) que aproveita os serviços de Web do Exchange (EWS) para enviar mensagens do Skype para o cliente de negócios, caixa de correio do Exchange do usuário.</span><span class="sxs-lookup"><span data-stu-id="241ad-106">Offline IM is a client side feature built into Skype for Business client (2016 C2R build 16.0.6701.1000 or higher) that leverages Exchange Web Services (EWS) to send messages from the Skype for Business client to a user's Exchange mailbox.</span></span> <span data-ttu-id="241ad-107">Offline IM usa serviços Web do Exchange (EWS) para enviar mensagens Offline do Skype para o cliente de negócios para a caixa de correio do destinatário.</span><span class="sxs-lookup"><span data-stu-id="241ad-107">Offline IM uses Exchange Web Services (EWS) to send Offline messages from the Skype for Business client to the mailbox of recipient.</span></span> <span data-ttu-id="241ad-108">EWS deve estar disponível para o Skype para o cliente de negócios para mensagens Offline a serem enviadas.</span><span class="sxs-lookup"><span data-stu-id="241ad-108">EWS must be available to the Skype for Business client for Offline messages to be sent.</span></span> <span data-ttu-id="241ad-109">Para saber mais sobre o planejamento de mensagens instantâneas e presença, consulte [Planejar a mensagens instantâneas e presença no Skype para Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="241ad-109">To learn more about planning for instant messaging and presence, see [Plan for instant messaging and presence in Skype for Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="241ad-110">Se a caixa de correio do usuário está hospedada no Exchange local, o Skype para o cliente de negócios (2016 C2R build 16.0.6920.1000) é necessária</span><span class="sxs-lookup"><span data-stu-id="241ad-110">If the user's mailbox is hosted in Exchange On-Premises, the Skype for Business client (2016 C2R build 16.0.6920.1000) is required</span></span> 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a><span data-ttu-id="241ad-111">Para habilitar ou desabilitar Offline mensagens Instantâneas no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="241ad-111">To enable or disable Offline IM in Skype for Business Server</span></span>

1. <span data-ttu-id="241ad-112">Abra o Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="241ad-112">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="241ad-113">Execute o comando a seguir para habilitar o IM Offline.</span><span class="sxs-lookup"><span data-stu-id="241ad-113">Run the following command to enable Offline IM.</span></span>
    
   ```
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > <span data-ttu-id="241ad-114">No Skype para Business Server 2015 CU3, a opção de EnableOfflineIM é definida como $True, por padrão.</span><span class="sxs-lookup"><span data-stu-id="241ad-114">In Skype for Business Server 2015 CU3, the EnableOfflineIM option is set to $True by default.</span></span> <span data-ttu-id="241ad-115">Para desabilitá-la, defina esse valor como $False.</span><span class="sxs-lookup"><span data-stu-id="241ad-115">To disable, set this value to $False.</span></span> 
  
3. <span data-ttu-id="241ad-116">Execute o seguinte comando para confirmar a capacidade de armazenar Offline IM estiver definida.</span><span class="sxs-lookup"><span data-stu-id="241ad-116">Run the following command to confirm the ability to store Offline IM's is set.</span></span>
    
   ```
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a><span data-ttu-id="241ad-117">Integração do IM Offline com o Exchange</span><span class="sxs-lookup"><span data-stu-id="241ad-117">Offline IM Integration with Exchange</span></span>

<span data-ttu-id="241ad-p103">O IM Offline não estará disponível para os remetentes se eles tiverem uma política de cliente que desabilite o salvamento automático de mensagens offline na pasta do histórico da conversa (EnableIMAutoArchiving = $false). Não há nenhum mecanismo para verificar se o destinatário é capaz de receber mensagens offline.</span><span class="sxs-lookup"><span data-stu-id="241ad-p103">Offline IM will not be available to senders if they have a client policy that disables automatic saving of Offline messages to the conversation history folder (EnableIMAutoArchiving = $false). There is no mechanism to check if the recipient is able to receive Offline messages.</span></span>
  
<span data-ttu-id="241ad-120">Para Offline mensagens enviadas dentro da mesma organização que eles serão recebidos como uma mensagem de email com a classe de mensagem das mensagens Instantâneas. Note.MissedConversation e será incluído na pasta do Outlook **Conversas perdidas** , bem como histórico da conversa que será obtido no guia de histórico de lista/conversa recente do Skype para clientes corporativos.</span><span class="sxs-lookup"><span data-stu-id="241ad-120">For Offline messages sent within the same organization they will be received as an email message with message class of IM.Note.MissedConversation and will be included in Outlook **Missed Conversation** folder, as well as conversation history which will be picked up in recent list/conversation history tab in Skype for Business clients.</span></span>
  
<span data-ttu-id="241ad-121">Para mensagens offline enviadas de organização federada, elas serão recebidas como mensagens de email sem IM.Note.MisssedConversation e não serão incluídas nas pastas de histórico da conversa nem de conversas perdidas.</span><span class="sxs-lookup"><span data-stu-id="241ad-121">For Offline messages sent from federated organization they will be received as an email message without IM.Note.MisssedConversation and will not be picked up in the missed conversation or conversation history folders.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="241ad-122">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="241ad-122">Troubleshooting</span></span>

<span data-ttu-id="241ad-123">Não há um timer minuto dois quando uma mensagem offline é enviado a quando ele tem buscadas e processadas.</span><span class="sxs-lookup"><span data-stu-id="241ad-123">There is a two minute timer from when an offline message is sent to when it's picked up and processed.</span></span> <span data-ttu-id="241ad-124">Se mensagens offline não podem ser processadas, eles aparecerão no seguinte diretório:</span><span class="sxs-lookup"><span data-stu-id="241ad-124">If offline messages can't be processed they will appear in the following directory:</span></span> 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

<span data-ttu-id="241ad-125">O Skype principal para o log de negócios ETL irá conter informações sobre o processamento de mensagens Offline e é a melhor fonte para solução de problemas/investigação.</span><span class="sxs-lookup"><span data-stu-id="241ad-125">The primary Skype for Business ETL log will contain information about Offline message processing and is your best source for investigation/troubleshooting.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="241ad-p105">Foi relatado um problema em que as mensagens offline não eram enviadas e a pasta "Rascunhos" era preenchida com mensagens. Isso ocorria em caixas de correio do Exchange no Local. O problema foi resolvido em todos os canais C2R em 14/06/2016. </span><span class="sxs-lookup"><span data-stu-id="241ad-p105">An issue has been reported where Offline messages failed to send and the 'Drafts' folder was getting filled with messages. This occurred with Exchange On-Premises mailboxes. The issue has been fixed in all C2R channels as of 6/14/2016.</span></span>  
