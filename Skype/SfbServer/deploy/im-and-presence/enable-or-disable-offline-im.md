---
title: Habilitar ou desabilitar mensagens instantâneas (IM) offline no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: Saiba como habilitar ou desabilitar mensagens instantâneas (IM) offline no Skype for Business Server.
ms.openlocfilehash: 02056618aff8a2dcaa6edc2023b67ad38aa9f314
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003041"
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a><span data-ttu-id="4b7f0-103">Habilitar ou desabilitar mensagens instantâneas (IM) offline no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4b7f0-103">Enable or Disable Offline Instant Messaging (IM) in Skype for Business Server</span></span>
 
<span data-ttu-id="4b7f0-104">Saiba como habilitar ou desabilitar mensagens instantâneas (IM) offline no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4b7f0-104">Learn to enable or disable Offline Instant Messaging (IM) in Skype for Business Server.</span></span>
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a><span data-ttu-id="4b7f0-105">Habilitar mensagens instantâneas offline no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4b7f0-105">Enable Offline Instant Messaging (IM) in Skype for Business Server</span></span>

<span data-ttu-id="4b7f0-106">As mensagens instantâneas offline são um recurso do lado do cliente incorporado ao cliente Skype for Business (2016 C2R Build 16.0.6701.1000 ou superior) que aproveita os serviços Web do Exchange (EWS) para enviar mensagens do cliente Skype for Business para a caixa de correio do Exchange de um usuário.</span><span class="sxs-lookup"><span data-stu-id="4b7f0-106">Offline IM is a client side feature built into Skype for Business client (2016 C2R build 16.0.6701.1000 or higher) that leverages Exchange Web Services (EWS) to send messages from the Skype for Business client to a user's Exchange mailbox.</span></span> <span data-ttu-id="4b7f0-107">As mensagens INSTANTÂNEAs offline usam o EWS (Exchange Web Services) para enviar mensagens offline do cliente Skype for Business para a caixa de correio do destinatário.</span><span class="sxs-lookup"><span data-stu-id="4b7f0-107">Offline IM uses Exchange Web Services (EWS) to send Offline messages from the Skype for Business client to the mailbox of recipient.</span></span> <span data-ttu-id="4b7f0-108">O EWS deve estar disponível para o cliente Skype for Business para que as mensagens offline sejam enviadas.</span><span class="sxs-lookup"><span data-stu-id="4b7f0-108">EWS must be available to the Skype for Business client for Offline messages to be sent.</span></span> <span data-ttu-id="4b7f0-109">Para saber mais sobre como planejar mensagens instantâneas e presença, consulte [planejar mensagens instantâneas e presença no Skype for Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="4b7f0-109">To learn more about planning for instant messaging and presence, see [Plan for instant messaging and presence in Skype for Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="4b7f0-110">Se a caixa de correio do usuário estiver hospedada no Exchange local, será necessário o cliente Skype for Business (2016 C2R Build 16.0.6920.1000)</span><span class="sxs-lookup"><span data-stu-id="4b7f0-110">If the user's mailbox is hosted in Exchange On-Premises, the Skype for Business client (2016 C2R build 16.0.6920.1000) is required</span></span> 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a><span data-ttu-id="4b7f0-111">Para habilitar ou desabilitar mensagens instantâneas offline no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4b7f0-111">To enable or disable Offline IM in Skype for Business Server</span></span>

