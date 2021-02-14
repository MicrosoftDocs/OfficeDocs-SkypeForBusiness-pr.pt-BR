---
title: Habilitar ou desabilitar mensagens instantâneas offline (IM) no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: Aprenda a habilitar ou desabilitar o IM (Sistema de Mensagens Instantâneas) Offline no Skype for Business Server.
ms.openlocfilehash: 510ebe65e60b9ea12d2f368b0e2d33c705b8d0d6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801941"
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a><span data-ttu-id="57905-103">Habilitar ou desabilitar mensagens instantâneas offline (IM) no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="57905-103">Enable or Disable Offline Instant Messaging (IM) in Skype for Business Server</span></span>
 
<span data-ttu-id="57905-104">Aprenda a habilitar ou desabilitar o IM (Sistema de Mensagens Instantâneas) Offline no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="57905-104">Learn to enable or disable Offline Instant Messaging (IM) in Skype for Business Server.</span></span>
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a><span data-ttu-id="57905-105">Habilitar mensagens instantâneas offline (IM) no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="57905-105">Enable Offline Instant Messaging (IM) in Skype for Business Server</span></span>

<span data-ttu-id="57905-106">O IM offline é um recurso do lado do cliente integrado ao cliente Skype for Business (build 16.0.6701.1000 ou superior do 2016 C2R) que aproveita os Serviços Web do Exchange (EWS) para enviar mensagens do cliente Skype for Business para a caixa de correio do Exchange de um usuário.</span><span class="sxs-lookup"><span data-stu-id="57905-106">Offline IM is a client side feature built into Skype for Business client (2016 C2R build 16.0.6701.1000 or higher) that leverages Exchange Web Services (EWS) to send messages from the Skype for Business client to a user's Exchange mailbox.</span></span> <span data-ttu-id="57905-107">O IM offline usa os Serviços Web do Exchange (EWS) para enviar mensagens offline do cliente Skype for Business para a caixa de correio do destinatário.</span><span class="sxs-lookup"><span data-stu-id="57905-107">Offline IM uses Exchange Web Services (EWS) to send Offline messages from the Skype for Business client to the mailbox of recipient.</span></span> <span data-ttu-id="57905-108">O EWS deve estar disponível para o cliente Skype for Business para que as mensagens offline sejam enviadas.</span><span class="sxs-lookup"><span data-stu-id="57905-108">EWS must be available to the Skype for Business client for Offline messages to be sent.</span></span> <span data-ttu-id="57905-109">Para saber mais sobre o planejamento de mensagens instantâneas e presença, consulte Planejar mensagens instantâneas e [presença no Skype for Business Server.](../../plan-your-deployment/instant-messaging-and-presence.md)</span><span class="sxs-lookup"><span data-stu-id="57905-109">To learn more about planning for instant messaging and presence, see [Plan for instant messaging and presence in Skype for Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="57905-110">Se a caixa de correio do usuário estiver hospedada no Exchange Local, o cliente Skype for Business (2016 C2R build 16.0.6920.1000) será necessário</span><span class="sxs-lookup"><span data-stu-id="57905-110">If the user's mailbox is hosted in Exchange On-Premises, the Skype for Business client (2016 C2R build 16.0.6920.1000) is required</span></span> 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a><span data-ttu-id="57905-111">Para habilitar ou desabilitar o IM Offline no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="57905-111">To enable or disable Offline IM in Skype for Business Server</span></span>

1. <span data-ttu-id="57905-112">Abra o Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="57905-112">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="57905-113">Execute o seguinte comando para habilitar o IM Offline.</span><span class="sxs-lookup"><span data-stu-id="57905-113">Run the following command to enable Offline IM.</span></span>
    
   ```powershell
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > <span data-ttu-id="57905-114">No Skype for Business Server 2015 CU3, a opção EnableOfflineIM é definida como $True por padrão.</span><span class="sxs-lookup"><span data-stu-id="57905-114">In Skype for Business Server 2015 CU3, the EnableOfflineIM option is set to $True by default.</span></span> <span data-ttu-id="57905-115">Para desabilitar, de definir esse valor como $False.</span><span class="sxs-lookup"><span data-stu-id="57905-115">To disable, set this value to $False.</span></span> 
  
3. <span data-ttu-id="57905-116">Execute o seguinte comando para confirmar se a capacidade de armazenar as IMs Offline está definida.</span><span class="sxs-lookup"><span data-stu-id="57905-116">Run the following command to confirm the ability to store Offline IM's is set.</span></span>
    
   ```powershell
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a><span data-ttu-id="57905-117">Integração de IM Offline com o Exchange</span><span class="sxs-lookup"><span data-stu-id="57905-117">Offline IM Integration with Exchange</span></span>

