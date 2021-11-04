---
title: Habilitar ou desabilitar mensagens instantâneas offline (IM) em Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: Saiba como habilitar ou desabilitar o IM (Mensagens Instantâneas Offline) Skype for Business Server.
ms.openlocfilehash: 36894fb2a1ed11428b21b572a28e9ac177a4237d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60753323"
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a>Habilitar ou desabilitar mensagens instantâneas offline (IM) em Skype for Business Server
 
Saiba como habilitar ou desabilitar o IM (Mensagens Instantâneas Offline) Skype for Business Server.
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a>Habilitar mensagens instantâneas offline (IM) em Skype for Business Server

O IM offline é um recurso do lado do cliente integrado ao cliente do Skype for Business (2016 C2R build 16.0.6701.1000 ou superior) que aproveita o Exchange Web Services (EWS) para enviar mensagens do cliente Skype for Business para a caixa de correio Exchange do usuário. O IM offline usa Exchange Web Services (EWS) para enviar mensagens offline do cliente Skype for Business para a caixa de correio do destinatário. O EWS deve estar disponível para o cliente Skype for Business mensagens offline a serem enviadas. Para saber mais sobre o planejamento de mensagens instantâneas e presença, consulte [Plan for instant messaging and presence in Skype for Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).
  
> [!NOTE]
> Se Exchange caixa de correio do usuário estiver hospedada no local, o cliente Skype for Business (build 16.0.6920.1000) do Skype for Business (build 16.0.6920.1000) 2016 (build 16.0.6920.1000) será necessário 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a>Para habilitar ou desabilitar o IM Offline Skype for Business Server

1. Abra o Shell Skype for Business Server Gerenciamento.
    
2. Execute o seguinte comando para habilitar o IM Offline.
    
   ```powershell
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > No Skype for Business Server 2015 CU3, a opção EnableOfflineIM é definida como $True por padrão. Para desabilitar, de definir esse valor como $False. 
  
3. Execute o seguinte comando para confirmar se a capacidade de armazenar IMs offline está definida.
    
   ```powershell
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a>Integração de IM Offline com Exchange

O IM offline não estará disponível para os envios se eles têm uma política de cliente que desabilita o armazenamento automático de mensagens Offline na pasta de histórico de conversas (EnableIMAutoArchiving = $false). Não há mecanismo para verificar se o destinatário é capaz de receber mensagens Offline.
  
Para mensagens offline enviadas na mesma organização, elas serão recebidas como uma mensagem de email com **classe** de mensagem de IM.Note.MissedConversation e serão incluídas na pasta Conversa Perdida do Outlook, bem como no histórico da conversa que será escolhido na guia histórico de lista/conversa recente nos clientes Skype for Business.
  
Para mensagens offline enviadas da organização federada, elas serão recebidas como uma mensagem de email sem IM.Note.MisssedConversation e não serão escolhidas nas pastas de histórico de conversas ou conversas perdidas. 
  
## <a name="troubleshooting"></a>Solução de problemas

Há um temporizador de dois minutos a partir de quando uma mensagem offline é enviada para quando ela é escolhida e processada. Se as mensagens offline não puderem ser processadas, elas aparecerão no seguinte diretório: 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

O log Skype for Business ETL principal conterá informações sobre o processamento de mensagens offline e é sua melhor fonte para investigação/solução de problemas. 
  
> [!NOTE]
> Um problema foi relatado em que as mensagens offline não foram enviadas e a pasta 'Rascunhos' estava sendo preenchida com mensagens. Isso ocorreu com Exchange caixas de correio locais. O problema foi corrigido em todos os canais C2R a partir de 14/06/2016.  
