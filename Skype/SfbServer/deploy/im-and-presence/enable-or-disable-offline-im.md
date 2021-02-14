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
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a>Habilitar ou desabilitar mensagens instantâneas offline (IM) no Skype for Business Server
 
Aprenda a habilitar ou desabilitar o IM (Sistema de Mensagens Instantâneas) Offline no Skype for Business Server.
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a>Habilitar mensagens instantâneas offline (IM) no Skype for Business Server

O IM offline é um recurso do lado do cliente integrado ao cliente Skype for Business (build 16.0.6701.1000 ou superior do 2016 C2R) que aproveita os Serviços Web do Exchange (EWS) para enviar mensagens do cliente Skype for Business para a caixa de correio do Exchange de um usuário. O IM offline usa os Serviços Web do Exchange (EWS) para enviar mensagens offline do cliente Skype for Business para a caixa de correio do destinatário. O EWS deve estar disponível para o cliente Skype for Business para que as mensagens offline sejam enviadas. Para saber mais sobre o planejamento de mensagens instantâneas e presença, consulte Planejar mensagens instantâneas e [presença no Skype for Business Server.](../../plan-your-deployment/instant-messaging-and-presence.md)
  
> [!NOTE]
> Se a caixa de correio do usuário estiver hospedada no Exchange Local, o cliente Skype for Business (2016 C2R build 16.0.6920.1000) será necessário 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a>Para habilitar ou desabilitar o IM Offline no Skype for Business Server

1. Abra o Shell de Gerenciamento do Skype for Business Server.
    
2. Execute o seguinte comando para habilitar o IM Offline.
    
   ```powershell
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > No Skype for Business Server 2015 CU3, a opção EnableOfflineIM é definida como $True por padrão. Para desabilitar, de definir esse valor como $False. 
  
3. Execute o seguinte comando para confirmar se a capacidade de armazenar as IMs Offline está definida.
    
   ```powershell
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a>Integração de IM Offline com o Exchange

O IM offline não estará disponível para os envios se eles têm uma política de cliente que desabilita o salvar automático de mensagens Offline na pasta do histórico da conversa (EnableIMAutoArchiving = $false). Não há mecanismo para verificar se o destinatário é capaz de receber mensagens Offline.
  
Para mensagens offline enviadas dentro da mesma organização, elas serão recebidas como uma mensagem de email com classe de mensagem de IM.Note.MissedConversation e serão incluídas na pasta Conversa Perdida do **Outlook,** bem como no histórico da conversa que será escolhido na guia de histórico de conversa/lista recente no Skype for Business.
  
Para mensagens offline enviadas de uma organização federada, elas serão recebidas como uma mensagem de email sem IM.Note.MisssedConversation e não serão escolhidas nas pastas de histórico da conversa ou da conversa perdida. 
  
## <a name="troubleshooting"></a>Solução de problemas

Há um temporizador de dois minutos a partir do momento em que uma mensagem offline é enviada para quando ela é escolhida e processada. Se as mensagens offline não puderem ser processadas, elas aparecerão no seguinte diretório: 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

O log de ETL principal do Skype for Business conterá informações sobre o processamento de mensagens offline e é sua melhor fonte para investigação/solução de problemas. 
  
> [!NOTE]
> Foi relatado um problema em que as mensagens offline não foram enviadas e a pasta "Rascunhos" foi preenchida com mensagens. Isso ocorreu com caixas de correio locais do Exchange. O problema foi corrigido em todos os canais C2R desde 14/06/2016.  