1. <span data-ttu-id="4b7f0-112">Abra o Shell de gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4b7f0-112">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="4b7f0-113">Execute o comando a seguir para habilitar o IM Offline.</span><span class="sxs-lookup"><span data-stu-id="4b7f0-113">Run the following command to enable Offline IM.</span></span>
    
   ```powershell
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > <span data-ttu-id="4b7f0-114">No Skype for Business Server 2015 CU3, a opção EnableOfflineIM é definida como $True por padrão.</span><span class="sxs-lookup"><span data-stu-id="4b7f0-114">In Skype for Business Server 2015 CU3, the EnableOfflineIM option is set to $True by default.</span></span> <span data-ttu-id="4b7f0-115">Para desabilitá-la, defina esse valor como $False.</span><span class="sxs-lookup"><span data-stu-id="4b7f0-115">To disable, set this value to $False.</span></span> 
  
3. <span data-ttu-id="4b7f0-116">Execute o seguinte comando para confirmar se o recurso armazenar mensagens de chat offline está definido.</span><span class="sxs-lookup"><span data-stu-id="4b7f0-116">Run the following command to confirm the ability to store Offline IM's is set.</span></span>
    
   ```powershell
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a><span data-ttu-id="4b7f0-117">Integração do IM Offline com o Exchange</span><span class="sxs-lookup"><span data-stu-id="4b7f0-117">Offline IM Integration with Exchange</span></span>

<span data-ttu-id="4b7f0-p103">O IM Offline não estará disponível para os remetentes se eles tiverem uma política de cliente que desabilite o salvamento automático de mensagens offline na pasta do histórico da conversa (EnableIMAutoArchiving = $false). Não há nenhum mecanismo para verificar se o destinatário é capaz de receber mensagens offline.</span><span class="sxs-lookup"><span data-stu-id="4b7f0-p103">Offline IM will not be available to senders if they have a client policy that disables automatic saving of Offline messages to the conversation history folder (EnableIMAutoArchiving = $false). There is no mechanism to check if the recipient is able to receive Offline messages.</span></span>
  
<span data-ttu-id="4b7f0-120">Para mensagens offline enviadas dentro da mesma organização, elas serão recebidas como uma mensagem de email com classe de mensagem de mensagem instantânea. Note. MissedConversation e será incluído na pasta de **conversa perdida** do Outlook, bem como histórico de conversas que será retirado na guia lista/histórico de conversas recentes dos clientes do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="4b7f0-120">For Offline messages sent within the same organization they will be received as an email message with message class of IM.Note.MissedConversation and will be included in Outlook **Missed Conversation** folder, as well as conversation history which will be picked up in recent list/conversation history tab in Skype for Business clients.</span></span>
  
<span data-ttu-id="4b7f0-121">Para mensagens offline enviadas de organização federada, elas serão recebidas como mensagens de email sem IM.Note.MisssedConversation e não serão incluídas nas pastas de histórico da conversa nem de conversas perdidas.</span><span class="sxs-lookup"><span data-stu-id="4b7f0-121">For Offline messages sent from federated organization they will be received as an email message without IM.Note.MisssedConversation and will not be picked up in the missed conversation or conversation history folders.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="4b7f0-122">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="4b7f0-122">Troubleshooting</span></span>

<span data-ttu-id="4b7f0-123">Há um temporizador de dois minutos quando uma mensagem offline é enviada quando é retirada e processada.</span><span class="sxs-lookup"><span data-stu-id="4b7f0-123">There is a two minute timer from when an offline message is sent to when it's picked up and processed.</span></span> <span data-ttu-id="4b7f0-124">Se não for possível processar mensagens offline, elas aparecerão no seguinte diretório:</span><span class="sxs-lookup"><span data-stu-id="4b7f0-124">If offline messages can't be processed they will appear in the following directory:</span></span> 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

<span data-ttu-id="4b7f0-125">O log de ETL principal do Skype for Business conterá informações sobre o processamento de mensagens offline e será a melhor fonte de investigação/solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="4b7f0-125">The primary Skype for Business ETL log will contain information about Offline message processing and is your best source for investigation/troubleshooting.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="4b7f0-p105">Foi relatado um problema em que as mensagens offline não eram enviadas e a pasta "Rascunhos" era preenchida com mensagens. Isso ocorria em caixas de correio do Exchange no Local. O problema foi resolvido em todos os canais C2R em 14/06/2016. </span><span class="sxs-lookup"><span data-stu-id="4b7f0-p105">An issue has been reported where Offline messages failed to send and the 'Drafts' folder was getting filled with messages. This occurred with Exchange On-Premises mailboxes. The issue has been fixed in all C2R channels as of 6/14/2016.</span></span>  