<span data-ttu-id="57905-118">O IM offline não estará disponível para os envios se eles têm uma política de cliente que desabilita o salvar automático de mensagens Offline na pasta do histórico da conversa (EnableIMAutoArchiving = $false).</span><span class="sxs-lookup"><span data-stu-id="57905-118">Offline IM will not be available to senders if they have a client policy that disables automatic saving of Offline messages to the conversation history folder (EnableIMAutoArchiving = $false).</span></span> <span data-ttu-id="57905-119">Não há mecanismo para verificar se o destinatário é capaz de receber mensagens Offline.</span><span class="sxs-lookup"><span data-stu-id="57905-119">There is no mechanism to check if the recipient is able to receive Offline messages.</span></span>
  
<span data-ttu-id="57905-120">Para mensagens offline enviadas dentro da mesma organização, elas serão recebidas como uma mensagem de email com classe de mensagem de IM.Note.MissedConversation e serão incluídas na pasta Conversa Perdida do **Outlook,** bem como no histórico da conversa que será escolhido na guia de histórico de conversa/lista recente no Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="57905-120">For Offline messages sent within the same organization they will be received as an email message with message class of IM.Note.MissedConversation and will be included in Outlook **Missed Conversation** folder, as well as conversation history which will be picked up in recent list/conversation history tab in Skype for Business clients.</span></span>
  
<span data-ttu-id="57905-121">Para mensagens offline enviadas de uma organização federada, elas serão recebidas como uma mensagem de email sem IM.Note.MisssedConversation e não serão escolhidas nas pastas de histórico da conversa ou da conversa perdida.</span><span class="sxs-lookup"><span data-stu-id="57905-121">For Offline messages sent from federated organization they will be received as an email message without IM.Note.MisssedConversation and will not be picked up in the missed conversation or conversation history folders.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="57905-122">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="57905-122">Troubleshooting</span></span>

<span data-ttu-id="57905-123">Há um temporizador de dois minutos a partir do momento em que uma mensagem offline é enviada para quando ela é escolhida e processada.</span><span class="sxs-lookup"><span data-stu-id="57905-123">There is a two minute timer from when an offline message is sent to when it's picked up and processed.</span></span> <span data-ttu-id="57905-124">Se as mensagens offline não puderem ser processadas, elas aparecerão no seguinte diretório:</span><span class="sxs-lookup"><span data-stu-id="57905-124">If offline messages can't be processed they will appear in the following directory:</span></span> 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

<span data-ttu-id="57905-125">O log de ETL principal do Skype for Business conterá informações sobre o processamento de mensagens offline e é sua melhor fonte para investigação/solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="57905-125">The primary Skype for Business ETL log will contain information about Offline message processing and is your best source for investigation/troubleshooting.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="57905-126">Foi relatado um problema em que as mensagens offline não foram enviadas e a pasta "Rascunhos" foi preenchida com mensagens.</span><span class="sxs-lookup"><span data-stu-id="57905-126">An issue has been reported where Offline messages failed to send and the 'Drafts' folder was getting filled with messages.</span></span> <span data-ttu-id="57905-127">Isso ocorreu com caixas de correio locais do Exchange.</span><span class="sxs-lookup"><span data-stu-id="57905-127">This occurred with Exchange On-Premises mailboxes.</span></span> <span data-ttu-id="57905-128">O problema foi corrigido em todos os canais C2R desde 14/06/2016.</span><span class="sxs-lookup"><span data-stu-id="57905-128">The issue has been fixed in all C2R channels as of 6/14/2016.</span></span>  
